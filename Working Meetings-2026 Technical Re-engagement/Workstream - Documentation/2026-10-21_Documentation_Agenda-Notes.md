IdPy Worksteam: DOCUMENTATION
====================================
_2026 October 21_

# Agenda
* Review and consent to Key Deliverables, Goals, and Tasks
  - [ ] **All** review Hannah's documentation plan / gap analysis (Google Doc above)
  - [ ] **All** consider which projects to prioritize for documentation and bring thoughts to the next meeting
  - [ ] **All** start an improved SATOSA getting-started how-to guide as the first documentation example
* Consent to high-level schedule through the end of 2026
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**: Laura Paglione, Elliott Elrod, Derrick Ssemanda, Shannon Roddy, Rahmah Nanyonga, Hannah Sebuliba, Matthew Economou

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl_

---

# Notes

* By the next town hall, where we'll review the work streams, we'll
  provide documentation guidance for the entire Identity Python
  project---required types of documentation, documentation tooling,
  address concerns about overall contributor workload.

* Shannon Roddy has worked with LLMs to generate documentation for
  pyFF and will share his experiences with the group.

## Documentation Types

- Derrick: operations manuals, administrator guides, developer
  documentation

- Hannah: [Diátaxis](https://diataxis.fr/), which breaks
  documentation down into tutorials (learning), how-to guides
  (goals), explanations (understanding), and reference (information)

- Elliott: reference material should include artifacts like software
  bills of materials, to facilitate vulnerability management

- Laura: a "getting started" guide, what the product does and common
  use cases (projects currently assume a high degree of experience in
  federated IAM); good documentation doesn't assume deep knowledge

- Examples of good documentation---

  - [pytest](https://docs.pytest.org/), which has quick start guidance
    on the front page

  - [The FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/),
    a formal book with good narrative structure

- Should documentation be the same?  That will require a template
  listing required sections and provide a common theme (look/feel).

## Shannon Roddy's experience documenting pyFF using LLMs

- Shannon kept finding pyFF functionality that was completely
  undocumented, e.g., entity attributes.

- He asked an LLM to look at the source code and document
  functionality in which he was interested.  Ten minutes with
  Antigravity yielded a
  [complete set of docs](https://github.com/sbroddy/pyFFdoc/blob/main/comprehensive_readme.md).
  That yielded introductory material, all the functionality,
  configuring pipelines, and how to run it.

- Shannon used two prompts:

> In this folder is an open source project called pyFF.  The official
> documentation is here: https://pyff.readthedocs.io/en/latest/
>
> I have noticed that the documentation is incomplete for things like
> the setattr pipeline.  I would like you to try to create a
> comprehensive document for running pyFF both as a metadata processor
> and as an MDQ server.  Please store the documentation in markdown,
> and save it in a file titled comprehensive_readme.md in this folder.

  And:

> Please double check that there are no undocumented pipeline features
> in the documentation you created.  If there are currently
> undocumented pipes, please add them to the doc.

- Laura has also been using AI to generate documentation from
  presentations to provide contextual information about how to use a
  specific plugin or feature.  In her experience, LLMs are good at
  following templates.  She tries to write one document to flesh out
  the documentation structure and then lets the LLM follow that.

# Key Actions

- [ ] Matthew: Develop a documentation proposal.

- [ ] Laura: Provide example templates for LLM-generated
      documentation.

- [ ] Shannon: Incorporate Diátaxis into the next set of prompts.
