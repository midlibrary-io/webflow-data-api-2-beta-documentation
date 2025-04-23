# Get Authorization User Info

```
GET https://api.webflow.com/beta/token/authorized_by
```

Information about the Authorized User
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




## Errors

* **401:** Token Authorized by Request Unauthorized Error
* **403:** Token Authorized by Request Forbidden Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/token/authorized_by \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "id": "545bbecb7bdd6769632504a7",
  "email": "some@email.com",
  "firstName": "Some",
  "lastName": "One"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/meta/authorized-by](https://developers.webflow.com/v2.0.0-beta/reference/meta/authorized-by)*