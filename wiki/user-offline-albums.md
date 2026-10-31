#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/clients/{clientId}/offline/albums?countryCode={country}```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 52,
  "items": [
    {
      "created": "2020-08-15T11:14:36.690+0000",
      "item": {
        "id": 82448449,
        "title": "Neon Golden",
        "duration": 4906,
        "streamReady": true,
        "streamStartDate": "2017-12-05T00:00:00.000+0000",
        "allowStreaming": true,
        "premiumStreamingOnly": false,
        "numberOfTracks": 18,
        "numberOfVideos": 0,
        "numberOfVolumes": 1,
        "releaseDate": "2002-01-14",
        "copyright": "City Slang",
        "type": "ALBUM",
        "version": null,
        "url": "http://www.tidal.com/album/82448449",
        "cover": "ad3ed5f3-37a2-4b27-9002-b83459ab5a0e",
        "videoCover": null,
        "explicit": false,
        "upc": "192231021982",
        "popularity": 16,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 3529689,
          "name": "The Notwist",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 3529689,
            "name": "The Notwist",
            "type": "MAIN"
          }
        ]
      }
    }
  ]
}
```