<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9268/2196/7-reissue-renewal-and-synchronization/ | fetched: 2026-11-01T03:38:01Z -->

# 7. Reissue, renewal and synchronization

Reissue and renewal are 2 different actions with SSL certificate.

After the certificate gets issued, its status becomes ‘active’ and you will see the following screen while viewing its info:

There you may download certificate in zip archive in corresponding format for your web-server or reissue the certificate.

## Reissue

Reissue is the process of having certificate regenerated with Certificate Authority if needed. For example, if your client has lost your Private Key. For that he needs to view details of his/her certificate from list of certificates in WHMCS user area and click the ‘Reissue Certificate’ button:

Further process will be very similar to activation – your customer will need to paste CSR for same domain name and select approval email. Reissuing a certificate will change its Namecheap Certificate ID. A new certificate record will be added to your Namecheap account.

## Due date and reissue state synchronization.

All changes done in WHMCS are synchronized with your Namecheap account automatically once a day (when WHMCS cron runs). Also you can perform manual synchronization any time by clicking ‘Synchronize with Namecheap’. This will set WHMCS due dates and reissue states in sync with Namecheap admin area when needed (Clients -> Products/Services -> Other services - click on the product ID):

## Renewal

Renewal is pretty much the same as purchasing new certificate with Namecheap. Renewal functionality is fully integrated into the module. As long as you have “Payment Type” set to “Recurring” when creating a product, invoices for renewals will be generated automatically. Once paid, renewal SSLs will be created automatically as well. Please keep in mind that after the renewal SSL is created, it still requires activation using CSR.

|  |  |
| --- | --- |
| Previous: [Activation of SSL from WHMCS](article.aspx__9266__2196__6-activation-of-ssl-from-whmcs.md) | Next: [Debugging and addon functions](article.aspx__9267__2196__8-debugging-and-addon-functions.md) |
