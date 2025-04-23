# List Orders

```
GET https://api.webflow.com/beta/sites/:site_id/orders
```

List all orders created for a given site.
**Required Scope:** `ecommerce:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `status` | enum | No | Filter the orders by status (Values: pending, refunded, dispute-lost, fulfilled, disputed, unfulfilled) |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `orders` | list of objects | No | List of orders |
| `orders.orderId` | string | No | The order ID. Will usually be 6 hex characters, but can also be 9 hex characters if the site has a very large number of Orders. Randomly assigned. |
| `orders.status` | enum | No | The status of the Order (Values: pending, unfulfilled, fulfilled, disputed, dispute-lost, refunded) |
| `orders.comment` | string | No | A comment string for this Order, which is editable by API user (not used by Webflow). |
| `orders.orderComment` | string | No | A comment that the customer left when making their Order |
| `orders.acceptedOn` | datetime | No | The ISO8601 timestamp that an Order was placed. |
| `orders.fulfilledOn` | datetime | No | When an Order is marked as ‘fulfilled’, this field represents the timestamp of the fulfillment in ISO8601 format. Otherwise, it is null. |
| `orders.refundedOn` | datetime | No | When an Order is marked as ‘refunded’, this field represents the timestamp of the fulfillment in ISO8601 format. Otherwise, it is null. |
| `orders.disputedOn` | datetime | No | When an Order is marked as ‘disputed’, this field represents the timestamp of the fulfillment in ISO8601 format. Otherwise, it is null. |
| `orders.disputeUpdatedOn` | datetime | No | If an Order has been disputed by the customer, this key will be set to the ISO8601 timestamp of the last update received. If the Order is not disputed, the key will be null. |
| `orders.disputeLastStatus` | enum | No | If an order was disputed by the customer, then this key will be set with thedispute’s status. (Values: warning_needs_response, warning_under_review, warning_closed, needs_response, under_review, charge_refunded, won, lost) |
| `orders.customerPaid` | object | No | The total paid by the customer |
| `orders.customerPaid.unit` | string | No | The three-letter ISO currency code |
| `orders.customerPaid.value` | string | No | The numeric value in the base unit of the currency |
| `orders.customerPaid.string` | string | No | The user-facing string representation of the amount |
| `orders.netAmount` | object | No | The net amount after application fees |
| `orders.netAmount.unit` | string | No | The three-letter ISO currency code |
| `orders.netAmount.value` | string | No | The numeric value in the base unit of the currency |
| `orders.netAmount.string` | string | No | The user-facing string representation of the amount |
| `orders.applicationFee` | object | No | The application fee assessed by the platform |
| `orders.applicationFee.unit` | string | No | The three-letter ISO currency code |
| `orders.applicationFee.value` | string | No | The numeric value in the base unit of the currency |
| `orders.applicationFee.string` | string | No | The user-facing string representation of the amount |
| `orders.allAddresses` | list of objects | No | All addresses provided by the customer during the ordering flow. |
| `orders.allAddresses.type` | enum | No | The type of the order address (billing or shipping) (Values: shipping, billing) |
| `orders.allAddresses.japanType` | enum | No | Represents a Japan-only address format. This field will only appear on orders placed from Japan. (Values: kana, kanji) |
| `orders.allAddresses.addressee` | string | No | Display name on the address |
| `orders.allAddresses.line1` | string | No | The first line of the address |
| `orders.allAddresses.line2` | string | No | The second line of the address |
| `orders.allAddresses.city` | string | No | The city of the address. |
| `orders.allAddresses.state` | string | No | The state or province of the address |
| `orders.allAddresses.country` | string | No | The country of the address |
| `orders.allAddresses.postalCode` | string | No | The postal code of the address |
| `orders.shippingAddress` | object | No | The shipping address |
| `orders.shippingAddress.type` | enum | No | The type of the order address (billing or shipping) (Values: shipping, billing) |
| `orders.shippingAddress.japanType` | enum | No | Represents a Japan-only address format. This field will only appear on orders placed from Japan. (Values: kana, kanji) |
| `orders.shippingAddress.addressee` | string | No | Display name on the address |
| `orders.shippingAddress.line1` | string | No | The first line of the address |
| `orders.shippingAddress.line2` | string | No | The second line of the address |
| `orders.shippingAddress.city` | string | No | The city of the address. |
| `orders.shippingAddress.state` | string | No | The state or province of the address |
| `orders.shippingAddress.country` | string | No | The country of the address |
| `orders.shippingAddress.postalCode` | string | No | The postal code of the address |
| `orders.billingAddress` | object | No | The billing address |
| `orders.billingAddress.type` | enum | No | The type of the order address (billing or shipping) (Values: shipping, billing) |
| `orders.billingAddress.japanType` | enum | No | Represents a Japan-only address format. This field will only appear on orders placed from Japan. (Values: kana, kanji) |
| `orders.billingAddress.addressee` | string | No | Display name on the address |
| `orders.billingAddress.line1` | string | No | The first line of the address |
| `orders.billingAddress.line2` | string | No | The second line of the address |
| `orders.billingAddress.city` | string | No | The city of the address. |
| `orders.billingAddress.state` | string | No | The state or province of the address |
| `orders.billingAddress.country` | string | No | The country of the address |
| `orders.billingAddress.postalCode` | string | No | The postal code of the address |
| `orders.shippingProvider` | string | No | A string editable by the API user to note the shipping provider used (not used by Webflow). |
| `orders.shippingTracking` | string | No | A string editable by the API user to note the shipping tracking number for the order (not used by Webflow). |
| `orders.shippingTrackingURL` | string | No | N/A |
| `orders.customerInfo` | object | No | An object with the keysfullNameandemail. |
| `orders.customerInfo.fullName` | string | No | The full name of the Customer |
| `orders.customerInfo.email` | string | No | The Customer’s email address |
| `orders.purchasedItems` | list of objects | No | An array of all things that the Customer purchased. |
| `orders.purchasedItems.count` | double | No | Number of Item purchased. |
| `orders.purchasedItems.rowTotal` | object | No | The total for the row |
| `orders.purchasedItems.rowTotal.unit` | string | No | The three-letter ISO currency code |
| `orders.purchasedItems.rowTotal.value` | string | No | The numeric value in the base unit of the currency |
| `orders.purchasedItems.rowTotal.string` | string | No | The user-facing string representation of the amount |
| `orders.purchasedItems.productId` | string | No | The unique identifier for the Product |
| `orders.purchasedItems.productName` | string | No | User-facing name of the Product |
| `orders.purchasedItems.productSlug` | string | No | Slug for the Product |
| `orders.purchasedItems.variantId` | string | No | Identifier for the Product Variant (SKU) |
| `orders.purchasedItems.variantName` | string | No | User-facing name of the Product Variant (SKU) |
| `orders.purchasedItems.variantSlug` | string | No | Slug for the Product Variant (SKU) |
| `orders.purchasedItems.variantSKU` | string | No | The user-defined custom SKU of the Product Variant (SKU) |
| `orders.purchasedItems.variantImage` | object | No | N/A |
| `orders.purchasedItems.variantImage.url` | string | No | The hosted location for the Variant’s image |
| `orders.purchasedItems.variantImage.file` | object | No | N/A |
| `orders.purchasedItems.variantImage.file.size` | double | No | The image size in bytes |
| `orders.purchasedItems.variantImage.file.originalFileName` | string | No | the original name of the image |
| `orders.purchasedItems.variantImage.file.createdOn` | datetime | No | The creation timestamp of the image |
| `orders.purchasedItems.variantImage.file.contentType` | string | No | The MIME type of the image |
| `orders.purchasedItems.variantImage.file.width` | integer | No | The image width in pixels |
| `orders.purchasedItems.variantImage.file.height` | integer | No | The image height in pixels |
| `orders.purchasedItems.variantImage.file.variants` | list of objects | No | Variants of the supplied image |
| `orders.purchasedItems.variantImage.file.variants.url` | string | No | The hosted location for the Variant’s image |
| `orders.purchasedItems.variantImage.file.variants.originalFileName` | string | No | N/A |
| `orders.purchasedItems.variantImage.file.variants.size` | double | No | The image size in bytes |
| `orders.purchasedItems.variantImage.file.variants.width` | integer | No | The image width in pixels |
| `orders.purchasedItems.variantImage.file.variants.height` | integer | No | The image height in pixels |
| `orders.purchasedItems.variantPrice` | object | No | The price corresponding to the variant |
| `orders.purchasedItems.variantPrice.unit` | string | No | The three-letter ISO currency code |
| `orders.purchasedItems.variantPrice.value` | string | No | The numeric value in the base unit of the currency |
| `orders.purchasedItems.variantPrice.string` | string | No | The user-facing string representation of the amount |
| `orders.purchasedItems.weight` | double | No | The physical weight of the variant if provided, or null |
| `orders.purchasedItems.width` | double | No | The physical width of the variant if provided, or null |
| `orders.purchasedItems.height` | double | No | The physical height of the variant if provided, or null |
| `orders.purchasedItems.length` | double | No | The physical length of the variant if provided, or null |
| `orders.purchasedItemsCount` | double | No | The sum of all ‘count’ fields in ‘purchasedItems’. |
| `orders.stripeDetails` | object | No | An object with various Stripe IDs, useful for linking into the stripe dashboard. |
| `orders.stripeDetails.subscriptionId` | string | No | Stripe-generated identifier for the Subscription |
| `orders.stripeDetails.paymentMethod` | string | No | Stripe-generated identifier for the PaymentMethod used |
| `orders.stripeDetails.paymentIntentId` | string | No | Stripe-generated identifier for the PaymentIntent, or null |
| `orders.stripeDetails.customerId` | string | No | Stripe-generated customer identifier, or null |
| `orders.stripeDetails.chargeId` | string | No | Stripe-generated charge identifier, or null |
| `orders.stripeDetails.disputeId` | string | No | Stripe-generated dispute identifier, or null |
| `orders.stripeDetails.refundId` | string | No | Stripe-generated refund identifier, or null |
| `orders.stripeDetails.refundReason` | string | No | Stripe-generated refund reason, or null |
| `orders.stripeCard` | object | No | Details on the card used to fulfill this order, if this order was finalized with Stripe. |
| `orders.stripeCard.last4` | string | No | The last 4 digits on the card as a string |
| `orders.stripeCard.brand` | enum | No | The card’s brand (ie. credit card network) (Values: Visa, American Express, MasterCard, Discover, JCB, Diners Club, Unknown) |
| `orders.stripeCard.ownerName` | string | No | The name on the card. |
| `orders.stripeCard.expires` | object | No | The card’s expiration date. |
| `orders.stripeCard.expires.year` | double | No | Year that the card expires |
| `orders.stripeCard.expires.month` | double | No | Month that the card expires |
| `orders.paypalDetails` | object | No | N/A |
| `orders.paypalDetails.orderId` | string | No | PayPal order identifier |
| `orders.paypalDetails.payerId` | string | No | PayPal payer identifier |
| `orders.paypalDetails.captureId` | string | No | PayPal capture identifier |
| `orders.paypalDetails.refundId` | string | No | PayPal refund identifier |
| `orders.paypalDetails.refundReason` | string | No | PayPal-issued reason for the refund |
| `orders.paypalDetails.disputeId` | string | No | PayPal dispute identifier |
| `orders.customData` | list of maps from strings to any | No | An array of additional inputs for custom order data gathering. Each object in the array represents an input with a name, and a textInput, textArea, or checkbox value. |
| `orders.metadata` | object | No | N/A |
| `orders.metadata.isBuyNow` | boolean | No | N/A |
| `orders.isCustomerDeleted` | boolean | No | A boolean indicating whether the customer has been deleted from the site. |
| `orders.isShippingRequired` | boolean | No | A boolean indicating whether the order contains one or more purchased items that require shipping. |
| `orders.hasDownloads` | boolean | No | A boolean indicating whether the order contains one or more purchased items that are downloadable. |
| `orders.paymentProcessor` | string | No | A string indicating the payment processor used for this order. |
| `orders.totals` | object | No | An object describing various pricing totals |
| `orders.totals.subtotal` | object | No | The subtotal price |
| `orders.totals.subtotal.unit` | string | No | The three-letter ISO currency code |
| `orders.totals.subtotal.value` | string | No | The numeric value in the base unit of the currency |
| `orders.totals.subtotal.string` | string | No | The user-facing string representation of the amount |
| `orders.totals.extras` | list of objects | No | An array of extra items, includes discounts, shipping, and taxes. |
| `orders.totals.extras.type` | enum | No | The type of extra item this is. (Values: discount, discount-shipping, shipping, tax) |
| `orders.totals.extras.name` | string | No | A human-readable (but English) name for this extra charge. |
| `orders.totals.extras.description` | string | No | A human-readable (but English) description of this extra charge. |
| `orders.totals.extras.price` | object | No | The price for the item |
| `orders.totals.extras.price.unit` | string | No | The three-letter ISO currency code |
| `orders.totals.extras.price.value` | string | No | The numeric value in the base unit of the currency |
| `orders.totals.extras.price.string` | string | No | The user-facing string representation of the amount |
| `orders.totals.total` | object | No | The total price |
| `orders.totals.total.unit` | string | No | The three-letter ISO currency code |
| `orders.totals.total.value` | string | No | The numeric value in the base unit of the currency |
| `orders.totals.total.string` | string | No | The user-facing string representation of the amount |
| `orders.downloadFiles` | list of objects | No | An array of downloadable file objects. |
| `orders.downloadFiles.id` | string | No | The unique identifier for the downloadable file |
| `orders.downloadFiles.name` | string | No | The user-facing name for the downloadable file |
| `orders.downloadFiles.url` | string | No | The hosted location for the downloadable file |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Orders List Request Bad Request Error
* **401:** Orders List Request Unauthorized Error
* **403:** Orders List Request Forbidden Error
* **404:** Orders List Request Not Found Error
* **409:** Orders List Request Conflict Error
* **429:** Orders List Request Too Many Requests Error
* **500:** Orders List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/orders \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "orders": [
    {
      "orderId": "7c1-9fd",
      "status": "unfulfilled",
      "comment": "Customer requested gift wrapping and a personalized note saying: Happy Birthday, Ford! 🎉 Please ensure the item is packed with extra bubble wrap for safe transit.",
      "orderComment": "Please gift wrap with a personal note saying \"Happy Birthday, Ford! 🎉",
      "acceptedOn": "2024-04-10T13:16:21Z",
      "customerPaid": {
        "unit": "USD",
        "value": "5892",
        "string": " 211.55 USD"
      },
      "netAmount": {
        "unit": "USD",
        "value": "5892",
        "string": " 200.89 USD"
      },
      "applicationFee": {
        "unit": "USD",
        "value": "5892",
        "string": " 4.23 USD"
      },
      "allAddresses": [
        {
          "type": "billing",
          "addressee": "Arthur Dent",
          "line1": "20 W 34th St",
          "line2": "Empire State Building",
          "city": "New York",
          "state": "New York",
          "country": "US",
          "postalCode": "10118"
        },
        {
          "type": "shipping",
          "addressee": "Arthur Dent",
          "line1": "20 W 34th St",
          "line2": "Empire State Building",
          "city": "New York",
          "state": "New York",
          "country": "US",
          "postalCode": "10118"
        }
      ],
      "shippingAddress": {
        "type": "shipping",
        "japanType": "kanji",
        "addressee": "Arthur Dent",
        "line1": "20 W 34th St",
        "line2": "Empire State Building",
        "city": "New York",
        "state": "New York",
        "country": "US",
        "postalCode": "10118"
      },
      "billingAddress": {
        "type": "billing",
        "addressee": "Arthur Dent",
        "line1": "20 W 34th St",
        "line2": "Empire State Building",
        "city": "New York",
        "state": "New York",
        "country": "US",
        "postalCode": "10118"
      },
      "shippingProvider": "Shipping Company, Co.",
      "shippingTracking": "tr00000000002",
      "shippingTrackingURL": "https://www.shippingcompany.com/tracking/tr00000000002",
      "customerInfo": {
        "fullName": "Arthur Dent",
        "email": "arthur.dent@example.com"
      },
      "purchasedItems": [
        {
          "count": 2,
          "rowTotal": {
            "unit": "USD",
            "value": "5892",
            "string": " 111.22 USD"
          },
          "productId": "66072fb61b89448912e26791",
          "productName": "Luxurious Fresh Ball",
          "productSlug": "luxurious-fresh-ball",
          "variantId": "66072fb71b89448912e2683f",
          "variantName": "Luxurious Fresh Ball Generic: Bronze, Practical: Plastic",
          "variantSlug": "luxurious-fresh-ball-generic-bronze-practical-plastic",
          "variantSKU": "luxurious-fresh-ball-generic-bronze-practical-plastic",
          "variantImage": {
            "url": "https://d1otoma47x30pg.cloudfront.net/66072f39417a2a35b2589cc7/66072fb51b89448912e2672c_image14.jpeg"
          },
          "variantPrice": {
            "unit": "USD",
            "value": "5892",
            "string": " 55.61 USD"
          },
          "weight": 11,
          "width": 82,
          "height": 70,
          "length": 9
        },
        {
          "count": 1,
          "rowTotal": {
            "unit": "USD",
            "value": "5892",
            "string": " 83.09 USD"
          },
          "productId": "66072fb61b89448912e2678b",
          "productName": "Incredible Bronze Towels",
          "productSlug": "incredible-bronze-towels",
          "variantId": "66072fb71b89448912e2681e",
          "variantName": "Incredible Bronze Towels Sleek: Frozen, Incredible: Metal",
          "variantSlug": "incredible-bronze-towels-sleek-frozen-incredible-metal",
          "variantSKU": "incredible-bronze-towels-sleek-frozen-incredible-metal",
          "variantImage": {
            "url": "https://d1otoma47x30pg.cloudfront.net/66072f39417a2a35b2589cc7/66072fb51b89448912e26729_image16.jpeg"
          },
          "variantPrice": {
            "unit": "USD",
            "value": "5892",
            "string": " 83.09 USD"
          },
          "width": 19,
          "height": 72,
          "length": 18
        }
      ],
      "purchasedItemsCount": 3,
      "stripeDetails": {
        "paymentMethod": "pm_1P410gJYFi4lcbXWbeKghqjK",
        "paymentIntentId": "pi_3P410iJYFi4lcbXW0EKKgcVg",
        "customerId": "cus_Ptod8KJBiiPgnH",
        "chargeId": "ch_3P410iJYFi4lcbXW0DxUkzCH"
      },
      "stripeCard": {
        "last4": "4242",
        "brand": "Visa",
        "ownerName": "Arthur Dent",
        "expires": {
          "year": 2025,
          "month": 4
        }
      },
      "customData": [
        {
          "key": "value"
        }
      ],
      "metadata": {
        "isBuyNow": false
      },
      "isCustomerDeleted": false,
      "isShippingRequired": false,
      "hasDownloads": false,
      "paymentProcessor": "stripe",
      "totals": {
        "extras": [
          {
            "type": "tax",
            "name": "State Taxes",
            "description": "CA Taxes (6.25%)",
            "price": {
              "unit": "USD",
              "value": "5892",
              "string": "3.44"
            }
          }
        ]
      },
      "downloadFiles": [
        {
          "id": "5e9a5eba75e0ac242e1b6f64",
          "name": "The modern web design process - Webflow Ebook.pdf",
          "url": "https://webflow.com/dashboard/download-digital-product?payload=5d93ba5e38c6b0160ab711d3;e7634a;5eb1aac72912ec06f561278c;5e9a5eba75e0ac242e1b6f63:ka2nehxy:4a1ee0a632feaab94294350087215ed89533f2f530903e3b933b638940e921aa"
        }
      ]
    },
    {
      "orderId": "fc7-128",
      "status": "refunded",
      "comment": "Example comment to myself",
      "orderComment": "",
      "acceptedOn": "2024-03-29T21:29:21Z",
      "refundedOn": "2024-04-08T18:25:04Z",
      "customerPaid": {
        "unit": "USD",
        "value": "5892",
        "string": " 118.73 USD"
      },
      "netAmount": {
        "unit": "USD",
        "value": "5892",
        "string": " 112.62 USD"
      },
      "applicationFee": {
        "unit": "USD",
        "value": "5892",
        "string": " 2.37 USD"
      },
      "allAddresses": [
        {
          "type": "billing",
          "addressee": "Arthur Dent",
          "line1": "20 W 34th St",
          "line2": "Empire State Building",
          "city": "New York",
          "state": "New York",
          "country": "US",
          "postalCode": "10118"
        },
        {
          "type": "shipping",
          "addressee": "Arthur Dent",
          "line1": "20 W 34th St",
          "line2": "Empire State Building",
          "city": "New York",
          "state": "New York",
          "country": "US",
          "postalCode": "10118"
        }
      ],
      "shippingAddress": {
        "type": "shipping",
        "addressee": "Arthur Dent",
        "line1": "20 W 34th St",
        "line2": "Empire State Building",
        "city": "New York",
        "state": "New York",
        "country": "US",
        "postalCode": "10118"
      },
      "billingAddress": {
        "type": "billing",
        "addressee": "Arthur Dent",
        "line1": "20 W 34th St",
        "line2": "Empire State Building",
        "city": "New York",
        "state": "New York",
        "country": "US",
        "postalCode": "10118"
      },
      "shippingProvider": "Shipping Company, Co.",
      "shippingTracking": "tr00000000001",
      "shippingTrackingURL": "https://www.shippingcompany.com/tracking/tr00000000001",
      "customerInfo": {
        "fullName": "Arthur Dent",
        "email": "arthur.dent@example.com"
      },
      "purchasedItems": [
        {
          "count": 1,
          "rowTotal": {
            "unit": "USD",
            "value": "5892",
            "string": " 55.61 USD"
          },
          "productId": "66072fb61b89448912e26791",
          "productName": "Luxurious Fresh Ball",
          "productSlug": "luxurious-fresh-ball",
          "variantId": "66072fb71b89448912e2683f",
          "variantName": "Luxurious Fresh Ball Generic: Bronze, Practical: Plastic",
          "variantSlug": "luxurious-fresh-ball-generic-bronze-practical-plastic",
          "variantSKU": "luxurious-fresh-ball-generic-bronze-practical-plastic",
          "variantImage": {
            "url": "https://d1otoma47x30pg.cloudfront.net/66072f39417a2a35b2589cc7/66072fb51b89448912e2672c_image14.jpeg"
          },
          "variantPrice": {
            "unit": "USD",
            "value": "5892",
            "string": " 55.61 USD"
          },
          "weight": 11,
          "width": 82,
          "height": 70,
          "length": 9
        },
        {
          "count": 1,
          "rowTotal": {
            "unit": "USD",
            "value": "5892",
            "string": " 53.44 USD"
          },
          "productId": "66072fb61b89448912e26799",
          "productName": "Recycled Steel Gloves",
          "productSlug": "recycled-steel-gloves",
          "variantId": "66072fb91b89448912e26ab9",
          "variantName": "Recycled Steel Gloves Electronic: Granite, Handcrafted: grey",
          "variantSlug": "recycled-steel-gloves-electronic-granite-handcrafted-grey",
          "variantSKU": "recycled-steel-gloves-electronic-granite-handcrafted-grey",
          "variantImage": {
            "url": "https://d1otoma47x30pg.cloudfront.net/66072f39417a2a35b2589cc7/66072fb51b89448912e2671e_image2.jpeg"
          },
          "variantPrice": {
            "unit": "USD",
            "value": "5892",
            "string": " 53.44 USD"
          },
          "weight": 38,
          "width": 76,
          "height": 85,
          "length": 40
        }
      ],
      "purchasedItemsCount": 2,
      "stripeDetails": {
        "paymentMethod": "pm_1OzmzBJYFi4lcbXWHKNdXU7j",
        "paymentIntentId": "pi_3OzmzDJYFi4lcbXW1hTBW6ft",
        "customerId": "cus_PpRsNHwWdUoRKR",
        "chargeId": "ch_3OzmzDJYFi4lcbXW1ndkkrH2",
        "refundId": "re_3OzmzDJYFi4lcbXW1kFAmlBk",
        "refundReason": "fraudulent"
      },
      "stripeCard": {
        "last4": "4242",
        "brand": "Visa",
        "ownerName": "Arthur Dent",
        "expires": {
          "year": 2024,
          "month": 4
        }
      },
      "customData": [
        {
          "key": "value"
        }
      ],
      "metadata": {
        "isBuyNow": false
      },
      "isCustomerDeleted": false,
      "isShippingRequired": true,
      "hasDownloads": false,
      "paymentProcessor": "stripe",
      "totals": {
        "subtotal": {
          "unit": "USD",
          "value": "5892",
          "string": " 109.05 USD"
        },
        "extras": [
          {
            "type": "tax",
            "name": "State Taxes",
            "description": "NY Taxes (4.00%)",
            "price": {
              "unit": "USD",
              "value": "5892",
              "string": " 4.36 USD"
            }
          },
          {
            "type": "tax",
            "name": "City Taxes",
            "description": "NEW YORK Taxes (4.88%)",
            "price": {
              "unit": "USD",
              "value": "5892",
              "string": " 5.32 USD"
            }
          },
          {
            "type": "shipping",
            "name": "Flat",
            "description": "",
            "price": {
              "unit": "USD",
              "value": "5892",
              "string": " 0.00 USD"
            }
          }
        ],
        "total": {
          "unit": "USD",
          "value": "5892",
          "string": " 118.73 USD"
        }
      },
      "downloadFiles": [
        {
          "id": "5e9a5eba75e0ac242e1b6f64",
          "name": "New product guide",
          "url": "https://webflow.com/dashboard/download-digital-product?payload=5d93ba5e38c6b0160ab711d3;e7634a;5eb1aac72912ec06f561278c;5e9a5eba75e0ac242e1b6f63:ka2nehxy:4a1ee0a632feaab94294350087215ed89533f2f530903e3b933b638940e921aa"
        }
      ]
    }
  ],
  "pagination": {
    "limit": 100,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/orders/list](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/orders/list)*