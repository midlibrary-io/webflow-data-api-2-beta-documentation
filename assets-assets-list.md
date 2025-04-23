# List Assets

```
GET https://api.webflow.com/beta/sites/:site_id/assets
```

List assets for a given site
**Required Scope:** `assets:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `locale` | string | No | Unique identifier for a specific locale. Applicable, when using localization. |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for this asset |
| `contentType` | string | No | File format type |
| `size` | integer | No | size in bytes |
| `siteId` | string | No | Unique identifier for the site that hosts this asset |
| `hostedUrl` | string | No | Link to the asset |
| `originalFileName` | string | No | Original file name at the time of upload |
| `displayName` | string | No | Display name of the asset |
| `lastUpdated` | datetime | No | Date the asset metadata was last updated |
| `createdOn` | datetime | No | Date the asset metadata was created |
| `variants` | list of objects | No | A list ofasset variantscreated by Webflow to serve your site responsively. |
| `variants.hostedUrl` | string | No | URL of where the asset variant is hosted |
| `variants.originalFileName` | string | No | Original file name of the variant |
| `variants.displayName` | string | No | Display name of the variant |
| `variants.format` | string | No | format of the variant |
| `variants.width` | integer | No | Width in pixels |
| `variants.height` | integer | No | Height in pixels |
| `variants.quality` | integer | No | Value between 0 and 100 representing the image quality |
| `variants.error` | string | No | Any associated validation errors |
| `altText` | string | No | The visual description of the asset |




## Errors

* **400:** Assets List Request Bad Request Error
* **401:** Assets List Request Unauthorized Error
* **404:** Assets List Request Not Found Error
* **429:** Assets List Request Too Many Requests Error
* **500:** Assets List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/assets \
     -H "Authorization: Bearer <token>" \
     -d locale=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
[
  {
    "id": "63e5889e7fe4eafa7384cea4",
    "contentType": "image/png",
    "size": 2212772,
    "siteId": "63938b302ea6b0aa6f3d8745",
    "hostedUrl": "https://s3.amazonaws.com/webflow-prod-assets/63938b302ea6b0aa6f3d8745/63e5889e7fe4eafa7384cea4_Vectors-Wrapper.svg",
    "originalFileName": "Candy-Wrapper.svg",
    "displayName": "63e5889e7fe4eafa7384cea4_Candy-Wrapper.png",
    "lastUpdated": "2023-03-01T23:42:57Z",
    "createdOn": "2023-02-09T23:58:22Z",
    "variants": [
      {
        "hostedUrl": "https://s3.amazonaws.com/webflow-prod-assets/6258612d1ee792848f805dcf/660d83ce30f3a599ddb0bdb3_Screenshot%202024-03-20%20at%209.03.24%E2%80%AFPM-p-500.png",
        "originalFileName": "Screenshot%202024-03-20%20at%209.03.24%E2%80%AFPM-p-500.png",
        "displayName": "660d83ce30f3a599ddb0bdb3_Screenshot%202024-03-20%20at%209.03.24%E2%80%AFPM-p-500.png",
        "format": "png",
        "width": 500,
        "height": 900,
        "quality": 100
      }
    ],
    "altText": "A single candy wrapper"
  }
]
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/assets/assets/list](https://developers.webflow.com/v2.0.0-beta/reference/assets/assets/list)*