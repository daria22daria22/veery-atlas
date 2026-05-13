# Veery Atlas

Interactive world map of cosmetic dentists and dental ceramists, part of the [Veery](https://veery.co) platform.

**Live site:** https://veery-atlas.pplx.app

## How it works

The map is a single-page static site (`deploy/index.html`) that fetches its data at runtime from a Google Sheet:

- **Dentists tab** → cosmetic dentists with name, specialty, city/state/country, contact info, lat/lng
- **Ceramists tab** → dental labs/studios with similar fields

Because data lives in the Sheet, you can add or edit entries without touching code or redeploying — the next page load picks up the changes.

## Project structure

```
deploy/
├── index.html          # Main app (HTML + CSS + JS in one file)
├── geo_us.json         # US state boundaries for the map
├── geo_world.json      # World country boundaries
└── npi/                # State-by-state NPI dentist shards (cached lookups)
    ├── AK.json
    ├── AL.json
    └── ... (60 files)
```

## Deployment

Deployed on Perplexity's S3-backed hosting. The `site_id` for redeploys is `1847ca31-c75a-4758-8a16-8039e5b5f7de`.

To update the live site after editing `deploy/index.html`:

1. Make your changes locally
2. Use Perplexity Computer's `deploy_website` + `publish_website` tools with the saved `site_id`

## Data source

Google Sheet: `18h16EEURItsTQh08OMDgyc-UWrZE1odhi_asRfnrqgs`

### Schemas

**Dentists (19 cols):** Name, Tier, Specialty, City, State, Country, Practice, Address, Phone, Email, Website, Instagram, Awards, Year, Celebrity Clients, Sources, Source URL, Lat, Lng

**Ceramists (17 cols):** Name, Tier, Score, City, Country, Lab, Specialty, Materials, Style, Phone, Email, Website, Instagram, How Discovered, Sources, Lat, Lng

## License

Proprietary — © Veery
