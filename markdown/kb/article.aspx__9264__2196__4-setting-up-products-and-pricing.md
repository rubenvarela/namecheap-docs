<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9264/2196/4-setting-up-products-and-pricing/ | fetched: 2026-11-01T03:37:46Z -->

# 4. Setting up products and pricing

To setup an SSL certificate product, please follow the steps below:

1. Open the Setup - Products/Services - Products/Services tab within your WHMCS.

2. Click on the **Create a New Product** link at the top of the tab.

3. Ensure the welcome email is set to "None" in the dropdown menu on the Details tab, as the module sends its own email.

4. In this version, the module billing cycles and SSL validity period are configured via standard WHMCS “Products/Services” settings. To access this, go to the *Pricing* tab and select *Payment Type to Recurring*. Now disable *“One Time/Monthly”*, *“Quarterly”* and *“Semi-Annualy”* billing cycles since they are not applicable to SSL Certificates. Finally, specify prices for remaining billing cycles. *“Annually”* corresponds to 1 year of SSL certificate validity (i.e. the SSL will be registered for 1 year). Biennially refer to 2 years respectively.

5. On the *Module Settings* tab, choose *"Namecheapssl"* from Module Name dropdown menu.

6. Enter your API credentials. If you wish to test this module in sandbox environment, make sure to enter your sandbox username, sandbox API key in the corresponding text fields. Also, be sure to check the *“Test Mode”* box.

7. Choose the certificate type from the drop-down menu.

8. If you have a special *“Promotion Code”*, type it into the corresponding text field.

9. If *“Use existing SSL from account”* option is checked we will try to use an existing SSL certificate of this type from your Namecheap account first. If there is no SSL available that can be used, a new certificate will be purchased.

10. The purpose of the next set of fields is to customize the **Technical Contact Details** for any purchased SSL Certificates (fields are shown on a screens shot below). By default, Namecheap Contact details are used (email address sslsupport@namecheap.com). Using a custom Technical Contact Details is useful for resellers who wish to appear as an independent business entity to their customers. Depending on whether you want to use custom Technical Contact Details or not, perform the corresponding action:

* In order to use **Default Technical Email** leave ALL of the fields below empty.
* If you wish to use **Custom Technical Email** fill in ALL of the fields below.

11. It is possible to set up a **Featured product** option for any product that belongs to a group.

To do this, please follow these steps: Go to **Details** tab > Mark the checkbox **Featured > Save**.

The featured product will be promoted more prominently than others.

***It is recommended to chose only one featured product per group to avoid any issues.***

**Note**: Product groups can be created in the same **Setup - Products/Services - Products/Services** tab within your WHMCS.

|  |  |
| --- | --- |
| Previous: [Download and installation](article.aspx__9270__2196__3-download-and-installation.md) | Next: [Order process and welcome emails in WHMCS](article.aspx__9265__2196__5-order-process-and-welcome-emails-in-whmcs.md) |
