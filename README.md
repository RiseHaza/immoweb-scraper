[Immoweb Scraper](https://apify.com/haketa/immoweb-scraper?fpr=data)

# 🏠 Immoweb.be Belgium Property Scraper

Extract property listings from **[Immoweb.be](https://www.immoweb.be)** — Belgium's #1 real estate platform with 200,000+ active listings. Covers houses, apartments, land and commercial properties across **Flanders**, **Wallonia** and **Brussels**. Sale and rent.

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-blue)](https://apify.com/)

---

## ⚡ What It Does

Scrapes Immoweb.be search result pages and optionally fetches individual property profiles. Extracts price, rooms, area, EPC energy score, location, agency info and 70+ fields from detail pages. Includes Belgium-specific data: **PEB/EPC energy certificate**, **flood zone risk** and **4-digit postcode** with automatic region/province mapping.

**Default run:** Scrapes Belgian properties for sale, completes in under 3 minutes, produces a non-empty dataset.

---

## 🔧 How It Works

Immoweb uses Cloudflare protection — this actor uses real Chrome via Playwright with Belgian residential proxy:

1. 🚀 Launches Chrome browser with 🇧🇪 Belgian residential proxy
2. 🍪 Accepts cookie consent on homepage
3. 🔍 Navigates to search results pages
4. 📊 Extracts structured JSON from `__NEXT_DATA__` or DOM
5. 📄 Optionally fetches detail pages for `window.classified` rich data
6. 🗺️ Maps postcodes to region (Flanders/Wallonia/Brussels) and province

---

## 🚀 Quick Start

### Default Input (works out of the box)

```
{
  "startUrls": [
    { "url": "https://www.immoweb.be/en/search/house-and-apartment/for-sale?countries=BE&page=1&orderBy=relevance" }
  ],
  "maxListings": 50,
  "maxPages": 3
}
```

### 🔍 Filter Mode (no URL needed)

```
{
  "propertyType": "apartment",
  "transactionType": "for-rent",
  "location": "brussels/district",
  "minPrice": 800,
  "maxPrice": 1500,
  "minBedrooms": 1,
  "scrapeDetails": true,
  "maxListings": 100,
  "maxPages": 5
}
```

---

## 📋 Input Parameters

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `startUrls` | array | prefilled | 🔗 Immoweb search URLs — paste any search URL |
| `propertyType` | string | `house-and-apartment` | 🏘️ `house`, `apartment`, `land`, `office`, `commercial`, `garage` |
| `transactionType` | string | `for-sale` | 💰 `for-sale` or `for-rent` |
| `location` | string | `""` | 📍 City/district/province slug (see below) |
| `language` | string | `en` | 🌐 `en` (English), `fr` (Français), `nl` (Nederlands) |
| `minPrice` | integer | `0` | 💶 Min price in EUR |
| `maxPrice` | integer | `0` | 💶 Max price in EUR |
| `minBedrooms` | integer | `0` | 🛏️ Min number of bedrooms |
| `scrapeDetails` | boolean | `false` | 📄 Fetch 70+ fields from detail pages |
| `maxListings` | integer | `50` | 🔢 Total listings cap |
| `maxPages` | integer | `3` | 📑 Max search result pages (~30 listings each) |
| `proxyConfiguration` | object | BE residential | 🔒 Belgian residential proxy (required) |
| `requestDelay` | integer (ms) | `2000` | ⏱️ Delay between page loads |

---

## 📍 Location Slugs

### 🏙️ Major Cities

| Slug | City | Region |
| --- | --- | --- |
| `brussels/district` | Brussels | 🇧🇪 Brussels |
| `antwerpen/province` | Antwerp area | 🟡 Flanders |
| `ghent/city` | Ghent | 🟡 Flanders |
| `bruges/city` | Bruges | 🟡 Flanders |
| `leuven/city` | Leuven | 🟡 Flanders |
| `liege/city` | Liège | 🔴 Wallonia |
| `namur/city` | Namur | 🔴 Wallonia |
| `mons/city` | Mons | 🔴 Wallonia |
| `charleroi/city` | Charleroi | 🔴 Wallonia |

### 🗺️ Regions & Provinces

| Slug | Coverage |
| --- | --- |
| `brussels/district` | 19 communes of Brussels Capital Region |
| `antwerpen/province` | Antwerp province |
| `oost-vlaanderen/province` | East Flanders (Ghent) |
| `west-vlaanderen/province` | West Flanders (Bruges) |
| `vlaams-brabant/province` | Flemish Brabant |
| `limburg/province` | Limburg |
| `liege/province` | Liège province |
| `hainaut/province` | Hainaut |
| `namur/province` | Namur province |
| `luxembourg/province` | Luxembourg province |
| `brabant-wallon/province` | Walloon Brabant |

---

## 📦 Output

### 🔍 Search Mode (`scrapeDetails: false`)

Quick extraction from search result cards (~30 per page):

```
{
  "listingId": "12345678",
  "listingType": "for-sale",
  "propertyType": "apartment",
  "price": 485000,
  "currency": "EUR",
  "bedrooms": 2,
  "livingArea": 95,
  "postcode": "1040",
  "city": "Brussels",
  "province": "Brussels",
  "region": "Brussels",
  "epcScore": "B",
  "agencyName": "Color Properties",
  "listingUrl": "https://www.immoweb.be/en/classified/apartment/for-sale/brussels/1040/12345678",
  "scrapedAt": "2026-05-05T09:00:00Z"
}
```

### 📄 Detail Mode (`scrapeDetails: true`)

Rich data from individual property pages (70+ fields):

```
{
  "listingId": "12345678",
  "listingType": "for-sale",
  "propertyType": "apartment",
  "title": "Penthouse with terrace near Montgomery",
  "price": 485000,
  "currency": "EUR",
  "bedrooms": 2,
  "bathrooms": 1,
  "livingArea": 95,
  "landSurface": null,
  "postcode": "1040",
  "city": "Brussels",
  "province": "Brussels",
  "region": "Brussels",
  "latitude": 50.8412,
  "longitude": 4.3954,
  "epcScore": "B",
  "epcValue": 142,
  "heatingType": "gas",
  "buildYear": 2019,
  "condition": "as new",
  "facade": 2,
  "floodZone": false,
  "description": "Magnificent penthouse with panoramic terrace...",
  "agencyName": "Color Properties",
  "agencyPhone": "+32 2 345 6789",
  "agencyEmail": "info@colorproperties.be",
  "viewCount": 847,
  "bookmarkCount": 34,
  "daysOnMarket": 12,
  "images": ["https://media.immowebstatic.be/..."],
  "scrapedAt": "2026-05-05T09:00:00Z"
}
```

---

## 🇧🇪 Belgium-Specific Data

### ⚡ PEB/EPC Energy Score

Belgium's mandatory energy performance certificate. Required for all property sales since 2008.

| Score | Rating | kWh/m²/year |
| --- | --- | --- |
| A++ | 🟢 Excellent | ≤ 0 (net zero) |
| A+ | 🟢 Very good | 0 – 45 |
| A | 🟢 Good | 45 – 85 |
| B | 🟡 Above average | 85 – 170 |
| C | 🟡 Average | 170 – 255 |
| D | 🟠 Below average | 255 – 340 |
| E | 🔴 Poor | 340 – 425 |
| F | 🔴 Very poor | 425 – 510 |
| G | ⚫ Worst | > 510 |

Low EPC = renovation opportunity. High EPC = premium pricing.

### 🌊 Flood Zone

Since the 2021 Liège floods, flood zone information is mandatory in Belgian property sales. The `floodZone` field indicates whether the property is in a designated flood risk area.

### 📮 Postcode → Region Mapping

Belgian 4-digit postcodes are automatically mapped to region and province:

| Postcode Range | Region | Province |
| --- | --- | --- |
| 1000 – 1299 | 🇧🇪 Brussels | Brussels |
| 1500 – 1999 | 🟡 Flanders | Flemish Brabant |
| 2000 – 2999 | 🟡 Flanders | Antwerp |
| 3000 – 3499 | 🟡 Flanders | Flemish Brabant |
| 3500 – 3999 | 🟡 Flanders | Limburg |
| 4000 – 4999 | 🔴 Wallonia | Liège |
| 8000 – 8999 | 🟡 Flanders | West Flanders |
| 9000 – 9999 | 🟡 Flanders | East Flanders |

---

## 🎯 Use Cases

- 🏡 **Property investment** — analyze rental yields, price trends by postcode
- 📊 **Automated valuation (AVM)** — EPC + m² + location data for valuation models
- 🏢 **Agency competitor analysis** — track new listings, pricing, market share
- 🏦 **Mortgage & insurance** — regional market data, flood risk assessment
- 🌍 **Expat relocation** — Brussels housing market monitoring for EU workers
- ⚡ **Energy renovation** — identify low-EPC properties as renovation opportunities

---

## ⚙️ Technical Notes

| Feature | Detail |
| --- | --- |
| 🔗 **Engine** | Playwright Chrome (real browser for JS rendering) |
| 🔒 **Proxy** | Belgian residential proxy **required** (Cloudflare blocks datacenter IPs) |
| 📊 **Data source** | `__NEXT_DATA__` JSON + `window.classified` object |
| 📄 **Pagination** | `?page=N`, ~30 results per page |
| 🌐 **Languages** | English (`en`), French (`fr`), Dutch (`nl`) |
| 🗺️ **Auto-mapping** | Postcode → region + province |

---

## 💸 Cost & Performance

| Mode | Speed | CU per 100 listings |
| --- | --- | --- |
| 🚀 Search only | ~20-30/min | ~0.03 |
| 📄 With details | ~3-5/min | ~0.08 |

Belgian residential proxy adds ~$0.003/request to compute cost.

---

## 📜 Changelog

| Version | Date | Notes |
| --- | --- | --- |
| 1.0.0 | 2026-05-05 | 🎉 Initial release — Playwright + BE proxy, EPC/flood data, postcode mapping, 3 languages |