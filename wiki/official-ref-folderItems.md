Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

One placement of a folder or album inside a folder. Everything in a folder is a folder item: an owned folder or album, or a reference to something another user shared with you. Removing a reference never touches its subject.

#### Resource `folderItems`
| Attribute | Type | Description |
|---|---|---|
| `itemStatus` | string (OK, DELETED, NO_ACCESS) |  |
| `reference` | boolean | Whether this item references a subject in another owner's tree, regardless of its current availability. |

Relationships (`include=`): `breadcrumb`, `owners`, `parent`, `subject`, `subjectSharingSettings`

### Get multiple folderItems
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Lists items in a folder, newest placement first. Select a folder with parent.id, or select your root with parent.isRoot=true and parent.owners.id=me. These forms cannot be combined; no other parent-filter combinations are supported. To search every folder in your tree instead, use query, subject.albums:published or both with parent.owners.id=me alone.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[parent.id]` | query |  | string | Folder id (e.g. `e3226624-355b-48f8-aa93-db42532caa66`). Also accepts `me`. |
| `filter[parent.isRoot]` | query |  | string | Filter by parent.isRoot |
| `filter[parent.owners.id]` | query |  | string | Owner of the folder an item is in; must be the authenticated user. With parent.isRoot=true it selects your root, and with query or subject.albums:published your whole tree. Also accepts `me`. |
| `filter[query]` | query |  | string | Searches every folder in your tree, selected with parent.owners.id=me, and lists the matching items in one flat list. An item matches when each word given starts a word in its folder's name, its album's title or the title of one of the album's tracks, ignoring case. An item shared with you matches by its subject, and only while you can open it. (e.g. `demo`) |
| `filter[subject.albums:published]` | query |  | string | Searches every folder in your tree, selected with parent.owners.id=me, for albums that are (true) or are not (false) published, and lists them in one flat list. Other items never match. Combines with query. (e.g. `true`) |
| `filter[subject.owners.id]` | query |  | string | In your folders, `=me` selects owned placements and `[ne]=me` selects shared placements. In someone else's folder, `=me` returns no items and `[ne]=me` returns all items. Accepts only `me` or your own user ID. |
| `filter[subject.owners.id][ne]` | query |  | string | In your folders, `=me` selects owned placements and `[ne]=me` selects shared placements. In someone else's folder, `=me` returns no items and `[ne]=me` returns all items. Accepts only `me` or your own user ID. |
| `include` | query |  | string[] | Include related resources. Available relationships: breadcrumb, owners, parent, subject, subjectSharingSettings |
| `includeLinkage` | query |  | string[]: breadcrumb, owners, parent, subject, subjectSharingSettings | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: breadcrumb.children.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single folderItem
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/folderItems```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Creates a new folderItem.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "parent": {
        "data": {
          "id": "string",
          "type": "folders"
        }
      },
      "subject": {
        "data": {
          "id": "string",
          "type": "folders | albums"
        }
      }
    },
    "type": "folderItems"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single folderItem
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Deletes existing folderItem.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single folderItem
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves single folderItem by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `include` | query |  | string[] | Include related resources. Available relationships: breadcrumb, owners, parent, subject, subjectSharingSettings |
| `includeLinkage` | query |  | string[]: breadcrumb, owners, parent, subject, subjectSharingSettings | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: breadcrumb.children.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get breadcrumb relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}/relationships/breadcrumb```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

The folders from the root to this item's parent; only for the tree's owner, empty otherwise.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `include` | query |  | string[] | Include related resources. Available relationships: breadcrumb |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: breadcrumb.children.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get parent relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}/relationships/parent```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves parent relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `include` | query |  | string[] | Include related resources. Available relationships: parent |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: parent.children.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update parent relationship ("to-one")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}/relationships/parent```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Moves the item to the supplied parent folder, replacing its previous parent. To move to the top level, supply the root folder explicitly; null data is rejected. Returns the new parent linkage.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "id": "string",
    "type": "folders"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subjectSharingSettings relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folderItems/{id}/relationships/subjectSharingSettings```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves subjectSharingSettings relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder item id |
| `include` | query |  | string[] | Include related resources. Available relationships: subjectSharingSettings |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subjectSharingSettings.subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
