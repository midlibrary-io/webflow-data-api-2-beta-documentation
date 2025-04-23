# Get URL redirects

```
GET https://api.webflow.com/beta/sites/:site_id/redirects
```

Fetch a list of all URL redirect rules configured for a specific site.
Use this endpoint to review, audit, or manage the redirection rules that control how traffic is rerouted on your site.
**Required Scope:** `sites:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `redirects` | list of objects | No | List of redirects for a given site |
| `redirects.id` | string | No | The ID of the specific redirect rule |
| `redirects.fromUrl` | string | No | The source URL path that will be redirected. |
| `redirects.toUrl` | string | No | The target URL path where the user or client will be redirected. |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Redirects List Request Bad Request Error
* **401:** Redirects List Request Unauthorized Error
* **404:** Redirects List Request Not Found Error
* **429:** Redirects List Request Too Many Requests Error
* **500:** Redirects List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/redirects \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "redirects": [
    {
      "id": "42e1a2b7aa1a13f768a0042a",
      "fromUrl": "/mostly-harmless",
      "toUrl": "/earth"
    },
    {
      "id": "6x9e7f8d9a4b1c2d3e4f5678",
      "fromUrl": "/babel-fish",
      "toUrl": "/translate"
    }
  ],
  "pagination": {
    "limit": 100,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/url-redirects/get](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/url-redirects/get)*