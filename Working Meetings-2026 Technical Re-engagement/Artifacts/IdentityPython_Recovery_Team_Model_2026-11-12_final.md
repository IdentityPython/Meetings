# IdentityPython: Recommended Recovery Team Model

Date: 12 November 2026, revised 25 November 2026. Prepared with AI-assisted research.

This document proposes the team needed to restore the health and reputation of the IdentityPython (IdPy) projects. It stands on its own: all evidence is summarized inline and cited to public sources (GitHub issues and PRs, public mailing-list archives, and the public [IdentityPython/Meetings](https://github.com/IdentityPython/Meetings) repository).

---

## Table of Contents

1. [Recommendation in Brief](#1-recommendation-in-brief)
2. [Background: The Problem the Team Must Solve](#2-background-the-problem-the-team-must-solve)
3. [Why This Shape](#3-why-this-shape)
4. [Phase 1: Recovery Team (about 6 months)](#4-phase-1-recovery-team-about-6-months)
5. [Phase 2: Steady-State Project Pods](#5-phase-2-steady-state-project-pods)
6. [Cross-Cutting Roles and Responsibilities](#6-cross-cutting-roles-and-responsibilities)
7. [Design Rules](#7-design-rules)
8. [Governance and Accountability](#8-governance-and-accountability)
9. [Operating Rhythm](#9-operating-rhythm)
10. [Recruitment Pipeline](#10-recruitment-pipeline)
11. [Capacity and In-Kind Resourcing](#11-capacity-and-in-kind-resourcing)
12. [Anti-Patterns to Avoid](#12-anti-patterns-to-avoid)
13. [Mapping Roles to Recovery Actions](#13-mapping-roles-to-recovery-actions)
14. [Risks and Mitigations](#14-risks-and-mitigations)
15. [Next Steps](#15-next-steps)
16. [Sources](#16-sources)
17. [Appendix: Initial Suggestions for the Group's Consideration](#17-appendix-initial-suggestions-for-the-groups-consideration)

---

## 1. Recommendation in Brief

Set up **a small core team, staffed with named in-kind time from member organisations and working to a fixed rhythm, and give each tier-1 project a "pod" anchored by organisations that commit named time, as agreed by the group.** Do not build this around a large volunteer working group.

- **Phase 1 (recovery, about 6 months):** 8–10 people sharing about **3–4 FTE**. They clear the backlog, spread merge and release rights, and restore visible communication.
- **Phase 2 (steady state):** each tier-1 project gets a pod of 2–3 people, at least one of whom runs it in production. A thin shared layer covers security, release infrastructure and community.
- **Accountability:** the existing **maintainer group**, a committee of the IdPy board, owns technical decisions. The **board** owns policy and secures in-kind time commitments from its members ([Governance notes, 30 Sep 2026][gov]). IdPy has no budget of its own, so the model relies on donated staff time, not money ([§11](#11-capacity-and-in-kind-resourcing)).

---

## 2. Background: The Problem the Team Must Solve

### 2.1 What users are unhappy about

Users and contributors are not unhappy with the code or the technology. They are unhappy with **stewardship**: PRs left unreviewed, releases missing, dependency-CVE fixes stalled, and long silences. Production users keep the software and **fork it rather than leave**.

Key public evidence:

- **Maintainer succession crisis (Oct 2023).** The main OIDC maintainer wrote that the situation was "Not sustainable" and asked for successors for five packages ([idpy-board thread](https://lists.sunet.se/hyperkitty/list/idpy-board@lists.sunet.se/thread/N2LU5UBWXGLUWKRMRREOBLZVXTQPU3WR/)).
- **Stalled dependency-CVE fixes in pysaml2 (Dec 2024 – Sep 2026):**
  - pyOpenSSL breakage reported in [#975](https://github.com/IdentityPython/pysaml2/issues/975);
  - the fix PR [#977](https://github.com/IdentityPython/pysaml2/pull/977) (46 reactions) stayed open for more than nine months while several organisations ran it unmerged in production;
  - follow-up CVE reports [#1012](https://github.com/IdentityPython/pysaml2/issues/1012) and [#1024](https://github.com/IdentityPython/pysaml2/issues/1024);
  - a second, independent fix PR [#1021](https://github.com/IdentityPython/pysaml2/pull/1021);
  - resolved only with v7.5.5 in September 2026, about 21 months after the first report.
- **"Is this project still alive?"**
  - [pysaml2#1031](https://github.com/IdentityPython/pysaml2/issues/1031) (June 2026): *"I've sent an email to the mentioned mailing list… without any response… So is this project still alive?"*, followed by *"I'm almost ready to fork it…. Who would help?"*
  - [SATOSA#503](https://github.com/IdentityPython/SATOSA/issues/503) (August 2026): no SATOSA release between February 2025 (v8.5.1) and September 2026 (v8.6.0).
- **The Town Hall (17 June 2026).** An operator asked where the "only active maintainer" had gone. The answer: *"The main problem is to have enough people that can dedicate time on the projects, do the reviews, and make progress"* ([Town Hall notes][th]).
- **The community's own diagnosis.**
  - *"PySAML2 and SATOSA are maintained by a small group; work has been bottlenecked waiting on review/merge"*;
  - *"some libraries are effectively orphaned"*;
  - *"there may be a lack of interest because of past failures. We will need to demonstrate that things are different"*

  All three are from the [Fork Review notes, 15 Sep 2026][fr].

### 2.2 Measured decline in responsiveness

These figures were computed from the public GitHub API data for the IdentityPython repositories (snapshot 5 October 2026, bot accounts excluded). The percentages are the share of PRs opened in each year that were eventually merged.

| Repository | Merged (2022) | Merged (2024 / 2025 / 2026) | Median days to merge | Open PRs older than 2 years |
|---|---:|---:|---:|---:|
| pysaml2 | 80% | 33% / 43% / 15% | ~5 (2022) → 125–143 (2024–2026) | 24 of 39 |
| SATOSA | 85% | 35% / 12% / – | rising | 27 of 33 |

Together, pysaml2 and SATOSA had about **85 open issues and PRs with no comment at all**. Other projects (CryptoJWT, djangosaml2, pyFF) stayed largely responsive.

**Conclusion:** external contributions kept coming in. What ran out was **review and release capacity**.

### 2.3 Root causes

| ID | Root cause | Public evidence |
|---|---|---|
| RC1 | Maintainers concentrated in very few people; release rights held by one or two | [idpy-board 2023](https://lists.sunet.se/hyperkitty/list/idpy-board@lists.sunet.se/thread/N2LU5UBWXGLUWKRMRREOBLZVXTQPU3WR/); [Fork Review notes][fr]; [Town Hall][th] |
| RC2 | Silence and weak public communication | [pysaml2#1024](https://github.com/IdentityPython/pysaml2/issues/1024) (*"A statement from you would be good"*); [pysaml2#1031](https://github.com/IdentityPython/pysaml2/issues/1031); [SATOSA#503](https://github.com/IdentityPython/SATOSA/issues/503) |
| RC3 | Slow handling of *dependency* CVEs flagged by downstream scanners | [#952](https://github.com/IdentityPython/pysaml2/issues/952), [#975](https://github.com/IdentityPython/pysaml2/issues/975), [#977](https://github.com/IdentityPython/pysaml2/pull/977), [#1012](https://github.com/IdentityPython/pysaml2/issues/1012), [#1024](https://github.com/IdentityPython/pysaml2/issues/1024) |
| RC4 | A fork-debt loop: fixes live in forks instead of upstream | [SUNET/pysaml2 vs upstream](https://github.com/IdentityPython/pysaml2/compare/master...SUNET:pysaml2:master); [unigreen-alliance/SATOSA vs upstream](https://github.com/IdentityPython/SATOSA/compare/master...unigreen-alliance:SATOSA:master); [italia/iam-proxy-italia](https://github.com/italia/iam-proxy-italia); [BotoX/SATOSA](https://github.com/BotoX/SATOSA) |
| RC5 | Too many overlapping repositories without lifecycle labels | [idpy-oidc#53](https://github.com/IdentityPython/idpy-oidc/issues/53); [pyjwkest#101](https://github.com/IdentityPython/pyjwkest/issues/101) (*"This package should be archived"*) |
| RC6 | Inconsistent release discipline | [djangosaml2#412](https://github.com/IdentityPython/djangosaml2/issues/412) (minimum Python raised in a patch release, then yanked) |
| RC7 | Long-standing documentation and onboarding gap | [Town Hall][th]; [Re-Kickoff][rk] (*"documentation was a critical weak spot"*); [satosa-users, Aug 2025](https://lists.sunet.se/hyperkitty/list/satosa-users@lists.sunet.se/thread/4S2XCN62F2X3DJKMFRYAZWSAXF4VTTX5/) (demo lost when SAMLtest shut down) |
| RC8 | Under-resourcing | Participants work "alongside other professional obligations" ([Re-Kickoff][rk]); the programme statutes provide no budget of their own ([DRACC 0024](https://commonsconservancy.org/dracc/0024/)) |

---

## 3. Why This Shape

| Root cause | What the team must provide |
|---|---|
| RC1 Maintainer concentration | ≥ 2 people with merge and release rights per tier-1 project |
| RC2 Silence | A named owner for communication, plus a weekly duty person |
| RC3 Slow dependency-CVE handling | A dedicated security and dependency lead with a target fix time |
| RC4 Fork-debt loop | An upstreaming lead, starting with member organisations' own forks |
| RC5 Fragmentation | A tier-1 focus; other projects archived or marked "seeking maintainer" |
| RC6 Release discipline | A release and infrastructure engineer; automated, policy-driven releases |
| RC7 Documentation and onboarding | A documentation and onboarding owner |
| RC8 Under-resourcing | Named, written time commitments from organisations |

**Core insight:** adding more *occasional* volunteers does not remove the bottleneck. **Guaranteed time** and **shared merge and release rights** do.

---

## 4. Phase 1: Recovery Team (about 6 months)

**Mission:** close the visible backlog, remove single points of failure, and show that things have changed. In the [Fork Review workstream's][fr] words: *"Do this through action, not promises (delivering code and new releases)."*

**Finite scope:** about 51 PRs older than two years and about 85 items with no comment in pysaml2 and SATOSA, plus infrastructure setup. That is why a small team is enough.

| Role | Count | Time | Responsibilities | Qualities and experience |
|---|---|---|---|---|
| **Technical lead / architect** | 1 | 0.5 FTE | Final technical decisions; reviews risky changes (crypto, XML signature, protocol); sets the architecture direction | Deep knowledge of the IdPy codebases and of SAML/OIDC; experience reviewing security-sensitive code; trusted by the community; able to delegate routine decisions |
| **Core maintainers (merge and release rights)** | 3–4 | 0.3–0.5 FTE each | Triage, review, merge and release for tier-1 projects; at least 2 per project | Track record of contributions or reviews in at least one tier-1 project; able to commit time regularly; preferably working for an organisation that runs the software in production |
| **Security and dependency lead** | 1 (may rotate among core maintainers) | 0.2–0.3 FTE | CVE monitoring, Dependabot/Renovate, GitHub security advisories, incident manager; enforces the 30-day dependency-CVE target | Experience with vulnerability handling and coordinated disclosure; familiar with Python supply-chain tooling; available at short notice. Works under the [incident-response policy](https://github.com/IdentityPython/Governance/blob/master/idpy-incidentresponse.md) |
| **Release and infrastructure engineer** | 1 | 0.3 FTE (front-loaded) | PyPI organization, trusted publishing, GitHub Actions CI, common tooling, metrics dashboard | Experience with GitHub Actions, Python packaging and release automation; comfortable setting up shared templates across repositories |
| **Fork upstreaming lead** | 1 | 0.3 FTE | Reviews downstream forks and brings valuable changes upstream, crediting the original authors | Good knowledge of the downstream ecosystem and its forks; diplomatic and able to work with external maintainers; ideally from an organisation that maintains a fork itself, as this signals commitment. Serves the [Re-Kickoff][rk] goal: *"recover trust so that the forked code can come back into the projects"* |
| **Community and communications coordinator** | 1 | 0.2–0.3 FTE | Status statements, GitHub replies, mailing-list care, quarterly updates, recruitment | Strong written communication; experience coordinating projects or communities; neutral and trusted across member organisations |
| **Documentation and onboarding** | 1–2 | 0.2 FTE each | `docker compose` demo replacing SAMLtest, deployment cookbooks, an "OIDC: which library?" page | Hands-on deployment experience; clear technical writing; preferably someone who has recently been through onboarding. Works with the [Documentation workstream][doc] |

**How roles are filled.** This document does not assign people to roles. Roles are filled through volunteering or nomination within the workstreams. The maintainer group confirms them and the board is informed, in line with the board's decision that the maintainer group may co-opt maintainers ([Governance notes][gov]). Where a role has already been assigned by a board decision, that decision stands until it is reviewed at the end of Phase 1. Initial ideas collected during drafting are listed in [§17](#17-appendix-initial-suggestions-for-the-groups-consideration) for the group's consideration only.

**Total:** about **3–4 FTE** across 8–10 people.

### Phase 1 exit criteria

- No undecided PR older than 2 years in pysaml2 and SATOSA.
- No item with zero comments older than 7 days.
- At least 2 release-capable maintainers per tier-1 project, and PyPI ownership moved to an organization.
- Dependabot or Renovate, `SECURITY.md` and a lifecycle badge in every active repository.
- At least 3 change sets from forks merged upstream with credit.
- A public status statement and the first quarterly update published.

---

## 5. Phase 2: Steady-State Project Pods

Each **tier-1 project** gets a pod: a small team **anchored by one or more organisations that commit named time**, with at least one production operator in it. Which organisations anchor which pod is decided by the group, based on the commitments offered. Projects without a pod are out of scope. This is consistent with the governance decision that *"projects without a designated maintainer are treated as out of scope until someone steps up"* ([Governance notes][gov]).

| Pod | Repositories | Minimum size | Desired profile |
|---|---|---|---|
| **SAML core** | [pysaml2](https://github.com/IdentityPython/pysaml2), [pyXMLSecurity](https://github.com/IdentityPython/pyXMLSecurity) | 2–3 | At least one maintainer from an organisation running pysaml2 in production; at least one independent or external contributor (for example an author of an open fix PR such as [#977](https://github.com/IdentityPython/pysaml2/pull/977) or [#1021](https://github.com/IdentityPython/pysaml2/pull/1021)); XML signature and cryptography expertise |
| **Proxy** | [SATOSA](https://github.com/IdentityPython/SATOSA), [satosa-docker](https://github.com/IdentityPython/satosa-docker) | 2–3 | At least one production operator (for example a federation or campus deployment); experience with SAML↔OIDC bridging and container deployment |
| **Metadata** | [pyFF](https://github.com/IdentityPython/pyFF), [pyeleven](https://github.com/IdentityPython/pyeleven) | 2 | Experience running metadata aggregation or MDQ services at federation scale; PKCS#11/HSM knowledge for pyeleven |
| **OIDC / JWT** | [idpy-oidc](https://github.com/IdentityPython/idpy-oidc), [JWTConnect-Python-CryptoJWT](https://github.com/IdentityPython/JWTConnect-Python-CryptoJWT), [pyop](https://github.com/IdentityPython/pyop) | 2 | OAuth/OIDC protocol expertise; production use of idpy-oidc or SATOSA OIDC frontends; interest in OpenID Federation and wallet work |
| **Everything else** | [pyjwkest](https://github.com/IdentityPython/pyjwkest), [djangosaml2](https://github.com/IdentityPython/djangosaml2) (until adopted), legacy repositories | 0 | "Seeking maintainer", or archived through the [DRACC 0025](https://commonsconservancy.org/dracc/0025/) removal process (the pyjwkest README already states: *"This library is NOT actively maintained anymore"*) |

**djangosaml2** has historically been responsive to PRs but has a release-discipline problem ([#412](https://github.com/IdentityPython/djangosaml2/issues/412)). It becomes a pod as soon as an organisation commits a named maintainer.

### Pod responsibilities

- Triage and review within the published response targets.
- At least one release per quarter, plus security releases on demand.
- A project roadmap, changelog and documentation.
- A short monthly health report to the maintainer group.

---

## 6. Cross-Cutting Roles and Responsibilities

A thin shared layer across all pods:

| Function | Owner | Scope |
|---|---|---|
| Security and dependencies | Security lead (rotating) | Advisories, dependency CVEs, incident response, `SECURITY.md`, private vulnerability reporting |
| Release and infrastructure | Release engineer | PyPI organization, trusted publishing, CI templates, [OpenSSF Scorecard](https://scorecard.dev/), metrics dashboard |
| Community and communications | Coordinator | Website ([idpy.org](https://idpy.org/)), mailing lists, quarterly updates, conference presence (TNC, TechEx, TIIME), adopter stories |
| Architecture | Technical lead | Cross-project consistency (pysaml2 ↔ SATOSA ↔ pyFF), Python support policy, long-term technical direction |

### Responsibility matrix (RACI) for key activities

R = does the work, A = accountable, C = consulted, I = informed.

| Activity | Pod maintainers | Tech lead | Security lead | Release engineer | Coordinator | Board |
|---|---|---|---|---|---|---|
| Issue/PR triage | R/A | C | I | — | I | — |
| Merge of risky changes | R | A | C | — | — | — |
| Dependency-CVE fix and release | R | C | A | C | I | I |
| Security advisory publication | C | C | R/A | C | I | I |
| Release pipeline and PyPI | C | I | C | R/A | — | — |
| Fork upstreaming | R | A | C | — | I | — |
| Status statements and updates | C | C | C | — | R/A | I |
| Adding or removing a project | C | C | — | — | C | A |
| In-kind time commitments | I | C | — | — | R | A |

---

## 7. Design Rules

These rules matter more than the org chart.

1. **Named time, not best effort.** Each organisation commits in writing (for example "Organisation X: 0.5 FTE of a named developer on project Y"). At the [Re-Kickoff][rk], participating organisations could not yet quantify the time they could commit.
2. **No single key-holder.** Every tier-1 project has ≥ 2 people with merge and release rights, using a PyPI organization with trusted publishing. The [Re-Kickoff][rk] goal: *"Any authorized maintainer or group can cut a release."*
3. **Mix maintainers and operators.** Each pod includes at least one production user, so priorities follow real deployment needs.
4. **Recruit from fork authors.** People who wrote duplicate CVE fixes or run production forks have already shown they care ([#977](https://github.com/IdentityPython/pysaml2/pull/977), [#1021](https://github.com/IdentityPython/pysaml2/pull/1021), [Town Hall][th]).
5. **Weekly triage duty rotation.** One person per week is responsible for first responses. This prevents silence and spreads the load.
6. **Fewer projects, done well.** Only tier-1 projects get pods. Spreading scarce people across 18 active repositories diluted attention.
7. **Decisions on GitHub.** Substantive outcomes are recorded in GitHub issues and discussions. Slack is only for real-time exchanges ([Fork Review notes][fr]).
8. **Protect against burnout.** Work is capped at the committed time. The default is "seeking maintainer", not overcommitting ([Governance notes][gov]).

---

## 8. Governance and Accountability

```text
             IdPy Board (policy, in-kind commitments, admission/removal — DRACC 0024/0025)
                                    │
                 Maintainer Group (board committee; technical authority)
                 Tech Lead · Security Lead · Release Engineer · Coordinator
                                    │
     ┌──────────────┬──────────────┼──────────────┬──────────────┐
  SAML core pod   Proxy pod     Metadata pod    OIDC/JWT pod   (seeking maintainer)
  pysaml2,        SATOSA,       pyFF,           idpy-oidc,
  pyXMLSecurity   satosa-docker pyeleven        CryptoJWT, pyop
```

- The **board** sets policy, secures in-kind time commitments from member organisations, and decides on project admission and removal under [DRACC 0024](https://commonsconservancy.org/dracc/0024/) and [DRACC 0025](https://commonsconservancy.org/dracc/0025/).
- The **maintainer group** already exists as a board committee and can co-opt maintainers, reporting changes to the board ([Governance notes][gov]). It owns technical decisions, the response targets and the metrics.
- **Pods** have autonomy within their project, subject to the shared policies (release, security, contribution).
- All roles are **transitional** until reviewed after Phase 1, consistent with the board's appointment of transitional roles.

---

## 9. Operating Rhythm

| Cadence | Activity | Participants | Output |
|---|---|---|---|
| Daily (async) | Duty-person triage | Weekly duty maintainer | First response to all new issues and PRs |
| Weekly | Security and dependency check | Security lead | Dependency-CVE list and actions |
| Bi-weekly | Maintainer sync (30 min) | Maintainer group + pod leads | Blockers, merge decisions, release plan |
| Monthly | Health dashboard | Release engineer + coordinator | Public metrics (response time, PR age, merge share, release cadence), generated from the GitHub API |
| Quarterly | Community update and releases | Coordinator + pods | Post on [idpy-discuss](https://lists.sunet.se/hyperkitty/list/idpy-discuss@lists.sunet.se/latest); at least one release per tier-1 project |
| Semi-annual | Board review | Board + maintainer group | Capacity, in-kind commitments, project lifecycle decisions |

### Proposed response targets

- First response to issues and PRs within 7 days.
- Security reports acknowledged within 72 hours.
- Dependency-CVE fixes released within 30 days.
- Every PR decided within 90 days.

---

## 10. Recruitment Pipeline

A contributor ladder, as requested at the [Re-Kickoff][rk] (*"Clear contributor ladder"*):

| Step | Criteria | Rights |
|---|---|---|
| User | Uses the software | Open issues and discussions |
| Contributor | ≥ 1 merged PR | Recognized in release notes |
| Triager | Sustained helpful triage (for example 3 months) | Label, close and assign issues |
| Reviewer | Quality reviews over time | Approving reviews count toward merge |
| Maintainer | Nominated by the pod and approved by the maintainer group | Merge and release rights |

**Initial recruitment targets** (categories of people who are already active; the coordinator compiles the actual contact list with the group):

- Authors and users of the stalled pysaml2 CVE PRs ([#977](https://github.com/IdentityPython/pysaml2/pull/977), [#1021](https://github.com/IdentityPython/pysaml2/pull/1021), [#1044](https://github.com/IdentityPython/pysaml2/pull/1044)).
- Maintainers of active downstream forks.
- Production operators who have offered contributions (for example at the [Town Hall][th]).
- Past committers, as listed in each repository's contributor graph (for example [pysaml2](https://github.com/IdentityPython/pysaml2/graphs/contributors) and [SATOSA](https://github.com/IdentityPython/SATOSA/graphs/contributors)).

---

## 11. Capacity and In-Kind Resourcing

### 11.1 What the statutes allow

IdPy is a programme of the [Commons Conservancy](https://commonsconservancy.org/). Its statutes ([DRACC 0024, "Financial Considerations"](https://commonsconservancy.org/dracc/0024/)) are explicit:

- *"IdentityPython operates on a nil budget, which means there are no direct financial considerations."*
- At the request of grantmaking organisations, donors and partners, IdPy *may* provide guidance and inspiration, but *"IdentityPython itself will have no direct financial involvement in such activities under any circumstances."*
- *"Members of the Board are expected to donate in-kind resources to the development efforts around IdentityPython projects."*

**Consequence:** IdPy does not receive, hold or spend money. It cannot apply for grants, accept sponsorship or pay contractors. This team model therefore relies entirely on **in-kind contributions**: staff time that organisations donate to work on IdPy projects.

### 11.2 How capacity is provided

| Source | Form | Use | IdPy's role |
|---|---|---|---|
| Organisations represented on the board or in the maintainer group | **Named, written in-kind time commitments** (for example "0.5 FTE of a named developer on pysaml2") | Pod maintainers, technical lead, cross-cutting roles | Board asks for, records and reviews commitments, as the statutes expect of board members |
| Production operators and downstream adopters (see the GitHub dependents graphs, for example [pysaml2](https://github.com/IdentityPython/pysaml2/network/dependents)) | In-kind staff time; upstreaming of their own fixes | Pod membership, reviews, fork upstreaming | Invites contributors; offers a clear contributor ladder ([§10](#10-recruitment-pipeline)) |
| Individual volunteers | Personal time | Triage, docs, reviews | Recognition (release notes, ladder progression) |
| Grants obtained **by a member organisation for its own staff** (for example from [Sovereign Tech Agency](https://www.sovereign.tech/), [NLnet / NGI](https://nlnet.nl/) or the [GitHub Secure Open Source Fund](https://github.com/open-source/github-secure-open-source-fund)) | The grant is held and managed **entirely by the applying organisation**, and the resulting work is contributed upstream in kind | Security hardening, release infrastructure, documentation | **Guidance only**, if a grantmaker or the applicant asks (for example confirming priorities or the roadmap). No financial involvement. |
| Free tooling for open-source projects | GitHub Actions, Dependabot, private vulnerability reporting, trusted publishing, OpenSSF Scorecard | Security and release automation | Configure and use; no cost involved |

### 11.3 Practical implications

- **The "commitment ask" is about time, not money.** The board should ask each participating organisation for a named person and a percentage of their time per pod, recorded publicly (for example on idpy.org).
- **External engagements belong to the organisation that pays.** If a member organisation hires a contractor or uses grant money, the contract and the money stay with that organisation. IdPy only receives the resulting open-source contributions under the projects' licences.
- **Paid tooling is out of scope** unless a member organisation provides it in kind. Prefer free tooling for open-source projects.
- **Capacity sets the scope.** If commitments fall short, reduce the number of tier-1 pods rather than overcommitting volunteers ([Governance notes][gov]).

---

## 12. Anti-Patterns to Avoid

| Anti-pattern | Why it fails here |
|---|---|
| **A large open working group with no named owners** | Produces documents but not merges. The bottleneck is merge and release rights, not ideas. |
| **Relying on an external contractor alone** (engaged by a member organisation, since IdPy cannot hold contracts) | Clears the backlog, but trust and knowledge leave with the contract, and the concentration problem returns. |
| **A separate "fork merge team" disconnected from the maintainers** | Upstreamed code needs the people who will maintain it afterwards. Otherwise it becomes new orphaned code. |
| **Covering every repository** | Dilutes scarce capacity across many low-priority projects. |
| **Reformatting entire codebases first** | Huge diffs break every open PR and discourage the contributors you are trying to win back ([Governance notes][gov]). |
| **Communicating only through private Slack** | The public sees silence, which repeats the main cause of the reputational damage ([Fork Review notes][fr]). |

---

## 13. Mapping Roles to Recovery Actions

| # | Recovery action | Lead role | Supporting roles |
|---|---|---|---|
| A1 | Publish a public status statement (on [pysaml2#1031](https://github.com/IdentityPython/pysaml2/issues/1031), [SATOSA#503](https://github.com/IdentityPython/SATOSA/issues/503), idpy-discuss, idpy.org) acknowledging past slow reaction and stating commitments | Coordinator | Tech lead, maintainer group |
| A2 | Triage the backlog with respect: decide on every PR older than 2 years; answer every item with no comment | Core maintainers / pods | Tech lead |
| A3 | Dependency and security hygiene: Dependabot/Renovate, private vulnerability reporting, `SECURITY.md`, GitHub Actions CI ([pysaml2#1029](https://github.com/IdentityPython/pysaml2/pull/1029)) | Security lead | Release engineer |
| A4 | Publish response targets ([§9](#proposed-response-targets)) | Maintainer group | Coordinator |
| A5 | Spread release capability: PyPI organization, trusted publishing, ≥ 2 releasers per project | Release engineer | Core maintainers |
| A6 | Lifecycle labels: status badges, archive pyjwkest, an "OIDC: which library?" page, maintainers listed on idpy.org | Coordinator | Tech lead, board |
| B1 | Upstream fork changes with credit to their authors | Fork upstreaming lead | Pods, tech lead |
| B2 | Contributor ladder ([§10](#10-recruitment-pipeline)) | Maintainer group | Coordinator |
| B3 | Release and versioning policy: semver, changelogs, a Python support policy aligned with CPython end-of-life dates | Release engineer | Tech lead |
| B4 | Common tooling baseline (`pyproject.toml`, pytest, ruff), introduced gradually | Release engineer | Pods |
| B5 | Onboarding and docs: `docker compose` demo, deployment cookbooks | Documentation owner | Proxy pod, SAML core pod |
| B6 | Regular communication: monthly dashboard, quarterly updates, mailing-list cleanup | Coordinator | Release engineer |
| B7 | Named in-kind time commitments from member organisations ([§11](#11-capacity-and-in-kind-resourcing)) | Board | Coordinator |
| B8 | Simplify the portfolio to tier-1 projects | Board | Maintainer group |
| C1–C3 | Rebuild the external reputation: public retrospective, per-project roadmaps, adopter stories | Coordinator | Tech lead, pods |

---

## 14. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Organisations cannot commit named time | Medium | High | Start with whatever capacity is confirmed; reduce the number of tier-1 projects; member organisations may seek grants for their own staff (IdPy provides guidance only) |
| Technical lead becomes the new bottleneck | Medium | High | Limit tech-lead approval to risky changes only; pods merge routine changes themselves |
| Recruited fork authors drift away | Medium | Medium | Quick recognition (release notes, triager role within weeks); regular syncs |
| Burnout of the core team | Medium | High | Hard cap at the committed time; duty rotation; "seeking maintainer" as the default |
| Upstreamed fork code adds maintenance debt | Low–medium | Medium | Merge only with tests and a pod owner; reject environment-specific patches |
| A security incident during the transition | Low–medium | High | Security lead named from day one; [incident-response policy](https://github.com/IdentityPython/Governance/blob/master/idpy-incidentresponse.md) refreshed; incident-response list cleaned up ([Governance notes][gov]) |

---

## 15. Next Steps

1. **Maintainer group:** adopt this model, or an amended version, as a proposal to the board. The target is the December community update ([Governance notes][gov]).
2. **Board:** ask member organisations for written, named time commitments per pod.
3. **Coordinator:** contact the recruitment targets in [§10](#10-recruitment-pipeline).
4. **Release engineer:** set up the PyPI organization and trusted publishing for pysaml2 and SATOSA first.
5. **Security lead:** enable Dependabot/Renovate and private vulnerability reporting across the tier-1 repositories.
6. **All:** start the weekly triage duty rotation immediately. It is the cheapest and most visible change.

---

## 16. Sources

### IdentityPython meeting records (public)

- [IdPy Town Hall, 17 June 2026][th]
- [IdPy Technical Re-Kickoff, 26 June 2026][rk]
- [DRAFT IdPy Technical Transition Charter (PDF)](https://github.com/IdentityPython/Meetings/blob/master/2026-06-26%20DRAFT%20IdPY%20Technical%20Transition%20Charter.pdf)
- [Fork Review workstream notes, 15 September 2026][fr]
- [Governance workstream notes, 30 September 2026][gov]
- [Documentation workstream][doc]

### Governance

- [DRACC 0024: IdentityPython statutes](https://commonsconservancy.org/dracc/0024/)
- [DRACC 0025: project addition and removal](https://commonsconservancy.org/dracc/0025/)
- [IdPy incident-response policy](https://github.com/IdentityPython/Governance/blob/master/idpy-incidentresponse.md)

### Mailing lists

- [idpy-board: "Not sustainable" (October 2023)](https://lists.sunet.se/hyperkitty/list/idpy-board@lists.sunet.se/thread/N2LU5UBWXGLUWKRMRREOBLZVXTQPU3WR/)
- [satosa-users: SATOSA 8.5.1 images and lost demo (August 2025)](https://lists.sunet.se/hyperkitty/list/satosa-users@lists.sunet.se/thread/4S2XCN62F2X3DJKMFRYAZWSAXF4VTTX5/)

### GitHub issues and pull requests

- pysaml2: [#952](https://github.com/IdentityPython/pysaml2/issues/952), [#975](https://github.com/IdentityPython/pysaml2/issues/975), [#977](https://github.com/IdentityPython/pysaml2/pull/977), [#1012](https://github.com/IdentityPython/pysaml2/issues/1012), [#1021](https://github.com/IdentityPython/pysaml2/pull/1021), [#1024](https://github.com/IdentityPython/pysaml2/issues/1024), [#1029](https://github.com/IdentityPython/pysaml2/pull/1029), [#1031](https://github.com/IdentityPython/pysaml2/issues/1031), [#1044](https://github.com/IdentityPython/pysaml2/pull/1044)
- SATOSA: [#503](https://github.com/IdentityPython/SATOSA/issues/503)
- djangosaml2: [#412](https://github.com/IdentityPython/djangosaml2/issues/412)
- idpy-oidc: [#53](https://github.com/IdentityPython/idpy-oidc/issues/53)
- pyjwkest: [#101](https://github.com/IdentityPython/pyjwkest/issues/101)

### Forks referenced

- [SUNET/pysaml2](https://github.com/SUNET/pysaml2)
- [unigreen-alliance/SATOSA](https://github.com/unigreen-alliance/SATOSA)
- [BotoX/SATOSA](https://github.com/BotoX/SATOSA)
- [italia/iam-proxy-italia](https://github.com/italia/iam-proxy-italia)
- [GÉANT core AAI platform](https://gitlab.geant.org/core-aai-platform/)

### Metrics

The PR merge shares, times to merge and open-item ages in [§2.2](#22-measured-decline-in-responsiveness) were computed from the public GitHub REST API for the IdentityPython organization (snapshot 5 October 2026):

- **Merge share:** PRs opened in a year that were later merged, divided by all non-bot PRs opened that year.
- **Time to merge:** `merged_at − created_at`.
- **Open-item age:** measured from `created_at`.
- **"No comment":** zero discussion comments at retrieval time (PR review comments not included).

---

<div style="page-break-before: always; break-before: page;"></div>

## 17. Appendix: Initial Suggestions for the Group's Consideration

The main text describes roles by the qualities they require, and leaves the choice of people and organisations to the group. During drafting, some specific names and organisations were suggested. They are recorded here **for transparency only**. These are ideas, not decisions or nominations. Nobody listed here has been asked or has agreed, and the group may choose differently.

### 17.1 Phase 1 roles (originally in §4)

| Role | Initial suggestion | Reasoning at the time |
|---|---|---|
| Technical lead / architect | Ivan Kanakarakis | Already appointed Project Architect by the board ([Governance notes][gov]) |
| Core maintainers | Alessandro Distaso, Matthew Economou, plus 1–2 recruited fork authors | Members of the maintainer group ([Governance notes][gov]) |
| Security and dependency lead | One core maintainer, rotating | The maintainer group was collectively appointed Incident Manager ([Governance notes][gov]) |
| Release and infrastructure engineer | Matthew Economou | Existing CI/release [templates](https://github.com/ResearchDataCom/templates) and [actions](https://github.com/ResearchDataCom/actions), offered at the [Town Hall][th] |
| Fork upstreaming lead | SUNET (Alessandro), starting with SUNET's own pysaml2 changes; scope: SUNET, GÉANT, unigreen, REANNZ and iam-proxy-italia changes | [SUNET/pysaml2 divergence](https://github.com/IdentityPython/pysaml2/compare/master...SUNET:pysaml2:master) |
| Community and communications coordinator | Laura Paglione | Current coordinator, asked by the board to continue ([Governance notes][gov]) |
| Documentation and onboarding | Documentation workstream (Shayna, Hannah, Elliott) | [Documentation workstream][doc] volunteers |

### 17.2 Phase 2 pods (originally in §5)

| Pod | Initial anchor organisation(s) | Initial suggested composition | Reasoning at the time |
|---|---|---|---|
| SAML core | SUNET + 1 external maintainer | SUNET developer; author of #977 or #1021; a REANNZ or iam-proxy-italia representative | SUNET runs pysaml2 in production ([SUNET/pysaml2](https://github.com/SUNET/pysaml2)) |
| Proxy | GÉANT / RDCT + operators | GÉANT or RDCT engineer; University of Graz and TU Wien operators | Operators at the [Town Hall][th]; [GÉANT public repos](https://gitlab.geant.org/core-aai-platform/) |
| Metadata | SUNET | Current SUNET maintainers | Board formally recognized SUNET's pyFF maintenance ([Governance notes][gov]) |
| OIDC / JWT | GÉANT + Italian public sector | GÉANT developer; [iam-proxy-italia](https://github.com/italia/iam-proxy-italia) maintainer | Production use in GÉANT and Italian public-sector deployments |

### 17.3 Other examples (originally in §1, §7, §10, §11)

| Section | Original wording |
|---|---|
| §1 | "give each tier-1 project a 'pod' owned by a member organisation" |
| §7, rule 1 | Example commitment: "SUNET: 0.5 FTE on pysaml2 and pyFF" |
| §10, recruitment targets | Production fork maintainers: REANNZ, [italia/iam-proxy-italia](https://github.com/italia/iam-proxy-italia), [BotoX/SATOSA](https://github.com/BotoX/SATOSA), [unigreen-alliance/SATOSA](https://github.com/unigreen-alliance/SATOSA); operators from the University of Graz and TU Wien |
| §11.2, capacity sources | Organisations listed as examples: SUNET, GÉANT, RDCT, NIH/NIAID, Italian public sector |

[th]: https://github.com/IdentityPython/Meetings/blob/master/2026-06-17%20IdPY%20Town%20Hall/README.md
[rk]: https://github.com/IdentityPython/Meetings/blob/master/2026-06-29%20IdPy%20Technical%20Re-Kickoff/README.md
[fr]: https://github.com/IdentityPython/Meetings/blob/master/Working%20Meetings-2026%20Technical%20Re-engagement/Workstream-Fork%20Review/2026-09-15_ForkReview_Agenda-Notes.md
[gov]: https://github.com/IdentityPython/Meetings/blob/master/Working%20Meetings-2026%20Technical%20Re-engagement/Workstream-Governance/2026-09-30_Governance_Agenda-Notes.md
[doc]: https://github.com/IdentityPython/Meetings/blob/master/Working%20Meetings-2026%20Technical%20Re-engagement/Workstream%20-%20Documentation/README.md
