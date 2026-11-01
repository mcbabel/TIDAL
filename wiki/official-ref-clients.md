Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An OAuth client.

#### Resource `clients`
| Attribute | Type | Description |
|---|---|---|
| `accessTier` | string (THIRD_PARTY, THIRD_PARTY_PROD, PARTNER, INTERNAL) |  |
| `clientSecret` (optional) | string |  |
| `createdAt` (optional) | string (date-time) |  |
| `description` (optional) | string |  |
| `name` | string |  |
| `redirectUris` (optional) | string[] |  |
| `scopes` (optional) | string[] |  |

Relationships (`include=`): `certificates`, `owners`

### Get multiple clients
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/clients```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple clients by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: certificates, owners |
| `includeLinkage` | query |  | string[]: certificates, owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single client
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/clients```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Creates API credentials (client id + secret) or TIDAL Connect partner certificates for the account.

Creates a new client.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "description?": "string",
      "name": "string"
    },
    "type": "clients"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single client
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/clients/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `404` `NOT_FOUND: Clients '{id}' not found`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes existing client.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | OAuth client identifier |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single client
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/clients/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single client by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | OAuth client identifier |
| `include` | query |  | string[] | Include related resources. Available relationships: certificates, owners |
| `includeLinkage` | query |  | string[]: certificates, owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single client
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/clients/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `404` `NOT_FOUND: Clients '{id}' not found`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates existing client.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | OAuth client identifier |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "description?": "string",
      "name?": "string",
      "redirectUris?": [
        "string"
      ],
      "scopes?": [
        "string"
      ]
    },
    "id": "string",
    "type": "clients"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get certificates relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/clients/{id}/relationships/certificates```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** answered `403` `UNAUTHORIZED: TIDAL Connect partner access is required`.

Retrieves certificates relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | OAuth client identifier |
| `include` | query |  | string[] | Include related resources. Available relationships: certificates |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/clients/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | OAuth client identifier |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
