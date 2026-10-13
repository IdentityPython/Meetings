IdPy Worksteam: FORK REVIEW
====================================
_2026 September 29_

# Agenda
* Review updates from Board meeting & other workstreams
* Review Actions from last meeting:
  * Completed before the meeting - no report
    - [X] **Ivan** - respond to the Slack group message from Davide (GARR)
    - [X] **Ivan** - merge pending crypto-library MRs and publish a release; apply planned fixes to the current SATOSA release
  * See Notes Within - reported on this meeting
    - [X] **Matthew** provide a more in depth analysis of the state of the public forks to get a more detailed idea of what has been changed and how they are behind (versions, fork origins, branches) - for the next Fork Review meeting
    - [x] **Laura** bring this group's input on trust-building, maintainer responsibilities, and response-time expectations to the Governance workstream (2026-09-16)
  * Abandoned (funding not available)
    - [X] **Alessandro** can take a look at the Security tools within GitHub / dependencies ([Github-advanced-security Bot](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)) - note, there is a cost associated with this tool
  * Still Outstanding
    - [ ] **Laura** pull together a list of people who have been involved in commits in the past and try to engage them in this work (look for work beyond the main branches)

* Discuss any blockers or new developments
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**:

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Michael Jones, Alessandro Distaso, Ivan Kanakarakis, Hannah Sebuliba, Matthew Economou, Johan Lundberg, Vlad Mencl_

---

# Notes

**Updates from Board meeting & other workstreams**

* The Board appointed a maintainer group (Matthew, Alessandro, Ivan). Board members are expected to contribute in-kind resources. Board notes will be published in the IdentityPython repositories.
* The Board has suspended discussion about contracting with Roland (re: incorporating [OIDC contributions](https://github.com/IdentityPython/idpy-oidc/tree/issuer_metadata)) until the maintainer group and fork workstream have an opportunity to review and provide a recommendation.
    * This is a branch (`issuer_metadata`) in idpy-oidc rather than a separate fork. Before merging to master it needs cleanup, conflict resolution, and a proper PyPI release.
    * Nikos is working on the SATOSA OpenID Connect frontend, which will help align this branch.
    * Ask Roland who is using this work. SUNET is using it?
        * GÉANT was using it as prototype for wallets
        * SUNET previously used it for wallet prototypes but is moving to other libraries
        * If there are people who are using this code, we should have them involved - testers, etc
* Contribution Notes: RDCT has dedicated Rahmah full-time to supporting IdPy; Laura's coordination time is also supported by RDCT.

**Analysis of the state of the public forks (Matthew)**

* Use GitHub Project for project management - task board using GitHub Issues
* Did Fork reviews - did a SATOSA review (75 active forks). Rahmah also reviewed forks of pyFF, PySAML2, and idpy-oidc (manual review).
* Shared his team's GitHub + Sphinx/Markdown documentation setup as a possible model for the Documentation workstream

**PROCESS SUGGESTIONS:**
How do we decide what should be implemented and the level of effort that will be needed to do so

* What are we trying to do here?
    * Forks are created for many reasons, so it is difficult to understand if these are all things that should be brought back to the project - forks are signs of how popular the projects are (many are created just to submit a PR) - The goal may not be to try to eliminate forks
    * Need to identify who are the contributors and engage with those with active PRs
    * Reach out to those related to the project and specifically those with existing PRs
    * Correlate unmerged forks with open pull requests
    * Collect data and prioritize it
* Prioritize forks by outstanding pull requests & issues
* Also consider infomration about the contributor -
    * have they been active in this community?
    * Are they easy to reach?
    * What is their history/willingness in being involved
* Re-engage socially with past contributors who forked because the main repository lacked activity.
* An external party has expressed interest in funding work on specific pull requests.
* Tooling:
    * Project board in GitHub - Matthew & Laura to prototype something for next meeting
    * Laura to set up Slack (persistent information still lives in GitHub)

## Key Actions

- [ ] **Mike** - ask Roland who is using his code base (`issuer_metadata` branch) and report back
- [ ] **Matthew / Rahmah** - correlate public forks with open pull requests to prioritize integration work
- [ ] **Matthew / Alessandro** - reach out to past contributors and known contacts about their pending work and interest in participating
- [ ] **Matthew / Laura** - prototype a GitHub Project board on the IdentityPython organization for the next meeting
- [ ] **Laura** - set up a Slack channel for the group
- [ ] **Laura** - (carried over) pull together a list of people who have been involved in past commits and engage them
- [ ] **Laura** - publish outstanding meeting notes (this and previous meetings, plus Board summary)
