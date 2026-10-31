#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/subscription?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "validUntil": "1920-11-28T17:28:02.333+0000",
  "status": "ACTIVE",
  "subscription": {
    "type": "HIFI",
    "offlineGracePeriod": 30
  },
  "highestSoundQuality": "HI_RES",
  "premiumAccess": true,
  "canGetTrial": false,
  "paymentType": "PARENT"
}
```
``` yaml
{
  "validUntil": "1920-11-20T14:56:31.747+0000",
  "status": "ACTIVE",
  "subscription": {
    "type": "FREE",
    "offlineGracePeriod": 0
  },
  "highestSoundQuality": null,
  "premiumAccess": false,
  "canGetTrial": true,
  "paymentType": "NONE"
}
```

#### Update 2026-11 (verified)
* Since 2024 the subscription types are `FREE` and `PREMIUM` (`HIFI` / `HIFI_PLUS` are legacy). `highestSoundQuality` still reports `HI_RES` for Premium, which means `HI_RES_LOSSLESS` today, see [Audio Quality](AudioQuality).
* New fields: `startDate`, `paymentOverdue`.
