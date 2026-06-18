# Watcher

This mirror is updated by `substack-block` in `rss_latest` watcher mode.

Why: GitHub-hosted runners received `HTTP Error 403: Forbidden` from Substack's archive API for `hitchhikertothefuture.substack.com`. The archive API remains useful for initial full cuts; the built-in Substack RSS feed is the right scheduled-update source because it exposes the latest posts without needing archive pagination. Beige, but load-bearing.

Hermes cron job:

- name: `weekly-leo-substack-block-mirrors`
- id: `60f50f88598a`
- schedule: `17 9 * * 1`
- script: `/Users/leoguinan/.hermes/scripts/update-leo-substack-blocks.py`
- behavior: rerun the mirror locally, commit and push only when the ordered post set changes, stay silent otherwise.

Manual local update:

```bash
/Users/leoguinan/.hermes/scripts/update-leo-substack-blocks.py
```
