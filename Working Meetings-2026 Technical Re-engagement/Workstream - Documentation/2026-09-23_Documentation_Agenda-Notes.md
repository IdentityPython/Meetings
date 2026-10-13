IdPy Worksteam: DOCUMENTATION
====================================
_2026 September 23_

# Agenda
* Review and consent to Key Deliverables, Goals, and Tasks
* Consent to high-level schedule through the end of 2026
* Determine the tasks we'll accomplish for the next meeting

# Attendees

**IN ATTENDANCE**: Hannah Sebuliba, Matthew Echonomou, Ramah Nanyonga, Shayna Attkinson, Laura Paglione (notetaker)

**REGRETS**: Derrick Ssemanda, Ivan Kanakarakis, Elliott Elrod, Vlad Mencl

**ASYNC ACTIVITY**: 

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl_

---

# Notes

**Documentation Strategy**

* Documentation embedded in codebase
    * Documentation updates would be reviewed and merged by project maintainers (via pull requests)
    * Expectations: Developers would write technical documentation (for example, for API or function information, perhaps using [docstrings](https://www.geeksforgeeks.org/python/python-docstrings/)), while non-developers could handle other documentation sections (for example, announcements, context info, etc). Non-code content such as announcements would live as Markdown files in the repository's docs folder.
    * Note: context-setting documentation can be more difficult and time-consuming because it requires a different communication lens, and may face resistance from developers who may be more interested/capable of documenting what is more closely tied to the written code.

**Current state / transition**

* Documentation is currently spread across platforms: some projects use Read the Docs, SATOSA uses GitHub Markdown pages, and PySAML2 uses reStructuredText (rendered through Read The Docs). <br/> _(Also see the Workstream [README file](README.md) for links to existing documentation.)_
* Matthew would prefer to move from reStructuredText to Markdown. Rewriting everything would be a large, unfunded effort, so any migration should be staged.
* Possible early win: show that Read the Docs can pull code-generated documentation without disrupting existing setups.
* A first look at PySAML2 `client.py` showed mostly configuration directives/options rather than full docstrings; much user documentation is currently written by hand rather than generated from code.

**A goal - agile PM**

* Vision: documentation with immediate usability; versions; announcements, etc
* How it is implemented - an example, https://docs.rdctdev.us/actions/v4.0.0/en/index.html
    * Building documentation from the [Git repository](https://github.com/ResearchDataCom/actions/tree/main/docs)
    * automate the publication process by GitHub actions

**Tools to consider for documentation**

* Swagger (used in other contexts)
* [Python DocStrings](https://peps.python.org/pep-0257/) (interpreted through automation to produce documentation)

## Key Actions

Conduct Experiments: 

- [ ] **Hannah** - see what we can get from the docs: try the Markdown (.md) approach on PySAML2 [client.py](https://github.com/IdentityPython/pysaml2/blob/master/src/saml2/client.py) (~2 weeks)
- [ ] **Laura** - try the reStructuredText (.rst) / Sphinx approach on the same file, for comparison with the .md approach

