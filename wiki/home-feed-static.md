#### Example Request (verified 2026-11)
* New home page of the apps (replaces [Get Page Home](page-home) in the web player).
* `timeOffset` is the UTC offset url-encoded, e.g. `%2B01%3A00`
* Pagination: `page.cursor` → send it as `cursor={cursor}` for the next modules
* Works without user (generic modules) and with user (personal modules like shortcuts).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/home/feed/static?countryCode={country}&locale={locale}&deviceType={enum}&platform={enum}&timeOffset={offset}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### platform
```WEB``` (web player)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "page": {
    "cursor": "QUxCVU1fUkVDT01NRU5EQVRJT05T"
  },
  "header": {
    "vibes": {
      "items": [
        {
          "name": "For you",
          "type": "STATIC"
        },
        {
          "name": "Staff Picks",
          "type": "EDITORIAL"
        },
        {
          "name": "Uploads",
          "type": "UPLOADS"
        }
      ]
    }
  },
  "items": [
    {
      "type": "HORIZONTAL_LIST",
      "moduleId": "...",
      "title": "Popular albums",
      "icons": [],
      "showQuickPlay": true,
      "viewAll": "...",
      "items": [
        {
          "type": "ALBUM",
          "following": false,
          "latestRelease": false,
          "data": {
            "id": 539302525,
            "title": "I Used to Kill",
            "artists": [
              {
                "id": 7528086,
                "name": "Daine",
                "handle": null,
                "picture": "eff72e89-c33a-48ff-9b49-48f9219f77e2",
                "main": true,
                "userId": null
              }
            ],
            "cover": "f528be98-ca7d-4c0f-bdf3-9dc1e0e409f2",
            "releaseDate": "2026-08-12",
            "type": "SINGLE",
            ...
          }
        }
      ]
    }
  ]
}
```

#### Update 2026-11: Android app (verified)
* The Android app loads `home/feed/{vibe}` with `platform=ANDROID`. Without `platform` the v2 page endpoints answer `400 Bad Request`.
