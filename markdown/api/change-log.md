<!-- source: https://www.namecheap.com/support/api/change-log/ | fetched: 2026-11-01T03:17:22Z -->

## Namecheap API Change Log

###### 28-Feb-2018

* Disabled possibility of activating 3-year SSL products in [namecheap.ssl.activate](methods__ssl__activate.md).
* Added warning for 3-year SSL products in [namecheap.ssl.reissue](methods__ssl__reissue.md).

###### 26-Feb-2018

* Deprecated 3-year option for all SSL products in [namecheap.ssl.create](methods__ssl__create.md) and [namecheap.ssl.renew](methods__ssl__renew.md).

###### 20-July-2017

* New command [namecheap.ssl.editdcvmethod](methods__ssl__editdcvmethod.md) added.

###### 10-June-2017

* Numerous parameters were deprecated, some were made not required in [namecheap.ssl.activate](methods__ssl__activate.md) and [namecheap.ssl.reissue](methods__ssl__reissue.md) APIs. Introduced CNAME DCV method.

###### 22-May-2014

* Additional parameters were added to [namecheap.ssl.activate](methods__ssl__activate.md), [namecheap.ssl.reissue](methods__ssl__reissue.md), [namecheap.ssl.create](methods__ssl__create.md), [namecheap.ssl.getinfo](methods__ssl__get-info.md), [namecheap.ssl.parsecsr](methods__ssl__parse-csr.md) commands related to multi-domain and http-based validation method.
* New commands [namecheap.ssl.purchasemoresans](methods__ssl__purchasemoresans.md) and [namecheap.ssl.revokecertificate](methods__ssl__revokecertificate.md) added.

###### 10-July-2012

* Additional parameters for Comodo OV certificates were added to [namecheap.ssl.activate](methods__ssl__activate.md) command.

###### 08-Jun-2012

* UK domain registrations are now real time in [namecheap.domains.create](methods__domains__create.md) command.

###### 08-May-2012

* EPP code with special characters should now be sent in base64 format in [namecheap.domains.transfer.create](methods__domains-transfer__create.md) command.

###### 15-Dec-2011

* IDN domain registeration support enabled in [namecheap.domains.create](methods__domains__create.md) command.
* New command [namecheap.domains.getInfo](methods__domains__get-info.md) added.

###### 17-Nov-2011

* Quantity parameter is removed in [namecheap.ssl.create](methods__ssl__create.md) command.

###### 12-Nov-2011

* Added support for OX as email type in [namecheap.domains.dns.sethosts](methods__domains-dns__set-hosts.md) command.

###### 24-Aug-2011

* The following parameters were added to [namecheap.ssl.activate](methods__ssl__activate.md) command: CompanyIncorporationLocality, CompanyIncorporationStateProvince, CompanyIncorporationCountry, CompanyIncorporationDate, CompanyDBA, CompanyRegistrationNumber.

###### 27-May-2011

* New command [namecheap.ssl.reissue](methods__ssl__reissue.md) added.

###### 30-Apr-2011

* Added support for EssentialSSL, EssentialSSL Wildcard, InstantSSL Pro, Premiumssl wildcard, EV SSL, EV SSL SGC.

###### 31-Mar-2011

* Free PositiveSSL offer is no longer supported.

###### 29-Nov-2010

* Added support for .ASIA registration
* Added extended attributes information for .ASIA domains ([Extended Attributes](extended-attributes.md)).

###### 18 Oct-2010

* Updated extended attributes for .CA registration ([Extended Attributes](extended-attributes.md)).Removed attributes: CIRA-Registrant, CIRA-Registrant-Desc, CIRA-Org-Registered-In, CIRA-Trademark-No Added attributes: CIRAWhoisDisplay, CIRAAgreementVersion, CIRAAgreementValue, CIRALanguage
* EPP code now required for .CA transfers

###### 12-Aug-2010

* Domain registrations, renewals and transfers now allowed for .co domains.

###### 05-Aug-2010

* [namecheap.domains.transfer.create](methods__domains-transfer__create.md) now supports .de domain transfers.

###### 22-Jun-2010

* New command [namecheap.domains.transfer.getlist](methods__domains-transfer__get-list.md) added.

###### 19-Jul-2010

* .EU registrations allowed through API.

###### 11-Jun-2010

* New optional parameter TTL added in [namecheap.domains.dns.sethosts](methods__domains-dns__set-hosts.md) command.

###### 17-Feb-2010

* New command [namecheap.users.createaddfundsrequest](methods__users__create-add-funds-request.md) added in sandbox.
* New command [namecheap.users.getaddfundsstatus](methods__users__get-add-funds-status.md) added in sandbox.

###### 30-Jan-2010

* New command [namecheap.users.login](methods__users__login.md) added in sandbox.

###### 13-Jan-2010

* New commands namecheap.ssl.resendApproverEmail and namecheap.ssl.resendFulfillmentEmail added.

###### 09-Sep-2009

* Added a few more possible values in [extended attributes](extended-attributes.md) page for .co.uk and .org.uk TLDs.

###### 24-Jul-2009

* New optional parameter *PhoneExt* added in [namecheap.users.update](methods__users__update.md) commands.
* New optional parameter *AdminPhoneExt* added in [namecheap.ssl.activate](methods__ssl__activate.md) command.

###### 02-Jun-2009

* New command [namecheap.users.getPricing](methods__users__get-pricing.md) added.

###### 30-May-2009

* New optional parameters *AddFreeWhoisguard*, *WGEnabled* and *AddFreePositiveSSL* added in [namecheap.domains.create](methods__domains__create.md) command.
* New command [namecheap.domains.getTldlist](methods__domains__get-tld-list.md) added.
