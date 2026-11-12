# IdentityPython Gap Analysis Against Open Source Best Practices

Date: 2026-09-28

## Purpose

This document compares open source best practices with the current state of the IdentityPython organization and project portfolio.

It is intended to answer one question clearly:

Where does IdentityPython already align with strong open source operating practice, and where are the highest-value gaps?

## Scope and Method

This analysis uses:

- Generic best-practice guidance from GitHub Open Source Guides, GitHub Docs, Apache, Rust, Node.js, and Choose a License.
- Local repository evidence from the IdentityPython Meetings repository.
- The existing project portfolio assessment in `2026-09-28_IdentityPython_Status_Report.md`.

This is not a code audit. It is an operating-model and maintainer-practice gap analysis.

## Executive Summary

IdentityPython is active, but it is not yet operating like a fully standardized, low-friction open source ecosystem.

The strongest positive signals are:

- The organization is still publicly present and has real projects with recent maintenance.
- A governance and technical re-engagement effort is visibly underway.
- Several important repositories, especially `pysaml2`, `pyFF`, and `pyMDOC-CBOR`, show healthy maintenance signals.
- A public security process exists at the organization level.

The most important gaps are:

- The public maintainer surface is inconsistent across repositories.
- Governance and contributor process are not yet clearly standardized and exposed as repository-level practice.
- Portfolio status is not clear enough for users choosing between active, maintenance-only, legacy, and archived projects.
- Maintainer-capacity strain is still visible in specific important projects, especially `SATOSA`.
- Documentation freshness, release clarity, and migration guidance are uneven across the portfolio.

The highest-value conclusion is this:

IdentityPython does not primarily need new abstract policy. It needs the operating basics of a healthy open source ecosystem to become visible, consistent, and repeatable across active repositories.

## Overall Maturity Judgment

IdentityPython appears to be in a rebuilding or re-standardization phase.

That means the organization is beyond the stage of a casual personal project, but not yet in a steady-state mature maintainer phase with fully normalized workflows across its active project set.

This matters because the best response is not maximal bureaucracy. The best response is to close the gaps that most improve contributor confidence and maintainer leverage:

- clearer project status labeling,
- clearer maintainer and contribution process,
- more consistent governance and support surface,
- better release and portfolio hygiene.

## Summary Scorecard

| Area | Best-practice expectation | Current IdentityPython state | Gap severity | Direction |
|---|---|---|---|---|
| Project purpose and status clarity | Every repo and portfolio page clearly explains scope and maintenance state | Mixed; org exists, but project status messaging is uneven across portfolio | High | Standardize project status labels and portfolio map |
| Community health files | Active repos expose README, CONTRIBUTING, CODE_OF_CONDUCT, SECURITY, SUPPORT, templates | Inconsistent and not clearly standardized at org level | High | Roll out a common maintainer surface |
| Governance visibility | Public roles, decision-making, escalation, maintainer progression | Governance effort exists, but public artifacts are stale or incomplete relative to current reboot | High | Publish lightweight current governance and maintainer model |
| Contributor onboarding | Easy path to first contribution, clear issue flow, good first issues | Work in progress; docs and contributor guidance recognized as gaps internally | High | Improve contribution docs and labels |
| Triage and responsiveness | Backlogs visibly managed with clear maintainer signals | Mixed; some active repos healthy, others show merge or issue backlog strain | High | Prioritize triage discipline in highest-risk repos |
| Release clarity and automation | Releases are documented, repeatable, and not dependent on one person | Explicitly identified as a workstream goal; not yet clearly normalized portfolio-wide | High | Document and automate release ownership |
| Security posture | Public reporting path, defined handling, version guidance | Better than many projects at org level, but repo-level clarity appears uneven | Medium | Link or standardize SECURITY.md across active repos |
| Documentation quality | Current docs, migration guidance, compatibility clarity | Uneven; recognized internally as a major problem area | High | Treat documentation as a first-order maintenance task |
| Portfolio lifecycle management | Active, legacy, deprecated, archived states are explicit | Mixed; archived and legacy OIDC repos complicate the public story | High | Publish portfolio taxonomy and migration map |
| Maintainer sustainability | Shared ownership, backup admins, contributor ladder | Capacity strain still visible; contributor ladder is an explicit goal, not yet clearly complete | High | Make ownership and progression visible |

## Detailed Gap Analysis

## 1. Purpose, Scope, and Public Status Clarity

### Best-practice expectation

Users and contributors should quickly understand:

