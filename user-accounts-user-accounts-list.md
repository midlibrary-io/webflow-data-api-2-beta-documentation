# List Users

```
GET https://api.webflow.com/beta/sites/:site_id/users
```

Get a list of users for a site
**Required Scope:** `users:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `sort` | enum | No | Sort string to use when ordering usersExample(CreatedOn,Email,Status,LastLogin,UpdatedOn).Can be prefixed with a-to reverse the sort (ex.-CreatedOn) (Values: CreatedOn, -CreatedOn, Email, -Email, Status, -Status, LastLogin, -LastLogin, UpdatedOn, -UpdatedOn) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `count` | double | No | Number of users returned |
| `limit` | double | No | The limit specified in the request |
| `offset` | double | No | The offset specified for pagination |
| `total` | double | No | Total number of users in the collection |
| `users` | list of objects | No | List of Users for a Site |
| `users.id` | string | No | Unique identifier for the User |
| `users.isEmailVerified` | boolean | No | Shows whether the user has verified their email address |
| `users.lastUpdated` | datetime | No | The timestamp the user was updated |
| `users.invitedOn` | datetime | No | The timestamp the user was invited |
| `users.createdOn` | datetime | No | The timestamp the user was created |
| `users.lastLogin` | datetime | No | The timestamp the user was logged in |
| `users.status` | enum | No | The status of the user (Values: invited, verified, unverified) |
| `users.accessGroups` | list of objects | No | Access groups the user belongs to |
| `users.accessGroups.slug` | string | No | Access group identifier for APIs |
| `users.accessGroups.type` | enum | No | The type of access group based on how it was assigned to the user.admin- Assigned to the user via API or in the designerecommerce- Assigned to the user via an ecommerce purchase (Values: admin, ecommerce) |
| `users.data` | object | No | An object containing the User’s basic info and custom fields |
| `users.data.data` | object | No | N/A |
| `users.data.data.name` | string | No | The name of the user |
| `users.data.data.email` | string | No | The email address of the user |
| `users.data.data.accept-privacy` | boolean | No | Boolean indicating if the user has accepted the privacy policy |
| `users.data.data.accept-communications` | boolean | No | Boolean indicating if the user has accepted to receive communications |
| `users.data.data.additionalProperties` | string | No | Custom user attributes |




## Errors

* **400:** Users List Request Bad Request Error
* **401:** Users List Request Unauthorized Error
* **403:** Users List Request Forbidden Error
* **404:** Users List Request Not Found Error
* **429:** Users List Request Too Many Requests Error
* **500:** Users List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/users \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "count": 5,
  "limit": 5,
  "offset": 0,
  "total": 201,
  "users": [
    {
      "id": "6287ec36a841b25637c663df",
      "isEmailVerified": false,
      "lastUpdated": "2022-05-20T13:46:12Z",
      "invitedOn": "2016-10-24T19:41:29Z",
      "createdOn": "2022-05-20T13:46:12Z",
      "lastLogin": "2016-10-24T19:41:29Z",
      "status": "unverified",
      "accessGroups": [
        {
          "slug": "vogon-construction-crew",
          "type": "admin"
        }
      ]
    },
    {
      "id": "6287ec36a841b25637c663f0",
      "isEmailVerified": false,
      "lastUpdated": "2022-05-19T05:32:04Z",
      "invitedOn": "2016-10-24T19:41:29Z",
      "createdOn": "2022-05-19T05:32:04Z",
      "lastLogin": "2016-10-24T19:41:29Z",
      "status": "unverified",
      "accessGroups": [
        {
          "slug": "improbability-drive-test-subjects",
          "type": "admin"
        }
      ]
    },
    {
      "id": "6287ec36a841b25637c663d9",
      "isEmailVerified": true,
      "lastUpdated": "2022-05-17T03:34:06Z",
      "invitedOn": "2016-10-24T19:41:29Z",
      "createdOn": "2022-05-17T03:34:06Z",
      "lastLogin": "2016-10-24T19:41:29Z",
      "status": "verified",
      "accessGroups": [
        {
          "slug": "heart-of-gold-crew",
          "type": "admin"
        }
      ]
    },
    {
      "id": "6287ec37a841b25637c6641b",
      "isEmailVerified": false,
      "lastUpdated": "2022-05-15T03:46:09Z",
      "invitedOn": "2016-10-24T19:41:29Z",
      "createdOn": "2022-05-15T03:46:09Z",
      "lastLogin": "2016-10-24T19:41:29Z",
      "status": "unverified",
      "accessGroups": [
        {
          "slug": "hitchhikers-guide-research-team",
          "type": "admin"
        }
      ]
    },
    {
      "id": "6287ec37a841b25637c66449",
      "isEmailVerified": true,
      "lastUpdated": "2022-05-15T02:55:38Z",
      "invitedOn": "2016-10-24T19:41:29Z",
      "createdOn": "2022-05-15T02:55:38Z",
      "lastLogin": "2016-10-24T19:41:29Z",
      "status": "verified",
      "accessGroups": [
        {
          "slug": "milliways-reservationists",
          "type": "admin"
        }
      ]
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/user-accounts/list](https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/user-accounts/list)*