Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Who has access to an access-core album, track or folder, and through what: the grants and active share links on it or a folder or album above it. Only the subject's owner may read it.

#### Resource `resourceSharingSettings`
| Attribute | Type | Description |
|---|---|---|
| `shared` | boolean | Whether anyone but the owner has a grant, or an active share link exists, on the subject or above it. |
| `sharedViaParent` | boolean | Whether a folder or album above the subject is shared, so the subject stays shared whatever is set on it. |

Relationships (`include=`): `grants`, `shares`, `subject`

### Get multiple resourceSharingSettings
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceSharingSettings```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Returns the sharing settings of up to 20 live access-core subjects. Subjects without a node, or that the caller does not own, return none.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[subject]` | query | yes | string[] | Filter by subject. Also accepts `folders:me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: grants, shares, subject |
| `includeLinkage` | query |  | string[]: grants, shares, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: grants.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single resourceSharingSetting
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceSharingSettings/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single resourceSharingSetting by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource sharing settings ID |
| `include` | query |  | string[] | Include related resources. Available relationships: grants, shares, subject |
| `includeLinkage` | query |  | string[]: grants, shares, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: grants.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get grants relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceSharingSettings/{id}/relationships/grants```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Each grantee's strongest grant on the subject or a folder or album above it: the strongest role, then the nearest grant, then a direct grant over a saved link's, then the oldest. The owner comes first, then groups, then users. A grant's subject is the node it is on.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource sharing settings ID |
| `include` | query |  | string[] | Include related resources. Available relationships: grants |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: grants.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get shares relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceSharingSettings/{id}/relationships/shares```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

The active share links on the subject or an album above it, or a folder above it whose link can be saved, next to expire first.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource sharing settings ID |
| `include` | query |  | string[] | Include related resources. Available relationships: shares |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: shares.sharedResources |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/resourceSharingSettings/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque resource sharing settings ID |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
