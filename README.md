# My frontend skills

One skill, `frontend`, linked into `~/.agents/skills` and updated the moment a file changes.

```
frontend/
  SKILL.md                  the order: brief, layout, states, reuse, words
  components/
    buttons.md               primary and secondary button specs
```

Component specs live under `components/` and are pulled in on demand. Rule IDs keep their prefixes: `page-*`, `layout-*`, `loading-*`, `reuse-*`, `unslop-copy-*`.

Restart OpenCode after adding or removing a skill. To unlink without touching the folder, use `cmd /c rmdir "<junction path>"`, never `Remove-Item -Recurse`.
