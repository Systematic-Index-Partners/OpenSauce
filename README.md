<img width="1280" height="320" alt="opensauce_banner" src="assets/opensauce_banner.png" />

**A precision recipe repository for New York-style pizza.** Every attempt logged. Every variable tracked. Every iteration building toward the perfect pie.

Recipes are stored as structured JSON files across three components (dough, sauce, and cheese) so every batch can be reproduced exactly, compared across attempts, and improved deliberately. A companion GitHub Pages site renders the full catalog with photos.

---

## Repository Structure

```
OpenSauce/
├── recipes/
│   └── YYYY-MM-DD_short-name/
│       ├── recipe.json        ← the full spec
│       └── photo.jpg          ← result photo (required)
├── schema/
│   └── recipe.schema.json     ← JSON schema for validation
├── index.html                 ← GitHub Pages catalog site
└── README.md
```

Each attempt lives in its own folder named by date and a short slug, e.g. `2024-03-15_high-hydration-poolish`.

---

## The Recipe Schema

Every `recipe.json` follows the same three-component structure. Below is a full annotated example.

```json
{
  "meta": {
    "id": "2024-03-15_high-hydration-poolish",
    "date": "2024-03-15",
    "author": "your-github-username",
    "title": "High Hydration Poolish",
    "style": "New York",
    "notes": "Third attempt at 70% hydration. Switched to bromated bread flour. Baked on steel."
  },

  "dough": {
    "flour": {
      "type": "King Arthur Bread Flour",
      "protein_percent": 12.7,
      "bromated": true,
      "grams": 500
    },
    "water": {
      "grams": 350,
      "hydration_percent": 70,
      "temperature_c": 20
    },
    "salt": {
      "grams": 12,
      "percent_of_flour": 2.4
    },
    "yeast": {
      "type": "instant dry",
      "grams": 1.5,
      "percent_of_flour": 0.3
    },
    "oil": {
      "type": "olive",
      "grams": 10
    },
    "sugar": {
      "grams": 5
    },
    "preferment": {
      "type": "poolish",
      "flour_grams": 100,
      "water_grams": 100,
      "yeast_grams": 0.1,
      "ferment_hours": 16,
      "ferment_temp_c": 20
    },
    "process": {
      "mix_method": "hand",
      "autolyse_minutes": 20,
      "bulk_ferment_hours": 2,
      "bulk_ferment_temp_c": 22,
      "cold_proof_hours": 48,
      "cold_proof_temp_c": 4,
      "ball_weight_grams": 280,
      "stretch_and_fold_sets": 3
    }
  },

  "sauce": {
    "tomatoes": {
      "brand": "Bianco DiNapoli",
      "type": "whole peeled",
      "grams": 400,
      "drained": true
    },
    "salt": {
      "grams": 6,
      "type": "kosher"
    },
    "garlic": {
      "cloves": 2,
      "method": "raw grated"
    },
    "olive_oil_ml": 15,
    "oregano_dry_grams": 1,
    "red_pepper_flakes_grams": 0.5,
    "cooked": false,
    "process_method": "hand-crushed",
    "moisture_content": "medium, drained 15 min in strainer",
    "grams_per_pizza": 90
  },

  "cheese": {
    "mozzarella": {
      "type": "low moisture whole milk",
      "brand": "Polly-O",
      "moisture_percent": 45,
      "grated": true,
      "grams_per_pizza": 180
    },
    "pecorino_romano": {
      "grams_per_pizza": 15,
      "application": "post-bake"
    },
    "application_order": "cheese under sauce",
    "cheese_to_edge_cm": 1.5
  },

  "bake": {
    "oven": "home electric",
    "surface": "baking steel",
    "preheat_minutes": 60,
    "temp_c": 290,
    "position": "top rack",
    "time_minutes": 6,
    "broil_finish": true,
    "broil_seconds": 90,
    "launch_method": "wooden peel with semolina"
  }
}
```

All fields in `meta`, `dough`, `sauce`, `cheese`, and `result` are required. The `bake` block is required. Optional fields (like `preferment`) can be omitted if not used.

---

## Submitting a Recipe

1. **Fork** this repository
2. **Create a folder** under `recipes/` named `YYYY-MM-DD_your-slug`
3. **Add your `recipe.json`** following the schema above
4. **Add a `photo.jpg`** of the finished pizza (required for the catalog site)
5. **Open a pull request** with a short description of what you were going for and what changed from your last attempt

All pull requests are reviewed before merging. We check that the JSON is valid, the photo is present, and the recipe is complete enough to reproduce. We're not gatekeeping quality; bad pizzas are welcome, that's how we learn. But the data needs to be thorough.

---

## Key Tracked Variables

These are the details that actually matter for reproducibility:

**Dough:** flour protein %, hydration %, water temperature, yeast type and quantity, fermentation time and temperature (both bulk and cold), preferment type if used, number of stretch-and-fold sets.

**Sauce:** tomato brand and type, whether drained and for how long, raw vs cooked, process method (crushed/blended/passed), grams per pizza, moisture assessment.

**Cheese:** brand, moisture percentage, grated vs sliced, application order relative to sauce, grams per pizza, any finishing cheeses and when applied.

**Bake:** surface type, oven temp, preheat duration, rack position, total bake time, whether broiler was used.

---

## Running the Catalog Site Locally

The site is plain HTML/CSS/JS hosted on GitHub Pages, no build step required.

```bash
git clone https://github.com/your-username/opensauce.git
cd opensauce
# Open index.html in your browser, or serve it:
npx serve .
```

The site reads all `recipe.json` files and renders a card per attempt with the photo, date, title, key stats, and overall score.

---

## Contributing Guidelines

- One attempt per pull request
- Photos must be of the actual pizza from that attempt, no stock images
- If you're iterating on someone else's recipe, reference the original `id` in your `notes`
- Don't round your measurements. Precision is the point.

---

## License

Recipes and data are released under [CC0](https://creativecommons.org/publicdomain/zero/1.0/), no rights reserved. Do whatever you want with them.
