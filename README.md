# corpora.inc

Publishes [corpora.inc](https://corpora.inc), the Corpora Inc website. The source lives in [`corpora-inc/encorpora` → `corpora-site/`](https://github.com/corpora-inc/encorpora/tree/main/corpora-site). This repository only builds that directory and publishes it to GitHub Pages.

- **When it builds:** hourly from encorpora `main`, and on manual runs (`gh workflow run publish -R corpora-inc/corpora-site`).
- **Configuration:** the public presentation config (prices, operator contacts, privacy summary) is the repository variable `CORPORA_SITE_CONFIG`, a JSON document validated by `corpora-site/src/config.ts`. It holds nothing secret.

## Funding directory configuration

The build reads public site configuration from `CORPORA_SITE_CONFIG`. Optional repository variables `CORPORA_SITE_FUNDING_1`, `_2` and `_3` hold consecutive JSON arrays of funding routes. When present, their combined array replaces only the base configuration’s `funding` field. Split at route boundaries and keep each variable below GitHub’s size limit. With no chunks, the base configuration is used unchanged. The site schema validates the combined data before deployment.

These settings are public website content. Never include credentials, private application records or internal account details. Update all needed chunks before dispatching publication; remove unused trailing chunks when shrinking the directory.
