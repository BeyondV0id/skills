# Buttons

Two buttons. Primary for the one action that moves the page forward, secondary for everything else. Pick by intent, never by size. A screen has one primary; a group has at most one.

Both are drawn on a 4px grid, use Geist Medium, and sit on the same radius family: 14px for the primary, 10px for the secondary.

## Primary

56px tall, 24px side padding, 14px radius, 16px label, 20px leading icon with an 8px gap. Fill `#296FF0`, label `#FFFFFF`.

The finish is four layers: a white hairline inside the edge, a soft white inner glow, a black drop shadow, and a 1px blue ring outside the box.

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  height: 56px;
  padding: 0 24px;
  border: 0;
  border-radius: 14px;
  background: #296ff0;
  color: #fff;
  font: 500 16px/1 Geist, system-ui, sans-serif;
  box-shadow:
    0 3px 6px rgba(0, 0, 0, 0.20),
    0 0 0 1px #296ff0,
    inset 0 0 0 1px rgba(255, 255, 255, 0.40),
    inset 0 0 6px 2px rgba(255, 255, 255, 0.24);
}

.btn-primary:hover  { background: #1f63dc; }
.btn-primary:active { background: #1a57c4; }
.btn-primary:disabled {
  background: #a9c3f7;
  box-shadow: none;
  cursor: not-allowed;
}
```

White on `#296FF0` measures 4.55:1, which clears 4.5:1 by a hair. Do not lighten the fill without re-measuring, or the label fails.

## Secondary

30px tall, 12px side padding, 10px radius, 14px label, 16px leading icon with a 6px gap. Label `#1A1A1A`.

It has no border. The edge is a 1px `#ECECEC` ring in the shadow stack, over a vertical gradient from `#FFFFFF` to `#F7F7F7`, with a 1px/2px shadow at 8%.

```css
.btn-secondary {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  height: 30px;
  padding: 0 12px;
  border: 0;
  border-radius: 10px;
  background: linear-gradient(180deg, #ffffff 0%, #f7f7f7 100%);
  color: #1a1a1a;
  font: 500 14px/1 Geist, system-ui, sans-serif;
  box-shadow:
    0 1px 2px rgba(40, 40, 40, 0.08),
    0 0 0 1px #ececec;
  cursor: pointer;
}

.btn-secondary:hover  { background: linear-gradient(180deg, #fbfbfb 0%, #f1f1f1 100%); }
.btn-secondary:active {
  background: #f2f2f2;
  box-shadow: 0 0 0 1px #e6e6e6, inset 0 1px 2px rgba(0, 0, 0, 0.06);
}

/* The drawn height is 30px; the touch target is 44px. */
.btn-secondary::after {
  content: "";
  position: absolute;
  inset: -7px;
}
```

## States for both

Focus is an outline, not another shadow, so it never fights the finish: `outline: 2px solid #296FF0; outline-offset: 2px;` on `:focus-visible` only. A button with no visible focus ring is a defect.

Hover is a change of fill only, never a lift, a scale or a new shadow. Pressed is darker still, applied on pointer down.

Loading keeps the button's width. Hide the label with `color: transparent`, overlay a 16px spinner in the primary and a 14px spinner in the secondary, set `aria-busy="true"`, and ignore repeat clicks. Restoring the label on failure is part of the button, not the form.

Disabled drops the shadow and the ring and changes the fill; it never just fades to 40% opacity, which makes the label unreadable.

Dark mode keeps the primary fill at `#296FF0`, so the white label still passes. Lower the inner white stroke to 28%. The secondary becomes a `#202020` to `#1A1A1A` gradient, ring `#2E2E2E`, label `#F2F2F2`.

## Choosing between them

Primary is the sentence's verb: Save, Invite, Publish, Start Free Trial. Secondary is the alternative beside it: Cancel, Preview, Skip. In a dialog footer, the primary sits last in the DOM and last visually.

Never two filled blue buttons in one row (`layout-two-actions`). Never a secondary where the primary belongs, which is the common failure: a form whose submit is grey and whose Cancel is blue.

A destructive action uses the red fill, not the blue one, and the red is never the page's primary action except on a confirmation screen.

## Sizes and icons

The primary has one size; do not add a compact variant, which is a secondary button. The secondary has one size. Icons are leading, 20px on primary and 16px on secondary, drawn at 1.5px stroke, and the icon carries no meaning the label does not (`unslop-copy-fewest-words`).

On touch, both keep their drawn height and expand the hit area to 44px, as the secondary does above. A 30px button with a 30px hit area is a miss on a phone.

## Labels

Title Case, verb first, object after: "Add Team Member", "Send Invite". The button names the result, not the mechanism, so "Submit" and "Confirm" are findings. One term per action across the product: Cancel, Close, Dismiss. All of this is the Words section of `design`; the button just has to obey it.
