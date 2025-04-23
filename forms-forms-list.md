# List Forms

```
GET https://api.webflow.com/beta/sites/:site_id/forms
```

List forms for a given site.
**Required Scope:** `forms:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `forms` | list of objects | No | N/A |
| `forms.displayName` | string | No | The Form name displayed on the site |
| `forms.createdOn` | datetime | No | Date that the Form was created on |
| `forms.lastUpdated` | datetime | No | Date that the Form was last updated on |
| `forms.fields` | map from strings to objects | No | A collection of form field objects |
| `forms.fields.displayName` | string | No | The field name displayed on the site |
| `forms.fields.type` | enum | No | The field type (Values: Plain, Email, Password, Phone, Number) |
| `forms.fields.placeholder` | string | No | The placeholder text for the field |
| `forms.fields.userVisible` | boolean | No | Whether the field is visible to the user |
| `forms.responseSettings` | object | No | Settings for form responses |
| `forms.responseSettings.redirectUrl` | string | No | The url or path to redirect the user to after form submission |
| `forms.responseSettings.redirectMethod` | string | No | The HTTP request method to use for the redirectUrl (eg. POST or GET) |
| `forms.responseSettings.redirectAction` | string | No | The action to take after form submission |
| `forms.responseSettings.sendEmailConfirmation` | boolean | No | Whether to send an email confirmation to the user |
| `forms.id` | string | No | The unique ID for the Form |
| `forms.siteId` | string | No | The unique ID of the Site the Form belongs to |
| `forms.siteDomainId` | string | No | The unique ID corresponding to the site’s Domain name |
| `forms.pageId` | string | No | The unique ID for the Page on which the Form is placed |
| `forms.pageName` | string | No | The user-visible name of the Page where the Form is placed |
| `forms.formElementId` | string | No | The unique ID of the Form element |
| `forms.workspaceId` | string | No | The unique ID of the Workspace the Site belongs to |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Forms List Request Bad Request Error
* **401:** Forms List Request Unauthorized Error
* **403:** Forms List Request Forbidden Error
* **404:** Forms List Request Not Found Error
* **409:** Forms List Request Conflict Error
* **429:** Forms List Request Too Many Requests Error
* **500:** Forms List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/forms \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "forms": [
    {
      "displayName": "Email Form",
      "createdOn": "2016-10-24T19:41:29Z",
      "lastUpdated": "2016-10-24T19:43:17Z",
      "fields": {
        "0": {
          "displayName": "Email",
          "userVisible": true
        },
        "1": {
          "displayName": "Email",
          "userVisible": true
        }
      },
      "responseSettings": {
        "redirectUrl": "https://example.com",
        "redirectMethod": "GET",
        "sendEmailConfirmation": true
      },
      "id": "589a331aa51e760df7ccb89e",
      "siteId": "580e63e98c9a982ac9b8b741",
      "siteDomainId": "6419db964a9c436a4baf6248",
      "pageId": "6419db964a9c43f6a3af6348",
      "pageName": "Home",
      "formElementId": "4e038d2c-6a1e-4953-7be9-a59a2b453177",
      "workspaceId": "580e63fc8c9a982ac9b8b744"
    },
    {
      "displayName": "Name Form",
      "createdOn": "2016-10-24T19:41:29Z",
      "lastUpdated": "2016-10-24T19:43:17Z",
      "fields": {
        "0": {
          "displayName": "Email",
          "userVisible": true
        }
      },
      "responseSettings": {
        "redirectUrl": "https://example.com",
        "redirectMethod": "GET",
        "sendEmailConfirmation": false
      },
      "id": "580ff8d7ba3e45ba9fe588e9",
      "siteId": "580e63e98c9a982ac9b8b741",
      "siteDomainId": "6419db964a9c436a4baf6248",
      "pageId": "6419db964a9c43f6a3af6348",
      "pageName": "Home",
      "formElementId": "4e038d2c-6a1e-4953-7be9-a59a2b453177",
      "workspaceId": "580e63fc8c9a982ac9b8b744"
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
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/forms/forms/list](https://developers.webflow.com/v2.0.0-beta/reference/forms/forms/list)*