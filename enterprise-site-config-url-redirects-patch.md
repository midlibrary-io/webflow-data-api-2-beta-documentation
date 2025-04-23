# Update URL redirect

```
PATCH https://api.webflow.com/beta/sites/:site_id/redirects/:redirect_id
```

Update a URL redirection rule from a site.
**Required Scope:** `sites:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `redirect_id` | string | Yes | Unique identifier site rediect |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | The ID of the specific redirect rule |
| `fromUrl` | string | No | The source URL path that will be redirected. |
| `toUrl` | string | No | The target URL path where the user or client will be redirected. |




## Errors

* **400:** Redirects Update Request Bad Request Error
* **401:** Redirects Update Request Unauthorized Error
* **404:** Redirects Update Request Not Found Error
* **429:** Redirects Update Request Too Many Requests Error
* **500:** Redirects Update Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/redirects/66c4cb9a20cac35ed19500e6 \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "fromUrl": "/mostly-harmless",
  "toUrl": "/earth"
}'
```

### Example Response (200 Updated)

```json
{
  "id": "42e1a2b7aa1a13f768a0042a",
  "fromUrl": "/mostly-harmless",
  "toUrl": "/earth"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/url-redirects/patch](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/url-redirects/patch)*