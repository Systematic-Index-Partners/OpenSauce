<img width="1200" height="240" alt="opensauce_banner" src="assets/opensauce_banner.svg" />

**A precision recipe repository for New York-style pizza.** Every attempt logged. Every variable tracked. Every iteration building toward the perfect pie.

Browse the full catalog and submit your own recipes at **[open-sauce-pn5a.vercel.app](https://open-sauce-pn5a.vercel.app)**.

---

## The Catalog

The site shows every submitted recipe as a card with the pizza photo, date, key stats (hydration, flour type, bake temp, surface), and the baker's notes. Use the sort control in the top right to order by newest or oldest attempt.

Each card is a snapshot of one bake - not a polished recipe, but a logged attempt with enough data to reproduce it exactly or identify what to change next.

---

## Submitting a Recipe

Everything happens through the site - no GitHub account setup or manual JSON editing required.

**1. Click the + button** in the top right of the catalog.

**2. Sign in with GitHub.** You'll be redirected to GitHub to authorize OpenSauce. This is how the site files your recipe as a pull request on your behalf. You only do this once per session.

**3. Fill out the 10-step form.** The form walks through every tracked variable:

| Step | What you're filling in |
|---|---|
| 1 - Recipe Info | Title, date, your GitHub username, style, notes on what you were going for |
| 2 - Flour & Water | Flour type, protein %, whether bromated, grams of each, hydration %, water temp |
| 3 - Yeast, Salt, Oil & Sugar | Yeast type and quantity, salt, oil type and quantity, sugar |
| 4 - Preferment | Toggle on if you used a poolish, biga, etc. - type, ratios, fermentation time and temp |
| 5 - Process | Mix method, autolyse, bulk ferment time and temp, cold proof time and temp, ball weight, stretch and fold sets |
| 6 - Sauce | Tomato brand and type, whether drained, garlic, olive oil, oregano, red pepper, process method, moisture assessment, grams per pizza |
| 7 - Cheese | Mozzarella brand, moisture %, grated or sliced, grams per pizza, optional pecorino, application order relative to sauce |
| 8 - Bake | Oven type, surface, preheat time, temp, rack position, bake time, broiler finish |
| 9 - Photo | A photo of the actual pizza from this attempt |
| 10 - Review | Confirm the assembled data before submitting |

**4. Submit.** The site creates a branch in this repository, commits your `recipe.json` and photo, and opens a pull request automatically. You'll get a link to the PR when it's done.

**5. Review.** All PRs are reviewed before merging. We check that the JSON is valid, the photo is present, and the data is complete enough to reproduce. Bad pizzas are welcome - that's how we learn. But the data needs to be thorough.

---

## What Gets Tracked and Why

Reproducibility is the entire point. These are the variables that actually move the needle:

**Dough:** flour protein % and whether it's bromated, hydration %, water temperature, yeast type and exact quantity, fermentation time and temperature for both bulk and cold proof, preferment type if used, number of stretch-and-fold sets.

**Sauce:** tomato brand and type (brand matters more than people think), whether drained and by what method, raw vs cooked, grams per pizza, moisture description.

**Cheese:** brand, moisture percentage, grated vs sliced, application order relative to sauce, grams per pizza, any finishing cheese and when it's applied.

**Bake:** surface type, oven temp, preheat duration, rack position, total bake time, whether the broiler was used and for how long, launch method.

---

## Contributing Guidelines

- One attempt per pull request
- Photos must be of the actual pizza from that attempt - no stock images
- If you're iterating on someone else's recipe, reference their `id` in your notes
- Don't round your measurements. Precision is the point.

---

## License

Recipes and data are released under [CC0](https://creativecommons.org/publicdomain/zero/1.0/) - no rights reserved. Do whatever you want with them.
