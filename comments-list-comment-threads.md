# List Comment Threads

```
GET https://api.webflow.com/beta/sites/:site_id/comments
```

List all comment threads for a site.
**Required Scope:** `comments:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




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
| `comments` | list of objects | No | N/A |
| `comments.id` | string | No | Unique identifier for the comment thread |
| `comments.siteId` | string | No | The site unique identifier |
| `comments.pageId` | string | No | The page unique identifier |
| `comments.breakpoint` | string | No | The breakpoint the comment was left on |
| `comments.url` | string | No | The URL of the page the comment was left on |
| `comments.content` | string | No | The content of the comment reply |
| `comments.isResolved` | boolean | No | Boolean determining if the comment thread is resolved |
| `comments.author` | object | No | N/A |
| `comments.author.userId` | string | No | The unique identifier of the author |
| `comments.author.email` | string | No | Email of the author |
| `comments.author.name` | string | No | Name of the author |
| `comments.mentionedUsers` | list of objects | No | List of mentioned users. This is an empty array until email notifications are sent, which can take up to 5 minutes after the comment is created. |
| `comments.mentionedUsers.userId` | string | No | The unique identifier of the mentioned user |
| `comments.mentionedUsers.email` | string | No | Email of the user |
| `comments.mentionedUsers.name` | string | No | Name of the  User |
| `comments.createdOn` | string | No | The date the item was created |
| `comments.lastUpdated` | string | No | The date the item was last updated |
| `comments.localeId` | string | No | The locale unique identifier |
| `comments.itemId` | string | No | The item unique identifier |
| `pagination` | object | No | N/A |
| `pagination.limit` | double | No | The limit specified in the request (default 100) |
| `pagination.offset` | double | No | The offset specified for pagination |
| `pagination.total` | double | No | Total number of comment threads |




## Errors

* **400:** Comments List Comment Threads Request Bad Request Error
* **401:** Comments List Comment Threads Request Unauthorized Error
* **404:** Comments List Comment Threads Request Not Found Error
* **429:** Comments List Comment Threads Request Too Many Requests Error
* **500:** Comments List Comment Threads Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/comments \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
{
  "comments": [
    {
      "id": "679d2ddb5196117ad04d1ffa",
      "siteId": "679826b3b20b045e176bc4b5",
      "pageId": "679826b3b20b045e176bc4bc",
      "breakpoint": "main",
      "url": "https://webflow.com/design/site-slug-4ec832?workflow=comment&commentId=679d2ddb5196117ad04d1ff8&pageId=679826b3b20b045e176bc4bc",
      "content": "Let's go to the pub! [[6287ec36a841b25637c663df]] ",
      "isResolved": false,
      "author": {
        "userId": "6287ec36a841b25637c663df",
        "email": "ford.prefect@heartofgold.spaceship",
        "name": "Ford Prefect"
      },
      "mentionedUsers": [
        {
          "userId": "6287ec36a841b25637c663df",
          "email": "arthur.dent@heartofgold.spaceship",
          "name": "Arthur Dent"
        }
      ],
      "createdOn": "2025-01-31T20:08:59.759Z",
      "lastUpdated": "2025-01-31T20:08:59.759Z",
      "localeId": "67993753d910db250db64b3e",
      "itemId": "580e64008c9a982ac9b8b754"
    },
    {
      "id": "679d2ddb5196117ad04d1ffc",
      "siteId": "679826b3b20b045e176bc4b5",
      "pageId": "679826b3b20b045e176bc4bc",
      "breakpoint": "main",
      "url": "https://webflow.com/design/site-slug-4ec832?workflow=comment&commentId=679d2ddb5196117ad04d1ff8&pageId=679826b3b20b045e176bc4bc",
      "content": "You have five minutes left to drink it [[6287ec36a841b25637c663df]] ",
      "isResolved": false,
      "author": {
        "userId": "6287ec36a841b25637c663df",
        "email": "ford.prefect@heartofgold.spaceship",
        "name": "Ford Prefect"
      },
      "mentionedUsers": [
        {
          "userId": "6287ec36a841b25637c663df",
          "email": "arthur.dent@heartofgold.spaceship",
          "name": "Arthur Dent"
        }
      ],
      "createdOn": "2025-01-31T20:08:59.759Z",
      "lastUpdated": "2025-01-31T20:08:59.759Z",
      "localeId": "67993753d910db250db64b3e",
      "itemId": "580e64008c9a982ac9b8b754"
    }
  ],
  "pagination": {
    "limit": 2,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/comments/list-comment-threads](https://developers.webflow.com/v2.0.0-beta/reference/comments/list-comment-threads)*