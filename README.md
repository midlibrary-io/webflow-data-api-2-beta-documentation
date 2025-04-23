# Webflow Data API v2 Beta Documentation

This directory contains individual Markdown files detailing the endpoints available in the Webflow Data API v2 Beta.

The documentation is organized by API resource category. Each file corresponds to a specific API action (e.g., list, get, create, update, delete) for a resource or sub-resource.

## API Categories

Below is a summary of the API categories and the available documentation files within each:

### App Subscriptions
- `app-subscriptions-app-subscriptions.md`: Manage app subscriptions.

### Assets
- `assets-asset-folders-get-folder.md`: Get an asset folder.
- `assets-asset-folders-create-folder.md`: Create an asset folder.
- `assets-asset-folders-list-folders.md`: List asset folders.
- `assets-assets-update.md`: Update an asset.
- `assets-assets-delete.md`: Delete an asset.
- `assets-assets-get.md`: Get an asset.
- `assets-assets-create.md`: Create/upload an asset.
- `assets-assets-list.md`: List assets.

### CMS (Content Management System)
- **Collections:**
    - `cms-collections-delete.md`: Delete a collection.
    - `cms-collections-create.md`: Create a collection.
    - `cms-collections-get.md`: Get a collection.
    - `cms-collections-list.md`: List collections.
- **Collection Fields:**
    - `cms-collection-fields-delete.md`: Delete a collection field.
    - `cms-collection-fields-update.md`: Update a collection field.
    - `cms-collection-fields-create.md`: Create a collection field.
- **Collection Items (Staged):**
    - `cms-collection-items-staged-items-publish-item.md`: Publish a staged item.
    - `cms-collection-items-staged-items-delete-items.md`: Delete multiple staged items.
    - `cms-collection-items-staged-items-delete-item.md`: Delete a staged item.
    - `cms-collection-items-staged-items-update-items.md`: Update multiple staged items.
    - `cms-collection-items-staged-items-update-item.md`: Update a staged item.
    - `cms-collection-items-staged-items-create-items.md`: Create multiple staged items.
    - `cms-collection-items-staged-items-create-item.md`: Create a staged item.
    - `cms-collection-items-staged-items-get-item.md`: Get a staged item.
    - `cms-collection-items-staged-items-list-items.md`: List staged items.
- **Collection Items (Live):**
    - `cms-collection-items-live-items-delete-items-live.md`: Delete multiple live items.
    - `cms-collection-items-live-items-delete-item-live.md`: Delete a live item.
    - `cms-collection-items-live-items-update-items-live.md`: Update multiple live items.
    - `cms-collection-items-live-items-update-item-live.md`: Update a live item.
    - `cms-collection-items-live-items-create-item-live.md`: Create a live item.
    - `cms-collection-items-live-items-get-item-live.md`: Get a live item.
    - `cms-collection-items-live-items-list-items-live.md`: List live items.

### Comments
- `comments-list-comment-replies.md`: List replies to a comment.
- `comments-get-comment-thread.md`: Get a comment thread.
- `comments-list-comment-threads.md`: List comment threads.

### Custom Code
- **Registered Scripts:**
    - `custom-code-custom-code-register-inline.md`: Register an inline script.
    - `custom-code-custom-code-register-hosted.md`: Register a hosted script.
    - `custom-code-custom-code-list.md`: List registered scripts.
- **Site Custom Code:**
    - `custom-code-custom-code-sites-list-custom-code-blocks.md`: List custom code blocks for a site.
    - `custom-code-custom-code-sites-delete-custom-code.md`: Delete a site's custom code block.
    - `custom-code-custom-code-sites-upsert-custom-code.md`: Upsert a site's custom code block.
    - `custom-code-custom-code-sites-get-custom-code.md`: Get a site's custom code block.
- **Page Custom Code:**
    - `custom-code-custom-code-pages-delete-custom-code.md`: Delete a page's custom code block.
    - `custom-code-custom-code-pages-upsert-custom-code.md`: Upsert a page's custom code block.
    - `custom-code-custom-code-pages-get-custom-code.md`: Get a page's custom code block.

