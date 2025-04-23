# Update Product

```
PATCH https://api.webflow.com/beta/sites/:site_id/products/:product_id
```

Update an existing Product.
Updating an existing Product will set the product type toAdvanced, which ensures all Product and SKU fields will be shown to users in the Designer.
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
| `id` | string | No | Unique identifier for the Product |
| `cmsLocaleId` | string | No | Identifier for the locale of the CMS item |
| `lastPublished` | datetime | No | The date the Product was last published |
| `lastUpdated` | datetime | No | The date the Product was last updated |
| `createdOn` | datetime | No | The date the Product was created |
| `isArchived` | boolean | No | Boolean determining if the Product is set to archived |
| `isDraft` | boolean | No | Boolean determining if the Product is set to draft |
| `fieldData` | object | No | Contains content-specific details for a product, covering both standard (e.g., title, description)  and custom fields tailored to the product setup. |
| `fieldData.name` | string | No | Name of the Product |
| `fieldData.slug` | string | No | URL structure of the Product in your site. |
| `fieldData.description` | string | No | A description of your product |
| `fieldData.shippable` | boolean | No | Boolean determining if the Product is shippable |
| `fieldData.sku-properties` | list of objects | No | Variant types to include in SKUs |
| `fieldData.sku-properties.id` | string | No | Unique identifier for a collection of Product Variants |
| `fieldData.sku-properties.name` | string | No | Name of the collection of Product Variants |
| `fieldData.sku-properties.enum` | list of objects | No | The individual Product variants that are contained within the collection |
| `fieldData.sku-properties.enum.id` | string | No | Unique identifier for a Product variant/Option |
| `fieldData.sku-properties.enum.name` | string | No | Name of the Product variant/Option |
| `fieldData.sku-properties.enum.slug` | string | No | Slug for the Product variant/Option in the Site URL structure |
| `fieldData.categories` | list of strings | No | The categories your product belongs to. |
| `fieldData.tax-category` | enum | No | Product tax class (Values: standard-taxable, standard-exempt, books-religious, books-textbook, clothing, clothing-swimwear, digital-goods, digital-service, drugs-non-prescription, drugs-prescription, food-bottled-water, food-candy, food-groceries, food-prepared, food-soda, food-supplements, magazine-individual, magazine-subscription, service-admission, service-advertising, service-dry-cleaning, service-hairdressing, service-installation, service-miscellaneous, service-parking, service-printing, service-professional, service-repair, service-training) |
| `fieldData.default-sku` | string | No | The default SKU associated with this product. |
| `fieldData.ec-product-type` | enum | No | Product types.Enums reflect the following values in order: Physical, Digital, Service, Advanced” (Values: ff42fee0113744f693a764e3431a9cc2, f22027db68002190aef89a4a2b7ac8a1, c599e43b1a1c34d5a323aedf75d3adf6, b6ccc1830db4b1babeb06a9ac5f6dd76) |




## Errors

* **400:** Products Update Request Bad Request Error
* **401:** Products Update Request Unauthorized Error
* **403:** Products Update Request Forbidden Error
* **404:** Products Update Request Not Found Error
* **409:** Products Update Request Conflict Error
* **429:** Products Update Request Too Many Requests Error
* **500:** Products Update Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/products/580e63fc8c9a982ac9b8b745 \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

### Example Response (200 Updated)

```json
{
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
    "categories": [
      "categories"
    ],
    "tax-category": "standard-taxable",
    "default-sku": "66072fb71b89448912e2681c",
    "ec-product-type": "b6ccc1830db4b1babeb06a9ac5f6dd76"
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/products-sk-us/update](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/products-sk-us/update)*