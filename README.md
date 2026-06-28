[Immoweb Scraper](https://apify.com/abotapi/immoweb-scraper?fpr=data)

# Immoweb.be Scraper

Extract property listings from **immoweb.be** - Belgium's largest property portal. Get price, location, coordinates, images, and 27 structured fields per listing. Enable detail page fetching for 70+ additional fields including description, EPC score, building details, energy features, and agent contact.

## Key Features

- **Two modes**: Search by filters (location, price, type) or paste Immoweb URLs directly
- **Automatic pagination**: Forward-walks search pages until limit reached
- **All property types**: House, Apartment, Land, Parking, Office, Industry, Garage, New Projects
- **Buy and Rent**: Supports both for-sale and for-rent listings
- **Advanced filters**: Price range, bedrooms, living area, land area, building condition, EPC grade, garden, terrace, pool, new builds
- **Full location data**: Street address, postal code, locality, district, province, region, coordinates (lat/lng)
- **Images included**: All listing photos with direct URLs
- **Optional detail enrichment**: Toggle on for 70+ extra fields per listing (description, EPC, building info, energy, agent contact, amenities)
- **Deduplication**: No duplicate listings across pages or URLs
- **Low cost**: Search-only mode uses minimal bandwidth; detail pages are opt-in

## Output Data

### Search Mode (27 fields, default)

| Category | Fields |
| --- | --- |
| **Core** | id, url, title, transactionType, propertyType, propertySubtype |
| **Price** | price, displayPrice, price_per_sqm, salePrice |
| **Size** | bedrooms, rooms, livingArea, landArea |
| **Location** | street, number, postalCode, locality, district, province, region, regionCode, country |
| **Coordinates** | latitude, longitude |
| **Media** | images (array of URLs), imageCount |
| **Other** | lastModified, listingFlag, customerName |

### Detail Mode (70+ additional fields)

When **Fetch Detail Pages** is enabled, each listing is enriched with:

| Category | Fields |
| --- | --- |
| **Description** | description (EN), descriptionFr, descriptionNl |
| **Building** | constructionYear, buildingCondition, facadeCount, floorCount |
| **Energy** | epcScore, heatingType, hasHeatPump, hasPhotovoltaicPanels, hasDoubleGlazing |
| **Interior** | bathrooms, toiletCount, kitchenType, showerRoomCount |
| **Exterior** | gardenSurface, terraceSurface, hasGarden, hasTerrace, hasSwimmingPool |
| **Amenities** | hasLift, hasAirConditioning, hasJacuzzi, hasSauna, hasWorkspace, hasDisabledAccess, ... |
| **Transaction** | cadastralIncome, availabilityPeriod, isSubjectToVat, renovationObligation |
| **Agent** | agencyName, agencyId, agencyPhone, agencyEmail, customerType |
| **Flags** | isNewlyBuilt, isPublicSale, isNewClassified, isNewPrice, isSoldOrRented |
| **Stats** | viewCount, bookmarkCount |
| **Dates** | creationDate, expirationDate |
| **Rental** | monthlyRentalPrice, monthlyRentalCosts, isFurnished, arePetsAllowed (rental listings only) |
| **Land** | floodZoneType, latestUseDesignation, plotDivisionAuthorization (land listings only) |

Fields vary by property type - houses include garden/terrace data, apartments include floor/lift info, land includes zoning permits, rentals include monthly costs and pet policies.

## How to Use

### Search by Filters

Set **mode** to "Search by Filters" and configure:

- **Transaction Type**: For Sale or For Rent
- **Property Types**: House, Apartment, Land, Parking, Office, etc.
- **Postal Codes**: Belgian postal codes (e.g. 1000 for Brussels, 2000 for Antwerp)
- **Price Range**: Minimum and maximum price in EUR
- **Bedrooms**: Minimum and maximum bedrooms
- **Living/Land Area**: Minimum and maximum in m2
- **Building Condition**: As new, Good, To renovate, etc.
- **EPC Grade**: Maximum energy rating (A++ to G)
- **Amenities**: Garden, Terrace, Swimming Pool, New Builds Only

### Direct URLs

Set **mode** to "Direct URLs" and paste search result page URLs from immoweb.be. The scraper will automatically paginate forward from the starting page.

Example URL:

```
https://www.immoweb.be/en/search/house/for-sale?countries=BE&postalCodes=1000&page=1&orderBy=newest
```

### Proxy Configuration

The scraper checks the paid proxy group first, then residential proxy access. Residential proxy access is required for detail page scraping. If residential access is unavailable, detail page scraping is disabled and only search-result data is collected.

## Example Output

```
{
  "id": 12345678,
  "url": "https://www.immoweb.be/en/classified/12345678",
  "title": "Charming villa with garden",
  "transactionType": "FOR_SALE",
  "propertyType": "HOUSE",
  "propertySubtype": "VILLA",
  "price": 425000,
  "displayPrice": "€425,000",
  "price_per_sqm": 2125,
  "bedrooms": 4,
  "livingArea": 200,
  "landArea": 850,
  "street": "Rue de la Gare",
  "number": "15",
  "postalCode": "1000",
  "locality": "Bruxelles",
  "district": "Brussels",
  "province": "Brussels",
  "region": "Brussels",
  "regionCode": "BRUSSELS",
  "country": "Belgium",
  "latitude": 50.8503,
  "longitude": 4.3517,
  "images": [
    "https://media-resize.immowebstatic.be/classifieds/.../736x736/image1.jpg",
    "https://media-resize.immowebstatic.be/classifieds/.../736x736/image2.jpg"
  ],
  "imageCount": 12,
  "lastModified": "2026-04-15T10:30:00.000Z",
  "customerName": "Example Agency"
}
```

With **Fetch Detail Pages** enabled, each listing includes 70+ additional fields like `description`, `epcScore`, `building_facadeCount`, `hasGarden`, `gardenSurface`, `agencyPhone`, `stat_viewCount`, etc.

## Limits

- **Maximum Listings**: Controls how many listings to scrape per run (default: 20)
- **Maximum Pages per URL**: Limits search result pages per URL/search (default: 20, ~30 listings per page)
- **Detail Concurrency**: Number of parallel detail-page fetches (default: 3, max: 8)