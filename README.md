# Skills

Repo: <https://github.com/BeyondV0id/skills>

My own skills are junctioned into `~/.agents/skills`, 

## Skills that i use

| Skill | Covers | Author | Link |
| --- | --- | --- | --- |
| [`design`](skills/design/) | Brief, order of work, layout, loading/empty/error, reuse, words, sidebar, buttons | [harsha007009](https://github.com/harsha007009) | [this repo](https://github.com/BeyondV0id/skills) |
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


## Setup

Folders here are junctioned into `~/.agents/skills`, not copied; edits apply immediately.

```powershell
New-Item -ItemType Junction -Path "$env:USERPROFILE\.agents\skills\<name>" -Target "D:\SKILLS\skills\<name>"
```

Restart OpenCode after adding or removing a skill. To unlink: `cmd /c rmdir "<junction path>"`.
