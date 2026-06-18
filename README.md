# Hitchhiker to the Future Substack Block

Public Data Mine block mirror for `hitchhikertothefuture.substack.com`.

Generated with [`substack-block-adapter`](https://github.com/Marvin-The-Bodega-Cat/substack-block-adapter) v0.1.0.

## Artifact shape

- `mirror/block.json` — Data Mine block records, ordered and stable.
- `mirror/index.json` — normalized post index.
- `mirror/posts/` — one markdown receipt per post.
- `mirror/raw/` — raw Substack archive API JSON per post.
- `mirror/receipts/scrape_completeness_report.json` — falsifiable scrape gate.
- `mirror/receipts/update_receipt.json` — last mirror run receipt.
- `WATCHER.md` — operational watcher receipt.

## Current mirror receipt

- Publication: https://hitchhikertothefuture.substack.com
- Posts mirrored: 95
- Date range: 2025-06-04T14:48:10.557Z to 2026-06-15T12:32:55.550Z
- Sitemap `/p/` URLs: 95
- API missing from sitemap: 0
- Sitemap missing from API: 0
- Offset probe terminated on zero-new batch: True
- Completeness gate passed: True
- Bodies fetched: 0 (`fetch_bodies = false`)

This is a metadata-first public mirror. It preserves stable URLs and archive records; it does not credential-scrape private or paid content.

## Updating locally

```bash
python -m pip install git+https://github.com/Marvin-The-Bodega-Cat/substack-block-adapter.git@v0.1.0
substack-block watch --config substack-block.toml
```

A local Hermes cron watcher commits and pushes new posts if the ordered post set changes. See `WATCHER.md`.
