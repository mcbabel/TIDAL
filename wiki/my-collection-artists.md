#### Example Request (verified 2026-11)
* Followed artists and user profiles ("Profiles" in My Collection). Cursor based pagination like [My Collection Folders](my-collection-folders).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-collection/artists?limit={limit}&cursor={cursor}&countryCode={country}&locale={locale}&deviceType={enum}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [
    {
      "trn": "trn:artist:3529689",
      "itemType": "ARTIST",
      "addedAt": "...",
      "lastModifiedAt": "...",
      "name": "The Notwist",
      "parent": null,
      "data": {
        "id": 3529689,
        "name": "The Notwist",
        "handle": null,
        "artistTypes": [ ... ],
        "artistRoles": [ ... ],
        "mixes": { ... },
        ...
      }
    }
  ],
  "lastModifiedAt": "...",
  "cursor": null
}
```

#### Update 2026-11: Android app (verified)
* The Android app uses `GET https://api.tidal.com/v2/my-collection/artists/folders` and the add/remove/folder endpoints described in [My Collection v2](my-collection-v2).
