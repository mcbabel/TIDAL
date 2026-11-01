Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's offline mixes.

#### Resource `userOfflineMixes`
| Attribute | Type | Description |
|---|---|---|

Relationships (`include=`): `items`

### Get single userOfflineMixe
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userOfflineMixes/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single userOfflineMixe by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User offline mixes id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `includeLinkage` | query |  | string[]: items | Comma-separated direct relationships to return as linkage only, without related content. |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get items relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userOfflineMixes/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User offline mixes id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
