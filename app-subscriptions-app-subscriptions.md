# Get app subscriptions

```
GET https://api.webflow.com/beta/app_subscriptions
```

Information about subscriptions for a specific authorization tokenAccess to this endpoint requires a bearer token from aData Client App.Required Scope |app_subscriptions:read


## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `appSubscriptions` | list of objects | No | N/A |
| `appSubscriptions.appSubscriptions` | object | No | N/A |
| `appSubscriptions.appSubscriptions.appId` | string | No | The unique ID of the App |
| `appSubscriptions.appSubscriptions.price` | object | No | The price of the Subscription |
| `appSubscriptions.appSubscriptions.price.value` | double | No | Price in cents |
| `appSubscriptions.appSubscriptions.price.unit` | string | No | Currency unit |
| `appSubscriptions.appSubscriptions.price.interval` | enum | No | Interval of payment (Values: MONTHLY, YEARLY, ONE_TIME) |
| `appSubscriptions.appSubscriptions.accessGrant` | object | No | Information about the granted access for the subscription. |
| `appSubscriptions.appSubscriptions.accessGrant.id` | string | No | The unique ID of the granted resource |
| `appSubscriptions.appSubscriptions.accessGrant.type` | string | No | The type of granted resource |
| `appSubscriptions.appSubscriptions.status` | enum | No | Status of the subscription (Values: active, cancelled, past due) |
| `appSubscriptions.appSubscriptions.startsAt` | datetime | No | Start time of the current billing period |
| `appSubscriptions.appSubscriptions.endsAt` | datetime | No | End time of the current billing period |




## Errors

* **401:** App Subscriptions App Subscriptions Request Unauthorized Error
* **403:** App Subscriptions App Subscriptions Request Forbidden Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/app_subscriptions \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "appSubscriptions": [
    {
      "appSubscriptions": {
        "appId": "65ae93df86d80c2f1fe3b2f8",
        "startsAt": "2024-03-19T16:00:31Z",
        "endsAt": "2024-04-19T16:00:31Z"
      }
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/app-subscriptions/app-subscriptions](https://developers.webflow.com/v2.0.0-beta/reference/app-subscriptions/app-subscriptions)*