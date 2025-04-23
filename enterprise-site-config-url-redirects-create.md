# Create a URL redirect

```
POST https://api.webflow.com/beta/sites/:site_id/redirects
```

Add a new URL redirection rule to a site.
This endpoint allows you to define a source path (fromUrl) and its corresponding destination path (toUrl), which will dictate how traffic is rerouted on your site. This is useful for managing site changes, restructuring URLs, or handling outdated links.
**Required Scope:** `sites:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | The ID of the specific redirect rule |
| `fromUrl` | string | No | The source URL path that will be redirected. |
| `toUrl` | string | No | The target URL path where the user or client will be redirected. |




## Errors

* **400:** Redirects Create Request Bad Request Error
* **401:** Redirects Create Request Unauthorized Error
* **404:** Redirects Create Request Not Found Error
* **429:** Redirects Create Request Too Many Requests Error
* **500:** Redirects Create Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/redirects \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "fromUrl": "/mostly-harmless",
  "toUrl": "/earth"
}'
```

### Example Response (200 Successful)

```json
{
  "id": "42e1a2b7aa1a13f768a0042a",
  "fromUrl": "/mostly-harmless",
  "toUrl": "/earth"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/url-redirects/create](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/url-redirects/create)*