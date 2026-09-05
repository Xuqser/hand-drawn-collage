---
name: hand-drawn-collage
description: Transform a user-supplied photo into a minimal hand-drawn paper-collage illustration in version A (original-plus-collage), B (pure collage), or C (full-page collage with poem). Preserve scene elements, clothing and object colors, and the source aspect ratio. Use when the user asks for photo-to-illustration, editorial paper collage, 原图对照, 纯手绘, or 整页撕纸拼贴. Generate with the host image model (image2). Never draw SVG or code illustrations.
---

# Hand-Drawn Collage

Generate a tactile paper-collage page from a supplied photo using Codex image generation. Read the scene first. Compile a photo-specific prompt. Generate with the user's photo as the reference image.

## Decision Priority

1. Identify Version A, B, or C. If unspecified, ask; do not mix them.
2. Keep the scene identifiable: landscape and foreground, not a cropped close-up of people.
3. Lock protected clothing and object colors from this photo only.
4. Keep the source ratio: B = `W:H`; A = `W:2H` as two equal `W:H` panels; C = `W:2H` as one continuous page (4:3 → 4:6, 16:9 → 16:18). Never default to 1:1.
5. Prefer irregular torn-paper shapes over a circular stamp or a traced miniature photo. Version C is one continuous page, not two framed panels.
6. Abstract first: featureless silhouettes, a handful of large shards, no photographic likeness on generated collage. Size still follows `W:H` / `W:2H`.
7. For A and C, write the poem from the same scene elements; do not use a mood-only line that could fit any picture.
8. Call a real image-generation tool. Never SVG, canvas, HTML-to-image, or `node_repl` drawing.

## Runtime

This skill is built for Codex with image2.

1. Inspect the photo and fill the Scene Card.
2. Read the matching version file and compile the prompt (fill `[SCENE ELEMENTS]`, `[PRESERVE]`, `[ASPECT]`, `[STACKED ASPECT]`).
3. Write the A/C poem from the Scene Card before generating, so wording is fixed.
4. Generate with the supplied photo as the reference image, requesting the exact ratio in the version file.
5. If the result looks photographic, has a straight panel split, goes circular, drops a scene element, or uses the wrong ratio, regenerate once with the matching repair clause.
6. Return the image plus a short Chinese 创作说明. Do not show the full prompt unless the user asks.

If the host has no image model, return copy-ready prompts and stop. Do not fake an image.

## Privacy

Treat a supplied photo plus a request to make A/B/C as consent to generate. Send only the compiled prompt and the required reference image to the image service. Do not browse, search, save, commit, or upload the source elsewhere.

## Scene Card

Record from this photo only:

- **Scene:** 3–7 elements that make this place recognizable (landscape and foreground).
- **Preserve:** clothing, accessories, or named objects whose hue must survive.
- **Size:** source `W:H`; B stays `W:H`; A is two stacked `W:H` panels (`W:2H`); C is one continuous `W:2H` page.
- **Gesture:** one main spatial relationship (near/far, lean, horizon, facing).

Never copy colors or objects from examples.

Version files:

- A: [references/version-a.md](references/version-a.md)
- B: [references/version-b.md](references/version-b.md)
- C: [references/version-c.md](references/version-c.md)

Shared poem, size, and repair patches: [references/shared-clauses.md](references/shared-clauses.md).

## Variants

Triggers: 「原图对照、上半原图、上下拼接、纸底融合、不铺满」→ A. 「纯手绘、不带文字」→ B. 「整页撕纸、诗句留白、不保留原图」→ C.

### A — Photo Pair

Do **not** redraw the original photo.

1. Generate only the bottom panel at `W:H` (cream paper, irregular collage cluster, poem in empty paper).
2. Stack the **unaltered original** above that panel so both halves are the same `W:H` and the sheet is `W:2H`. Join real pixels (image concat / layout). Do not ask image2 to invent the top photo.
3. If you cannot concat, return the original and the bottom panel as two images plus the stack instruction. Do not deliver a regenerated fake original.

### B — Pure Hand-Drawn

Generate **one** image at `W:H`. Full-frame collage. No poem, no letters.

### C — Full-Page Collage With Poem

Generate **one** continuous page at `W:2H` (4:3 → 4:6, 16:9 → 16:18). Upper field = abstracted collage; lower field = overlapping torn paper for the poem. Do not keep the original photograph. Do not draw two stacked frames or a white gutter. Place the already-written poem as small quiet serif type on an irregular shard. If letters come out wrong, regenerate with no type and print the poem in the 创作说明.

## Color Preservation

Allow the background to use a restrained collage palette. Keep protected garments and objects as distinct, recognizable color blocks. Do not write only `preserve colors`.

## Style

Limited palette, broad irregular blocks, flat silhouettes, paper texture. No cinematic, realistic, painterly, highly detailed, or photographic language.

## Output

Return in this order:

1. The generated image(s).
2. Two to four Chinese sentences: version, what was kept, what was omitted, `Size:`.
3. For A and C, the poem as plain text if it is not already correct in the image.
4. The full prompt only if the user asks.

Use Chinese with the user unless they ask otherwise. Generation prompts stay English when that works better for image2.
