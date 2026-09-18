## Niraj Patel

I make AI engineering accountable, in an industry where "it seems better" is not an acceptable answer.

I built the AI engineering practice on a regulated clinical platform. Most of what I build serves one idea. A claim about a software system should be checkable by someone who does not trust the person making it.

That turns out to be the same discipline at three altitudes.

- **Under regulation.** Shipping an agent is easy. The hard part is shipping one inside a validated, audited software lifecycle, with traceability, verification evidence, human approval gates, and an auditor who can ask you to prove it. That is where I work.
- **Across an organisation.** A company does not adopt AI engineering by buying licences. It adopts by installing a layer of skills, quality gates, conventions and connectors that every engineer inherits by default, so one person's context becomes everyone's starting point.
- **In the work itself.** Teams improve agent systems on assertion far more often than on measurement. I build the harnesses that settle the question, including the ones designed to return a result I would rather not see.

### Two things you can run

**[evidence-as-a-build-output](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output)**. A service and its complete validation package, emitted from one specification in one run: requirements, risk register, generated tests, traceability matrix, summary report. Two runs of the same input are byte-identical. Break the service and the report says so in its first line, then exits non-zero. Node 24, no dependencies.

**[agent-memory-proving-ground](https://github.com/NirajPatel-AI-PM/agent-memory-proving-ground)**. Three agents identical except for how they remember. A blinded judge scores them against the same probes on a pinned rubric. One probe has no correct answer, so the scoring penalises an arm that improves by becoming more confident. The published run reports a tie between the sophisticated arm and the naive one, and says which layer failed and why. Node 24, no dependencies.

### How I think about problems

- [The operating system for an AI-adopting team](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output/blob/main/essays/operating-system-for-an-ai-adopting-team.md). Knowledge in a wiki does not get used. Knowledge that loads itself at the moment of relevance does.
- [Prove it or it didn't happen](https://github.com/NirajPatel-AI-PM/agent-memory-proving-ground). Why agent improvements go unmeasured, and what measuring one costs.
- [Evidence as a build output](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output). Nobody has to assemble the validation package by hand, after the fact, from what people remember.
- [Debugging absences](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output/blob/main/essays/debugging-absences.md). The hardest production failures in agent systems leave nothing in the log.
- [What survives when you design for the verifier](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output/blob/main/essays/designing-for-the-verifier.md). A paused research build, never in production, and what building it taught me about how agents should work.

### Selected work

I built these for a regulated clinical platform. None is public, so I describe them in the general case.

- **A study-configuration product, from zero to deployment.** A product for building and running clinical studies on a regulated platform: protocol configuration, participant-facing content, and site workflow. A study team defines a study once and deploys it without a per-study engineering build. I took it from nothing to production. It now runs more than 100 active studies for more than 20 pharmaceutical sponsors, and tens of thousands of participants have enrolled.
- **A shared engineering layer, installed once.** Roughly three dozen skills plus quality gates, workflows and connectors. One idempotent command installs them at user scope, so an entire team inherits the same conventions, including the ones that encode regulatory process.
- **Operator tooling for a multi-environment agent platform.** It promotes an agent and its full dependency closure between environments under a stable identity, so the second run updates instead of duplicating. It also documents a method for diagnosing the failures that present as an absence rather than an error.
- **A deterministic conformance check that replaced a vendor review cycle.** An approved source document and the digital version built from it go in. Out comes either a certificate of conformance or a located finding, byte-identical across runs. A difference matching no ruling blocks the certificate. Quality owns the rulings, the code owns only detection. Writing the standard down was harder than comparing the documents, because the review it replaced had never set one.
- **A factory for integration connectors.** An API document and a change request go in. A deployable connector comes out alongside its complete validation package: requirements, risk assessment, delivery backlog, test evidence, controlled documents. The package traces every artifact to the requirement it satisfies, and stops for human approval at the points where a human must decide. Nobody reconstructs the compliance evidence any more. The run emits it.
- **The same factory, inverted, for inbound events.** A spec goes in. A deployable event-ingest service comes out, and produces its evidence the same way. It is younger and still maturing, and it is the reason I believe the first one was a pattern rather than a script.

### Elsewhere

Open to conversations about building AI systems where the evidence has to hold up, in regulated industries especially.
