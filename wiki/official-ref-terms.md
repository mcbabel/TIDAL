Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A terms and conditions document.

#### Resource `terms`
| Attribute | Type | Description |
|---|---|---|
| `contentLink` | Link_Object | A JSON:API link object |
| `countryCode` | string |  |
| `effectiveAt` | string (date-time) |  |
| `termsType` | string (DEVELOPER, UPLOAD_MARKETPLACE, MERCH_GUIDELINES, TIDAL_CONNECT_DEVELOPER) |  |

### Get multiple terms
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/terms```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple terms by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[termsType]` | query | yes | string[]: DEVELOPER, UPLOAD_MARKETPLACE, MERCH_GUIDELINES, TIDAL_CONNECT_DEVELOPER | One of: DEVELOPER, UPLOAD_MARKETPLACE, MERCH_GUIDELINES, TIDAL_CONNECT_DEVELOPER (e.g. `DEVELOPER`) |
| `filter[countryCode]` | query |  | string[] | Selects the country-specific terms variant when it has an effective version; otherwise falls back to the worldwide (WW) variant. Combine with `filter[isLatestVersion]=true` to return the currently acceptable terms. (e.g. `US`) |
| `filter[isLatestVersion]` | query |  | string[] | Filter by isLatestVersion |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single term
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/terms/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single term by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Terms id |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
