# Veery Atlas

Interactive world map of cosmetic dentists and dental ceramists, part of the [Veery](https://veery.co) platform.

## Live URLs

- **Production:** https://veery-atlas.pplx.app (Perplexity-hosted)
- **GitHub Pages preview:** https://daria22daria22.github.io/veery-atlas/ (auto-updates on every push)

## How it works

The map is a single-page static site (`index.html`) that fetches its data at runtime from a Google Sheet:

- **Dentists tab** → cosmetic dentists with name, specialty, city/state/country, contact info, lat/lng
- **Ceramists tab** → dental labs/studios with similar fields

Because data lives in the Sheet, you can add or edit entries without touching code or redeploying — the next page load picks up the changes.

## Project structure

```
index.html          # Main app (HTML + CSS + JS in one file)
geo_us.json         # US state boundaries
geo_world.json      # World country boundaries
npi/                # State-by-state NPI dentist shards (60 files)
```

## Editing

To change the map UI/behavior:
1. Edit `index.html` directly on GitHub (pencil icon) or locally
2. Commit to `main`
3. Preview at https://daria22daria22.github.io/veery-atlas/ within ~30 seconds
4. When happy, redeploy to production at veery-atlas.pplx.app (site_id `1847ca31-c75a-4758-8a16-8039e5b5f7de`)

To change the data (dentists/ceramists): edit the Google Sheet directly — no code changes needed.

## Data source

Google Sheet: `18h16EEURItsTQh08OMDgyc-UWrZE1odhi_asRfnrqgs`

### Schemas

**Dentists (19 cols):** Name, Tier, Specialty, City, State, Country, Practice, Address, Phone, Email, Website, Instagram, Awards, Year, Celebrity Clients, Sources, Source URL, Lat, Lng

**Ceramists (17 cols):** Name, Tier, Score, City, Country, Lab, Specialty, Materials, Style, Phone, Email, Website, Instagram, How Discovered, Sources, Lat, Lng

## License

Proprietary — © Veery
