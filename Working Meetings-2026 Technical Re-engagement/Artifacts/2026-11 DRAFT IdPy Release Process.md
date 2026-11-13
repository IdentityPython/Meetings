# DRAFT — IdentityPython release process

_Governance & Fork Review workstream · coordinated by Laura Paglione · draft started 12 Nov 2026_

> [!IMPORTANT]
> **The live version of this draft is now in a [Google Doc](https://docs.google.com/document/d/1Luv89uvxAWHjvNjapOc-dSE2ki3ZczviG7HK5nLmO6Y/edit?usp=drive_link)** for collaborative editing (workstream participants only). This copy on GitHub is a snapshot from 12 Nov 2026 and may be out of date.

> [!NOTE]
> **This is a starting draft, written in the shape we expect the final version to take.**
> Sections marked ✍️ **Needed** are where the workstream needs your input. The starting positions come from workstream meeting notes and Alessandro's [gap analysis](IdentityPython_Gap_Analysis_Against_Open_Source_Best_Practices.md). They are proposals, not decisions. A summary of what's needed is [at the end](#whats-needed-to-finish-this-draft).

**The goal:** releasing should be easy enough to do often, shouldn't depend on any one person, and should be automated as much as possible.

---

## Who can release

* Any **maintainer of a project** can release that project.
* Packages are published to PyPI under the [IdentityPython PyPI organization](https://pypi.org/org/idpy/), so publishing rights belong to the project rather than to individuals.

> ✍️ **Needed:** a list of who currently holds PyPI publishing rights for each active project, and which projects still need to move into the PyPI organization.

## How often

> ✍️ **Needed:** agree on a release cadence. Two views were raised on 13 Oct:
> * **Small, frequent releases**, which show the project is actively maintained.
> * **A predictable schedule** (for example, every 3–6 months), which gives contributors a clear sense of when their change will ship.
>
> Either way, **security fixes are released as soon as they're ready**, outside the normal schedule.

## Release checklist

A starting checklist, for each release:

1. **Changelog updated:** newest first, security fixes listed first.
2. **Version number set**, following ✍️ _[versioning scheme, e.g. semantic versioning]_.
3. **Tests pass** in CI.
4. **Tag the release** on GitHub.
5. **GitHub Actions builds and publishes** the package to PyPI, using [trusted publishing](https://docs.pypi.org/trusted-publishers/) so no personal API tokens are needed.
6. **Publish release notes** on GitHub Releases.
7. **Announce it** through the channels in the [communications strategy](2026-11%20DRAFT%20IdPy%20Communications%20Strategy.md).

> ✍️ **Needed:** steps 3–6 aren't automated for most projects today. Package publishing used to be automated, but wasn't restored when it broke. Starting points to build from:
> * pysaml2's [RELEASE.md](https://github.com/IdentityPython/pysaml2/blob/master/RELEASE.md)
> * Matthew's [example CI workflow with PyPI publishing](https://github.com/irtnog/lethbridge/blob/main/.github/workflows/ci.yml)
> * the public-domain (CC0) [ResearchDataCom actions](https://github.com/ResearchDataCom/actions) and [templates](https://github.com/ResearchDataCom/templates)
>
> The shared workflow would come from the [common tooling baseline](README.md#tooling--templates).

## Security releases

Security fixes follow the [Security Incident Response Plan](https://github.com/IdentityPython/Governance/blob/master/idpy-incidentresponse.md). The release notes should say which versions are affected and which version to upgrade to.

> ✍️ **Needed:** say which versions are supported, and whether fixes are ever backported to older release lines or users are expected to upgrade.

---

## What's needed to finish this draft

- [ ] Who holds PyPI publishing rights today, project by project
- [ ] Release cadence
- [ ] Versioning scheme
- [ ] A shared, automated release workflow (with the common tooling baseline)
- [ ] Supported versions and backport policy

**Where the starting positions came from:** goals from the [Governance workstream README](../Workstream-Governance/README.md); current state, PyPI organization, and example workflows from the [14 Oct Governance meeting](../Workstream-Governance/2026-10-14_Governance_Agenda-Notes.md); cadence discussion from the [13 Oct Fork Review meeting](../Workstream-Fork%20Review/2026-10-13_ForkReview_Agenda-Notes.md); changelog format from the draft [Documentation Policy](2026-11%20DRAFT%20IdPy%20Documentation%20Policy%20-%20Discussion%20Guide.md) (row A5); publishing rights and backport policy suggested in Alessandro's [gap analysis](IdentityPython_Gap_Analysis_Against_Open_Source_Best_Practices.md) (sections 6 and 7).
