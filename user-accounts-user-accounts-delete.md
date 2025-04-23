# Delete User

```
DELETE https://api.webflow.com/beta/sites/:site_id/users/:user_id
```

Delete a User by ID
**Required Scope:** `users:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `user_id` | string | Yes | Unique identifier for a User |




## Errors

* **400:** Users Delete Request Bad Request Error
* **401:** Users Delete Request Unauthorized Error
* **403:** Users Delete Request Forbidden Error
* **404:** Users Delete Request Not Found Error
* **429:** Users Delete Request Too Many Requests Error
* **500:** Users Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/users/580e63e98c9a982ac9b8b741 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/user-accounts/delete](https://developers.webflow.com/v2.0.0-beta/reference/user-accounts/user-accounts/delete)*