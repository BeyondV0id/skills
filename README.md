# Skills

Repo: <https://github.com/BeyondV0id/skills>

My own skills are junctioned into `~/.agents/skills`, not copied. Below: what I wrote, and the installed skills I actually use, with authors and links.

## Frontend skills

| Skill | Covers | Author | Link |
| --- | --- | --- | --- |
| [`frontend`](skills/frontend/) | Brief, order of work, layout, loading/empty/error, reuse, words, sidebar, buttons | [harsha007009](https://github.com/harsha007009) | [this repo](https://github.com/BeyondV0id/skills) |
| `awwwards` | Award-caliber sites from one line | [juliobsz](https://github.com/juliobsz) (MIT) | [github.com/juliobsz/skills](https://github.com/juliobsz/skills) |
| `jury` | Scores a site like a jury would | [juliobsz](https://github.com/juliobsz) (MIT) | [github.com/juliobsz/skills](https://github.com/juliobsz/skills) |
| `unslop` | Turns "AI slop" UI into designed UI | [Damir Sokolovsky](https://heydamir.design/unslop) ([@heydamir](https://x.com/heydamir), CC-BY-4.0) | [heydamir.design/unslop](https://heydamir.design/unslop) |
| `animate` | Build an animation from scratch | [Emil Kowalski](https://animations.dev) | [animations.dev](https://animations.dev) |
| `animation-performance` | Frame budget, compositor-friendly motion | Emil Kowalski | [animations.dev](https://animations.dev) |
| `animation-vocabulary` | Give any motion effect a name | Emil Kowalski | [animations.dev](https://animations.dev) |
| `find-animation-opportunities` | Where this animate, where not | Emil Kowalski | [animations.dev](https://animations.dev) |
| `review-animations` | Motion code review against the bar | Emil Kowalski | [animations.dev](https://animations.dev) |
| `mobile-native` | The platform layer on phones | Emil Kowalski | [animations.dev](https://animations.dev) |
| `emil-design-eng` | Emil's design engineering philosophy, condensed | Emil Kowalski | [animations.dev](https://animations.dev) |
| `tailwind-design-system` | Tokens, components, responsive with Tailwind v4 | [wshobson](https://github.com/wshobson) | [github.com/wshobson/agents](https://github.com/wshobson/agents) |
| `reanimate` | Clone a reference animation, verified frame by frame | Niaz Morshed (MIT) | Not published |

[raphaelsalaja/skills](https://github.com/raphaelsalaja/skills) (MIT, (c) 2026 Raphael Salaja) no longer lives in `~/.agents/skills`. Three of his skills are vendored inside [`frontend/`](skills/frontend/) as `reuse/`, `viewports/` and `alignment/`, with their upstream LICENSE files; the `alignment` copy here keeps your local `report.html`. The rest of the collection (`audit`, `color`, `deconstruct`, `defaults`, `frames`, `gather`, `keyboard`) is not in this repo and is gone from `~/.agents/skills`.

## Other skills

| Skill | Covers | Author | Link |
| --- | --- | --- | --- |
| [`go-or-stop`](skills/go-or-stop/) | Go or no-go before a ship: diff, tests, migrations, flags, watch signals, rollback | [harsha007009](https://github.com/harsha007009) | [this repo](https://github.com/BeyondV0id/skills) |
| `performance-optimization` | Frontend/backend/query/db perf work | [addyosmani](https://github.com/addyosmani) (Addy Osmani) | [github.com/addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) |
| `better-auth-best-practices` | Auth setup with Better Auth | [Better Auth](https://better-auth.com) | [github.com/better-auth/skills](https://github.com/better-auth/skills) |
| `create-auth` | Scaffold auth in a TypeScript app | [Better Auth](https://better-auth.com) | [github.com/better-auth/skills](https://github.com/better-auth/skills) |
| `agent-browser` | Browser automation CLI via CDP | [Vercel Labs](https://vercel.com) | [github.com/vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser) |
| `find-skills` | Discover skills in repos | [Vercel Labs](https://vercel.com) | [github.com/vercel-labs/skills](https://github.com/vercel-labs/skills) |
| `ego-browser` | Browser automation, ego Chromium | ego (v2.2.0) | Not published |

## Setup

Folders here are junctioned into `~/.agents/skills`, not copied; edits apply immediately.

```powershell
New-Item -ItemType Junction -Path "$env:USERPROFILE\.agents\skills\<name>" -Target "D:\SKILLS\skills\<name>"
```

Restart OpenCode after adding or removing a skill. To unlink: `cmd /c rmdir "<junction path>"`.
