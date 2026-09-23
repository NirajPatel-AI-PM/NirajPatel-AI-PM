# Harness engineering

In early July 2026, when Claude Fable 5 was released, I used it to rebuild the memory system for our agent platform. I did the work entirely with Fable 5, and our engineers reviewed the pull requests. The goal was an agent that carries what it learns from one conversation into the next, keeps that knowledge current, and shows its working. Before the engineers reviewed anything, I built an evaluation to show that the new system was better than the old one.

## What the memory is for

Our platform builds agents for clinical trial knowledge work. The people who use these agents tell them things that matter later: how a site works, who signs off on what, what was agreed in the last review. An agent without memory asks again every time.

In a regulated setting, the customer also has to be able to see what the agent believed, when that changed, and which conversation changed it. So the new system never overwrites what it knows. When a fact changes, it closes the old one and links it to the new one, and the full history stays open to inspection.

## How it works

Every conversation is saved as a dated episode while it happens. This is a plain database write, with no model call and no delay to the conversation.

After a conversation goes quiet, a background process reads the episode. It writes a short summary, stops there if the conversation repeats something it already knows, and otherwise pulls out durable facts. For each new fact it decides whether to add it, update a fact it holds, close a fact that is no longer true, or reinforce one it already has. A fixed rule sits in front of that decision. An older conversation can never replace a newer fact, whatever the model decides.

The facts roll up into short profiles, one for the agent and one for each person it works with. On every model call, the agent gets its profiles and the few facts most relevant to what was just asked. Recall combines search by meaning with search by exact words, so site codes and record ids match as well as topics. The amount of memory that reaches the model is capped, so the prompt does not grow as the memory grows.

Shared memory has one more rule. Something one person says about a specific person stays private until a second, independent person says the same thing. Contact details are never shared, and shared memory holds facts, never instructions. One voice cannot change what the agent tells everyone.

Each reasoning step in that process is itself an agent on the platform. The team can inspect and tune how memory summarizes, extracts and decides without a code release.

## Proving it first

I wanted proof before anyone reviewed the code. So I built an evaluation harness. It runs the same probes against three arms: the old memory system, the new one, and a control with no memory at all. Each probe gives the agent a task and scores its answer from 0 to 1.

A run against live connectors put the new system at 0.931 and the old one at 0.658. The control with no memory scored far below both. The gap between the two memory systems is larger than that run's noise floor, the spread you get from running the same arm again. The new system tied or beat the old one on every probe.

## What's next

The memory already notices when people confirm the same thing again, and it gives that fact more weight. The next step is to turn a proven routine into a skill, a named set of instructions the agent follows every time.

The lifecycle has five steps. People repeat a routine, and the agent remembers it. The memory drafts a skill from that routine. A check proves that the skill helps. A person approves it. Then the skill is published into the agent's instructions.

Two parts of that lifecycle need their own measurement. The skills gate comes before publishing. A drafted skill has to pass its test cases before a person is asked to approve it. Skill adherence monitoring comes after publishing. It checks that the agent picks the skill when a request calls for it, and follows the skill once it has picked it.

I built the method for the second part as a separate project, [skill-adherence-eval](https://github.com/NirajPatel-AI-PM/skill-adherence-eval). It scores selection and adherence apart, and it repeats each case to measure the noise floor. The rule is the same as for the memory rebuild. A skill reaches the agent only after a run shows that it helps.
