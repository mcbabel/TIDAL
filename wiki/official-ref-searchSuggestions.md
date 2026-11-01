Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Autocomplete suggestions for a search query.

#### Resource `searchSuggestions`
| Attribute | Type | Description |
|---|---|---|
| `query` | string | The search query represented by this resource |
| `suggestions` | SearchSuggestions_Suggestions[] | Suggested search queries |
| `trackingId` | string | Unique tracking id |

Relationships (`include=`): `directHits`, `history`

### Get search suggestions by query
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchSuggestions```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Searches for a query and returns a collection containing exactly one search suggestions resource.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[query]` | query | yes | string | Search query (e.g. `hello`) |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: directHits, history |
| `includeLinkage` | query |  | string[]: directHits, history | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: directHits |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get directHits relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchSuggestions/{id}/relationships/directHits```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves directHits relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search suggestions identifier |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: directHits |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: directHits |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get history relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchSuggestions/{id}/relationships/history```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves history relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search suggestions identifier |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: history |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
