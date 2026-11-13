# DRAFT — Bringing work from forks back into IdentityPython

_Governance & Fork Review workstream · coordinated by Laura Paglione · draft started 12 Nov 2026_

> [!NOTE]
> **This is a starting draft, written in the shape we expect the final version to take.**
> Sections marked ✍️ **Needed** are where the workstream needs your input. The starting positions come from Fork Review meeting notes. They are proposals, not decisions. A summary of what's needed is [at the end](#whats-needed-to-finish-this-draft).

**Why this matters.** For several years, fixes and features piled up in forks while the main projects were quiet. Some of that work, including security fixes, should come back so everyone benefits. Many forks also exist for good reasons: local customizations, or a single pull request someone opened. **The goal is not to eliminate forks.** It's to bring back the work that belongs in the main projects.

---

## The approach

### 1. Find the work
* Start from **open pull requests and issues**. They're the clearest signal that someone wants their change upstream.
* Match public forks to open pull requests, so forks with unmerged work stand out.
* Look **beyond the main branch**. Much of the work lives in other branches.

### 2. Prioritize
Work through it in this order:
1. **Security fixes**
2. **Foundational libraries** (such as pysaml2 and idpy-oidc) before the applications built on them (such as SATOSA)
3. **Newer work** before older, since it needs less rework
4. **Contributors we can reach.** People active in the community make the back-and-forth easier.

### 3. Reach out
Contact the author before reworking their changes. They know the context, and they may want to stay involved, which is also how new maintainers emerge.

### 4. Review and merge
Fork work goes through the normal [contribution guidelines](2026-11%20DRAFT%20IdPy%20Contribution%20Guidelines.md): tests, docs, and a maintainer's review.

### 5. Record the outcome
For each fork or pull request, note whether it was **merged**, **declined (with the reason)**, or **needs work**, so the same ground isn't covered twice.

> ✍️ **Needed:** where to track this. One option discussed is a GitHub Project board in the IdentityPython organization.

---

## Open questions

> ✍️ **Needed:**
> * **When do we decline?** For example: changes specific to one deployment, or changes that conflict with the project's direction.
> * **Large diverged branches.** For example, the idpy-oidc variant with OpenID Federation support includes breaking changes. Who decides whether and how to bring in work like that?
> * **Sponsored work.** Some organizations have offered to fund merging specific changes. How should those offers be handled?
> * **Private forks.** How do we invite organizations with private forks to share their changes?

---

## What's needed to finish this draft

- [ ] Where outcomes are tracked
- [ ] Criteria for declining fork work
- [ ] How to decide on large, diverged branches
- [ ] How to handle offers of sponsored work
- [ ] How to approach owners of private forks
- [ ] Publish the current fork and pull request review (Rahmah, Matthew) and link it here

**Where the starting positions came from:** Fork Review meetings on [15 Sep](../Workstream-Fork%20Review/2026-09-15_ForkReview_Agenda-Notes.md) (security first, branches beyond main, private forks), [29 Sep](../Workstream-Fork%20Review/2026-09-29_ForkReview_Agenda-Notes.md) (forks as a sign of popularity, matching forks to pull requests, sponsored work, project board), and [13 Oct](../Workstream-Fork%20Review/2026-10-13_ForkReview_Agenda-Notes.md) (prioritization order, the OpenID Federation fork); sponsored merges also raised at the [16 Sep Governance meeting](../Workstream-Governance/2026-09-16_Governance_Agenda-Notes.md).
