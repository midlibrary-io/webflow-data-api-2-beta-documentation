# Get Order

```
GET https://api.webflow.com/beta/sites/:site_id/orders/:order_id
```

Retrieve a single product by its ID. All of its SKUs will also be
retrieved.
**Required Scope:** `ecommerce:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `order_id` | string | Yes | Unique identifier for an Order |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `orderId` | string | No | The order ID. Will usually be 6 hex characters, but can also be 9 hex characters if the site has a very large number of Orders. Randomly assigned. |
| `status` | enum | No | The status of the Order (Values: pending, unfulfilled, fulfilled, disputed, dispute-lost, refunded) |
| `comment` | string | No | A comment string for this Order, which is editable by API user (not used by Webflow). |
| `orderComment` | string | No | A comment that the customer left when making their Order |
| `acceptedOn` | datetime | No | The ISO8601 timestamp that an Order was placed. |
| `fulfilledOn` | datetime | No | When an Order is marked as ‘fulfilled’, this field represents the timestamp of the fulfillment in ISO8601 format. Otherwise, it is null. |
| `refundedOn` | datetime | No | When an Order is marked as ‘refunded’, this field represents the timestamp of the fulfillment in ISO8601 format. Otherwise, it is null. |
| `disputedOn` | datetime | No | When an Order is marked as ‘disputed’, this field represents the timestamp of the fulfillment in ISO8601 format. Otherwise, it is null. |
| `disputeUpdatedOn` | datetime | No | If an Order has been disputed by the customer, this key will be set to the ISO8601 timestamp of the last update received. If the Order is not disputed, the key will be null. |
| `disputeLastStatus` | enum | No | If an order was disputed by the customer, then this key will be set with thedispute’s status. (Values: warning_needs_response, warning_under_review, warning_closed, needs_response, under_review, charge_refunded, won, lost) |
| `customerPaid` | object | No | The total paid by the customer |
| `customerPaid.unit` | string | No | The three-letter ISO currency code |
| `customerPaid.value` | string | No | The numeric value in the base unit of the currency |
| `customerPaid.string` | string | No | The user-facing string representation of the amount |
| `netAmount` | object | No | The net amount after application fees |
| `netAmount.unit` | string | No | The three-letter ISO currency code |
| `netAmount.value` | string | No | The numeric value in the base unit of the currency |
| `netAmount.string` | string | No | The user-facing string representation of the amount |
| `applicationFee` | object | No | The application fee assessed by the platform |
| `applicationFee.unit` | string | No | The three-letter ISO currency code |
| `applicationFee.value` | string | No | The numeric value in the base unit of the currency |
| `applicationFee.string` | string | No | The user-facing string representation of the amount |
| `allAddresses` | list of objects | No | All addresses provided by the customer during the ordering flow. |
| `allAddresses.type` | enum | No | The type of the order address (billing or shipping) (Values: shipping, billing) |
| `allAddresses.japanType` | enum | No | Represents a Japan-only address format. This field will only appear on orders placed from Japan. (Values: kana, kanji) |
| `allAddresses.addressee` | string | No | Display name on the address |
| `allAddresses.line1` | string | No | The first line of the address |
| `allAddresses.line2` | string | No | The second line of the address |
| `allAddresses.city` | string | No | The city of the address. |
| `allAddresses.state` | string | No | The state or province of the address |
| `allAddresses.country` | string | No | The country of the address |
| `allAddresses.postalCode` | string | No | The postal code of the address |
| `shippingAddress` | object | No | The shipping address |
| `shippingAddress.type` | enum | No | The type of the order address (billing or shipping) (Values: shipping, billing) |
| `shippingAddress.japanType` | enum | No | Represents a Japan-only address format. This field will only appear on orders placed from Japan. (Values: kana, kanji) |
| `shippingAddress.addressee` | string | No | Display name on the address |
| `shippingAddress.line1` | string | No | The first line of the address |
| `shippingAddress.line2` | string | No | The second line of the address |
| `shippingAddress.city` | string | No | The city of the address. |
| `shippingAddress.state` | string | No | The state or province of the address |
| `shippingAddress.country` | string | No | The country of the address |
| `shippingAddress.postalCode` | string | No | The postal code of the address |
| `billingAddress` | object | No | The billing address |
| `billingAddress.type` | enum | No | The type of the order address (billing or shipping) (Values: shipping, billing) |
| `billingAddress.japanType` | enum | No | Represents a Japan-only address format. This field will only appear on orders placed from Japan. (Values: kana, kanji) |
| `billingAddress.addressee` | string | No | Display name on the address |
| `billingAddress.line1` | string | No | The first line of the address |
| `billingAddress.line2` | string | No | The second line of the address |
| `billingAddress.city` | string | No | The city of the address. |
| `billingAddress.state` | string | No | The state or province of the address |
| `billingAddress.country` | string | No | The country of the address |
| `billingAddress.postalCode` | string | No | The postal code of the address |
| `shippingProvider` | string | No | A string editable by the API user to note the shipping provider used (not used by Webflow). |
| `shippingTracking` | string | No | A string editable by the API user to note the shipping tracking number for the order (not used by Webflow). |
| `shippingTrackingURL` | string | No | N/A |
| `customerInfo` | object | No | An object with the keysfullNameandemail. |
| `customerInfo.fullName` | string | No | The full name of the Customer |
| `customerInfo.email` | string | No | The Customer’s email address |
| `purchasedItems` | list of objects | No | An array of all things that the Customer purchased. |
| `purchasedItems.count` | double | No | Number of Item purchased. |
| `purchasedItems.rowTotal` | object | No | The total for the row |
| `purchasedItems.rowTotal.unit` | string | No | The three-letter ISO currency code |
| `purchasedItems.rowTotal.value` | string | No | The numeric value in the base unit of the currency |
| `purchasedItems.rowTotal.string` | string | No | The user-facing string representation of the amount |
| `purchasedItems.productId` | string | No | The unique identifier for the Product |
| `purchasedItems.productName` | string | No | User-facing name of the Product |
| `purchasedItems.productSlug` | string | No | Slug for the Product |
| `purchasedItems.variantId` | string | No | Identifier for the Product Variant (SKU) |
| `purchasedItems.variantName` | string | No | User-facing name of the Product Variant (SKU) |
| `purchasedItems.variantSlug` | string | No | Slug for the Product Variant (SKU) |
| `purchasedItems.variantSKU` | string | No | The user-defined custom SKU of the Product Variant (SKU) |
| `purchasedItems.variantImage` | object | No | N/A |
| `purchasedItems.variantImage.url` | string | No | The hosted location for the Variant’s image |
| `purchasedItems.variantImage.file` | object | No | N/A |
| `purchasedItems.variantImage.file.size` | double | No | The image size in bytes |
| `purchasedItems.variantImage.file.originalFileName` | string | No | the original name of the image |
| `purchasedItems.variantImage.file.createdOn` | datetime | No | The creation timestamp of the image |
| `purchasedItems.variantImage.file.contentType` | string | No | The MIME type of the image |
| `purchasedItems.variantImage.file.width` | integer | No | The image width in pixels |
| `purchasedItems.variantImage.file.height` | integer | No | The image height in pixels |
| `purchasedItems.variantImage.file.variants` | list of objects | No | Variants of the supplied image |
| `purchasedItems.variantImage.file.variants.url` | string | No | The hosted location for the Variant’s image |
| `purchasedItems.variantImage.file.variants.originalFileName` | string | No | N/A |
| `purchasedItems.variantImage.file.variants.size` | double | No | The image size in bytes |
| `purchasedItems.variantImage.file.variants.width` | integer | No | The image width in pixels |
| `purchasedItems.variantImage.file.variants.height` | integer | No | The image height in pixels |
| `purchasedItems.variantPrice` | object | No | The price corresponding to the variant |
| `purchasedItems.variantPrice.unit` | string | No | The three-letter ISO currency code |
| `purchasedItems.variantPrice.value` | string | No | The numeric value in the base unit of the currency |
| `purchasedItems.variantPrice.string` | string | No | The user-facing string representation of the amount |
| `purchasedItems.weight` | double | No | The physical weight of the variant if provided, or null |
| `purchasedItems.width` | double | No | The physical width of the variant if provided, or null |
| `purchasedItems.height` | double | No | The physical height of the variant if provided, or null |
| `purchasedItems.length` | double | No | The physical length of the variant if provided, or null |
| `purchasedItemsCount` | double | No | The sum of all ‘count’ fields in ‘purchasedItems’. |
| `stripeDetails` | object | No | An object with various Stripe IDs, useful for linking into the stripe dashboard. |
| `stripeDetails.subscriptionId` | string | No | Stripe-generated identifier for the Subscription |
| `stripeDetails.paymentMethod` | string | No | Stripe-generated identifier for the PaymentMethod used |
| `stripeDetails.paymentIntentId` | string | No | Stripe-generated identifier for the PaymentIntent, or null |
| `stripeDetails.customerId` | string | No | Stripe-generated customer identifier, or null |
| `stripeDetails.chargeId` | string | No | Stripe-generated charge identifier, or null |
| `stripeDetails.disputeId` | string | No | Stripe-generated dispute identifier, or null |
| `stripeDetails.refundId` | string | No | Stripe-generated refund identifier, or null |
| `stripeDetails.refundReason` | string | No | Stripe-generated refund reason, or null |
| `stripeCard` | object | No | Details on the card used to fulfill this order, if this order was finalized with Stripe. |
| `stripeCard.last4` | string | No | The last 4 digits on the card as a string |
| `stripeCard.brand` | enum | No | The card’s brand (ie. credit card network) (Values: Visa, American Express, MasterCard, Discover, JCB, Diners Club, Unknown) |
| `stripeCard.ownerName` | string | No | The name on the card. |
| `stripeCard.expires` | object | No | The card’s expiration date. |
| `stripeCard.expires.year` | double | No | Year that the card expires |
| `stripeCard.expires.month` | double | No | Month that the card expires |
| `paypalDetails` | object | No | N/A |
| `paypalDetails.orderId` | string | No | PayPal order identifier |
| `paypalDetails.payerId` | string | No | PayPal payer identifier |
| `paypalDetails.captureId` | string | No | PayPal capture identifier |
| `paypalDetails.refundId` | string | No | PayPal refund identifier |
| `paypalDetails.refundReason` | string | No | PayPal-issued reason for the refund |
| `paypalDetails.disputeId` | string | No | PayPal dispute identifier |
| `customData` | list of maps from strings to any | No | An array of additional inputs for custom order data gathering. Each object in the array represents an input with a name, and a textInput, textArea, or checkbox value. |
| `metadata` | object | No | N/A |
| `metadata.isBuyNow` | boolean | No | N/A |
| `isCustomerDeleted` | boolean | No | A boolean indicating whether the customer has been deleted from the site. |
| `isShippingRequired` | boolean | No | A boolean indicating whether the order contains one or more purchased items that require shipping. |
| `hasDownloads` | boolean | No | A boolean indicating whether the order contains one or more purchased items that are downloadable. |
| `paymentProcessor` | string | No | A string indicating the payment processor used for this order. |
| `totals` | object | No | An object describing various pricing totals |
| `totals.subtotal` | object | No | The subtotal price |
| `totals.subtotal.unit` | string | No | The three-letter ISO currency code |
| `totals.subtotal.value` | string | No | The numeric value in the base unit of the currency |
| `totals.subtotal.string` | string | No | The user-facing string representation of the amount |
| `totals.extras` | list of objects | No | An array of extra items, includes discounts, shipping, and taxes. |
| `totals.extras.type` | enum | No | The type of extra item this is. (Values: discount, discount-shipping, shipping, tax) |
| `totals.extras.name` | string | No | A human-readable (but English) name for this extra charge. |
| `totals.extras.description` | string | No | A human-readable (but English) description of this extra charge. |
| `totals.extras.price` | object | No | The price for the item |
| `totals.extras.price.unit` | string | No | The three-letter ISO currency code |
| `totals.extras.price.value` | string | No | The numeric value in the base unit of the currency |
| `totals.extras.price.string` | string | No | The user-facing string representation of the amount |
| `totals.total` | object | No | The total price |
| `totals.total.unit` | string | No | The three-letter ISO currency code |
| `totals.total.value` | string | No | The numeric value in the base unit of the currency |
| `totals.total.string` | string | No | The user-facing string representation of the amount |
| `downloadFiles` | list of objects | No | An array of downloadable file objects. |
| `downloadFiles.id` | string | No | The unique identifier for the downloadable file |
| `downloadFiles.name` | string | No | The user-facing name for the downloadable file |
| `downloadFiles.url` | string | No | The hosted location for the downloadable file |




## Errors

* **400:** Orders Get Request Bad Request Error
* **401:** Orders Get Request Unauthorized Error
* **403:** Orders Get Request Forbidden Error
* **404:** Orders Get Request Not Found Error
* **409:** Orders Get Request Conflict Error
* **429:** Orders Get Request Too Many Requests Error
* **500:** Orders Get Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/orders/5e8518516e147040726cc415 \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "orderId": "fc7-128",
  "status": "refunded",
  "comment": "Customer requested gift wrapping and a personalized note saying: Happy Birthday, Ford! 🎉 Please ensure the item is packed with extra bubble wrap for safe transit.",
  "orderComment": "Please gift wrap with a personal note saying \"Happy Birthday, Ford! 🎉",
  "acceptedOn": "2024-03-29T21:29:21Z",
  "fulfilledOn": "2024-03-29T21:29:21Z",
  "refundedOn": "2024-04-08T18:25:04Z",
  "disputedOn": "2024-03-29T21:29:21Z",
  "disputeUpdatedOn": "2024-03-29T21:29:21Z",
  "disputeLastStatus": "charge_refunded",
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
      "japanType": "kana",
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
      "japanType": "kana",
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
    "japanType": "kana",
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
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/orders/get](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/orders/get)*