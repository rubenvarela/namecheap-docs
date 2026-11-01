<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9302/2196/release-notes/ | fetched: 2026-11-01T03:35:25Z -->

# Release notes

**NOTE: Starting from December 1, 2016, we no longer provide Symantec group certificates (Symantec, GeoTrust or Thawte).**

**Note** that starting from **September 2019**, WHMCS SSL module development has been terminated. Please [Contact Us](https://www.namecheap.com/support/live-chat/ssl/) if you have any issues with the module setup.

### Version 1.6.5

*Released on Mar 28, 2016*

* Fixed bug with approver emails for Symantec OV and EV certificates.
* Added notification about latin characters to the first certificate activation page.
* Job/Title set as an obligatory field for Symantec certificates.

### Version 1.6.4

*Released on Nov 27, 2015*

* Removed email and HTTP validation for Symantec OV and EV certificates.
* Added product due date synchronization offset in settings section of addon.
* Simplified domain validation choice for Symantec DV certificates reissue.

### Version 1.6.3

*Released on Dec 24, 2014*

* Fixed a bug with Job Title field for Thawte and Symantec certificates.
* Fixed a type in the lang file.

### Version 1.6.2

*Released on Dec 15, 2014*

**Important Information:** Previous versions of WHMCS SSL Module contained the bug that could potentially affect clients that resell Multi-Domain SSL certificates using WHMCS module. Please check details of the bug and how it might have affected you in the following [Knowledgebase article](article.aspx__9444__2196__whmcs-ssl-module-bug.md).

Other changes:

* Fixed number of addon domains for Comodo EV Multi Domain SSL and Multi Domain SSL to 3.
* Fixed approver email resendingfor Geotrust DV certificates.
* Fixed Organization fields for Comodo EV Multi Domain SSL.
* Fixed issues with Job Title field: Added Job Title to Module Settings and made it required field for Thawte, Symantec and EV Geotrust certificates.
* 15 seconds timeout was implemented for uploading certificate types.
* Added "SourceOfCall" parameter to API calls to Namecheap.

### Version 1.6.1

*Released on Jul 25, 2014*

* Small fixes related to PHP 5.4 Strict Standards warning.

### Version 1.6.0

*Released on Jul 23, 2014*

* Added MYSQL wrapper, improved security for DBMS work.
* Changed RapidSSL/Geotrust/Thawte/Symantec reissue procedure: Now, administrative information and emails cannot be edited, due to restrictions from the Certificate Authority.
* Added revocation functionality.
* Performed partial code refactoring.
* Fixed error involving inability to use multi-domain certificates without setting up configurable options.
* Added fix for hook sending empty requests in case of mySQL malfunction.
* Minor fixes.

### Version 1.5.1

*Released on Jun 20, 2014*

* Minor fixed related to cron sending empty requests to Namecheap API users.

### Version 1.5

*Released on Dec 16, 2013*

* Multi-Domain Certificates support added
* Fixed bug causing incorrect display of list of certificates in addon for cases when production username is same as sandbox one.
* Fixed showing all possible Management options in user area instead of showing only available ones.
* Fixed of issue with no fields appearing in ‘Module Settings’ after selecting ‘namecheapssl’ from dropdown menu.
* Fixed issue with "Unhandled Exception" error being received while reissue
* Minor internal fixes.

### Version 1.4.2

*Released on Nov 15, 2013*

* Fixed bug related to ‘Invalid Link Followed’ error (Addon updated to version 1.3)

### Version 1.4.1

*Released on Nov 1, 2013*

* Added possibility to reissue Symantec certificates from WHMCS interface.
  + Added possibility to use HTTP-based validation instead of approval email.
  + Added possibility to download certificate from WHMCS user area.
  + Added additional checks for API responses.
  + Added Whois emails to list of addresses for Domain Control Validation.
  + Fixed uninformative error message ‘Invalid Phone or Country code’.
  + Fixed dependence of module language upon language choice in WHMCS
  + Minor fixes.

### Version 1.4.0

*Released on Sep 27, 2013*

* Improved log functionality
* Added possibility to link/relink Namecheap certificates (existing) with WHMCS orders.
* Added built-in lookup for list of certs for all of users having products set up within WHMCS module.
* Added compatibility with Comodo Sandbox Environment
* Added daily email report for all actions with Namecheap SSL Module.
* Reduced amount of hard-coded lang variables for better translatability
* Minor fixes

### Version 1.3.2

*Released on Jul 04, 2013*

* Fixed minor file issue of version 1.3.1.

### Version 1.3.1

*Released on Jul 04, 2013*

* Changed installation process.
* Changed certificate creation process. Now the NC side certificate is created on the third step of configuration.
  + The created Certificate’s used for backward compatibility with the presence of certificate NC REMOTE ID in database.
* If the product settings of the ordered Certificate have "Use existing SSL from account" option enabled, then on the third step of configuration all the certificates with the "new purchase" status will be verified. If there is an Active certificate of the same type a REMOTE ID will be used and a new certificate will not be created.
  + For PositiveSSL certificates type of "PositiveSSL Free" is checked.
* Added Thawte certificates support.
* Added necessary additional fields Comodo EV SSL, Comodo EV SGC SSL certificates on the first configuration step.
* Added necessary additional fields for the following Certificates: GEOTRUST: True BusinessID With EV, True BusinessID, True BusinessID Wildcard; VERISIGN: Secure Site, Secure Site Pro, Secure Site with EV, Secure Site Pro with EV; THAWTE: SSL123, SSL Web Server, SGC Super Certs, SSL WebServer EV

**Bug Fixes:**

* Fixed a case where the php.ini directive arg\_separator.input not equal to "&".
* Removed extra check for null value phone / fax number on the side of the module.
* Fixed the hook to synchronize the date and state of expiration and reissue
* Fixed possible php parse error in addon. Could take place previously when php.ini directive short\_open\_tag was disabled.

### Version 1.3.0

*Released on Jun 20, 2013*

* $1.99 PositiveSSL certificates can now be used for activation from WHMCS with ‘Use existing SSL from account’ feature.
* Fixed possible issues with viewing information and synchronizing due dates from admin area.
* Fixed possible source of ‘memory’ issue occurring while first access to Namecheap addon.
* Changed installation directories – now addon is located in ‘addons’ folder, not in ‘admin’ .

### Version 1.2.6

*Released on Oct 25, 2012*

* Products/Services Configuration bug fixed.
* Callback details for DV SSLs bug fixed.

### Version 1.2.4

*Released on Oct 21, 2012*

* "Use existing SSL from account" bug related to absence of eligible products fixed.

### Version 1.2.3

*Released on Oct 13, 2012*

* Renewal bug related to error 2011300 fixed.

* "Use existing SSL from account" bug related to mismatch of product names fixed.

### Version 1.2.2

*Released on Aug 20, 2012*

* Installation mechanism improved.

* Database related error during installation fixed.

* New 'Callback Contact Fields' added for organization validation comodo certificates.

### Version 1.2.1

*Released on Apr 8, 2012*

* Additional compatibility with WHMCS 5.x version added.

### Version 1.2

*Released on Mar 30, 2012*

* Reissue functionality for Comodo SSL Certificates
* Synchronize due date and reissue state functionality
* View certificate details (including Namecheap Order ID and Certificate ID)
* Debug Mode for troubleshooting issues (log Namecheap API events)

### Version 1.1.5

*Released on Dec 22, 2011*

* Compatibility with the latest Symantec API for Organization and Extended validation added.

### Version 1.1.4

*Released on Sep 8, 2011*

* Maintenance Release
* Multilanguage support added
* Automatic renewal functionality enabled
* “Activation Expiration” compatibility added for “$1.99 upgraded” Free PositiveSSL certs.
* Compatibility with New Namecheap API added
* “Tech Organization Name” field added to Technical Contact details
* Welcome/configuration email sending control functionality added

### Version 1.1.3

*Released on Aug 1, 2011*

* The list of available SSL Certificates is automatically synchronized with Namecheap.com
* Compatibility with the latest version of WHMCS (4.5.2) added
* Customization options for “Technical Contact Details” added
* SSL Certificate Validity Period configuration process changed. Now validity period is set based on the billing cycle

### Version 1.1.2

*Released on May 28, 2011*

* Bug Fix: Use existing SSL from account bug fixed.

### Version 1.1.0

*Released on Jan 21, 2011*

* Support for VeriSign Secure Site, VeriSign Secure Site Pro, VeriSign Secure Site EV, VeriSign Secure Site Pro EV, Geotrust TrueBusinessID and Geotrust TrueBusinessID WildCard certificates.

* Initial Release

### Version 1.0.0

*Released on Nov 07, 2010*

* Initial Release
