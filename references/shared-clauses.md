# Shared Clauses

Use these with any version. Do not paste them into an image prompt unless that version needs them.

## Poem Prompt

Use separately from image generation for Version A and Version C. First fill `[SCENE ELEMENTS]` with the same `Scene:` list used for the image prompt. Output only the poem, never embed it in the image prompt.

Write from the picture's concrete elements (sea, rock, two people, smoke, fields, and so on). A line like `Smoke writes the wind, / fields keep the quiet.` is the pattern: the nouns come from the photo, the syntax stays poetic. Do not write a mood-only line that could fit any picture, such as `The afternoon keeps its distance.` Do not write a caption that merely lists objects.

```text
Write one short original English poem from these scene elements: [SCENE ELEMENTS].
Use one to three lines and about six to sixteen words. Let one or two of those elements appear as quiet nouns or verbs. Keep the language simple and poetic. Avoid motivational slogans, quotation marks, cliches, and lines that name no element from the photo. Output only the poem.
```

## When Clothing Or Object Colors Drift

Append this block after the preservation clause. Name the real colors rather than using generic words such as "original colors."

```text
Color-lock requirement: preserve [SUBJECT]'s [GARMENT OR OBJECT] as [COLOR], and [SECOND GARMENT OR OBJECT] as [COLOR]. These colors are identity-defining visual facts. Stylize their shape and texture only; do not change the hue family, swap the colors, desaturate them into the background palette, or invent a different outfit or object color.
```

## Size

Use the source photo's own ratio `W:H`. Do not snap to a preset list. Double the height for A and C; keep the same width.

- Version B: `[ASPECT]` = `W:H` (4:3 stays 4:3, 16:9 stays 16:9).
- Version A and Version C: `[STACKED ASPECT]` = `W:(2H)`. Two equal halves. 4:3 → 4:6; 16:9 → 16:18; 3:2 → 3:4.

Never default to 1:1. Never rewrite 4:6 as 2:3 or 16:18 as 8:9 in the prompt — keep the doubled-height form so the two halves stay obviously equal to the source.

## Make It More Minimal

Append this block when the result looks like a detailed painting, a photo filter, or a tidy two-panel poster.

```text
Reduce visual information further: use no more than six broad torn-paper shapes, one simple contour per major subject, no facial features, no realistic shading, no straight panel divider, and at least forty percent quiet paper. The scene must look cut from paper, not photographed.
```

## Too Photographic Or Too Neat

Append this block when likeness, perspective, or a straight seam survives.

```text
Increase abstraction: replace photographic surfaces with flat irregular paper shards; remove facial likeness and small architecture; overlap the lower torn-paper field into the scene; delete any straight horizontal split, white gutter, or rectangular caption box.
```
