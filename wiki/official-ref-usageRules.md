Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Usage rules defining how content may be consumed in a given country.

#### Resource `usageRules`
| Attribute | Type | Description |
|---|---|---|
| `countryCode` | string | Country code (ISO 3166-1 alpha-2) |
| `free` (optional) | string[] (STREAM, DJ, STEM, DOWNLOAD) | Usage types allowed for free/ad-supported model |
| `inherited` (optional) | boolean | Whether these usage rules are inherited from a parent (e.g. a track inheriting from its album). Tri-state: true means the rules are inherited, false means an explicit per-track override, null means the value is unknown or not applicable (albums, videos, and legacy data). |
| `paid` (optional) | string[] (STREAM, DJ, STEM, DOWNLOAD) | Usage types allowed for paid/purchase model |
| `subscription` (optional) | string[] (STREAM, DJ, STEM, DOWNLOAD) | Usage types allowed for subscription model |
| `validFrom` (optional) | string (date-time) | Datetime from which these usage rules are valid (ISO 8601) |

### Create single usageRule
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/usageRules```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new usageRule.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "countryCode?": "string",
      "free?": [
        "STREAM | DJ | STEM | DOWNLOAD"
      ],
      "inherited?": "boolean",
      "paid?": [
        "STREAM | DJ | STEM | DOWNLOAD"
      ],
      "subscription?": [
        "STREAM | DJ | STEM | DOWNLOAD"
      ],
      "validFrom?": "string (date-time)"
    },
    "relationships": {
      "subject": {
        "data": {
          "id": "string",
          "type": "tracks | albums | videos"
        }
      }
    },
    "type": "usageRules"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single usageRule
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/usageRules/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single usageRule by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Usage rules id |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
