Play queue in the cloud, used by TIDAL Connect, Sonos and other casting targets. Base url: `https://connectqueue.tidal.com/v1/`. All requests: ```authorization: Bearer {access_token}```, ```Content-Type: application/json```. Modifications need ```If-Match: {eTag}``` (ETag of the last response).

### Create Queue (endpoint verified 2026-11 without effect)
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

### Get Queue (endpoint verified 2026-11 without effect)
##### Method
```GET```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}```
##### Header
```authorization: Bearer {access_token}```

### Get Queue Items (endpoint verified 2026-11 without effect)
* Response: `{"items": [...], "total": 123}`
##### Method
```GET```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/items?limit=50&offset={offset}```
##### Header
```authorization: Bearer {access_token}```

### Add Items (endpoint verified 2026-11 without effect)
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

### Move Items (endpoint verified 2026-11 without effect)
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

### Remove Item (endpoint verified 2026-11 without effect)
##### Method
```DELETE```
##### Url
```https://connectqueue.tidal.com/v1/queues/{queueId}/items/{queueItemId}```
##### Header
```authorization: Bearer {access_token}```

### Shuffle (endpoint verified 2026-11 without effect)
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

### Get Queue Content (endpoint verified 2026-11 without effect)
* Media metadata of the queue items: `{"items": [...], "offset": 0, "total": 123}`
##### Method
```GET```
##### Url
```https://connectqueue.tidal.com/v1/content/{queueId}?offset={offset}&limit=50```
##### Header
```authorization: Bearer {access_token}```

#### Update 2026-11: Test status
All 8 endpoints exist and were verified with a non-existent queue id or an invalid body (no queue was created or changed):

| Endpoint | Result |
|---|---|
| `GET queues/{id}`, `GET queues/{id}/items`, `PUT queues/{id}/shuffle`, `GET content/{id}` | `404 {"error":"queue_not_found","error_description":"Could not find queue '...'"}` |
| `PUT queues/{id}/items` with empty `items` | `400 input_validation_error: items size must be between 1 and 100` |
| `PATCH queues/{id}/items` with empty `ids` | `400 input_validation_error: ids size must be between 1 and 100` |
| `POST queues` with `{}` | `400 input_validation_error: shuffled must not be null, repeat_mode: invalid value` |
| `DELETE queues/{id}/items/{itemId}` | `204` (idempotent) |

Not done: creating a real queue. There is no endpoint to delete a queue, so a test queue would stay in the account and could show up on TIDAL Connect devices.
