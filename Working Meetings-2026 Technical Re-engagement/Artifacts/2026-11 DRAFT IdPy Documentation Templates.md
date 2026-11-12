# DRAFT — IdentityPython documentation templates

_For the Documentation workstream · Laura Paglione · draft started 4 Nov 2026 · for discussion at the next meeting_

**What this is.** A small set of page templates that every IdentityPython project can fill in, so a newcomer finds the same kinds of information in the same places whichever project they open. These are **structure templates**. They say which sections a page has, in what order, at what level of detail and in what format. They don't prescribe wording.

**Why templates.** Two reasons came up on 21 October:

1. **Consistency across projects.** This covers the "front matter" every project should have: what it is, how to install it, and how to get a first thing working.
2. **They make generated drafts usable.** When an LLM is given the code *and* a template, the draft comes back in the expected shape, so reviewing it is quicker. A human still checks every generated draft, and adds the *why* that the code alone can't supply.

**How these relate to other proposals.** The page types follow [Diátaxis](https://diataxis.fr/): tutorial, how-to, reference and explanation. Tooling (Sphinx, MyST Markdown, autodoc, GitHub Pages) is covered in Matthew's proposal. The templates below are plain Markdown, written to work with either. Where they and the tooling proposal disagree, the tooling proposal wins.

---

## 1. What every project needs

Some sections apply to every project, some only to services people run, and some only to libraries people code against.

| Page | Diátaxis type | Main reader | All projects | Services (SATOSA, pyFF, satosa-docker) | Libraries (pysaml2, idpy-oidc, CryptoJWT, pyop, pyXMLSecurity, …) |
|---|---|---|---|---|---|
| [T1 Project overview](#t1-project-overview) | Explanation (short) | Everyone, first visit | **Required** | | |
| [T2 Getting started](#t2-getting-started) | Tutorial | New user or developer | **Required** | | |
| [T3 Security, support and versions](#t3-security-support-and-versions) | Reference | Operators, security teams | **Required** | | |
| [T4 Release and upgrade notes](#t4-release-and-upgrade-notes) | Reference | Operators, upgraders | **Required** | | |
| [T5 How-to guide](#t5-how-to-guide) | How-to | Operator / admin | | **Required** (at least the common tasks) | Recommended |
| [T6 Configuration reference](#t6-configuration-reference) | Reference | Operator / admin | | **Required** | If configurable |
| [T7 Design and architecture](#t7-design-and-architecture) | Explanation | Developers, contributors, advanced operators | Recommended | Recommended | Recommended |
| [T8 API reference conventions](#t8-api-reference-conventions) | Reference | Developers | | | **Required** (generated from docstrings) |
| Contributing guide | — | Contributors | **Required** | | |

The first four rows (T1–T4) are the **minimum front matter**. That's the realistic target for every active project before the December town hall.

**How this maps to Derrick's three audiences:**
- **"Operations manual" (users):** T2 and T5.
- **"Admin guide":** T5, T6 and T4.
- **"Developer guide":** T7, T8 and the contributing guide.

---

## 2. Conventions for all templates

- **Lead with the answer.** The first sentence of each page or section says what it's for, or what the reader will have at the end.
- **Assume a newcomer.** Most readers are occasional users. Link concepts (SAML, OIDC, metadata) the first time they appear, rather than assuming them, and don't re-explain the standards themselves.
- **One page, one job.** Don't mix a tutorial with reference tables. Link between them instead.
- **Runnable examples.** Every code or config snippet should work as shown, with the version it was tested against.
- **Markdown (MyST-compatible).** Use ATX headings (`#`), fenced code blocks with a language, and relative links between pages.
- **Mark generated text.** If a page was drafted by an LLM, say so in a comment at the top, and note who reviewed it and when.

---

## T1 Project overview

_The landing page, which may also be the README. **Diátaxis:** short explanation. **Length:** one screen plus links._

| # | Section | What goes in it | Format |
|---|---|---|---|
| 1 | Name + one-line description | What it is, in one sentence, with no jargon beyond the protocol name | One sentence |
| 2 | What it's for | 2–4 common use cases ("Use pysaml2 to add SAML login to a Python web app…") | Bullets |
| 3 | What it isn't | Common misunderstandings; nearby projects that do something else | 1–3 bullets |
| 4 | Status | Maintained / maintenance-only / looking for maintainers; maintainers' names; supported Python versions | Short table |
| 5 | Standards implemented | Spec, version, level of support (full / partial / not supported) | Table: Spec · Version · Support · Notes |
| 6 | How it fits with other IdPy projects | What it depends on and what depends on it (from the dependency map); key external dependencies | Bullets, or a link to the project map |
| 7 | Install | One command | Code block |
| 8 | Next steps | Links to Getting started, How-tos, Reference, Security, Contributing | Link list |

```markdown
# <project>

<One sentence: what it is.>

## What it's for
- <use case 1>
- <use case 2>

## What it isn't
- <common misunderstanding>

## Status
| Maintained? | Maintainers | Python | Latest release |
|---|---|---|---|
| <yes/maintenance-only/seeking maintainers> | <names> | <3.x–3.y> | <x.y.z> |

## Standards implemented
| Spec | Version | Support | Notes |
|---|---|---|---|
| <SAML 2.0 Core> | <2.0> | <full/partial> | <what's not covered> |

## How it fits with other IdentityPython projects
- **Depends on:** <projects / key external libraries>
- **Used by:** <projects>

## Install
    pip install <package>

## Next steps
- [Getting started](getting-started.md) · [How-to guides](how-to/) · [Reference](reference/) · [Security & support](security.md) · [Contributing](CONTRIBUTING.md)
```

---

## T2 Getting started

_A tutorial: the reader ends with something working. **Diátaxis:** tutorial. **Length:** completable in 15–30 minutes. The pytest docs are the model: a working example that fits on one screen._

| # | Section | What goes in it | Format |
|---|---|---|---|
| 1 | What you'll build | One sentence plus what "working" looks like | Sentence |
| 2 | Before you start | Exact prerequisites: Python version, OS packages (e.g. `xmlsec1`), accounts, test IdP/SP | Checklist |
| 3 | Steps | Numbered; one action per step; the expected output after each important step | Numbered list with code blocks |
| 4 | Check it works | How to confirm success | Short |
| 5 | If something goes wrong | The 3–5 most common failures and fixes | Table: Symptom · Likely cause · Fix |
| 6 | Where to go next | Links to the relevant how-tos and reference | Links |

**Rules:** no choices or branches (pick sensible defaults and link to the alternatives), no explanation beyond one line per step, and every step tested on a clean machine.

```markdown
# Getting started with <project>

By the end of this guide you will have <working thing>, tested with <project> <x.y.z> on Python <3.x>.

## Before you start
- [ ] Python <3.x> or later
- [ ] <system package>
- [ ] <test account / sample metadata>

## Steps
1. Install <project>:

       pip install <package>

2. <Action>. You should see:

       <expected output>

3. …

## Check it works
<How to confirm.>

## If something goes wrong
| Symptom | Likely cause | Fix |
|---|---|---|
| <error text> | <cause> | <fix> |

## Next
- <How-to guide> · <Configuration reference>
```

---

## T3 Security, support and versions

_**Diátaxis:** reference. **Length:** short. Every project links to the same IdPy-wide policy and adds only its own details._

| # | Section | What goes in it | Format |
|---|---|---|---|
| 1 | Reporting a vulnerability | Link to the IdPy-wide `SECURITY.md`: where to report (incident-response@idpy.org or GitHub private reporting) and what to expect | Link + 2 sentences |
| 2 | Supported versions | Which releases get security fixes | Table: Version · Supported until · Notes |
| 3 | Security-relevant configuration | Settings that must be on or off in production (e.g. signature checks, allowed algorithms) | Table: Setting · Safe value · Why |
| 4 | Known limitations | What the project doesn't protect against | Bullets |
| 5 | Dependencies to watch | Key libraries whose vulnerabilities affect this project (e.g. xmlsec1/libxml2, cryptography). This is a light software bill of materials | Table: Dependency · Used for · Where pinned |
| 6 | Advisories | Link to the repo's published GitHub security advisories | Link |

---

## T4 Release and upgrade notes

_**Diátaxis:** reference. One entry per release, newest first, in `CHANGELOG.md`. Upgrade-relevant items go first._

```markdown
## <x.y.z> — <YYYY-MM-DD>

### Security
- <Fix, with GHSA/CVE link>

### Breaking changes and upgrade steps
- <What changed> → <what operators must do>

### Added / Changed / Fixed
- <Item> (#<PR>)

### Dependencies
- <Bumped / pinned / dropped>, with reason
```

---

## T5 How-to guide

_One task, for someone who already knows the basics. Example: "How to roll over the signing certificate for an IdP." **Diátaxis:** how-to. **Length:** as short as the task allows._

| # | Section | What goes in it | Format |
|---|---|---|---|
| 1 | Title | "How to <verb> <thing>" | Heading |
| 2 | When you need this | One or two sentences | Sentences |
| 3 | Before you start | Assumptions and prerequisites | Checklist |
| 4 | Steps | Numbered; config snippets in full | Numbered list with code |
| 5 | Verify | How to confirm it worked | Short |
| 6 | Roll back | How to undo it, if relevant | Short |
| 7 | Related | Links to reference and explanation | Links |

**Starter list for SATOSA and pyFF** (ops tasks named in meetings; maintainers to add to it): roll over a signing certificate, add a new backend or frontend, set up metadata refresh, run behind a reverse proxy, mirror or proxy an IdP, upgrade between major versions, enable logging for troubleshooting.

---

## T6 Configuration reference

_Every setting, in one place. **Diátaxis:** reference. Ideally generated or checked against the code, so it can't drift._

| Option | Type | Default | Required | Description | Example |
|---|---|---|---|---|---|
| `<KEY>` | <str/bool/list/path> | <default or —> | <yes/no> | <one line; link to a how-to if non-obvious> | `<value>` |

Group the tables by config file or component. Below each group, add a complete minimal example config.

---

## T7 Design and architecture

_The why. **Diátaxis:** explanation. This is the page an LLM can't write well from code alone, so it needs a maintainer's input._

| # | Section | What goes in it |
|---|---|---|
| 1 | The problem it solves | Context and history in a paragraph |
| 2 | How it's put together | Main components and the flow of a request; a diagram where it helps |
| 3 | Key design decisions | For each decision: what was chosen, the alternatives, and why. Table: Decision · Alternatives · Reason |
| 4 | Extension points | Plugins, micro-services, backends and how they fit |
| 5 | Trade-offs and known gaps | What it deliberately doesn't do |

---

## T8 API reference conventions

_For libraries. Generated from docstrings; details and tooling as per Matthew's proposal. Hannah's pysaml2 experiment showed that the existing docstrings are written for maintainers rather than users._

- **One docstring style everywhere** (to be chosen with the tooling proposal). Every public module, class and function gets a one-line summary, its parameters, return value and exceptions raised, plus an example for the main entry points.
- **Type annotations on public APIs**, so the reference can show types without repeating them in prose.
- **Each module page starts with one paragraph** saying what the module is for and when you'd use it, before the generated list.
- **Mark internals as internal**, with a leading underscore or a note, so the reference shows only what users should rely on.

---

## Using these templates with an LLM

This is the approach that has worked so far: write **one** page by hand, adjust the template from that experience, then let the model produce the rest.

1. **Give the model** the template, the source (code, existing docs, config samples, presentations) and one finished page as a model.
2. **Ask for the template's sections in its order**, with the stated formats (which parts as tables and which columns, which as bullets, which as prose), and for gaps to be marked rather than guessed.
3. **Review every draft.** A maintainer checks facts, runs the examples and adds the *why* (T7 especially).
4. **Mark the page** as generated, with the reviewer and date (see Conventions).

**Sample prompt** (to adjust):

```text
You are drafting documentation for <project>, an IdentityPython project.
Using ONLY the attached source and docs, fill in the attached template "<T2 Getting started>".
Keep the section order and formats exactly as the template specifies.
Where the source does not tell you something, write "TODO: <what is missing>" instead of guessing.
Write for a newcomer who knows <SAML/OIDC> basics but not this project.
Every command and config example must be copied from or consistent with the source.
```

Shannon's prompt work and Diátaxis-based experiments will feed into this section.

---

## Open questions for the workstream

- Are the four front-matter pages (T1–T4) the right minimum for every project by December?
- Should the project overview (T1) be the README, the docs landing page, or both, with one generated from the other?
- Who writes the design and architecture pages (T7) for SATOSA and pysaml2, given they need maintainer knowledge?
- Should one IdPy-wide `SECURITY.md` and contributing guide be inherited from the org's `.github` repo, with project pages only adding specifics?

_Drafted with help from Claude from the 21 Oct workstream discussion; structure and sample prompt for the group to adjust._
