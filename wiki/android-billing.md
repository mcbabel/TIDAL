Subscription purchase on Android and mobile operator integration.

### Get Active Google Play Subscriptions (verified 2026-11)
* Products the app offers in Google Play billing.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/googleplay/subscriptions/active```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "activeSubscriptions": [
    {
      "googlePlayProductId": "…",
      "subscriptionType": "PREMIUM",
      "subscriptionPlan": "STANDARD",
      "basePlan": {
        "basePlanTag": "monthly",
        "availableOfferTags": [ "freetrial" ],
        "replacementMode": "NA",
        "currentlyActive": false,
        "deferredStartDate": null
      }
    }
  ],
  "latestGooglePlaySubscription": null
}
```

### Get Purchase Status (verified 2026-11)
* Verified with an invalid token: `200 {"status":"NOT_FOUND"}`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/googleplay/purchase/status?purchaseToken={token}&productId={productId}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "status": "NOT_FOUND"
}
```

### Operator Subscriber Id (verified 2026-11)
* Answers `204 No Content` for an account without mobile operator billing. Related, not executed (operator login with a signed JWT of the operator): `POST v1/play/autologin` (`loginJwt`, `token`), `POST v1/registration/play` (`registrationJwt`, `clientVersion`, `token`).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/play/subscriberid```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
```204 No Content```
