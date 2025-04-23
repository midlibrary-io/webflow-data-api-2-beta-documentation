# Get Comment Thread

```
GET https://api.webflow.com/beta/sites/:site_id/comments/:comment_thread_id
```

Get details of a specific comment thread.
**Required Scope:** `comments:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `comment_thread_id` | string | Yes | Unique identifier for a Comment Thread |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `localeId` | string | No | Unique identifier for a specific locale. Applicable, when using localization. |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `sortBy` | enum | No | Sort results by the provided value. Only allowed when sortOrder is provided. (Values: createdOn, lastUpdated) |
| `sortOrder` | enum | No | Sorts the results by asc or desc (Values: asc, desc) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the comment thread |
| `siteId` | string | No | The site unique identifier |
| `pageId` | string | No | The page unique identifier |
| `breakpoint` | string | No | The breakpoint the comment was left on |
| `url` | string | No | The URL of the page the comment was left on |
| `content` | string | No | The content of the comment reply |
| `isResolved` | boolean | No | Boolean determining if the comment thread is resolved |
| `author` | object | No | N/A |
| `author.userId` | string | No | The unique identifier of the author |
| `author.email` | string | No | Email of the author |
| `author.name` | string | No | Name of the author |
| `mentionedUsers` | list of objects | No | List of mentioned users. This is an empty array until email notifications are sent, which can take up to 5 minutes after the comment is created. |
| `mentionedUsers.userId` | string | No | The unique identifier of the mentioned user |
| `mentionedUsers.email` | string | No | Email of the user |
| `mentionedUsers.name` | string | No | Name of the  User |
| `createdOn` | string | No | The date the item was created |
| `lastUpdated` | string | No | The date the item was last updated |
| `localeId` | string | No | The locale unique identifier |
| `itemId` | string | No | The item unique identifier |




## Errors

* **400:** Comments Get Comment Thread Request Bad Request Error
* **401:** Comments Get Comment Thread Request Unauthorized Error
* **404:** Comments Get Comment Thread Request Not Found Error
* **429:** Comments Get Comment Thread Request Too Many Requests Error
* **500:** Comments Get Comment Thread Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/comments/580e63e98c9a982ac9b8b741 \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
{
  "id": "580e64008c9a982ac9b8b754",
  "siteId": "580e64008c9a982ac9b8b754",
  "pageId": "580e64008c9a982ac9b8b754",
  "breakpoint": "main",
  "url": "https://webflow.com/design/site-slug-4ec832?workflow=comment&commentId=679d2ddb5196117ad04d1ff8&pageId=679826b3b20b045e176bc4bc",
  "content": "This is a comment reply",
  "isResolved": true,
  "author": {
    "userId": "userId",
    "email": "email",
    "name": "name"
  },
  "mentionedUsers": [
    {
      "userId": "6287ec36a841b25637c663df",
      "email": "arthur.dent@heartofgold.spaceship",
      "name": "Arthur Dent"
    }
  ],
  "createdOn": "2023-03-17T18:47:35.560Z",
  "lastUpdated": "2023-03-17T18:47:35.560Z",
  "localeId": "580e64008c9a982ac9b8b754",
  "itemId": "580e64008c9a982ac9b8b754"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/comments/get-comment-thread](https://developers.webflow.com/v2.0.0-beta/reference/comments/get-comment-thread)*