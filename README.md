# Etude market

Themes, decks and card types for [Etude](https://github.com/Zibhelina/etude), shared by the people who made them.

Open the **Market** tab in Etude to browse and install with one click, or use the CLI:

```sh
etude market list --kind type
etude market show typing-test
etude market install typing-test
```

## What's here

| Folder | What | Installs as |
|---|---|---|
| `entries/themes/` | App color themes (CSS variables, optional extra CSS) | A custom theme |
| `entries/decks/` | Decks of items, with any custom card types they use | A pack import; reinstalling updates content and keeps your scheduling |
| `entries/types/` | Card types, with a few example items | A pack import of the type and its examples |

`index.json` lists every entry with a summary. It's rebuilt by CI after each merge, so don't edit it by hand.

## Sharing something

From Etude: **Market → Publish**, pick the theme, deck or card type, describe it, and press **Open pull request**. Etude uses your GitHub CLI (`gh auth login`) to fork this repository, add the file and open the pull request.

From the terminal:

```sh
etude market publish "Japanese::Kana" --kind deck --description "All 92 kana, both ways" --tag japanese
etude market publish my-theme --kind theme --tag dark
etude market publish morse --kind type
```

Without the GitHub CLI, write the file with `-o entry.json` and add it to `entries/<kind>s/` with a pull request on github.com.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the file format and review rules.

## License

Each entry is shared under the license its author states in its description. If none is stated, it's [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) by the author named in the file.
