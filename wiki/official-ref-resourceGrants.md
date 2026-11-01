Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A stored grant on an access-core album, track or folder, including saved-share-link grants. The subject's owner and directly named user grantee may read the grant; only the owner may administer it. Grants from any source may be deleted; creation and role updates apply only to direct grants.

#### Resource `resourceGrants`
| Attribute | Type | Description |
|---|---|---|
| `role` | string (VIEWER, COLLABORATOR, OWNER) |  |

Relationships (`include=`): `grantee`, `subject`

### Get multiple resourceGrants
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceGrants```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Lists stored grants from every source visible to the subject's owner or named user grantee, selected by subject or grantee, optionally restricted by assigned role. Requires subject or grantee.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[grantee]` | query |  | string | Filter by grantee. Also accepts `users:me`. |
| `filter[role]` | query |  | string: VIEWER, COLLABORATOR, OWNER | One of: VIEWER, COLLABORATOR, OWNER (e.g. `VIEWER`) |
| `filter[subject]` | query |  | string | Filter by subject. Also accepts `folders:me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: grantee, subject |
| `includeLinkage` | query |  | string[]: grantee, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: grantee.artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single resourceGrant
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/resourceGrants```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** answered `400` `GENERIC_REQUEST_ERROR: Owned-content grant management is not enabled for this owner`.

Creates a new resourceGrant.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "role": "VIEWER | COLLABORATOR"
    },
    "relationships": {
      "grantee": {
        "data": {
          "id": "string",
          "type": "users | groups"
        }
      },
      "subject": {
        "data": {
          "id": "string",
          "type": "albums | tracks | folders"
        }
      }
    },
    "type": "resourceGrants"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single resourceGrant
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/resourceGrants/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes existing resourceGrant.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource grant ID |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single resourceGrant
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceGrants/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single resourceGrant by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource grant ID |
| `include` | query |  | string[] | Include related resources. Available relationships: grantee, subject |
| `includeLinkage` | query |  | string[]: grantee, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: grantee.artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single resourceGrant
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/resourceGrants/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates existing resourceGrant.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource grant ID |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "role": "VIEWER | COLLABORATOR"
    },
    "id": "string",
    "type": "resourceGrants"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get grantee relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceGrants/{id}/relationships/grantee```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves grantee relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource grant ID |
| `include` | query |  | string[] | Include related resources. Available relationships: grantee |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: grantee.artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceGrants/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource grant ID |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
