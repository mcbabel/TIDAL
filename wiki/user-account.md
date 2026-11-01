Account changes of the Android app (`com.aspiro.tidal` 2.215.0). None of the writes was executed: they change personal account data, send emails or accept legal agreements.

### Update User (not executed)
* Variants of the same endpoint: `acceptedEULA=true` (accept EULA), `profileName={name}`, and `firstName`, `lastName`, `profileName`, `email`, `newsletter`, … (update user).
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

### Request Verification Email (not executed)
* Sends an email.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/email/verify```
##### Header
```authorization: Bearer {access_token}```

### Change Email (not executed)
* Resend: `POST v2/email-change/{id}/resend` (verified with a non-existent id: `404`).
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/email-change```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```

### Facebook Connection (not executed)
* `accessToken` of Facebook; remove: `DELETE v1/users/{userId}/facebook`.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/facebook```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```
