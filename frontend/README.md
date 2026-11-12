# Frontend

One skill, `frontend`, covering how I build every page: the order of work, the layout rules, all the states, reuse of existing parts and tokens, and the words on screen.

## What it covers

| Section | File | What's in it |
| --- | --- | --- |
| Build order | `SKILL.md` | Brief, references, copy, wireframe, tokens, build, states, QA |
| Layout | `SKILL.md` | Hierarchy, measure, grid, rhythm, density, breakpoints, sidebar spec |
| States | `SKILL.md` | Loading thresholds, skeletons (measure the loaded UI), empty, error, a11y |
| Reuse | `SKILL.md` | Project parts first, then library, then custom - all on role tokens |
| Words | `SKILL.md` | Title Case labels, fewest words, one term per thing, no em dashes |
| Buttons | `components/buttons.md` | Primary and secondary finishes, sizes, states, labels, contrast |

## Files

```
frontend/
  SKILL.md                the entry point - read this first
  components/
    buttons.md              component spec, pulled in on demand
  README.md                this file
```

`SKILL.md` is the only file loaded by the agent until a reference is cited; `components/buttons.md` stays out of context until the page needs buttons.

## Rule prefixes

`page-*` (build order), `layout-*` (layout and sidebar), `loading-*` (states), `reuse-*` (tokens and reuse), `unslop-copy-*` (words). Component specs keep the prefix of their own area.

## What it defers to

Deliberately not in here, because the installed collection already owns it: motion (`animate`), contrast and dark mode (`color`), component defaults (`defaults`), pixel-level alignment (`alignment`), review (`audit`, `jury`), full design takeover (`awwwards`, `unslop`).

## Adding a component spec

1. Add `components/<name>.md` following the buttons format: what it is, exact values, every state, choosing-rules, labels.
2. Cite it from `SKILL.md` where the order step uses it.
3. Commit. The junction in `~/.agents/skills/frontend` picks the file up without another link.
