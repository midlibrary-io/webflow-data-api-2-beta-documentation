# List Pages

```
GET https://api.webflow.com/beta/sites/:site_id/pages
```

List of all pages for a site.
**Required Scope:** `pages:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `localeId` | string | No | Unique identifier for a specific locale. Applicable, when using localization. |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `pages` | list of objects | No | N/A |
| `pages.id` | string | No | Unique identifier for the Page |
| `pages.siteId` | string | No | Unique identifier for the Site |
| `pages.title` | string | No | Title of the Page |
| `pages.slug` | string | No | slug of the Page (derived from title) |
| `pages.parentId` | string | No | Identifier of the parent folder |
| `pages.collectionId` | string | No | Unique identifier for a linked Collection, value will be null if the Page is not part of a Collection. |
| `pages.createdOn` | datetime | No | The date the Page was created |
| `pages.lastUpdated` | datetime | No | The date the Page was most recently updated |
| `pages.archived` | boolean | No | Whether the Page has been archived |
| `pages.draft` | boolean | No | Whether the Page is a draft |
| `pages.canBranch` | boolean | No | Indicates whether the Page supportsPage Branching |
| `pages.isBranch` | boolean | No | Indicates whether the Page is a Branch of another PagePage Branching |
| `pages.isMembersOnly` | boolean | No | Indicates whether the Page is restricted byMemberships Controls |
| `pages.seo` | object | No | SEO-related fields for the Page |
| `pages.seo.title` | string | No | The Page title shown in search engine results |
| `pages.seo.description` | string | No | The Page description shown in search engine results |
| `pages.openGraph` | object | No | Open Graph fields for the Page |
| `pages.openGraph.title` | string | No | The title supplied to Open Graph annotations |
| `pages.openGraph.titleCopied` | boolean | No | Indicates the Open Graph title was copied from the SEO title |
| `pages.openGraph.description` | string | No | The description supplied to Open Graph annotations |
| `pages.openGraph.descriptionCopied` | boolean | No | Indicates the Open Graph description was copied from the SEO description |
| `pages.localeId` | string | No | Unique ID of the page locale |
| `pages.publishedPath` | string | No | Relative path of the published page URL |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Pages List Request Bad Request Error
* **401:** Pages List Request Unauthorized Error
* **404:** Pages List Request Not Found Error
* **429:** Pages List Request Too Many Requests Error
* **500:** Pages List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/pages \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
{
  "pages": [
    {
      "id": "6596da6045e56dee495bcbba",
      "siteId": "6258612d1ee792848f805dcf",
      "title": "Guide to the Galaxy",
      "slug": "guide-to-the-galaxy",
      "createdOn": "2024-03-11T10:42:00Z",
      "lastUpdated": "2024-03-11T10:42:42Z",
      "archived": false,
      "draft": false,
      "canBranch": true,
      "isBranch": false,
      "isMembersOnly": false,
      "seo": {
        "title": "The Ultimate Hitchhiker's Guide to the Galaxy",
        "description": "Everything you need to know about the galaxy, from avoiding Vogon poetry to the importance of towels."
      },
      "openGraph": {
        "title": "Explore the Cosmos with The Ultimate Guide",
        "titleCopied": false,
        "description": "Dive deep into the mysteries of the universe with your guide to everything galactic.",
        "descriptionCopied": false
      },
      "localeId": "653fd9af6a07fc9cfd7a5e57",
      "publishedPath": "/en-us/guide-to-the-galaxy"
    },
    {
      "id": "6596da6045e56dee495bcbad",
      "siteId": "6258612d1ee792848f805dcf",
      "title": "Towel Day Celebrations",
      "slug": "towel-day",
      "createdOn": "2024-05-25T09:00:00Z",
      "lastUpdated": "2024-05-25T09:42:00Z",
      "archived": false,
      "draft": false,
      "canBranch": true,
      "isBranch": false,
      "isMembersOnly": false,
      "seo": {
        "title": "Celebrate Towel Day - The Hitchhiker's Guide to the Galaxy",
        "description": "A guide to celebrating Towel Day, in honor of the most massively useful thing an interstellar hitchhiker can have."
      },
      "openGraph": {
        "title": "Towel Day - Don't Panic",
        "titleCopied": false,
        "description": "Join the galaxy in celebrating Towel Day, the day dedicated to carrying towels everywhere in memory of Douglas Adams.",
        "descriptionCopied": false
      },
      "localeId": "653fd9af6a07fc9cfd7a5e57",
      "publishedPath": "/en-us/towel-day"
    }
  ],
  "pagination": {
    "limit": 20,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/list](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/list)*