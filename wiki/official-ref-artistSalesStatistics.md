Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Sales statistics of an artist over one reporting window. Every attribute other than windowPeriod, startDate, endDate, dataThrough, lastModifiedAt and status is present only when status is OK.

#### Resource `artistSalesStatistics`
| Attribute | Type | Description |
|---|---|---|
| `buyerSources` (optional) | ArtistSalesStatistics_BuyerSources | Where buyers came from. items is present exactly when status is OK, and an empty items is a measured empty result |
| `byType` (optional) | ArtistSalesStatistics_ByType | Net sales by product type |
| `currency` (optional) | string (USD) | Currency of every amount |
| `dataThrough` | string (date) | Last day included in the underlying data |
| `endDate` | string (date) | Last day of the window, inclusive |
| `itemsSold` (optional) | integer (int64) | Items sold in the window |
| `lastModifiedAt` | string (date-time) | When these statistics were computed |
| `netSales` (optional) | ArtistSalesStatistics_NetSales | Sold minus refunded in the window. previousAmount is the same for the previous window of the same length and is absent when there is no earlier window to compare with |
| `orders` (optional) | integer (int64) | Orders in the window |
| `refunds` (optional) | ArtistSalesStatistics_Refunds | Refunds in the window. amount is the total refunded |
| `series` (optional) | ArtistSalesStatistics_Series | Net sales per bucket |
| `startDate` | string (date) | First day of the window |
| `status` | string (OK, NOT_SET_UP, UNAVAILABLE) | Status of sales statistics. NOT_SET_UP: the artist has not set up sales. UNAVAILABLE: not available at the moment |
| `windowPeriod` | ArtistStatisticsWindowPeriod (P7D, P28D, P12M) | Reporting window preset. startDate and endDate give the actual data coverage |

Relationships (`include=`): `artist`, `topSellers`

### Get multiple artistSalesStatistics
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistSalesStatistics```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple artistSalesStatistics by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[artist.id]` | query | yes | string[] | Artist ID. Every published range of the artist is returned (e.g. `1566`) |
| `include` | query |  | string[] | Include related resources. Available relationships: artist, topSellers |
| `includeLinkage` | query |  | string[]: artist, topSellers | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistSalesStatistics/{id}/relationships/artist```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The list answered `200` without data: statistics only exist for artist accounts with sales.

Retrieves artist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist sales statistics id |
| `include` | query |  | string[] | Include related resources. Available relationships: artist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get topSellers relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistSalesStatistics/{id}/relationships/topSellers```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The list answered `200` without data: statistics only exist for artist accounts with sales.

Retrieves topSellers relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist sales statistics id |
| `include` | query |  | string[] | Include related resources. Available relationships: topSellers |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: topSellers |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
