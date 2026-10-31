All requests (verified 2026-11):\
```Authorization: Bearer {access_token}``` (PKCE, scope `playlists.write` for changes)\
```Accept: application/vnd.api+json```\
```Content-Type: application/vnd.api+json```\
```Idempotency-Key: {uuid}``` (optional, safe retries)

### Create Playlist
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlists```
##### Body
``` yaml
{
  "data": {
    "type": "playlists",
    "attributes": {
      "name": "My Playlist",
      "description": "test",
      "accessType": "UNLISTED"
    }
  }
}
```
##### accessType Enums
```PUBLIC```\
```UNLISTED```
#### Example Response
```201 Created```
``` yaml
{
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "type": "playlists",
    "attributes": {
      "name": "My Playlist",
      "description": "test",
      "bounded": false,
      "externalLinks": [
        {
          "href": "https://listen.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "meta": {
            "type": "TIDAL_SHARING"
          }
        },
        ...
      ],
      ...
    }
  }
}
```

### Add Items
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Body
``` yaml
{
  "data": [
    { "type": "tracks", "id": "38519997" },
    { "type": "tracks", "id": "136469594" }
  ],
  "meta": {
    "onDuplicates": "SKIP"
  }
}
```
`meta.onDuplicates`: `ADD` | `FAIL` | `SKIP`, `meta.positionBefore`: `{itemId}` (insert position, default: end)
#### Example Response
``` yaml
{
  "data": [
    {
      "id": "38519997",
      "type": "tracks",
      "meta": {
        "itemId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "addedAt": "2026-10-31T23:45:00.674017Z"
      }
    },
    {
      "id": "136469594",
      "type": "tracks",
      "meta": {
        "itemId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "addedAt": "2026-10-31T23:45:00.674017Z"
      }
    }
  ],
  "links": {
    "self": "/playlists/{id}/relationships/items"
  },
  "meta": {
    "skipped": []
  }
}
```
Every entry has its own `meta.itemId`. Use it to move or remove a specific entry (a track can be in a playlist more than once).

### Get Items
```GET https://openapi.tidal.com/v2/playlists/{id}/relationships/items``` (also with Client Credentials for public playlists). Optional: `include=items`, `sort=itemIndex`, `page[cursor]=...`

### Move Items
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Body
``` yaml
{
  "data": [
    { "type": "tracks", "id": "136469594", "meta": { "itemId": "{itemId}" } }
  ],
  "meta": {
    "positionBefore": "{itemId}"
  }
}
```
Without `meta.positionBefore` the items are moved to the end. Response: `{"links": {...}, "meta": {}}`

### Remove Items
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Body
``` yaml
{
  "data": [
    { "type": "tracks", "id": "38519997", "meta": { "itemId": "{itemId}" } }
  ]
}
```

### Update Playlist
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}```
##### Body
``` yaml
{
  "data": {
    "type": "playlists",
    "id": "{id}",
    "attributes": {
      "name": "New name",
      "description": "New description",
      "accessType": "PUBLIC"
    }
  }
}
```
Note: the PATCH response may still contain the old attributes. The next GET shows the new values.

### Delete Playlist
```DELETE https://openapi.tidal.com/v2/playlists/{id}``` → `200 OK` with `{"links": {...}, "meta": {}}`

### List Playlists Of The User
```GET https://openapi.tidal.com/v2/playlists?filter[owners.id]=me&sort=-lastModifiedAt```\
(the web player uses `filter[collaborators.id]=me&include=collaborators,coverArt,ownerProfiles&sort=-lastModifiedAt`)
