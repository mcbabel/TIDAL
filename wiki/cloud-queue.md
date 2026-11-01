Play queue in the cloud, used by TIDAL Connect, Sonos and other casting targets. Base url: `https://connectqueue.tidal.com/v1/`. All requests (from web player code 2026-11, not live-tested): ```authorization: Bearer {access_token}```, ```Content-Type: application/json```. Modifications need ```If-Match: {eTag}``` (ETag of the last response).

### Create Queue (from web player code 2026-11, not live-tested)
* Response contains `id`, `items` (each with an `id`), `properties.position`, `repeat_mode`, `shuffled` and an `ETag` header.
##### Method
```POST```
##### Url
```https://connectqueue.tidal.com/v1/queues```
##### Header
```authorization: Bearer {access_token}```
##### Body
``` yaml
{
  "items": [
    {
      "media_id": "38519997",
      "type": "track",
      "properties": {
        "active": "false",
        "original_order": "0",
        "source_id": "38519994",
        "source_type": "ALBUM"
      }
    }
  ],
  "properties": {
    "position": 0
  },
  "repeat_mode": "off",
  "shuffled": false
}
```

### Get Queue (from web player code 2026-11, not live-tested)
##### Method
```GET```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}```
##### Header
```authorization: Bearer {access_token}```

### Get Queue Items (from web player code 2026-11, not live-tested)
* Response: `{"items": [...], "total": 123}`
##### Method
```GET```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/items?limit=50&offset={offset}```
##### Header
```authorization: Bearer {access_token}```

### Add Items (from web player code 2026-11, not live-tested)
* `mode`: `append` | `prepend` (prepend without `item_id`). Max 100 items per request.
##### Method
```PUT```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/items```
##### Header
```authorization: Bearer {access_token}```
##### Body
``` yaml
{
  "item_id": "{after this queue item id}",
  "items": [ ... ],
  "mode": "append"
}
```

### Move Items (from web player code 2026-11, not live-tested)
##### Method
```PATCH```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/items```
##### Header
```authorization: Bearer {access_token}```
##### Body
``` yaml
{
  "after": "{queue item id}",
  "ids": [
    "{queue item id}"
  ]
}
```

### Remove Item (from web player code 2026-11, not live-tested)
##### Method
```DELETE```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/items/{queueItemId}```
##### Header
```authorization: Bearer {access_token}```

### Shuffle (from web player code 2026-11, not live-tested)
##### Method
```PUT```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/shuffle```
##### Header
```authorization: Bearer {access_token}```
##### Body
``` yaml
{
  "current_item": "{queue item id}",
  "shuffle": true
}
```

### Get Queue Content (from web player code 2026-11, not live-tested)
* Media metadata of the queue items: `{"items": [...], "offset": 0, "total": 123}`
##### Method
```GET```
##### Url
```https://connectqueue.tidal.com/v1/content/{queueId}?offset={offset}&limit=50```
##### Header
```authorization: Bearer {access_token}```
