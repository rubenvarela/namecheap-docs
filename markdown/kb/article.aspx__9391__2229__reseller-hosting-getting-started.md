<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9391/2229/reseller-hosting-getting-started/ | fetched: 2026-11-01T03:36:01Z -->

# Reseller Hosting

In this article, you will find all the basic information on where to start from with our [Reseller Hosting Service](https://www.namecheap.com/hosting/reseller/).
The following items are to be explained here:

[1. Package Information](#packageinfo)

* [Welcome Guide Email](#Welcome)
* [Email with Addons](#Email)

[2. Preparing the Domain Name](#dnprep)

* [How to manage Personal Nameservers](#Manage)

[3. Preparing the Reseller Account. Description of WHM main functions](#raprep)

* [How to create a new package in WHM](#package)
* [How to use Feature Manager in WHM](#Feature)
* [How to create a new cPanel Account in WHM](#Account)
* [How to change a password/contact email address for a cPanel account in WHM](#password)
* [How to change a package for a particular cPanel account in WHM](#change)
* [How to edit Resource Limits in WHM](#Resource)
* [How to edit DNS Zone of a particular Domain Name in WHM](#Zone)

[4. WHMCS Billing Platform](#whmcs)

* [How to install WHMCS](#install)
* [Namecheap Domain Registration module in WHMCS](#Domain)

- [Module Configuration](#module)

- [General Settings](#General)

- [Debug Mode](#Debug)

* [Namecheap SSL Certificates module in WHMCS](#SSL)

 **### Package information**
**Welcome Guide Email**

Once your Reseller Hosting account is activated, you will receive a Welcome Guide Email containing the information about your hosting package, including WHM/cPanel access details, Addons, FTP details and other important references.

**Email with Addons**

If you choose some additional services for your hosting account, or in case some of them are included into the package already like SSL Certificate or Private Nameservers, you will receive an additional email message containing the detailed information about them, for example, IP addresses for Private Nameservers, etc.
 **NOTE**: A number of Addons may vary depending on the type of the Reseller package you choose. You can check available Reseller Hosting packages
[here](https://www.namecheap.com/hosting/reseller/). To view full technical specification of the package, click on the Tech Specs tab at the bottom of the page.

**### Preparing the Domain Name**Once the hosting account is active, you will need to point the domain name to our nameservers or Personal Nameservers if such are included in the package. You will find nameservers in the Welcome Guide email after the package activation.
**How to Manage Personal Nameservers**

If you have Personal Nameservers included in your hosting package, you will need to register and set them on the side of your Domain Name Registrar.

In case the domain name is registered with Namecheap, use [this tutorial](https://www.namecheap.com/support/knowledgebase/article.aspx/768/10/how-do-i-register-personal-nameservers-for-my-domain) to create Personal Nameservers.

**NOTE**: IP Addresses for Personal Nameservers are also provided in the Welcome Guide Email.

 
Once registered, you can set them for your Namecheap domain following the guide [here](https://www.namecheap.com/support/knowledgebase/article.aspx/767/10/how-can-i-change-the-nameservers-for-my-domain).

### **Preparing the Reseller Account. Description of WHM main functions**

Once you receive the Welcome Guide email and get access to WHM, you can start learning WHM basics and get a few things done. Find the description of main WHM functions below.

**How to create new packages in WHM**

A
[hosting package](https://documentation.cpanel.net/display/78Docs/Add+a+Package)
is simply a set of functions, limitations, and resources each cPanel account may have within a Reseller Hosting Account. Basically, having different packages with a different set of functions and limitations allows providing a range of hosting accounts based on particular features.

**NOTE**: It is recommended to configure a hosting package prior to creating a new cPanel account in WHM to simplify further cPanel accounts management process.

To create a new package in WHM, you will need to do the following:

1. Log into WHM using http://domain.com/whm or https://hostname\_server/whm.
2. Navigate to the **Add a Package** menu in the section **Packages**.
3. Set appropriate quotas in the **Resources** section.

4. Choose required settings for the package in **Settings**, including Feature List.

5. Click on the **Add** button:

**How to use Feature Manager in WHM**

[Feature Manager](https://docs.cpanel.net/whm/packages/feature-manager) is an interface that allows creating a list of features that will be available for particular cPanel accounts.

In order to create a specific Feature List, do the following:

1. In WHM navigate to the **Feature Manager** menu in the section **Packages**.
2. Type in the name of the list you wish to create next to the **Feature List Name** field and click on the **Add Feature List** button:

3. Once done, choose the newly created list from the drop-down menu next to the **Edit a Feature List** field and click on the **Edit** button:

4. You will be forwarded to the list of features available on our server. Simply pick up the required ones and click on **Save** at the bottom of the page.

**How to create new cPanel Account in WHM**

In order to create a fresh cPanel account in WHM you need to do the following:

1. In WHM navigate to the **Create a New Account** menu in **Account Functions**.
2. Fill in the gaps and choose appropriate settings in the following sections:

* Domain Information
* Package
  Settings
* DNS Settings
* Mail Routing Settings

3. Click on the **Create** button:

**How to change a password/contact email address for a cPanel account in WHM**

If you need to change a password or a contact email address for a particular cPanel account, you can do this in the following way:

1. Navigate to the **List Accounts** menu.

2. Click on **'+'** next to the cPanel account you need to change the information for.
3. Change the password or email account in corresponding fields and confirm by clicking on **Change**:

**How to change a package for a particular cPanel account in WHM**

In order to change a package for a cPanel account you will need to do the following:

1. Navigate to the **Upgrade/Downgrade an Account** menu.
2. Choose the account you wish to upgrade/downgrade in **Account Selection** and click on the **Modify** button:

3. In the next windows you will need to choose the required package from the **Available Packages** list and click on the **Upgrade/Downgrade** button:

**How to edit Resource Limits in WHM**

Resource Limits is a WHM function that allows allocating available system resources to cPanel users. It may be useful in order to prevent some accounts from overusing server resources.

Apart from resource limits stipulated by a package, it is possible to adjust the limits for a cPanel account particularly. This can be done in the following way:

1. In WHM navigate to the **Modify an Account** menu.
2. Choose the account you wish to adjust the limits for in the **Account Selection** field and click on the **Modify** button.
3. You will be forwarded to the account modification window, and specific resources can be adjusted in the **Resource Limits** section accordingly.

**How to edit DNS Zone of a particular Domain Name in WHM**

A DNS Zone is an administrative portion of DNS settings that belongs to a domain name.
In other words, every domain name has certain DNS settings and in order to keep them all together, a DNS Zone file was designed. A DNS Zone can be easily edited via WHM >> DNS Zone Manager menu.

To edit DNS Zone, follow the steps below:

1. In WHM navigate to the **DNS Zone Manager** menu on the left-side bar.

2. Choose the account you wish to adjust the settings for in the **Domains** list and click on the **Manage** button:

3. You will be forwarded to the DNS settings modification window where different DNS records types including A, CNAME, TXT, SOA, NS, MX, etc. can be adjusted accordingly.

More details on this tool can be found
[here](https://docs.cpanel.net/whm/dns-functions/dns-zone-manager).

### **WHMCS billing platform**

[WHMCS](https://www.whmcs.com/) is an all-in-one client management, billing and support system with set-valued
[features](https://www.whmcs.com/features/feature-list/)
designed specifically for online businesses.
Before the installation and configuration process, you can check out the WHMCS demo
[here](https://demo.whmcsadmintheme.com/admin/login.php).

**How to install WHMCS**

We highly recommend using the Softaculous script-installer as it is the easiest and the most convenient way to install the WHMCS Billing platform in a few clicks. Furthermore, Softaculous is included in a Reseller Hosting Account by default and is integrated into cPanel.

Feel free to check our video tutorial that explains how to install WHMCS using the Softaculous script installer
[here](https://www.namecheap.com/support/knowledgebase/article.aspx/1317/81/how-to-install-whmcs-from-softaculous).

**Namecheap Domain Registration module in WHMCS**
Namecheap.com WHMCS Registrar module is an open-source plugin provided free of charge. It was specifically designed with the purpose of integrating Namecheap as a Domain Registrar into the WHMCS platform.

**NOTE**: You can alternatively use the built-in Namecheap Registrar module in WHMCS. However, we highly recommend using our own module due to constant updates, implementation of new features and advanced functionality.

You can download the plugin right
[here](https://github.com/namecheap/domains-whmcs)
and install it following the instructions provided on the same page.

**Module Configuration**

To access module configuration settings, follow the steps below:

1. Log into WHMCS Admin panel
2. Navigate to **Setup >> Products/Services >> Domain Registrars** menu:

3. In the list of Domain Registrars available, find Namecheap and click on the **Configure** button. You need to indicate the following information there:

* **Username:** your Namecheap username
* **Password:** Namecheap API key. To get it, you need to log into Namecheap Account, mouse over your Namecheap username >> Manage Profile >> API Access menu
* **PromotionCode:** here you can use the Domain Registration Promo Code. Available promo codes can be checked
  [here](https://www.namecheap.com/promos/coupons/)

**NOTE:** In order to have API enabled for your account, you should meet one of the following requirements:

* have at least 20 domains under your account
* have at least $50 on your account balance
* have at least $50 spent within the last 2 years

Still, you are free to test our API through the Sandbox environment at www.sandbox.namecheap.com

It is also possible to run WHMCS in a test mode. This is useful to test how the configured system will work prior to making it available for the public. For this, you may register a Sandbox account and get corresponding access details [here](https://www.sandbox.namecheap.com/).

* **SandboxUsername:** your Sandbox Username
* **SandboxPassword:** Sandbox API key. Sandbox API Key can be retrieved in the same way as the Namecheap API key right
  [here](https://www.sandbox.namecheap.com/)
* **TestMode:**
  By choosing this option, all the APIs will be forwarded to the Sandbox environment using the corresponding Sandbox Credentials
* **DebugMode:** This option allows identifying and investigating issues with remote API systems. It will make a record of all the API calls sent to the Registrar and all the responses sent back

**General Settings**

General Settings of the module are available in **WHMCS Admin** panel >> **Setup** >> **General Settings** menu >> **Domains** tab:

Here you can adjust different Domain-related settings to make the domain registration process even more comfortable for your customers:

* **Enable Renewal Orders** - this option allows domain renewals from the WHMCS client’s area
* **Auto Renew on Payment** - with these settings enabled, the system will automatically renew domain names in WHMCS after the payment is processed
* **Auto Renew Requires Product** - only free domains with the corresponding active service (hosting account, email subscription, etc.) will be auto-renewed
* **Default Auto Renewal Setting** - this option will auto-generate invoices for expiring domain names. This also can be adjusted for every domain name particularly in **Clients** >> **Domain Registrations** >> choose the domain name >> select **Disable Auto Renew** setting
* **Domain Sync Enabled** - enables automated synchronization with the Domain Registrar
* **Domain Sync Notify Only** - the synchronization with the Domain Registrar will not be performed automatically; email notifications will be sent to Admin instead
* **Allow IDN Domains** - this setting will disable A-Z; 0-9 cross-check character validation for domain names entered via the WHMCS client area
* **Bulk Check TLDs** - this option includes TLDs that you want to check in addition to the TLD the client selects during the order
* **Use Clients Details** - this setting allows specifying the details/information that will be publicly displayed during WHOIS lookup for the domains registered through WHMCS

More information on additional options can be found
[here](http://docs.whmcs.com/Configuration).

**Domain Sync Mode**

Domain Sync Mode allows setting up synchronization between WHMCS module and Domain Name Registrar to keep all the domain-related information up-to-date. This includes any domain name status changes, renewals, expiration dates, etc.

To enable this feature, simply navigate to **Setup >> General Settings >> Domains** and check **the Domain Sync Enabled** option:

Once this is done, you will need to set up a Cron Job which will be responsible for synchronization in a Reseller’s cPanel account. To do this, simply follow the steps below:

1. Log into the Reseller’s cPanel account: *http://domain.com/cpanel* or *https://hostname\_server/cpanel*.

2. Click on the **Cron Jobs** menu under the **Advanced** section:

3. In the **Common Settings** section choose the **Once a week option** and insert the following string into the **Command** field:

*/usr/bin/php /home/cpanel\_username/public\_html/path\_to\_WHMCS/crons/domainsync.php*

**NOTE:** Make sure that you replace the 'cpanel\_username' part with your actual cPanel username provided in the Welcome Guide email and 'path\_to\_WHMCS' with the actual path to your WHMCS installation.

The sync mode is configured now and all the domain-related information will be synchronized with the WHMCS system.

**Debug Mode**

The Debug Mode feature allows identifying and investigating any issues with API systems, recording and displaying output results of all the API calls sent to the Registrar and all the responses received back.

**NOTE:** It is highly recommended to enable Debug Mode only in case of any issues with Module behavior. Make sure that you have not enabled it permanently as it will result in massive log archives on the server side which will take a good part of disk space.

To enable Debug Mode, go to **Setup >> Products/Services >> Domain Registrars**:

Next to Namecheap, click on the **Configure** button and select the **DebugMode** option there. Then click on **Save Changes** to confirm:

In order to enable/disable debug logging and view the logs, you will need to open **Utilities >> Logs >> Module Log** menu:

You will find the **Enable/Disable Debug Logging** and **Reset Debug Module Log** buttons there:

All the API calls will be listed in the **Request** field and all the responses from the remote system can be found in the **Response** field correspondingly.

**Namecheap SSL Certificates module in WHMCS**

Namecheap.com WHMCS SSL Certificates plugin is an open-source plugin that is provided free of charge. The module is fully integrated with Namecheap, and it completely interacts with our API, which allows automating and managing SSL sales with Namecheap in full.

We have a corresponding KnowledgeBase category dedicated to the module’s general information and configuration settings
[here](https://www.namecheap.com/support/knowledgebase/category.aspx/2196/whmcs-module-for-ssl).
To have quick access to any required section, use the navigation list below:

1.
[Before you begin](article.aspx__9261__2196__1-before-you-begin.md)
2. [Sandbox and Production environments](article.aspx__9262__2196__2-sandbox-and-production-environments.md)
3.
[Download and installation](article.aspx__9270__2196__3-download-and-installation.md)
4. [Setting up products and pricing](article.aspx__9264__2196__4-setting-up-products-and-pricing.md)
5.
[Order process and welcome emails in WHMCS](article.aspx__9265__2196__5-order-process-and-welcome-emails-in-whmcs.md)
6. [SSL activation from WHMCS](article.aspx__9266__2196__6-activation-of-ssl-from-whmcs.md)
7. [Reissue, renewal and synchronization](article.aspx__9268__2196__7-reissue-renewal-and-synchronization.md)
8. [Debugging and addon functions](article.aspx__9267__2196__8-debugging-and-addon-functions.md)
9. [Multi-domain certificates](article.aspx__9299__2196__9-multidomain-certificates.md)
10. [FAQs](article.aspx__9269__2196__10-faqs.md)

Need any help? Contact our [Helpdesk](https://www.namecheap.com/help-center/)
