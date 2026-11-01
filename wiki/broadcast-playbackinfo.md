#### Example Request (verified 2026-11 with a non-existent id: 404)
* Playback info for a live DJ session (TIDAL "DJ"/broadcast feature of the Android app (`com.aspiro.tidal` 2.215.0)).
* A non-existent session answers `404 {"userMessage":"No content available for the requested product."}`. A real session id is only available while someone broadcasts.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/broadcasts/{djSessionId}/playbackinfo?audioquality={enum}```
##### Header
```authorization: Bearer {access_token}```
