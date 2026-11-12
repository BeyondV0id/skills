---
name: viewports
description: Renders a page at every width, each breakpoint edge, a short landscape phone and 200% text, then reports what overflows, clips or hides.
---

# Viewports

Render one page at a fixed set of widths and heights. Measure each render for sideways scroll, clipped text, small targets and hover-only controls.

Adapted from raphaelsalaja/skills (MIT, (c) 2026 Raphael Salaja).

## Every width rendered, none inferred

The widths are exact: 320, 375, 768, 1024 and 1440, plus 1px either side of each project breakpoint. A width reasoned from the media queries is a finding. Run it after any layout change and whenever the user names a phone or a width.

## 1. Read the breakpoints

Read the breakpoints from the CSS, the Tailwind config or the tokens. Add 1px below and 1px above each one to the fixed widths. A sweep that skips the edges of a breakpoint is `viewports-cross-each-breakpoint`.

## 2. Render each width

Set the viewport through device emulation at each width. Use 320x568, 375x812, 768x1024, 1024x768 and 1440x900. Breakpoint edges render 800px tall. Emulate touch at every width under 1024. Take a full-page screenshot of each. A layout judged from the code is `viewports-render-every-width`.

## 3. Measure each render

Run `overflow.js` in the page through the browser's evaluate call at each width. Treat each result as a candidate until a crop of that width shows it.

The page never scrolls sideways, though a box may scroll inside itself. A 40px sideways scroll at 320 is `viewports-no-sideways-scroll`.

Text is never cut by its box without an ellipsis or a clamp. A button label cut in half at 375 is `viewports-no-clipped-text`. A target under 24px is small; flag it.

## 4. Tap at touch widths

Tap through the page with touch emulated. Row actions, copy buttons and menus that appear on hover need another way to appear. A delete button that shows only on row hover is `viewports-no-hover-only-controls`.

## 5. Shorten the height

Render 812x375, a phone held sideways. Open each dialog, sheet and menu at that size. Content scrolls inside the overlay and its actions stay reachable. A dialog whose `Save` sits below the screen with no scroll is `viewports-short-heights`.

## 6. Double the text

At 1024 wide, set the root font size to 200% and render again. Text wraps and its boxes grow, with nothing overlapping. Labels overlapping their icons at 200% is `viewports-text-zoom`. A layout that cannot grow because sizes are set in `px` gets the same id.

## 7. Report by width

Return one screenshot per width with the overlay numbers, then the findings in the same order. A finding with no width named is `viewports-name-the-width`.

## Report

One finding per root cause, naming the width:

```
file:line - [rule-id] at 375, what is wrong (measured values)
```

Then a `Rule | Count | Severity` summary. Mark any width you could not render as `Not verified`.