- which projects are active,
- which are stable but lightly maintained,
- which are legacy or archived,
- and which replacements or migration paths exist.

### Current IdentityPython state

- IdentityPython has a public website and public project list.
- The project status report shows that the active portfolio is real but uneven.
- Some repositories have recent releases and clear activity.
- Some repositories are legacy, archived, or stale, especially in the older OIDC/JWT split area.

### Gap

The public portfolio story is not clear enough. Users can find active projects, archived projects, and important component libraries, but the status differences are not normalized and the replacement story is incomplete.

### Why it matters

- Ambiguous lifecycle status increases adoption risk.
- Contributors waste time on the wrong repositories.
- Maintainers inherit portfolio debt from unclear public messaging.

### Priority actions

1. Publish a portfolio map that classifies projects as active, maintenance-only, legacy, superseded, or archived.
2. Add migration links where older projects have newer replacements.
3. Align the website, GitHub org, and README-level messaging.

## 2. Community Health Files and Repository Operating Surface

### Best-practice expectation

Active repositories should provide a consistent maintainer surface:

- README
- CONTRIBUTING
- CODE_OF_CONDUCT
- SECURITY
- SUPPORT
- LICENSE
- issue and pull request templates

### Current IdentityPython state

- The Meetings repository has a README and a LICENSE.
- The governance research already confirmed that this repository does not visibly expose CONTRIBUTING, CODE_OF_CONDUCT, SECURITY, SUPPORT, GOVERNANCE, or template files.
- The status report suggests the broader portfolio is operationally uneven, which usually correlates with inconsistent repository health files.

### Gap

IdentityPython appears to have organizational intent, but not yet a clearly standardized repository-level maintainer surface across active projects.

### Why it matters

- New contributors cannot reliably predict process from one repo to another.
- Maintainers lose time repeating instructions.
- GitHub community standards signals remain incomplete.

### Priority actions

1. Create a standard set of default community health files for active repositories.
2. Override the defaults only where a project has a real need to diverge.
3. Start with active flagship repositories and the org’s coordination repositories.

## 3. Governance Visibility and Decision-Making

### Best-practice expectation

A healthy project should make visible:

- who maintains it,
- how decisions are made,
- how major changes are proposed,
- and how people gain more responsibility.

### Current IdentityPython state

- The governance workstream is active and already names the right deliverables: maintainer model, contributor guidelines, vulnerability process, contributor ladder, release process, and regular technical coordination.
- The status report notes that governance artifacts are public but stale relative to the current re-engagement effort.

### Gap

IdentityPython has governance intent and some historic governance artifacts, but the current operating model is not yet fully visible as a fresh, contributor-facing, project-level practice.

### Why it matters

- Projects look less stable when authority and process are implied rather than documented.
- Governance ambiguity creates friction in triage, releases, and roadmap decisions.

### Priority actions

1. Publish a lightweight current governance statement now rather than waiting for a perfect final model.
2. Name current technical maintainers or coordination roles publicly.
3. Add a documented escalation or tie-break process for unresolved technical decisions.

## 4. Contributor Onboarding and Contributor Ladder

### Best-practice expectation

Strong projects make it easy to move from user to first-time contributor to trusted repeat contributor.

That usually requires:

- contribution guidelines,
- low-friction first tasks,
- labels such as `good first issue`,
- and explicit paths to more responsibility.

### Current IdentityPython state

- Internal workstream goals explicitly call for a clear contributor ladder.
- Documentation and contributor guidance are already recognized as weak points.

### Gap

The contributor growth mechanism is identified as necessary, but it is not yet clearly operationalized across the project set.

### Why it matters

- Without a contributor ladder, maintainer capacity does not grow.
- Open source ecosystems with important infrastructure cannot rely on passive good will alone.

### Priority actions

1. Define contributor roles in plain language.
2. Publish how someone becomes a maintainer or trusted releaser.
3. Label and document newcomer-friendly issues in active projects.

## 5. Triage Discipline and Responsiveness

### Best-practice expectation

Issues and pull requests should not sit indefinitely without a clear state. Healthy projects:

- acknowledge incoming work quickly,
- use labels consistently,
- close out-of-scope work politely,
- and keep high-risk queues moving.

### Current IdentityPython state

- The status report shows uneven triage health.
- `pyFF` appears tractable and active.
- `pysaml2` is active but carries a large and sensitive backlog.
- `SATOSA` shows the clearest signs of maintainer-capacity strain, with both issue backlog and open PR backlog.

