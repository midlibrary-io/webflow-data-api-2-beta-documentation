# Delete Single Live Collection Item

```
DELETE https://api.webflow.com/beta/collections/:collection_id/items/:item_id/live
```

Remove a live item from the site. Removing a published item will unpublish the item from the live site and set it to draft.
This endpoint does not currently support bulk deletion.
**Required Scope:** `CMS:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |
| `item_id` | string | Yes | Unique identifier for an Item |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `cmsLocaleId` | string | No | Unique identifier for a CMS Locale. This UID is different from the Site locale identifier and is listed ascmsLocaleIdin the Sites response. To query multiple locales, input a comma separated string. |




## Errors

* **400:** Items Delete Item Live Request Bad Request Error
* **401:** Items Delete Item Live Request Unauthorized Error
* **404:** Items Delete Item Live Request Not Found Error
* **429:** Items Delete Item Live Request Too Many Requests Error
* **500:** Items Delete Item Live Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/580e64008c9a982ac9b8b754/live \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/delete-item-live](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/delete-item-live)*