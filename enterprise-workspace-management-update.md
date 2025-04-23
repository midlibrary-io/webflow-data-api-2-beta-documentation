# Update Site

```
PATCH https://api.webflow.com/beta/sites/:site_id
```

Update a site.
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

* **400:** Sites Update Request Bad Request Error
* **401:** Sites Update Request Unauthorized Error
* **403:** Sites Update Request Forbidden Error
* **404:** Sites Update Request Not Found Error
* **429:** Sites Update Request Too Many Requests Error
* **500:** Sites Update Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741 \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

### Example Response (200 Updated)

```json
{
  "id": "42e98c9a982ac9b8b742",
  "workspaceId": "42e63e98c9a982ac9b8b742",
  "createdOn": "1979-10-12T12:00:00Z",
  "displayName": "The Hitchhiker's Guide to the Galaxy",
  "shortName": "hitchhikers-guide",
  "lastPublished": "2023-04-02T12:42:00Z",
  "lastUpdated": "2023-04-02T12:42:00Z",
  "previewUrl": "https://screenshots.webflow.com/sites/6258612d1ee792848f805dcf/20231219211811_d5990556c743f33b7071300a03bf67e6.png",
  "timeZone": "Magrathea/FactoryFloor",
  "dataCollectionEnabled": true,
  "dataCollectionType": "always",
  "parentFolderId": "1as2d3f4g5h6j7k8l9z0x1c2v3b4n5m6",
  "customDomains": [
    {
      "id": "589a331aa51e760df7ccb89d",
      "url": "hitchhikersguide.galaxy",
      "lastPublished": "2022-12-07T16:51:37Z"
    },
    {
      "id": "589a331aa51e760df7ccb89e",
      "url": "heartofgold.spaceship",
      "lastPublished": "2022-12-07T16:51:37Z"
    }
  ],
  "locales": {
    "primary": {
      "id": "653fd9af6a07fc9cfd7a5e57",
      "cmsLocaleId": "653ad57de882f528b32e810e",
      "enabled": false,
      "displayName": "English (United States)",
      "redirect": true,
      "subdirectory": "",
      "tag": "en-US"
    },
    "secondary": [
      {
        "id": "653fd9af6a07fc9cfd7a5e56",
        "cmsLocaleId": "653fd9af6a07fc9cfd7a5e5d",
        "enabled": true,
        "displayName": "French (France)",
        "redirect": true,
        "subdirectory": "fr-fr",
        "tag": "fr-FR"
      },
      {
        "id": "654112a3a525b2739d97664c",
        "cmsLocaleId": "654112a3a525b2739d97664f",
        "enabled": true,
        "displayName": "Spanish (Mexico)",
        "redirect": true,
        "subdirectory": "es-mx",
        "tag": "es-MX"
      }
    ]
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/update](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/update)*