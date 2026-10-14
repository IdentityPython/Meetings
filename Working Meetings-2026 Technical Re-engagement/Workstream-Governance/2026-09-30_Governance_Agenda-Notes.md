IdPy Worksteam: GOVERNANCE
====================================
_2026 September 30_

# Agenda
* Review Actions from last meeting:
  - [X] **Elliott** found things that are in the statutes that either didn't make sense - he will formalize these notes and share with the group
  - [ ] **Laura / Ivan** - clean up the Incident response group (remove inactive/outdated members)
  - [ ] **Laura** - simplify the processes as they are currently stated and bring back to this group
* Discuss any blockers or new developments
* Determine the tasks we'll accomplish for the next meeting

# Attendees

**IN ATTENDANCE**: Elliott Elrod, Rahmah Nanyonga, Hannah Sebuila, Alessandro Distaso, Ivan Kanakarakis

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Alessandro Distaso, Eliott Elrod, Hannah Sebuliba, Ivan Kanakarakis, Nanyonga Rahmah, Derrick Ssemanda, Matthew Economou, Robin Blair, Vlad Mencl, Federico Bond, Laura Paglione_

---

# Notes

**Updates from Board meeting**

* The Board established the maintainer group as a committee of the Board, with initial members Alessandro, Matthew, and Ivan, and the authority to co-opt other maintainers (reporting changes to the Board).
* Ivan appointed Project Architect; the maintainer group collectively appointed Incident Manager. All roles are transitional.
* The Board asked Laura to continue in the coordination role, to the extent these groups request it.
* The Board formally recognized SUNET's contributions to pyFF and its agreement to continue maintaining it.

**Review of actions from last meeting**

* Elliott: Statute notes sent; Laura to sort out where they go and share them.
* Ivan: Done (responded to Davide on Slack).
* Laura / Ivan: Incident response group cleanup not yet done.
* Laura: Process simplification not yet done.

**Process/Policy Needs**

* Coding standards - could be different - there is a lot of diversity in how the projects have been developed
    * Reformatting whole codebases at once (e.g., with black) would produce huge diffs; better to start with high-level guidelines (e.g., conventional commits, test-driven development)
    * Packaging also varies across repositories; pyproject.toml is becoming the de facto standard
* Testing, actions, publication processes (e.g., run tests and package publication through GitHub Actions)
* Contributor guidelines might be easier place to start
* Do we try to get more people
    * Go back through repositories and answer neglected PRs and issues; recent activity shows people still care

Need to have more communication

* SATOSA mailing list - e.g., the SATOSA contribution guide doesn't mention the SATOSA mailing list
* Small, basic cleanups would make it easier for external people to contribute and communicate with us

**Three outputs** (for Board review and community consent; roughly three months of work)

* Communications strategy
    * Clean up website - clarity on what exists and how we maintain it (website should describe each project and list its maintainers)
    * Project management
* High-level contribution guidelines
* Common tooling (for example, packaging)

**Scope**

* To avoid overpromising and volunteer burnout, projects without a designated maintainer are treated as out of scope until someone steps up.
* Aim for at least two maintainers per project; start by getting at least one.

Matthew suggested the following to be the projects that we actively find maintainers for

