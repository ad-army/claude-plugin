---
name: explainer
description:
  'Build a short narrated explainer video with Ad Army: a grounded script, a
  measured voiceover, matching illustrations and an assembled, captioned video.
  Use when the user asks to "make an explainer video", "turn this article or
  these notes into a narrated video", "make a how-it-works video" or "add a
  voiceover to illustrations" and Ad Army is connected. NOT for product ads (use
  product-ad) or shortening existing footage (use recut).'
---

# Narrated explainer with Ad Army

Follow the `ad-army` skill throughout, above all its spending rules. The steps
come from the server's `narrated-explainer` recipe.

1. Call `get_recipe` with `recipeId: "narrated-explainer"` and follow its
   inputs, steps and review criteria.
2. Write the script only from facts the user supplied or the workspace holds. Do
   not invent evidence, quotations or product claims; ask when a claim is
   missing.
3. Choose the voice with `list_voices`, preferring a saved Brand Kit voice. Get
   the voiceover price from `estimate_voiceover`, and include it with the image
   and render estimates in one total for the user to approve.
4. Time the visuals to the measured narration (`probe_media` on the voiceover
   asset), not to the target duration.
5. Hand back the Playground with the script, beat plan, images, voiceover and
   finished video, plus settled credits and anything still to review.
