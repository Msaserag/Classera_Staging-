# AY26-27 Classera Programs & Events — how to update links

**You only ever edit one file: `links.json`.** Nothing else in this repository needs to change
when a registration link becomes available.

---

## Update a link in four steps

1. Open **`links.json`** here on GitHub.
2. Click the **pencil icon** (Edit this file).
3. Find the id of the session or event and paste the URL between the quotes:

   ```json
   "pd-s03": "https://elearning.classera.com/course/1234",
   ```

4. Click **Commit changes**. The site refreshes within about a minute.

That is the whole process. No HTML is touched, and no rebuild is needed.

---

## What happens on the page

| In `links.json` | What visitors see |
| --- | --- |
| Link is empty `""` | The button still opens the platform, and the note *"Course link will be updated soon"* stays visible. |
| Link is filled | The button becomes **Register now** and opens your link. The note disappears. The Google and Outlook calendar buttons carry the same link inside the invitation. |

Enrichment activities behave the same way: a filled link turns *"Open on Enrichment Academy"*
into **Register now** pointing at that activity.

For product and in-person events, a filled link adds a **Register now** button to that
event card. The official event website button (Bett, InnoXera, EWF) is never replaced.

---

## The ids

Ids are grouped by page and never change:

- **`pd-s01` … `pd-s11`** — professional development sessions, numbered exactly as the cards
  show them (SESSION 01 … SESSION 11).
- **`product-events-…`** — the four product events, for example `product-events-founding-day`.
- **`in-person-events-…`** — the twelve in-person events, for example `in-person-events-bett-uk`.
- **`enr-01` … `enr-31`** — the Enrichment Academy activities, numbered exactly as the cards show
  them (NO. 01 … NO. 31).

Open `links.json` and you will see every id listed with an empty value, ready to fill.

---

## Rules that keep the file valid

- Keep the **quotes** around both the id and the link.
- Keep the **comma** at the end of every line except the last one in the block.
- Do not rename or delete an id. Leave it empty instead.
- Paste the full address, starting with `https://`.

If the file is saved with a typo, the pages simply fall back to the platform links and keep
showing "link will be updated soon" — nothing breaks, and fixing the typo restores everything.

---

## Repository layout

```
index.html                 the hub: five cards + the full events calendar band
links.json                 ← the only file you edit
eLearning/index.html       Professional Development plan
Accreditation/index.html   Accreditation exam calendar + how to get accredited
Enrichment/index.html      Enrichment Academy plan
ProductEvents/index.html   Product events
InPersonEvents/index.html  In-person events
Calendar/index.html        Full events calendar (printable)
.nojekyll                  keeps GitHub Pages serving the folders as they are
```

The hub loads each plan from its own file, so editing a plan page — or `links.json` — shows up
on the hub immediately, with no rebuild.

---

## Checking your work

1. Open the published site and click the plan you changed.
2. The session button should read **Register now** and open your URL.
3. If it still says "link will be updated soon", re-open `links.json` and check the id spelling
   and that the link is inside quotes.

Tip: your browser may hold an old copy for a minute. Press **Ctrl+F5** (Windows) to force a refresh.