[PySAML2](https://github.com/IdentityPython/pysaml2)
a pure Python implementation of version 2.0 of the Security
Assertion Markup Language (SAML), including the components required
to build a service provider (relying party) and an identity
provider

[pyFF](https://github.com/IdentityPython/pyFF)
a SAML metadata aggregator that implements the latest draft of the
Metadata Query Protocol, which alleviates scaling issues related to
federation metadata aggregate signing, distribution, and lookup

[SATOSA](https://github.com/IdentityPython/SATOSA)
translates between different authentication protocols, such as SAML
2.0, OpenID Connect, and OAuth 2.0—a key feature of the
[Authentication and Authorisation for Research and Collaboration (AARC)
Blueprint Architecture (BPA)](https://aarc-community.org/)

[idpy-oidc](https://github.com/IdentityPython/idpy-oidc)
a pure Python implementation of version 1.0 of OpenID Connect
similar to PySAML2, including the components required to build an
OIDC relying party, an OpenID identity provider, or an OpenID
authorization server

[JWT Connect Python](https://jwtconnect.io/)
a collection of OIDC relying party (client) libraries

There are [18 repositories](https://github.com/orgs/IdentityPython/repositories?q=-archived%3Atrue%20-visibility%3Aprivate) that aren't archived, but are publicly visible.

**Draft documents to set up**

* List of roles
* Communication Strategy
* Collaboration Guidelines
* Common Tooling

Drafting will happen in Google Docs temporarily; final versions live as Markdown in GitHub. One shared Slack channel across all workstreams for real-time discussion while drafting.

**Maintainers:**

* Governance, Meetings, Website - Laura
* pyFF - SUNET

**Timeline:** Target a community update in December (about six months after the June town hall), before the holidays, to set up 2027.


**Updates**

* Incident response mailing list: Laura now has moderation access and can push through legitimate messages. The recipient list includes inactive members and needs cleanup. Some SUNET/Outlook addresses are not receiving list mail (likely domain alignment); to be checked.
* Ivan's near-term technical plans: merge pending MRs on the crypto library for a new release, and apply planned fixes to the current SATOSA release.

## Key Actions

- [ ] **Laura** - set up Google Docs for the outputs (roles, communication strategy, collaboration guidelines, common tooling)
- [ ] **Laura** - set up a Slack channel for this conversation with external contributors (one channel across workstreams)
- [ ] **Maintainer group** - go a little deeper in understanding how the projects are being maintained (repositories, issues, PRs) - take notes
- [ ] **Alessandro** - continue drafting notes on working philosophy/approach and share with the group
- [ ] **Laura** - sort out and share Elliott's statute notes with the appropriate group
- [ ] **Laura / Ivan** - (carried over) clean up the Incident response group
- [ ] **Laura** - (carried over) simplify the processes as they are currently stated and bring back to this group
- [ ] **Laura** - website cleanup (e.g., identify archived/obsolete repositories)

----

## REFERENCE

_Sample content for the upcoming documents - to be considered for policy starting points_

**Governance section of the IdPy**

* Key qualities
    * People have time (capabilities too)
    * Group with succession planning / Mentorship
    * Proper tools
    * Guidance documents / information about how to do the job
* Properties / Policies
    * More than one maintainer for each part of the project << RESOURCES!
    * Time? Response? pull request acknowledgement/review/result
* Building back trust
    * acknowledging what hadn't worked in the past
    * Note that we are trying to change
    * Streamlining governance processes is part of rebuilding trust
* Do we have a people challenge or a role definition challenge?
    * Probably a combination of both
* Current governance documents are formal and hard for newcomers to navigate. A simplified overview of roles would help guide new participants.
* Open questions: how to handle old moderation items (back to 2023), and how to evaluate external offers to sponsor merging code from forks.

**Security/incidents**

* Next steps
    * Triage: What has not been addressed? What things are blocked? Evaluate why. _(There are fixes for some of the more immediate things)_
    * COMMUNICATE!!
        * Follow up with community about what this group is doing
        * Increase clarity about the process and people
* If things were perfect
    * Incident manager collects requests, etc and brings it to the maintainers of the group
    * the maintainers prioritize - critical items prioritized
    * Schedule work accordingly
    * Why isn't this happening now? right now we are treating all of the projects equally and there is only one maintainer stream (vs, per project)

**Maintainers**

* Role of maintainers
    * Maintainers act as technical leads: guide architecture, write code, review and merge changes, and manage releases.
* Transition Maintainer group
    * goal: the group would have authorization to merge (stewardship and triage of open PRs during the restart)
    * Who? Ivan, Alessandro, Matthew (open to others who want to join)
    * Goal to ensure that there are at least 2 maintainers for each project
    * Proposed that the group be able to expand its own membership without further board approval
    * To be brought to the Board for approval
* Communicate clearly to the community which projects have active maintainers.

**Project Architect** - Ivan (interim) and possibly another person

* understands the structure of the set of tools that can intercommunicate - system with multiple components (projects)
* Advises on how a change will impact other parts of the system
* Advises on how to improve things / provides direction

**Incident Manager** - Maintainer group (interim)

**Coordination role**
* keeps the workflow moving, keeps reporters informed, drives toward a resolution
* Laura will continue to participate in the Coordination role

In the interim, multiple people can fulfil roles, and one person can fulfil multiple roles