<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9266/2196/6-activation-of-ssl-from-whmcs/ | fetched: 2026-11-01T03:37:55Z -->

# 6. Activation of SSL from WHMCS

In order to activate an SSL certificate, your client should access the list of their services and click on the "View Details" button next to the ordered certificate.

* Next, they will need to click "View certificate details", and then - "Configure certificate". They will see the window with the SSL activation fields.
* Here, they will be prompted to input the CSR code (obtained from the web-server their domain is hosted on), select a web-server type, and fill in valid admin contact info.
* Admin contact info will be pre-filled from the customer profile in WHMCS.
* In case CSR code is ok, your client will see the list of the available DCV options on the next page.
  Those are, basically, HTTP-based validation or approval email validation.
  Our client can choose any of the listed emails to receive the Domain Control Validation email on that address, or select HTTP-based DCV. If the HTTP-based method is selected, no email is to be sent for validation, however, your customer should submit a certain text file into the particular directory of the website (/.well-known/pki-validation/).

***Note**: The name and content of the file will be shown after they click "Submit", and the activation data gets transmitted to the Certificate Authority. Also, the file content can be checked in customer area by viewing the certificate details for the SSL that is being activated.*

***Note**: If you have activated the certificate with **domain.com** or **www.domain.com**
indicated as FQDN in your CSR code, please make sure that the file is available
via **http://domain.com/.well-known/pki-validation/file.txt** . In this
case, www.domain.com is considered to be under your control as well.*

*Content of the file should not be changed in any way as the Sectigo validation system is case sensitive.*

The further process will go between you or your customer and the Certificate Authority. You are to receive the approval email and to confirm it. Once done, the certificate will be sent to the admin contact email address for the SSL order within 10-15 minutes. Otherwise, some documents request will be sent to the order email for OV or EV certificates.

---

**Important**
**Note:** 

Language variables containing strings with instructions to HTTP-based validation and file content are stored in /modules/servers/namecheapssl/lang/English.php. If you use other language, you need to create
/modules/servers/namecheapssl/lang/%yourlanguage%.php and change the values of the following variables to the corresponding phrases in your language: $\_MOD\_LANG['ncssl\_http\_based\_validation'] ,$\_MOD\_LANG['ncssl\_show\_validation\_file\_contents'] , $\_MOD\_LANG['ncssl\_custom\_phrase\_sslcertapproveremaildetails'],$\_MOD\_LANG['ncssl\_custom\_phrase\_sslconfigcompletedetails']

---

|  |  |
| --- | --- |
| Previous: [Order and welcome emails for WHMCS orders](article.aspx__9265__2196__5-order-process-and-welcome-emails-in-whmcs.md) | Next: [Reissue, renewal and synchronization](article.aspx__9268__2196__7-reissue-renewal-and-synchronization.md) |
