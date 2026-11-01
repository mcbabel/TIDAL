### Get Blocked Ids (verified 2026-11)
* Ids of blocked artists, tracks and videos (the apps hide blocked items from mixes, radio and recommendations).
* The response has an `ETag`. Send `If-None-Match: {eTag}` to get `304` when nothing changed.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/blocks/ids?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "artists": [
    11083
  ],
  "tracks": [],
  "videos": []
}
```

### Get Blocked Items (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/blocks/{type}?limit={limit}&offset={offset}&countryCode={country}```
##### type Enums
```artists```\
```tracks```\
```videos```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "limit": 5,
  "offset": 0,
  "totalNumberOfItems": 1,
  "items": [
    {
      "item": {
        "id": 11083,
        "name": "Kings Of Convenience",
        ...
      },
      "created": "...",
      "type": "..."
    }
  ]
}
```

### Block Item (verified 2026-11)
* `409` if the block list limit is reached.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/blocks/{type}?countryCode={country}```
##### type Enums
```artists```\
```tracks```\
```videos```
##### Url-Encoded POST Parameter
```artistId: {id}``` / ```trackId: {id}``` / ```videoId: {id}```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
```200 OK``` (empty body)

### Unblock Item (verified 2026-11)
##### Method
```DELETE```
##### Url
```https://api.tidal.com/v1/users/{userId}/blocks/{type}/{id}?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
```204 No Content```
