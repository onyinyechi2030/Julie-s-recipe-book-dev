# Julie's Recipe Book — Development 2.0 Visual Beta

This build preserves Firebase sync and all 321 recipes while introducing the first photographic recipe system.

## New in this build
- Photo-backed collection cards on My Kitchen.
- Lazy-loaded thumbnails on recipe cards and mobile recipe rows where a suitable image is available.
- Large hero photographs in the recipe reader.
- Responsive photo layouts for phone, tablet, and desktop.
- Graceful emoji/illustration fallback for recipes that do not yet have an appropriate photo.

Upload `index.html`, `README.md`, **and the entire `assets` folder** to the development repository.

## Image credits
Bundled images are resized/cropped derivatives for app display.
- pork-belly.webp — Arnold Gatilao, CC BY 2.0, Wikimedia Commons.
- kimchi-fried-rice.webp — JulieB.2, CC BY-SA 4.0, Wikimedia Commons.
- shrimp-fried-rice.webp — Jon Sullivan, public domain.
- wings.webp — Aerous, CC BY-SA 4.0, Wikimedia Commons.
- yogurt.webp — Jumbocombo0811, CC BY-SA 4.0, Wikimedia Commons.
- miso-soup.webp — Joditran, CC BY-SA 4.0, Wikimedia Commons.
- tikka.webp — Guddu1996, CC BY-SA 4.0, Wikimedia Commons.

The recipe reader displays the corresponding credit whenever one of these photographs is used.


## Gamma content expansion
Added vegetable-forward recipes, a honey-bean and legume collection, and a dedicated Nigerian collection including classic Nigerian meat pies, jollof rice, fried rice, efo riro, pepper soup, peppered gizzards, gizzard dodo, moi moi, akara, yam with vegetable egg sauce, chicken stew, suya-spiced chicken, and coconut rice.


## Cleanup 1
Audited and rebuilt 85 recipes across fried rice, pork belly, gizzards, Nigerian dishes, vegetable sides, and legumes. These recipes now have distinct ingredient sets, distinct instruction sets, structured quantities for serving scaling, and recipe-specific nutrition estimates. The seven current photographs are embedded directly in index.html so the app no longer depends on separate image asset paths.


## Full cleanup pass
The full 356-recipe library has been structurally rebuilt/audited for exact duplicate instructions, ingredient lists, nutrition profiles, serving-scaling data, and core detail fields. A small number of confusing near-duplicate titles were renamed while retaining their original recipe IDs for compatibility with saved favorites/notes.

## Culinary Audit Pass 2

This development build includes a second-stage culinary review across all 356 recipes.

Highlights:
- Rebuilt 52 soups, 27 curries, 27 stir-fries, 23 noodle/pasta dishes, 26 rice bowls, 62 mains, and 26 breakfast/egg recipes around dish-specific techniques.
- Differentiated previously redundant variations while preserving stable recipe IDs.
- Removed generic placeholder language and restored ingredients named in recipe titles.
- Zero exact duplicate full instruction sets.
- Zero exact duplicate full ingredient lists.
- Zero duplicate nutrition profiles.
- All core metadata fields, including chef tips, are populated.
- Nutrition remains approximate per-serving planning data, but calorie totals were checked for broad consistency with protein/carbohydrate/fat estimates.


## Visual Beta
Implements the Recipe Book 2.0 visual system across desktop and mobile while preserving the reviewed 356-recipe library and Firebase sync configuration. Recipes with a verified embedded food photo display it; other recipes use cuisine-colored illustrated covers rather than blank image boxes or misleading photographs.
\n\n## Healthy After-Dinner Desserts\nAdded the user-supplied gluten-free, no-added-sugar evening dessert collection. The library now contains 374 recipes. Closely overlapping existing entries were updated rather than duplicated, with recipe IDs preserved where possible for Firebase favorites/notes compatibility.\n

## Recipe-loading fix
The embedded recipe library in index.html is now always the authoritative built-in library. The app no longer fetches or prefers data/recipes.json, preventing an older leftover data folder in a GitHub repository from overriding the current 374 recipes. Firebase continues to sync only personal data.

## Runtime loading fix

This build contains the 374-recipe library directly in `index.html`.

It restores the missing `normalizeSearchText()` and `recipeMatchesQuery()` helpers that prevented the recipe rendering path from executing. The built-in library no longer depends on `data/recipes.json` or recipe-specific data files.

## Clean Visual Edition

Recipe-level photography is now intentionally limited to photographs that closely match the named dish. Broad category mappings that previously repeated the same pork-belly, wing, yogurt, soup, curry, or fried-rice image across many recipes have been removed.

Recipes without a verified specific photograph use a polished cuisine-colored graphic cover. This is intentional and prevents misleading imagery while keeping the interface visually distinctive. Collection-level imagery remains available where it functions as a collection banner rather than a claim about a specific recipe.


## Healthy Gluten-Free Breakfasts & Desserts

Added eight recipes using King Arthur Gluten-Free Measure for Measure Flour and a 1:1 monk-fruit/allulose sweetener:
- Blueberry Greek-Yogurt Muffins
- Fluffy Greek-Yogurt Pancakes
- Apple-Cinnamon Breakfast Cake
- Strawberry-Oat Breakfast Squares
- Chocolate Greek-Yogurt Brownies
- Cherry-Vanilla Cobbler
- Vanilla-Strawberry Snack Cake
- Apple-Cinnamon Oat Crisp

The library now contains 382 recipes. General allulose and gluten-free baking notes are included in each recipe's chef tips.


## Vegetables Made Delicious expansion

