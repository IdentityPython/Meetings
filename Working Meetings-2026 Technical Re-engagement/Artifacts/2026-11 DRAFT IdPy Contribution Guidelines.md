# DRAFT — Contributing to IdentityPython

_Governance & Fork Review workstream · coordinated by Laura Paglione · draft started 12 Nov 2026_

> [!NOTE]
> **This is a starting draft, written in the shape we expect the final version to take.** Once agreed, it would become the default `CONTRIBUTING.md` for every IdentityPython repository. Projects could add their own details on top.
> Sections marked ✍️ **Needed** are where the workstream needs your input. The starting positions come from workstream meeting notes, the draft [Documentation Policy](2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md), and Alessandro's [gap analysis](IdentityPython_Gap_Analysis_Against_Open_Source_Best_Practices.md). They are proposals, not decisions. A summary of what's needed is [at the end](#whats-needed-to-finish-this-draft).

Thank you for helping! IdentityPython is maintained by volunteers, and contributions of every kind are welcome: bug reports, documentation, reviews, and code.

---

## Before you start

* **Check the project's status** at the top of its README. Projects marked _Seeking maintainers_ or _Archived_ may not get a response. See [project status](2026-11%20DRAFT%20IdPy%20Roles%20and%20Maintainer%20Model.md#project-status).
* **Found a security vulnerability?** Don't open a public issue. Follow the [security reporting process](https://github.com/IdentityPython/Governance/blob/master/idpy-incidentresponse.md) instead.
* **Planning a larger change?** Open an issue first to discuss it, so your work fits the project's direction.
* **Have a question?** ✍️ _[where to ask: mailing list / Slack / Discussions, to be set by the [communications strategy](2026-11%20DRAFT%20IdPy%20Communications%20Strategy.md)]_

## Making a pull request

1. **Fork the repository and work on a branch.** Keep your fork's main branch in sync with upstream, and open pull requests from a separate branch rather than from your main branch.
2. **Keep it focused.** One change per pull request. Small pull requests are reviewed faster.
3. **Include tests** for code changes.
4. **Update the docs** if your change affects how people use the project.
5. **Add a changelog entry** for user-facing changes.
6. **Say if you used AI tools** to write code or docs. A person must check facts and examples before merging.
7. **Follow the project's coding style.** ✍️ _[link to the shared tooling baseline, once agreed]_

> ✍️ **Needed:** confirm items 4–6 against the Documentation Policy (rows D1, D2, D4). Decide whether to adopt [Conventional Commits](https://www.conventionalcommits.org/) for commit messages, which was suggested on 30 Sep.

## What happens next

* A maintainer will **acknowledge your pull request** within ✍️ _[time to agree; see the [maintainer model](2026-11%20DRAFT%20IdPy%20Roles%20and%20Maintainer%20Model.md)]_.
* A maintainer **reviews** it, checking that it has tests and docs, fits the project, and doesn't break the projects that depend on it.
* Only a project maintainer **merges**. If your pull request is declined, we'll explain why.
* When there are many open pull requests, maintainers generally prioritize:
  1. **the repository:** foundational libraries (such as pysaml2 and idpy-oidc) before the applications built on them (such as SATOSA)
  2. **age:** newer pull requests first, since they need less rework
  3. **contributor:** people the maintainers can easily follow up with

> ✍️ **Needed:** agree on the review criteria and how many approvals a merge needs. Should docs-only changes get a lighter review (Documentation Policy row D3)?

## Code of conduct

> ✍️ **Needed:** IdentityPython doesn't appear to have a code of conduct today. Choose one (for example, the [Contributor Covenant](https://www.contributor-covenant.org/)) and decide who handles reports.

---

## What's needed to finish this draft

- [ ] Where contributors should ask questions (from the communications strategy)
- [ ] The acknowledgement time for pull requests (from the maintainer model)
- [ ] Review criteria and the number of approvals needed to merge
- [ ] Whether to adopt Conventional Commits
- [ ] A link to the coding style / tooling baseline
- [ ] A code of conduct, and who handles reports
- [ ] Where shared files live: probably an org-level `.github` repository, so every repo inherits them (suggested on 14 Oct)

**Where the starting positions came from:** branch practice from the [15 Sep Fork Review meeting](../Workstream-Fork%20Review/2026-09-15_ForkReview_Agenda-Notes.md); prioritization and review questions from the [13 Oct Fork Review meeting](../Workstream-Fork%20Review/2026-10-13_ForkReview_Agenda-Notes.md); Conventional Commits from the [30 Sep Governance meeting](../Workstream-Governance/2026-09-30_Governance_Agenda-Notes.md); `.github` defaults from the [14 Oct Governance meeting](../Workstream-Governance/2026-10-14_Governance_Agenda-Notes.md); docs, changelog and AI items from the draft Documentation Policy (rows D1–D5); the missing code of conduct and community health files from Alessandro's [gap analysis](IdentityPython_Gap_Analysis_Against_Open_Source_Best_Practices.md) (section 2), still to be confirmed across all repositories.
