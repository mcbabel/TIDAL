Public user profiles of TIDAL (social features of the Android app (`com.aspiro.tidal` 2.215.0)). See also [Get User Profile](user-profile) and [Get User Public Playlists](user-playlists-public).

### Get My Profile (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/profiles/me```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "userId": 123456789,
  "artistId": null,
  "name": null,
  "handle": null,
  "color": [ … ],
  "picture": null,
  "numberOfFollowers": 0,
  "numberOfFollows": 0,
  "prompts": [ … ],
  "socialLinks": [ … ]
}
```

### Get Profile (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/profiles/{userId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
Same fields as Get My Profile.

### Get Followers / Following (verified 2026-11)
* Following: `GET …/profiles/{userId}/following?includeOnly={enum}&cursor={cursor}`
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/profiles/{userId}/followers?cursor={cursor}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [ … ],
  "cursor": null
}
```

### Get Playlist Followers (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/profiles/followers?trn=trn:playlist:{uuid}&cursor={cursor}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [ … ],
  "cursor": null
}
```

### Follow / Unfollow (verified 2026-11)
* Unfollow: `DELETE https://api.tidal.com/v2/follow/?trn={trn}`
* `trn` can be a user (`trn:user:{id}`), artist (`trn:artist:{id}`) or playlist. Tested with an artist trn (`200` / `200`), so no user was notified.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/follow/?trn={trn}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
```200 OK``` (empty body)

### Get Profile Page (verified 2026-11 with a non-existent handle: 404)
* Dynamic page of a user profile by handle. The web player uses [`v2/profile/@{handle}`](artist-page-v2).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/profile/{handle}```
##### Header
```authorization: Bearer {access_token}```\
```If-None-Match: {eTag}``` (optional)

### Change Profile (not executed)
* Other profile writes of the app (all not executed because they change the public profile or cannot be undone):
* `PUT v2/profile/social-handles?facebook=&instagram=&snapchat=&tiktok=&twitter=&userId=`
* `PUT v2/profile/onboarded` / `DELETE v2/profile/onboarded` (enable / disable the public profile)
* `DELETE v2/profile/picture`, `GET v2/profile/picture/status` (status of a picture upload, `404` without upload)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/profile/profile-name?profileName={name}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
