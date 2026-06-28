[Idealista Scraper](https://apify.com/memo23/idealista-scraper?fpr=data)

# Idealista.com Scraper

There are two versions of the Idealista.com Scraper available:

- **Rentable Version:** [Idealista.com Scraper (Rent)](https://apify.com/memo23/apify-idealista-scraper-rental)
- **Pay Per Result Version:** [Idealista.com Scraper (Pay Per Result)](https://apify.com/memo23/apify-idealista-scraper)

**Unlock the Full Power of Idealista.com Real Estate Market Data** - The only scraper you need to track, analyze, and understand property listings on Idealista.com with enterprise-grade reliability and precision. Whether you're monitoring property trends, tracking specific locations, or conducting real estate market research, our scraper delivers comprehensive, real-time insights while saving you time and resources.

*"From residential properties and new developments to commercial real estate and luxury homes, we turn Idealista's property market data into your competitive advantage."*

## Overview

The Idealista.com Scraper is your go-to tool for extracting property listing data from Idealista.com. Ideal for real estate agents, property investors, market analysts, and researchers, it tracks property details, price information, and listing features across Spain's leading real estate platform. With easy setup and multiple export formats (JSON, CSV), it's perfect for anyone looking to gather comprehensive property market data from Idealista.com.

## What does Idealista.com Scraper do?

The Idealista.com Scraper is a powerful tool that enables you to:

### Comprehensive Data Collection

- **Property Listings**

- Extract complete property details and specifications
- Scrape price information and historical pricing data
- Gather comprehensive property descriptions and features
- Analyze property types and location characteristics
- Access contact details and listing information
- **Market Data**

- Scrape regional market trends and statistics
- Extract price per square meter information
- Gather property availability and inventory data
- Access neighborhood and location insights

### Advanced Scraping Capabilities

- **Pagination Handling**: Automatically navigates through all search result pages
- **Efficient Processing**: Processes only new or updated property listings in subsequent runs
- **Change Detection**: Identifies price changes, status updates, and new listings
- **Scheduled Monitoring**: Set up automated runs to keep your property market data current
- **Incremental Data Collection**: Build comprehensive real estate datasets over time

### Flexible Scraping Options

- **Property Listings**: Scrape individual property postings using property URLs

- Example: `https://www.idealista.com/inmueble/109366429/`
- **Search Results**: Extract property listings by search criteria

- Example: `https://www.idealista.com/venta-viviendas/madrid/`
- **Filtered Searches**: Apply advanced filters directly in the URL

- Example: `https://www.idealista.com/en/geo/venta-obranueva/andalucia/con-2-dormitorios,3-dormitorios/?ordenado-por=precios-asc`
- **New Developments**: Target specific new development listings

- Example: `https://www.idealista.com/obra-nueva/109366429/`

This tool is ideal for:

- Real estate market research and analysis
- Property price analysis and competitive intelligence
- Market trend analysis across various regions
- Building property databases for investment decisions
- Tracking price trends and market performance in real estate

## Features

- **Comprehensive Data Extraction**: Detailed property listing information, prices, and agent profiles
- **Dual Scraping Modes**:

- **Search Results**: Scrape all property listings from search results (e.g., `https://www.idealista.com/venta-viviendas/madrid/`)
- **Individual Listings**: Target specific property postings using direct URLs (e.g., `https://www.idealista.com/inmueble/109366429/`)
- **Flexible Input**: Supports multiple input formats:

- Search result URLs (e.g., `https://www.idealista.com/venta-viviendas/madrid/`)
- Direct property listing URLs (e.g., `https://www.idealista.com/inmueble/109366429/`)
- New development URLs (e.g., `https://www.idealista.com/obra-nueva/109366429/`)
- Custom search criteria with advanced filters
- **Automatic Pagination**: Handles multi-page results automatically across all search types
- **Efficient Processing**: Concurrent scraping with configurable concurrency settings
- **Reliable Performance**: Built-in retry mechanisms and proxy support
- **Structured Data Export**: Download property listing data in JSON or CSV format for analysis

## How to Use

### Scraping Property Listings

To scrape property listings:

1. **Set Up**: Ensure you have an Apify account and access to the Apify platform.
2. **Configure Input**: Provide the search URL or specific property listing URL:

- `https://www.idealista.com/venta-viviendas/madrid/`
- `https://www.idealista.com/inmueble/109366429/`
- `https://www.idealista.com/obra-nueva/109366429/`
3. **Adjust Settings**: Configure options like max items, monitoring mode, and proxy settings as needed.
4. **Run the Scraper**: Execute the scraper on the Apify platform.
5. **Data Collection**: The scraper will output all available property listing data.

## Input Configuration

Here's an example of how to set up the input for the Idealista.com Scraper:

```
{
    "startUrls": [
        {
            "url": "https://www.idealista.com/venta-viviendas/madrid/"
        },
        {
            "url": "https://www.idealista.com/en/geo/venta-obranueva/andalucia/con-2-dormitorios,3-dormitorios/?ordenado-por=precios-asc"
        },
        {
            "url": "https://www.idealista.com/inmueble/109366429/"
        }
    ],
    "maxItems": 1000,
    "monitoringMode": false,
    "maxConcurrency": 10,
    "minConcurrency": 1,
    "maxRequestRetries": 100,
    "proxyConfiguration": {
        "useApifyProxy": true
    }
}
```

### Input Fields Explanation

- `startUrls`: Array of objects containing one of these formats:

- Search URL: `{"url": "https://www.idealista.com/venta-viviendas/madrid/"}`
- Property Listing URL: `{"url": "https://www.idealista.com/inmueble/109366429/"}`
- New Development URL: `{"url": "https://www.idealista.com/obra-nueva/109366429/"}`
- `maxItems`: Maximum number of items to scrape (default: 1000).
- `monitoringMode`: When enabled, only scrapes new listings compared to previous runs (default: false).
- `maxConcurrency`: Maximum number of pages processed simultaneously (default: 10).
- `minConcurrency`: Minimum number of pages processed simultaneously (default: 1).
- `maxRequestRetries`: Number of retries for failed requests (default: 100).
- `proxyConfiguration`: Proxy settings for enhanced scraping reliability.

## Monitoring Mode

When `monitoringMode` is enabled, the scraper will only collect new listings that haven't been seen in previous runs. This is useful for:

- Tracking new property listings as they come on the market
- Building a historical archive of property data
- Monitoring specific areas for new opportunities without duplicating data

### How Monitoring Mode Works

1. The scraper maintains a record of previously scraped property listing IDs
2. On subsequent runs with `monitoringMode: true`, it checks each property against this record
3. Only new properties (those not in the record) are processed and added to the output
4. The record is updated with any new property IDs found

## Output Structure

The scraper provides comprehensive information about Idealista.com property listings. The output includes detailed property information, agent details, location data, and multimedia content. Sample output will be provided in future updates.

```
{
  "adid": 109195360,
  "price": 2500000,
  "priceInfo": {
      "amount": 2500000,
      "currencySuffix": "€"
  },
  "operation": "sale",
  "propertyType": "homes",
  "extendedPropertyType": "chalet",
  "homeType": "chalet",
  "state": "active",
  "multimedia": {
      "images": [
          {
              "url": "https://img4.idealista.com/blur/WEB_DETAIL-L-L/0/id.pro.es.image.master/fe/de/51/1367093735.webp",
              "tag": "facade",
              "localizedName": "Facade",
              "multimediaId": 1367093735,
              "deeplinkUrl": "https://www.idealista.com/en/inmueble/109195360/foto/1/?utm_medium=socialmedia&utm_campaign=private_sendadpicturetofriend&utm_source=notifications",
              "madeByIdealista": false,
              "width": 1500,
              "height": 844
          },
          {
              "url": "https://img4.idealista.com/blur/WEB_DETAIL-L-L/0/id.pro.es.image.master/82/03/e6/1367219884.webp",
              "tag": "plan",
              "localizedName": "Plan",
              "multimediaId": 1367219884,
              "deeplinkUrl": "https://www.idealista.com/en/inmueble/109195360/plano/1/?utm_medium=socialmedia&utm_campaign=private_sendadpicturetofriend&utm_source=notifications",
              "madeByIdealista": false,
              "width": 1489,
              "height": 820
          },
          ...
      ],
      "videos": [],
      "hasMultimediasMadeByIdealista": false
  },
  "propertyComment": "Villa de lujo de obra nueva con piscina y spa en El Campanario Golf – Nueva Milla de Oro\n\nFINAL OBRA PRIMAVERA 2026\n\nVilla 4 es una joya arquitectónica que combina líneas modernas, materiales de primera calidad y una calidez atemporal que la hace acogedora todo el año.\n\nDormitorios: 4\nBaños: 3 + 1 aseo\nParcela: 680,93 m²\nConstruidos: 529,56 m²\nTerrazas: 121,35 m²\nPiscina privada independiente\nSpa en la terraza de la suite principal\nSauna privada y espacio para gimnasio incluidos\nPlacas solares integradas\nDomótica avanzada y sistema de sonido Bose\n\nEn la planta baja, el salón-comedor abierto conecta con la cocina de diseño y la zona exterior con porche y piscina privada. Dispone también de un dormitorio de invitados/despacho y un aseo.\n\nEn la planta superior, la suite principal ofrece vestidor, baño en suite y salida a una terraza privada con spa y vistas. Dos dormitorios adicionales y un baño completo completan este nivel.\n\nEl sótano de 157 m² con luz natural incluye sauna y espacio para gimnasio, además de un área polivalente ideal como sala de cine o de entretenimiento.\n\nExtras disponibles: vinoteca climatizada, equipamiento de gimnasio, servicio de diseño de interiores, sistema de seguridad con videovigilancia y gestión de la propiedad con conserge y limpieza premium.\n\nUna villa nueva que redefine el estilo de vida en Marbella: lujo, confort y sostenibilidad.",
  "ubication": {
      "title": "Calle Ágata, 2",
      "latitude": 36.476812,
      "longitude": -5.0222844,
      "hasHiddenAddress": false,
      "administrativeAreaLevel4": "Nueva Atalaya",
      "administrativeAreaLevel3": "Benamara - Atalaya",
      "administrativeAreaLevel2": "Estepona",
      "administrativeAreaLevel1": "Málaga",
      "locationId": "0-EU-ES-29-07-001-051-07-007",
      "administrativeAreaLevel1Id": "0-EU-ES-29",
      "locationName": "Nueva Atalaya, Estepona"
  },
  "country": "es",
  "contactInfo": {
      "commercialName": "ATTA VILLAS",
      "phone1": {
          "phoneNumber": "951120041",
          "formattedPhone": "951 12 00 41",
          "prefix": "34",
          "phoneNumberForMobileDialing": "+34951120041",
          "nationalNumber": true,
          "formattedPhoneWithPrefix": "+34 951 12 00 41"
      },
      "contactName": "Boren Brothers SL. .",
      "externalReference": "Villa 4",
      "userType": "developer",
      "agencyLogo": "https://st3.idealista.com/22/0c/ed/villas-atta.gif",
      "contactMethod": "all",
      "micrositeShortName": "villas-atta",
      "address": {
          "streetName": "Ágata",
          "streetNumber": 2,
          "locationName": "Estepona",
          "postalCode": "29688"
      },
      "agentInfo": {
          "name": "Boren Brothers SL. .",
          "proAgent": false
      },
      "inVirtualMicrosite": false,
      "sharedSeekerProfile": false,
      "totalAds": 0,
      "needLoginForContact": false,
      "chatEnabled": false,
      "professional": true
  },
  "moreCharacteristics": {
      "roomNumber": 4,
      "bathNumber": 4,
      "plotOfLand": 681,
      "housingFurnitures": "unknown",
      "agencyIsABank": false,
      "energyCertificationType": "inProcess",
      "swimmingPool": true,
      "modificationDate": 1758214533000,
      "chaletType": "independantHouse",
      "constructedArea": 530,
      "garden": true,
      "boxroom": true,
      "buildTypeEnergyCertification": "project",
      "status": "newdevelopment"
  },
  "translatedTexts": {
      "characteristicsDescriptions": [
          {
              "key": "newDevelopment",
              "title": "new home",
              "detailFeatures": [
                  {
                      "phrase": "Atta Villas"
                  },
                  {
                      "phrase": "Detached houses of 4 bedrooms"
                  },
                  {
                      "phrase": "for sale"
                  }
              ]
          },
          {
              "key": "features",
              "title": "Basic features",
              "detailFeatures": [
                  {
                      "phrase": "Detached house"
                  },
                  {
                      "phrase": "3 floors"
                  },
                  {
                      "phrase": "530 m² constructed"
                  },
                  {
                      "phrase": "4 bedrooms"
                  },
                  {
                      "phrase": "4 bathrooms"
                  },
                  {
                      "phrase": "Land of 681 m²"
                  },
                  {
                      "phrase": "Terrace and balcony"
                  },
                  {
                      "phrase": "Parking space included in the price"
                  },
                  {
                      "phrase": "New home development"
                  },
                  {
                      "phrase": "Storage room"
                  }
              ]
          },
          {
              "key": "equipment",
              "title": "Equipment",
              "detailFeatures": [
                  {
                      "phrase": "Air conditioning"
                  },
                  {
                      "phrase": "Swimming pool"
                  },
                  {
                      "phrase": "Garden"
                  }
              ]
          },
          {
              "key": "costs",
              "title": "Price",
              "detailFeatures": [
                  {
                      "phrase": "2,500,000 €"
                  },
                  {
                      "phrase": "4,717 €/m²"
                  }
              ]
          }
      ]
  },
  "suggestedTexts": {
      "title": "Detached house in calle Ágata, 2"
  },
  "detailedType": {
      "typology": "chalet",
      "subTypology": "independantHouse"
  },
  "comments": [
      {
          "propertyComment": "Luxuriöse Neubauvilla mit Pool und Spa in El Campanario Golf – Neue Goldene Meile\n\nFERTIGSTELLUNG FRÜHJAHR 2026\n\nVilla 4 ist ein architektonisches Juwel, das moderne Linien, hochwertige Materialien und eine zeitlose Wärme vereint, die sie das ganze Jahr über einladend macht.\n\nSchlafzimmer: 4\nBäder: 3 + 1 Gäste-WC\nGrundstück: 680,93 m²\nBebaute Fläche: 529,56 m²\nTerrassen: 121,35 m²\nUnabhängiger privater Pool\nSpa auf der Terrasse der Master-Suite\nPrivate Sauna und Platz für ein Fitnessstudio inklusive\nIntegrierte Solarzellen\nFortschrittliche Hausautomation und Bose-Soundsystem\n\nIm Erdgeschoss verbindet das offene Wohn-Esszimmer die Designerküche mit dem Außenbereich mit Veranda und privatem Pool. Es gibt auch ein Gästezimmer/Büro und eine Toilette.\n\nIm Obergeschoss bietet die Master-Suite ein Ankleidezimmer, ein Badezimmer en suite und Zugang zu einer privaten Terrasse mit Spa und Aussicht. Zwei weitere Schlafzimmer und ein komplettes Badezimmer vervollständigen diese Ebene.\n\nDer 157 m² große Keller mit Tageslicht umfasst eine Sauna und einen Bereich für ein Fitnessstudio sowie einen Mehrzweckbereich, der sich ideal als Kino oder Unterhaltungsraum eignet.\n\nVerfügbare Extras: klimatisierter Weinkeller, Fitnessgeräte, Innenarchitektur-Service, Sicherheitssystem mit Videoüberwachung und Immobilienverwaltung mit Concierge- und Premium-Reinigung.\n\nEine neue Villa, die den Lebensstil in Marbella neu definiert: Luxus, Komfort und Nachhaltigkeit.",
          "autoTranslated": true,
          "language": "de",
          "defaultLanguage": false
      },
      {
          "propertyComment": "Luksuriøs nybygd villa med basseng og spa i El Campanario Golf – Nueva Milla de Oro\n\nFERDIGSTILLELSE VÅREN 2026\n\nVilla 4 er en arkitektonisk juvel som kombinerer moderne linjer, førsteklasses materialer og en tidløs varme som gjør den innbydende hele året.\n\nSoverom: 4\nBaderom: 3 + 1 toalett\nTomt: 680,93 m²\nBebygd areal: 529,56 m²\nTerrasser: 121,35 m²\nPrivat, frittstående basseng\nSpa på terrassen til hovedsuiten\nPrivat badstue og plass for treningsstudio inkludert\nIntegrerte solcellepaneler\nAvansert domotikk og Bose lydanlegg\n\nI første etasje kobles den åpne stue-spisestuen til designerkjøkkenet og uteområdet med veranda og privat basseng. Det er også et gjesterom/kontor og et toalett.\n\nI øverste etasje tilbyr hovedsuiten et omkledningsrom, bad en suite og utgang til en privat terrasse med spa og utsikt. To ekstra soverom og et komplett bad fullfører dette nivået.\n\nKjelleren på 157 m² med naturlig lys inkluderer badstue og plass for treningsstudio, i tillegg til et allsidig område som er ideelt som kino eller underholdningsrom.\n\nTilgjengelige tillegg: klimastyrt vinkjeller, treningsutstyr, interiørdesigntjeneste, sikkerhetssystem med videoovervåking og eiendomsforvaltning med concierge og premium rengjøring.\n\nEn ny villa som redefinerer livsstilen i Marbella: luksus, komfort og bærekraft.",
          "autoTranslated": true,
          "language": "nb",
          "defaultLanguage": false
      },
      {
          "propertyComment": "Contemporary new construction villa with pool and spa in El Campanario Golf – Marbella/Estepona\n\nNEW CONSTRUCTION\n\nVilla 5 offers a modern and timeless style in a privileged location on the New Golden Mile. Its architecture combines clean lines, top quality materials and open spaces bathed in natural light.\n\nBedrooms: 4\nBathrooms: 3 + 1 toilet\nPlot: 567.32 m²\nBuilt: 525.97 m²\nTerraces: 106.20 m²\nIndependent private pool\nPrivate sauna and gym space included\nIntegrated solar panels\nAdvanced home automation and Bose sound system\n\nOn the ground floor, the open-plan living-dining room connects to the fully equipped kitchen and the outdoor porch next to the pool. It also includes a guest bedroom/office and guest toilet.\n\nThe upper floor houses the master suite with dressing room, en-suite bathroom and private terrace, along with two additional bedrooms and a shared bathroom.\n\nThe 174 m² basement with natural light has a garage for two vehicles, a multipurpose room, sauna and gym space, as well as a technical room.\n\nOptional extras: gym equipment, climate-controlled wine cellar, interior design service, video surveillance security system and comprehensive property and luxury vacation management.\n\nVilla 5 is designed for those looking for an exclusive, sustainable and comfortable home on the Costa del Sol.",
          "autoTranslated": false,
          "language": "en",
          "defaultLanguage": false
      },
      {
          "propertyComment": "Villa de lujo de obra nueva con piscina y spa en El Campanario Golf – Nueva Milla de Oro\n\nFINAL OBRA PRIMAVERA 2026\n\nVilla 4 es una joya arquitectónica que combina líneas modernas, materiales de primera calidad y una calidez atemporal que la hace acogedora todo el año.\n\nDormitorios: 4\nBaños: 3 + 1 aseo\nParcela: 680,93 m²\nConstruidos: 529,56 m²\nTerrazas: 121,35 m²\nPiscina privada independiente\nSpa en la terraza de la suite principal\nSauna privada y espacio para gimnasio incluidos\nPlacas solares integradas\nDomótica avanzada y sistema de sonido Bose\n\nEn la planta baja, el salón-comedor abierto conecta con la cocina de diseño y la zona exterior con porche y piscina privada. Dispone también de un dormitorio de invitados/despacho y un aseo.\n\nEn la planta superior, la suite principal ofrece vestidor, baño en suite y salida a una terraza privada con spa y vistas. Dos dormitorios adicionales y un baño completo completan este nivel.\n\nEl sótano de 157 m² con luz natural incluye sauna y espacio para gimnasio, además de un área polivalente ideal como sala de cine o de entretenimiento.\n\nExtras disponibles: vinoteca climatizada, equipamiento de gimnasio, servicio de diseño de interiores, sistema de seguridad con videovigilancia y gestión de la propiedad con conserge y limpieza premium.\n\nUna villa nueva que redefine el estilo de vida en Marbella: lujo, confort y sostenibilidad.",
          "autoTranslated": false,
          "language": "es",
          "defaultLanguage": true
      },
      {
          "propertyComment": "Luxe nieuwbouwvilla met zwembad en spa in El Campanario Golf – Nieuwe Gouden Mijl\n\nEINDOPLEVERING LENTE 2026\n\nVilla 4 is een architectonisch juweel dat moderne lijnen, hoogwaardige materialen en een tijdloze warmte combineert, waardoor het het hele jaar door gastvrij is.\n\nSlaapkamers: 4\nBadkamers: 3 + 1 toilet\nPerceel: 680,93 m²\nBebouwd: 529,56 m²\nTerrassen: 121,35 m²\nOnafhankelijk privézwembad\nSpa op het terras van de master suite\nPrivésauna en ruimte voor een fitnessruimte inbegrepen\nGeïntegreerde zonnepanelen\nGeavanceerde domotica en Bose-geluidssysteem\n\nOp de begane grond verbindt de open woon-eetkamer met de designkeuken en de buitenruimte met veranda en privézwembad. Er is ook een gastenslaapkamer/kantoor en een toilet.\n\nOp de bovenverdieping biedt de master suite een kleedkamer, een badkamer en suite en toegang tot een privéterras met spa en uitzicht. Twee extra slaapkamers en een complete badkamer maken dit niveau compleet.\n\nDe kelder van 157 m² met natuurlijk licht omvat een sauna en ruimte voor een fitnessruimte, evenals een multifunctionele ruimte die ideaal is als bioscoop of entertainmentruimte.\n\nBeschikbare extra's: geklimatiseerde wijnkelder, fitnessapparatuur, interieurontwerp service, beveiligingssysteem met videobewaking en property management met conciërge en premium schoonmaak.\n\nEen nieuwe villa die de levensstijl in Marbella herdefinieert: luxe, comfort en duurzaamheid.",
          "autoTranslated": true,
          "language": "nl",
          "defaultLanguage": false
      }
  ],
  "detailWebLink": "https://www.idealista.com/inmueble/109195360/?utm_medium=socialmedia&utm_campaign=private_sendadtofriend&utm_source=notifications",
  "energyCertification": {
      "title": "Energy certificate of the project",
      "energyConsumption": {
          "type": "inProcess"
      },
      "text": "In progress"
  },
  "allowsCounterOffers": true,
  "allowsRemoteVisit": false,
  "allowsMortgageSimulator": true,
  "allowsProfileQualification": false,
  "promotion": {
      "promotionId": 109190794,
      "name": "Atta Villas ",
      "description": "Detached houses of 4 bedrooms for sale",
      "price": 1800000,
      "promotionType": "notFinished"
  },
  "tracking": {
      "isSuitableForRecommended": true,
      "commercialDataId": 260436139
  },
  "has360VHS": false,
  "labels": [
      {
          "name": "luxuryType",
          "text": "Luxury"
      },
      {
          "name": "villaType",
          "text": "Villa"
      }
  ],
  "showSuggestedPrice": false,
  "allowsRecommendation": true,
  "modificationDate": {
      "value": 1758214533000,
      "text": "Listing updated 10 days ago"
  },
  "basicInfo": {
      "propertyCode": "109195360",
      "thumbnail": "https://img4.idealista.com/blur/480_360_mq/0/id.pro.es.image.master/fe/de/51/1367093735.webp",
      "externalReference": "Villa 4",
      "numPhotos": 13,
      "price": 2500000,
      "priceInfo": {
          "price": {
              "amount": 2500000,
              "currencySuffix": "€"
          }
      },
      "propertyType": "chalet",
      "operation": "sale",
      "size": 530,
      "rooms": 4,
      "bathrooms": 4,
      "address": "calle Ágata, 2",
      "province": "Málaga",
      "municipality": "Estepona",
      "district": "Benamara - Atalaya",
      "country": "es",
      "neighborhood": "Nueva Atalaya",
      "locationId": "0-EU-ES-29-07-001-051-07-007",
      "latitude": 36.476812,
      "longitude": -5.0222844,
      "showAddress": true,
      "url": "https://www.idealista.com/obra-nueva/109195360/",
      "description": "Contemporary new construction villa with pool and spa in El Campanario Golf – Marbella/Estepona NEW CONSTRUCTION Villa 5 offers a modern and timeless style in a privileged location on the New Golden Mile. Its architecture combines clean lines, top quality materials and open spaces bathed in natural light. Bedrooms: 4 Bathrooms: 3 + 1 toilet Plot: 567.32 m² Built: 525.97 m² Terraces: 106.20 m² Independent private pool Private sauna and gym space included Integrated solar panels Advanced home automation and Bose sound system On the ground floor, the open-plan living-dining room connects to the fully equipped kitchen and the outdoor porch next to the pool. It also includes a guest bedroom/office and guest toilet. The upper floor houses the master suite with dressing room, en-suite bathroom and private terrace, along with two additional bedrooms and a shared bathroom. The 174 m² basement with natural light has a garage for two vehicles, a multipurpose room, sauna and gym space, as well as a technical room. Optional extras: gym equipment, climate-controlled wine cellar, interior design service, video surveillance security system and comprehensive property and luxury vacation management. Villa 5 is designed for those looking for an exclusive, sustainable and comfortable home on the Costa del Sol.",
      "hasVideo": false,
      "status": "newdevelopment",
      "newDevelopment": true,
      "favourite": false,
      "newProperty": false,
      "multimedia": {
          "images": [
              {
                  "url": "https://img4.idealista.com/blur/480_360_mq/0/id.pro.es.image.master/fe/de/51/1367093735.webp",
                  "tag": "facade"
              }
          ]
      },
      "contactInfo": {
          "commercialName": "ATTA VILLAS",
          "phone1": {
              "phoneNumber": "951120041",
              "formattedPhone": "951 12 00 41",
              "prefix": "34",
              "phoneNumberForMobileDialing": "+34951120041",
              "nationalNumber": true
          },
          "contactName": "Boren Brothers SL.",
          "userType": "professional",
          "agencyLogo": "https://st3.idealista.com/22/0c/ed/villas-atta.gif",
          "contactMethod": "all",
          "micrositeShortName": "villas-atta",
          "totalAds": 0,
          "needLoginForContact": false
      },
      "parkingSpace": {
          "hasParkingSpace": true,
          "isParkingSpaceIncludedInPrice": true
      },
      "newDevelopmentFinished": false,
      "priceByArea": 4717,
      "features": {
          "hasSwimmingPool": true,
          "hasTerrace": true,
          "hasAirConditioning": true,
          "hasBoxRoom": true,
          "hasGarden": true
      },
      "detailedType": {
          "typology": "chalet",
          "subTypology": "independantHouse"
      },
      "suggestedTexts": {
          "subtitle": "Nueva Atalaya, Estepona",
          "title": "Detached house in calle Ágata, 2"
      },
      "hasPlan": true,
      "has3DTour": false,
      "has360": false,
      "hasStaging": false,
      "labels": [
          {
              "name": "luxuryType",
              "text": "Luxury"
          },
          {
              "name": "villaType",
              "text": "Villa"
          }
      ],
      "savedAd": {},
      "ribbons": [
          {
              "name": "newDevelopment",
              "text": "New development"
          }
      ],
      "notes": [],
      "topNewDevelopment": false,
      "newDevelopmentHighlight": false,
      "topPlus": false,
      "preferenceHighlight": false,
      "topHighlight": false,
      "urgentVisualHighlight": false,
      "visualHighlight": false
  }
}
```

## Output Fields Explanation

This section provides a detailed breakdown of all fields in the JSON output from the Idealista.com Scraper. The output is organized into logical sections for easy reference.

### Main Property Data

- `adid` (Number): Unique property identifier used by Idealista
- `price` (Number): Property price in euros
- `priceInfo` (Object): Detailed price information

- `amount` (Number): Price amount
- `currencySuffix` (String): Currency symbol (e.g., "€")
- `operation` (String): Type of operation ("sale", "rent")
- `propertyType` (String): General property category (e.g., "homes")
- `extendedPropertyType` (String): Specific property type (e.g., "chalet")
- `homeType` (String): Home classification (e.g., "chalet")
- `state` (String): Property listing status (e.g., "active")

### Multimedia Content

- `multimedia` (Object): Media content for the property

- `images` (Array): Property images

- `url` (String): Direct image URL
- `tag` (String): Image category (facade, plan, livingRoom, bedroom, etc.)
- `localizedName` (String): Human-readable image type
- `multimediaId` (Number): Unique image identifier
- `deeplinkUrl` (String): Shareable image URL
- `madeByIdealista` (Boolean): Whether image was created by Idealista
- `width` (Number): Image width in pixels
- `height` (Number): Image height in pixels
- `videos` (Array): Property videos (if any)
- `hasMultimediasMadeByIdealista` (Boolean): If any media was created by Idealista

### Property Description

- `propertyComment` (String): Detailed property description in the default language
- `comments` (Array): Multi-language property descriptions

- `propertyComment` (String): Description text
- `autoTranslated` (Boolean): Whether the text was automatically translated
- `language` (String): Language code (es, en, de, etc.)
- `defaultLanguage` (Boolean): If this is the original language

### Location Information

- `ubication` (Object): Property location details

- `title` (String): Street address
- `latitude` (Number): GPS latitude coordinate
- `longitude` (Number): GPS longitude coordinate
- `hasHiddenAddress` (Boolean): If exact address is hidden
- `administrativeAreaLevel4` (String): Neighborhood name
- `administrativeAreaLevel3` (String): District name
- `administrativeAreaLevel2` (String): City name
- `administrativeAreaLevel1` (String): Province name
- `locationId` (String): Unique location identifier
- `locationName` (String): Formatted location string

### Contact Information

- `contactInfo` (Object): Agent/seller contact details

- `commercialName` (String): Business/agency name
- `phone1` (Object): Primary phone contact

- `phoneNumber` (String): Raw phone number
- `formattedPhone` (String): Formatted phone for display
- `prefix` (String): Country code
- `phoneNumberForMobileDialing` (String): International format
- `formattedPhoneWithPrefix` (String): Full formatted number
- `contactName` (String): Contact person name
- `externalReference` (String): Property reference from agent
- `userType` (String): Type of seller (developer, professional, private)
- `agencyLogo` (String): URL to agency logo
- `contactMethod` (String): Available contact methods
- `professional` (Boolean): If seller is a professional/agency

### Property Characteristics

- `moreCharacteristics` (Object): Detailed property features

- `roomNumber` (Number): Number of bedrooms
- `bathNumber` (Number): Number of bathrooms
- `plotOfLand` (Number): Land area in square meters
- `housingFurnitures` (String): Furniture status ("furnished", "unfurnished", "unknown")
- `agencyIsABank` (Boolean): If seller is a bank
- `energyCertificationType` (String): Energy certificate status
- `swimmingPool` (Boolean): Has swimming pool
- `modificationDate` (Number): Last modification timestamp
- `chaletType` (String): Type of house (independantHouse, townhouse, etc.)
- `constructedArea` (Number): Built area in square meters
- `garden` (Boolean): Has garden
- `boxroom` (Boolean): Has storage room
- `status` (String): Property development status

### Feature Descriptions

- `translatedTexts` (Object): Organized feature descriptions

- `characteristicsDescriptions` (Array): Feature categories

- `key` (String): Category identifier (features, equipment, costs, etc.)
- `title` (String): Category display name
- `detailFeatures` (Array): Individual features in this category

- `phrase` (String): Feature description

### Property Details

- `detailedType` (Object): Specific property classification

- `typology` (String): Main property type
- `subTypology` (String): Specific subtype
- `detailWebLink` (String): Direct URL to property page
- `energyCertification` (Object): Energy efficiency information
- `allowsCounterOffers` (Boolean): If counter-offers are accepted
- `allowsRemoteVisit` (Boolean): If virtual visits are available
- `allowsMortgageSimulator` (Boolean): If mortgage calculator is available

### Development Information (for new constructions)

- `promotion` (Object): New development details

- `promotionId` (Number): Development project ID
- `name` (String): Development name
- `description` (String): Development description
- `price` (Number): Starting price for development
- `promotionType` (String): Development status

### Property Labels and Features

- `labels` (Array): Property tags

- `name` (String): Label identifier (luxuryType, villaType, etc.)
- `text` (String): Display text for label
- `basicInfo` (Object): Summary property information

- `thumbnail` (String): Main property image thumbnail
- `externalReference` (String): Agent's property reference
- `numPhotos` (Number): Total number of photos
- `features` (Object): Key property features (boolean flags)

- `hasSwimmingPool` (Boolean)
- `hasTerrace` (Boolean)
- `hasAirConditioning` (Boolean)
- `hasBoxRoom` (Boolean)
- `hasGarden` (Boolean)

---

## Explore More Scrapers

If you found this Apify Idealista.com Scraper useful, be sure to check out our other powerful scrapers and actors at [memo23's Apify profile](https://apify.com/memo23). We offer a wide range of tools to enhance your web scraping and automation needs across various platforms and use cases.

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