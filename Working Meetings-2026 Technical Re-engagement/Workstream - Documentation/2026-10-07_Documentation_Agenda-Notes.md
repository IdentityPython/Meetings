IdPy Worksteam: DOCUMENTATION
====================================
_2026 October 07_

# Agenda
* Review Actions from last meeting:
  - [X] Experiments - see what we can get from the docs. pysaml2 - Hannah will try it in .md ([client.py](https://github.com/IdentityPython/pysaml2/blob/master/src/saml2/client.py))
    - Example using [Read The Docs](https://rtd-docs-example.readthedocs.io/en/latest/)
  - [X] .md and .rst approaches
* Discuss any blockers or new developments
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**: Rahmah Nanyonga, Hannah Sebuliba, Elliott Elrod, Matthew X. Economou, Laura Paglione

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl_

---

# Notes

Review Actions from last meeting:

- Hannah and Laura looked into generating API docs from the source
  code, starting with
  [`saml2.client`](https://github.com/IdentityPython/pysaml2/blob/master/src/saml2/client.py).
  Hannah created a few Markdown files and posted them to GitHub Pages
  (https://sebulibah.github.io/pysaml2/) for wider review.  She used
  autodoc2 to pull the existing documentation strings from the code
  (NB: currently reStructured Text).  She added docstrings and type
  annotations in `saml2.client_demo`, which adds internal
  cross-references. Matthew also showed his team's
  GitHub Actions library and repository templates (version picker,
  multilingual docs, Markdown guidance) as a possible model.

  Laura created a Read the Docs site
  (https://rtd-docs-example.readthedocs.io/en/latest/) similar to
  Hannah's experiment.  She used Claude to summarize various aspects
  of the code and included documentation.  She also used it to
  prototype reference material for a class. The
  existing docstrings use a consistent style but are written mostly
  for maintainers rather than users.

  This reminded Matthew of similar work Shannon Roddy mentioned.
  LLM-generated documenation needs verification but might provide a
  good starting point for further work. It tends to explain the
  "what" rather than the "why" and "when."

- Matthew suggested [Diátaxis](https://diataxis.fr/) as a
  documentation methodology  (tutorials, how-to guides, reference,
  explanation).  Hannah used Diátaxis in creating her
  outline.  She raised a question about how much of SAML 2.0 we needs
  to recapitulate versus cross-referencing.  She developed a
  documentation gap analysis for pySAML2 (current status, required
  steps, roadmap ideas);
  cf. https://docs.google.com/document/d/1vpJlsZIX1_bzvt071hdsNXEr-Rk8hXoTjL-yF3t5MOQ/.

Discuss any blockers or new developments:

- Laura reminded everyone how expensive documentation is to create.
  That makes maintaining it difficult.  Maybe that goes into the
  contribution guidelines for the overall project?  Some of the
  required documentation updates may need to get caught in code
  review. Matthew suggested the guidelines require documentation
  updates alongside code and test changes.

Determine the tasks we'll accomplish for the next meeting.

- Repositories are inconsistent (e.g., Markdown vs. reStructured Text
  support), so we need to pick one project to start with.  Matthew
  proposed SATOSA: adapt the old getting-started guide into a
  practical how-to guide, which should also surface configuration and
  packaging pain points.

# Key Actions
- [ ] **All** review Hannah's documentation plan / gap analysis (Google Doc above)
- [ ] **All** consider which projects to prioritize for documentation and bring thoughts to the next meeting
- [ ] **All** start an improved SATOSA getting-started how-to guide as the first documentation example
