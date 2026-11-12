# DRAFT — Documentation worth learning from

_For the Documentation workstream · Laura Paglione · draft started 4 Nov 2026_

**Purpose.** These are examples to look at for one specific thing each, not sites to copy wholesale. Each entry names what to borrow and which IdPy template (see *[IdPy Documentation Templates](2026-11 DRAFT IdPy Documentation Templates.md)*) it informs. Readers are invited to add to this list.

## Frameworks and guidance

| Resource | What to learn from it | Informs |
|---|---|---|
| [Diátaxis](https://diataxis.fr/) | The four documentation types (tutorials, how-to guides, reference, explanation), each serving a different reader need. Already the workstream's working model (Matthew; Hannah's outline) | All templates |
| [Canonical: "Diátaxis, a new foundation for Canonical documentation"](https://ubuntu.com/blog/diataxis-a-new-foundation-for-canonical-documentation) | How a multi-product organization applied Diátaxis across products for a consistent structure, and used it to expose gaps in existing docs. A close parallel to IdPy's many-projects problem | Doc structure across projects |
| [Technical documentation in 2026: built for humans and AI](https://slite.com/learn/technical-documentation) | good general "what makes things good or bad" resource | General advice |

## Named at the 21 October Documentation Workstream meeting
_[(meeting notes)](../Workstream%20-%20Documentation/2026-10-21_Documentation_Agenda-Notes.md)_

| Example | What to learn from it | Informs |
|---|---|---|
| [pytest documentation](https://docs.pytest.org/) | A working example that fits on one screen and shows common use cases right away. The model for "get something working fast" (Matthew) | T2 Getting started; T1 overview |
| [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/) | A full manual with a clear narrative arc: getting started → common tasks → system administration → advanced topics → appendices (Matthew) | Structure for a SATOSA / pyFF operator manual (T5, T6) |

## Close peers in identity and Python

| Example | What to learn from it | Informs |
|---|---|---|
| [Authlib](https://docs.authlib.org/en/v1.5.0/index.html) (Python OAuth / OIDC / JOSE) | The nearest peer to idpy-oidc and CryptoJWT. **Get Started** comes first; **client** guides are separate from **server/provider** guides (split by framework); there's a dedicated **Specifications** section listing each RFC it implements; security reporting sits under Community; there's a top-level changelog | T1 "Standards implemented" table; library docs structure; T3 |
| [SimpleSAMLphp](https://simplesamlphp.org/docs/stable/) | The nearest peer to pysaml2 and SATOSA, in PHP. Organized **by role**: "Using it as a Service Provider" and "Using it as an Identity Provider", each with its own quickstart. Upgrade notes sit next to installation | Role-based getting-started guides for pysaml2 / SATOSA (T2); T4 upgrade notes |

## Our own experiments (to build on)

| Example | What to learn from it | Informs |
|---|---|---|
| [Hannah's pysaml2 GitHub Pages experiment](https://sebulibah.github.io/pysaml2/) | Generating Markdown reference from existing docstrings with autodoc2; adding type annotations and docstrings to get cross-references | T8 API reference |
| [Laura's Read the Docs prototype](https://rtd-docs-example.readthedocs.io/en/latest/) | LLM-drafted, user-focused summaries and class reference from the pysaml2 source | "Using templates with an LLM" |
| [RDCT Actions docs](https://docs.rdctdev.us/actions/v4.0.0/en/index.html) ([source](https://github.com/ResearchDataCom/actions/tree/main/docs)) | Docs built from the Git repo and published by GitHub Actions, with a version picker. Matthew's model for publishing | Tooling proposal |

## Community picks

| Example | What makes it good                                                                                                                    | Informs                                                                                         | Suggested by |
|---|---------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------|
| [Stripe documentation](https://docs.stripe.com/) | Excellent overall structure; Great API docs (side-by-side with sticky code snips), clear navigation                                   | Clear getting started, use case-based structure, separate API/SDK/library docs, integrated help | Laura |
| [Django documentation](https://docs.djangoproject.com/) | Its docs openly explain how they're organized (tutorials, topic guides, reference, how-tos), and djangosaml2 users will know it       | common glossary, include contribution guidelines                                                | Laura |
| [Keycloak documentation](https://www.keycloak.org/documentation) | An identity service with separate server-admin and app-integration guides. A possible model for SATOSA's operator vs integrator split | separate guides & docs                                                                          | Laura |
| [Twillio documentation](https://www.twilio.com/docs) | Essentials/Tools/ Resources, ability to download pages as .md, abiity to attach an AI agent | enable user's AI use                                                                            |  Laura |
