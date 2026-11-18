IdPy Worksteam: DOCUMENTATION
====================================
_2026 November 18_

# Agenda
* Review Actions from past meeting
    - [ ] Documentation structure and tooling proposal _(Matthew)_
    - [X] Documentation inventory template _(Laura)_ (draft to be reviewed in next meeting)
    - [ ] [Examples](../Artifacts/2026-11%20DRAFT%20IdPy%20Documentation%20Examples.md) of high-quality documentation _(Laura)_
    - [ ] [Documentation Inventory](../Artifacts/2026-11%20DRAFT%20IdPy%20Documentation%20Inventory.md) _(First pass, w/AI assist)_
* Further the discussion about [IdPy Documentation Policy](https://docs.google.com/document/d/1AgS15-xktdid1GWwDlCmMzbjMmJsenLG40RHX4CBdAs/edit?usp=sharing) 
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**: Hannah Sebuliba, Nanyonga Rahmah, Elliott Elrod, Laura Paglione

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl, Shannon Roddy_

---

# Notes
**Artifacts and next steps**

* Reviewed the structure of the new [Artifacts](../Artifacts) section of the Meetings repository and discussed next steps for the Documentation Workstream.
    * All workstream deliverables are now in one place, grouped by role: policies, processes, tooling and templates, guidance and examples, and background and analysis. "Current asks" at the top lists what needs input now.
    * Documents that are still changing quickly live in Google Drive, in a folder for each workstream. Everyone in the workstream should be able to edit, suggest changes, or comment there.
* The Board meets in a couple of weeks. The group agreed that the Documentation Policy should go to the Board, for approval and visibility.
* Matthew was away this week. His documentation tooling proposal is still to come.

**Reviewed the [IdPy Documentation Policy](https://docs.google.com/document/d/1AgS15-xktdid1GWwDlCmMzbjMmJsenLG40RHX4CBdAs/edit?usp=sharing) document**

* Most notes were taken in the document.
* We went through the policy line by line, using a consent process ("can you live with it?").
* All lines in the policy were reviewed and agreed to, with notes on two items that still require input from others: **C1 - Documentation tooling** and **C3 - theme and branding**.
    * C1 depends on Matthew's tooling proposal.
    * C3: everyone agreed projects should look like they belong to the same family; today, docs hosted on Read the Docs look different from project to project. But we're not aware of existing IdPy branding (for example, a logo) to build on.
* Points settled along the way:
    * **A1 front matter** applies to every project, whether or not it has active maintainers. This is relevant to the two-maintainer rule proposed by the Governance & Fork Review workstream.
    * **B2 spelling:** US English. It is already used in most of the current documentation.
    * **B3 docstring style:** Sphinx style. It is the most widely used across the projects and works best with the proposed tooling.
    * **C4 docs built in CI:** a broken link should make the CI check fail gracefully.
    * Where possible, compliance should be checked with automated tooling rather than checklists.
    * **B1:** new pages are written in MyST Markdown. Some existing reStructuredText pages (for example, in pysaml2) are out of date and should be reviewed and updated soon.
    * **When it takes effect:** as soon as the policy is approved.
* Not yet discussed: the shared resources (glossary, shared theme, CI workflow, docs portal). The front-matter templates will be reviewed at the next meeting.
* The Google Docs version of the document has been set to accept comments from anyone with the link.

# Key Actions
- [ ] **Laura** - reach out to Matthew about his documentation tooling proposal
- [ ] **All** - look for any theming/branding documentation that may exist
- [ ] **Laura** - clean up the Documentation Policy and share it with the broader community (Slack general channel) for feedback
- [ ] **Laura** - bring the Documentation Policy to the Board
- [ ] **Laura** - prepare the [Templates document](../Artifacts/2026-11%20DRAFT%20IdPy%20Documentation%20Templates.md) for collaboration and our next review

