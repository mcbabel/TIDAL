#### Example Request
* Adding more than one track is possible by separating itemIds: ```{track_id},{track_id}```
* To prevent corruption you need to extract the eTag Value from the Get Playlist Header
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}/items?countryCode={country}```
##### onDupes Enums
```FAIL```\
```SKIP```\
```ADD```
##### Url-Encoded POST Parameter
```itemIds: {track_id}```\
```onArtifactNotFound: FAIL```\
```onDupes: {enum}```
##### Header
```authorization: Bearer {access_token}```\
```If-None-Match: {eTag}``` (Use eTag from the Get Playlist Header)

#### Update 2026-11 (verified)
* Still works. The Url-Encoded POST Parameter `trackIds: {track_id},{track_id}` is accepted as well.
#### Example Response
``` yaml
{
  "lastUpdated": 1793490268755,
  "addedItemIds": [
    38519997,
    136469594
  ]
}
```
* The response carries a new `ETag` header. Use it for the next modification.
* For playlist folders and creating playlists see [Create Playlist (My Collection)](my-collection-create-playlist).
