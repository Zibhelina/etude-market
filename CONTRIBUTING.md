# Contributing to the Etude market

## The file

One JSON file per entry, at `entries/<kind>s/<id>.json`:

```json
{
  "etudeMarket": 1,
  "kind": "theme | deck | type",
  "id": "lowercase-slug",
  "name": "Shown in the market",
  "description": "What it is and who it's for.",
  "author": "how you want to be credited",
  "tags": ["a", "few", "words"],
  "version": "1",
  "updated": "2026-10-25",
  "content": { }
}
```

- **theme**: `content` is a theme as `etude theme export` writes it.
- **deck**: `content` is an Etude pack (`"etude": "pack/1"`), as `etude pack export` writes it, with the custom types its items use.
- **type**: `content` is a pack with the type in `types` and a few example items.

`etude market publish` builds the file for you. `etude market check <file>` validates one.

## Rules

- No review history, personal data or keys. Packs never carry scheduling; check that your item notes don't either.
- Card type scripts run sandboxed (QuickJS on the server, sandboxed iframes in the browser), but keep them readable: no minified or obfuscated code.
- Theme CSS can't load remote files; Etude strips remote `@import` and `url()`.
- Only share what you have the right to share. Course decks made from copyrighted slides or textbooks don't belong here.
- To update your entry, publish again with the same id and a new `version`. People who installed it see an Update button.

## Review

Every pull request runs `etude market index --check`, which validates every entry and dry-run imports each deck and type into an empty collection. A maintainer reads the diff and merges; CI then rebuilds `index.json`.
