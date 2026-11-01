### Init Chat (from web player code 2026-11, not live-tested)
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
