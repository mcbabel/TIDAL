#### Example Request
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/login/username```
##### Url-Encoded Parameter
```username: {username}```\
```password: {password}```\
```token: {client_id}```\
```clientUniqueKey: {randomBytes}``` (optional)\
```clientVersion: {version}``` (optional)

#### Example Response
```yaml
{
  "userId": xxxxxxxxx,
  "sessionId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "countryCode": "DE"
}
```

Session based authentication works with the "sessionId={sessionId}" Url parameter. The authentication header is not necessary.

#### Update 2026-11 (not executed)
Not tested: it needs a real username and password, and the client_ids that still allowed this login were disabled (see [Deprecation](Deprecation)). Entering account passwords is not part of these tests.
