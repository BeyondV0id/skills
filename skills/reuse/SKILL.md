---
name: reuse
description: Reaches for the project's own components, then a maintained library, then a native feature, before writing new code.
---

# Reuse

This skill sets the order for building anything new. The project's own parts come first, then a maintained library or a platform feature. Custom code comes last.

Adapted from raphaelsalaja/skills (MIT, (c) 2026 Raphael Salaja).

## A duplicate is a finding

A new component, style or icon that duplicates one the project already has is a finding. Adding a primitive to the shared package and then using it is not. A project with no shared package is judged on the libraries it already depends on.

## The project's parts come first

Search the shared component package, the icon set and the tokens before writing UI. Name what you found. A raw `<input>` beside the project's `Input` is `reuse-house-component-first`.

## Shipped components stay as shipped

Use a component's variants and `data-*` attributes. Restyling it with a local `className` is `reuse-no-local-restyle`.

## One style per kind of thing

Keep one menu, one table and one dialog shell. A second dropdown style is `reuse-one-standard`.

## Fix it once, in the primitive

When a fix applies to every instance, make it inside the shared component. Patching five call sites is `reuse-fix-in-the-primitive`. Then search for every sibling, remove its local fix and list the files. Fixing only the cited line is `reuse-sweep-siblings`.

## Then a library or the platform

When the project has nothing, use a maintained library or a platform feature before custom code. `Intl` formats dates and numbers. The native context menu handles right-click. A hand-written formatter is `reuse-library-before-custom`.

Check that a library is maintained. When it is not, port the pattern instead of installing it. That is `reuse-no-stale-dependency`.

## Read the docs before the props

Read a primitive's documentation before using it, and use its current APIs. A guessed prop is `reuse-read-the-docs`.

## Icons from the set, at native size

Use the project's icon set at the size it was drawn for. A generated SVG, or an `18px` icon scaled to `12px`, is `reuse-icon-set-native-size`. A glyph the set lacks, drawn at native size and added to the shared icon package or folder, is not a finding.

## Report

One finding per root cause:

```
file:line - [rule-id] what is wrong
```

Then a `Rule | Count | Severity` summary. Never `Approve` a file you did not read. Mark every check you could not run as `Not verified`.
