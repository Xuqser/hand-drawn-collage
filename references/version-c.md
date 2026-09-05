# Version C: Full-Page Collage With Poem

Generate **one continuous vertical collage** at `W:2H`, not two framed photos glued together.

Fill `[ASPECT]` with the source `W:H` and `[STACKED ASPECT]` with `W:(2H)`. 4:3 → 4:6. 16:9 → 16:18. Do not convert those to 2:3 or 8:9.

Write the poem first from [shared-clauses.md](shared-clauses.md), then generate.

The canvas is tall so the lower field has room for paper and type. Do **not** draw a straight seam, white gutter, or second rectangular panel. Scene and paper must overlap through torn shards, like a zine page. Do not keep the original photograph in the finished image.

## Image Prompt

```text
Create one continuous vertical paper-collage page at aspect ratio [STACKED ASPECT] (if the photo is 4:3, this page is 4:6; if 16:9, 16:18). Do not output 1:1. Do not crop or squeeze.

This is a single handmade zine page, not two stacked photographs and not a caption under a picture. Do not draw a straight horizontal divider, white gap, or neat rectangular text box. Do not embed the original photograph.

Upper field: a highly abstracted paper-cut interpretation of the input photo. Reduce the scene to about five to eight large irregular torn-paper color blocks. Keep only the most recognizable placement of [SCENE ELEMENTS]. People and animals are featureless silhouettes — no facial features, hair strands, jewelry, fabric folds, or photographic likeness. Landmarks become two or three flat shards (for example white triangles for sails), not a detailed building. Water, sky, and ground are broad torn sheets, not realistic surfaces. [PRESERVE: keep protected clothing or object hues as distinct flat color blocks, without rendering their material.]

Lower field: roughly the bottom half of the page is layered cream, tan, and muted color shards with ragged torn edges that overlap the scene above, so the picture melts into paper. Place one large irregular off-white torn piece in that field for type. Leave generous quiet paper.

If rendering the poem, use exactly: [POEM]. Small quiet serif type on that torn shard only. No quotation marks. Otherwise leave the shard empty and generate no letters.

The result should feel sparse, graphic, and slightly unfinished — independent-magazine collage — not a photo filter, not a tidy two-panel poster.

Avoid photographic realism, neat alignment, straight seams, captions under a frame, high detail, complex lighting, precise perspective, 3D, anime, logos, and watermarks.
```

## Codex image2

Generate once at `[STACKED ASPECT]` with the user photo as a **weak** composition reference (low transformation resistance). If the result looks like a photograph with torn edges, has a straight split, or keeps facial likeness, regenerate once with the "too photographic" clause in [shared-clauses.md](shared-clauses.md).
