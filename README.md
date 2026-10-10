# French Extensions for Tachimanga / Mihon (FR only)

French-language manga, manhwa, and light novel source extensions for [Tachimanga](https://tachimanga.app) / Mihon / Tachiyomi.

This is a **pruned fork** of `keiyoushi/extensions-source`, keeping only French sources (no NSFW/hentai/porn). It contains **22 sources** across **7 lib-multisrc themes**.

## Sources

### Manga FR
| Source | Package suffix | Theme |
|---|---|---|
| Scan VF | fr.scanvf | mmrcms |
| Japscan | fr.japscan | (standalone) |
| Manga-Scantrad | fr.mangascantrad | madara |
| Mangakawaii | fr.mangakawaii | (standalone) |
| Sushiscan.fr | fr.sushiscanfr | mangathemesia |
| Mangas-Origines.fr | fr.mangasoriginesfr | origines |
| Banchan Scan | fr.banchanscan | (standalone) |
| LanorTrad | fr.lanortrad | (standalone) |
| Raijin Scans | fr.raijinscans | (standalone) |
| Poseidon Scans | fr.poseidonscans | (standalone) |
| Ma Brute | fr.mabrute | madara |
| Manga-Corporation | fr.mangacorporation | pizzareader |
| MangaHub.fr | fr.mangahubfr | madara |
| Pantheon Scan | fr.pantheonscan | madara |
| Lelscan-VF | fr.lelscanvf | fuzzydoodle |

### Manhwa FR
| Source | Package suffix | Theme |
|---|---|---|
| Sushi-Scan | fr.sushiscan | mangathemesia |
| Scan Reader | fr.scanreader | scanreader |
| X-Manga | fr.scanhentaimenu | madara |

### Light Novel FR
| Source | Package suffix | Theme |
|---|---|---|
| Aniverse | fr.aniverse | (standalone) |
| Lelscan | fr.lelscan | (standalone) |
| Scan-Manga | fr.scanmanga | (standalone) |
| Hana Book | fr.hanabook | (standalone) |

## Usage

Add this repo in Tachimanga using the extension index URL:
```
https://raw.githubusercontent.com/ArthurRoux99/fr-extensions-fr/mirror/index.pb
```

In the app: `Browser` → `Extensions` → `+` → paste the URL above.

Use `index.pb`, not `index.min.json`: with `index.pb` Tachimanga installs the JVM `.jar` builds, while `index.min.json` makes it convert the Android APKs, which fails with `java.lang.VerifyError`.

Japscan reads pages through an Android WebView, so it doesn't work on Tachimanga (iOS).

## Build & Index

CI (`.github/workflows/build_push.yml`) builds all 22 sources via GitHub Actions (Java 25) and publishes to the `mirror` branch: `index.min.json` + `repo.json` + `apk/` + `icon/` (Tachimanga / Mihon) and `index.json`/`index.pb`.

Release signing uses the `SIGNING_KEY` (base64 keystore), `ALIAS`, `KEY_STORE_PASSWORD` and `KEY_PASSWORD` secrets. Without them, APKs are signed with a throwaway debug key that changes on every run, so installed extensions can't be updated. To create a key:

```bash
keytool -genkeypair -v -keystore signingkey.jks -alias fr-ext -keyalg RSA -keysize 4096 -validity 36500
base64 -w0 signingkey.jks   # paste as the SIGNING_KEY secret
```

## Contributing

Contributions welcome — open an issue or PR for new FR sources (manga/manhwa/LN, no NSFW).

## License

    Copyright 2015 Javier Tomás
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

    http://www.apache.org/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

## Disclaimer

This project does not have any affiliation with the content providers available.
This project is not affiliated with Mihon/Tachiyomi/Tachimanga. All credits to the codebase goes to the original contributors.
