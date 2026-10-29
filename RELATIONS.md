# Related repos: this work copy's side

The family and its outline are in the template's `docs/related-repos.md`; this file follows its numbering and says
how this repo, the work copy (larsgson/make-tanakh-work, until 2026-10-29 bsb-add-books-work), stands in it.

## 1. The three repos

| Repo | Role | History | Visibility |
|---|---|---|---|
| **bcv-commons/make-tanakh** | the toolkit and template | its own | public |
| **make-tanakh-work** (this repo) | data: projects, drafts, language stores, alignments, the website | starts from make-tanakh v0.1.0 (2026-10-29, both histories reset) | public |
| **bcv-commons/make-tanakh-grammar** | the rules-engine lab, the language analysis (bcv-commons/language-analysis), where tools start | its own | public, screened |

## 2. This repo's role

In: the projects under `export/` (Danish, Bern German, Kuni, Jamaican, Zinza: drafts, notes, `.align` files, stores,
wikis, status), the imported editions' metadata under `import/` (their texts stay local), the website (`.site`, the
`site` branch). Not here: tools (`scripts/`, `docs/`, `.claude/` are the template's, unchanged), the lab, source texts,
non-free texts and what is built from them (`local_output/`, git-ignored).

## 3. What it takes from the others, and how that is pinned

- **make-tanakh:** everything outside the projects, by merging `template/main` at a tag (now v0.2.0). The template's
  demo projects `export/dan/dan_BSB` and `export/jam/jam_BSB` share their paths with this repo's full projects: at a
  merge, this repo's project files win; the template's other demo files come in.
- **Sources and bcv-commons datasets:** as the template pins them (`scripts/setup.py`, `docs/sources.md`), fetched into
  the git-ignored `orig/`, `reference/`, `download/`.
- **make-tanakh-grammar:** only published, pinned datasets, never code.

## 4. What it gives the others, and in what form

- **To make-tanakh:** fixes found while drafting, as patches; demo material by file.
- **To make-tanakh-grammar:** data by path (`MAKE_TANAKH_ROOT`, or the grammar repo's `MAKE_TANAKH_WORK`): the projects'
  `.align` files and stores, `orig/heb.sqlite`, `orig/grc.sqlite`. The grammar repo reads, never writes here; a change
  it needs in a store or an alignment is made here.
- **To lexeme-aligner and bcv-query:** alignment layers (`full_align.py export`, `<edition>+auto+make-tanakh`) and
  checks, through notes the user sends.
- **To readers:** the website, every chapter marked as a draft until its team publishes it.

## 5. How a change travels

A tool idea goes to make-tanakh-grammar (or straight to the template as a fix); it arrives here only with a merge of
the template. A data change (a draft, a store entry, an alignment) is made here. The user commits and pushes.

## 6. Licences and what never moves

Drafts, notes and stores CC0 (`docs/licensing.md`); quotes short and credited. Never in git here: source texts,
non-free edition texts (Kuni NC-ND, Bietenhard, HEBM95), `local_output/`, BHSA data and anything laid out on it (the
site derives the BHSA view at build time), TBTA data.

## 7. Version records

- The template tag this repo stands on: v0.2.0 (cbda58e). Each later merge names its tag in the merge commit.
- The contract test after each merge (`docs/related-repos.md`, section 7): `git diff template/main -- scripts docs
  .claude` empty; `check_project.py` and `full_align.py check` on every project; `src.py stats`.
