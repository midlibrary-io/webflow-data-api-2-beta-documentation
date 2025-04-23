# Create SKUs

```
POST https://api.webflow.com/beta/sites/:site_id/products/:product_id/skus
```

Create additional SKUs to manage everyoption and variant of your Product.
Creating SKUs through the API will set the product type toAdvanced, which ensures all Product and SKU fields will be shown to users in the Designer.
**Required Scope:** `ecommerce:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `product_id` | string | Yes | Unique identifier for a Product |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `skus` | list of objects | No | N/A |
| `skus.id` | string | No | Unique identifier for the Product |
| `skus.cmsLocaleId` | string | No | Identifier for the locale of the CMS item |
| `skus.lastPublished` | datetime | No | The date the Product was last published |
| `skus.lastUpdated` | datetime | No | The date the Product was last updated |
| `skus.createdOn` | datetime | No | The date the Product was created |
| `skus.fieldData` | object | No | Standard and Custom fields for a SKU |
| `skus.fieldData.name` | string | No | Name of the Product |
| `skus.fieldData.slug` | string | No | URL structure of the Product in your site. |
| `skus.fieldData.price` | object | No | price of SKU |
| `skus.fieldData.price.value` | double | No | Price of SKU |
| `skus.fieldData.price.unit` | string | No | Currency of Item |
| `skus.fieldData.price.currency` | string | No | Currency of Item (alternative representation) |
| `skus.fieldData.sku-values` | map from strings to strings | No | A mapping between SKU properties and their values, represented as key-value pairs. Each key represents a SKU Property ID (e.g. “color”) and maps to its corresponding SKU Value ID (e.g. “blue”). This structure defines the specific variant combination for a SKU. |
| `skus.fieldData.compare-at-price` | object | No | comparison price of SKU |
| `skus.fieldData.compare-at-price.value` | double | No | Price of SKU |
| `skus.fieldData.compare-at-price.unit` | string | No | Currency of Item |
| `skus.fieldData.ec-sku-billing-method` | enum | No | Billing methodfor the SKU (Values: one-time, subscription) |
| `skus.fieldData.ec-sku-subscription-plan` | object | No | Subscription planfor the SKU |
| `skus.fieldData.ec-sku-subscription-plan.interval` | enum | No | Interval of subscription renewal (Values: day, week, month, year) |
| `skus.fieldData.ec-sku-subscription-plan.frequency` | double | No | Frequncy of billing within interval |
| `skus.fieldData.ec-sku-subscription-plan.trial` | double | No | Number of days of a trial |
| `skus.fieldData.ec-sku-subscription-plan.plans` | list of objects | No | N/A |
| `skus.fieldData.ec-sku-subscription-plan.plans.platform` | "stripe" | No | The platform of the subscription plan |
| `skus.fieldData.ec-sku-subscription-plan.plans.id` | string | No | The unique identifier of the plan |
| `skus.fieldData.ec-sku-subscription-plan.plans.status` | enum | No | The status of the plan (Values: active, inactive, canceled) |
| `skus.fieldData.track-inventory` | boolean | No | A boolean indicating whether inventory for this product should be tracked. |
| `skus.fieldData.quantity` | double | No | Quantity of SKU that will be tracked as items are ordered. |
| `skus.fieldData.main-image` | string | No | The URL for the main image of the SKU |
| `skus.fieldData.sku` | string | No | A unique identifier for the SKU |
| `skus.fieldData.sku-properties` | list of objects | No | The properties of the SKU |
| `skus.fieldData.sku-properties.id` | string | No | Unique identifier for a collection of Product Variants |
| `skus.fieldData.sku-properties.name` | string | No | Name of the collection of Product Variants |
| `skus.fieldData.sku-properties.enum` | list of objects | No | The individual Product variants that are contained within the collection |
| `skus.fieldData.sku-properties.enum.id` | string | No | Unique identifier for a Product variant/Option |
| `skus.fieldData.sku-properties.enum.name` | string | No | Name of the Product variant/Option |
| `skus.fieldData.sku-properties.enum.slug` | string | No | Slug for the Product variant/Option in the Site URL structure |




## Errors

* **400:** Products Create SKU Request Bad Request Error
* **401:** Products Create SKU Request Unauthorized Error
* **403:** Products Create SKU Request Forbidden Error
* **404:** Products Create SKU Request Not Found Error
* **409:** Products Create SKU Request Conflict Error
* **429:** Products Create SKU Request Too Many Requests Error
* **500:** Products Create SKU Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/products/580e63fc8c9a982ac9b8b745/skus \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "skus": [
    {
      "fieldData": {
        "name": "Colorful T-shirt - Default",
        "slug": "colorful-t-shirt-default",
        "price": {
          "value": 2499,
          "unit": "USD",
          "currency": "USD"
        }
      }
    }
  ]
}'
```

### Example Response (200 Successful)

```json
{
  "skus": [
    {
      "id": "580e63fc8c9a982ac9b8b745",
      "cmsLocaleId": "653ad57de882f528b32e810e",
      "lastPublished": "2023-03-17T18:47:35Z",
      "lastUpdated": "2023-03-17T18:47:35Z",
      "createdOn": "2023-03-17T18:47:35Z",
      "fieldData": {
        "name": "Colorful T-shirt - Default",
        "slug": "colorful-t-shirt-default",
        "price": {
          "value": 2499,
          "unit": "USD",
          "currency": "USD"
        },
        "sku-values": {
          "color": "blue",
          "size": "small"
        },
        "quantity": 10,
        "main-image": "https://www.example.com/image.jpg",
        "sku": "1234567890",
        "sku-properties": [
          {
            "id": "Color",
            "name": "Color",
            "enum": [
              {
                "id": "id",
                "name": "Royal Blue",
                "slug": "royal-blue"
              }
            ]
          }
        ]
      }
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/products-sk-us/create-sku](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/products-sk-us/create-sku)*