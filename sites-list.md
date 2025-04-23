# List Sites

```
GET https://api.webflow.com/beta/sites
```

List of all sites the provided access token is able to access.
**Required Scope:** `sites:read`


## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `sites` | list of objects | No | N/A |
| `sites.id` | string | No | Unique identifier for the Site |
| `sites.workspaceId` | string | No | Unique identifier for the Workspace |
| `sites.createdOn` | datetime | No | Date the Site was created |
| `sites.displayName` | string | No | Name given to Site |
| `sites.shortName` | string | No | Slugified version of name |
| `sites.lastPublished` | datetime | No | Date the Site was last published |
| `sites.lastUpdated` | datetime | No | Date the Site was last updated |
| `sites.previewUrl` | string | No | URL of a generated image for the given Site |
| `sites.timeZone` | string | No | Site timezone set under Site Settings |
| `sites.parentFolderId` | string | No | The ID of the parent folder the Site exists in |
| `sites.customDomains` | list of objects | No | N/A |
| `sites.customDomains.id` | string | No | Unique identifier for the Domain |
| `sites.customDomains.url` | string | No | The registered Domain name |
| `sites.customDomains.lastPublished` | datetime | No | The date the custom domain was last published to |
| `sites.locales` | object | No | N/A |
| `sites.locales.primary` | object | No | The primary locale for the site or application. |
| `sites.locales.primary.id` | string | No | The unique identifier for the locale. |
| `sites.locales.primary.cmsLocaleId` | string | No | A CMS-specific identifier for the locale. |
| `sites.locales.primary.enabled` | boolean | No | Indicates if the locale is enabled. |
| `sites.locales.primary.displayName` | string | No | The display name of the locale, typically in English. |
| `sites.locales.primary.displayImageId` | string | No | An optional ID for an image associated with the locale, nullable. |
| `sites.locales.primary.redirect` | boolean | No | Determines if requests should redirect to the locale’s subdirectory. |
| `sites.locales.primary.subdirectory` | string | No | The subdirectory path for the locale, used in URLs. |
| `sites.locales.primary.tag` | string | No | A tag or code representing the locale, often following a standard format like ‘en-US’. |
| `sites.locales.secondary` | list of objects | No | A list of secondary locales available for the site or application. |
| `sites.locales.secondary.id` | string | No | The unique identifier for the locale. |
| `sites.locales.secondary.cmsLocaleId` | string | No | A CMS-specific identifier for the locale. |
| `sites.locales.secondary.enabled` | boolean | No | Indicates if the locale is enabled. |
| `sites.locales.secondary.displayName` | string | No | The display name of the locale, typically in English. |
| `sites.locales.secondary.displayImageId` | string | No | An optional ID for an image associated with the locale, nullable. |
| `sites.locales.secondary.redirect` | boolean | No | Determines if requests should redirect to the locale’s subdirectory. |
| `sites.locales.secondary.subdirectory` | string | No | The subdirectory path for the locale, used in URLs. |
| `sites.locales.secondary.tag` | string | No | A tag or code representing the locale, often following a standard format like ‘en-US’. |
| `sites.dataCollectionEnabled` | boolean | No | Indicates if data collection is enabled for the site. |
| `sites.dataCollectionType` | enum | No | The type of data collection enabled for the site. (Values: always, optOut, disabled) |




## Errors

