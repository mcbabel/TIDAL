Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A claim by an artist asserting ownership of a piece of content.

#### Resource `contentClaims`
| Attribute | Type | Description |
|---|---|---|
| `assertion` | string (CLAIM, DISCLAIM) | The claim assertion type |
| `createdAt` | string (date-time) | Timestamp when the claim was created |
| `lastModifiedAt` | string (date-time) | Timestamp when the claim was last modified |
| `status` | string (OPEN, IN_PROGRESS, RESOLVED, REJECTED) | Current status of this claim |

Relationships (`include=`): `claimedResource`, `claimingArtist`, `owners`

### Get multiple contentClaims
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/contentClaims```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple contentClaims by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: claimedResource, claimingArtist, owners |
| `includeLinkage` | query |  | string[]: claimedResource, claimingArtist, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: claimedResource |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single contentClaim
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/contentClaims```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new contentClaim.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "assertion": "CLAIM | DISCLAIM"
    },
    "relationships": {
      "claimedResource": {
        "data": {
          "id": "string",
          "type": "tracks | albums | videos"
        }
      },
      "claimingArtist": {
        "data": {
          "id": "string",
          "type": "artists"
        }
      }
    },
    "type": "contentClaims"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single contentClaim
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/contentClaims/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single contentClaim by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Content claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: claimedResource, claimingArtist, owners |
| `includeLinkage` | query |  | string[]: claimedResource, claimingArtist, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: claimedResource |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get claimedResource relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/contentClaims/{id}/relationships/claimedResource```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves claimedResource relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Content claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: claimedResource |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: claimedResource |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get claimingArtist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/contentClaims/{id}/relationships/claimingArtist```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves claimingArtist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Content claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: claimingArtist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: claimingArtist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/contentClaims/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Content claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
