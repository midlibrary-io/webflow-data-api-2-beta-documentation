# Create Asset Metadata

```
POST https://api.webflow.com/beta/sites/:site_id/assets
```

Create a new asset entry.
This endpoint generates a response with the following information:uploadUrlanduploadDetails.
You can use these two properties toupload the file to Amazon s3 by making a POSTrequest to theuploadUrlwith theuploadDetailsobject as your header information in the request.
**Required Scope:** `assets:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `uploadDetails` | object | No | Metadata for uploading the asset binary |
| `uploadDetails.acl` | string | No | N/A |
| `uploadDetails.bucket` | string | No | N/A |
| `uploadDetails.X-Amz-Algorithm` | string | No | N/A |
| `uploadDetails.X-Amz-Credential` | string | No | N/A |
| `uploadDetails.X-Amz-Date` | string | No | N/A |
| `uploadDetails.key` | string | No | N/A |
| `uploadDetails.Policy` | string | No | N/A |
| `uploadDetails.X-Amz-Signature` | string | No | N/A |
| `uploadDetails.success_action_status` | string | No | N/A |
| `uploadDetails.content-type` | string | No | N/A |
| `uploadDetails.Cache-Control` | string | No | N/A |
| `contentType` | string | No | N/A |
| `id` | string | No | N/A |
| `parentFolder` | string | No | Parent folder for the asset |
| `uploadUrl` | string | No | N/A |
| `assetUrl` | string | No | S3 link to the asset |
| `hostedUrl` | string | No | Represents the link to the asset |
| `originalFileName` | string | No | Original file name when uploaded. If not specified at time of upload, it may be extracted from the raw file name |
| `createdOn` | datetime | No | Date the asset metadata was created |
| `lastUpdated` | datetime | No | Date the asset metadata was last updated |




## Errors

* **400:** Assets Create Request Bad Request Error
* **401:** Assets Create Request Unauthorized Error
* **404:** Assets Create Request Not Found Error
* **429:** Assets Create Request Too Many Requests Error
* **500:** Assets Create Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/assets \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "fileName": "file.png",
  "fileHash": "3c7d87c9575702bc3b1e991f4d3c638e"
}'
```

### Example Response (200 Successful)

```json
{
  "uploadDetails": {
    "acl": "public-read",
    "bucket": "webflow-bucket-name",
    "X-Amz-Algorithm": "AWS4-HMAC-SHA256",
    "X-Amz-Credential": "<credential-key>/<date>/<region-zone>/s3/aws4_request",
    "X-Amz-Date": "<date-in-iso-like-string>",
    "key": "<siteId>/<fileId>_<filename-with-extension>",
    "Policy": "<a-very-long-alphanumeric-token-with-equal-sign-at-the-end>",
    "X-Amz-Signature": "<one-line-ling-alphanumeric-signature>",
    "success_action_status": "201",
    "content-type": "image/png",
    "Cache-Control": "max-age=31536000, must-revalidate"
  },
  "contentType": "image/png",
  "id": "64358b9544249dc43d37d2b7",
  "parentFolder": "6436b1ce5281cace05b65aea",
  "uploadUrl": "https://s3.amazonaws.com/webflow-dev-assets/643021114e290e0d3a0602b2/64358b9544249dc43d37d2b7_Screenshot%202023-04-11%20at%209.50.42%20AM.png",
  "assetUrl": "https://s3.amazonaws.com/webflow-prod-assets/6258612d1ee792848f805dcf/660d907ab9e91e3e9f56385e_paranoidAndroid-2024.png",
  "hostedUrl": "https://d1otoma47x30pg.cloudfront.net/643021114e290e0d3a0602b2/64358b9544249dc43d37d2b7_Screenshot%202023-04-11%20at%209.50.42%20AM.png",
  "originalFileName": "file.png",
  "createdOn": "2023-04-11T16:32:21Z",
  "lastUpdated": "2023-04-12T20:31:03Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/assets/assets/create](https://developers.webflow.com/v2.0.0-beta/reference/assets/assets/create)*