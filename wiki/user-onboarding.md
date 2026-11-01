### Get Onboarding Steps (verified 2026-11)
* Flags for onboarding hints the user has already seen.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/onboarding?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
[
  {
    "key": "CAST",
    "value": "true"
  },
  {
    "key": "CONTRIBUTOR",
    "value": "true"
  },
  {
    "key": "MENU_OFFLINE_CONTENT",
    "value": "true"
  },
  {
    "key": "ONBOARDING_WELCOME",
    "value": "true"
  },
  ...
]
```

### Set Onboarding Step (verified 2026-11)
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/onboarding?countryCode={country}```
##### Url-Encoded POST Parameter
```key: {key}```\
```value: true```
* Tested by setting a key that was already `true` again (`200`, no change).
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

### Set Early Access Program (verified 2026-11)
* Opts the user in or out of TIDAL's early access (beta) program. `GET` answers `405` (verified 2026-11). The current state is `earlyAccessProgram` in [Get User](user).
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/earlyAccessProgram?countryCode={country}```
##### Url-Encoded POST Parameter
```active: true|false```
* Tested by sending the current value again (`200`, no change).
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

#### Update 2026-11: Android app (verified)
* `POST v1/users/{userId}/onboarding/list` sets several flags at once. The keys are sent as **repeated** fields (`keys=A&keys=B`); a comma separated value creates one key with that literal name.
* `DELETE v1/users/{userId}/onboarding` removes all flags (`200`). Restore by posting the keys again.