The cookbook now contains 408 recipes total, including a dedicated 38-recipe `Vegetable Side` collection surfaced on the home screen as **Vegetables Made Delicious**.

The original 12 vegetable recipes are retained. Twenty-six new recipes expand broccoli, kale/greens, spinach, Brussels sprouts, cabbage, carrots, zucchini, mushrooms, green beans, sweet potatoes, and mixed vegetables. The recipes emphasize browning, crisp texture, garlic-Parmesan, sesame, miso, gochujang, curry spices, and Greek-yogurt sauces rather than bland steamed vegetables.


## Firebase Auth compatibility fix

Firebase CDN imports are pinned to version 12.16.0. Firebase 12.17.0/12.17.1 introduced an Auth persistence regression that can make Google popup sign-in fail with `Database is closing/hidden` when the opener page becomes hidden while the popup has focus.

Do not update the Firebase CDN version until that upstream Auth regression is resolved.


## Full 408-recipe culinary audit

This build incorporates a full ingredient/instruction/post-recipe QA pass across all 408 recipes. It also repairs structured ingredient parsing for serving-size scaling and adds support for scaling ingredient ranges.

Firebase remains pinned to 12.16.0 to avoid the Google popup-auth regression seen in Firebase 12.17.x.


## Spice Mixes & Dry Rubs

Added a dedicated 15-blend searchable Spice Mix collection. The nine user-supplied blends are included, plus six complementary blends: Lemon-Garlic Herb Fish & Seafood, Smoky Barbecue, Steakhouse Peppercorn-Herb, Mediterranean Garlic-Herb, Suya-Inspired Yaji-Style Spice Base, and Ginger-Sesame Umami. Spice-mix cards display use/application information rather than meal nutrition. The cookbook now contains 423 built-in entries.


## Custom recipe quantity & batch-scaling fix

The Add Recipe workflow now parses custom ingredient quantities into the same structured format used by built-in recipes. It supports integers, decimals, common fractions, mixed fractions, Unicode fractions, and quantity ranges. Common unit abbreviations are normalized to cookbook units.

Previously saved custom recipes whose ingredients were stored as unstructured text are automatically upgraded when loaded, including recipes synced from Firebase. Spice Mix recipes can therefore use the Batch multiplier correctly.

Ingredient display also standardizes common units and pluralization after scaling.

Spice Mix / Dry Rub / Seasoning Blend category variants are normalized to `Spice Mix` and use a 1-batch baseline automatically, including previously saved custom spice mixes.


## Custom spice-mix batch multiplier & Best For fix

- Custom spice mixes now use a true 1× base batch in the recipe reader regardless of the value previously stored in `servings`.
- Spice category detection accepts category names containing `Spice Mix`, `Dry Rub`, or `Seasoning Blend`, including older user-entered variants.
- Previously saved custom spice mixes are normalized on load.
- Add/Edit Recipe now includes dedicated `Best for` and `Application / use rate` fields.
- Spice cards and recipe details read `Best for` from the correct `bestFor` field.


## Prominent Spice Mix Details & Kitchen Converter

The Add/Edit Recipe screen now presents `Best for` and `Application / use rate` inside a visually distinct **Spice Mix Details** panel.

A new **Kitchen Converter** top-level tab supports:
- exact volume conversions: teaspoons, tablespoons, cups, fluid ounces, milliliters, liters
- exact weight conversions: ounces, pounds, grams, kilograms
- ingredient-aware weight ↔ volume conversions using grams-per-cup density presets or a custom density

The converter deliberately distinguishes fluid ounces from ounces by weight. Weight-to-volume results are estimates and depend on ingredient density.


## Recipe sharing

The full recipe view now includes **Share recipe**. On devices/browsers supporting the Web Share API (including most modern mobile browsers), it opens the native share sheet so a recipe can be sent by text/iMessage, email, WhatsApp, and other installed apps.

The shared text includes the recipe name, description, scaled ingredient quantities, instructions, and key spice-mix guidance. The currently selected servings/batch multiplier is respected. If native sharing is unavailable, the app copies the formatted recipe to the clipboard instead.


## Search stability & personal-recipe classification fix

Search now uses a strong-match-first model:
- title, description, dish type, meal, cuisine/region, protein/main ingredient, tags and Best For are searched first;
- ingredient-only matching is used only when no strong recipe matches exist;
- instructions, pairings, substitutions and chef tips no longer create unrelated search results.

Filter selections are preserved when Firebase sync repopulates the dropdown options, fixing the apparent jump from a narrowed result set back to the full library.

Add/Edit Recipe now includes filterable classification fields for:
- Dish type / category
- Meal
- Cuisine / region
- Protein / main ingredient
- Labels/tags

The form offers the built-in cookbook's existing values through datalist suggestions while still allowing a custom value.

Search relevance was further tightened so descriptions are part of the fallback tier rather than the primary identity tier; e.g. a recipe that merely says 'serve with rice' will not outrank actual rice recipes.


## Cooked / Tried recipe history

Each recipe now has a Cooking History panel with:
- Mark as Cooked / Cooked Again
- cook count
- last-cooked date
- Undo last entry

Recipe cards display a `✓ Cooked` badge and cook count when applicable. Browse Recipes includes a dedicated `Cooked Recipes` filter that can be combined with search, My Recipes, dish type, meal, region, and protein filters.

Cooked history is stored locally and included in the Firebase sync snapshot as `cookedHistory`, so it follows the signed-in user across devices.

Firebase state normalization and initial device/cloud merging now include `cookedHistory`; the greater cook count and the most recent last-cooked timestamp are preserved when two devices are merged.
