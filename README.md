# Campaign Watch

Campaign Watch is an agent research platform covering US elections.

The goal is to create an automated reporting system that provides information
profiles on every candidate in every electoral race in the US.

![Campaign Watch — race and candidate view](diagrams/ui-candidate-view.png)

## Deep research agent

The system design of the deep research agent is:

[![Deep research agent architecture](diagrams/deep-research-agent.png)](diagrams/deep-research-agent.png)

_Wide diagram — click to open it full size._

## Testing framework

The design of our testing framework is:

![Closed loop testing and evals framework](diagrams/testing-framework.png)

## Engineering decisions

An active log of engineering decisions will be updated here:

| Date | Context | Decision | Result | Status |
| --- | --- | --- | --- | --- |
| Aug 29, 2026 | User interviews request further information citations | Built in the evidence citation into the research model and UI dropdown list | Each 'Talking Point' has source(s) attached | 🟢 Deployed |
| Aug 25, 2026 | Initial gate affecting usability | UI changed to account for interface accessibility and usage patterns | Noticeable increase in post-gate accesses | 🟢 Deployed |
| Aug 24, 2026 | Not showing up on Google search | Route metadata revision, sitemaps, and immutable caching for reduced bandwidth requirements | Sitemap live but still unlisted on Google | 🟡 Needs Update |
| Aug 23, 2026 | 26% "what's new" coverage for candidates | Context widening, added information priorities and improved failure case detection, also separated the pipeline to ensure that the "what's new" search could be triggered independently | 100% "what's new" coverage | 🟢 Deployed |
| Aug 17, 2026 | Candidates who are no longer in contention are still researched | Word or phrase searching to detect elimination and UI fix | Eliminated candidates are crossed off and reasons shown | 🟢 Deployed |
