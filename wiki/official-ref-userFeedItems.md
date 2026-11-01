Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A group of activity events in the authenticated user's inbox or feed.

#### Resource `userFeedItems`
| Attribute | Type | Description |
|---|---|---|
| `activityDetails` | UserFeedItemActivityDetails | Details of the activity represented by the group. |
| `countIsPeople` | boolean | Whether `eventCount` also counts distinct people |
| `eventCount` | integer (int32) | Number of events represented by the item |
| `firstAt` | string (date-time) | Time of the first event in the group |
| `lastAt` | string (date-time) | Time of the latest event in the group |
| `surface` | string (INBOX, FEED) | The feed surface containing the activity |
| `unread` | boolean | Whether the item contains unseen activity |

Relationships (`include=`): `actors`, `subject`

### Get multiple userFeedItems
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userFeedItems```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

The authenticated user's activity on the selected feed surface.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `filter[surface]` | query | yes | string: INBOX, FEED | Feed surface to read (e.g. `INBOX`) |
| `include` | query |  | string[] | Include related resources. Available relationships: actors, subject |
| `includeLinkage` | query |  | string[]: actors, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: actors.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get actors relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userFeedItems/{id}/relationships/actors```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Artists attributed to the activity. Always empty for `ALBUM_FAVOURITED`, `TRACK_FAVOURITED` and `TRACK_PLAYLISTED`, which are counts only, and for `HISTORY_MIX_READY` and `TRACK_PLAY_MILESTONE`, which nobody else acted on.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of a user feed item. |
| `include` | query |  | string[] | Include related resources. Available relationships: actors |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: actors.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userFeedItems/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

The resource the activity concerns. For `HISTORY_MIX_READY`, the viewer's history mix as a playlist.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of a user feed item. |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
