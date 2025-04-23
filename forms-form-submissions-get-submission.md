# Get Form Submission

```
GET https://api.webflow.com/beta/form_submissions/:form_submission_id
```

Get information about a given form submissio.
**Required Scope:** `forms:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `form_submission_id` | string | Yes | Unique identifier for a Form Submission |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | The unique ID of the Form submission |
| `displayName` | string | No | The Form name displayed on the site |
| `siteId` | string | No | The unique ID of the Site the Form belongs to |
| `workspaceId` | string | No | The unique ID of the Workspace the Site belongs to |
| `dateSubmitted` | datetime | No | Date that the Form was submitted on |
| `formResponse` | map from strings to any | No | The data submitted in the Form |




## Errors

* **400:** Forms Get Submission Request Bad Request Error
* **401:** Forms Get Submission Request Unauthorized Error
* **403:** Forms Get Submission Request Forbidden Error
* **404:** Forms Get Submission Request Not Found Error
* **429:** Forms Get Submission Request Too Many Requests Error
* **500:** Forms Get Submission Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/form_submissions/580e63e98c9a982ac9b8b741 \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
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
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/forms/form-submissions/get-submission](https://developers.webflow.com/v2.0.0-beta/reference/forms/form-submissions/get-submission)*