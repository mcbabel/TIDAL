Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A record of a user's acceptance of terms and conditions.

#### Resource `acceptedTerms`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) |  |

Relationships (`include=`): `owners`, `terms`

### Get multiple acceptedTerms
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/acceptedTerms```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple acceptedTerms by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `filter[terms.termsType]` | query | yes | string[]: DEVELOPER, UPLOAD_MARKETPLACE, MERCH_GUIDELINES, TIDAL_CONNECT_DEVELOPER | One of: DEVELOPER, UPLOAD_MARKETPLACE, MERCH_GUIDELINES, TIDAL_CONNECT_DEVELOPER (e.g. `DEVELOPER`) |
| `filter[terms.isLatestVersion]` | query |  | string[] | Filter by terms.isLatestVersion |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, terms |
| `includeLinkage` | query |  | string[]: owners, terms | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single acceptedTerm
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/acceptedTerms```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new acceptedTerm.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "terms": {
        "data": {
          "id": "string",
          "type": "terms"
        }
      }
    },
    "type": "acceptedTerms"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/acceptedTerms/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Accepted terms id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get terms relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/acceptedTerms/{id}/relationships/terms```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves terms relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Accepted terms id |
| `include` | query |  | string[] | Include related resources. Available relationships: terms |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
