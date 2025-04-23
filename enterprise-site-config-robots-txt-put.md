# Replace robots.txt

```
PUT https://api.webflow.com/beta/sites/:site_id/robots_txt
```

Replace therobots.txtconfiguration for various user agents.
**Required Scope:** `site_config:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `rules` | list of objects | No | List of rules for user agents. |
| `rules.userAgent` | string | No | The user agent the rules apply to. |
| `rules.allows` | list of strings | No | List of paths allowed for this user agent. |
| `rules.disallows` | list of strings | No | List of paths disallowed for this user agent. |
| `sitemap` | string | No | URL to the sitemap. |




## Errors

* **400:** Robots TXT Put Request Bad Request Error
* **401:** Robots TXT Put Request Unauthorized Error
* **404:** Robots TXT Put Request Not Found Error
* **429:** Robots TXT Put Request Too Many Requests Error
* **500:** Robots TXT Put Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PUT https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/robots_txt \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "rules": [
    {
      "userAgent": "googlebot",
      "allows": [
        "/public"
      ],
      "disallows": [
        "/vogon-poetry",
        "/total-perspective-vortex"
      ]
    }
  ],
  "sitemap": "https://heartofgold.ship/sitemap.xml"
}'
```

### Example Response (200 Updated)

```json
{
  "rules": [
    {
      "userAgent": "googlebot",
      "allows": [
        "/public"
      ],
      "disallows": [
        "/vogon-poetry",
        "/total-perspective-vortex"
      ]
    }
  ],
  "sitemap": "https://heartofgold.ship/sitemap.xml"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/robots-txt/put](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/robots-txt/put)*