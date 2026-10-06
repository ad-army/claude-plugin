---
name: product-ad
description:
  'Plan and produce product creative in Ad Army from a product image: a set of
  deliberately different product shots, the same product placed in several
  worlds joined by transitions, or a 15–25 second cinematic character-led
  vertical video ad with music. Use when the user asks to "make an ad for this
  product", "turn this product photo into a video ad", "create product
  variations", "put my product in different scenes", "make a cinematic product
  ad" or "make a launch video for this product" and Ad Army is connected. NOT
  for cutting existing footage down (use recut) or narrated explainers (use
  explainer).'
---

# Product creative with Ad Army

Follow the `ad-army` skill throughout, above all its spending rules. This skill
only chooses the recipe and gathers the brief. The recipe itself comes from the
server, so it is always current.

## Choose the recipe

| The user wants                                                         | Recipe                           |
| ---------------------------------------------------------------------- | -------------------------------- |
| Several distinct stills of one product, same identity and brand        | `product-image-variations`       |
| One product in two or more environments, connected by transition clips | `one-product-n-worlds`           |
| A short vertical story with a character, acts, music and an end card   | `cinematic-character-product-ad` |

If the request fits none of them, say so and plan from the individual tools
instead of forcing a recipe.

## Run it

1. Call `get_recipe` with the chosen `recipeId`. Its `inputs`, `steps`, `review`
   criteria and limitations are the plan. Its `access` object shows missing
   permissions; if any are missing, give the user `reconnectUrl` from
   `get_workspace`.
2. Gather the required inputs before estimating. Every recipe needs a readable
   product image as an `assetId`: use one already in the workspace
   (`search_assets`), import it, or ask for an upload. Ask about anything the
   recipe marks required and the user has not given. Read `get_brand_kit` rather
   than asking for brand rules the workspace already holds.
3. Estimate the whole recipe, including retries, and get approval for one total
   before the first paid call. Budget is per workflow, not per step.
4. Save the locked requirements and plan to a Playground before generating, then
   review each output against the recipe's criteria before moving on. Keep a
   flawed output on the board with a note rather than silently regenerating it.
5. Hand back the Playground link, asset IDs, settled credits and any review the
   user still needs to do.