### Gap

Backlog pressure is not uniform, but the organization’s most important risk areas are exactly the places where predictable triage matters most.

### Why it matters

- Unmanaged backlog is both a technical and reputational problem.
- It directly increases contributor drop-off and maintainer stress.

### Priority actions

1. Publish triage ownership or rotation for the highest-value repos.
2. Triage old PRs in `SATOSA` and identify which are mergeable, obsolete, or need maintainership decisions.
3. Separate support questions from actionable defects more consistently.

## 6. Release Management and Automation

### Best-practice expectation

Release authority and release steps should be documented, repeatable, and not concentrated in one person’s unpublished knowledge.

### Current IdentityPython state

- The governance workstream explicitly calls out easy releases, releaser authorization, automation, trusted publishing, and PyPI ownership cleanup.
- The status report shows that some projects have healthy recent release cadence and others do not.

### Gap

IdentityPython has correctly identified release and publishing process as a core maintenance problem, which strongly suggests the portfolio is not yet consistently normalized in this area.

### Why it matters

- Release ambiguity makes healthy code look stale.
- It slows security response and discourages shared ownership.

### Priority actions

1. Publish a standard release checklist or release process template.
2. Track who holds publish rights for active projects.
3. Move active projects toward repeatable, org-owned publishing workflows.

## 7. Security Posture

### Best-practice expectation

Projects should provide:

- a private reporting path,
- clear handling expectations,
- and version guidance when vulnerabilities are fixed.

### Current IdentityPython state

- The status report shows that IdentityPython has a public incident response path and uses GitHub advisories.
- That is a meaningful strength compared with many small ecosystems.
- The same report also notes a pragmatic but demanding support model: users are expected to upgrade rather than rely on long-term backports.

### Gap

Security process exists, but repo-level visibility and maintenance-branch expectations may not be equally obvious everywhere.

### Why it matters

- Security trust depends on clarity, not only on intent.
- Users need to know what support model they are accepting.

### Priority actions

1. Add or standardize SECURITY.md across active repositories.
2. State supported-version and backport expectations clearly.
3. Keep security-report routing consistent with the org-level process.

## 8. Documentation Quality and Freshness

### Best-practice expectation

Documentation should be current enough that users can succeed without reverse-engineering issue trackers.

### Current IdentityPython state

- Documentation is explicitly recognized as an organization-wide problem area.
- The status report identifies documentation freshness issues in `idpy-oidc`, integration clarity issues in `djangosaml2`, operational guidance needs in `SATOSA`, and branding or relationship ambiguity in parts of the JWT/OIDC stack.

### Gap

Documentation debt is not isolated. It affects onboarding, support load, release trust, and migration clarity.

### Why it matters

- Poor docs convert maintainers into private support staff.
- In authentication and federation software, configuration clarity is part of operational safety.

### Priority actions

1. Treat documentation as a first-order maintenance queue, not a side task.
2. Prioritize current quickstarts, version compatibility, and migration guidance.
3. Add sample configurations and supported-version tables where users repeatedly struggle.

## 9. Maintainer Model and Sustainability

### Best-practice expectation

Healthy ecosystems make ownership visible and survivable.

That usually means:

- named maintainers,
- backup admins,
- contributor progression,
- bounded scope,
- and succession planning.

### Current IdentityPython state

- The re-engagement effort itself is evidence that maintainer capacity has been a real bottleneck.
- The governance workstream goals explicitly mention a functioning maintainer model and contributor privilege management.

### Gap

The problem is recognized, but the stable visible solution is not yet complete.

### Why it matters

- A project can have active code and still remain fragile if too few people can review, release, or respond.

### Priority actions

1. Name maintainer ownership per active project.
2. Define inactivity and handoff expectations.
3. Make contributor growth part of normal operations, not an occasional appeal for help.

## 10. Organization-Wide Portfolio Hygiene

### Best-practice expectation

Large or multi-project organizations should manage the portfolio, not just individual repositories.

That means:

- clear active versus archived classification,
- rationalized branding,
- current website-to-repo mapping,
- and explicit relationships between older and newer libraries.

### Current IdentityPython state

- The status report identifies portfolio messaging problems, especially around older OIDC/JWT split projects and the relationship between `pyjwkest`, `JWTConnect-Python-CryptoJWT`, and related libraries.
- The report also notes that some active repositories are not emphasized on the website as clearly as they should be.

### Gap

The ecosystem contains real working software, but the portfolio story is harder to understand than it should be.

