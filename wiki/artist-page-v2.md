#### Example Request (verified 2026-11)
* Artist page of the web player (replaces [pages/artist](page-artist)).
* Module types seen: `TRACK_LIST` (popular tracks), `HORIZONTAL_LIST` (albums, EPs & singles, compilations, live albums, playlists, fans also like, appears on), `ARTIST_TRACK_CREDITS_CARD` (credits)
* The web player additionally loads `GET https://openapi.tidal.com/v2/artists/{id}?countryCode={country}&include=claimStatus` from the [Official API](OfficialAPI).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/artist/{id}?countryCode={country}&locale={locale}&deviceType={enum}&platform={enum}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "type": "ARTIST",
  "header": {
    "type": "ARTIST",
    "profilePrivacyType": "PUBLIC",
    "contributionLinkUrl": null,
    "contributions": null,
    "playableContent": {
      "play": true,
      "shuffle": true,
      "items": [ ... ],
      "url": "artist/3529689/playable",
      "cursor": null
    },
    "biography": {
      "text": "Morphing from a post-hardcore outfit into one of indie electronic's definitive acts, [wimpLink artistId=\"3529689\"]the Notwist[/wimpLink] ..."
    },
    "mainLink": ...,
    "followersAmount": 9753,
    "followingsAmount": ...,
    "listeners": ...,
    "foregroundColor": ...,
    "backgroundColor": ...,
    "bannerArtworkId": ...,
    "logoArtworkId": ...
  },
  "item": { ... },
  "items": [
    {
      "type": "TRACK_LIST",
      "title": "Popular tracks",
      "items": [ ... ]
    },
    {
      "type": "HORIZONTAL_LIST",
      "title": "Albums",
      "items": [ ... ]
    }
  ]
}
```
