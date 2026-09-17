## Niraj Patel

I make AI engineering accountable — in an industry where "it seems better" is not an acceptable answer.

I built the AI engineering practice on a regulated clinical platform. Most of what I build is in service of one idea: a claim about a software system should be checkable by someone who does not trust the person making it.

That turns out to be the same discipline at three altitudes.

- **Under regulation.** Shipping an agent is easy. Shipping one inside a validated, audited software lifecycle — traceability, verification evidence, human approval gates, an auditor who can ask you to prove it — is the hard part, and it is where I work.
- **Across an organisation.** A company does not adopt AI engineering by buying licences. It adopts by installing a layer: skills, quality gates, conventions and connectors that every engineer inherits by default, so one person's hard-won context becomes everyone's starting point.
- **In the work itself.** Agent systems are improved on assertion far more often than on measurement. I build the harnesses that decide the question, including the ones designed to return a result I would rather not see.

### Two things you can run

**[evidence-as-a-build-output](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output)** — a service and its complete validation package, emitted from one specification in one run: requirements, risk register, generated tests, traceability matrix, summary report. Two runs of the same input are byte-identical. Break the service and the report says so, in its first line, and exits non-zero. Node 24, no dependencies.

**[agent-memory-proving-ground](https://github.com/NirajPatel-AI-PM/agent-memory-proving-ground)** — three agents identical except for how they remember, measured against the same probes by a blinded judge on a pinned rubric. One probe has no correct answer, so an arm that improves by becoming more confident is penalised rather than rewarded. The published run reports a **tie** between the sophisticated arm and the naive one, and explains exactly which layer failed and why. Node 24, no dependencies.

### How I think about problems

- [The operating system for an AI-adopting team](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output/blob/main/essays/operating-system-for-an-ai-adopting-team.md) — knowledge in a wiki does not get used; knowledge that loads itself at the moment of relevance does.
- [Prove it or it didn't happen](https://github.com/NirajPatel-AI-PM/agent-memory-proving-ground) — why agent improvements go unmeasured, and what measuring one actually costs.
- [Evidence as a build output](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output) — the validation package does not have to be assembled by hand, after the fact, by people reconstructing what happened.
- [Debugging absences](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output/blob/main/essays/debugging-absences.md) — the hardest production failures in agent systems leave nothing in the log.
- [What survives when you design for the verifier](https://github.com/NirajPatel-AI-PM/evidence-as-a-build-output/blob/main/essays/designing-for-the-verifier.md) — a paused personal experiment, never in production, and what building it taught me about how agents should be made to work.

### Selected work

Built for a regulated clinical platform. Not public, described here in the general case.

- **A study-configuration product, from zero to deployment.** A product for building and running clinical studies on a regulated platform: protocol configuration, participant-facing content and site workflow, defined once and deployed without a per-study engineering build. Taken from nothing to production and now running more than 100 active studies for more than 20 pharmaceutical sponsors, with tens of thousands of participants enrolled.
- **A deterministic conformance check that replaced a vendor review cycle.** An approved source document and the digital version built from it go in; out comes either a certificate of conformance or a located finding, byte-identical across runs. A difference matching no ruling blocks the certificate: quality owns the rulings, the code owns only detection. Writing the standard down was harder than comparing the documents, because the review it replaced had never set one.
- **A shared engineering layer, installed once.** Roughly three dozen skills plus quality gates, workflows and connectors, installed at user scope so an entire team inherits the same conventions — including the ones that encode regulatory process — from a single idempotent command.
- **Operator tooling for a multi-environment agent platform.** Promotion of an agent and its full dependency closure between environments under a stable identity, so the second run updates instead of duplicating, plus a documented method for diagnosing the failures that present as an absence rather than an error.
- **A factory for integration connectors.** An API document and a change request go in; a deployable connector comes out alongside its complete validation package — requirements, risk assessment, delivery backlog, test evidence, controlled documents — every artifact traced to the requirement it satisfies, with human approval at the points where a human must actually decide. Compliance evidence stops being reconstructed and starts being emitted.
- **The same factory, inverted, for inbound events.** A spec goes in; a deployable event-ingest service comes out with the same evidence spine. Younger and still maturing — and the reason I believe the first one was a pattern rather than a script.

### Elsewhere

Open to conversations about building AI systems where the evidence has to hold up — regulated industries especially.
