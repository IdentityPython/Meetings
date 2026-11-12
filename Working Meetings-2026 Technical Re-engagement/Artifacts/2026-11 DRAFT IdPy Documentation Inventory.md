# DRAFT — IdentityPython documentation inventory

_For the Documentation workstream · coordinated by Laura Paglione · first pass 5 Nov 2026, by Claude from the repositories themselves; to be verified by workstream members_

Covers the **18 public, non-archived repositories** in the IdentityPython GitHub organization, measured against the policy questions (A–E) in the *Documentation Policy Discussion Guide*. The blank template is in *IdPy Documentation Inventory - Template*.

## How this was produced, and how to verify it

**Sources (primary only).** Each repo's default branch was cloned on 5 Nov 2026 with full history and tags. Wikis were cloned where they exist (SATOSA, pyFF, pysaml2). Every finding comes from:
- files in the repo, cited as `repo:path`
- `git log` / `git tag` output (dates, commit counts, committers)
- a script that parsed the Python source (docstring and type-hint counts).

Nothing here comes from memory or from other summaries.

**Not checked (out of reach from here):**
- The hosted documentation sites (Read the Docs, pyff.io, Docker Hub). Only the documentation *source* in each repo was read, so whether a hosted site is built and current is unverified.
- GitHub Releases pages and repo settings, which need the GitHub API. Release notes kept only on GitHub Releases would not show up here.
- Non-default branches. idpy-oidc and djangosaml2 say development happens on a `develop`/`dev` branch, so newer docs may exist there.

**Labels used throughout:**
- **No label** = a fact read directly from the cited source.
- **[Inference]** = a conclusion drawn from facts; the basis is given in brackets. Please check these first.
- **[Rating]** = a 0–3 judgement on the template's scale, with the reason. All ratings are auto (not yet reviewed by a person).

**Measurement rules:**
- *Commits (12 mo)* = non-merge commits to the default branch from 5 Nov 2025 to 5 Nov 2026. Committers excludes bots (dependabot, snyk-bot, publiccode-pr-bot).
- *Maintainer evidence:*
  - **active** = a release tag in the last 6 months, or 5+ commits in 12 months
  - **occasional** = some activity in 12 months, but neither of the above
  - **none** = no commits in 12 months
- *Docstring % / typed %:* the share of public functions and classes (names not starting with `_`, excluding tests, docs and examples) that have a docstring / that have any type annotation.
- *Spelling* counts US vs UK forms of 26 word pairs (behavior/behaviour, organization/organisation, authorize/authorise, serialize/serialise …) in README and docs files.
- *Front matter (A1)* = the sum of four 0–3 ratings: overview, getting started, security & versions, changelog. Maximum 12.

---

## Key findings across projects

