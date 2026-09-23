## Niraj Patel

I lead product for a regulated clinical research company's internal builder platform, and I write much of the software myself. With Claude Code and Claude Fable 5, I built our shared AI engineering layer, the deployment tooling for our agent apps, and a new memory system for our agents. I build the measurement too, so each of them has to show that it works.

### Two things you can run

**[team-os](https://github.com/NirajPatel-AI-PM/team-os)**. A Claude Code plugin with the skills, subagents and hooks a product team uses to ship, and the records that show whether the team uses them. It is a clean-room version of a system I built at work. I share it to show the intent and the design, and it holds none of the company's own skills or process. After you install it, its skills load when the work calls for them, and two scripts turn the usage records into an adoption summary and an HTML dashboard.

```
/plugin marketplace add NirajPatel-AI-PM/team-os
/plugin install team-os@niraj-patel
```

**[skill-adherence-eval](https://github.com/NirajPatel-AI-PM/skill-adherence-eval)**. An evaluation that measures, for any folder of `SKILL.md` files, whether a model picks the right skill for a request and then follows it. It records every model call, so you can replay a run with no API key. The report gives the selection and adherence rates and the noise floor between repeats.

```
RECORDINGS_DIR=runs/claude-sonnet-5/recordings MODEL_LABEL=claude-sonnet-5 node eval.ts --repeats 3
```

### Essays

- [How a playbook spread, and what its memory measures](https://github.com/NirajPatel-AI-PM/NirajPatel-AI-PM/blob/main/essays/how-a-playbook-spread.md). How I got our shared AI engineering layer adopted by over 35 people. [team-os](https://github.com/NirajPatel-AI-PM/team-os) is a clean-room version of it.
- [Prioritizing capabilities](https://github.com/NirajPatel-AI-PM/NirajPatel-AI-PM/blob/main/essays/prioritizing-capabilities.md). Why I said "not now" to a feature the platform needed, and what backed that answer.
- [Rolling out Claude Design](https://github.com/NirajPatel-AI-PM/NirajPatel-AI-PM/blob/main/essays/rolling-out-claude-design.md). How Claude Design reached over half the company, and why the design systems went in first.
- [Slowing a launch to meet customer needs](https://github.com/NirajPatel-AI-PM/NirajPatel-AI-PM/blob/main/essays/slowing-a-launch-to-meet-customer-needs.md). Why we slowed a large customer's launch, and built the isolated workspaces they needed with them.
- [Harness engineering](https://github.com/NirajPatel-AI-PM/NirajPatel-AI-PM/blob/main/essays/harness-engineering.md). How I rebuilt an agent memory system with Claude Fable 5, and built the evaluation that proved it.
