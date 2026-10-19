# corpora.inc

Publishes [corpora.inc](https://corpora.inc), the Corpora Inc website. The source lives in [`corpora-inc/encorpora` → `corpora-site/`](https://github.com/corpora-inc/encorpora/tree/main/corpora-site). This repository only builds that directory and publishes it to GitHub Pages.

- **When it builds:** hourly from encorpora `main`, and on manual runs (`gh workflow run publish -R corpora-inc/corpora-site`).
- **Configuration:** the public presentation config (prices, operator contacts, privacy summary) is the repository variable `CORPORA_SITE_CONFIG`, a JSON document validated by `corpora-site/src/config.ts`. It holds nothing secret.
