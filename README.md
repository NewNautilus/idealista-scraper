[Idealista Scraper](https://apify.com/skebby/idealista-scraper?fpr=data)

# Idealista Listings Scraper

Scrapes real estate listings from Idealista (Italy), filtered by a geographic polygon drawn on Idealista's map.

## Pricing

**$1.00 per 1,000 results** (billed via Apify pay-per-event at $0.001/item).

---

## Input

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `searchUrl` | string | Recommended | Paste any Idealista search URL with a drawn polygon (the `?shape=` parameter). Both plain and URL-encoded URLs are accepted. |
| `polygon` | array | Advanced | Alternative to `searchUrl`: polygon vertices as `[[lat, lng], ...]` (min 3 vertices). Ignored if `searchUrl` is provided. |
| `maxPages` | integer | No | Maximum number of result pages to fetch. Leave empty to fetch all pages. |
| `maxItems` | integer | No | Maximum number of listings to return overall. |
| `maxItemsPerPage` | integer | No | Items per API page (default: 50, max: 50). |

### How to get the search URL

1. Go to [idealista.it](https://www.idealista.it) and run a search
2. Click "Disegna area" (Draw area) and draw your polygon on the map
3. Copy the URL from your browser's address bar — it will contain `?shape=...`
4. Paste it as `searchUrl`

### Example input (URL-based)

```
{
    "searchUrl": "https://www.idealista.it/aree/vendita-case/?shape=%28%28ajetG%7DnzaA...%29%29"
}
```

### Example input (polygon coordinates)

```
{
    "polygon": [
        [45.41617, 10.95423],
        [45.42099, 10.96149],
        [45.41780, 10.96634],
        [45.41566, 10.96264],
        [45.41208, 10.96672],
        [45.40991, 10.96488],
        [45.41301, 10.95831]
    ],
    "maxPages": 2,
    "maxItems": 10
}
```

---

## Output

Each item in the dataset contains:

| Field | Type | Description |
| --- | --- | --- |
| `id` | string | Prefixed listing ID (e.g., `ide_35173114`) |
| `typology` | string | Property type (Appartamento, Casa, Attico, etc.) |
| `price_raw` | float | Listing price in EUR |
| `surface_sqm` | float | Surface area in m² |
| `rooms` | int | Number of rooms |
| `bedrooms` | int | Number of bedrooms |
| `bathrooms` | int | Number of bathrooms |
| `floor` | string | Floor number or description |
| `condition` | string | Property condition (Buono, Nuovo, Da ristrutturare, etc.) |
| `street` | string | Street address |
| `neighborhood` | string | Neighborhood name |
| `district` | string | District name |
| `latitude` | float | GPS latitude |
| `longitude` | float | GPS longitude |
| `agency_name` | string | Real estate agency name |
| `share_url` | string | Direct link to the Idealista listing |
| `image_cover` | string | Best available cover image URL returned by the API; this may still be signed and temporary |
| `image_cover_signed` | string | Original signed cover image URL, when the API only exposes a temporary signed variant |
| `image_cover_temporary` | bool | `true` when the available cover URL is signed and expected to expire |
| `image_expires_at` | string | ISO 8601 UTC expiration timestamp parsed from the signed image URL when available |
| `image_source` | string | Image source identifier, currently `idealista` |
| `image_cover_hd` | string | Higher-resolution cover image URL when available |
| `image_cover_original` | string | Original-size cover image URL when available |
| `image_cover_thumbnail` | string | Thumbnail cover image URL |
| `image_gallery` | array | Gallery image URLs, ordered and deduplicated |
| `has_parking` | bool | Has a parking space |
| `has_lift` | bool | Has an elevator |
| `created_at` | string | ISO 8601 scrape timestamp |

### Example output item

```
{
    "id": "ide_35173114",
    "typology": "Appartamento",
    "price_raw": 195000.0,
    "surface_sqm": 85.0,
    "rooms": 3,
    "bathrooms": 1,
    "floor": "3",
    "condition": "Buono",
    "street": "Via Mazzini",
    "neighborhood": "Centro Storico",
    "district": "Verona",
    "latitude": 45.4385,
    "longitude": 10.9916,
    "agency_name": "Agenzia Immobiliare XYZ",
    "share_url": "https://www.idealista.it/immobile/35173114/",
    "image_cover": "https://img3.idealista.it/s/v1/abcdef?Expires=1776868237&Signature=...",
    "image_cover_signed": "https://img3.idealista.it/s/v1/abcdef?Expires=1776868237&Signature=...",
    "image_cover_temporary": true,
    "image_expires_at": "2026-04-21T14:30:37+00:00",
    "image_source": "idealista",
    "image_cover_hd": "https://img3.idealista.it/immobile/1234567890_hd.jpg",
    "image_cover_original": "https://img3.idealista.it/immobile/1234567890_original.jpg",
    "image_cover_thumbnail": "https://img3.idealista.it/blur/...",
    "image_gallery": [
        "https://img3.idealista.it/immobile/1234567890.jpg",
        "https://img3.idealista.it/immobile/1234567891.jpg"
    ],
    "has_parking": false,
    "has_lift": true,
    "created_at": "2025-04-07T10:23:45+00:00"
}
```