[Immoweb Scraper](https://apify.com/memo23/immoweb-scraper?fpr=data)

# Immoweb.be Scraper

![Immoweb Scraper - How It Works](https://images.apifyusercontent.com/GUUivrg1LxBuKYuX42iOoRmdMKBii0NWYWoSqH8tVD0/w:1800/cb:1/aHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL211aGFtZWQtZGlkb3ZpYy9tdWhhbWVkLWRpZG92aWMuZ2l0aHViLmlvL21haW4vYXNzZXRzL2hvdy1pdC13b3Jrcy1pbW1vd2ViLWdlbmVyYXRlZC5wbmc.webp)

**Unlock the Full Power of Immoweb.be Real Estate Data** - The only scraper you need to track, analyze, and understand property listings on Immoweb.be with enterprise-grade reliability and precision. Whether you're monitoring property trends, tracking specific real estate investments, or conducting housing market research, our scraper delivers comprehensive, real-time insights while saving you time and resources.

*"From houses and apartments to office blocks and investment projects, we turn Immoweb's real estate data into your competitive advantage."*

## Overview

The Immoweb.be Scraper is your go-to tool for extracting property posting data from Immoweb.be. Ideal for real estate agents, investors, housing market analysts, and property seekers, it tracks property details, pricing information, and agency profiles across the Belgian real estate sector. With easy setup and multiple export formats (JSON, CSV), it's perfect for anyone looking to gather comprehensive housing market data from Immoweb.be.

## Supported Inputs

The Immoweb scraper is highly flexible and accepts multiple starting points. You can mix and match these in your `startUrls` array:

**✅ Supported:**

- **Search Pages**: `https://www.immoweb.be/en/search/house/for-sale?countries=BE&page=1`
- **Filtered Searches**: `https://www.immoweb.be/en/search-3-rooms/house/for-rent/bruxelles/district`
- **Direct Listings**: `https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580`
- **Project Listings**: `https://www.immoweb.be/en/classified/house_group/for-sale/schelle/2627/21513401`

**❌ Not Supported:**

- User account dashboards or saved favorites (`/my-immoweb/`)
- URLs outside of the `immoweb.be` domain.

## What does Immoweb.be Scraper do?

The Immoweb.be Scraper is a powerful tool that enables you to:

### Comprehensive Data Collection

- **Property Listings**

- Extract complete property details and requirements
- Scrape pricing information and monthly costs
- Gather comprehensive property descriptions and spatial dimensions
- Analyze property categories, energy scores (EPC), and amenities
- Access location coordinates and building conditions
- **Agency Data**

- Scrape real estate agency profiles with complete information
- Extract agency contact details, phone numbers, and websites
- Gather company size and industry information
- Access company location and remote work policies

### Advanced Scraping Capabilities

- **Pagination Handling**: Automatically navigates through all search result pages
- **Efficient Processing**: Bypass Cloudflare DataDome protections natively using HTML extraction
- **Deep Data Extraction**: Extracts and flattens heavily nested JSON states automatically
- **Comprehensive Output**: Captures everything from EPC values to exact GPS coordinates

### Flexible Scraping Options

- **Search Results**: Scrape all property postings from search results (e.g., `https://www.immoweb.be/en/search/house/for-sale`)
- **Individual Listings**: Target specific property postings using direct URLs (e.g., `https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580`)
- **Flexible Input**: Supports multiple input formats:

- Search result URLs (e.g., `https://www.immoweb.be/en/search/house/for-sale`)
- Direct property posting URLs (e.g., `https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580`)
- Custom search criteria with advanced filters
- **Automatic Pagination**: Handles multi-page results automatically across all search types
- **Efficient Processing**: Concurrent scraping with configurable concurrency settings
- **Reliable Performance**: Built-in retry mechanisms and proxy support
- **Structured Data Export**: Download property listing data in JSON or CSV format for analysis

## Why use Immoweb.be Scraper?

- **Real Estate Monitoring**: Keep track of new properties, price adjustments, and market supply.
- **Investor Insights**: Discover under-priced properties, track yield opportunities, and build data models.
- **Competitor Tracking**: Real estate agencies can seamlessly monitor rival portfolios and sales speeds.
- **Save Time**: Automate manual property searching and data entry tasks.

## How it works

1. Provide search URLs (e.g., `https://www.immoweb.be/en/search/house/for-sale`) or direct listing URLs.
2. The scraper bypasses protections and paginates through the results automatically.
3. For each listing, it extracts the full React state object (`window.classified`).
4. The nested JSON is instantly flattened and delivered to you as CSV, Excel, or JSON.

## How to Use

### Scraping Property Listings

To scrape property listings:

1. **Set Up**: Ensure you have an Apify account and access to the Apify platform.
2. **Configure Input**: Provide the search URL or specific property posting URL:

- `https://www.immoweb.be/en/search/house/for-sale`
- `https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580`
3. **Adjust Settings**: Configure options like max items, concurrency, retries, and proxy settings as needed.
4. **Run the Scraper**: Execute the scraper on the Apify platform.
5. **Data Collection**: The scraper will output all available property listing data.

## Input Configuration

Here's an example of how to set up the input for the Immoweb.be Scraper:

```
{
    "startUrls": [
        "https://www.immoweb.be/en/search/house/for-sale",
        "https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580"
    ],
    "maxItems": 20,
    "monitoringMode": false,
    "maxConcurrency": 10,
    "minConcurrency": 1,
    "maxRequestRetries": 3,
    "proxy": {
        "useApifyProxy": true
    }
}
```

The actor stores its results in the default dataset. Below is a sample output object. For a detailed breakdown of every field, see the Output Fields Explanation section below.

```
{
  "id": 21064580,
  "url": "https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580",
  "original_request_url": "https://www.immoweb.be/en/classified/office-block/for-rent/houthalen-helchteren/3530/21064580",
  "customers": [
    {
      "id": 1248059,
      "type": "AGENCY",
      "email": "info@agency.be",
      "logoUrl": "https://media.immowebstatic.be/.../logo.jpg",
      "phoneNumber": "+3211800000",
      "name": "Vestio",
      "website": "http://www.vestio.com",
      "location": {
        "country": "Belgium",
        "province": "Limburg",
        "locality": "Hasselt",
        "postalCode": "3500",
        "street": "20 Kolonel Dusartplein"
      },
      "ipiNo": "206808",
      "isOwner": true
    }
  ],
  "media_pictures": [
    {
      "smallUrl": "https://media-resize.immowebstatic.be/.../small.jpg",
      "largeUrl": "https://media-resize.immowebstatic.be/.../large.jpg"
    }
  ],
  "property_type": "OFFICE",
  "property_subtype": "OFFICE_BLOCK",
  "property_title": "Flexibele kantoorruimtes in bedrijvencentrum",
  "property_description": "In het innovatieve bedrijvencentrum Greenville...",
  "property_location_country": "Belgium",
  "property_location_region": "Flanders",
  "property_location_province": "Limburg",
  "property_location_locality": "Houthalen-Helchteren",
  "property_location_postalCode": "3530",
  "property_location_street": "Centrum Zuid",
  "property_location_latitude": 51.0256269,
  "property_location_longitude": 5.3723637,
  "property_hasLift": true,
  "property_constructionPermit_isObtained": true,
  "transaction_type": "FOR_RENT",
  "transaction_subtype": "RENT_AND_BUY",
  "price_mainValue": 34,
  "price_type": "PRICE",
  "publication_creationDate": "2025-10-03T10:04:27.998Z",
  "publication_lastModificationDate": "2026-04-13T18:38:28.747Z"
}
```

## Output Fields Explanation

This section provides a detailed breakdown of all key fields in the JSON output from the Immoweb.be Scraper. The output is organized into flattened key-value pairs for easy CSV/Excel export.

### Core Listing Details

- `id` (Number): Internal unique identifier for the property listing on Immoweb.
- `url` (String): The direct URL to the property listing.
- `original_request_url` (String): The original URL that led to the discovery of this property.

### Agency / Customer Details

- `customers` (Array): Contains details about the real estate agency or seller.

- `type` (String): Always "AGENCY" for real estate agencies.
- `email` (String): Agency contact email.
- `logoUrl` (String): Direct URL to the agency's logo.
- `phoneNumber` (String): Landline contact number.
- `name` (String): Name of the real estate agency.
- `website` (String): Agency's official website URL.
- `location` (Object): Physical location details of the agency (country, province, locality, postalCode, street).
- `ipiNo` (String): The agency's BIV/IPI real estate license number.
- `isOwner` (Boolean): If the agency is the direct owner of the listing.

### Media & Pictures

- `media_pictures` (Array): List of all property images, containing objects with `smallUrl`, `mediumUrl`, `largeUrl`, and `extralargeUrl` for different resolutions.
- `media_virtualTourUrl` (String|null): URL to a 3D/virtual tour of the property.
- `media_floorPlans` (Array|null): Floor plan documents/images.
- `media_documents` (Array): Any attached documents (e.g., PDFs, EPC certificates).

### Property Details

- `property_type` (String): Main property type (e.g., "HOUSE", "APARTMENT", "OFFICE").
- `property_subtype` (String): Specific property subtype (e.g., "HOUSE_GROUP", "OFFICE_BLOCK").
- `property_title` (String): The main listing title in the primary language.
- `property_description` (String): Full property description text.
- `property_bedroomCount` (Number|null): Total number of bedrooms.
- `property_bathroomCount` (Number|null): Total number of bathrooms.
- `property_netHabitableSurface` (Number|null): Total habitable living space in square meters.
- `property_roomCount` (Number|null): Total number of rooms.
- `property_monthlyCosts` (Number): Monthly shared/syndic costs.

### Property Location

- `property_location_country` (String): Country (e.g., "Belgium").
- `property_location_region` (String): Region (e.g., "Flanders", "Wallonia", "Brussels").
- `property_location_province` (String): Province name.
- `property_location_district` (String): District name.
- `property_location_locality` (String): City / Town name.
- `property_location_postalCode` (String): ZIP / Postal code.
- `property_location_street` (String): Street name.
- `property_location_number` (String): Street number.
- `property_location_latitude` (Number): Geographic latitude coordinate.
- `property_location_longitude` (Number): Geographic longitude coordinate.

### Building & Construction

- `property_building_condition` (String|null): State of the building (e.g., "GOOD", "AS_NEW", "TO_RENOVATE").
- `property_building_constructionYear` (Number|null): Year the property was built.
- `property_building_facadeCount` (Number|null): Number of facades/free-standing sides.
- `property_building_floorCount` (Number|null): Total number of floors in the building.
- `property_hasLift` (Boolean|null): If the building has an elevator.
- `property_constructionPermit_isObtained` (Boolean|null): If proper construction permits exist.

### Features & Amenities

- `property_hasGarden` (Boolean|null): If the property has a garden.
- `property_gardenSurface` (Number|null): Size of the garden in square meters.
- `property_hasTerrace` (Boolean|null): If the property has a terrace.
- `property_terraceSurface` (Number|null): Size of the terrace in square meters.
- `property_hasSwimmingPool` (Boolean|null): If the property has a pool.
- `property_hasAirConditioning` (Boolean|null): If air conditioning is installed.
- `property_kitchen_type` (String|null): Type of kitchen (e.g., "HYPER_EQUIPPED", "INSTALLED").
- `property_parkingCountIndoor` (Number|null): Number of indoor parking spaces.
- `property_parkingCountOutdoor` (Number|null): Number of outdoor parking spaces.

### Energy & EPC

- `property_energy_epcScore` (String|null): The official EPC rating letter (e.g., "A", "B", "C").
- `property_energy_heatingType` (String|null): Type of heating (e.g., "GAS", "ELECTRIC", "PELLET").
- `property_energy_primaryEnergyConsumptionPerSqm` (Number|null): Energy consumption (kWh/m²/year).

### Transaction & Pricing

- `transaction_type` (String): Type of transaction (e.g., "FOR_SALE", "FOR_RENT").
- `transaction_subtype` (String): Subtype of transaction.
- `price_mainValue` (Number): The main asking price in Euros.
- `price_type` (String): The price type (e.g., "PRICE").
- `flags_isNewlyBuilt` (Boolean): If the property is a new construction.
- `flags_isPublicSale` (Boolean): If the property is being sold at a public auction.
- `flags_isUnderOption` (Boolean): If the property is currently under option/offer.

### Publication & Statistics

- `publication_creationDate` (ISO 8601): When the listing was first published on Immoweb.
- `publication_lastModificationDate` (ISO 8601): When the listing was last updated.
- `statistics_viewCount` (Number|null): Number of times the listing has been viewed.
- `statistics_bookmarkCount` (Number|null): Number of times the listing was saved/bookmarked.

---

## FAQ

**How does this bypass Immoweb's DataDome protections?**
Immoweb's REST API is aggressively guarded by Cloudflare's DataDome. To bypass this, our scraper extracts the exact same data directly from the frontend React state (`window.classified`) rendered on the HTML page. This yields a 100% data match with a significantly lower block rate.

**What does the flattened output look like?**
Nested properties like `property: { location: { street: "Main St" } }` are automatically flattened into single-level columns: `property_location_street: "Main St"`. This prevents messy JSON objects from appearing in your CSV or Excel exports. Note that arrays (like `media_pictures`) remain as lists.

**Can I mix search URLs and direct listings?**
Yes! You can put a mix of `/search/` URLs and `/classified/` URLs into the `startUrls` array. The scraper will automatically detect the URL type and process it appropriately.

**Why am I still getting blocked?**
If you're scraping thousands of pages in a single run, it is highly recommended to enable Apify's Residential Proxies in your configuration. Datacenter proxies are frequently flagged by Belgian real estate sites.

---

## Explore More Scrapers

If you found this Apify Immoweb.be Scraper useful, be sure to check out our other powerful scrapers and actors at [memo23's Apify profile](https://apify.com/memo23). We offer a wide range of tools to enhance your web scraping and automation needs across various platforms and use cases.

## Support

- For issues or feature requests, please use the [Issues](https://console.apify.com/actors/7Fw4OYjfMapM6l49D/issues) section of this actor.
- If you need customization or have questions, feel free to contact the author:

- Author's website: [https://muhamed-didovic.github.io/](https://muhamed-didovic.github.io/)
- Email: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)

## Additional Services

- Request customization or whole dataset: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)
- If you need anything else scraped, or this actor customized, email: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)
- For API services of this scraper (no Apify fee, just usage fee for the API), contact: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)
- Email: [muhamed.didovic@gmail.com](mailto:muhamed.didovic@gmail.com)