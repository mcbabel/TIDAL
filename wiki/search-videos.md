#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/search/videos?countryCode={country}&query={query}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 24,
  "items": [
    {
      "id": 53654641,
      "title": "All Res",
      "volumeNumber": 1,
      "trackNumber": 1,
      "releaseDate": "2015-11-20T00:00:00.000+0000",
      "imagePath": null,
      "imageId": "c7eeb6cb-21e3-4b43-b5a1-f7a0dbaae6ca",
      "duration": 259,
      "quality": "MP4_1080P",
      "streamReady": true,
      "streamStartDate": "2015-12-04T00:00:00.000+0000",
      "allowStreaming": true,
      "explicit": false,
      "popularity": 7,
      "type": "Music Video",
      "adsUrl": null,
      "adsPrePaywallOnly": true,
      "artist": {
        "id": 4764457,
        "name": "GoGo Penguin",
        "type": "MAIN"
      },
      "artists": [
        {
          "id": 4764457,
          "name": "GoGo Penguin",
          "type": "MAIN"
        }
      ],
      "album": null
    }
  ]
}
```