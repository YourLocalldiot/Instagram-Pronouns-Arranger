# Instagram Pronouns Arranger

Instagram lets you show between 1 and 4 pronouns from different languages next to
your name. This is a single-page web tool that checks whether a given **word or
phrase** can be spelled out by chaining 1–4 of those pronouns together — and, if
so, shows every way to do it along with the source language of each pronoun.

For example, `superhero` can be your pronouns: **su/per/her/o**.

The page is styled after Instagram's "Edit profile" screen.

## Usage

Open [`index.html`](index.html) in a browser. No build step, no dependencies —
everything (the 175-pronoun list and its languages) is embedded in the file.

## Features

- Type a word or phrase and see instantly whether it can be built from Instagram
  pronouns, rendered in an Instagram-style **Pronouns** field with a `n/4` counter.
- A per-result breakdown listing each pronoun and the language(s) it comes from.
- All other valid combinations, each clickable.
- When a word can't be built, it says why (e.g. *no Instagram pronoun uses the
  letter "g"*).
- Example words and a "Surprise me" button.
- The full list of all 175 pronouns with their languages, alphabetically,
  collapsed to 3 rows with an expand/collapse toggle.

## How it works

The input is lowercased, stripped of everything but letters, and has its accents
simplified (`á → a`). The tool then finds every way to split the resulting string
into 1–4 **distinct** pronouns (no pronoun may be reused, matching Instagram's
picker and the original project's algorithm).

The pronoun data lives in [`pronouns/`](pronouns) — one file per language. No
pronoun contains the letters **g**, **q** or **w**, so any word using those is
rejected immediately.

## Some interesting results

| Word      | Pronouns     |
| --------- | ------------ |
| aero      | a/er/o       |
| alive     | al/i/ve      |
| axe       | a/xe         |
| blade     | bla/de       |
| coala     | co/al/a      |
| code      | co/de        |
| cola      | co/la        |
| cool      | co/ol        |
| cosine    | cos/i/ne     |
| deluxe    | delu/xe      |
| developer | de/ve/lo/per |
| dianoia   | dia/no/i/a   |
| elvis     | el/vis       |
| eros      | er/os        |
| ethanol   | et/han/ol    |
| ethereal  | et/her/e/al  |
| heroine   | her/o/i/ne   |
| hiroshima | hir/os/him/a |
| idea      | i/de/a       |
| laser     | la/ser       |
| looser    | lo/os/er     |
| love      | lo/ve        |
| lover     | lo/ver       |
| nasa      | na/sa        |
| never     | ne/ver       |
| none      | no/ne        |
| odessa    | o/dess/a     |
| oliver    | ol/i/ver     |
| olivia    | ol/i/vi/a    |
| opera     | o/per/a      |
| over      | o/ver        |
| persia    | pers/i/a     |
| save      | sa/ve        |
| seoul     | se/o/ul      |
| sexier    | se/xier      |
| sinner    | sin/ner      |
| super     | su/per       |
| supercool | su/per/co/ol |
| superhero | su/per/her/o |

## Credits

- Pronoun lists and the original word-discovery project:
  [SpyrosAcheimastos/instagram_pronouns](https://github.com/SpyrosAcheimastos/instagram_pronouns).
- English word list (`dictionary.json`, used by the upstream project's script):
  [dwyl/english-words](https://github.com/dwyl/english-words).

## Remarks

The Finnish pronouns "hän", "hänet" and "hänen" are stored as `han`, `hanet` and
`hanen` (the "ä" simplified to "a"), following the upstream project, so more
English words can be formed.

Not affiliated with Instagram or Meta.
