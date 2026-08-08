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
