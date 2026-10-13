IdPy Worksteam: FORK REVIEW
====================================
_2026 October 13_

# Agenda
* Review updates from Board meeting & other workstreams
* Review Actions from last meeting
  - [X] **Mike** - ask Roland who is using his code base (`issuer_metadata` branch) and report back
  - [X] **Matthew / Rahmah** - correlate public forks with open pull requests to prioritize integration work
  - [ ] **Matthew / Alessandro** - reach out to past contributors and known contacts about their pending work and interest in participating
  - [ ] **Matthew / Laura** - prototype a GitHub Project board on the IdentityPython organization for the next meeting
  - [X] **Ivan** - Set up Maintainer list
  - [X] **Laura** - set up a Slack channel for the maintainers group
  - [ ] **Laura** - (carried over) pull together a list of people who have been involved in past commits and engage them
  - [ ] **Laura** - publish outstanding meeting notes (this and previous meetings, plus Board summary)
* Discuss any blockers or new developments
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**: Matthew, Alessandro, Hannah, Ramah, Laura

**REGRETS**:

**ASYNC ACTIVITY**: Mike Jones

**INVITED**: _Laura Paglione, Michael Jones, Alessandro Distaso, Ivan Kanakarakis, Hannah Sebuliba, Matthew Economou, Johan Lundberg, Vlad Mencl_

---

# Notes

**Update about Roland's IdPy Forks** _(async)_

* Roland said that the most important fork that he has is a version of idpy-oidc that is used with his OpenID Federation implementation.
* Roland believes that the mainline version of idpy-oidc doesn’t have OpenID Federation support; there are breaking changes that were necessary to support OpenID Federation
* People that have OPs or RPs that live in an OpenID Federation environment would need them

**Where to share results so we can collaborate?**

* Matthew plans to publish his team's review notes on a public GitHub Pages site (MyST Markdown) and link to it from the relevant repository.
* Links to working materials will be added to the meeting notes and to the Resources section of the Fork Review README in the "Meetings" repo of the IdentityPython organization.
* Some workstream members don't yet have contributor access to the Meetings repo. A workstream team in the IdentityPython org would fix this.
* Alessandro will share his draft analyses once there is a shared place for them.

*Who show we reach out to?**

* Use Issues & pull requests as a first pass of who to reach out to.

**Pull requests** (Rahmah did an evaluation of the pull requests)

* prioritize by repository, then age (newer is higher priority), then contributor (known contributors may be easier to collaborate with)
    * Repository: foundational libraries (e.g., PySAML2, idpy-oidc) before the applications that depend on them (e.g., SATOSA)
    * Age: newer PRs likely need less rework
    * Also consider PRs from org members and PRs previously tagged for upcoming releases
* Conduct a review - what should the guidelines be?
    * should have tests, documentation
    * Published guidelines would help contributors understand why a PR is accepted or rejected
* Authority to merge? What is the protocol and level of confidence needed before merging?
* Release schedule? - What approach should be used? (point releases? speed?)
    * Small, frequent releases show the project is actively maintained.
    * A predictable cadence (e.g., every 3–6 months) gives contributors a clear sense of what "ready" means.
    * Security fixes would follow their own schedule.

**Alessandro created a relationship graph** of how the applications and libraries depend on each other. Possible categorization additions:

  * SAML vs OIDC Federation
  * Service vs library vs other types of components (architectural layers)
  * External dependencies
    * Some projects depend on external libraries outside IdPy's control (e.g., pyop), and these aren't well documented. That makes it hard to track updates, discontinuations, or version changes.
    * Open question: is pyop meant to be replaced by idpy-oidc?
  * What projects are closed/ no longer active
    * Inactive repositories should be clearly archived (e.g., the SATOSA AWS reference architecture CloudFormation repo).

*Managing security vulnerabilities**

**Quality of the projects** - evaluate what tooling is being used for each project - to what degree should they be harmonized

* Setup varies across repositories (e.g., `setup.py` vs `pyproject.toml`), partly from the projects' Python 2.7 origins. Harmonizing would make collaborating easier and faster.
* Pick a baseline - update code to this baseline
* write a proposal of what to do
* Catalog what tooling the existing repos are using

**Other**

* links to some free accounts that we may be able to use - Alessandro
* Events:
    * TIIME conference: Laura and Matthew plan to attend. A BoF or side meeting for IdPy has been suggested.
    * A December community town hall was suggested to keep momentum and promote the in-person meeting.
* Meeting consolidation: The Fork Review and Governance meetings have nearly the same participants. The group favors combining them. This Wednesday's Governance meeting stays on the calendar so Ivan can weigh in.

# Key Actions
- [ ] **Matthew** review Alessandro's map and make suggestions on additional information to include (e.g., sketch a revised layered diagram for the website)
- [ ] **Matthew** propose a baseline for tooling (for discussion at the next call)
- [ ] **Matthew** catalog what tooling and versions the existing repos are using
- [ ] **Matthew** publish review materials on a public GitHub Pages site and link to it from the relevant repository
- [ ] **Alessandro** share his analysis results and drafts in the Meetings repo
- [ ] **Laura** propose what to do for TIIME conference (BoF - add to event?)
- [ ] **Laura** create a new team in the IdentityPython org for workstream members and give them access to the Meetings repo.
- [ ] **Matthew / Alessandro** - (carried over) reach out to past contributors and known contacts about their pending work and interest in participating
- [ ] **Matthew / Laura** - (carried over) prototype a GitHub Project board on the IdentityPython organization for the next meeting
- [ ] **Laura** - (carried over) pull together a list of people who have been involved in past commits and engage them
- [ ] **Laura** - (carried over) publish outstanding meeting notes (this and previous meetings, plus Board summary)

