# List Access Groups

```
GET https://api.webflow.com/beta/sites/:site_id/accessgroups
```

Get a list of access groups for a site
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
| `sort` | enum | No | Sort string to use when ordering access groups Can be prefixed with a-to reverse the sort (ex.-CreatedOn) (Values: CreatedOn, -CreatedOn) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `count` | double | No | Number of access groups returned |
| `limit` | double | No | The limit specified in the request |
| `offset` | double | No | The offset specified for pagination |
| `total` | double | No | Total number of access groups in the collection |
| `accessGroups` | list of objects | No | List of Site Access Groups |
| `accessGroups.id` | string | No | Unique identifier for the Access Group |
| `accessGroups.name` | string | No | Name of the the Access Group |
| `accessGroups.shortId` | string | No | Shortened unique identifier based on name, optimized for its use in the user’s JWT |
| `accessGroups.slug` | string | No | Shortened unique identifier based on name, optimized for human readability and public API use |
| `accessGroups.createdOn` | datetime | No | The date the Access Group was created |




## Errors

* **400:** Access Groups List Request Bad Request Error
* **401:** Access Groups List Request Unauthorized Error
* **403:** Access Groups List Request Forbidden Error
* **404:** Access Groups List Request Not Found Error
* **429:** Access Groups List Request Too Many Requests Error
* **500:** Access Groups List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/accessgroups \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "count": 1,
  "limit": 10,
  "offset": 0,
  "total": 1,
  "accessGroups": [
    {
      "id": "62be58d404be8a6cc900c081",
      "name": "Research Team",
      "shortId": "rt",
      "slug": "hitchhikers-guide-research-team",
      "createdOn": "2022-08-01T19:41:48Z"
    },
    {
      "id": "65a96161991e77bbb4a6c573",
      "name": "Admin",
      "shortId": "ad",
      "slug": "admin",
      "createdOn": "2022-08-01T19:41:48Z"
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/access-groups/list](https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/access-groups/list)*