---
name: frontend
description: Builds and reviews a page end to end - the order to work in, layout and measure, loading, empty and error states, reusing existing parts and tokens, and the words. Use when building or fixing a page, landing page, dashboard or app screen, when a layout feels cramped or generic, when adding loading or empty states, when reaching for a new component, colour or icon, or when writing labels and status text.
---

# Frontend

A page is finished when it reads in the right order at every width and looks like the same product made it. That means one job per page, real words, a layout that holds, states that exist, parts that already exist, and labels that say what happens.

Work in the order below. Each step has a condition for leaving it; do not start the next until it passes.

## Start with one sentence

Who reads this page, what single action it exists to produce, and the one thing they should remember. Write all three down before code. A page with no one-thing is `page-no-brief`, and no amount of polish rescues it.

## The order

1. **Brief.** Who, what action, the one memory, the limits: brand, stack, deadline, languages, data.
2. **References.** Five to ten that solve the same problem, not merely look good. Commit to a direction in three adjectives plus one reference. Averaging five references into beige is `page-averaged-direction`.
3. **Copy first.** Headline, subline, buttons, three feature titles, one proof point, the empty and error states. Write the longest plausible string for every field. Lorem is `page-lorem`.
4. **Wireframe.** Number the sections, give each a job and one action, then sketch the first screen and the densest screen. If two sections can swap without changing the reading, one is redundant.
5. **Tokens.** Type scale, spacing scale, colour roles, radii, three elevations, two durations and one curve. Everything you use later has a name. Contrast passes here, not afterwards.
6. **Build.** Shell and grid, then sections in reading order, one complete at a time. Build a component the second time it is needed, not the first (`page-components-first`). Then states, then details. Button finishes, both of them, live in [components/buttons.md](components/buttons.md).
7. **States.** Default, hover, focus-visible, active, disabled, selected, invalid, loading, empty, error, success. Plus long content, 320px, dark mode, reduced motion, slow network.
8. **QA.** Widths 320, 375, 768, 1024, 1280, 1536 and 200% zoom. Keyboard through the whole page, contrast in both themes, no shift when fonts or images land, every string read aloud.

Only designing the default state is `page-happy-path-only`. Checking one width is `page-single-width`.

## Layout

- One action per page. Two equal primary buttons is `layout-two-actions`.
- Above the fold: what it is, why it is better, what to do next. A hero that only names the company is `layout-hero-without-promise`.
- Three widths and no more: 1280 for the page shell, 1024 for content blocks, 65ch for prose. A fourth width is `layout-four-widths`.
- Body text runs 45 to 75 characters. Edge to edge on a wide screen is `layout-wide-measure`.
- One spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128. A 37px gap is `layout-off-scale`.
- Section padding is visibly larger than the spacing inside it, or `layout-flat-rhythm`.
- Hierarchy is size, then weight, then space. Each step down is at least 1.25x, or it does not read as a step (`layout-flat-hierarchy`). One h1. Colour is not a hierarchy tool.
- Density follows the page type: marketing 1.6 line-height, app 1.5, table 1.4. Mixing them is `layout-mixed-density`.
- Breakpoints go where the content breaks, not where a device exists. Test the ladder at every step. Use container queries for components that appear in a sidebar and at full width.
- Stacking keeps DOM order. Reversing with `order` is `layout-order-not-dom`.
- One surface per section: a background or a card, not both. A page of stacked bordered boxes is `layout-box-everything`.

## Sidebar

A sidebar is a container, not a list of rows. It holds grouped sections; each group has a heading, a set of rows, and a gap between them that is visibly larger than the gap between rows. If the group gap equals the row gap, the rows read as one long list and the grouping is lost (`layout-group-gap`).

Panel radius 12px, not 4. At 4 the corners look sharp against the rounded rows inside, and the panel reads as a clipped rectangle rather than a surface (`layout-panel-radius`).

Rows are 32px tall, inset 8px from the panel edge, so a selected row sits clear of the border instead of touching it. A row flush with the panel edge is `layout-row-flush`. Row gap 10px; group gap 20px.

Each row is 18px icon, 10px gap to the label, then the label and trailing content. At 22px the icon is louder than the label, and at a 4px gap the icon and label read as one shape rather than two (`layout-icon-size`, `layout-icon-label-gap`).

The active row is the only row with a fill; the others show hover on `:hover`. Active is `background: var(--surface-raised)` plus a 1px ring, never a second colour, and never an accent fill on a navigation row.

The sidebar is 240px wide, scrolls its own content with `overscroll-behavior: contain`, and collapses to a rail on the same breakpoint the main content switches to two columns. A fixed-width sidebar that never collapses is `layout-rigid-sidebar`.

```css
.sidebar {
  width: 240px;
  overflow-y: auto;
  overscroll-behavior: contain;
}

.sidebar-group { margin-bottom: 20px; }

.sidebar-row {
  display: flex;
  align-items: center;
  gap: 10px;
  height: 32px;
  padding: 0 8px;
  border-radius: 8px;
}

.sidebar-row svg { width: 18px; height: 18px; flex-shrink: 0; }
.sidebar-row.is-active {
  background: var(--surface-raised);
  box-shadow: 0 0 0 1px var(--border);
}
```

## Waiting, empty, broken

