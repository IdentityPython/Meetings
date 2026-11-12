# DRAFT — Setting documentation policy across IdentityPython: a discussion guide

_For the Documentation workstream · facilitated by Laura Paglione · draft 4 Nov 2026_

> [!NOTE]
> This document has been transferred to a temporary document for collaborative editing. This document will be replaced by the policy document when finalized. 
>
> Members of this workstream may access the collaboration draft [here](https://docs.google.com/document/d/1AgS15-xktdid1GWwDlCmMzbjMmJsenLG40RHX4CBdAs/edit?usp=sharing). 

**What we're deciding.** For each aspect of documentation (what content exists, how it's written, what tools build it, what contributors must do in a pull request), the group decides two things:

1. **How strongly** IdPy asks for it.
2. **Who decides the details:** the IdPy community as a whole, or each project.

**What we'll produce.** A one-page *documentation policy recommendation*. Under our charter, governance of documentation belongs to the Governance workstream; this workstream recommends. So the output goes to the Governance workstream and the maintainer group for consent, and to the Board if it needs to become a formal regulation.

---

## 1. Shared vocabulary

Every policy item gets a value on four dimensions.

**A. How strongly.** The terms follow the RFC 2119 style this group already uses.

| Level | Meaning in practice |
|---|---|
| **Required** (MUST) | A pull request or release can be held back if it's missing. Only for things that are cheap, checkable, and that users really need |
| **Recommended** (SHOULD) | The default. Projects can deviate with a stated reason |
| **Optional** (MAY) | A known good practice; projects choose |
| **Not addressed** | Deliberately left out of the policy for now |

**B. Who decides the details**

| Level | Meaning | Example |
|---|---|---|
| **Centralized** | One IdPy-wide answer, maintained in one place | One `SECURITY.md` in the org `.github` repo, inherited by every repo |
| **Federated** | IdPy sets the baseline; each project chooses how to meet it | "Every project has a Getting started page," written however suits the project |
| **Decentralized** | Each project decides | Choice of example framework in tutorials |

**C. Applies to:** all projects · services (SATOSA, pyFF, satosa-docker) · libraries · only projects with active maintainers.

**D. How it's enforced:** automated check in CI · PR review / checklist · release checklist · trust (no enforcement).

**Rule of thumb to propose:** don't make something **Required** unless it can be enforced by automation or a checklist item, and a volunteer maintainer can meet it in minutes, not days.

---

## 2. Principles to agree first (about 10 minutes)

Proposed as a starting point. Ask: *can everyone live with these?*

1. **Readers first.** Consistency matters most where readers notice it: the front matter (what this is, how to install it, how to start, how to report a vulnerability). Below that surface, projects keep freedom.
2. **Fit volunteer capacity.** Every requirement has an owner and a realistic cost. When in doubt, recommend rather than require.
3. **New work first, no big rewrites.** Rules apply to new and changed docs. Existing docs move over gradually, starting with the projects that have active maintainers.
4. **Automate what we require.** If we can't check it, it's a recommendation.
5. **Revisit in six months.** This is a starting policy, reviewed after the first release cycle under it.

---

## 3. The policy questions (sorting exercise)

**How to run it:**
- **Quick pass first, 1–2 minutes per row.** Accept the starting position, adjust it, or mark the row "discuss."
- **Then spend the remaining time on the rows marked "discuss."**
- The starting positions are deliberately concrete so the group has something to react to; they're not decisions.

### A. Content: what documentation must exist

| # | Question | Starting position | How strongly | Who decides | Applies to | Enforced by |
|---|---|---|---|---|---|---|
| A1 | Must every project have the four front-matter pages (overview, getting started, security & versions, release notes)? | Yes, using the shared templates | Required | Federated | Projects with active maintainers | Release checklist |
| A2 | Must services have a configuration reference and core how-tos? | Yes | Recommended → Required in 2027 | Federated | Services | Review |
| A3 | Should docs follow the Diátaxis structure (tutorial / how-to / reference / explanation)? | Yes, as the organizing model | Recommended | Federated | All | Review |
| A4 | Must public APIs have docstrings? | Yes for new or changed public APIs | Required | Federated (style set centrally, see B3) | Libraries | CI lint + review |
| A5 | Must each project keep a changelog? | Yes, newest first, security items first | Required | Centralized format | All | Release checklist |
| A6 | Should each project list the standards it implements and its key dependencies? | Yes, in the overview | Recommended | Federated | Protocol libraries | Review |

### B. Style: how documentation is written

| # | Question | Starting position | How strongly | Who decides | Applies to | Enforced by |
|---|---|---|---|---|---|---|
| B1 | Markup format: Markdown (MyST) or reStructuredText? | MyST Markdown for new pages; existing rST can stay until it's rewritten | Recommended | Centralized | All | Review |
| B2 | Language and spelling | English; pick US or UK and use it consistently | Recommended | Centralized | All | Trust |
| B3 | Docstring style (e.g. Google vs NumPy vs Sphinx field lists) | Pick one IdPy-wide | Recommended | Centralized | Libraries | CI lint |
| B4 | Shared glossary of terms (IdP, SP, metadata, frontend/backend…) | One IdPy glossary, linked from every project | Recommended | Centralized | All | Trust |
| B5 | Tone and audience | Write for a newcomer; link concepts rather than assume them | Recommended | Centralized guidance | All | Review |

