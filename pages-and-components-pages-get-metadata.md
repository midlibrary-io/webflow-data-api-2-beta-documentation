# Get Page Metadata

```
GET https://api.webflow.com/beta/pages/:page_id
```

Get metadata information for a single page.
**Required Scope:** `pages:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `page_id` | string | Yes | Unique identifier for a Page |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `localeId` | string | No | Unique identifier for a specific locale. Applicable, when using localization. |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the Page |
| `siteId` | string | No | Unique identifier for the Site |
| `title` | string | No | Title of the Page |
| `slug` | string | No | slug of the Page (derived from title) |
| `parentId` | string | No | Identifier of the parent folder |
| `collectionId` | string | No | Unique identifier for a linked Collection, value will be null if the Page is not part of a Collection. |
| `createdOn` | datetime | No | The date the Page was created |
| `lastUpdated` | datetime | No | The date the Page was most recently updated |
| `archived` | boolean | No | Whether the Page has been archived |
| `draft` | boolean | No | Whether the Page is a draft |
| `canBranch` | boolean | No | Indicates whether the Page supportsPage Branching |
| `isBranch` | boolean | No | Indicates whether the Page is a Branch of another PagePage Branching |
| `isMembersOnly` | boolean | No | Indicates whether the Page is restricted byMemberships Controls |
| `seo` | object | No | SEO-related fields for the Page |
| `seo.title` | string | No | The Page title shown in search engine results |
| `seo.description` | string | No | The Page description shown in search engine results |
| `openGraph` | object | No | Open Graph fields for the Page |
| `openGraph.title` | string | No | The title supplied to Open Graph annotations |
| `openGraph.titleCopied` | boolean | No | Indicates the Open Graph title was copied from the SEO title |
| `openGraph.description` | string | No | The description supplied to Open Graph annotations |
| `openGraph.descriptionCopied` | boolean | No | Indicates the Open Graph description was copied from the SEO description |
| `localeId` | string | No | Unique ID of the page locale |
| `publishedPath` | string | No | Relative path of the published page URL |




## Errors

* **400:** Pages Get Metadata Request Bad Request Error
* **401:** Pages Get Metadata Request Unauthorized Error
* **404:** Pages Get Metadata Request Not Found Error
* **429:** Pages Get Metadata Request Too Many Requests Error
* **500:** Pages Get Metadata Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/pages/63c720f9347c2139b248e552 \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
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
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/get-metadata](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/get-metadata)*