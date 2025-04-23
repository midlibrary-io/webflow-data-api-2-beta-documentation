# List Form Submissions

```
GET https://api.webflow.com/beta/forms/:form_id/submissions
```

List form submissions for a given form
**Required Scope:** `forms:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `form_id` | string | Yes | Unique identifier for a Form |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `formSubmissions` | list of objects | No | N/A |
| `formSubmissions.id` | string | No | The unique ID of the Form submission |
| `formSubmissions.displayName` | string | No | The Form name displayed on the site |
| `formSubmissions.siteId` | string | No | The unique ID of the Site the Form belongs to |
| `formSubmissions.workspaceId` | string | No | The unique ID of the Workspace the Site belongs to |
| `formSubmissions.dateSubmitted` | datetime | No | Date that the Form was submitted on |
| `formSubmissions.formResponse` | map from strings to any | No | The data submitted in the Form |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Forms List Submissions Request Bad Request Error
* **401:** Forms List Submissions Request Unauthorized Error
* **403:** Forms List Submissions Request Forbidden Error
* **404:** Forms List Submissions Request Not Found Error
* **429:** Forms List Submissions Request Too Many Requests Error
* **500:** Forms List Submissions Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/forms/580e63e98c9a982ac9b8b741/submissions \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "formSubmissions": [
    {
      "id": "6321ca84df3949bfc6752327",
      "displayName": "Sample Form",
      "siteId": "62749158efef318abc8d5a0f",
      "workspaceId": "62749158efef318abc8d5a0f",
      "dateSubmitted": "2022-09-14T12:35:16Z",
      "formResponse": {
        "First Name": "Arthur",
        "Last Name": "Dent"
      }
    },
    {
      "id": "660d64fabf6e0a0d4edab981",
      "displayName": "Sample Form",
      "siteId": "62749158efef318abc8d5a0f",
      "workspaceId": "62749158efef318abc8d5a0f",
      "dateSubmitted": "2022-09-14T12:35:16Z",
      "formResponse": {
        "First Name": "Ford",
        "Last Name": "Prefect"
      }
    }
  ],
  "pagination": {
    "limit": 25,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/forms/form-submissions/list-submissions](https://developers.webflow.com/v2.0.0-beta/reference/forms/form-submissions/list-submissions)*