Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A playback manifest for a video, containing streaming URIs and format details.

#### Resource `videoManifests`
| Attribute | Type | Description |
|---|---|---|
| `drmData` (optional) | DrmData | DRM data. Absence implies no DRM. |
| `link` (optional) | Link_Object | A JSON:API link object |
| `previewReason` (optional) | string (FULL_REQUIRES_SUBSCRIPTION, FULL_REQUIRES_PURCHASE, FULL_REQUIRES_HIGHER_ACCESS_TIER) | Why a preview is served instead of the full video |
| `videoPresentation` (optional) | string (FULL, PREVIEW) | Video presentation |

### Get single videoManifest
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videoManifests/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `playback`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single videoManifest by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video manifest id |
| `uriScheme` | query | yes | string: HTTPS, DATA |  |
| `usage` | query | yes | string: PLAYBACK, DOWNLOAD |  |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
