IdPy Worksteam: GOVERNANCE
====================================
_2026 October 14_

# Agenda
* Review Actions from last meeting
  - [ ] **Laura** - set up Google Docs for the outputs (roles, communication strategy, collaboration guidelines, common tooling)
  - [ ] **Laura** - set up a Slack channel for this conversation with external contributors (one channel across workstreams)
  - [ ] **Maintainer group** - go a little deeper in understanding how the projects are being maintained (repositories, issues, PRs) - take notes
  - [X] **Alessandro** - continue drafting notes on working philosophy/approach and share with the group
  - [ ] **Laura** - sort out and share Elliott's statute notes with the appropriate group
  - [ ] **Laura / Ivan** - (carried over) clean up the Incident response group
  - [ ] **Laura** - (carried over) simplify the processes as they are currently stated and bring back to this group
  - [ ] **Laura** - website cleanup (e.g., identify archived/obsolete repositories)
* FOR DECISION: Do we combine this workstream wtih the Fork Review one?
* Discuss any blockers or new developments
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**: Matthew, Alessandro, Robin, Derrick, Hannah, Rahmah, Elliott, Ivan, Laura

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Alessandro Distaso, Eliott Elrod, Hannah Sebuliba, Ivan Kanakarakis, Nanyonga Rahmah, Derrick Ssemanda, Matthew Economou, Robin Blair, Vlad Mencl, Federico Bond, Laura Paglione_

---

# Notes
**What IdPy projects do attendees work with?**

* Robin's organization mainly uses SATOSA.
* Derrick's organization uses Shibboleth, connected to federation metadata and eduGAIN.

**Review of project map that Alessandro created**

* [Link to the project map](../Artifacts/IdentityPython_Project_Map_By_Protocol_and_Type.md)
* Updated from yesterday - by service and area of work. It groups projects by protocol (SAML, OIDC, both, other) and by type (services, libraries, development and deployment tools).
* Ivan mentioned that djangosaml2 could be promoted to be a service
* The CBOR-related work (pyMDOC-CBOR, and Roland's related repositories) comes from the OpenID Federation and wallet space. It is used in Italian federation projects and is separate from the current core services.
* Laura mentioned putting this diagram onto the website
* Perhaps we include information about which NRENs (or other users) are working with each of the projects

**Projects (or components) that are no longer active - how should these be handled in policy?**

* Deprecate project, but don't delete it (Robin's comment)
    * Rather than deleting packages from PyPI, publish a final release that shows a deprecation warning when the package is used, pointing to an alternative. The PyPI project page should say it is deprecated too.
    * Keeping the package also stops someone else from publishing a malicious package under the same name.
* Alessandro mentioned PyPI https://pypi.org/org/idpy/
    * Some IdPy packages on PyPI aren't yet in the IdPy PyPI organization (e.g., cookie-samesite-compat, md-sign). These should be transferred, and their metadata updated to link back to the project.

**Release process**

* Is there automation to create the PyPI packages? No, it is largely manual and each project has its own process. It had been automated (CI), but when it broke (around Travis CI's policy changes), it was not restored.
* fyi, this is what we do with pysaml2: https://github.com/IdentityPython/pysaml2/blob/master/RELEASE.md
* Matthew shared his automation script, which includes PyPI deploy: https://github.com/irtnog/lethbridge/blob/main/.github/workflows/ci.yml
    * It uses GitHub Actions to automate linting, testing, versioning and package building.
    * PyPI publishing uses trusted publishing (OpenID Connect between GitHub Actions and PyPI), so no API keys or secrets need to be stored.
    * Supply chain risks matter: for example, pinning the exact versions of actions and dependencies.
* https://github.com/ResearchDataCom/actions and https://github.com/ResearchDataCom/templates are in the public domain (or under CC0 if your country doesn't have a public domain).

**What should the policy be?**

* We need to set some standards for a more harmonized process
* Ideally releases wouldn't depend on one person having special credentials. Everything goes through CI, where it is publicly reviewed and visible.
* Two parts:
    * **Policy:** what is required, including the artifacts every project must produce (for example, change logs)
    * **Implementation:** the tooling that meets the policy. A written description of tooling that could be adopted for automation would be helpful.
* Also worth agreeing: a commit message format, and possibly generating the change log automatically from commits.
* Generic direction: "automate processes through GitHub Actions": PR tests, linting, releases, etc. The more we reuse from the GitHub Actions ecosystem, the less we have to maintain.
* Harmonization: projects maintained and released in a similar way would make it easier to work across them, though some friction is expected.
* .github folder can be used to provide centralized, inherited resources for any project used by IdPy

**FOR DECISION: Do we combine this workstream with the Fork Review one?**

* The two meetings cover very similar content with mostly the same people. The group supported combining them.
* Open question: Tuesday (Fork Review slot) or Wednesday (Governance slot). Laura to check with Derrick and Mike, for whom time zones make some slots difficult.

**Schedule**

* The 28 Oct meeting is cancelled because many participants are at TechEx. The time can be used to catch up on open items

# Key Actions
- [ ] **Matthew** - write up his CI and release automation approach as a proposal for the group to consider (GitHub Actions for tests, linting and releases; trusted publishing to PyPI)
- [ ] **Ivan** - transfer IdPy packages that aren't yet in the IdPy PyPI organization (e.g., cookie-samesite-compat, md-sign), and update their metadata
- [ ] **Maintainers** - for inactive or archived packages, publish a release with a deprecation warning pointing to alternatives, rather than deleting them from PyPI
- [X] **Laura** - add Alessandro's project map to the website
- [X] **Laura** - check with Derrick and Mike on a Tuesday or Wednesday time for the combined meeting, and let everyone know
- [X] **Laura** - set up a Slack channel and send out the task list
- [X] **Laura** - set up initial files for the upcoming policies, so people can work on them offline
- [ ] **Elliott** - share more about the CISA threat intelligence tool with Matthew when the API is available
- 
- from past meetings
    - [X] **Laura** - set up Google Docs for the outputs (roles, communication strategy, collaboration guidelines, common tooling)
    - [X] **Laura** - set up a Slack channel for this conversation with external contributors (one channel across workstreams)
    - [X] **Maintainer group** - go a little deeper in understanding how the projects are being maintained (repositories, issues, PRs) - take notes
    - [ ] **Laura** - sort out and share Elliott's statute notes with the appropriate group
    - [X] **Laura / Ivan** - (carried over) clean up the Incident response group
    - [ ] **Laura** - (carried over) simplify the processes as they are currently stated and bring back to this group
    - [ ] **Laura** - website cleanup (e.g., identify archived/obsolete repositories)


