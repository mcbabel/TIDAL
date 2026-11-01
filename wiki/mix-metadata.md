#### Example Request (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/mixes/{mixId}/metadata?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "id": "0015fef37ea3cfb30058cef8a738ec",
  "mixNumber": 0,
  "title": "Object 3",
  "artists": null,
  "type": "TRACK_MIX",
  "images": { "S": "https://images.tidal.com/0/…", "M": "https://images.tidal.com/0/…", "L": "https://images.tidal.com/0/…" },
  "mixImages": {
    "S": { "width": 320, "height": 320, "url": "https://images.tidal.com/0/…" },
    "M": { "width": 640, "height": 640, "url": "…" },
    "L": { "width": 640, "height": 640, "url": "…" }
  }
}
```
