# Get Authorization Info

```
GET https://api.webflow.com/beta/token/introspect
```

Information about the authorization token


## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `authorization` | object | No | The Authorization object |
| `authorization.id` | string | No | The unique ID of the Authorization instance |
| `authorization.createdOn` | datetime | No | The date the Authorization was created |
| `authorization.lastUsed` | datetime | No | The date the Authorization was last used |
| `authorization.grantType` | string | No | The grant type of the Authorization |
| `authorization.rateLimit` | integer | No | The default rate limit for the Authorization (requests/min) |
| `authorization.scope` | string | No | Comma separted list of OAuth scopes corresponding to the Authorization |
| `authorization.authorizedTo` | object | No | N/A |
| `authorization.authorizedTo.siteIds` | list of any | No | Array of Sites this app is authorized to |
| `authorization.authorizedTo.workspaceIds` | list of any | No | Array of Workspaces this app is authorized to |
| `authorization.authorizedTo.userIds` | list of any | No | Array of Users this app is authorized to |
| `application` | any | No | N/A |




## Errors

* **401:** Token Introspect Request Unauthorized Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/token/introspect \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "authorization": {
    "id": "55818d58616600637b9a5786",
    "createdOn": "2016-10-03T23:12:00Z",
    "lastUsed": "2016-10-10T21:41:12Z",
    "grantType": "authorization_code",
    "rateLimit": 60,
    "scope": "assets:read,assets:write",
    "authorizedTo": {
      "siteIds": [
        "62f3b1f7eafac55d0c64ef91"
      ],
      "workspaceIds": [
        "52f3b1f7eafac55d0c64ef91"
      ],
      "userIds": [
        "545bbecb7bdd6769632504a7"
      ]
    }
  },
  "application": {
    "id": "55131cd036c09f7d07883dfc",
    "description": "My Amazing App",
    "homepage": "https://webflow.com",
    "displayName": "My Amazing App"
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/meta/introspect](https://developers.webflow.com/v2.0.0-beta/reference/meta/introspect)*