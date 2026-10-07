IdPy Worksteam: DOCUMENTATION
====================================
_2026 October 07_

# Agenda
* Review updates from Board meeting & other workstreams
* Review Actions from last meeting:
  - [ ] Experiments - see what we can get from the docs. pysaml2 - Hannah will try it in .md ([client.py](https://github.com/IdentityPython/pysaml2/blob/master/src/saml2/client.py))
    - Example using [Read The Docs](https://rtd-docs-example.readthedocs.io/en/latest/)
  - [ ] .md and .rst approaches
  - [ ] What Matthew wants to do.
* Discuss any blockers or new developments
* Determine the tasks we'll accomplish for the next meeting.

# Attendees

**IN ATTENDANCE**:

- Rahmah Nanyonga

- Hannah Sebuliba

- Elliott Elrod

- Matthew X. Economou

- Laura Paglione

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl_

---

# Notes

Review updates from Board meeting & other workstreams:

- N/A

Review Actions from last meeting:

- Hannah and Laura looked into generating API docs from the source
  code, starting with
  [`saml2.client`](https://github.com/IdentityPython/pysaml2/blob/master/src/saml2/client.py).
  Hannah created a few Markdown files and posted them to GitHub Pages
  (https://sebulibah.github.io/pysaml2/) for wider review.  She used
  autodoc2 to pull the existing documentation strings from the code
  (NB: currently reStructured Text).  She added docstrings and type
  annotations in `saml2.client_demo`, which adds internal
  cross-references.

  Laura created a Read the Docs site
  (https://rtd-docs-example.readthedocs.io/en/latest/) similar to
  Hannah's experiment.  She used Claude to summarize various aspects
  of the code and included documentation.  She also used it to
  prototype reference material for a class.

  This reminded Matthew of similar work Shannon Roddy mentioned.
  LLM-generated documenation needs verification but might provide a
  good starting point for further work.

- Matthew suggested [Diátaxis](https://diataxis.fr/) as a
  documentation methodology.  Hannah used Diátaxis in creating her
  outline.  She raised a question about how much of SAML 2.0 we needs
  to recapitulate versus cross-referencing.  She developed a
  documentation gap analysis for pySAML2;
  cf. https://docs.google.com/document/d/1vpJlsZIX1_bzvt071hdsNXEr-Rk8hXoTjL-yF3t5MOQ/.

Discuss any blockers or new developments:

- Laura reminded everyone how expensive documentation is to create.
  That makes maintaining it difficult.  Maybe that goes into the
  contribution guidelines for the overall project?  Some of the
  required documentation updates may need to get caught in code
  review.

Determine the tasks we'll accomplish for the next meeting.

# Key Actions
- [ ] task 1
- [ ] task 2
- [ ] task 3

