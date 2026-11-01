#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/clients?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 10,
  "offset": 0,
  "totalNumberOfItems": 2,
  "items": [
    {
      "id": 01234567,
      "name": "Some Smartphone",
      "application": {
        "name": "TIDAL_Android_2.25.0",
        "type": {
          "name": "Something"
        },
        "service": "TIDAL"
      },
      "uniqueKey": "xxxxxxxxxxxxxxx",
      "authorizedForOffline": true,
      "authorizedForOfflineDate": "1900-02-22T20:26:16.511+0000",
      "lastLogin": "1970-02-15T07:25:09.966+0000",
      "created": "1899-09-10T21:20:52.442+0000",
      "numberOfOfflineAlbums": 57,
      "numberOfOfflinePlaylists": 11
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
