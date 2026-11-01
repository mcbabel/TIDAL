### Init Chat (verified 2026-11)
* AI music assistant of the web player. Starts a chat in the context of the current page.
* Follow-up messages: `POST https://api.tidal.com/v2/chat/`
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/chat/init```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/json```
##### Body
``` yaml
{
  "currentProductId": "{trackId}",
  "pageId": "{id}",
  "pageType": "ALBUM",
  "sourceId": "{id}",
  "sourceType": "ALBUM"
}
```
* For accounts that are not part of the experiment the endpoint answers `400 {"detail":"User not enabled for AI chat experiment"}` (verified). The chat itself could not be tested with the test account for that reason.
