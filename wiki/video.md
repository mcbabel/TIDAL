#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "id": 143147453,
  "title": "Atomised",
  "volumeNumber": 1,
  "trackNumber": 1,
  "releaseDate": "2020-06-16T00:00:00.000+0000",
  "imagePath": null,
  "imageId": "2ef62a00-e310-48ab-afc2-f8cb76757968",
  "duration": 263,
  "quality": "MP4_1080P",
  "streamReady": true,
  "streamStartDate": "2020-06-17T11:00:00.000+0000",
  "allowStreaming": true,
  "explicit": false,
  "popularity": 2,
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
```

#### Update 2026-11 (verified)
New fields in the response: `vibrantColor`, `adSupportedStreamReady`, `djReady`, `stemReady`. Example values: `"quality": "MP4_1080P"`, `"type": "Promotional"` / `"Music Video"`.
