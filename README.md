# Campaign Watch

Campaign Watch is an agent research platform covering US elections.

Check it out now at https://campaignwatch.us/

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
| 16 September, 2026 | States that didn't have a race for the office wasn't listed in the dropdown making state/race switches challenging for users | Dropdown lists all states, historical information also colors every state and clicking on a state which didn't have the campaign for that year (on history view) switches to previous race details | Easier user switch experience | 🟡 Needs improvement (Prevent repeated clicks in history mode for other states lead to indefinitely earlier dates - have cache or path memory) |
| 16 September, 2026 | States now have official voter guides out with proposition and candidate information | Wrote pdf to app logic which converted information to local data schema | California proposition coverage functional | 🟢 Deployed |
| 7 September, 2026 | Similar products covered candidate endorsements | Wrote new parsing logic to detect formal endorsements in media. Ran it on the data corpus and wrote a verifier to invalidate endorsements of previous years or statements of support | Beta feature of endorsement list for candidates | 🟢 Deployed |
| 1 September, 2026 | Candidate name list missing on phone UI | Cross-platform UI fix and removed candidate duplicates due to list wraparounds + regression testing for UI | Functional phone UI | 🟢 Deployed |
| 30 Aug, 2026 | Image showing on social shares was tagline instead of UI screenshot | Had public reference image to force social reference of screenshot | Linkedin and platform shares showed stable UI | 🟢 Deployed |
| Aug 29, 2026 | User interviews request further information citations | Built in the evidence citation into the research model and UI dropdown list | Each 'Talking Point' has source(s) attached | 🟢 Deployed |
| Aug 25, 2026 | Initial gate affecting usability | UI changed to account for interface accessibility and usage patterns | Noticeable increase in post-gate accesses | 🟢 Deployed |
| Aug 24, 2026 | Not showing up on Google search | Route metadata revision, sitemaps, and immutable caching for reduced bandwidth requirements | Sitemap live but still unlisted on Google | 🟢 Fixed |
| Aug 23, 2026 | 26% "what's new" coverage for candidates | Context widening, added information priorities and improved failure case detection, also separated the pipeline to ensure that the "what's new" search could be triggered independently | 100% "what's new" coverage | 🟢 Deployed |
| Aug 17, 2026 | Candidates who are no longer in contention are still researched | Word or phrase searching to detect elimination and UI fix | Eliminated candidates are crossed off and reasons shown | 🟢 Deployed |
