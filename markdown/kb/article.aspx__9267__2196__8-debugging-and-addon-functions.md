<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9267/2196/8-debugging-and-addon-functions/ | fetched: 2026-11-01T03:38:06Z -->

# 8. Debugging and add-on functions

 Our Namecheap module addon has following functions:

* Log
* Link/Re-Link WHMCS cert ID to NC Cert ID

## Log

While setting up product you may check ‘Debug mode’ box below technical contact info in module settings of your product in order to have your actions with module logged :

This will allow you to check log of actions performed by module in addons section in WHMCS.

There you will find all of the actions performed by your customer with namecheapssl products, all hook actions and all API calls and responses. This is very convenient for investigation of possible issues.

Each action will have WHMCS service ID of certificate that was viewed/activated/reissued from WHMCS user area so you will be able to track actions of your customers.

## Link/Re-Link WHMCS Cert ID to NC Cert ID

This feature allows connecting WHMCS certificate record to an existing Namecheap certificate.

For this you will need to input WHMCS product ID, given after order placement to corresponding box and then to input cert ID of an existing certificate within your NC account (can be found in the URL when clicking on the certificate details in your Domain list at Namecheap).

After clicking ‘Sync’ details for specific certificate in your WHMCS will be taken from Namecheap.

## Certificate List

In this section you may see all of the certificates recorded via your WHMCS from all of the NC accounts associated with it.

You will see the following fields in the lists:

|  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Certificate ID** | **Host Name** | **Type** | **Purchase Date** | **Expire Date** | **Activaton Expire Date** | **Expired** | **Status** | **WHMCS Product ID** | **WHMCS Cert Status** |
| 611111 | domain.com | PositiveSSL | 03.03.2013 | 03.03.2014 | - | N | Active | 1 | Active |
|

|  |  |
| --- | --- |
| Go to: [Reissue, renewal and synchronization](article.aspx__9268__2196__7-reissue-renewal-and-synchronization.md) | Go to: [FAQ](article.aspx__9269__2196__10-faqs.md) |
