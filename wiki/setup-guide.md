### Get Setup Tasks (verified 2026-11)
* Setup guide of the Android app (`com.aspiro.tidal` 2.215.0) (e.g. "transfer your music"). Base url is `https://api.tidal.com/v2/onboarding/`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/onboarding/tasks?version=2&locale={locale}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
[
  {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "title": "Transfer music",
    "icon": "playlists",
    "actions": [ { "title": "", "url": "", "type": "OPEN_CAROUSEL", "variant": "PRIMARY" } ],
    "asset": { "url": "https://…", "type": "IMAGE" },
    "completed": true
  }
]
```

### Get Subtasks (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/onboarding/tasks/{taskId}?version=2&locale={locale}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
List of subtasks (3 for the tested task).

### Complete Task (endpoint verified 2026-11 with a non-existent id: 200)
* Not executed with a real task: it cannot be undone. The web player uses `v2/onboarding/tasks/set-completed/{id}` as well ([Onboarding (v2)](onboarding-v2)).
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/onboarding/tasks/set-completed/{taskId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
