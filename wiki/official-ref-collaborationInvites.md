Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Deprecated compatibility view of a COLLABORATOR playlist share. Use `shares` instead. The ID and code identify the same share through either resource. Links are reusable. Expiry and revocation follow the underlying share.

#### Resource `collaborationInvites`
| Attribute | Type | Description |
|---|---|---|
| `code` | string | Opaque invite code embedded in the share link |
| `createdAt` | string (date-time) | Datetime the invite was created (ISO 8601) |
| `expiresAt` | string (date-time) | Time the underlying share expires; accepted grants remain valid |
| `revoked` | boolean | Whether the underlying share has been revoked |

Relationships (`include=`): `owners`, `subject`

### Get multiple collaborationInvites (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/collaborationInvites```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple collaborationInvites by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[code]` | query | yes | string[] | Invite code |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, subject |
| `includeLinkage` | query |  | string[]: owners, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single collaborationInvite (Deprecated)
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/collaborationInvites```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `201` (write test with cleanup).

Creates a new collaborationInvite.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "subject": {
        "data": {
          "id": "string",
          "type": "playlists"
        }
      }
    },
    "type": "collaborationInvites"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single collaborationInvite (Deprecated)
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/collaborationInvites/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Deletes existing collaborationInvite.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Collaboration invite id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single collaborationInvite (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/collaborationInvites/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves single collaborationInvite by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Collaboration invite id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, subject |
| `includeLinkage` | query |  | string[]: owners, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many") (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/collaborationInvites/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Collaboration invite id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one") (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/collaborationInvites/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Collaboration invite id |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
