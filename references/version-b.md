# Version B: Pure Hand-Drawn

Generate one collage at the source ratio. No poem. No letters.

Fill `[ASPECT]` with the source `W:H` (4:3 stays 4:3, 16:9 stays 16:9).

## Image Prompt

```text
Transform the input image into a highly abstracted paper-cut collage at aspect ratio [ASPECT], matching the photograph's ratio only — not its photographic detail. Do not output 1:1. Do not crop, letterbox, or squeeze. Use the full page. No typography.

Keep the recognizable placement of [SCENE ELEMENTS], not a tracing of the photo. Reduce the whole scene to about five to eight large irregular torn-paper shapes. People and animals are featureless silhouettes: no faces, hair strands, jewelry, or garment folds. Landmarks and landscape become flat shards, not realistic surfaces. [PRESERVE: keep protected clothing or object hues as distinct flat color blocks.]

Off-white fibrous paper, restrained low-saturation palette, rough torn edges, light crayon or dry-brush marks, generous blank paper. Graphic and sparse, not a photo filter.

Avoid photographic realism, realistic watercolor, oil painting, high detail, complex lighting, precise perspective, 3D, anime, captions, letters, words, logos, and watermarks.
```

## Codex image2

Generate once at `[ASPECT]` with the user photo as a weak composition reference. If it still looks like a photograph, regenerate once with the "too photographic" clause.
