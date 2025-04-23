# List Products & SKUs

```
GET https://api.webflow.com/beta/sites/:site_id/products
```

Retrieve all products for a site.
Uselimitandoffsetto page through all products with subsequent requests. All SKUs for each product
will also be fetched and returned. Thelimit,offsetandtotalvalues represent Products only and do not include any SKUs.
**Required Scope:** `ecommerce:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `items` | list of objects | No | List of Item objects within the Collection. Contains product and skus keys for each Item |
| `items.product` | object | No | The Product object |
| `items.product.id` | string | No | Unique identifier for the Product |
| `items.product.cmsLocaleId` | string | No | Identifier for the locale of the CMS item |
| `items.product.lastPublished` | datetime | No | The date the Product was last published |
| `items.product.lastUpdated` | datetime | No | The date the Product was last updated |
| `items.product.createdOn` | datetime | No | The date the Product was created |
| `items.product.isArchived` | boolean | No | Boolean determining if the Product is set to archived |
| `items.product.isDraft` | boolean | No | Boolean determining if the Product is set to draft |
| `items.product.fieldData` | object | No | Contains content-specific details for a product, covering both standard (e.g., title, description)  and custom fields tailored to the product setup. |
| `items.product.fieldData.name` | string | No | Name of the Product |
| `items.product.fieldData.slug` | string | No | URL structure of the Product in your site. |
| `items.product.fieldData.description` | string | No | A description of your product |
| `items.product.fieldData.shippable` | boolean | No | Boolean determining if the Product is shippable |
| `items.product.fieldData.sku-properties` | list of objects | No | Variant types to include in SKUs |
| `items.product.fieldData.sku-properties.id` | string | No | Unique identifier for a collection of Product Variants |
| `items.product.fieldData.sku-properties.name` | string | No | Name of the collection of Product Variants |
| `items.product.fieldData.sku-properties.enum` | list of objects | No | The individual Product variants that are contained within the collection |
| `items.product.fieldData.sku-properties.enum.id` | string | No | Unique identifier for a Product variant/Option |
| `items.product.fieldData.sku-properties.enum.name` | string | No | Name of the Product variant/Option |
| `items.product.fieldData.sku-properties.enum.slug` | string | No | Slug for the Product variant/Option in the Site URL structure |
| `items.product.fieldData.categories` | list of strings | No | The categories your product belongs to. |
| `items.product.fieldData.tax-category` | enum | No | Product tax class (Values: standard-taxable, standard-exempt, books-religious, books-textbook, clothing, clothing-swimwear, digital-goods, digital-service, drugs-non-prescription, drugs-prescription, food-bottled-water, food-candy, food-groceries, food-prepared, food-soda, food-supplements, magazine-individual, magazine-subscription, service-admission, service-advertising, service-dry-cleaning, service-hairdressing, service-installation, service-miscellaneous, service-parking, service-printing, service-professional, service-repair, service-training) |
| `items.product.fieldData.default-sku` | string | No | The default SKU associated with this product. |
| `items.product.fieldData.ec-product-type` | enum | No | Product types.Enums reflect the following values in order: Physical, Digital, Service, Advanced” (Values: ff42fee0113744f693a764e3431a9cc2, f22027db68002190aef89a4a2b7ac8a1, c599e43b1a1c34d5a323aedf75d3adf6, b6ccc1830db4b1babeb06a9ac5f6dd76) |
| `items.skus` | list of objects | No | A list of SKU Objects |
| `items.skus.id` | string | No | Unique identifier for the Product |
| `items.skus.cmsLocaleId` | string | No | Identifier for the locale of the CMS item |
| `items.skus.lastPublished` | datetime | No | The date the Product was last published |
| `items.skus.lastUpdated` | datetime | No | The date the Product was last updated |
| `items.skus.createdOn` | datetime | No | The date the Product was created |
| `items.skus.fieldData` | object | No | Standard and Custom fields for a SKU |
| `items.skus.fieldData.name` | string | No | Name of the Product |
| `items.skus.fieldData.slug` | string | No | URL structure of the Product in your site. |
| `items.skus.fieldData.price` | object | No | price of SKU |
| `items.skus.fieldData.price.value` | double | No | Price of SKU |
| `items.skus.fieldData.price.unit` | string | No | Currency of Item |
| `items.skus.fieldData.price.currency` | string | No | Currency of Item (alternative representation) |
| `items.skus.fieldData.sku-values` | map from strings to strings | No | A mapping between SKU properties and their values, represented as key-value pairs. Each key represents a SKU Property ID (e.g. “color”) and maps to its corresponding SKU Value ID (e.g. “blue”). This structure defines the specific variant combination for a SKU. |
| `items.skus.fieldData.compare-at-price` | object | No | comparison price of SKU |
| `items.skus.fieldData.compare-at-price.value` | double | No | Price of SKU |
| `items.skus.fieldData.compare-at-price.unit` | string | No | Currency of Item |
| `items.skus.fieldData.ec-sku-billing-method` | enum | No | Billing methodfor the SKU (Values: one-time, subscription) |
| `items.skus.fieldData.ec-sku-subscription-plan` | object | No | Subscription planfor the SKU |
| `items.skus.fieldData.ec-sku-subscription-plan.interval` | enum | No | Interval of subscription renewal (Values: day, week, month, year) |
| `items.skus.fieldData.ec-sku-subscription-plan.frequency` | double | No | Frequncy of billing within interval |
| `items.skus.fieldData.ec-sku-subscription-plan.trial` | double | No | Number of days of a trial |
| `items.skus.fieldData.ec-sku-subscription-plan.plans` | list of objects | No | N/A |
| `items.skus.fieldData.ec-sku-subscription-plan.plans.platform` | "stripe" | No | The platform of the subscription plan |
| `items.skus.fieldData.ec-sku-subscription-plan.plans.id` | string | No | The unique identifier of the plan |
| `items.skus.fieldData.ec-sku-subscription-plan.plans.status` | enum | No | The status of the plan (Values: active, inactive, canceled) |
| `items.skus.fieldData.track-inventory` | boolean | No | A boolean indicating whether inventory for this product should be tracked. |
| `items.skus.fieldData.quantity` | double | No | Quantity of SKU that will be tracked as items are ordered. |
| `items.skus.fieldData.main-image` | string | No | The URL for the main image of the SKU |
| `items.skus.fieldData.sku` | string | No | A unique identifier for the SKU |
| `items.skus.fieldData.sku-properties` | list of objects | No | The properties of the SKU |
| `items.skus.fieldData.sku-properties.id` | string | No | Unique identifier for a collection of Product Variants |
| `items.skus.fieldData.sku-properties.name` | string | No | Name of the collection of Product Variants |
| `items.skus.fieldData.sku-properties.enum` | list of objects | No | The individual Product variants that are contained within the collection |
| `items.skus.fieldData.sku-properties.enum.id` | string | No | Unique identifier for a Product variant/Option |
| `items.skus.fieldData.sku-properties.enum.name` | string | No | Name of the Product variant/Option |
| `items.skus.fieldData.sku-properties.enum.slug` | string | No | Slug for the Product variant/Option in the Site URL structure |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Products List Request Bad Request Error
* **401:** Products List Request Unauthorized Error
* **403:** Products List Request Forbidden Error
* **404:** Products List Request Not Found Error
* **409:** Products List Request Conflict Error
* **429:** Products List Request Too Many Requests Error
* **500:** Products List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/products \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "items": [
    {
      "product": {
        "id": "660eb7a486d1d6e0412292d7",
        "cmsLocaleId": "653ad57de882f528b32e810e",
        "lastPublished": "2024-04-04T14:24:19Z",
        "lastUpdated": "2024-04-04T14:30:19Z",
        "createdOn": "2024-04-04T14:22:28Z",
        "isArchived": false,
        "isDraft": false,
        "fieldData": {
          "name": "T-Shirt",
          "slug": "t-shirt",
          "description": "A plain t-shirt",
          "shippable": true,
          "sku-properties": [
            {
              "id": "31b77fa66fa376c2c0abb458d5be39fb",
              "name": "Size",
              "enum": [
                {
                  "id": "8d21a625d655ab260e9941c27180c75b",
                  "name": "Small",
                  "slug": "small"
                },
                {
                  "id": "ecdca17106ad86c0dfe3b5f3ac8be6c9",
                  "name": "Medium",
                  "slug": "medium"
                },
                {
                  "id": "ec7877d6137ecf7ec86f726c135b1812",
                  "name": "Large",
                  "slug": "large"
                }
              ]
            },
            {
              "id": "74d3738e62c568d5634dd6989daec5ec",
              "name": "Color",
              "enum": [
                {
                  "id": "e539b0d6c3a609cd06ddb2da804f68f0",
                  "name": "Royal Blue",
                  "slug": "royal-blue"
                },
                {
                  "id": "68d98f2fbafc0fd45651cddc44798dd0",
                  "name": "Crimson Red",
                  "slug": "crimson-red"
                },
                {
                  "id": "996cd95c97fd5620d0a374c835b37205",
                  "name": "Forrest Green",
                  "slug": "forrest-green"
                }
              ]
            }
          ],
          "tax-category": "standard-taxable",
          "default-sku": "66072fb71b89448912e2681c",
          "ec-product-type": "b6ccc1830db4b1babeb06a9ac5f6dd76"
        }
      },
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
  ],
  "pagination": {
    "limit": 100,
    "offset": 0,
    "total": 100
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/products-sk-us/list](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/products-sk-us/list)*