### Ecommerce
- **Inventory:**
    - `ecommerce-inventory-update.md`: Update inventory for SKUs.
    - `ecommerce-inventory-list.md`: List inventory for SKUs.
- **Orders:**
    - `ecommerce-orders-refund.md`: Refund an order.
    - `ecommerce-orders-update-unfulfill.md`: Unfulfill an order.
    - `ecommerce-orders-update-fulfill.md`: Fulfill an order.
    - `ecommerce-orders-update.md`: Update an order.
    - `ecommerce-orders-get.md`: Get an order.
    - `ecommerce-orders-list.md`: List orders.
- **Products & SKUs:**
    - `ecommerce-products-sk-us-update-sku.md`: Update a specific SKU for a product.
    - `ecommerce-products-sk-us-create-sku.md`: Create a specific SKU for a product.
    - `ecommerce-products-sk-us-update.md`: Update SKUs for a product.
    - `ecommerce-products-sk-us-get.md`: Get SKUs for a product.
    - `ecommerce-products-sk-us-create.md`: Create SKUs for a product.
    - `ecommerce-products-sk-us-list.md`: List SKUs for a product.
- **Settings:**
    - `ecommerce-settings-get-settings.md`: Get Ecommerce settings.

### Enterprise
- `enterprise-site-activity-list.md`: List site activity logs (Enterprise).
- **Site Config (Well Known Files):**
    - `enterprise-site-config-well-known-files-delete.md`: Delete a well-known file configuration.
    - `enterprise-site-config-well-known-files-put.md`: Create or update a well-known file configuration.
- **Site Config (URL Redirects):**
    - `enterprise-site-config-url-redirects-delete.md`: Delete URL redirects.
    - `enterprise-site-config-url-redirects-patch.md`: Update URL redirects.
    - `enterprise-site-config-url-redirects-create.md`: Create URL redirects.

### Forms
- **Submissions:**
    - `forms-form-submissions-delete-submission.md`: Delete a form submission.
    - `forms-form-submissions-update-submission.md`: Update a form submission.
    - `forms-form-submissions-list-submissions-by-site.md`: List form submissions for a site.
    - `forms-form-submissions-get-submission.md`: Get a form submission.
    - `forms-form-submissions-list-submissions.md`: List form submissions for a form.
- **Forms:**
    - `forms-forms-get.md`: Get a form.
    - `forms-forms-list.md`: List forms for a site.

### Meta
- `meta-resolve.md`: Resolve IDs.
- `meta-authorized-by.md`: Get authorization info.

### Pages and Components
- **Components:**
    - `pages-and-components-components-update-properties.md`: Update component properties.
    - `pages-and-components-components-get-properties.md`: Get component properties.
    - `pages-and-components-components-update-content.md`: Update component content.
    - `pages-and-components-components-get-content.md`: Get component content.
    - `pages-and-components-components-list.md`: List components.
- **Pages:**
    - `pages-and-components-pages-update-static-content.md`: Update static page content.
    - `pages-and-components-pages-get-content.md`: Get page content.
    - `pages-and-components-pages-update-page-settings.md`: Update page settings.
    - `pages-and-components-pages-get-metadata.md`: Get page metadata.
    - `pages-and-components-pages-list.md`: List pages.

### Sites
- `sites-publish.md`: Publish a site.
- `sites-get-custom-domain.md`: Get a site's custom domain.
- `sites-get.md`: Get a site.
- `sites-list.md`: List sites.

### User Accounts
- **Access Groups:**
    - `user-accounts-access-groups-list.md`: List access groups.
- **Users:**
    - `user-accounts-user-accounts-invite.md`: Invite a user.
    - `user-accounts-user-accounts-update.md`: Update a user.
    - `user-accounts-user-accounts-delete.md`: Delete a user.
    - `user-accounts-user-accounts-get.md`: Get a user.
    - `user-accounts-user-accounts-list.md`: List users.

### Webhooks
- `webhooks-webhooks-delete.md`: Delete a webhook.
- `webhooks-webhooks-create.md`: Create a webhook.
- `webhooks-webhooks-get.md`: Get a webhook.
- `webhooks-webhooks-list.md`: List webhooks.

---

Refer to the individual `.md` files for detailed information on each endpoint, including request/response formats, parameters, and examples. 