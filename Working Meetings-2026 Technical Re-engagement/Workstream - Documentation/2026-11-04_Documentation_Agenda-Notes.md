IdPy Worksteam: WORKSTREAM - DOCUMENTATION
====================================
_2026 November 04_

[comment --- File naming convention: yyyy-mm-dd_wprkstreamName_Agenda-notes.md --- use "Documentation, "ForkReview", or "Governance" in place of "wprkstreamName" in the file name]: #

# Agenda
* Check-in
* Consider components for an IdPy Documentation Policy
  * Review the content of the [DRAFT IdPy Documentation Policy - Discussion Guide](https://github.com/IdentityPython/Meetings/blob/master/Working%20Meetings-2026%20Technical%20Re-engagement/Workstream%20-%20Documentation/2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md)
* Determine the tasks we'll accomplish for the next meeting & make assignments

# Attendees

**IN ATTENDANCE**: Hannah, Rahmah, Elliott, Derrick, Laura

**REGRETS**:

**ASYNC ACTIVITY**:

**INVITED**: _Laura Paglione, Shayna Atkinson, Hannah Sebuliba, Nanyonga Rahmah, Ivan Kanakarakis, Derrick Ssemanda, Matthew Economou, Elliott Elrod, Vlad Mencl_

---

# Notes

* The group began reviewing the [DRAFT IdPy Documentation Policy - Discussion Guide](https://github.com/IdentityPython/Meetings/blob/master/Working%20Meetings-2026%20Technical%20Re-engagement/Workstream%20-%20Documentation/2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md).
    * The guide is a framework for deciding, for each aspect of documentation, how strongly IdPy asks for it and who decides the details.
    * This workstream will produce a recommendation for the Governance workstream and maintainer group.
* For context, the IdentityPython org has 33 repositories: 6 private security-related, 6 archived, and 18 active (12 updated in 2026).
* We should review the existing repos and look at the documentation guidelines in each, to see where they are similar and where they differ.

**Section 1. Shared vocabulary**

* *How strongly* (Required / Recommended / Optional, following RFC 2119 MUST / SHOULD / MAY): agreed to use these terms.
* *Who decides the details* (Centralized / Federated / Decentralized):
    * The policy as a whole wouldn't be any one of these. Each item would be labelled according to which of these it follows.
    * The result is a hybrid model. Some items are set centrally for all of IdPy, some set a baseline that each project meets in its own way, and some are left to each project.
* *Applies to*: fully decentralized doesn't really work. The policy should cut across all projects.

**Section 2. Principles**

* Agreed in general to the proposed principles:
    * readers first
    * fit volunteer capacity
    * new work first, no big rewrites of existing docs
    * automate what we require
    * revisit in six months

**Section 3. The policy questions**

A. Content: what documentation must exist 

* *What is affected?* (e.g., changelog format) would apply to new and changed documentation. Existing docs would move over gradually rather than being rewritten all at once.

B. Style: how documentation is written

* B1 (Markdown/MyST vs reStructuredText): when reviewing existing documentation, also note which markup format each project uses.
* B2 (spelling): we should pick one, US or UK English, rather than allowing either. US English was suggested.
* B4: a shared glossary of terms is a good thing.

C. Tooling: what builds and hosts the docs

* C2: like the proposed arrangement of hosting docs on GitHub Pages under the IdPy org.
* C6: a single IdPy docs portal linking to every project would be great. Today you have to search for each project's docs separately.

D. Contribution rules: what a pull request must include
* D - all makes sense

E. Ownership and upkeep

* E1 (ownership): maintainers own each project's docs, but developers should also be involved in reviewing non-code documentation, for consistency and accuracy.
* E2 (shared pieces):
    * Where should shared pieces live, so that a change in one place applies everywhere?
    * Hannah's example: some repos (e.g., SATOSA) have identical issue templates that were created separately in each repo, so they can drift apart.
    * Org-level templates (in the org's `.github` repository) would keep a single copy.

# Key Actions
- [ ] **All** look at existing documentation for how it fits into these guidelines (including markup format)
- [ ] **All** look at PR & issue templates and summarize how other projects are doing their documentation
    - **Laura** to create a place to capture this information and invite others to contribute to it
    - No volunteers to review documentation over the next two weeks. This will go on the agenda for the next meeting.
- [ ] **Anyone not on the call** review the discussion guide
- [ ] **Laura** send the discussion guide to Matthew for his input

