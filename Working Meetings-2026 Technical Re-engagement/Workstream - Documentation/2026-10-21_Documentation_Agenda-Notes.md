IdPy Worksteam: DOCUMENTATION
====================================
_2026 October 21_

# Agenda
* Review and consent to Key Deliverables, Goals, and Tasks
  - [ ] **All** consider which projects to prioritize for documentation and bring thoughts to the next meeting
  - [ ] **All** start an improved SATOSA getting-started how-to guide as the first documentation example
* AI-Generated Documentation: An example from pyFF
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**: Derrick, Elliott, Hannah, Laura, Rahmah, Matthew, and Shannon Roddy (LBL)

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl, Shannon Roddy_

---

# Notes

**Focus for this workstream**

* The goal is to agree on high-level documentation guidelines and requirements that apply across *all* IdentityPython projects. This guidance would be shared with the community at the December town hall.
* A participant raised a concern about spending limited volunteer time on evaluating toolkits for individual projects. The group will focus on shared guidance first.

**What kinds of documentation should every project have?**

* Building on the [Diátaxis](https://diataxis.fr/) framework discussed at the last meeting (tutorials, how-to guides, reference, explanation), participants suggested:
    * Documentation organized by audience: users/operators, administrators, and developers.
    * Consistent "front matter" for every project:
        * what the project is and its common uses
        * how to install it
        * a getting-started guide
    * Tracking dependencies (e.g., a software bill of materials), so that when a vulnerability is announced it's quick to see which components need updating.
* The current idpy-oidc documentation was reviewed against these categories, and several gaps were noted.
* Examples of good documentation:
    * [pytest](https://docs.pytest.org/en/stable/), a short working example on the first screen, organized around use cases
    * the [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/), a comprehensive, well-structured reference with a clear narrative
* Shared front-matter templates would help keep projects consistent.

**Proposed documentation tooling**

* Matthew proposed one toolchain across IdPy projects:
    * Sphinx with the Sphinx Book Theme
    * MyST Markdown
    * autodoc for API documentation generated from the code
    * GitHub Pages for hosting
* The group asked Matthew to write this up as a formal proposal for review at a future meeting. No decision yet.

**AI-assisted documentation**

* Shannon Roddy (LBNL) shared an experiment: an LLM-generated documentation set for pyFF, produced in about 10 minutes. It includes introductory material (e.g., an overview of the Metadata Query Protocol) as well as configuration and usage.
* Laura reported similar results using AI with templates to produce user-focused documentation from code and training materials.
* Discussion points:
    * AI output is a useful starting point and "force multiplier."
    * It still needs human review.
    * It tends to miss the *why*: architectural context and the reasons behind design choices. That is where human authors add the most value.
    * Giving the AI a template of the expected structure helps produce consistent output across projects.
* Running models at scale has costs. Options mentioned:
    * open-weight models
    * research computing resources or grants
    * contributed resources from participating organizations

# Key Actions
- [ ] **Matthew** write up the proposed documentation structure and tooling for review by the group
- [ ] **Laura** share example documentation templates (front matter / structure)
- [ ] **Laura** share examples of projects with high-quality documentation
- [ ] **Shannon** try a revised prompt that incorporates the Diátaxis structure and the agreed requirements
- [ ] **Matthew** test open-weight models against proprietary models for generating technical documentation