### C. Tooling: what builds and hosts the docs

_Matthew's tooling proposal is the input here._

| # | Question | Starting position | How strongly | Who decides | Applies to | Enforced by |
|---|---|---|---|---|---|---|
| C1 | Generator (Sphinx + MyST + autodoc, per proposal) | Standard toolchain for new or migrated docs | Recommended | Centralized | All | Trust |
| C2 | Hosting: GitHub Pages vs Read the Docs | GitHub Pages under the IdPy org; migrate when a project rebuilds its docs | Recommended | Centralized | All | Trust |
| C3 | Shared theme / look | One shared theme and branding | Recommended | Centralized | All | Trust |
| C4 | Docs built in CI on every PR | Yes: the build must pass; broken links get flagged | Required once the toolchain is adopted | Centralized (shared workflow) | Projects on the toolchain | CI |
| C5 | Versioned docs (one version per release) | For projects with several supported release lines | Optional | Federated | Libraries / services | Trust |
| C6 | One IdPy-wide docs portal linking every project | Yes: idpy.org links each project's docs | Recommended | Centralized | All | Trust |

### D. Contribution rules: what a pull request must include

| # | Question | Starting position | How strongly | Who decides | Applies to | Enforced by |
|---|---|---|---|---|---|---|
| D1 | Must a PR that changes user-facing behaviour update the docs? | Yes ("docs, tests and code together") | Required | Centralized rule | All | PR template checkbox + review |
| D2 | Must a PR add a changelog entry? | Yes for user-facing changes | Required | Centralized format | All | PR template / CI |
| D3 | Do docs-only PRs need the same review as code? | One maintainer approval; lighter than code review | Recommended | Federated | All | Branch rules |
| D4 | Must AI-generated docs be disclosed and human-reviewed? | Yes: note it in the PR, and a human checks facts and examples | Required | Centralized rule | All | PR template |
| D5 | Shared PR / issue templates across repos | Yes, from the org `.github` repo | Recommended | Centralized | All | Inherited |

### E. Ownership and upkeep

| # | Question | Starting position | How strongly | Who decides | Applies to | Enforced by |
|---|---|---|---|---|---|---|
| E1 | Who owns each project's docs? | That project's maintainers; non-developers welcome for non-code pages | Required (named owner) | Federated | All | Overview page |
| E2 | Who owns the shared pieces (templates, glossary, theme, portal)? | The Documentation workstream now; a named docs maintainer later | Required | Centralized | Shared pieces | Governance |
| E3 | Periodic review for stale docs | Check the front matter at every minor release | Recommended | Federated | All | Release checklist |
| E4 | What about projects with no maintainer? | Out of scope; the overview page says "seeking maintainers" | Required (status shown) | Centralized | Unmaintained | Trust |

---

## 4. Questions to test contested items

When a row stalls, ask:

- **Cost:** who does the work, and how many hours? Is that realistic for volunteers?
- **Benefit:** which readers gain, and how much? Would a newcomer notice?
- **Enforcement:** how would we know if a project isn't doing it? If we can't tell, can it really be Required?
- **Reversibility:** how hard would it be to undo in six months?
- **Variety:** does the difference between projects (rST vs Markdown, service vs library) justify a federated answer?
- **Fallback:** would "Recommended now, Required in 2027" settle it?

---

## 5. Suggested session plan

| Session | Date (from the workstream schedule) | Goal | Output |
|---|-------------------------------------|---|---|
| 1 | 4 Nov ([MEETING NOTES](../Workstream%20-%20Documentation/2026-11-04_Documentation_Agenda-Notes.md))        | Agree the vocabulary and principles (sections 1–2); quick pass through tables A and D | Rows marked agreed / adjusted / discuss |
| 2 | 18 Nov                              | Quick pass through B, C, E with Matthew's tooling proposal; deep dive on "discuss" rows | Full grid filled in |
| — | Between sessions                    | Laura drafts the one-page recommendation from the grid; asynchronous comments | Draft policy |
| 3 | 2 Dec                               | Consent round on the draft ("can you live with it?"); agree what goes to the Governance workstream and the town hall | Recommendation sent on |

**Decision method:** consent, not unanimity. An item passes unless someone has a reasoned objection that it would harm the project. Objections are recorded and resolved, or the item drops to Recommended.

---

## 6. What the final policy looks like (target shape)

A one-page document with three short lists, plus links to the templates, toolchain and PR template that put it into practice:

- **Every IdentityPython project must…** (only the Required rows)
- **IdentityPython projects should…** (Recommended)
- **Shared resources IdPy provides…** (the Centralized items: templates, `SECURITY.md`, theme, glossary, PR template, CI workflow, portal)

_Drafted with help from Claude. The starting positions are proposals for the group to react to, not recommendations from the maintainers._
