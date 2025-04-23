# Delete Single Collection Item

```
DELETE https://api.webflow.com/beta/collections/:collection_id/items/:item_id
```

Delete an item from a collection.
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

* **400:** Items Delete Item Request Bad Request Error
* **401:** Items Delete Item Request Unauthorized Error
* **404:** Items Delete Item Request Not Found Error
* **429:** Items Delete Item Request Too Many Requests Error
* **500:** Items Delete Item Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/580e64008c9a982ac9b8b754 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/delete-item](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/delete-item)*