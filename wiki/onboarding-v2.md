### Get Playlist Import Url (verified 2026-11)
* Url to import playlists from other services (TuneMyMusic). Response is plain text.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/onboarding/tmm/migration?version=2&countryCode={country}&locale={locale}&deviceType={enum}&platform=WEB```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
```"https://offer.tidal.com/playlist/migration/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"```

### Complete Home Task (endpoint verified 2026-11)
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/onboarding/tasks/set-completed/{taskId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
* Verified with a non-existent task id (`200`, no visible effect). Not tested with a real task: completing a real home task hides it permanently and cannot be undone.
