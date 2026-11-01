Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Links to equivalent content on other streaming platforms.

#### Resource `dspSharingLinks`
| Attribute | Type | Description |
|---|---|---|
| `amazonMusic` (optional) | Link_Object | A JSON:API link object |
| `appleMusic` (optional) | Link_Object | A JSON:API link object |
| `spotify` (optional) | Link_Object | A JSON:API link object |
| `youTubeMusic` (optional) | Link_Object | A JSON:API link object |

Relationships (`include=`): `subject`

### Get multiple dspSharingLinks
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dspSharingLinks```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple dspSharingLinks by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[subject.id]` | query |  | string[] | Deprecated: use filter[subject]. The id of the subject resource **Deprecated.** |
| `filter[subject.type]` | query |  | string[]: tracks, albums, artists | Deprecated: use filter[subject]. The type of the subject resource (e.g. `tracks`) **Deprecated.** |
| `filter[subject]` | query |  | string | The subject whose DSP sharing links to return. Use either subject or the deprecated subject.id and subject.type pair. |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `includeLinkage` | query |  | string[]: subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dspSharingLinks/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | DspSharingLinks Id |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