- Nothing shows before 200ms. A loader that flashes is `loading-flash`, and it makes the product feel slower.
- From 200ms, a skeleton. From 1s, add a status line. Over 10s, offer a way out. A spinner at 30s with no escape is `loading-no-escape`.
- Reserve the box. Give images and embeds an aspect ratio, and give the skeleton the real padding, radius and row count. Anything else shifts when the data lands (`loading-layout-shift`, `loading-skeleton-mismatch`).
- The skeleton is a grey wireframe of the content: circle, two text bars, badge, action. `currentColor` at 8 to 12%, so dark mode needs no second palette.
- Measure the loaded UI instead of guessing the skeleton. Run the page in Playwright, let the data settle, then read the real boxes with `getBoundingClientRect()` on a row, its title, its avatar and its action, and give the skeleton those exact sizes and gaps. A skeleton drawn by eye drifts a few pixels per row, and that drift is the jank when the data lands (`loading-skeleton-guessed`).
- Shimmer only if it is one direction, 1.6 to 2s, transform-only, and stops under `prefers-reduced-motion`. When unsure, leave it still.
- One loader at a time. No spinner on a skeleton, and no overlay over content that is already usable (`loading-blocks-usable-content`).
- Refetch keeps the old content and dims it. Replacing a list with skeletons on every filter is `loading-refetch-flicker`.
- Buttons keep their width, set `aria-busy`, ignore repeat clicks, and restore the label on failure (`loading-button-jump`).
- Loading, empty and error are three different screens. Empty explains what would be there and offers the action. Error says what failed and what to do next, in the scope that failed (`loading-states-blurred`, `loading-error-scope`).
- Mark the region `aria-busy`, hide the skeleton from screen readers, announce completion once, and keep focus where it was.

## Reuse before writing

A new component, style, icon or colour that duplicates one the project already has is a finding. Adding a primitive to the shared package and then using it is not. A project with no shared package is judged on the libraries it already depends on.

Cutting what nobody asked for belongs to restraint. Copying an outside app belongs to match. Contrast, dark mode and role tokens are covered in depth by `color`; this section is about reaching for the existing one first.

**The project's parts come first.** Search the shared component package, the icon set, the colour tokens and the type scale before writing UI. Name what you found. A raw `<input>` beside the project's `Input` is `reuse-house-component-first`.

**Shipped components stay as shipped.** Use a component's variants and `data-*` attributes. Restyling it with a local `className` is `reuse-no-local-restyle`.

**One style per kind of thing.** Keep one menu, one table and one dialog shell. A second dropdown style is `reuse-one-standard`.

**Fix it once, in the primitive.** When a fix applies to every instance, make it inside the shared component. Patching five call sites is `reuse-fix-in-the-primitive`. Then find every sibling and list the files.

**Then a library or the platform.** `Intl` formats dates and numbers. The native context menu handles right-click. A hand-written formatter is `reuse-library-before-custom`. Check that a library is maintained; if it is not, port the pattern instead of installing it (`reuse-no-stale-dependency`). Read a primitive's docs before you use it; a guessed prop is `reuse-read-the-docs`.

**Icons come from the set, at native size.** An 18px icon scaled to 12px is `reuse-icon-set-native-size`. A glyph the set lacks gets drawn and added to the shared package, which is not a finding.

**Colour comes from a role token.** Read the role, not a hex: `var(--text-secondary)`, not `#737373`; not `text-blue-500` inside a component (`reuse-new-colour`). One token maps to light and dark; a hand-darkened second value is `reuse-second-palette`. Status colours keep one meaning, so a green "New" badge is `reuse-status-recolour`. When a design truly needs a new colour, add it once, in the theme file, named by role, then use that role everywhere (`reuse-colour-not-tokenised`).

**Type, space and shape come from the scale.** No 18px between 16 and 20 (`reuse-off-scale`). Radius, shadow and border width come from the shape tokens; a local `6px` beside the shared `8px` is `reuse-shape-token`. Transitions use the house duration and curve (`reuse-motion-token`). Reuse the focus ring rather than drawing a second one (`reuse-focus-ring`).

A value that appears a third time is a token nobody has named yet. Name it, then replace all three.

## Words

**Labels take Title Case.** Buttons, menu items, tabs, headings and setting names. Short articles, conjunctions and prepositions stay lowercase unless they come first. "Add to library" is `unslop-copy-title-case`.

**As few words as still say what happens.** "Start Download" on a download screen is just "Start" (`unslop-copy-fewest-words`). Cut the noun the screen already names, the redundant verb, the courtesy, the mechanism. Never cut the outcome: "Delete" does not become "OK".

**The button names the result.** "Send Invite", not "Submit". A destructive action names its object: "Delete Project", not "Confirm". One word per action across the product: Cancel, Close, Dismiss.

**Plain names, never ids.** `instagram_graph` in a select is `unslop-copy-display-names`. Spell out an abbreviation the user would not say aloud, then shorten it only if it repeats on the same screen.

**One word for one thing.** "Remove" or "Delete", never both. "Workspace" or "Project", never both (`unslop-copy-two-words-one-thing`). The button, the confirmation and the error use the same term.

**One line of description or none.** It adds what the label cannot, and never repeats the label (`unslop-copy-one-line-description`). Details go in a tooltip.

**Status matches the moment.** "Searching", then "Searched" (`unslop-copy-state-tense`). An error says what happened and what to do: "Card declined. Try another card", not "Something went wrong".

**Numbers stand alone when the context names the noun.** "12", not "12 items". Where it does not, the unit travels with the number. Dates inside a week are relative; beyond it, absolute. `03/04` is `unslop-copy-ambiguous-date`.

**No em dashes, no ellipses, no exclamation marks.** A comma or a full stop replaces the dash (`unslop-copy-no-em-dash`). "Loading" is the label; "Loading..." is `unslop-copy-no-ellipsis`. Sentence case for full sentences, Title Case for labels, no terminal full stop on a label.
