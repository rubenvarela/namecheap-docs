<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9269/2196/10-faqs/ | fetched: 2026-11-01T03:38:16Z -->

# 10. FAQs

**I cancel certificate and nothing happens**

   
Cancellation is being performed only in your WHMCS, but not in our system. Please submit a cancellation request with our SSL support team for certificate to be revoked and refunded.

**Does your module have multi-language support?**

   
Yes, multi-language is fully integrated with WHMCS so you may change the default language of your WHMCS and language will be changed in fields used in module as well. Please note that you will need to create a custom %yourlanguage%.php file in lang directory at modules/servers/namecheapssl/lang for some fields to be translated as well. You may use default English.php as translation template.

**Getting "*2010167* Parameter Years is Missing" error while accepting order**

   
This error usually occurs when Pricing is set up inproperly for your SSL product. Please doublecheck that Payment type is set to ‘Recurring’ and there is ‘-1’ input in ‘Monhtly, Quarterly, and Semi-Anually’ fields to disable possibility of ordering SSL for terms less than a year as SSL certificates can only be ordered and issued for a whole number of years only.

**I am receiving ''['" or any other strange characters instead or error messages while activation of my renewal certificate**

   
This is a known bug, our developers are currently investigating it. In case you face this issue please email details at sslsupport@namecheap.com and purchase and activate renewal certificate manually from Namecheap if renewal is urgent. After purchasing certificate manually you will need to sync the IDs using ‘Link/Re-Link WHMCS Cert ID to NC Cert ID’ addon function.

|  |
| --- |
| Previous: [Multi-domain certificates](article.aspx__9299__2196__9-multidomain-certificates.md) |
