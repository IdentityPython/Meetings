IdPy Working Meetings: ARTIFACTS
==================================

This folder collects the documents produced by the 2026 Technical Re-engagement workstreams. Together, they will describe how IdentityPython projects are run: the policies contributors follow, the processes they use, shared tooling, and the guidance and analysis behind them.

If you use or contribute to an IdentityPython project, start with [Current asks](#current-asks) to see where your input is needed now, then browse the [artifacts](#artifacts) by what you're looking for.

---

## Current asks
The following require input from Workstream members & the community. The list is refreshed every week and kept to five items or fewer.

**How to respond:** for working drafts, edit or comment directly in the Google Doc. For items you can read on GitHub, open an [issue](https://github.com/IdentityPython/Meetings/issues) or a pull request, or bring it to the next workstream meeting.

> [!NOTE]
> _Updated **12 November 2026** · next update **19 November 2026**_
>
> 1. **Comment on the documentation policy rows still to be discussed (sections B, C and E)**
  >    * **Artifact:** [Documentation Policy: Working Document](https://docs.google.com/document/d/1AgS15-xktdid1GWwDlCmMzbjMmJsenLG40RHX4CBdAs/edit?usp=sharing) (Google Doc, working draft; workstream participants only)
  >    * **What's needed:** for each row in section 3 tables B (style), C (tooling) and E (ownership), say whether you can live with the starting position. If you can't, suggest a change.
  >    * **Who:** Documentation workstream, especially anyone who missed the 4 Nov meeting
>    * **By:** 17 Nov, ahead of the 18 Nov Documentation meeting
> 2. **Check the inventory for the projects you know**
>    * **Artifact:** [Documentation Inventory](2026-11%20DRAFT%20IdPy%20Documentation%20Inventory.md)
>    * **What's needed:** on the detail sheet for a project you use or maintain, check the items marked **[Inference]** and the 0–3 ratings. Correct anything that's wrong and mark the row "reviewed." Start with pysaml2, SATOSA, pyFF and idpy-oidc.
>    * **Who:** anyone who uses or maintains these projects
>    * **By:** 1 Dec (first look at the 18 Nov meeting)
> 3. **New Resources for Review** - Items that have been added since the last update
>    * Tooling & Templates
>      * **[Documentation templates](2026-11%20DRAFT%20IdPy%20Documentation%20Templates.md)** - _Examples of templates for the pages every project should have (overview, getting started, etc.), with guidance for using the templates with an LLM._
>    * Guidance & examples
>      * **[Documentation Examples](2026-11%20DRAFT%20IdPy%20Documentation%20Examples.md)** - _Documentation from other projects worth learning from. Each entry says what to borrow and which part of IdPy's documentation it could inform. Includes frameworks such as Diátaxis, peer identity projects, and our own experiments._
>    * Background & analysis
>      * **[GitHub Repository Review](2026-11%20IdPy%20GitHub%20Repository%20Review.md)** - _An inventory of the repositories in the IdentityPython organization on GitHub._


<!--
### Recently completed
_Items from last week's list that are done. They stay here for one week._

* _(none yet)_
-->
---

## Artifacts

**Types of Resources:** The artifacts are grouped by the role they will play for anyone who uses or contributes to an IdentityPython project:

| If you want to know…                                                                                                | Look at                                            |
|---------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|
| What rules apply to me if I contribute to or maintain a project?                                                    | [**Policies**](#policies)                          |
| How do I get something done, such as reporting a vulnerability, making a release, or getting a pull request merged? | [**Processes**](#processes)                        |
| What shared tools and templates should I use?                                                                       | [**Tooling & templates**](#tooling--templates)     |
| How can I do this well?                                                                                             | [**Guidance & examples**](#guidance--examples)     |
| Why were these decisions made, and what did we find?                                                                | [**Background & analysis**](#background--analysis) |

**Status** shows where each item is in its life cycle:
* ✍️ **Working draft:** being actively written by workstream members in a shared Google Doc (linked in the Status column). This is the stage for filling gaps, proposing larger changes, and adding new content. Access to the Google Doc is limited to workstream participants, and any copy on GitHub may be out of date. To take part, [join a workstream](../README.md#workstreams).
* 📄 **Read it on GitHub:** the version on GitHub is current. Anyone can read it and react through an [issue](https://github.com/IdentityPython/Meetings/issues), a pull request, or at a workstream meeting.
* 🧪 **Try the experiment:** a prototype to look at and learn from.
* 📨 **Proposed:** sent to the maintainer group or Board for consent.
* ✅ **Adopted:** in effect.
* 🗓️ **Coming later:** a workstream has committed to producing it.

### Policies
_Rules that IdentityPython projects and their contributors are expected to follow._

| Artifact                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Status                                                                                                                                                                  |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Documentation Policy: [Working Document](2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md)**<br/><sub>_The future policy on what documentation every IdPy project needs, how it is written and built, and what a pull request must include. Today it is a discussion guide. For each topic, it proposes how strongly IdPy should ask for it and whether IdPy or each project decides the details. It will become a one-page policy recommendation. The version on GitHub (linked above) is a 4 Nov snapshot._</sub><br/><br/><sub>Workstream: Documentation</sub> | ✍️ Working draft<br/>[Google Doc](https://docs.google.com/document/d/1AgS15-xktdid1GWwDlCmMzbjMmJsenLG40RHX4CBdAs/edit?usp=sharing) _(workstream participants)_ |
| **Contribution guidelines**<br/><sub>_High-level guidelines for contributing to any IdPy project._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later |
| **Roles and maintainer model**<br/><sub>_Who maintains what, what maintainers are responsible for, and how people become maintainers._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later |
| **[Project Statutes](https://github.com/IdentityPython/Governance/blob/master/idpy-statutes.md)**<br/><sub>_IdentityPython's founding governance document._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 📄 Read it on GitHub<br/><sub>_Predates 2026; to be reviewed_</sub> |
| **[Project Addition Policy](https://github.com/IdentityPython/Governance/blob/master/idpy-projects.md)**<br/><sub>_How a project becomes part of IdentityPython._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 📄 Read it on GitHub<br/><sub>_Predates 2026; to be reviewed_</sub> |

### Processes
_Step-by-step ways of getting things done._

| Artifact                                                                                                                                                                                                                               | Status   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| **[Security Incident Response Plan](https://github.com/IdentityPython/Governance/blob/master/idpy-incidentresponse.md)**<br/><sub>_How security incidents in IdPy projects are handled._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 📄 Read it on GitHub<br/><sub>_Predates 2026; to be reviewed_</sub> |
| **Release process**<br/><sub>_How a maintainer cuts a release, aiming for releases that are easy, frequent and automated._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later |
| **Fork integration approach**<br/><sub>_How changes in community forks are evaluated and brought back into the main projects._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later |
| **Communications strategy**<br/><sub>_How the project communicates with its community, and where to find what._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later |

### Tooling & templates
_Shared tools, configurations and templates that projects can adopt._

| Artifact                                                                                                                                                                                                                | Status                             |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| **Common tooling baseline**<br/><sub>_A shared baseline for packaging, testing and CI across IdPy projects._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later |
| **Documentation toolchain proposal**<br/><sub>_A proposed standard way to build and publish documentation._</sub><br/><br/><sub>Workstream: Documentation</sub> | 🗓️ Coming later |
| **[Documentation templates](2026-11%20DRAFT%20IdPy%20Documentation%20Templates.md)**<br/><sub>_Templates for the pages every project should have (overview, getting started, etc.)._</sub><br/><br/><sub>Workstream: Documentation</sub> | 📄 Read it on GitHub<br/><sub>_Initial draft, not yet reviewed_</sub> |

### Guidance & examples
_Advice and good examples to learn from. Not rules._

| Artifact                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Status           |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|
| **[Documentation Examples](2026-11%20DRAFT%20IdPy%20Documentation%20Examples.md)**<br/><sub>_Documentation from other projects worth learning from. Each entry says what to borrow and which part of IdPy's documentation it could inform. Includes frameworks such as Diátaxis, peer identity projects, and our own experiments._</sub><br/><br/><sub>Workstream: Documentation</sub>                                                                                                                                                                           | 📄 Read it on GitHub |
| **[Auto-generated docs experiment: GitHub Pages](https://sebulibah.github.io/pysaml2/)** _(Hannah)_<br/><sub>_API reference generated from the docstrings in pysaml2's [`saml2.client`](https://github.com/IdentityPython/pysaml2/blob/master/src/saml2/client.py) (Sphinx with autodoc2, Markdown), plus added type hints for cross-references._</sub><br/><br/><sub>Workstream: Documentation</sub>                                                                                                                                                            | 🧪 Try the experiment |
| **[Auto-generated docs experiment: Read the Docs](https://rtd-docs-example.readthedocs.io/en/latest/)** _(Laura)_<br/><sub>_The same pysaml2 source, used for an AI-assisted prototype of user-focused summaries and class reference on Read the Docs. This resource also has an analysis of the effectiveness of the docstrings in the clint.py code that was chosen for the example, and a description of what would be included in an improved set. (this improved documentation was auto created by AI._</sub><br/><br/><sub>Workstream: Documentation</sub> | 🧪 Try the experiment |

### Background & analysis
_Research and findings that inform the policies and processes above._

| Artifact                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Status                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|
| **[Documentation Inventory](2026-11%20DRAFT%20IdPy%20Documentation%20Inventory.md) _(Laura)_**<br/><sub>_A survey of the documentation in each of the 18 active public IdentityPython repositories, checked against the questions in the (in-progress) [Documentation Policy](2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md). It has key findings across projects and a detail sheet per repository. The first pass was AI-assisted and drawn from the repositories themselves. Unverified conclusions require review_</sub><br/><br/><sub>Workstream: Documentation</sub> | 📄 Read it on GitHub |
| **[pysaml2 documentation gap analysis](https://docs.google.com/document/d/1vpJlsZIX1_bzvt071hdsNXEr-Rk8hXoTjL-yF3t5MOQ/)** _(Hannah)_<br/><sub>_An outline of pysaml2's documentation organized by Diátaxis type (tutorials, how-to guides, reference, explanation), with current status, required steps, and roadmap ideas._</sub><br/><br/><sub>Workstream: Documentation</sub> | ✍️ Working draft<br/>[Google Doc](https://docs.google.com/document/d/1vpJlsZIX1_bzvt071hdsNXEr-Rk8hXoTjL-yF3t5MOQ/) _(workstream participants)_ |
| **Fork and pull request review** _(Rahmah)_<br/><sub>_Analysis of public forks and open pull requests across the core repositories, used to prioritize integration work._</sub><br/><br/><sub>Workstream: Governance & Fork Review</sub> | 🗓️ Coming later<br/><sub>_To be published_</sub> |
| **Asset Custody Plan** _(to be shared after Board Review)_<br/><sub>_Plan for transferring IdentityPython project assets to be closer to institutional control by the project._</sub><br/><br/><sub>BOARD REQUEST</sub> | 📨 Proposed |
| **[GitHub Repository Review](2026-11%20IdPy%20GitHub%20Repository%20Review.md) _(Laura)_**<br/><sub>_An inventory of the repositories in the IdentityPython organization on GitHub._</sub><br/><br/><sub>Workstream: GENERAL</sub> | 📄 Read it on GitHub |

---

## How to contribute

Everyone in the community is welcome to review, add to, or comment on these artifacts.

* **Comment or suggest a change:** open an [issue](https://github.com/IdentityPython/Meetings/issues) or a pull request against the document.
* **Working drafts:** some documents are written collaboratively in a shared Google Doc before they are published here. Access is limited to workstream participants. If you'd like to help write them, [join a workstream](../README.md#workstreams). Until a working draft is published, any copy in this folder is a snapshot and may be out of date.
* **Discuss in a meeting:** each artifact is reviewed in its workstream's meetings (see the [workstream folders](../README.md#workstreams)).

---
## More information

Project homepage: https://idpy.org
