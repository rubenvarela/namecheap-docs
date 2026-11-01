<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9265/2196/5-order-process-and-welcome-emails-in-whmcs/ | fetched: 2026-11-01T03:37:50Z -->

# 5. Order process and welcome emails in WHMCS

The product will appear in the order process as a regular product which can be added to the cart. No configuration is performed before purchase. Once a certificate is purchased, paid for, and activated, the user is sent an email containing a link which takes them to configure the certificate in the client area. Once all details have been provided, the configuration data is sent to the Certificate Authority for validation. No manual intervention is required from you.

You have an option to resend an email containing a link to the certificate configuration page to the client. This page is also accessible from the client area (My Products & Services -> Product Details -> View Certificate Details). Options to resend approver email and email with the certificate issued are also available in the client area.

## Welcome/Configuration Email

On its first launch, Namecheap SSL module automatically creates a configuration email template (see "SSL Certificate Configuration Required" in section "Product Messages" of Email Templates in Setup). It contains link to activation process inside your client area for a specific SSL certificate.

Sending of SSL Configuration Email is controlled by the following parameters: Type of product setup behavior in Module Settings tab.

1. Configuration email is always sent for options "Automatically setup the product as soon as an order is placed" and "Automatically setup the product as soon as the first payment is received". If you select "Automatically setup the product as soon as an order is placed", a configuration email will only be sent if the order is placed from the client area. The module itself will run only if you place the order from client area as well.

2. If the options "Automatically setup the product when you manually accept a pending order" or "Do not automatically setup this product" are selected, then sending of the Configuration Email will depend on the box "Send Welcome Email".

You can modify content of the configuration email at any time.

|  |  |
| --- | --- |
| Previous: [Setting up products and settings](article.aspx__9264__2196__4-setting-up-products-and-pricing.md) | Next: [Activation of SSL from WHMCS](article.aspx__9266__2196__6-activation-of-ssl-from-whmcs.md) |
