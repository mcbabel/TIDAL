#### Example Request
* Needs a user. Answers `404` if the track has no lyrics (verified 2026-11 for a track without lyrics).
* Response fields as used by python-tidal (not verified with a track that has lyrics): `trackId`, `lyricsProvider`, `providerCommontrackId`, `providerLyricsId`, `lyrics` (plain text), `subtitles` (LRC with timestamps), `isRightToLeft`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/lyrics?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
