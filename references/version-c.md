# Version C: Photo Pair

Stack two equal `W:H` panels into `W:2H`. Top = the unaltered original photo. Bottom = irregular collage on cream paper.

Write the poem first from [shared-clauses.md](shared-clauses.md). Fill `[ASPECT]` = source `W:H`. `[STACKED ASPECT]` = `W:(2H)` (4:3 → 4:6, 16:9 → 16:18).

Every `Scene:` element must appear as its own irregular paper-cut shape. Do not zoom into people and drop the landscape.

## Image Prompt (bottom panel only)

```text
Create a landscape editorial collage panel on an off-white fibrous paper background.

Output at aspect ratio [ASPECT], matching the input photograph. Do not output 1:1. Do not output the stacked [STACKED ASPECT] canvas in this step. Do not crop, letterbox, or squeeze. This is the bottom panel only.

Do not paint a full-bleed picture and do not crop into a close-up. Distill the whole scene into five to eight large irregular torn-paper shards on cream paper, not a miniature photograph. People are featureless silhouettes. Landmarks are two or three flat shapes. Keep relative placement of [SCENE ELEMENTS]. Do not omit background landmarks to enlarge the people.

Let the shapes sit on the paper with rough torn edges so they melt into the base color. The cluster must be irregular and open, not a circle, oval, stamp, or vignette.

Keep poses and essential relationships. [PRESERVE: keep the observed protected subject or object colors as distinct color blocks.]

Restrained low-saturation palette, calm silhouettes, about five to eight major shapes. Leave empty paper beside the cluster.

If rendering the poem, use exactly: [POEM]. Small quiet serif type in the empty paper, beside the cluster, not a title banner. Otherwise generate no letters.

Avoid photographic realism, high detail, complex lighting, precise perspective, 3D rendering, anime, logos, and watermarks.
```

## When The Collage Zooms Or Becomes A Round Stamp

```text
Keep every listed scene element visible as a separate irregular torn-paper shape. Do not zoom or crop. Restore omitted landscape. Use an open, asymmetric collage, not a circular, oval, or stamp-shaped vignette.
```

## Codex image2

1. Generate the bottom panel only, at `[ASPECT]`, with the user photo as reference.
2. Place the original photograph on top, unaltered, same width and height as the bottom panel.
3. Concatenate them vertically into `[STACKED ASPECT]`. Do not send the original through image2 again.
4. If concat is unavailable, return both images separately rather than a redrawn stack.
