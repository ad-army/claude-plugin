---
name: recut
description:
  'Turn existing footage into a shorter captioned cut with Ad Army: measure the
  source, pick complete spoken phrases, retime captions, preview and render. Use
  when the user asks to "cut this video down", "make a 15/30-second version",
  "recut this ad", "add captions or subtitles to this video", "reframe this for
  9:16" or "repurpose this clip" and Ad Army is connected. NOT for generating
  new footage (use product-ad) or building a video from a script (use
  explainer).'
---

# Captioned recut with Ad Army

Follow the `ad-army` skill throughout, above all its spending and measurement
rules. The steps come from the server's `captioned-recut` recipe.

1. Call `get_recipe` with `recipeId: "captioned-recut"` and follow its inputs,
   steps and review criteria.
2. Get the source video as an `assetId`: find it with `search_assets` or on the
   user's Playground, or bring it in with `import_asset` or an upload.
3. Measure before planning. Call `probe_media` (free) for exact duration, frame
   rate and audio. Transcription and video analysis cost credits, so include
   them in the estimate you show the user before calling them.
4. Never cut through a spoken word, and never pad a short source to reach a
   target length. Tell the user if their target does not fit the material.
5. Check the cut with `preview_composition` (free) before `estimate_composition`
   and `render_composition`. A still preview does not prove audio sync, so say
   what playback the user should still check.
6. Hand back the rendered video on a Playground, the source-to-output timing
   notes, and settled credits.
