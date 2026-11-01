<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9444/2196/whmcs-ssl-module-bug/ | fetched: 2026-11-01T03:35:20Z -->

# WHMCS SSL Module bug

Recently we discovered a bug in our WHMCS SSL Module that could possibly affect our SSL reseller. If you are not using Namecheap WHMCS SSL Module, you are not affected by the bug.The bug is that unrequested extra slots for addon domains can be purchased at Namecheap side whenever you or your clients activate any Multi-domain SSL certificates via WHMCS SSL Module with 1 or more addon domains specified in default slots.This may lead to extra amount of funds being charged for addon domain slots that are not accounted in WHMCS module, but are present at Namecheap’s side.We fixed this bug in the new version of our WHMCS SSL Module (1.6.2) and released it at <https://github.com/namecheap/ssl-whmcs> already.If you are using our WHMCS SSL Module and have Multi-domain SSL certificates activated via it, please check if you have any extra domain slots ordered at NC. For this, please do the following:

1. Log into your Namecheap account > open the Domain List from the left-side menu > locate the domain name the certificates was activated for > click on V button to expand the list of services > locate the necessary certificate and click on Manage button
2. Check “Total Domains” field. The default value of “Total Domains” for Comodo Multi-Domain SSL certificates is “3”. If the number of domains in “Total Domains” field is larger than the default one, please go to the next step.
3. Now you have to check how many slots were initially ordered. This can be done in your WHMCS Module. ‘Clients’ tab > ‘View/Search Clients’ > click on the client > ‘Invoices’ > click on the Invoice ID. Under ‘Invoice Items’ you can see the actual number of addon domains ordered by your customer (if any).
4. If you see a zero value for addon domains, the certificate was purchase with the default number of addons and no further actions are required. In case there are some addon domains listed in the ‘Invoice Items’, compare the number with the one in your Namecheap account (3+ for Comodo SSLs) and if it differs, please contact our [Support Team](https://www.namecheap.com/support/live-chat/ssl.aspx).

If there are any unused slots, our Team will be able to refund them to your account balance. Please install the [new version](https://github.com/namecheap/ssl-whmcs) of the module to avoid this bug in future.

 This is it!
