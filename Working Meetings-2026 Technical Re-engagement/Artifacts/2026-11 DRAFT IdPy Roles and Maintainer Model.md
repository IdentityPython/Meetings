# DRAFT — IdentityPython roles and maintainer model

_Governance & Fork Review workstream · coordinated by Laura Paglione · draft started 12 Nov 2026_

> [!IMPORTANT]
> **The live version of this draft is now in a [Google Doc](https://docs.google.com/document/d/1Yqsrzqa-1PRybCcFxHbx6FlnxLeAGHen_ddQBWMyW5s/edit?usp=drive_link)** for collaborative editing (workstream participants only). This copy on GitHub is a snapshot from 12 Nov 2026 and may be out of date.

> [!NOTE]
> **This is a starting draft, written in the shape we expect the final version to take.**
> Sections marked ✍️ **Needed** are where the workstream needs your input. The starting positions come from workstream meeting notes, Board decisions, and Alessandro's [gap analysis](IdentityPython_Gap_Analysis_Against_Open_Source_Best_Practices.md). They are proposals, not decisions. A summary of what's needed is [at the end](#whats-needed-to-finish-this-draft).

**What this covers.** Who does what in IdentityPython, how responsibility is shared across projects, and how people take on more of it over time.

---

## Roles

| Role | What they do | Who today |
|---|---|---|
| **Contributor** | Anyone who opens an issue, reviews a pull request, improves docs, or submits code. | Everyone is welcome |
| **Project maintainer** | Technical lead for one project. Guides its direction, reviews and merges changes, triages issues, and makes releases. | See [Project maintainers](#project-maintainers) |
| **Maintainer group** | Maintainers across all projects. A committee of the Board, with authority to add maintainers (reporting changes to the Board). | Alessandro Distaso, Matthew Economou, Ivan Kanakarakis _(transitional)_ |
| **Project architect** | Understands how the projects fit together. Advises on how a change in one project affects the others, and on overall technical direction. | Ivan Kanakarakis _(transitional)_ |
| **Incident manager** | Makes sure security reports are triaged, routed to the right maintainers, and followed through. Keeps reporters informed. | The maintainer group _(transitional)_ |
| **Coordinator** | Keeps the work moving between groups: meetings, notes, follow-ups, and communication. Works at the request of the groups above. | Laura Paglione |
| **Board** | Oversees the project and approves policy. | See [Governance](https://github.com/IdentityPython/Governance) |

All current appointments are **transitional**. During this period, one person can hold several roles, and several people can share one.

---

## Project maintainers

**Every project needs at least two named maintainers to be listed as Active.** A project with fewer than two is listed as **Inactive** until enough maintainers step forward. A project that depends on one person's time is the situation IdentityPython is working to move away from, and users deserve to know which projects have that cover.

This applies to every public, non-archived repository in the IdentityPython organization (18 as of the [3 Nov repository review](2026-11%20IdPy%20GitHub%20Repository%20Review.md)).

| Project | What it is | Maintainers (2 needed) | Status |
|---|---|---|---|
| **Core protocol projects** | | | |
| [pysaml2](https://github.com/IdentityPython/pysaml2) | SAML2 library | ✍️ | ✍️ |
| [SATOSA](https://github.com/IdentityPython/SATOSA) | Proxy translating between SAML2, OIDC and OAuth2 | ✍️ | ✍️ |
| [pyFF](https://github.com/IdentityPython/pyFF) | SAML metadata aggregator | SUNET ✍️ _(names)_ | ✍️ |
| [idpy-oidc](https://github.com/IdentityPython/idpy-oidc) | OIDC and OAuth2 library | ✍️ | ✍️ |
| [JWTConnect-Python-CryptoJWT](https://github.com/IdentityPython/JWTConnect-Python-CryptoJWT) | JOSE (JWT/JWS/JWE/JWK) library | ✍️ | ✍️ |
| [pyop](https://github.com/IdentityPython/pyop) | OpenID Connect Provider library | ✍️ | ✍️ |
| [djangosaml2](https://github.com/IdentityPython/djangosaml2) | Django SAML2 service provider | ✍️ | ✍️ |
| [pyMDOC-CBOR](https://github.com/IdentityPython/pyMDOC-CBOR) | mDOC/CBOR verifier and issuer (EUDI Wallet, mDL) | ✍️ | ✍️ |
| [pyjwkest](https://github.com/IdentityPython/pyjwkest) | Older JWT/JWS/JWE/JWK library | ✍️ | ✍️ |
| [pyXMLSecurity](https://github.com/IdentityPython/pyXMLSecurity) | XML signature library | ✍️ | ✍️ |
| [pyeleven](https://github.com/IdentityPython/pyeleven) | PKCS#11 REST signing proxy | ✍️ | ✍️ |
| **Deployment and development** | | | |
| [satosa-docker](https://github.com/IdentityPython/satosa-docker) | Docker image for SATOSA | ✍️ | ✍️ |
| [satosa-developer](https://github.com/IdentityPython/satosa-developer) | Developer environment for SATOSA | ✍️ | ✍️ |
| [satosa-refarch-aws](https://github.com/IdentityPython/satosa-refarch-aws) | SATOSA reference deployment on AWS | ✍️ | ✍️ |
| [new-session-management](https://github.com/IdentityPython/new-session-management) | Session management design docs | ✍️ | ✍️ |
| **Project administration** | | | |
| [IdentityPython.github.io](https://github.com/IdentityPython/IdentityPython.github.io) | Website (idpy.org) | IdPy Coordinator (Laura Paglione)<br/>IdPy Board Chair | ✍️ |
| [Meetings](https://github.com/IdentityPython/Meetings) | Meeting notes and artifacts | IdPy Coordinator (Laura Paglione)<br/>IdPy Board Chair | ✍️ |
| [Governance](https://github.com/IdentityPython/Governance) | Governance documents | IdPy Coordinator (Laura Paglione)<br/>IdPy Board Chair | ✍️ |

> ✍️ **Needed:**
> * Confirm who maintains each project today, by name. Organizations such as SUNET can back a project, but the maintainers listed should be people.
> * Find a second maintainer for each project, or agree that it will be listed as Inactive.
> * Decide when the two-maintainer rule takes effect, for example at the end of the transition period.
>
> Once confirmed, this table moves to the website and each project's README.

### What maintainers commit to
* Acknowledge new issues and pull requests within ✍️ _[time to agree]_, even if a full review takes longer.
* Keep the project's front-matter documentation and changelog current (see the [Documentation Policy](2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md)).
* Follow the shared [release process](2026-11%20DRAFT%20IdPy%20Release%20Process.md) and [contribution guidelines](2026-11%20DRAFT%20IdPy%20Contribution%20Guidelines.md).
* Tell the maintainer group if they need to step back, so the project isn't left without cover.

> ✍️ **Needed:** agree on a realistic acknowledgement time for volunteers (for example, one week).

---

## Project status

Every project shows one of these labels on its README and on the website, so users know what to expect.

| Status | Meaning |
|---|---|
| **Active** | At least two named maintainers. Issues and pull requests are reviewed, and releases happen. |
| **Inactive** | Fewer than two named maintainers. Issues and pull requests may not get a response. The project becomes Active again when it has two maintainers. Volunteers welcome! |
| **Superseded** | Replaced by another project. The README links to the replacement and explains how to migrate. |
| **Archived** | No longer maintained. Kept read-only for reference. Projects are deprecated and archived, not deleted. |

> ✍️ **Needed:**
> * Decide what an Inactive project still gets. For example, does the maintainer group still triage security reports for it?
> * Decide which projects should be Superseded or Archived rather than Inactive. The [repository review](2026-11%20IdPy%20GitHub%20Repository%20Review.md) suggests satosa-refarch-aws, satosa-developer and new-session-management as archive candidates.

---

## Becoming a maintainer

A suggested path, for discussion:

1. **Contribute.** Issues, reviews, docs, fixes.
2. **Help with triage and review** on a project you know well.
3. **Be invited** by the maintainer group, usually on the suggestion of an existing maintainer. The maintainer group reports the change to the Board.

> ✍️ **Needed:** agree on this path, and what "ready to be a maintainer" looks like in practice (for example, a track record of reviews on that project).

## Stepping back

Maintainers can step back at any time. Please tell the maintainer group, so they can look for someone to take your place. If a project drops below two maintainers, it is listed as Inactive until a replacement is found.

> ✍️ **Needed:** what happens when a maintainer stops responding without stepping back. A starting idea: if a maintainer hasn't responded for ✍️ _[period]_, the maintainer group checks in. If there's no reply, they are no longer counted as a maintainer.

---

## What's needed to finish this draft

- [ ] Confirm the current maintainers of all 18 projects, by name
- [ ] Find a second maintainer for each project, or list it as Inactive
- [ ] Decide when the two-maintainer rule takes effect
- [ ] Decide what an Inactive project still gets (for example, security triage)
- [ ] Decide which projects to mark Superseded or Archived
- [ ] Agree on an acknowledgement time for new issues and pull requests
- [ ] Agree on the path to becoming a maintainer
- [ ] Agree on what happens when a maintainer stops responding

**Where the starting positions came from:** Board decisions reported at the [30 Sep Governance meeting](../Workstream-Governance/2026-09-30_Governance_Agenda-Notes.md); role descriptions from the [16 Sep Governance meeting](../Workstream-Governance/2026-09-16_Governance_Agenda-Notes.md); "deprecate, don't delete" from the [14 Oct Governance meeting](../Workstream-Governance/2026-10-14_Governance_Agenda-Notes.md); the project list and archive candidates from the [GitHub Repository Review](2026-11%20IdPy%20GitHub%20Repository%20Review.md); status labels and contributor ladder suggested in Alessandro's [gap analysis](IdentityPython_Gap_Analysis_Against_Open_Source_Best_Practices.md) (sections 1, 4 and 9).
