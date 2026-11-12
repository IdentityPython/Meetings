# IdentityPython GitHub repositories — review

_Snapshot of the org's repository list as of 3 Nov 2026 (33 repos), copied from github.com/orgs/IdentityPython/repositories._

**Freshness** is based on GitHub's "Updated" date (a push or a settings/metadata change, so it isn't a perfect measure of real activity):
🟢 **Active** = updated in the last 3 months (since Aug 2026) · 🟡 **Recent** = 3–12 months · 🟠 **Stale** = 1–3 years · 🔴 **Dormant** = 3+ years

| | Public | Private | Archived | Total |
|---|---|---|---|---|
| Repos | 18 | 6 | 9 | **33** |

Counts below are forks / stars / open issues / open PRs, as shown in the list.

---

## 1. Public, not archived (18)

| Repo | Updated | Fresh | Forks | Stars | Issues | PRs | License | Description | Review notes |
|---|---|---|---|---|---|---|---|---|---|
| [pysaml2](https://github.com/IdentityPython/pysaml2) | 2 Nov 2026 | 🟢 | 479 | 616 | 101 | 35 | Apache 2.0 | Python implementation of SAML2 | Core. Largest issue/PR backlog |
| [pyFF](https://github.com/IdentityPython/pyFF) | 2 Nov 2026 | 🟢 | 43 | 59 | 14 | 6 | Other | SAML metadata aggregator | Core; maintained by SUNET. License shows as "Other": check |
| [Meetings](https://github.com/IdentityPython/Meetings) | ~20 Oct 2026 | 🟢 | 0 | 0 | 0 | 0 | Apache 2.0 | Notes and artifacts from IdPy meetings | Project admin (your notes repo) |
| [satosa-docker](https://github.com/IdentityPython/satosa-docker) | 4 Oct 2026 | 🟢 | 6 | 11 | 3 | 0 | Other | Docker Official Image packaging for SATOSA | Packaging for SATOSA. License "Other": check |
| [idpy-oidc](https://github.com/IdentityPython/idpy-oidc) | 2 Oct 2026 | 🟢 | 30 | 49 | 13 | 3 | Apache 2.0 | Implementation of everything OIDC and OAuth2 | Core |
| [SATOSA](https://github.com/IdentityPython/SATOSA) | 30 Sep 2026 | 🟢 | 136 | 276 | 59 | 33 | Apache 2.0 | Proxy translating between SAML2, OIDC and OAuth2 | Core. Second-largest backlog |
| [pyop](https://github.com/IdentityPython/pyop) | 28 Sep 2026 | 🟢 | 36 | 100 | 2 | 2 | Apache 2.0 | OpenID Connect Provider library | SATOSA dependency; has an advisory fork (section 2). Open question from 13 Oct: is it being replaced by idpy-oidc? |
| [pyMDOC-CBOR](https://github.com/IdentityPython/pyMDOC-CBOR) | 21 Jul 2026 | 🟡 | 21 | 22 | 3 | 0 | Apache 2.0 | MDOC CBOR verifier/issuer for EUDI Wallet PID and mDL | Not in the agreed core list. Who maintains it? |
| [IdentityPython.github.io](https://github.com/IdentityPython/IdentityPython.github.io) | 23 Jun 2026 | 🟡 | 0 | 1 | 0 | 4 | BSD 2-Clause | Organization website | Website (asset 5). 4 open PRs |
| [JWTConnect-Python-CryptoJWT](https://github.com/IdentityPython/JWTConnect-Python-CryptoJWT) | 24 Mar 2026 | 🟡 | 18 | 16 | 8 | 1 | Apache 2.0 | RFC 7515–18 (JOSE) using Cryptography | Crypto library used by idpy-oidc. Has an advisory fork (section 2) |
| [djangosaml2](https://github.com/IdentityPython/djangosaml2) | 17 Feb 2026 | 🟡 | 147 | 272 | 35 | 8 | Apache 2.0 | Django SAML2 SP based on pySAML2 | Widely used (272 stars) but not in the agreed core list. Maintainer? |
| [pyjwkest](https://github.com/IdentityPython/pyjwkest) | 8 Jan 2026 | 🟡 | 60 | 94 | 12 | 7 | Apache 2.0 | JWT, JWS, JWE and JWK | Still in use: pyop → pyoidc (external, CZ-NIC) → pyjwkest, so it sits under SATOSA's OIDC provider path. Keep |
| [pyeleven](https://github.com/IdentityPython/pyeleven) | 29 Aug 2025 | 🟠 | 3 | 19 | 0 | 1 | Other | Python PKCS11 REST proxy | Optional REST signing target for pyXMLSecurity. Low activity but in use; keep unless maintainers say otherwise |
| [pyXMLSecurity](https://github.com/IdentityPython/pyXMLSecurity) | 22 May 2024 | 🟠 | 22 | 15 | 12 | 2 | Other | Python XML security (xml-dsig) | Was required by pyFF up to 2.1.7; **pyFF 3.0.0 (26 Oct 2026) replaced it with pybergshamra** (`pyFF:pyproject.toml`). Still an optional signing backend for pysaml2 (`crypto_backend: "XMLSecurity"`). No commits since Oct 2023. Keep for now, but its future is a maintainer question |
| [satosa-developer](https://github.com/IdentityPython/satosa-developer) | 9 Oct 2023 | 🟠 | 2 | 3 | 0 | 0 | none listed | "A developer repo for SATOSA" | **Too little info.** Vague description, no license. Archive candidate |
| [satosa-refarch-aws](https://github.com/IdentityPython/satosa-refarch-aws) | 10 Dec 2022 | 🔴 | 1 | 2 | 7 | 0 | Other | SATOSA reference implementation on AWS | **Already flagged to archive** (Fork Review, 13 Oct) |
| [Governance](https://github.com/IdentityPython/Governance) | 9 Apr 2021 | 🔴 | 1 | 1 | 0 | 0 | none listed | Governance documents for the idpy project | Project admin. **No update since 2021**: Board decisions since (Sept 2026 appointments, Motion D) aren't reflected. No license |
| [new-session-management](https://github.com/IdentityPython/new-session-management) | 11 Dec 2020 | 🔴 | 0 | 0 | 0 | 0 | Apache 2.0 | Docs of the new session management subsystem | **Too little info.** No code language, no activity in 6 years. Archive candidate |

## 2. Private (6): temporary security advisory forks

There are six private repos that are being evaluated for a merge with existing public repos. _(Not listed below)_

## 3. Archived (9): read-only, no action needed

| Repo | Updated | Forks | Stars | Issues | PRs | Description | Note |
|---|---|---|---|---|---|---|---|
| [JWTConnect-Python-OidcRP](https://github.com/IdentityPython/JWTConnect-Python-OidcRP) | 12 Dec 2022 | 27 | 89 | 4 | 0 | High-level interface to the OIDC RP library | Probably superseded by idpy-oidc |
| [oidc-op](https://github.com/IdentityPython/oidc-op) | 3 Nov 2022 | 25 | 67 | 25 | 3 | An implementation of an OIDC Provider | Probably superseded by idpy-oidc. 25 issues left open at archive |
| [JWTConnect-Python-OidcMsg](https://github.com/IdentityPython/JWTConnect-Python-OidcMsg) | 29 Mar 2022 | 10 | 3 | 3 | 1 | OIDC protocol messages | Probably superseded by idpy-oidc |
| [JWTConnect-Python-OidcService](https://github.com/IdentityPython/JWTConnect-Python-OidcService) | 12 Jun 2021 | 4 | 6 | 1 | 3 | OIDC/OAuth2 services | Probably superseded by idpy-oidc |
| [oidcendpoint](https://github.com/IdentityPython/oidcendpoint) | 12 Jun 2021 | 7 | 6 | 7 | 3 | OIDC OP/OAuth2 AS endpoints | Probably superseded by idpy-oidc |
| [satosa_microservices](https://github.com/IdentityPython/satosa_microservices) | 28 Nov 2018 | 4 | 2 | 2 | 1 | Microservices for SATOSA | No license listed |
| [fedoidcrp](https://github.com/IdentityPython/fedoidcrp) | 4 Oct 2018 | 1 | 0 | 0 | 0 | Federation-aware OIDC RP | Early OIDC federation work |
| [fedoidcservice](https://github.com/IdentityPython/fedoidcservice) | 4 Oct 2018 | 1 | 2 | 0 | 0 | OIDC RP library for multilateral federations | Early OIDC federation work |
| [fedoidcmsg](https://github.com/IdentityPython/fedoidcmsg) | 4 Oct 2018 | 2 | 2 | 0 | 0 | OIDC protocol messages for multilateral federations | Early OIDC federation work |

---

## Outstanding Items

- **Archive candidates:** satosa-refarch-aws (already agreed in principle), new-session-management and satosa-developer. pyeleven and pyjwkest are **not** candidates: the dependency map shows each is still used. **pyXMLSecurity has changed status:** pyFF no longer depends on it from 3.0.0, leaving pysaml2's optional backend as its only known IdPy use, so its future is worth raising with the maintainers (see the Documentation Inventory, key finding 11).
- **Ownership gaps:** djangosaml2 and pyMDOC-CBOR are active, used, and not in the agreed core list. Who maintains them?
- **Issue and PR templates are copied by hand.** An identical `issue_template.md` sits at the top level of SATOSA, pyFF, pyXMLSecurity and pyeleven, and an identical `pull_request_template.md` in SATOSA, pyFF and pyXMLSecurity. pysaml2 has its own pair in `.github/`. None of the shared copies mention documentation; an org-level `.github` repo would keep one copy. _(Corrects the first scan, which missed top-level templates.)_
- **License "Other" or none:** pyFF, satosa-docker, pyeleven, pyXMLSecurity, satosa-refarch-aws (Other); satosa-developer, Governance, satosa_microservices (none). Worth confirming each has a clear license file. Part of the tooling/harmonization work.
- **External dependency:** pyop depends on pyoidc, maintained outside IdPy by CZ-NIC. A vulnerability there affects SATOSA's OIDC provider path, and IdPy can't fix it directly.
- **Governance repo is five years stale.** Updating it with the 2026 Board decisions would also support the asset custody plan.

<!--
## Dependency map (from the project diagram, corrected 5 Nov for pyFF 3.0)

A security issue in a lower library affects everything above it:

| Report against | Also affects |
|---|---|
| pysaml2 | SATOSA, djangosaml2, satosa-docker, satosa-developer |
| CryptoJWT | idpy-oidc → SATOSA (optional OIDC extra), satosa-docker |
| pyop | SATOSA (OIDC provider), satosa-docker, satosa-developer |
| pyjwkest (via external pyoidc) | pyop → SATOSA |
| pyXMLSecurity | pyFF **before 3.0.0**; pysaml2 when `crypto_backend` is set to "XMLSecurity" |
| pybergshamra, pyuppsala (external, not IdPy) | pyFF 3.0.0 and later |
| pyeleven | pyXMLSecurity users who sign over HTTP |

Not on the map: pyMDOC-CBOR (standalone), and project-admin repos (Meetings, Governance, website, new-session-management).
-->
_Freshness buckets and "probably superseded" / "archive candidate" notes are Claude's reading of the list; maintainers should confirm._
