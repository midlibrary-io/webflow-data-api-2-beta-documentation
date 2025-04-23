# Resolve ID Token

```
POST https://api.webflow.com/beta/token/resolve
```

Information about the authorized user derived from the resolved ID TokenAccess to this endpoint requires a bearer token from aData Client App.
**Required Scope** | `authorized_user:read`


## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | The unique ID of the user |
| `email` | string | No | The user’s email address |
| `firstName` | string | No | The user’s first name |
| `lastName` | string | No | The user’s last name |
| `siteId` | string | No | The ID of the site associated with the user |




## Errors

* **401:** ID Token Resolve Request Unauthorized Error
* **403:** ID Token Resolve Request Forbidden Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/token/resolve \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

### Example Response (200 Successful)

```json
{
  "id": "545bbecb7bdd6769632504a7",
  "email": "someone@email.com",
  "firstName": "Some",
  "lastName": "One",
  "siteId": "42e63e98c9a982ac9b8b741"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/meta/resolve](https://developers.webflow.com/v2.0.0-beta/reference/meta/resolve)*