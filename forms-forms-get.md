# Get Form Schema

```
GET https://api.webflow.com/beta/forms/:form_id
```

Get information about a given form.
**Required Scope:** `forms:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `form_id` | string | Yes | Unique identifier for a Form |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `displayName` | string | No | The Form name displayed on the site |
| `createdOn` | datetime | No | Date that the Form was created on |
| `lastUpdated` | datetime | No | Date that the Form was last updated on |
| `fields` | map from strings to objects | No | A collection of form field objects |
| `fields.displayName` | string | No | The field name displayed on the site |
| `fields.type` | enum | No | The field type (Values: Plain, Email, Password, Phone, Number) |
| `fields.placeholder` | string | No | The placeholder text for the field |
| `fields.userVisible` | boolean | No | Whether the field is visible to the user |
| `responseSettings` | object | No | Settings for form responses |
| `responseSettings.redirectUrl` | string | No | The url or path to redirect the user to after form submission |
| `responseSettings.redirectMethod` | string | No | The HTTP request method to use for the redirectUrl (eg. POST or GET) |
| `responseSettings.redirectAction` | string | No | The action to take after form submission |
| `responseSettings.sendEmailConfirmation` | boolean | No | Whether to send an email confirmation to the user |
| `id` | string | No | The unique ID for the Form |
| `siteId` | string | No | The unique ID of the Site the Form belongs to |
| `siteDomainId` | string | No | The unique ID corresponding to the site’s Domain name |
| `pageId` | string | No | The unique ID for the Page on which the Form is placed |
| `pageName` | string | No | The user-visible name of the Page where the Form is placed |
| `formElementId` | string | No | The unique ID of the Form element |
| `workspaceId` | string | No | The unique ID of the Workspace the Site belongs to |




## Errors

* **400:** Forms Get Request Bad Request Error
* **401:** Forms Get Request Unauthorized Error
* **403:** Forms Get Request Forbidden Error
* **404:** Forms Get Request Not Found Error
* **429:** Forms Get Request Too Many Requests Error
* **500:** Forms Get Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/forms/580e63e98c9a982ac9b8b741 \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "displayName": "Email Form",
  "createdOn": "2016-10-24T19:41:29Z",
  "lastUpdated": "2016-10-24T19:43:17Z",
  "fields": {
    "660d5bcc9c0772150459dfb1": {
      "displayName": "Name",
      "type": "Plain",
      "userVisible": true
    },
    "589a331aa51e760df7ccb89d": {
      "displayName": "Email",
      "type": "Email",
      "placeholder": "Enter your email",
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
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/forms/forms/get](https://developers.webflow.com/v2.0.0-beta/reference/forms/forms/get)*