1. **Security information is the most common gap.**
   - Only pysaml2 has a `SECURITY.md` (`pysaml2:SECURITY.md`): how to report, what happens next, and supported versions. No other repo explains how to report a vulnerability.
   - The website's security page (`IdentityPython.github.io:security.md`, last changed 2022-07-01) names an older set of libraries: pyXMLSecurity, pyeleven, oidcendpoint, JWT-Connect-Python.
   - [Inference: one org-level `SECURITY.md` in a `.github` repo would show on every repo at once. That's based on GitHub's documented default-files behavior, and no `.github` repo exists in the org today (it's not in the 33-repo list).]
2. **Documentation trails the code.** Last change to the docs folder vs last code change:

   | Repo | Docs last changed | Code last changed |
   |---|---|---|
   | SATOSA | 2024-06-11 | 2026-09-30 |
   | idpy-oidc | 2024-05-24 | 2026-10-02 |
   | CryptoJWT | 2026-03-16 (but most pages 2018–2021) | 2026-03-23 |
   | pyjwkest | 2016-11-10 | 2025-10-04 |

   Install instructions are out of date in several places:
   - pysaml2's install guide says development "has been done using 2.7" (`pysaml2:docs/install.rst`, 2020).
   - pyFF's install guide expects Python 3.6 and installs pyXMLSecurity (`pyFF:docs/usage/install.rst` lines 59–92), but pyFF 3.0 requires Python ≥3.11 and pybergshamra (`pyFF:pyproject.toml`).
   - pyjwkest says Python 2.7/3.4 and pycrypto (`pyjwkest:README.rst`).
3. **Changelogs are mixed.**
   - **Current:** pysaml2, SATOSA, pyop (`CHANGELOG.md`, latest entries in 2026) and pyFF (`NEWS.txt`, written oldest-first).
   - **Missing or stale:**
     - idpy-oidc: `CHANGELOG.md` says only "No change log folks. Sorry."
     - CryptoJWT: no changelog file.
     - djangosaml2: `CHANGES` stops at v1.2.2 (2021-05-27), while the latest tag is v1.12.0-1 (2026-02-17).
     - pyMDOC-CBOR: `CHANGELOG.md` is an empty file (0 bytes).
   - [Inference: djangosaml2 and idpy-oidc may keep release notes on GitHub Releases instead. Based on `.github/release-drafter.yml` in both repos; unverified.]
4. **Docs version numbers are typed in by hand and out of date.**

   | Repo | Version in Sphinx `conf.py` | Latest release tag |
   |---|---|---|
   | CryptoJWT | "0.4" | v1.11.0 |
   | idpy-oidc | '1.0.0' | v4.5.0 |
   | pyjwkest | '0.7' | v1.4.4 |
   | djangosaml2 | '0.2.4' | v1.12.0-1 |

   Only pysaml2 reads the version from the package (`str(saml2.version.version)`).
   idpy-oidc's own version numbers also disagree: `pyproject.toml` says 3.0.0, `src/idpyoidc/__init__.py` says 5.0.0, and the latest tag is v4.5.0 (2024-09-15).
5. **No repository builds its docs in CI.** No GitHub Actions workflow in any repo runs Sphinx or a docs build. Read the Docs config files exist only in pyFF, djangosaml2 and new-session-management. [Inference: pysaml2, idpy-oidc and CryptoJWT link Read the Docs sites from their READMEs without a config file, so those builds are set up in Read the Docs' web interface or use its defaults. Unverified.]
6. **Templates are copied by hand, and only one asks for docs.**
   - The same `issue_template.md` (identical checksum) sits at the root of SATOSA, pyFF, pyXMLSecurity and pyeleven. The same `pull_request_template.md` is in SATOSA, pyFF and pyXMLSecurity.
   - None of those PR templates mention documentation or the changelog.
   - pysaml2's own PR template (`pysaml2:.github/pull_request_template.md`) already asks "Updated documentation" and "Updated CHANGELOG.md". That's policy items D1/D2, already in practice in one repo.
7. **Two contributing guides belong to another organization.** `idpy-oidc:CONTRIBUTING.md` and `CryptoJWT:CONTRIBUTING.md` are titled "Contributing to JwtConnect-Python". They require the OpenID Foundation contributor agreements and point to `github.com/openid/JWTConnect-Python-OidcMsg` issues. [Inference: carried over from the OpenID Foundation era of these libraries. A governance question, not just a docs one.]
8. **The docs are split between two markup formats.**
   - **reStructuredText / Sphinx:** pysaml2, pyFF, idpy-oidc, CryptoJWT, pyjwkest, new-session-management.
   - **Markdown:** SATOSA, pyMDOC-CBOR, pyop (README only), satosa-docker.
   - **Both:** djangosaml2, via `recommonmark` in `docs/source/conf.py`.
9. **Docstring style is already uniform.** Every library that documents parameters uses Sphinx field lists (`:param`). Google-style `Args:` appears only 1–6 times per repo. So policy item B3 may simply confirm current practice.
   - **Coverage varies:** from 4% (pyeleven) to 74% (pyMDOC-CBOR).
   - **Type hints are rare:** 0–7% in most libraries. The exceptions are pyMDOC-CBOR (66%), pyFF (33%) and djangosaml2 (26%).
10. **Everything is in English, mostly US spelling.** UK forms do appear:

    | Repo | US forms | UK forms | Main UK form |
    |---|---|---|---|
    | idpy-oidc | 116 | 19 | "behaviour" ×19 |
    | SATOSA | 10 | 6 | |
    | djangosaml2 | 7 | 2 | |

    So the 4 Nov group preference for US English would mean small edits, not rewrites.
11. **pyFF 3.0 dropped pyXMLSecurity.** `pyFF:pyproject.toml` at tag 3.0.0 depends on `pybergshamra>=0.11.0`; at tag 2.1.7 it depended on `pyxmlsecurity>=1.0.0`. The change was the commit "feat: migrate the XML/crypto backend" (2026-09-15).
    - pyFF's own docs still mention pyXMLSecurity (`HACKING.txt` line 7, `docs/usage/install.rst` line 92).
    - [Inference: the IdPy dependency map, and the earlier repo review's "keep pyXMLSecurity because pyFF needs it", are out of date from pyFF 3.0 on.]
12. **Several READMEs carry dead badges.** Travis CI build badges appear in pyFF, pyop, pyjwkest, pyeleven and pyXMLSecurity. [Inference: travis-ci.org stopped serving open-source builds in 2021, so these badges are broken. General knowledge, not checked from here.]
13. **Wikis hold docs outside the versioned repos.**
    - SATOSA: 6 pages, last edited 2022-08-31, including `satosa-core-development-guidelines.md`.
    - pyFF: 10 pages, last edited 2024-01-08. Its `KAMPANAT-THUMWONG.md` contains only `* ` [Inference: probably a stray or spam page].
    - pysaml2: a single "Welcome" stub.

---

## Part 1 — Summary

_All rows auto; Reviewer column open. Docs toolchain and hosting are as declared in the repo._

| Repo | Type | Last commit | Commits (12 mo) / committers | Maintainer evidence | Markup | Docs toolchain | Hosted at (as linked in repo) | Front matter (A1, 0–12) | Changelog (A5) | Security page | Contributing guide | PR / issue templates | Docstring % / typed % | Language / spelling (US:UK) | Style (B5, 0–3) | Effort to A1 | Reviewer | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| pysaml2 | library | 2026-09-29 | 4 / 3 | active (tag v7.5.5, 2026-09-17) | rST docs; MD README | Sphinx (alabaster) | pysaml2.readthedocs.io | 9 | yes (2026-09-17) | ✓ `SECURITY.md` | ✓ | ✓ own (asks for docs + changelog) | 43 / 0 | English / 16:1 | 1 | M | | auto |
| SATOSA | service | 2026-09-30 | 19 / 3 | active (v8.6.0, 2026-09-28) | MD | none (GitHub-rendered MD) | GitHub repo `doc/` | 7 | yes (2026-09-28) | — | — | shared copy (no docs item) | 70 / 2 | English / 10:6 | 2 | M | | auto |
| pyFF | service | 2026-11-03 | 88 / 5 | active (3.0.0, 2026-10-26) | rST | Sphinx (rtd theme) + `.readthedocs.yml` | pyff.readthedocs.org; pyff.io | 6 | yes, `NEWS.txt` oldest-first (2026-10-26) | — | `HACKING.txt` (outdated) | shared copy | 26 / 33 | English / 5:1 | 2 | M | | auto |
| idpy-oidc | library | 2026-10-02 | 1 / 1 | occasional (last tag v4.5.0, 2024-09-15) | rST | Sphinx (classic) | idpy-oidc.readthedocs.io | 3 | placeholder only | — | OpenID Foundation text | — | 29 / 18 | English / 116:19 | 2 | L | | auto |
| pyop | library | 2026-09-28 | 8 / 4 | active (v3.5.0, 2026-09-28) | MD (README only) | none | GitHub README | 7 | yes (2026-09-28) | — | — | — | 38 / 0 | English / 9:0 | 2 | M | | auto |
| JWTConnect-Python-CryptoJWT | library | 2026-03-23 | 22 / 1 | active (v1.11.0, 2026-03-24) | rST | Sphinx (default) | cryptojwt.readthedocs.io | 2 | none in repo | — | OpenID Foundation text | — (`CODEOWNERS` → @IdentityPython/oidc) | 61 / 7 | English / 5:0 | 2 | M | | auto |
| djangosaml2 | library (Django app) | 2026-02-17 | 1 / 1 | occasional (v1.12.0-1, 2026-02-17) | rST + MD | Sphinx (rtd theme, recommonmark) + `.readthedocs.yml` | djangosaml2.readthedocs.io | 6 | stale (`CHANGES` ends 2021) | secure-config page only | in README | — | 41 / 26 | English / 7:2 | 2 | M | | auto |
| pyMDOC-CBOR | library | 2026-07-21 | 17 / 3 | active (1.4.0, 2026-07-21) | MD | none | GitHub repo | 7 | empty file | dependency-risk page only | — | — | 74 / 66 | English / 11:2 | 3 | S | | auto |
| satosa-docker | packaging | 2026-10-01 | 2 / 1 | occasional (no tags) | MD (README only) | n/a (image docs live in docker-library/docs) | Docker Hub | 3 | — | — | in README | — | n/a | English / 0:0 | 2 | S | | auto |
| pyjwkest | library | 2025-10-04 | 0 | none (README: "NOT actively maintained") | rST | Sphinx (classic) | none linked | 3 | yes (one entry, 2025-10-04) | — | — | — | 33 / 0 | English / 17:0 | 1 | S (status only) | | auto |
| pyeleven | service (small) | 2025-07-10 | 0 | none | MD (README only) | none | none | 2 | — | — | — | shared copy (PR template differs) | 4 / 0 | English / 0:0 | 1 | S (status only) | | auto |
| pyXMLSecurity | library | 2023-10-13 | 0 | none | rST (README only) | none | none | 4 | yes, `NEWS.txt` to 1.0.0 (2023) | — | `HACKING.txt` | shared copy | 35 / 0 | English / 0:0 | 1 | S (status only) | | auto |
| satosa-developer | packaging | 2023-10-07 | 0 | none | MD (README only) | none | none | 2 | — | — | — | — | n/a | English / 0:0 | 1 | S (status / archive) | | auto |
| satosa-refarch-aws | packaging | 2022-12-10 | 0 | none | MD (README only) | none | none | 4 | — | — | in README | — | n/a | English / 1:0 | 2 | S (status / archive) | | auto |
| new-session-management | docs only | 2020-12-10 | 0 | none | rST | Sphinx (alabaster) + `.readthedocs.yml` | not linked | 1 | — | — | — | — | n/a | English / 42:1 | 2 | S (status / archive) | | auto |
| IdentityPython.github.io | project admin (website) | 2025-09-19 | 0 | none | MD (Jekyll) | Jekyll | idpy.org | n/a | — | ✓ site page (2022) + `.well-known/security.txt` | `contribute.md` (2023) | — | n/a | English / 0:0 | 1 | S | | auto |
| Meetings | project admin | 2026-11-05 | 31 / 2 | active | MD | none | GitHub repo | n/a | — | — | — | — | n/a | English | n/a | n/a | | auto |
| Governance | project admin | 2021-04-09 | 0 | none | MD | none | GitHub repo | n/a | — | (holds the 2021 incident response plan) | — | — | n/a | English | 1 | S | | auto |

**Effort basis.** [Inference: these are sizes from the gap lists in Part 2, not timed estimates.]
- **S:** reorganizing, or a status notice.
- **M:** one new page, e.g. getting started or security, plus fixing stale facts.
- **L:** several new pages plus reconstructing history (idpy-oidc's changelog) and fixing version metadata.
- **"Status only":** where there's no maintainer, the realistic minimum is a clear status notice, as pyjwkest already has, and an archive decision. That follows principle "fit volunteer capacity" and policy item E4.

---

## Part 2 — Detail sheets

_Order: services and core libraries first, then the other libraries, packaging, and project-admin repos._

### pysaml2

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (SAML SP/IdP toolkit) | README |
| Maintenance | Last commit 2026-09-29; 4 commits from 3 people in 12 months (Ivan Kanakarakis, Okke Formsma, Samuel Raphael); latest tag v7.5.5 (2026-09-17) → **active** | `git log`, `git tag` |
| Where docs live | README; `docs/` (9 files, 8,341 words); hosted at pysaml2.readthedocs.io (linked); wiki is a one-line stub | `README.md`; wiki `Home.md` |
| Version documented | Synced to the package: `docs/conf.py` uses `str(saml2.version.version)` | `docs/conf.py` |
| **A1a Overview** | **[Rating 2]** One-paragraph description, links to docs/security/contributing/PyPI, and a full list of the SAML specifications implemented. No use cases, status or maintainers | `README.md` |
| **A1b Getting started** | **[Rating 1]** README install is current (`pip install`, xmlsec1 per OS). The docs install guide is out of date: "development has been done using 2.7", easy_install, rhel/centos 7 (last changed 2020-01-15). The SP example relies on repoze.who (2019-11-03). No end-to-end quickstart | `docs/install.rst`, `docs/examples/sp.rst` |
| **A1c Security & versions** | **[Rating 3]** `SECURITY.md`: reporting address, advisory/CVE process, "security fixes are not backported", supported version = latest only | `SECURITY.md` |
| **A1d Changelog** | **[Rating 3]** `CHANGELOG.md`, newest first, latest v7.5.5 (2026-09-17) | `CHANGELOG.md` |
| A2 Config reference | Comprehensive alphabetical directive list (4,797 words, updated 2025-10-07) | `docs/howto/config.rst` |
| A3 Diátaxis coverage | Tutorial ✗ (examples are partial); how-to ✓ (`howto/`); reference ✓ for config, ✗ for API (no autodoc directives in `docs/`); explanation partial ("About" paragraphs) | file list; `grep automodule` = 0 files |
| A4 Docstrings | 43% of 3,486 public defs; 0% typed | AST scan |
| A6 Standards / dependencies | ✓ Spec list in README; xmlsec1 dependency explained | `README.md` |
| B1 Markup | rST (8 docs files) + MD (README, CHANGELOG, `docs/FIXUP_COMMITS.md`) | file list |
| B2 Language / spelling | English; US 16 : UK 1 | spelling scan |
| B3 Docstring style | Sphinx `:param` (894 uses) | code scan |
| B5 Tone / clarity | **[Rating 1]** Conversational and dated in places ("I'm sorry to tell you this… This is middleware stuff!"). The index and howto/index repeat the same text. Config reference is clear | `docs/index.rst`, `docs/howto/index.rst` |
| C Tooling | Sphinx (alabaster); no `.readthedocs.yml` in repo; no docs build in CI (no GitHub workflows; `.travis.yml` present) | file list |
| D Contribution rules | PR template asks "Updated documentation" and "Updated CHANGELOG.md"; `CONTRIBUTING.md` has an "Improving Documentation" section; `DEVELOPERS.md` and `RELEASE.md` present | `.github/pull_request_template.md`, `CONTRIBUTING.md` |
| E Upkeep | Docs last changed 2025-10-07; code 2026-09-29 | `git log` |
| Biggest gaps | (1) Modern getting-started tutorial for SP and IdP; (2) API reference; (3) refresh install/examples | — |
| Effort to A1 | **M** [Inference: three of four front-matter items exist; needs a new getting-started page and overview additions] | — |
| Effort to full policy | **L** [Inference: adds API reference generation, CI build, tutorial rewrite] | — |

### SATOSA

| Field | Finding | Source / basis |
|---|---|---|
| Type | Service (protocol proxy) | README |
| Maintenance | Last commit 2026-09-30; 19 commits from 3 people (Ivan Kanakarakis, Ric Janus Sapasap, Vlad Mencl); v8.6.0 (2026-09-28) → **active** | `git log`, `git tag` |
| Where docs live | README (use cases + table of contents into `doc/README.md`); `doc/` (7 Markdown files, 7,066 words), rendered on GitHub; wiki with 6 pages (last edited 2022-08-31) | file list; wiki |
| Version documented | Not stated anywhere in the docs | `doc/` |
| **A1a Overview** | **[Rating 2]** One-line description and 3 use cases with links. No status, maintainers or supported versions | `README.md` (last changed 2022-11-15) |
| **A1b Getting started** | **[Rating 2]** `doc/README.md` covers Docker and manual install, then full configuration; use-case guides exist but date from 2016 (`SAML2-to-Social_logins.md`, `saml2-to-oidc.md`, `oidc-to-saml2.md`). No short tutorial to a first working proxy | `doc/*.md` dates via `git log` |
| **A1c Security & versions** | **[Rating 0]** No security file or section | file list |
| **A1d Changelog** | **[Rating 3]** `CHANGELOG.md`, newest first, 8.6.0 (2026-09-28) | `CHANGELOG.md` |
| A2 Config reference | ✓ Proxy config, attribute mapping, each plugin, micro-services (`doc/README.md`, 5,075 words, last changed 2024-06-11) | `doc/README.md` |
| A2 How-tos | Partial: `mod_wsgi.md` (2020), `one-to-many.md` (2024); no certificate rollover, upgrade or troubleshooting guides | file list |
| A3 Diátaxis coverage | Tutorial ✗; how-to partial; reference ✓ (config); explanation partial (`doc/internals/state.md`, wiki "Anatomy of a response micro-service", "Sequence diagram") | file list; wiki |
| A4 Docstrings | 70% of 285 public defs; 2% typed | AST scan |
| A6 Standards / dependencies | Protocols named in description; no list of specs or versions; dependencies listed in install section | `README.md`, `doc/README.md` |
| B1 Markup | Markdown (7 files); `release-howto.rst` is rST | file list |
| B2 Language / spelling | English; US 10 : UK 6 (e.g. behaviour ×5, behavior ×2) | spelling scan |
| B3 Docstring style | Sphinx `:param` (338) | code scan |
| B5 Tone / clarity | **[Rating 2]** Structured reference with headings and YAML examples; use-case guides short and dated | `doc/` |
| C Tooling | None: Markdown rendered by GitHub; no hosted site; CI is `.travis.yml` / `tox.ini` | file list |
| D Contribution rules | Root `pull_request_template.md` (shared copy; asks for tests and flake8, not docs); no contributing guide in repo; wiki has "satosa-core development guidelines" | templates; wiki |
| E Upkeep | Docs last changed 2024-06-11; code 2026-09-30 | `git log` |
| Notes | README "Contact" names the satosa-users mailing list but links the idpy-discuss list | `README.md` |
| Biggest gaps | (1) Security page; (2) a getting-started tutorial; (3) operator how-tos (rollover, upgrade, troubleshooting) | — |
| Effort to A1 | **M** | — |
| Effort to full policy | **L** [Inference: choosing a toolchain for Markdown docs, plus a how-to set needing maintainer knowledge] | — |

### pyFF

| Field | Finding | Source / basis |
|---|---|---|
| Type | Service (SAML metadata aggregator / MDQ server) | README |
| Maintenance | Last commit 2026-11-03; 88 commits from 5 people (Johan Wassberg, Kushal Das, Mikael Frykholm, Stephan Krinetzki, Vlad Mencl); 3.0.0 (2026-10-26) → **active** | `git log`, `git tag` |
| Where docs live | README; `docs/` (10 files, 3,996 words); pyff.readthedocs.org and pyff.io (linked); wiki with 10 pages (last edited 2024-01-08) | `README.rst`; wiki |
| Version documented | `docs/conf.py` version '3.0' (matches 3.0.0) | `docs/conf.py` |
| **A1a Overview** | **[Rating 2]** Features list; docs index explains purpose and use cases (eduGAIN, MDQ). README badges point to Travis, coveralls `leifj/pyFF` and pyXMLSecurity's license | `README.rst`, `docs/index.rst` |
| **A1b Getting started** | **[Rating 2]** `quickstart.rst` (2019) walks through a first pipeline. `install.rst` (2023) expects Python 3.6 and pyXMLSecurity, which conflicts with `pyproject.toml` (Python ≥3.11, pybergshamra) | `docs/usage/*.rst`; `pyproject.toml` |
| **A1c Security & versions** | **[Rating 0]** None | file list |
| **A1d Changelog** | **[Rating 2]** `NEWS.txt` has a 3.0.0 entry (line 219) and "3.0.1 UNRELEASED"; ordered oldest-first, plain text | `NEWS.txt` |
| A2 Config reference | Pipes reference generated at build (custom `pyff_pipes` extension); `running.rst` (2020) and `deploying.rst` (2026-10-26) | `docs/conf.py`, `docs/usage/` |
| A3 Diátaxis coverage | Tutorial ✓ (quickstart); how-to ✓ (running, deploying, examples); reference ✓ (API via `sphinx.ext.apidoc` in `conf.py`, pipes); explanation partial (wiki "Architecture") | `docs/index.rst`; `docs/conf.py`; wiki |
| A4 Docstrings | 26% of 422; 33% typed | AST scan |
| A6 Standards / dependencies | MDQ drafts named; dependencies listed in README (current) | `README.rst`, `docs/index.rst` |
| B1 Markup | rST | file list |
| B2 Language / spelling | English; US 5 : UK 1; typos in index ("signifficant") | spelling scan; `docs/index.rst` |
| B3 Docstring style | Sphinx `:param` (158) | code scan |
| B5 Tone / clarity | **[Rating 2]** Clear, purpose-first index; some pages stale | `docs/` |
| C Tooling | Sphinx (sphinx_rtd_theme) + `.readthedocs.yml`; CI does not build docs | files |
| D Contribution rules | Shared root PR/issue templates (no docs item); `HACKING.txt` says `./setup.py develop` and "optionally… pyXMLSecurity", now outdated | `HACKING.txt` |
| E Upkeep | Docs actively touched (2026-10-29) alongside the 3.0 release, but install and HACKING not updated for the backend change | `git log` |
| Notes | Wiki page `KAMPANAT-THUMWONG.md` contains only `* `. [Inference: stray or spam page; consider deleting] | wiki |
| Biggest gaps | (1) Update install/HACKING for 3.0 (pybergshamra, Python ≥3.11); (2) security page; (3) README badges and links | — |
| Effort to A1 | **M** | — |
| Effort to full policy | **M** [Inference: structure already close to Diátaxis; mostly currency fixes] | — |

### idpy-oidc

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (OIDC/OAuth2 client, server, messages) | README |
| Maintenance | Last commit 2026-10-02; 1 commit in 12 months (lionick); latest tag v4.5.0 (2024-09-15) → **occasional**. Most commits since 2023 by Roland Hedberg (77) | `git log`, `git shortlog` |
| Where docs live | README; `doc/` (74 rST files, 17,077 words); idpy-oidc.readthedocs.io (linked); examples in `example/` (per README) | file list |
| Version documented | **Inconsistent:** `doc/conf.py` '1.0.0'; `pyproject.toml` 3.0.0; `src/idpyoidc/__init__.py` 5.0.0; latest tag v4.5.0 | those files; `git tag` |
| **A1a Overview** | **[Rating 2]** Clear statement and a full list of standards and add-ons; no status or maintainers | `README.md` (last changed 2023-12-18) |
| **A1b Getting started** | **[Rating 1]** README points to `example/` and to the hosted docs; no quickstart in `doc/`. A migration guide (`doc/move.rst`) exists for users of oidcmsg/oidcrp/oidc-op | `README.md`, `doc/index.rst`, `doc/move.rst` |
| **A1c Security & versions** | **[Rating 0]** None | file list |
| **A1d Changelog** | **[Rating 0]** `CHANGELOG.md` contains only "0.1.0 [Unreleased] — No change log folks. Sorry." (last changed 2022-03-24). `.github/release-drafter.yml` present. [Inference: notes may be on GitHub Releases; unverified] | `CHANGELOG.md` |
| A2 Config reference | ✓ Server config (`doc/server/contents/conf.rst`) and client config (`doc/client/config.rst`) | file list |
| A3 Diátaxis coverage | Tutorial ✗; how-to partial (`doc/message/howto`, `move.rst`); reference ✓ (50 files with autodoc directives); explanation partial (`intro.rst`) | `grep automodule` |
| A4 Docstrings | 29% of 1,395; 18% typed | AST scan |
| A6 Standards / dependencies | ✓ Standards list with links; position in stack ("2nd layer… cryptojwt, idpyoidc") | `README.md` |
| B1 Markup | rST | file list |
| B2 Language / spelling | English; US 116 : UK 19 (behaviour ×19) | spelling scan |
| B3 Docstring style | Sphinx `:param` (772); a few epytext `@param` (10) | code scan |
| B5 Tone / clarity | **[Rating 2]** Large, reference-heavy; structure follows the code (message / server / client). [Inference: from table of contents and file names; page content not read in full] | `doc/index.rst` |
| C Tooling | Sphinx (classic) with autodoc/autosummary; no `.readthedocs.yml`; CI does not build docs | `doc/conf.py`; workflows |
| D Contribution rules | `CONTRIBUTING.md` is the OpenID Foundation "JwtConnect-Python" text (OIDF CLA, links to openid/ repos); README says PRs go to the `develop` branch | `CONTRIBUTING.md`, `README.md` |
| E Upkeep | Docs last changed 2024-05-24; code 2026-10-02; only 1 docs commit since Nov 2023 | `git log` |
| Notes | Default branch is `main`; README says development happens on `develop`, which was not inspected | `README.md` |
| Biggest gaps | (1) Version metadata and changelog; (2) contributing guide that matches IdPy governance; (3) getting-started tutorial | — |
| Effort to A1 | **L** [Inference: changelog has to be rebuilt from tags/releases, and version numbers sorted out with maintainers first] | — |
| Effort to full policy | **L** | — |

### pyop

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (OIDC provider) | README |
| Maintenance | Last commit 2026-09-28; 8 commits from 4 people (Benjamin Truninger, Ivan Kanakarakis, Sebastian Mennicke, Zoopa); v3.5.0 (2026-09-28) → **active** | `git log`, `git tag` |
| Where docs live | README only (1,186 words) | file list |
| Version documented | Not stated in README | `README.md` |
| **A1a Overview** | **[Rating 2]** Introduction, supported OIDC features with spec links, list of implementations (incl. SATOSA frontend, linked at the old `its-dirg/SATOSA` path) | `README.md` (last changed 2021-06-17) |
| **A1b Getting started** | **[Rating 2]** Configuration example and endpoint-by-endpoint usage with code; no install section | `README.md` |
| **A1c Security & versions** | **[Rating 0]** None | file list |
| **A1d Changelog** | **[Rating 3]** `CHANGELOG.md`, newest first, 3.5.0 (2026-09-28), includes a security entry | `CHANGELOG.md` |
| A3 Diátaxis coverage | All in one README: reference + how-to mixed; no explanation | `README.md` |
| A4 Docstrings | 38% of 97; 0% typed | AST scan |
| A6 Standards / dependencies | ✓ Specs listed; depends on "pyoidc and pyjwkest" (links to `rohe/` repos). pyjwkest's own README says it is not maintained | `pyop:README.md`; `pyjwkest:README.rst` |
| B1 Markup | Markdown | — |
| B2 Language / spelling | English; US 9 : UK 0 | spelling scan |
| B3 Docstring style | Sphinx `:param` (76) | code scan |
| B5 Tone / clarity | **[Rating 2]** Well structured by endpoint, with examples; Travis badge | `README.md` |
| C Tooling | None; `.travis.yml`, `tox.ini` | file list |
| D / E | No contributing guide or templates; README unchanged since 2021 while code released 2026-09 | `git log` |
| Biggest gaps | (1) Security page; (2) install section and current versions; (3) note on the pyjwkest dependency | — |
| Effort to A1 | **M** | — |
| Effort to full policy | **M** | — |

### JWTConnect-Python-CryptoJWT

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (JOSE: JWS/JWE/JWK/JWT) | README |
| Maintenance | Last commit 2026-03-23; 22 commits, 1 person (Jakob Schlyter); v1.11.0 (2026-03-24) → **active** (single committer). `.github/CODEOWNERS` assigns `@IdentityPython/oidc` | `git log`; `.github/CODEOWNERS` |
| Where docs live | README (41 words); `doc/` (14 rST files, 3,060 words); cryptojwt.readthedocs.io (linked) | file list |
| Version documented | `doc/conf.py` version "0.4" vs release v1.11.0 | `doc/conf.py`; `git tag` |
| **A1a Overview** | **[Rating 1]** One sentence naming RFC 7515–7519 plus a Python-version badge (3.7–3.13) | `README.md` |
| **A1b Getting started** | **[Rating 1]** No install section; `doc/keyhandling.rst`, `jws.rst`, `jwe.rst` give examples (last changed 2019–2021) | `doc/` dates |
| **A1c Security & versions** | **[Rating 0]** None | file list |
| **A1d Changelog** | **[Rating 0]** No changelog file. `.github/workflows/release.yml` present. [Inference: notes may be on GitHub Releases; unverified] | file list |
| A3 Diátaxis coverage | How-to ✓ (key handling, JWS, JWE); reference ✓ (9 files with autodoc, mostly 12-word stubs); tutorial ✗; explanation ✗ | `doc/source/*.rst` |
| A4 Docstrings | 61% of 427; 7% typed | AST scan |
| A6 Standards / dependencies | RFCs named in README; no dependency notes | `README.md` |
| B1 Markup | rST | — |
| B2 Language / spelling | English; US 5 : UK 0 | spelling scan |
| B3 Docstring style | Sphinx `:param` (408) | code scan |
| B5 Tone / clarity | **[Rating 2]** Task pages are practical with code; index is the sphinx-quickstart default text | `doc/index.rst` |
| C Tooling | Sphinx (default theme); no `.readthedocs.yml`; CI does not build docs | files |
| D Contribution rules | `CONTRIBUTING.md` is the OpenID Foundation "JwtConnect-Python" text (OIDF CLA) | `CONTRIBUTING.md` |
| Biggest gaps | (1) Changelog; (2) overview and install in README; (3) security page | — |
| Effort to A1 | **M** | — |
| Effort to full policy | **M** | — |

### djangosaml2

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (Django SAML SP app built on pysaml2) | README |
| Maintenance | Last commit 2026-02-17; 1 commit in 12 months (Giuseppe De Marco); v1.12.0-1 (2026-02-17) → **occasional** | `git log`, `git tag` |
| Where docs live | README; `docs/source/` (7 files: 4 rST + 3 MD, 4,776 words); djangosaml2.readthedocs.io (linked, with `.readthedocs.yml`) | file list |
| Version documented | `docs/source/conf.py` version '0.2.4' vs release v1.12.0-1 | `conf.py`; `git tag` |
| **A1a Overview** | **[Rating 2]** Description and feature list; "Special thanks" lists past maintainers; no current maintainer named | `README.md` (last changed 2023-09-29) |
| **A1b Getting started** | **[Rating 2]** `setup.rst` (3,281 words, last changed 2025-07-26) covers install and configuration; `usage.md` is 120 words | `docs/source/contents/` |
| **A1c Security & versions** | **[Rating 1]** `security.md` covers secure configuration (CSP, signatures); no reporting route or supported versions | `docs/source/contents/security.md` |
| **A1d Changelog** | **[Rating 1]** `CHANGES` ends at v1.2.2 (2021-05-27); `.github/release-drafter.yml` present. [Inference: later notes may be on GitHub Releases; unverified] | `CHANGES` |
| A3 Diátaxis coverage | How-to/reference mixed in setup; developer page; FAQ; no API reference (0 autodoc files) | file list |
| A4 Docstrings | 41% of 91; 26% typed | AST scan |
| A6 Standards / dependencies | Built on pysaml2 (stated); supported Python/Django versions shown via PyPI badges | `README.md` |
| B1 Markup | Mixed rST + MD (recommonmark) | `conf.py` |
| B2 Language / spelling | English; US 7 : UK 2 | spelling scan |
| B3 Docstring style | No field lists (docstrings are prose) | code scan |
| B5 Tone / clarity | **[Rating 2]** Practical setup guide | `setup.rst` |
| C Tooling | Sphinx (sphinx_rtd_theme, recommonmark) + `.readthedocs.yml`; CI does not build docs; CI badge points to `peppelinux/djangosaml2` | files; `README.md` |
| D Contribution rules | README: PRs to the `dev` branch; no contributing file or templates | `README.md` |
| Notes | Default branch `master`; README says development is on `dev`, which was not inspected | `README.md` |
| Biggest gaps | (1) Changelog/release notes in the docs; (2) vulnerability reporting route; (3) named maintainer | — |
| Effort to A1 | **M** | — |
| Effort to full policy | **M** | — |

### pyMDOC-CBOR

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (mdoc/mDL issuance and verification, EUDI Wallet) | README |
| Maintenance | Last commit 2026-07-21; 17 commits from 3 people (Flavius Bindea, Giuseppe De Marco, peppelinux); 1.4.0 (2026-07-21) → **active**. [Inference: "peppelinux" and "Giuseppe De Marco" are likely the same person; based on `djangosaml2:README.md` CI badge path `peppelinux/djangosaml2`] | `git log` |
| Where docs live | README (1,385 words); `docs/` (7 MD files, 4,277 words) | file list |
| **A1a Overview** | **[Rating 3]** Specs and resources, scope, references, authors | `README.md` (last changed 2026-07-21) |
| **A1b Getting started** | **[Rating 3]** Setup, then usage examples for issuing, parsing and verifying | `README.md` |
| **A1c Security & versions** | **[Rating 1]** `docs/SECURITY-DEPENDENCIES.md` documents accepted dependency CVEs; no reporting route | that file |
| **A1d Changelog** | **[Rating 0]** `CHANGELOG.md` exists but is empty (0 bytes) | file |
| A3 Diátaxis coverage | Tutorial/how-to ✓ (README usage, `docs/CREATE-MSO.md`); explanation ✓ (`docs/MSO.md`, `CERTIFICATE-CHAIN-VERIFICATION.md`); no API reference | `docs/` |
| A4 Docstrings | 74% of 53; 66% typed | AST scan |
| A6 Standards / dependencies | ✓ | `README.md`, `docs/SECURITY-DEPENDENCIES.md` |
| B1 Markup | Markdown | — |
| B2 Language / spelling | English; US 11 : UK 2 | spelling scan |
| B3 Docstring style | Sphinx `:param` (52), some Google `Args:` (6) | code scan |
| B5 Tone / clarity | **[Rating 3]** Current, example-led | `README.md` |
| C Tooling | None (Markdown in repo); CI runs lint/security checks, not docs | workflows |
| Notes | Not in the agreed core project list (Governance notes 2026-09-30) | Meetings repo |
| Biggest gaps | (1) Fill the changelog; (2) reporting route; (3) API reference | — |
| Effort to A1 | **S** | — |
| Effort to full policy | **M** | — |

### satosa-docker

| Field | Finding | Source / basis |
|---|---|---|
| Type | Packaging (Docker "Official Image" source) | README |
| Maintenance | Last commit 2026-10-01; 2 commits, 1 person (Jean-François Guillaume); no tags; most commits since 2023 by Matthew Economou → **occasional** | `git log` |
| Where docs live | README (547 words). The image's user documentation is generated from the external docker-library/docs repo (`satosa` directory) | `README.md` |
| **A1a Overview** | **[Rating 2]** States purpose and where user docs live | `README.md` |
| **A1b Getting started** | **[Rating 1]** Not in this repo (on Docker Hub via docker-library/docs). [Inference: Docker Hub content not checked] | `README.md` |
| **A1c Security & versions** | **[Rating 0]** None | — |
| **A1d Changelog** | **[Rating 0]** None (follows SATOSA releases). [Inference: from README's description of the image update process] | `README.md` |
| D Contribution rules | README has Contributing, Coding Style, Commit Messages, Update Process | `README.md` |
| Biggest gaps | Link to SATOSA docs and the IdPy security route | — |
| Effort to A1 | **S** | — |

### pyjwkest

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (JOSE, predecessor of CryptoJWT). [Inference: CryptoJWT covers the same RFCs; based on both READMEs] | READMEs |
| Maintenance | Last commit 2025-10-04 (v1.4.4); 0 commits in 12 months → **none**. README opens: "NOTE!! This library is NOT actively maintained anymore" | `README.rst` |
| Where docs live | README; `doc/` (10 rST files, last changed 2014–2016) | `git log` |
| A1 ratings | Overview **1** (honest status notice; spec links are to old drafts); getting started **0** (Python 2.7/3.4, pycrypto, `python setup.py install`); security **0**; changelog **2** (`CHANGELOG.md` created 2025-10-04 with one entry) | `README.rst`, `CHANGELOG.md` |
| Other | rST; Sphinx (classic, version '0.7'); docstrings 33% / typed 0%; US 17 : UK 0 | scans |
| Notes | pyop depends on it (`pyop:README.md`) | — |
| Suggested action | Status page only. Keep the "not maintained" notice, add the IdPy security route, and point to CryptoJWT. Raise the pyop dependency with maintainers | — |

### pyeleven

| Field | Finding | Source / basis |
|---|---|---|
| Type | Small service (PKCS#11 REST proxy) | README |
| Maintenance | Last commit 2025-07-10 (v0.0.2); 0 in 12 months → **none** | `git log` |
| A1 ratings | Overview **1** (one-line purpose); getting started **1** (step list using `apt-get install python-virtualenv`, `./setup develop`; README last changed 2019-09-05); security **0**; changelog **0** | `README.md` |
| Other | README only; docstrings 4% / typed 0%; badges point to landscape.io, Travis and `leifj/pyeleven` | scans; `README.md` |
| Notes | README: "Currently 'mech' is silently ignored and RSASHA1 is used for everything." [Inference: a security-relevant limitation worth stating in any status page] | `README.md` |
| Suggested action | Status page only, plus an archive decision with maintainers | — |

### pyXMLSecurity

| Field | Finding | Source / basis |
|---|---|---|
| Type | Library (XML-DSIG) | README |
| Maintenance | Last commit 2023-10-13; 1.0.0 (2023-08-24); 0 in 12 months → **none** | `git log`, `git tag` |
| A1 ratings | Overview **2** (purpose, dependencies, limitations); getting started **0**; security **0**; changelog **2** (`NEWS.txt` to 1.0.0, oldest-first) | `README.rst`, `NEWS.txt` |
| Other | README only (rST); docstrings 35% / typed 0%; Travis/coveralls badges | scans |
| Notes | pyFF stopped depending on it at 3.0.0 (Key finding 11); pysaml2 can use it as an optional signing backend when `crypto_backend` is set to "XMLSecurity" (default is `xmlsec1`) | `pyFF:pyproject.toml`; `pysaml2:src/saml2/sigver.py` lines 866–983; `pysaml2:docs/howto/config.rst` lines 630–635 |
| Suggested action | Status page only; revisit its future given pyFF's change | — |

### satosa-developer

| Field | Finding | Source / basis |
|---|---|---|
| Type | Packaging (local development environment for SATOSA) | README |
| Maintenance | Last commit 2023-10-07; code last changed 2017-03-29; 0 in 12 months → **none** | `git log` |
| A1 ratings | Overview **1** ("A developer repo for SATOSA"); getting started **1** (run `start.sh`, symlink SATOSA into `sources/`); security **0**; changelog **0** | `README.md` (77 words, last changed 2019-02-11) |
| Suggested action | Status notice and an archive decision (already flagged as an archive candidate in the repo review) | — |

### satosa-refarch-aws

| Field | Finding | Source / basis |
|---|---|---|
| Type | Packaging (AWS reference deployment) | README |
| Maintenance | Last commit 2022-12-10; 0 in 12 months → **none** | `git log` |
| A1 ratings | Overview **2** (purpose, design section); getting started **2** (Quick Start steps); security **0**; changelog **0** | `README.md` (860 words) |
| Suggested action | Archive, as agreed in principle at Fork Review 2026-10-13; add a status line first | Meetings repo |

### new-session-management

| Field | Finding | Source / basis |
|---|---|---|
| Type | Documentation only (session and grant management design) | `README.md` |
| Maintenance | Last commit 2020-12-10; 0 in 12 months → **none** | `git log` |
| Content | 14 rST pages (7,606 words): session claims, database, storage, grant, token, manager, use cases. `conf.py` header says "OidcEndpoint documentation" | `docs/source/` |
| A1 ratings | Overview **1** (README: one line); others **0** | `README.md` (9 words) |
| Notes | [Inference: describes the session subsystem of the archived oidcendpoint; idpy-oidc now has its own `doc/server/contents/session/` docs. Based on the `conf.py` header and the idpy-oidc file list; content overlap not compared] | files |
| Suggested action | Confirm with maintainers whether the content is superseded by idpy-oidc; if so, archive with a pointer | — |

### IdentityPython.github.io (website, idpy.org)

| Field | Finding | Source / basis |
|---|---|---|
| Type | Project admin (Jekyll site) | `_config.yml` |
| Maintenance | Last commit 2025-09-19; 0 in 12 months → **none** | `git log` |
| Pages | `security.md` (594 words, 2022-07-01): reporting address, CVE/advisory FAQ, list of advisories. `contribute.md` (2023-01-17); `org.md` (2024-03-24); `projects.md` (2022-11-29) lists pySAML2, SATOSA, pyFF, idpy-oidc "and associated libraries", djangosaml2; `.well-known/security.txt` → `incident-response@idpy.org`, expires 2032-02-02 | files; `git log` |
| Notes | The security page names pyXMLSecurity, pyeleven, oidcendpoint and JWT-Connect-Python as the main libraries | `security.md` |
| Relevance | [Inference: the natural home for the IdPy-wide security and contribution pages and the docs portal (policy items C6, D5), once refreshed] | — |

### Meetings

| Field | Finding | Source / basis |
|---|---|---|
| Type | Project admin (meeting notes) | `README.md` |
| Maintenance | 31 commits in 12 months (Laura Paglione, Matthew X. Economou) → **active** | `git log` |
| Notes | Not product documentation; listed for completeness | — |

### Governance

| Field | Finding | Source / basis |
|---|---|---|
| Type | Project admin (statutes, incident response plan, project policy) | file list |
| Maintenance | Last commit 2021-04-09 → **none** | `git log` |
| Notes | README is 32 words. Holds the 2021 incident response plan that `pysaml2:SECURITY.md` and the website link to; none of the 2026 Board decisions are recorded here | `README.md`; `pysaml2:SECURITY.md` |

---

## For the group: what to verify first

1. **Inferences** (marked [Inference]). Especially: release notes on GitHub Releases (idpy-oidc, djangosaml2, CryptoJWT); Read the Docs builds without config files; new-session-management being superseded.
2. **The `develop` / `dev` branches** of idpy-oidc and djangosaml2, which may hold newer docs.
3. **The hosted sites** (pysaml2, pyFF, idpy-oidc, CryptoJWT, djangosaml2 on Read the Docs; pyff.io; Docker Hub), to see whether what's published matches the repo source.
4. **The 0–3 ratings.** Change any you disagree with and mark the row "reviewed".
