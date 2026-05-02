# 🌳 Sylva — World Tree Planting Guide

A free, open-source, community-driven guide for planting deep-rooted, wind-resistant, long-lived trees — organized by **climate zone**, not by city.

**Live site:** [lassiipk.github.io/sylva](https://lassiipk.github.io/sylva/)

---

## Why climate zones, not cities?

There are hundreds of thousands of cities. But there are only a handful of meaningful climate zones. Lahore and Delhi share the same zone. London and Vancouver share the same zone. Organizing by zone means one dataset entry covers hundreds of cities automatically — and stays accurate indefinitely.

We use the **Köppen Climate Classification** system, the global scientific standard.

---

## What's in the guide

- **19 trees** across 9 climate zones (growing)
- **120+ cities** mapped to zones
- Planting calendars by month
- Seed preparation tips per species
- Universal care rules
- Filter by fruit / no fruit
- City search with instant zone detection

---

## How to contribute

You don't need to know how to code. All data lives in three JSON files.

### Add a tree → `data/trees.json`

```json
{
  "id": "your-tree-id",
  "name": "Common Name",
  "localNames": { "fr": "Nom français", "es": "Nombre español" },
  "scientific": "Genus species",
  "type": "fruit",
  "zones": ["Cfb", "Dfb"],
  "seedEase": "Easy",
  "rootDepth": 4,
  "windResistance": 5,
  "longevityYrs": [100, 300],
  "waterNeeds": "Low",
  "nativeRegion": "Europe",
  "seedTip": "How to prepare the seed before planting.",
  "notes": "Key facts about this tree in these zones.",
  "plantingMonths": "NNNBBGNNNNNN"
}
```

**plantingMonths** is a 12-character string (Jan→Dec):
- `B` = Best time to plant
- `G` = Good / acceptable
- `A` = Avoid
- `N` = Neutral / risky

**rootDepth** and **windResistance** are 1–5 ratings.

### Add a city → `data/cities.json`

```json
{ "city": "Kigali", "country": "Rwanda", "zone": "Aw" }
```

Find the right Köppen code for your city: [https://en.wikipedia.org/wiki/Köppen_climate_classification](https://en.wikipedia.org/wiki/K%C3%B6ppen_climate_classification)

### Add a zone → `data/zones.json`

```json
{
  "code": "Am",
  "name": "Tropical Monsoon",
  "koppen": "Am",
  "description": "Short dry season, heavy monsoon rains...",
  "summerpeak": "30–35°C",
  "winterlow": "20–26°C",
  "rainfall": "1500–3000 mm/yr",
  "soilType": "Laterite / Alluvial",
  "mainChallenge": "Waterlogging during monsoon season.",
  "bestWindow": "Start of dry season (Nov–Dec)",
  "avoidMonths": "Peak monsoon",
  "cities": ["Colombo", "Chittagong", "Yangon"]
}
```

---

## Project structure

```
sylva/
├── index.html          ← full standalone app (no build step)
├── data/
│   ├── trees.json      ← tree database
│   ├── zones.json      ← climate zone definitions
│   └── cities.json     ← city → zone mapping
├── README.md
└── LICENSE
```

No frameworks. No build tools. No dependencies. Just HTML, CSS, and vanilla JS that loads JSON files. Open `index.html` directly in a browser or host on GitHub Pages.

---

## Deploy to GitHub Pages

1. Fork this repo
2. Go to **Settings → Pages**
3. Set source: **main branch, root folder**
4. Save — your guide is live at `https://your-username.github.io/sylva`

---

## Zones currently covered

| Code | Zone | Example cities |
|------|------|----------------|
| BSh | Hot Semi-Arid | Faisalabad, Delhi, Ankara |
| BWh | Hot Desert | Dubai, Riyadh, Phoenix |
| Aw | Tropical Savanna | Lagos, Mumbai, Nairobi |
| Csa | Mediterranean Hot | Rome, Athens, LA |
| Csb | Mediterranean Warm | Lisbon, San Francisco |
| Cfb | Temperate Oceanic | London, Paris, Vancouver |
| Cfa | Humid Subtropical | Shanghai, Houston, Sydney |
| Dfb | Humid Continental | Warsaw, Toronto, Berlin |
| Dfc | Subarctic | Anchorage, Murmansk |

---

## License

MIT — free to use, fork, and build on. Credit appreciated but not required.

---

## Acknowledgements

Started in Faisalabad, Pakistan. Built for everyone.
