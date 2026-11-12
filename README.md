# Skills

My personal AI-agent skills. Full repo: <https://github.com/BeyondV0id/skills>

| Skill | What it covers | Author |
| --- | --- | --- |
| [`frontend`](frontend/) | Brief, order of work, layout, loading/empty/error states, reuse of parts and tokens, interface words, sidebar spec, button specs ([`frontend/components/buttons.md`](frontend/components/buttons.md)). Details: [frontend/README.md](frontend/README.md) | [harsha007009](https://github.com/harsha007009) |
| [`release-check`](release-check/) | Go or no-go before a ship: diff, tests, migrations, flags, risks, watch signals, rollback | [harsha007009](https://github.com/harsha007009) |

## Setup

Folders here are junctioned into `~/.agents/skills`, not copied; edits apply immediately.

```powershell
New-Item -ItemType Junction -Path "$env:USERPROFILE\.agents\skills\<name>" -Target "D:\SKILLS\<name>"
```

Restart OpenCode after adding or removing a skill. To unlink without touching the folder: `cmd /c rmdir "<junction path>"`, never `Remove-Item -Recurse`.
