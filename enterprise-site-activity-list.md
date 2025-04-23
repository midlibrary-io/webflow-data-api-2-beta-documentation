# Get Site Activity Logs

```
GET https://api.webflow.com/beta/sites/:site_id/activity_logs
```

Retrieve Activity Logs for a specific Site.
**Required Scope:** `site_activity:read`


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

_A list of site activity logs_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `items` | list of objects | No | N/A |
| `items.id` | string | No | N/A |
| `items.createdOn` | datetime | No | N/A |
| `items.lastUpdated` | datetime | No | N/A |
| `items.event` | enum | No |  (Values: styles_modified, site_published, ix2_modified_on_page, page_dom_modified, cms_item, backup_created, page_custom_code_modified, symbols_modified, variable_modified, variables_modified, cms_collection, page_settings_modified, page_settings_custom_code_modified, ix2_modified_on_component, ix2_modified_on_class, site_custom_code_modified, page_duplicated, secondary_locale_page_content_modified, page_renamed, page_created, page_deleted, site_unpublished, backup_restored, locale_added, branch_created, locale_display_name_updated, locale_subdirectory_updated, branch_merged, locale_tag_updated, branch_deleted, locale_enabled, locale_removed, locale_disabled, library_shared, library_unshared, library_installed, library_uninstalled, library_update_shared, library_update_accepted, branch_review_created, branch_review_approved, branch_review_canceled) |
| `items.resourceOperation` | enum | No |  (Values: CREATED, MODIFIED, PUBLISHED, UNPUBLISHED, DELETED, GROUP_REORDERED, GROUP_CREATED, GROUP_DELETED, REORDERED) |
| `items.user` | object | No | N/A |
| `items.user.id` | string | No | N/A |
| `items.user.displayName` | string | No | N/A |
| `items.resourceId` | string | No | N/A |
| `items.resourceName` | string | No | N/A |
| `items.newValue` | string | No | N/A |
| `items.previousValue` | string | No | N/A |
| `items.payload` | map from strings to any | No | N/A |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **403:** Activity Logs List Request Forbidden Error
* **404:** Activity Logs List Request Not Found Error
* **429:** Activity Logs List Request Too Many Requests Error
* **500:** Activity Logs List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/activity_logs \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "items": [
    {
      "id": "654c16c7b229e56bcf26872d",
      "createdOn": "2023-11-08T23:16:23Z",
      "lastUpdated": "2023-11-08T23:16:23Z",
      "event": "cms_collection",
      "resourceOperation": "CREATED",
      "user": {
        "id": "6509cd56e90eec668b009712",
        "displayName": "John Doe"
      },
      "resourceId": "654c16c7b229e56bcf26870c",
      "resourceName": "foo-bar"
    }
  ],
  "pagination": {
    "limit": 25,
    "offset": 0,
    "total": 1
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-activity/list](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-activity/list)*