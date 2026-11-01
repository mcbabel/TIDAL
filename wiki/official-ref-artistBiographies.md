Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A biography text for an artist.

#### Resource `artistBiographies`
| Attribute | Type | Description |
|---|---|---|
| `editable` | boolean | Boolean to indicate if the biography is editable (source = tidal or artist) |
| `source` (optional) | string (TIDAL, TiVo, MusicBrainz, Avex, Artist, UNKNOWN) | Source the biography is coming from |
| `text` | string | Artist biography |

Relationships (`include=`): `owners`

### Get single artistBiographie
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistBiographies/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single artistBiographie by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist biography id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single artistBiographie
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artistBiographies/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Updates existing artistBiographie.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist biography id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "text?": "string"
    },
    "id": "string",
    "type": "artistBiographies"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistBiographies/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist biography id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
