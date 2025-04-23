# Create Site

```
POST https://api.webflow.com/beta/workspaces/:workspace_id/sites
```

Create a site.
**Required Scope:** `workspace:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `workspace_id` | string | Yes | Unique identifier for a Workspace |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the Site |
| `workspaceId` | string | No | Unique identifier for the Workspace |
| `createdOn` | datetime | No | Date the Site was created |
| `displayName` | string | No | Name given to Site |
| `shortName` | string | No | Slugified version of name |
| `lastPublished` | datetime | No | Date the Site was last published |
| `lastUpdated` | datetime | No | Date the Site was last updated |
| `previewUrl` | string | No | URL of a generated image for the given Site |
| `timeZone` | string | No | Site timezone set under Site Settings |
| `dataCollectionEnabled` | boolean | No | Indicates if data collection is enabled for the site. |
| `dataCollectionType` | enum | No | The type of data collection enabled for the site. (Values: always, optOut, disabled) |
| `parentFolderId` | string | No | The ID of the parent folder the Site exists in |
| `customDomains` | list of objects | No | N/A |
| `customDomains.id` | string | No | Unique identifier for the Domain |
| `customDomains.url` | string | No | The registered Domain name |
| `customDomains.lastPublished` | datetime | No | The date the custom domain was last published to |
| `locales` | object | No | N/A |
| `locales.primary` | object | No | The primary locale for the site or application. |
| `locales.primary.id` | string | No | The unique identifier for the locale. |
| `locales.primary.cmsLocaleId` | string | No | A CMS-specific identifier for the locale. |
| `locales.primary.enabled` | boolean | No | Indicates if the locale is enabled. |
| `locales.primary.displayName` | string | No | The display name of the locale, typically in English. |
| `locales.primary.displayImageId` | string | No | An optional ID for an image associated with the locale, nullable. |
| `locales.primary.redirect` | boolean | No | Determines if requests should redirect to the locale’s subdirectory. |
| `locales.primary.subdirectory` | string | No | The subdirectory path for the locale, used in URLs. |
| `locales.primary.tag` | string | No | A tag or code representing the locale, often following a standard format like ‘en-US’. |
| `locales.secondary` | list of objects | No | A list of secondary locales available for the site or application. |
| `locales.secondary.id` | string | No | The unique identifier for the locale. |
| `locales.secondary.cmsLocaleId` | string | No | A CMS-specific identifier for the locale. |
| `locales.secondary.enabled` | boolean | No | Indicates if the locale is enabled. |
| `locales.secondary.displayName` | string | No | The display name of the locale, typically in English. |
| `locales.secondary.displayImageId` | string | No | An optional ID for an image associated with the locale, nullable. |
| `locales.secondary.redirect` | boolean | No | Determines if requests should redirect to the locale’s subdirectory. |
| `locales.secondary.subdirectory` | string | No | The subdirectory path for the locale, used in URLs. |
| `locales.secondary.tag` | string | No | A tag or code representing the locale, often following a standard format like ‘en-US’. |




## Errors

* **400:** Sites Create Request Bad Request Error
* **401:** Sites Create Request Unauthorized Error
* **403:** Sites Create Request Forbidden Error
* **404:** Sites Create Request Not Found Error
* **429:** Sites Create Request Too Many Requests Error
* **500:** Sites Create Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/workspaces/580e63e98c9a982ac9b8b741/sites \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "name": "The Hitchhiker\'s Guide to the Galaxy"
}'
```

### Example Response (201 NewlyCreatedSite)

```json
{
  "id": "670ecf86817e3cc7a510eb6a",
  "workspaceId": "625860a7a6c16d624927122f",
  "createdOn": "2024-10-15T20:24:38Z",
  "displayName": "The Hitchiker‘s Guide",
  "shortName": "hitchikers-guide",
  "lastPublished": "2016-10-24T19:43:17Z",
  "lastUpdated": "2024-10-15T20:24:38Z",
  "previewUrl": "https://d1otoma47x30pg.cloudfront.net/580e63e98c9a982ac9b8b741/201610241243.png",
  "timeZone": "America/Los_Angeles",
  "dataCollectionEnabled": false,
  "dataCollectionType": "always",
  "parentFolderId": "670ece123598db72d9648be1",
  "customDomains": [
    {
      "id": "589a331aa51e760df7ccb89d",
      "url": "test-api-domain.com",
      "lastPublished": "2022-12-07T16:51:37Z"
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/create](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/create)*