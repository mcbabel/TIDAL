Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A track source file is the media source file of a track, meaning audio content. After a track source file is uploaded successfully it will be ingested and transcoded into deliverables and stored like any other content we receive from labels.

#### Resource `trackSourceFiles`
| Attribute | Type | Description |
|---|---|---|
| `downloadLink` (optional) | Link_Object | A JSON:API link object |
| `md5Hash` | string | MD5 hash of file to be uploaded |
| `processing` (optional) | SourceProcessing | Available source-analysis results. Audio and waveform may be absent independently; presence does not indicate processing completion. |
| `size` | integer (int64) | File size of the track in bytes |
| `status` | File_Status | File status |
| `uploadLink` (optional) | File_Upload_Link | Upload link |

Relationships (`include=`): `owners`

### Create single trackSourceFile
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/trackSourceFiles```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Creates uploads (albums, tracks, audio source files, artwork) on TIDAL. Needs real media files and the rights to publish them; uploads can become visible to other users.

Create a track source file. <p/> The response contains a upload link that must be used to upload the actual content.<p/> The headers in the upload link response must be sent doing the actual upload.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "md5Hash": "string",
      "size": "integer (int64)"
    },
    "relationships": {
      "track": {
        "data?": {
          "id": "string",
          "type": "tracks"
        },
        "id?": "string",
        "type?": "tracks"
      }
    },
    "type": "trackSourceFiles"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single trackSourceFile
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackSourceFiles/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** answered `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a valid UUID`.

Retrieves single trackSourceFile by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track source file id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackSourceFiles/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** answered `500` `INTERNAL_SERVER_ERROR: Internal server error`.

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track source file id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
