#### Example Request (verified 2026-11)
* Public playlists of a user profile, with follow info.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/user-playlists/{userId}/public?limit={limit}&cursor={cursor}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "items": [
    {
      "playlist": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "...",
        "sharingLevel": "PUBLIC",
        ...
      },
      "followInfo": {
        "nrOfFollowers": 0,
        "followed": true,
        "tidalResourceName": "trn:playlist:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "followType": "PLAYLIST"
      },
      "profile": {
        "userId": 123456789,
        "name": "...",
        "color": [ ... ]
      }
    }
  ],
  "cursor": null
}
```
