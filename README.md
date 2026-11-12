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
| `alignment` | Edges, gaps, radii, optical weight measured | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `audit` | Findings across the whole skill collection | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `color` | Contrast ratios, role tokens, dark mode | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `deconstruct` | Scrub-able timeline of an animation | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `defaults` | Scroll edges, surfaces, type, focus, forms | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `frames` | Throttled CPU trace of one interaction | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `gather` | Reference board before building | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `keyboard` | Keyboard-only walk of a page | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `reuse` | Project parts first, then library, then platform, then custom | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `viewports` | Renders a page at every width, breakpoint edges, short landscape phone, 200% text | [Raphael Salaja](https://github.com/raphaelsalaja) (MIT) | [skills.sh/raphaelsalaja/skills](https://www.skills.sh/raphaelsalaja/skills) |
| `reanimate` | Clone a reference animation, verified frame by frame | Niaz Morshed (MIT) | Not published |

The eight `alignment` through `keyboard`, plus `reuse` and `viewports` installed here, are from [raphaelsalaja/skills](https://github.com/raphaelsalaja/skills) (MIT, (c) 2026 Raphael Salaja). Their `agents/openai.yaml` files ship with each skill. `alignment` is installed and identical to upstream except for its generated `report.html` (yours is the smaller one); it was not overwritten.

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
