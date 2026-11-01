<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9299/2196/9-multidomain-certificates/ | fetched: 2026-11-01T03:38:11Z -->

# 9. Multi-domain certificates

## General information about product

Recently [Multi-Domain Certificates](https://www.namecheap.com/security/ssl-certificates/multi-domain.aspx) were added to Namecheap’s product list. These certificates are quite popular among customers, but require some additional configurations.

Multidomain certificates can be divided into 2 categories – old [single domain](https://www.namecheap.com/security/ssl-certificates/single-domain.aspx) products that now support additional domains as a configurable addon, and new multi-domain products that come with a predefined number of domains included in the product by default (more domains can be included additionally as well). Therefore number of domains included by default differs across the products. See the table for details:

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| Provider | Product name | Default number of domains (domain from CSR is counted here) | Maximum number of domains | Maximum number of domains that should be used in configurable options |
| Comodo | PositiveSSL Multi-domain | 3 | 100 | 97 |
| Comodo | Unified Communications | 3 | 100 | 97 |

## Setting upMulti-Domain Certificates

First of all, you need to set up product as described in [‘Setting up products and pricings’](article.aspx__9264__2196__4-setting-up-products-and-pricing.md) section. After product is set up the default number of addon domains (from table above) will be available during activation.

In order to give your customers ability to order additional domains you need to set up configurable options for each multi-domain certificate you set up. It would not take much time.

1. Go to configurable options and click on ‘Create a new group’ there.
2. Fill in the name of your group (We recommend mentioning product name there) and select a product you wish to associate the configurable option with.

1. Click ‘Add new configurable option’ button.

1. Option Name. This field consists of two parts, the first one is internal and the other one is Visible to clients. Option name must contain ‘san|’ element. The text input after “|” will be displayed in your clients’ shopping cart.   We recommend  to specify default number of addon domains that are already included in certificate (For example – “san|Addon domains ( 3 domains are included by default)” for PositiveSSL MultiDomain.
2. Select ‘Quantity’ as Option Type from dropdown menu. Click ‘Save changes’.
3. Type 0 in ‘Minimum Quantity Required’ and the value from the last column of the table above as ‘Maximum Allowed’. For example, if you are setting up PositiveSSL Multi Domain, please input 97 as maximum.
4. Use any name (it will not be shown anywhere) in the box next to ‘Add Option:’ and click ‘Save changes’.
5. At this point you will see the table for pricing similar to one you’ve filled in during setting up product. Please fill in pricing for each additional domain for different terms.
6. Click ‘Save changes’

That’s it. Now if your customer orders a multi-domain certificate he will be able to add some additional domains to his order.

---

**Important**
**Note:** 

Please mention the default number of domains provided with Multi-Domain Certificates in product name or product description – this will guarantee your customers that even if they do not order any additional domains, they will have some of them added by default.

---

# Managing addon domains after purchase is made.

Your client as well as you will be able to add more domains to a certificate after order is complete.

This can be done either from user and admin areas.

In order to do that in client area, your customer needs to mouse over ‘Management Actions’ and select ‘Upgrade/Downgrade Options’.

There your customer can increase number of addon domains. An attempt to decrease that number will cause error. A new hook was implemented in client area tracking attempts to decrease number of addon domains.

**\*Note\*:** Please make sure to tick the box on the screenshot below to have the ability to add a SAN to a multi-domain certificate.

---

**Important**
**Note:** 

The number of addon domains can be changed from client area only after invoice for order is paid.

In order to complete the invoice manually, navigate to the "Billing" tab -> "Invoices" -> "Add Payment" tab -> click "Add Payment" button.

---

In order to change number of addon domains in WHMCS admin area, you need to access product page and manually input the new number of addon domains.

Please note that in case you decrease or increase this number here, you need to invoice/refund your client manually.

---

**Important**
**Note:** 

In case you or your client increases number of addon domains for a certificate your Namecheap account will be charged for every extra addon domain used during activation/reissue.

For example, if your customer has ordered 2 more domains before reissue or you have manually increased number of addon domains by 2, your Namecheap account will be charged for 2 addon domains after reissue is complete from WHMCS client area.

---

## Activation of Multi-Domain Certificates.

Activation process is similar to activation of single-domain certificates. Below the CSR box you will see fields for additional domains.

It is not strongly required to fill in all the Addon Domain field during the first activation. Duplicate records are not allowed (including duplicates in CSR common name and addon domain fields).

Below is an example of first configuration page for PositiveSSL Multi Domain with 5 addon domains ordered (1 domain from CSR + 2 addon domains by default + 5 addon domains ordered separately).

The list of approver emails is different from the one you see on the second configuration page for single-domain certificates. It contains only local parts of email addresses that can be used for domain control validation. Once your customer selects one of the local parts, it will be added to every domain/subdomain input in Addon domains fields.
For example, if he selects “admin@” as approver email having “domain.com” as common name in CSR and “secure.domain.com” and “domain2.com” as addon domains, the approvals will be sent to [admin@domain.com](mailto:admin@domain.com), [admin@secure.domain.com](mailto:admin@secure.domain.com) and [admin@domain2.com](mailto:admin@domain2.com) .

If your customer wishes to change email for one of the domains, he should contact you, and you in turn need to contact us via live chat or email to have emails changed.

Such approver email selection flow on second configuration page is caused by certain limitations in WHMCS core.

|  |  |
| --- | --- |
| Go to: [Debugging and Addon functions](article.aspx__9267__2196__8-debugging-and-addon-functions.md) | Go to: [FAQ](article.aspx__9269__2196__10-faqs.md) |