### Why it matters

- Confusing portfolio structure reduces trust.
- It hides strong current work behind old naming and legacy artifacts.

### Priority actions

1. Publish a portfolio map with status and relationships.
2. Add migration guidance for legacy OIDC/JWT repositories.
3. Align website links and repository branding with current reality.

## Project-Level Gap Highlights

## Stronger-aligned projects

These appear closer to best-practice expectations for active maintenance:

- `pyFF`: recent releases, manageable backlog, clear signs of ongoing care.
- `pysaml2`: active and important, though backlog and security pressure remain high.
- `pyMDOC-CBOR`: narrow scope, recent releases, small backlog.
- `JWTConnect-Python-CryptoJWT`: active enough to be useful, though portfolio clarity around it should improve.

## Projects with notable gaps but viable path forward

- `djangosaml2`: needs better compatibility clarity, documentation freshness, and integration guidance.
- `idpy-oidc`: needs clearer release hygiene, fresher docs, and stronger public roadmap or status signals.
- `pyop`: needs a clearer statement about whether it is strategic, maintenance-only, or lightly active.

## Highest-risk gap projects

- `SATOSA`: maintainer-capacity strain, open PR backlog, and uncertainty around activity are major gaps relative to best practice.
- `pyXMLSecurity`: weak public maintenance signals in a security-relevant area.
- `pyjwkest`: explicitly not actively maintained and should be treated as legacy, with migration guidance.

## Cross-Cutting Gaps by Severity

### Highest severity

- Portfolio status ambiguity.
- Inconsistent maintainer surface and contributor guidance.
- Maintainer capacity strain in strategically important projects.
- Uneven release and ownership clarity.

### Medium severity

- Repo-level security visibility inconsistency.
- Documentation freshness and migration guidance gaps.
- Public governance freshness relative to the 2026 reboot effort.

### Lower severity, but still useful to address

- Stronger recognition of non-code contributors.
- More visible organization-wide metrics for response, release, and backlog health.

## Recommended Action Plan

## First 30 days

1. Publish a project-status taxonomy for the IdentityPython portfolio.
2. Publish a lightweight current maintainer and governance statement.
3. Standardize the community health file baseline for active repositories.
4. Clarify the highest-risk legacy versus active relationships in the OIDC/JWT area.

## 30 to 90 days

1. Triage the `SATOSA` PR and issue backlog.
2. Normalize SECURITY.md and SUPPORT.md across active repos.
3. Publish release ownership and release steps for active flagship repos.
4. Improve contributor labels and newcomer pathways.

## 90 days and beyond

1. Build a contributor ladder and maintainer progression process.
2. Move active repos toward repeatable org-owned publishing and recovery paths.
3. Align website, GitHub org, and repository READMEs with a single portfolio story.
4. Track organization-wide metrics for response time, backlog age, and release cadence.

## Final Assessment

IdentityPython’s main challenge is not absence of code or absence of users. It is uneven operational maturity across a portfolio that still matters to real adopters.

That is a fixable problem.

The organization already appears to understand the right problem set: maintainer model, contributor process, release authority, security clarity, docs, and governance workflow. The gap is that these practices are not yet consistently exposed and normalized across the active project portfolio.

If IdentityPython closes that gap, it will improve trust faster than by almost any other single investment.

## References

### Best-practice sources

- Open Source Guides, Best Practices for Maintainers: <https://opensource.guide/best-practices/>
- Open Source Guides, Building Welcoming Communities: <https://opensource.guide/building-community/>
- Open Source Guides, Leadership and Governance: <https://opensource.guide/leadership-and-governance/>
- GitHub Docs, About community profiles for public repositories: <https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-profiles-for-public-repositories>
- GitHub Docs, Creating a default community health file: <https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file>
- GitHub Docs, Adding support resources to your project: <https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-support-resources-to-your-project>
- Choose a License: <https://choosealicense.com/>
- Apache Software Foundation, How the ASF Works: <https://www.apache.org/foundation/how-it-works.html>
- Rust Governance RFC 1068: <https://github.com/rust-lang/rfcs/blob/master/text/1068-rust-governance.md>
- Node.js Project Governance: <https://nodejs.org/en/about/governance>

### IdentityPython evidence used

- `2026-09-28_IdentityPython_Status_Report.md`
- `README.md`
- `Working Meetings-2026 Technical Re-engagement/README.md`
- `Working Meetings-2026 Technical Re-engagement/Workstream-Governance/README.md`