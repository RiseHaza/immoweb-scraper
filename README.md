[Immoweb Scraper](https://apify.com/ivanvs/immoweb-scraper?fpr=data)

Scrape listings from [Immoweb](https://www.immoweb.be) easily with Immoweb Scraper.

## About

Immoweb operates the website Immoweb.be. The group also includes the subsidiary Immoweb Financial Services S.A., which focuses on financial services, particularly insurance brokerage via the website protect.immoweb.be and soon mortgage credit, as well as the company G-Construct, which operates the website ConstructR.be.

Immoweb is 100% owned by the German media group Axel Springer, which also owns the companies operating the websites seloger.com, yad2.co.il, and immowelt.de, all grouped under the subsidiary Aviv Group.

Prior to its sale to Axel Springer in 2012, which led to the creation of the company Immoweb S.A., the website was operated by Produpress, the publisher of the magazine Le Moniteur Automobile and its corresponding website moniteurautomobile.be.

## Why should you use it?

It provides the realtime scraping of products from Immoweb, without requiring any other configuration and without any limits.

## How to use it?

Immoweb Scraper has number of input parameters that can be used.

| Input parameter | Description | Required | Default value |
| --- | --- | --- | --- |
| urls | Immoweb that needs to be scraped | `true` | `{url: "https://www.immoweb.be/en/search/house/for-sale/brussels/district?countries=BE&page=2&orderBy=relevance"}` |
| maxRecords | Maximum listings that needs to be scraped | `false` | 100 |

Valid Immoweb links:

- [https://www.immoweb.be/en/search/apartment/for-rent?countries=BE&page=2&orderBy=relevance](https://www.immoweb.be/en/search/apartment/for-rent?countries=BE&page=2&orderBy=relevance)
- [https://www.immoweb.be/en/classified/house/for-sale/ixelles/1050/21011976](https://www.immoweb.be/en/classified/house/for-sale/ixelles/1050/21011976)
- [https://www.immoweb.be/en/search/house/for-sale/brussels/district?countries=BE&page=2&orderBy=relevance](https://www.immoweb.be/en/search/house/for-sale/brussels/district?countries=BE&page=2&orderBy=relevance)

### Examples

#### Input

Scrape search results for all aparments that are for rent and scrape maximum of 100 results:

```
{
  "urls": { "url": "https://play.google.com/store/search?q=fitnes&c=apps&hl=en&gl=us" },
  "maxRecords": 100
}
```

#### Output

Listing Details

```
{
  "id": 21036106,
  "cluster": null,
  "customers": [
    {
      "id": 2513067,
      "type": "AGENCY",
      "email": "colorpro_bruxelles@importfrommedia.be",
      "logoUrl": "https://media.immowebstatic.be/customers/0012p00002W7ic4AAB/logo/e9288f089209f895c67ea15e0a9c91f7.jpg",
      "phoneNumber": null,
      "mobileNumber": "+32474232167",
      "name": "Color Properties",
      "website": "http://www.colorproperties.be",
      "location": {
        "country": "Belgium",
        "region": null,
        "province": "Brussels",
        "district": "Brussels",
        "locality": "Bruxelles",
        "postalCode": "1040",
        "street": "Rue Abbé Cuypers (étage 1) 3",
        "number": null,
        "box": null,
        "propertyName": null,
        "floor": null,
        "latitude": 50.87298357499019,
        "longitude": 4.375233506738514,
        "distance": null,
        "approximated": null,
        "regionCode": null,
        "type": null,
        "hasSeaView": null,
        "pointsOfInterest": null,
        "placeName": null
      },
      "ipiNo": "507206",
      "isOwner": true,
      "contactHoursMobile": "anytime",
      "contactHoursLandline": "anytime",
      "salesRepresentative": null,
      "features": {
        "page404": true,
        "investorFlag": false,
        "relatedClassifieds": true,
        "leafletsCTA": false,
        "leadQualification": true,
        "recommendation": true
      }
    }
  ],
  "premiumProjectPage": {
    "medias": null,
    "options": null,
    "promoter": null,
    "tabs": null
  },
  "flags": {
    "isPublicSale": false,
    "isNewClassified": true,
    "isNewPrice": false,
    "isInvestmentProject": false,
    "isNewlyBuilt": false,
    "isNotarySale": null,
    "isLifeAnnuitySale": false,
    "adQuality": null,
    "date": null,
    "priceSqm": null,
    "price": null,
    "default": null,
    "isSoldOrRented": false,
    "isLowEnergy": null,
    "percentSold": null,
    "isPassiveHouse": null,
    "isNewRealEstateProject": false,
    "isAnInteractiveSale": null,
    "isUnderOption": false
  },
  "media": {
    "pictures": [
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/802253f826c2de5b4c29a553ba4dc343.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/802253f826c2de5b4c29a553ba4dc343.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/802253f826c2de5b4c29a553ba4dc343.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/73e31a994328edfdecc8accd63eb84a2.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/73e31a994328edfdecc8accd63eb84a2.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/73e31a994328edfdecc8accd63eb84a2.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/ce066aa53d5b665c2bae68a0881e52de.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/ce066aa53d5b665c2bae68a0881e52de.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/ce066aa53d5b665c2bae68a0881e52de.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/9945e3a4901c8a8da5a0c6c125562585.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/9945e3a4901c8a8da5a0c6c125562585.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/9945e3a4901c8a8da5a0c6c125562585.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/58553aec1f509a218b0f863caa4abbff.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/58553aec1f509a218b0f863caa4abbff.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/58553aec1f509a218b0f863caa4abbff.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/3b1adea3f29a701dd8bc53b100862b49.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/3b1adea3f29a701dd8bc53b100862b49.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/3b1adea3f29a701dd8bc53b100862b49.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/98891e4cd924690927ee448c7a17123d.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/98891e4cd924690927ee448c7a17123d.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/98891e4cd924690927ee448c7a17123d.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/677b172ae042dc25f46c5159d4de20fa.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/677b172ae042dc25f46c5159d4de20fa.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/677b172ae042dc25f46c5159d4de20fa.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/b89140dee16ecd5fbdfc73d93ba4348b.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/b89140dee16ecd5fbdfc73d93ba4348b.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/b89140dee16ecd5fbdfc73d93ba4348b.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/50e7f82e909bbec6f67cf889c59562ab.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/50e7f82e909bbec6f67cf889c59562ab.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/50e7f82e909bbec6f67cf889c59562ab.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/7ab4c8b16e442905d86d8b2ef4f518ee.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/7ab4c8b16e442905d86d8b2ef4f518ee.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/7ab4c8b16e442905d86d8b2ef4f518ee.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/e84201f8ca75daabd8f768d11f76397a.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/e84201f8ca75daabd8f768d11f76397a.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/e84201f8ca75daabd8f768d11f76397a.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/70f13eff17958b6083022f875dd4cc13.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/70f13eff17958b6083022f875dd4cc13.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/70f13eff17958b6083022f875dd4cc13.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/9b9aef04eb45f248302e79011a27b0a5.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/9b9aef04eb45f248302e79011a27b0a5.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/9b9aef04eb45f248302e79011a27b0a5.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/d03d68002e1a9b4a9ed94089c18267be.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/d03d68002e1a9b4a9ed94089c18267be.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/d03d68002e1a9b4a9ed94089c18267be.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/a4bdc8708dc37ff2236f53ffcf9b53e4.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/a4bdc8708dc37ff2236f53ffcf9b53e4.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/a4bdc8708dc37ff2236f53ffcf9b53e4.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/224b0280317de860249402da6d8aa586.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/224b0280317de860249402da6d8aa586.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/224b0280317de860249402da6d8aa586.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/3399e1504513fa80b2fb157cde08ae4b.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/3399e1504513fa80b2fb157cde08ae4b.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/3399e1504513fa80b2fb157cde08ae4b.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/880dbfa1fe63af80c6b20833d7bb3bc6.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/880dbfa1fe63af80c6b20833d7bb3bc6.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/880dbfa1fe63af80c6b20833d7bb3bc6.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/6f62b3107423543c42b50e7aaa68f0b7.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/6f62b3107423543c42b50e7aaa68f0b7.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/6f62b3107423543c42b50e7aaa68f0b7.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/e364e20694da23cda3a9c8a9d385d516.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/e364e20694da23cda3a9c8a9d385d516.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/e364e20694da23cda3a9c8a9d385d516.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/6047e1c202770dac1ec648812a87a579.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/6047e1c202770dac1ec648812a87a579.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/6047e1c202770dac1ec648812a87a579.jpg",
        "isVertical": false
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/a4b437331ae69951008c9d7ccee6a032.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/a4b437331ae69951008c9d7ccee6a032.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/a4b437331ae69951008c9d7ccee6a032.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/2d68d480f0c00b2314ed888ce018c12a.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/2d68d480f0c00b2314ed888ce018c12a.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/2d68d480f0c00b2314ed888ce018c12a.jpg",
        "isVertical": true
      },
      {
        "smallUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/100x100/438891638b51d63bb2e6041d2b5b325b.jpg",
        "mediumUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/300x300/438891638b51d63bb2e6041d2b5b325b.jpg",
        "largeUrl": "https://media-resize.immowebstatic.be/classifieds/b923931a-4c52-4ee3-872b-e4a970b0ace6/736x736/438891638b51d63bb2e6041d2b5b325b.jpg",
        "isVertical": true
      }
    ],
    "virtualTourUrl": null,
    "floorPlans": null,
    "specifications": null,
    "virtualExperienceUrl": null
  },
  "property": {
    "type": "APARTMENT",
    "subtype": "PENTHOUSE",
    "title": "Standing 2B furnished apartment -garage- Montgomery",
    "description": "Immediately Available!  1ST CONTACT BY MAIL PLEASE.\nHigh standing apartment penthouse ( last floor with lift, 4/4) with 2 bedrooms, fully furnished, located on Avenue Vandendriessche 1C, next to Montgomery tube station.\nClose to green area and shops and transports..\nWooden floor. Entrance hall with living/dining areas. Fully fitted independant kitchen with balcony. Bathroom with bathtube and shower. Private laundry. 1 toilet. 2 large bedrooms.  Cellar in the basement. Possibility of box garage(150euros extra/month). For those looking for comfort, light and quality! LOCATION +++\nMonthly provision for building fees maintenance and private cold water = 125euros\nAll utilities ( heating on gas/electricity and water) on individual meters\n\nVisits info@colorproperties.be",
    "name": null,
    "isHolidayProperty": null,
    "bedroomCount": 2,
    "bedrooms": [
      {
        "surface": 13
      },
      {
        "surface": 10
      }
    ],
    "bathroomCount": 1,
    "bathrooms": [],
    "location": {
      "country": "Belgium",
      "region": "Brussels",
      "province": "Brussels",
      "district": "Brussels",
      "locality": "Woluwe-Saint-Pierre",
      "postalCode": "1150",
      "street": "Avenue Roger Vandendriessche",
      "number": "1",
      "box": null,
      "propertyName": null,
      "floor": 4,
      "latitude": 50.8349774,
      "longitude": 4.414238099999999,
      "distance": null,
      "approximated": null,
      "regionCode": "BRUSSELS",
      "type": "RESIDENTIAL",
      "hasSeaView": null,
      "pointsOfInterest": null,
      "placeName": null
    },
    "netHabitableSurface": 100,
    "roomCount": null,
    "monthlyCosts": 125,
    "attic": null,
    "hasAttic": null,
    "basement": {
      "surface": null
    },
    "hasBasement": true,
    "hasDressingRoom": null,
    "diningRoom": null,
    "hasDiningRoom": null,
    "building": {
      "annexCount": null,
      "condition": "AS_NEW",
      "constructionYear": 1960,
      "facadeCount": 2,
      "floorCount": 4,
      "streetFacadeWidth": null
    },
    "propertyCertificates": {
      "builtPlanStatus": null,
      "globalInsulationLevel": null,
      "oilTankCertificateStatus": null,
      "primaryEnergyConsumptionLevel": null,
      "hasAsbestosCertificate": null,
      "hasElectricalInstallationComplianceCertificate": true
    },
    "hasCaretakerOrConcierge": null,
    "hasDisabledAccess": true,
    "hasLift": true,
    "constructionPermit": {
      "constructionType": null,
      "floodZoneType": "NON_FLOOD_ZONE",
      "isObtained": null,
      "hasObligationToConstruct": null,
      "hasPlotDivisionAuthorization": null,
      "hasPossiblePriorityPurchaseRight": null,
      "isBreachingUrbanPlanningRegulation": null,
      "floodZoneIconUrl": null,
      "totalBuildableGroundFloorSurface": null,
      "urbanPlanningInformation": null,
      "pScore": null,
      "gScore": null
    },
    "energy": {
      "heatingType": "GAS",
      "hasHeatPump": null,
      "hasPhotovoltaicPanels": null,
      "hasThermicPanels": null,
      "hasCollectiveWaterHeater": null,
      "hasDoubleGlazing": true,
      "performance": null
    },
    "kitchen": {
      "surface": null,
      "type": "HYPER_EQUIPPED",
      "hasOven": null,
      "hasMicroWaveOven": null,
      "hasDishwasher": null,
      "hasWashingMachine": null,
      "hasFridge": null,
      "hasFreezer": null,
      "hasSteamOven": null
    },
    "land": null,
    "laundryRoom": {
      "surface": null
    },
    "hasLaundryRoom": true,
    "livingRoom": {
      "surface": 25
    },
    "hasLivingRoom": true,
    "isFirstOccupation": null,
    "hasBalcony": null,
    "hasBarbecue": null,
    "hasGarden": null,
    "gardenSurface": null,
    "gardenOrientation": null,
    "parkingCountIndoor": null,
    "parkingCountOutdoor": null,
    "parkingCountClosedBox": null,
    "hasAirConditioning": null,
    "hasArmoredDoor": true,
    "hasVisiophone": true,
    "hasSecureAccessAlarm": null,
    "hasCableTV": true,
    "hasDoorPhone": true,
    "hasInternet": null,
    "showerRoomCount": null,
    "showerRooms": [],
    "specificities": null,
    "toiletCount": 1,
    "toilets": [],
    "hasFitnessRoom": null,
    "hasTennisCourt": null,
    "hasSwimmingPool": false,
    "hasSauna": null,
    "hasJacuzzi": null,
    "hasHammam": null,
    "bedroomSurface": null,
    "alternativeDescriptions": {
      "fr": "Disponible immédiatement !  PREMIER CONTACT PAR E-MAIL SVP.\nAppartement penthouse haut de gamme (dernier étage avec ascenseur, 4/4) avec 2 chambres, entièrement meublé, situé avenue Vandendriessche 1C, à côté de la station de métro Montgomery.Proche d'espaces verts, des commerces et des transports.\nParquet à l'Honneur. Hall d'entrée avec salon/salle à manger. Cuisine indépendante entièrement équipée avec balcon. Salle de bains avec baignoire et douche. Buanderie privée. 1 WC. 2 grandes chambres.  Cave au sous-sol. Possibilité de garage (150 euros supplémentaires/mois). Pour ceux qui recherchent le confort, la lumière et la qualité ! EMPLACEMENT +++\nProvision mensuelle pour les frais d'entretien de l'immeuble et l'eau froide privée = 125 euros.\nTous les services publics (chauffage au gaz/électricité et eau) sont mesurés par des compteurs individuels.\n\nVisites info@colorproperties.be",
      "nl": "Immediately Available!  1ST CONTACT BY MAIL PLEASE.\nHigh standing apartment penthouse ( last floor with lift, 4/4) with 2 bedrooms, fully furnished, located on Avenue Vandendriessche 1C, next to Montgomery tube station.\nClose to green area and shops and transports..\nWooden floor. Entrance hall with living/dining areas. Fully fitted independant kitchen with balcony. Bathroom with bathtube and shower. Private laundry. 1 toilet. 2 large bedrooms.  Cellar in the basement. Possibility of box garage(150euros extra/month). For those looking for comfort, light and quality! LOCATION +++\nMonthly provision for building fees maintenance and private cold water = 125euros\nAll utilities ( heating on gas/electricity and water) on individual meters\n\nVisits info@colorproperties.be"
    },
    "habitableUnitCount": null,
    "fireplaceCount": null,
    "fireplaceExists": false,
    "hasTerrace": true,
    "terraceSurface": 3,
    "terraceOrientation": null
  },
  "publication": {
    "creationDate": "2025-09-21T16:59:20.789Z",
    "expirationDate": null,
    "publisherId": null,
    "visualisationOption": "XL",
    "lastModificationDate": "2025-09-21T16:59:27.332Z"
  },
  "transaction": {
    "type": "FOR_RENT",
    "subtype": "RENT_REGULAR",
    "availabilityPeriodType": "IMMEDIATELY",
    "availabilityDate": null,
    "certificates": {
      "carbonEmission": null,
      "primaryEnergyConsumptionPerSqm": 211,
      "primaryEnergyConsumptionYearly": null,
      "epcDescription": null,
      "epcReference": null,
      "epcScore": "E",
      "epcUrl": "https://media.immowebstatic.be/epc/en/pics/bxlD3.gif",
      "renovationObligation": null
    },
    "rental": {
      "monthlyRentalPrice": 1700,
      "monthlyRentalCosts": 125,
      "yearlyRentalPrice": null,
      "yearlyRentalPricePerSqm": null,
      "isFurnished": true,
      "areSmallPetsAllowed": null,
      "areBigPetsAllowed": null
    },
    "sale": null,
    "investor": {
      "isInvestmentProperty": false,
      "currentMonthlyRentalIncome": null,
      "currentReturnOnInvestment": null,
      "expectedMonthlyRentalIncome": null,
      "expectedMonthlyRentalIncomeDescription": null,
      "expectedReturnOnInvestment": null,
      "habitableUnitCount": null,
      "occupancyRate": null
    }
  },
  "priceType": null,
  "price": {
    "type": "residential_monthly_rent",
    "mainValue": 1700,
    "alternativeValue": null,
    "additionalValue": 125,
    "oldValue": null,
    "minRangeValue": null,
    "maxRangeValue": null,
    "mainDisplayPrice": "€1,700 (+ €125)",
    "HTMLDisplayPrice": "<span aria-hidden=\"true\">€1,700 (+ €125)</span>",
    "alternativeDisplayPrice": "",
    "oldDisplayPrice": null,
    "shortDisplayPrice": "€1.7K",
    "accessibilityPrice": "1700€ + 125€ per month",
    "label": "Requested monthly rental price",
    "date": null,
    "language": "en"
  },
  "externalReference": "7146407",
  "isBookmarked": false,
  "hasSectionsArray": {
    "hasGeneralSection": true,
    "hasInteriorSection": true,
    "hasExteriorSection": true,
    "hasFacilitiesSection": true,
    "hasEnergySection": true,
    "hasPlanningSection": true,
    "hasFinancialSection": true,
    "hasPublicSaleSection": false
  },
  "unitGroupings": [],
  "displayFlags": {
    "main": "new",
    "secondary": [],
    "percentSold": null
  },
  "statistics": {
    "bookmarkCount": 0,
    "viewCount": 0,
    "alertPrice": null,
    "creationDate": null,
    "description": null,
    "isAlertEmailSet": null,
    "rating": null,
    "wasOwnerContacted": null,
    "wasPropertyVisited": null
  },
  "url": "https://www.immoweb.be/en/classified/penthouse/for-rent/woluwe-saint-pierre/1150/21036106",
  "original_request_url": "https://www.immoweb.be/en/search/apartment/for-rent"
}
```

## Immoweb Scraper data output

The output from Immoweb Scraper is stored in the dataset. After the run is finished, you can download the dataset in various data formats (JSON, CSV, XML, RSS, HTML Table).

## ❓FAQ

### Do I need proxies to scrape search results from Immoweb Scraper?

Proxy for this scraper is already preconfigured for optimal performance.

## Support

For more custom/simplify outputs or Bug report please contact the developer (support (at) getmediumdata.com) or report an issue.