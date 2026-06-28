[Immoweb Scraper](https://apify.com/studio-amba/immoweb-scraper?fpr=data)

# Immoweb Scraper

Extract property listings from [Immoweb.be](https://www.immoweb.be) — Belgium's #1 real estate portal with over 200,000 active listings — into structured JSON with prices, locations, EPC scores, photos, and full property details.

## What is Immoweb Scraper?

**Immoweb Scraper** lets you extract structured real estate data from Belgium's largest property platform, helping you monitor the market, compare prices, and automate property research — all without manual browsing.

- **Track market prices by neighbourhood:** extract listings with prices, surface areas, and EPC scores to build price-per-m² maps across any Belgian city or postcode
- **Monitor new listings in real time:** schedule daily runs and get alerted the moment a property matching your criteria hits the market
- **Build property datasets for analysis:** export thousands of listings with GPS coordinates, build year, and energy ratings for valuation models, academic research, or investment screening
- **Compare rental vs. sale markets:** switch between sale and rent listings to analyse yield gaps and rental demand across regions
- **Feed your CRM or dashboard:** export structured data to Google Sheets, Airtable, or any BI tool via Apify integrations

Immoweb.be has **no public API and no bulk export feature**. This scraper is the only way to get structured data out of Belgium's dominant property platform at scale.

## What data does Immoweb Scraper extract?

🏠 **Title** and full property description
📍 **Address** — street, postal code, city, province
🗺️ **GPS coordinates** — latitude and longitude for mapping
💰 **Price** — asking price for sale or monthly rent
🏷️ **Listing type** — sale or rent
🏗️ **Property details** — type, bedrooms, bathrooms, surface (m²), land surface (m²), build year
⚡ **EPC energy score** — official energy performance certificate rating
🏢 **Agency name** — the estate agent marketing the property
📸 **All images** — main photo and full gallery of property photos
📝 **Description** — complete listing text
🔗 **Direct URL** to the listing on Immoweb.be

## How to scrape Immoweb.be

The input is simple: choose your **search criteria** and hit run. You can configure the scraper through the Apify Console UI or programmatically via the API.

### Input fields

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| **searchQuery** | String | — | Search by location, e.g. `"Brussels"`, `"Gent"`, `"1000"` |
| **startUrls** | Array | — | Immoweb search result URLs or individual listing URLs |
| **listingType** | String | `"sale"` | `"sale"` or `"rent"` |
| **propertyType** | String | `"any"` | `"any"`, `"house"`, or `"apartment"` |
| **maxResults** | Integer | `100` | Maximum number of listings to return (1–10,000) |
| **proxyConfiguration** | Object | — | Proxy settings (recommended — Immoweb has bot detection) |

### Tips for best results

- **Use `searchQuery` for quick location searches:** type a city name like `"Antwerpen"` or a postal code like `"1050"` to target a specific area
- **Use `startUrls` for advanced filtering:** apply filters on Immoweb.be (price range, number of bedrooms, garden, etc.), copy the URL, and paste it as a start URL to preserve all filters
- **Proxy is strongly recommended.** Immoweb blocks most datacenter IPs. Use residential proxy for large runs to avoid rate limits
- **Start with a small `maxResults`** (e.g. 50) to verify the output, then scale up
- **Schedule daily runs** to track new listings — Immoweb typically sees hundreds of new properties per day across Belgium

## Output

Results are stored in a **dataset** that you can download in JSON, CSV, Excel, XML, or HTML format directly from the Apify Console.

### JSON example

```
{
    "title": "Apartment for sale in Brussels",
    "price": 325000,
    "currency": "EUR",
    "url": "https://www.immoweb.be/en/classified/apartment/for-sale/brussels/1000/11284753",
    "scrapedAt": "2026-04-04T08:30:00.000Z",
    "listingType": "sale",
    "propertyType": "apartment",
    "address": "Rue de la Loi 42",
    "city": "Brussels",
    "postalCode": "1000",
    "province": "Brussels",
    "bedrooms": 2,
    "bathrooms": 1,
    "surface": 95,
    "landSurface": null,
    "buildYear": 1985,
    "epcScore": "B",
    "imageUrl": "https://pic.immoweb.be/pics/11284753/1.jpg",
    "imageUrls": [
        "https://pic.immoweb.be/pics/11284753/1.jpg",
        "https://pic.immoweb.be/pics/11284753/2.jpg",
        "https://pic.immoweb.be/pics/11284753/3.jpg",
        "https://pic.immoweb.be/pics/11284753/4.jpg"
    ],
    "description": "Bright 2-bedroom apartment in the European quarter with open kitchen, balcony, and cellar. Close to Schuman metro station and Parc du Cinquantenaire. Recently renovated with new double glazing and EPC B rating.",
    "latitude": 50.8465,
    "longitude": 4.3717,
    "agencyName": "Trevi Brussels"
}
```

## How much does it cost to scrape Immoweb?

Immoweb Scraper uses **Playwright (real browser)** because Immoweb relies on JavaScript rendering and has anti-bot protections. This makes it slightly more expensive than HTTP-only scrapers, but still very affordable.

| Scenario | Est. cost | Time |
| --- | --- | --- |
| 100 listings | ~$0.25 | ~3 min |
| 1,000 listings | ~$2.50 | ~25 min |
| 5,000 listings | ~$12.50 | ~2 hrs |

**Pricing breakdown:**

- Per result: $0.004

## Can I integrate Immoweb Scraper with other apps?

Yes. Immoweb Scraper connects with any tool through [Apify integrations](https://apify.com/integrations):

- **Google Sheets** — automatically export property data to a spreadsheet
- **Slack / Email** — get notified when new listings match your criteria
- **Zapier / Make** — trigger workflows when data is ready
- **Airtable** — build a searchable property database
- **REST API** — call the scraper programmatically from any language
- **Webhooks** — get notified when a run finishes

## Can I use Immoweb Scraper as an API?

Yes. Use the [Apify API](https://docs.apify.com/api/v2) to run Immoweb Scraper programmatically.

**Python:**

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("studio-amba/immoweb-scraper").call(run_input={
    "searchQuery": "Brussels",
    "listingType": "sale",
    "propertyType": "apartment",
    "maxResults": 200,
})

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(f"{item['title']} — {item['city']} — €{item['price']:,}")
```

**JavaScript:**

```
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: 'YOUR_API_TOKEN' });
const run = await client.actor('studio-amba/immoweb-scraper').call({
    searchQuery: 'Brussels',
    listingType: 'sale',
    propertyType: 'apartment',
    maxResults: 200,
});

const { items } = await client.dataset(run.defaultDatasetId).listItems();
console.log(items);
```

Check the [API tab](https://apify.com/studio-amba/immoweb-scraper/api) for full documentation.

## FAQ

### What is Immoweb.be?

Immoweb.be is Belgium's largest and most-visited real estate platform, with over 200,000 active property listings. It covers the entire Belgian market — Flanders, Wallonia, and Brussels — for both sales and rentals across all property types. It's operated by Immoweb Group (part of Aviv Group / Axel Springer).

### How does Immoweb Scraper work?

It uses a real browser (Playwright) to load Immoweb listing pages and extracts structured data from `window.classified` — a JavaScript object that Immoweb injects into every listing page. This gives clean, complete data without needing to parse messy HTML. If the JavaScript object isn't available (rare), there's an HTML fallback.

### Can I scrape both sale and rental listings?

Yes. Set `listingType` to `"sale"` or `"rent"`. You can also filter by property type: `"house"`, `"apartment"`, or `"any"` for all types.

### Can I filter by price, bedrooms, or other criteria?

Yes. Apply any filters on Immoweb.be directly, then copy the resulting URL and paste it into `startUrls`. The scraper will respect all URL parameters including price range, number of bedrooms, garden, terrace, and more.

### Is it legal to scrape Immoweb?

This scraper extracts publicly available listing data that Immoweb.be displays to all visitors. The data is factual (prices, addresses, property specifications) and does not contain private personal information. As with any scraping tool, use the data responsibly and in compliance with applicable laws.

## Limitations

- **Belgium only.** Immoweb.be covers exclusively Belgian real estate.
- **Browser-based.** Uses Playwright, which is slower and more expensive than HTTP-only scrapers — but necessary because Immoweb requires JavaScript rendering.
- **Proxy recommended.** Immoweb has bot detection. Residential proxy is recommended for runs over 500 listings.
- **Rate-limited crawling.** The scraper uses low concurrency to avoid triggering blocks, which means large runs take longer.
- **Some fields may be null.** Not all sellers fill in every field — `landSurface`, `buildYear`, or `epcScore` may be missing on some listings.

## Other Belgian real estate scrapers

Combine Immoweb Scraper with these actors for comprehensive Belgian and European property market coverage:

- ⚖️ [Biddit Scraper](https://apify.com/studio-amba/biddit-scraper) — Belgian notarial property auctions with bid prices
- 🏠 [Logic-Immo Scraper](https://apify.com/studio-amba/logicimmo-scraper) — French-language Belgian real estate listings
- 🏡 [Immovlan Scraper](https://apify.com/studio-amba/immovlan-scraper) — Belgian property listings (VTM/DPG network)
- 🇱🇺 [Athome.lu Scraper](https://apify.com/studio-amba/athome-scraper) — Luxembourg real estate
- 🇩🇪 [ImmoScout24 Scraper](https://apify.com/studio-amba/immoscout24-scraper) — German property listings

## Your feedback

Found a bug or have a feature request? Please open an issue on the [Issues tab](https://apify.com/studio-amba/immoweb-scraper/issues). We actively maintain this scraper and respond to all reports.