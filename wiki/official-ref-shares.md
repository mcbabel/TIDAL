Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A share of a TIDAL resource. Its access modes permit bearer access, redemption through savedShares for the offered role, or both.

#### Resource `shares`
| Attribute | Type | Description |
|---|---|---|
| `accessModes` | string[] (BEARER, VOUCHER) | Ways this share may be used to obtain access. BEARER permits access by presenting its code while active. VOUCHER permits an authenticated user to redeem it for a stored grant. Multiple modes may be enabled. |
| `code` | string | Share code |
| `createdAt` | string (date-time) | Time the share was created. |
| `expiresAt` | string (date-time) | Time bearer access and acceptance expire; accepted grants remain valid. |
| `externalLinks` (optional) | External_Link[] | Links external to TIDAL API |
| `maxUses` (optional) | integer (int32) | Number of users other than the owner who may save the share. Absent when unlimited. |
| `role` | string (VIEWER, COLLABORATOR) | Role offered on the shared resource. |
| `useCount` (optional) | integer (int32) | Number of users other than the owner who have saved the share. Once it reaches maxUses, bearer access and acceptance end. Absent when maxUses is. |

Relationships (`include=`): `owners`, `sharedResources`

### Get multiple shares
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/shares```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves multiple shares by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[code]` | query | yes | string[] | A share code (e.g. `xyz`) |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, sharedResources |
| `includeLinkage` | query |  | string[]: owners, sharedResources | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: sharedResources |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single share
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/shares```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new share.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "accessModes?": [
        "BEARER | VOUCHER"
      ],
      "expiresAt?": "string (date-time)",
      "maxUses?": "integer (int32)",
      "role": "VIEWER | COLLABORATOR"
    },
    "relationships": {
      "sharedResources": {
        "data": [
          {
            "id": "string",
            "type": "tracks | albums | playlists | folders"
          }
        ]
      }
    },
    "type": "shares"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single share
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/shares/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Delete share. Effectively revokes bearer access and acceptance.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Share id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `revokeGrants` | query |  | boolean | Also revoke the access granted to everyone who saved this share; access from other sources stays. Defaults to false. Not supported for playlist shares or for owners not yet on the access store; there true is rejected with 400. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single share
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/shares/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single share by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Share id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, sharedResources |
| `includeLinkage` | query |  | string[]: owners, sharedResources | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: sharedResources |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/shares/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Share id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get sharedResources relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/shares/{id}/relationships/sharedResources```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves sharedResources relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Share id |
| `include` | query |  | string[] | Include related resources. Available relationships: sharedResources |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: sharedResources |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