* **401:** Sites List Request Unauthorized Error
* **404:** Sites List Request Not Found Error
* **429:** Sites List Request Too Many Requests Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "sites": [
    {
      "id": "42e63e98c9a982ac9b8b741",
      "workspaceId": "42e63fc8c9a982ac9b8b744",
      "createdOn": "1979-10-12T12:00:00Z",
      "displayName": "Heart of Gold Spaceship",
      "shortName": "heart-of-gold",
      "lastPublished": "2023-04-02T12:42:00Z",
      "lastUpdated": "2016-10-24T19:43:17Z",
      "previewUrl": "https://d1otoma47x30pg.cloudfront.net/42e63e98c9a982ac9b8b741/197910121200.png",
      "timeZone": "DeepSpace/InfiniteImprobability",
      "parentFolderId": "1as2d3f4g5h6j7k8l9z0x1c2v3b4n5m6",
      "customDomains": [
        {
          "id": "589a331aa51e760df7ccb89e",
          "url": "heartofgold.galaxy",
          "lastPublished": "2022-12-07T16:51:37Z"
        }
      ],
      "locales": {
        "primary": {
          "id": "653fd9af6a07fc9cfd7a5e57",
          "cmsLocaleId": "653ad57de882f528b32e810e",
          "enabled": true,
          "displayName": "English - Heart of Gold Standard",
          "redirect": false,
          "subdirectory": "/en",
          "tag": "The Ultimate Answer"
        },
        "secondary": [
          {
            "id": "653fd9af6a07fc9cfd7a5e58",
            "cmsLocaleId": "653ad57de882f528b32e810g",
            "enabled": true,
            "displayName": "Betelgeusian - Vogon Liaison",
            "redirect": true,
            "subdirectory": "/bet",
            "tag": "Vogon"
          },
          {
            "id": "653fd9af6a07fc9cfd7a5e59",
            "cmsLocaleId": "653ad57de882f528b32e810h",
            "enabled": false,
            "displayName": "Magrathean - Custom Planet Designs",
            "redirect": true,
            "subdirectory": "/mg",
            "tag": "Magrathean"
          }
        ]
      },
      "dataCollectionEnabled": true,
      "dataCollectionType": "always"
    },
    {
      "id": "42e63e98c9a982ac9b8b742",
      "workspaceId": "42e63fc8c9a982ac9b8b745",
      "createdOn": "1981-10-12T12:00:00Z",
      "displayName": "Marvin's Personal Blog",
      "shortName": "paranoid-android",
      "lastPublished": "2023-04-02T12:45:00Z",
      "lastUpdated": "2016-10-24T19:43:17Z",
      "previewUrl": "https://d1otoma47x30pg.cloudfront.net/42e63e98c9a982ac9b8b742/198110121200.png",
      "timeZone": "DeepSpace/Depression",
      "customDomains": [
        {
          "id": "589a331aa51e760df7ccb89f",
          "url": "marvin.blog",
          "lastPublished": "2022-12-07T16:51:37Z"
        }
      ],
      "locales": {
        "primary": {
          "id": "653fd9af6a07fc9cfd7a5e57",
          "cmsLocaleId": "653ad57de882f528b32e810e",
          "enabled": true,
          "displayName": "English - Marvin's Musings",
          "redirect": false,
          "subdirectory": "/en",
          "tag": "English"
        },
        "secondary": [
          {
            "id": "653fd9af6a07fc9cfd7a5e56",
            "cmsLocaleId": "653ad57de882f528b32e810f",
            "enabled": true,
            "displayName": "Squornshellous - Mattress Speak",
            "redirect": true,
            "subdirectory": "/sr",
            "tag": "Squornshellous"
          }
        ]
      },
      "dataCollectionEnabled": true,
      "dataCollectionType": "always"
    },
    {
      "id": "42e63e98c9a982ac9b8b743",
      "workspaceId": "42e63fc8c9a982ac9b8b746",
      "createdOn": "1982-10-12T12:00:00Z",
      "displayName": "Vogon Poetry Archive",
      "shortName": "vogon-poetry",
      "lastPublished": "2023-04-02T12:50:00Z",
      "lastUpdated": "2016-10-24T19:43:17Z",
      "previewUrl": "https://d1otoma47x30pg.cloudfront.net/42e63e98c9a982ac9b8b743/198210121200.png",
      "timeZone": "Vogsphere/PoetryHall",
      "customDomains": [
        {
          "id": "589a331aa51e760df7ccb8a0",
          "url": "vogonpoetry.galaxy",
          "lastPublished": "2022-12-07T16:51:37Z"
        }
      ],
      "locales": {
        "primary": {
          "id": "653fd9af6a07fc9cfd7a5e55",
          "cmsLocaleId": "653ad57de882f528b32e810d",
          "enabled": true,
          "displayName": "English - Vogon Verse",
          "redirect": false,
          "subdirectory": "/en",
          "tag": "Third Worst Poetry"
        },
        "secondary": [
          {
            "id": "653fd9af6a07fc9cfd7a5e54",
            "cmsLocaleId": "653ad57de882f528b32e810c",
            "enabled": true,
            "displayName": "Galactic - Universal Language",
            "redirect": true,
            "subdirectory": "/gl",
            "tag": "Pan-Galactic Gargle Blaster"
          }
        ]
      },
      "dataCollectionEnabled": true,
      "dataCollectionType": "always"
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/sites/list](https://developers.webflow.com/v2.0.0-beta/reference/sites/list)*