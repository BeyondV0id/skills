# Skills

Personal AI-agent skills, junctioned into `~/.agents/skills` so they load with the installed collection. Folders here are linked, not copied; edits in place apply immediately.

```
frontend/          Everything UI in one skill (see frontend/README.md)
release-check/     Go or no-go before a ship (see its SKILL.md)
```

The table below lists the installed skills I use alongside it, with sources where they are known.

## Mine

| Skill | Covers | Source |
| --- | --- | --- |
| `frontend` | Brief, order of work, layout, loading/empty/error, reuse of parts and tokens, interface words, sidebar spec | This repo |
| `release-check` | Go or no-go before a ship: diff, tests, migrations, flags, risks, watch signals, rollback | This repo |

## Emil Kowalski, `animations.dev`

The craft bar for motion. All of these cite Emil Kowalski's design engineering philosophy directly.

| Skill | Covers |
| --- | --- |
| `animate` | Building an animation from scratch: whether, what purpose, tool, curve, duration |
| `animation-performance` | Frame budget, composite-only properties, the paint pipeline |
| `animation-vocabulary` | Naming an effect from a vague description |
| `find-animation-opportunities` | "Where should this animate, and where shouldn't it" |
| `review-animations` | Reviewing motion code against the bar |
| `mobile-native` | The platform layer on phones |
| `emil-design-eng` | Emil's philosophy, condensed |

Source: Emil Kowalski, `animations.dev`. Repo not recorded in the skill files.

## Damir Sokolovsky, `heydamir.design`

| Skill | Covers |
| --- | --- |
| `unslop` | Turning "AI slop" UI into a designed interface. CC-BY-4.0, [@heydamir](https://x.com/heydamir) |

Source recorded in the skill file: license CC-BY-4.0, author Damir Sokolovsky, `heydamir.design/unslop`.

## The "craft rule" collection

`alignment`, `audit`, `color`, `deconstruct`, `defaults`, `frames`, `gather`, `keyboard`

Same house style: numbered rule IDs, severities, "Rule | Count | Severity" reports, "Never Approve a file you did not read." Author and repo not recorded in any of these files. Likely the same author as `unslop` given the identical reporting format, but I could not verify this, so treat the attribution as unconfirmed.

| Skill | Covers |
| --- | --- |
| `alignment` | Pixel-level edges, gaps, radii, visual weight (`measure.js`) |
| `audit` | A review of a change against every skill in the collection |
| `color` | Contrast ratios, role tokens, dark mode (`contrast.js`) |
| `deconstruct` | An animation broken into a scrub-able timeline |
| `defaults` | House defaults: scroll edges, surfaces, type, focus, forms (`recipes.md`) |
| `frames` | A throttled CPU trace of one interaction |
| `gather` | Reference gathering before a design, into one board |
| `keyboard` | Walking a page with only the keyboard |

## Lock-file sources

Recorded in `~/.agents/.skill-lock.json`:

| Skill | Source |
| --- | --- |
| `agent-browser` | `vercel-labs/agent-browser` ([github.com/vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser)) |
| `awwwards` | `juliobsz/skills` |
| `jury` | `juliobsz/skills` |
| `tailwind-design-system` | `wshobson/agents` ([plugins/frontend-mobile-development](https://github.com/wshobson/agents)) |
| `better-auth-best-practices` | `better-auth/skills` plugin `auth-skills` |
| `create-auth` | `better-auth/skills` plugin `auth-skills` |
| `performance-optimization` | `addyosmani/agent-skills` ([github.com/addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)) |
| `find-skills` | `vercel-labs/skills` |

## Known author, unverified repo

| Skill | Covers | Source |
| --- | --- | --- |
| `reanimate` | Clone a reference animation into your own codebase, verified frame by frame | MIT, copyright Niaz Morshed. Repo not recorded in the skill files. |
| `ego-browser` | Browser automation via the ego Chromium stack | Junction to `~/.local/share/ego/ego-skills`, version 2.2.0. Publisher not recorded. |

## Usage notes

- `frontend` is mine and gets used for every page, but it deliberately defers to the others above instead of duplicating them: motion to `animate`, contrast to `color`, defaults to `defaults`, review to `jury` and `audit`.
- Two installed skills were deleted as redundant: `copy` (replaced by the Words section of `frontend`) and `frontend-design` (replaced by `awwwards` + `unslop` + `frontend`).
- Deleted refs you'll see elsewhere: `build-a-page`, `page-layout`, `loading-states`, `microcopy` were merged into `frontend`.

Restart OpenCode after adding a skill. To unlink without touching the folder, use `cmd /c rmdir "<junction path>"`, never `Remove-Item -Recurse`.
