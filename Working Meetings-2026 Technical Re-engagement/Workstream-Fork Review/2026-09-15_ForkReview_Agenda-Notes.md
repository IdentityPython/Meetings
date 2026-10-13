IdPy Worksteam: FORK REVIEW
====================================
_2026 September 15_

# Agenda
* Review and consent to Key Deliverables, Goals, and Tasks
* Consent to high-level schedule through the end of 2026
* Determine the tasks we'll accomplish for the next meeting

# Attendees

**IN ATTENDANCE**: Alessandro Distaso, Ivan Kanakarakis, Hannah Sebuliba, Laura Paglione, Rahmah Nanyonga, Matthew Economou

**REGRETS**: Michael Jones, Johan Lundberg, Vlad Mencl

**ASYNC ACTIVITY**:

**INVITED**: _Alessandro Distaso, Ivan Kanakarakis, Hannah Sebuliba, Laura Paglione, Rahmah Nanyonga. Michael Jones, Matthew Economou, Johan Lundberg, Vlad Mencl_

---

# Notes

**Workstream kickoff**

* Reviewed workstream scope and deliverables: catalog of forked projects, prioritized integration roadmap, integration guidelines, and access to known private forks. Eight meetings scheduled through end of 2026 (every other week).
* Reviewed the July snapshot of public forks for PySAML2 and SATOSA; several forks are clearly out of sync with upstream. Assessing forks is manual (GitHub has no native comparative view), so it takes time.

**Repositories in scope**

_What repos should be prioritized? The following were suggested as candidates_

* [PySAML2](https://github.com/IdentityPython/pysaml2), a pure Python implementation of SAML. It contains all necessary pieces for building a SAML service provider (relying party) or an identity provider.
* [pyFF](https://github.com/IdentityPython/pyFF), a SAML metadata aggregator. It features an implementation of the latest draft of the Metadata Query Protocol, which alleviates scaling issues as federation metadata aggregates grow in size.
* [SATOSA](https://github.com/IdentityPython/SATOSA), a configurable proxy that translates between different authentication protocols, such as SAML2, OpenID Connect, and OAuth2, a key feature of the Authentication and Authorisation for Research and Collaboration (AARC) Blueprint Architecture (BPA).
* [idpy-oidc](https://github.com/IdentityPython/idpy-oidc), a pure Python implementation of OpenID Connect. Like PySAML2, this contains all the necessary pieces for building an OIDC relying party, an OpenID provider, or an authorization server.
* [JWT Connect Python](https://jwtconnect.io/), a collection of OIDC relying party (client) libraries.
* PySAML2 and SATOSA identified as the immediate priorities; open questions remain about the OIDC components.

**Current state of the repositories**

* PySAML2 and SATOSA are maintained by a small group; work has been bottlenecked waiting on review/merge. Ivan has prepared changes ready to push.
* Some libraries are effectively orphaned and will need maintainer teams. Maintainer teams and policies are being addressed in the Governance workstream.
* There are a group of maintainers (at least in permissions, if not in action) that are associated with IdPy. The GitHub organization lists 28 members; team memberships map to specific repositories, and some people have repository access without being organization members. Membership reconciliation deferred to a future meeting.

**Strategies for connecting with people**

* CONFERENCES --- _Note: Conferences are valuable for human contact, but waiting for them alone adds too much latency_
    * Add a session (BoF discussion) to TechEx agenda, probably for the ACamp unconference
    * Propose a [TNC BoF](https://tnc27.geant.org/)
    * Consider a proposal for the [TIIME conference](https://tiime-unconference.eu/)
* **Reach out to people through GitHub (may be difficult)**
* IdPy Mailing list (note: spam issues)
* Slack

**Who to connect with**

_NOTE: there mayu be a lack of interest because of past failures. We will need to demonstrate that things are different._

* People who have opened issues
* Use our personal contacts to find the right person at places like CERN; LIGO; CILogon, other large VO Operators
* Reach out to people who have been committers
* Town hall participants

**What do we tell them?**

* GOAL-Building back trust: recognition of the past slow reaction from the maintainer of the project; why is this time different?
    * Do this through action, not promises (delivering code and new releases)
    * Mandate from governance - response time; information about how we ensure action
    * Matthew's organization may commit some resources.
* Discuss the responsibility of the community
    * What are community expectations - take ownership, engage, review work, etc
* Policy from the organization _(To be addressed by the Governance Workstream...)_
    * Response time (acknowledgement | specific response | update)
    * Resource expectations
* Is it possible to bring private repositories into the mix? who has them and what can they share?

**Possible strategy for what is merged/reviewed**

1. ensure we have addressed security issues (update dependencies, fix security issues)
2. Modernize the stack (e.g., newer Python versions)
3. Documentation _(To be addressed by the Documentation Workstream)_

Later: consider the underlying architecture to understand what changes may be needed.

* Tools such as GitHub security checks / Dependabot could help identify forks with up-to-date dependencies. (requires financial resources)
* Preferred contribution practice: keep a fork's main branch in sync with upstream and do work in separate branches (rather than PRs from a fork's main branch).

**General Fork Analysis**
* NOTE: For the work under GÉANT the public repositories are here: https://gitlab.geant.org/core-aai-platform/
* NOTE: From SUNET there is some work here - but it's mostly plugins: https://github.com/SUNET/swamid-satosa. I don't think there are any other forks/patches to the projects. There are a few PRs on the upstream repos under identitypython.
* Need to also look at subbranches - not just the main branch - to see what has changed
* Rather than reporting on every fork, prioritize known, engaged community members and bring diverged work back to the main repositories.

**Communicatio Strategyn**

* GitHub issues/comments will be the primary place for project discussion and decisions, so there is a lasting, searchable record. Slack remains available for real-time/informal pings; substantive outcomes get recorded in GitHub.

## Key Actions

- [ ] **Alessandro** can take a look at the Security tools within GitHub / dependencies ([Github-advanced-security Bot](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)) - note, there is a cost associated with this tool
- [ ] **Matthew** provide a more in depth analysis of the state of the public forks to get a more detailed idea of what has been changed and how they are behind (versions, fork origins, branches) - for the next Fork Review meeting
- [ ] **Laura** pull together a list of people who have been involved in commits in the past and try to engage them in this work (look for work beyond the main branches)
- [X] **Ivan** - respond to the Slack group message from Davide (GARR)
- [X] **Ivan** - merge pending crypto-library MRs and publish a release; apply planned fixes to the current SATOSA release
- [x] **Laura** bring this group's input on trust-building, maintainer responsibilities, and response-time expectations to the Governance workstream (2026-09-16)
