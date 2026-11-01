Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A small summary of the viewer’s current relationship with a known subject, for rendering its personalised presentation and interaction state. Enriches known subjects; domain APIs own discovery, details and mutations. A successful response replaces the previous context snapshot. Omission establishes absence only for supported, applicable, authorized facts. Reserved, unsupported and access-redacted fields remain unknown when omitted.

#### Resource `viewerContexts`
| Attribute | Type | Description |
|---|---|---|
| `hasCommentedOn` (optional) | Commented | The viewer has at least one existing comment on the subject; deleted historical comments do not count. Reserved; not currently populated and omitted from responses. Omission does not indicate that the relation is absent. |
| `hasInCollection` (optional) | InCollection | The viewer has the original subject in their normal collection. Present as an empty object when known present, otherwise omitted. Includes owned and saved playlists and saved mixes across folders; excludes Save for Later. |
| `hasPurchased` (optional) | Purchased | The viewer has a current qualifying purchase entitlement. Includes a track covered by its purchased album; excludes subscription access and free downloads. Reserved; not currently populated and omitted from responses. Omission does not indicate that the relation is absent. |
| `hasReactedTo` (optional) | Reaction | The viewer has a current reaction to the subject, with its emoji. Reserved; not currently populated and omitted from responses. Omission does not indicate that the relation is absent. |
| `hasSavedForLater` (optional) | SavedForLater | The viewer has saved the subject for later. Reserved; not currently populated and omitted from responses. Omission does not indicate that the relation is absent. |
| `isFollowedBy` (optional) | FollowedBy | The viewer is followed by the subject. Reserved; not currently populated and omitted from responses. Omission does not indicate that the relation is absent. |
| `isFollowing` (optional) | Following | The viewer follows the subject. Reserved; not currently populated and omitted from responses. Omission does not indicate that the relation is absent. |
| `isGranteeOf` (optional) | Grantee | The viewer's effective role for the subject. Populated for albums, tracks and folders; omitted for other subject types. |

Relationships (`include=`): `subject`, `viewer`

### Get multiple viewerContexts
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/viewerContexts```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Returns viewer contexts for up to 20 original subjects. Duplicate subjects are returned once.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[subject]` | query | yes | string[] | Original subjects to look up. Also accepts `folders:me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: subject, viewer |
| `includeLinkage` | query |  | string[]: subject, viewer | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single viewerContext
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/viewerContexts/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single viewerContext by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of one authenticated viewer and original subject pair |
| `include` | query |  | string[] | Include related resources. Available relationships: subject, viewer |
| `includeLinkage` | query |  | string[]: subject, viewer | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/viewerContexts/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Returns the subject of this viewer context.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of one authenticated viewer and original subject pair |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get viewer relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/viewerContexts/{id}/relationships/viewer```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Returns the authenticated viewer of this context.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of one authenticated viewer and original subject pair |
| `include` | query |  | string[] | Include related resources. Available relationships: viewer |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: viewer.artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
