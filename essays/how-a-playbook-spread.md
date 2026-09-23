# How a playbook spread, and what its memory measures

In January 2026 I started building a shared AI engineering layer for my company. It installs on a person's machine and gives them the skills, checks and workflows the rest of the team already uses with Claude Code. Today over 35 people run it, across product, engineering, forward deployed engineering, documentation and support. That number tells me the layer spread. It does not tell me whether the agents do better work because of it. For that question, the layer has a memory the whole team shares, and I built it to be measured.

## What the layer is

I work at a regulated clinical research company of about 300 people. I built most of the layer myself, with Claude Code. It installs with one command and puts about three dozen skills on a machine, along with subagent definitions, quality gates, code review, workflows, MCP servers and the memory system.

Each part does a different job. A skill loads itself when someone touches the subject it covers, so nobody has to remember to go and read it. A subagent definition describes a specialist, such as a backend developer or a code reviewer, that the main agent can hand part of a task to. Each one has its own instructions and its own tools, and the code reviewer can read code but never change it. A quality gate runs at a fixed point and fails loudly, because some rules cannot depend on the model agreeing to follow them. Code review puts every change in front of reviewer agents before a person sees it, so the person reviews a change that has already been checked once. A workflow is a procedure someone already worked out once, such as producing a release document. An MCP server connects the work to a system of record, so a workflow can create the ticket and attach the evidence itself.

The same command that sets up a machine also updates it. When anyone improves a skill, everyone gets the change on their next update, and nobody copies files between projects.

## Product managers on the layer

Product managers now build, test and release capabilities themselves through spec-driven development. Ten of them ship code. The platform ships two minor releases a month and several hotfixes a month on the layer.

For those ten, a requirement is no longer a document that waits for an engineer to interpret it. The spec is the input the build starts from, and the same gates and workflows that check an engineer's change check theirs. The layer holds everyone's work to one standard, whoever wrote it.

## Bottom up, then top down

It spread bottom up first. Nobody told anyone to install it. People ran it because it did something useful for them, and then they started committing improvements back to it.

I think the order mattered. A mandate on the first day would have produced installs. It would not have produced the improvements. Someone who chose a tool and finds a gap in it fixes the gap in the shared layer, where everyone gets the fix. Someone using a tool because of a mandate finds a gap and works around it on their own machine. That private workaround is the exact problem the layer exists to solve. A team's accumulated knowledge stays in individual heads, and only the people who found the faster way benefit from it.

Top down came second. The CTO and the CPO saw what the layer did for people and how excited people were to use it. Both started using it themselves. Then the CTO started opening pull requests of his own, to improve it and to add new capabilities. So leadership arrived the same way everyone else had. They used it first, and then they improved it.

## What the memory is for

One part of the layer builds MCP connectors, and it runs the same kind of task again and again. Each build teaches something. An API returns errors in an odd format, or a validation step fails for a reason an earlier build already hit. Without memory, the next build learns the same thing again from the start.

The memory system keeps those lessons, and it keeps them for the whole team. It is one shared memory, not one per person or per machine. The lessons live in the shared repository, so a lesson from one person's build reaches everyone's next build when they update. Before a build starts, and again before the verification, validation and document steps, the agent reads the lessons that apply to that step. When a task ends, pass or fail, the agent writes down anything new it learned. A task that taught nothing new writes nothing.

Each lesson is a plain text file in git. People and agents edit them the same way, as small changes anyone can review. Git keeps the history, so every lesson shows when it arrived and what has changed it since.

## What the memory measures

I built the memory to measure itself. Some of the measures come from the lesson files alone. The rest come from a log that gets one line at the end of each task.

The lesson files show four things:

- How many separate releases taught each lesson. The count is of distinct releases, not of writes. If five steps in one release record the same lesson, it counts once, so one data point cannot look like five confirmations.
- Which lessons have earned trust. A warning becomes a standard pattern only after three separate releases teach it.
- Whether the store is still alive. A store that stops getting new or reinforced lessons means people stopped using it.
- Which lessons moved into a skill. When a lesson is stable, it goes into the skill itself, and the lesson file records where it went.

The task log answers the questions the files cannot:

- Is the memory in use? Did the agent read lessons before the task, did the store have any for it, and did the task write anything back?
- Do builds get better? The pass rate for each kind of connector, and how many validation attempts a build needs before it passes.
- Did the memory change what the agent did? If the agent was warned about a known pitfall and then hit it anyway, the memory did not help. If it was warned and avoided the pitfall, it did. This is the measure I care about most.
- What does a build cost? Time and tokens for each successful build, and how much goes on builds that fail.

## Looking back

In under a year, the layer went from a first install to the way more than 35 people across five functions work with Claude Code. People took it up because it helped them, and then they made it better. Leadership joined the same way. The CTO and the CPO used it first, and then the CTO added to it. Ten product managers now ship code on it, held to the same standard as the engineers. The team's knowledge no longer stays in individual heads. Each connector build leaves behind what it learned, in a memory the whole team shares, with measures that show whether that memory makes the next build better.
