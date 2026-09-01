# Version A: Poetry Blank Space

Generate one stacked image: hand-drawn scene on top, equal blank paper below, poem in the blank.

Fill `[ASPECT]` with the source `W:H` and `[STACKED ASPECT]` with `W:(2H)`. 4:3 → 4:6. 16:9 → 16:18. Do not convert those to 2:3 or 8:9.

Write the poem first from [shared-clauses.md](shared-clauses.md), then generate.

## Image Prompt

```text
Create one image at aspect ratio [STACKED ASPECT], made of two equal panels stacked vertically. Each panel is [ASPECT], the same as the input photograph. If the photo is 4:3, this canvas is 4:6. If the photo is 16:9, this canvas is 16:18. The two halves have the same width and the same height. Do not output 1:1. Do not crop, letterbox, or squeeze.

Use the input photo as the composition reference for the top panel only.

The top [ASPECT] panel is a minimal hand-drawn paper collage of the input image. Keep the main subject, subject relationships, pose, placement, and essential composition. Include every scene element: [SCENE ELEMENTS]. [PRESERVE: keep the observed protected subject or object colors, their relative lightness, and their separation as distinct color blocks.]

The bottom [ASPECT] panel is equal-height off-white fibrous paper with sparse irregular paper-cut marks only at the edges. Reserve a clean quiet center for typography.

Preserve only the most recognizable shapes. Keep people and animals as simplified silhouettes. Flat, sparse, poetic, magazine-interior collage.

If rendering the poem, use exactly: [POEM]. Small quiet serif type in the bottom-panel blank. Otherwise leave the blank empty and generate no letters.

Avoid photographic realism, high detail, complex lighting, precise perspective, 3D rendering, anime, logos, and watermarks.
```

## Codex image2

Generate once at `[STACKED ASPECT]` with the user photo as reference. If type is misspelled, regenerate with no letters and return `[POEM]` in the chat.
