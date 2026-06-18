# Watcher

This mirror is updated by a local Hermes cron watcher, not by GitHub-hosted Actions.

Why: GitHub-hosted runners currently receive `HTTP Error 403: Forbidden` from Substack's archive API for `hitchhikertothefuture.substack.com`. The local adapter run succeeds and passes the sitemap completeness gate. Pretending the GitHub Action works would be tidy and false, a common but unlovely combination.

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
