# Create and Invite a User

```
POST https://api.webflow.com/beta/sites/:site_id/users/invite
```

Create and invite a user with an email address.
The user will be sent and invite via email, which they will need to accept in order to join paid any paid access group.
**Required Scope:** `users:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the User |
| `isEmailVerified` | boolean | No | Shows whether the user has verified their email address |
| `lastUpdated` | datetime | No | The timestamp the user was updated |
| `invitedOn` | datetime | No | The timestamp the user was invited |
| `createdOn` | datetime | No | The timestamp the user was created |
| `lastLogin` | datetime | No | The timestamp the user was logged in |
| `status` | enum | No | The status of the user (Values: invited, verified, unverified) |
| `accessGroups` | list of objects | No | Access groups the user belongs to |
| `accessGroups.slug` | string | No | Access group identifier for APIs |
| `accessGroups.type` | enum | No | The type of access group based on how it was assigned to the user.admin- Assigned to the user via API or in the designerecommerce- Assigned to the user via an ecommerce purchase (Values: admin, ecommerce) |
| `data` | object | No | An object containing the User’s basic info and custom fields |
| `data.data` | object | No | N/A |
| `data.data.name` | string | No | The name of the user |
| `data.data.email` | string | No | The email address of the user |
| `data.data.accept-privacy` | boolean | No | Boolean indicating if the user has accepted the privacy policy |
| `data.data.accept-communications` | boolean | No | Boolean indicating if the user has accepted to receive communications |
| `data.data.additionalProperties` | string | No | Custom user attributes |




## Errors

* **400:** Users Invite Request Bad Request Error
* **401:** Users Invite Request Unauthorized Error
* **403:** Users Invite Request Forbidden Error
* **404:** Users Invite Request Not Found Error
* **409:** Users Invite Request Conflict Error
* **429:** Users Invite Request Too Many Requests Error
* **500:** Users Invite Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/users/invite \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "email": "some.one@home.com",
  "accessGroups": [
    "webflowers"
  ]
}'
```

### Example Response (200 Successful)

```json
{
  "id": "6287ec36a841b25637c663df",
  "isEmailVerified": true,
  "lastUpdated": "2022-05-20T13:46:12Z",
  "invitedOn": "2022-05-20T13:46:12Z",
  "createdOn": "2022-05-20T13:46:12Z",
  "lastLogin": "2022-05-20T13:46:12Z",
  "status": "verified",
  "accessGroups": [
    {
      "slug": "webflowers",
      "type": "admin"
    }
  ],
  "data": {
    "data": {
      "name": "name",
      "email": "email",
      "accept-privacy": true,
      "accept-communications": true,
      "additionalProperties": "additionalProperties"
    }
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/user-accounts/invite](https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/user-accounts/invite)*