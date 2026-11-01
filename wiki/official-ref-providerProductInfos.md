Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Product information for a content provider's catalogue.

#### Resource `providerProductInfos`
| Attribute | Type | Description |
|---|---|---|
| `barcodeId` (optional) | string |  |
| `broken` (optional) | boolean |  |
| `brokenCode` (optional) | integer (int32) |  |
| `grid` (optional) | string |  |
| `tracks` (optional) | TrackInfo[] |  |

Relationships (`include=`): `provider`, `subject`

### Get multiple providerProductInfos
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providerProductInfos```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple providerProductInfos by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[provider.id]` | query | yes | string[] | Content provider ID (e.g. `50`) |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[barcodeId]` | query |  | string[] | List of barcode IDs (EAN-13 or UPC-A) (e.g. `00602527336510`) |
| `filter[grid]` | query |  | string[] | List of GRIDs (Global Release Identifier, ISO 7064) (e.g. `A10302B0013941653J`) |
| `include` | query |  | string[] | Include related resources. Available relationships: provider, subject |
| `includeLinkage` | query |  | string[]: provider, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get provider relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providerProductInfos/{id}/relationships/provider```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The list answered `200` without data for the tested provider.

Retrieves provider relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Provider product info id |
| `include` | query |  | string[] | Include related resources. Available relationships: provider |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providerProductInfos/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The list answered `200` without data for the tested provider.

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Provider product info id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
