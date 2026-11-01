<!-- source: https://www.namecheap.com/support/api/methods/ | fetched: 2026-11-01T03:17:27Z -->

# API Methods

**NOTE:** These methods work only for the **domains registered with Namecheap** that are **currently present in your Namecheap account**.

### domains

* [getList](methods__domains__get-list.md) — Returns a list of domains for the particular user.
* [getContacts](methods__domains__get-contacts.md) — Gets contact information of the requested domain.
* [create](methods__domains__create.md) — Registers a new domain name.
* [getTldList](methods__domains__get-tld-list.md) — Returns a list of tlds
* [setContacts](methods__domains__set-contacts.md) — Sets contact information for the domain.
* [check](methods__domains__check.md) — Checks the availability of domains.
* [reactivate](methods__domains__reactivate.md) — Reactivates an expired domain.
* [renew](methods__domains__renew.md) — Renews an expiring domain.
* [getRegistrarLock](methods__domains__get-registrar-lock.md) — Gets the RegistrarLock status of the requested domain.
* [setRegistrarLock](methods__domains__set-registrar-lock.md) — Sets the RegistrarLock status for a domain.
* [getInfo](methods__domains__get-info.md) — Returns information about the requested domain.

### domains.dns

* [setDefault](methods__domains-dns__set-default.md) — Sets domain to use our default DNS servers. Required for free services like Host record management, URL forwarding, email forwarding, dynamic dns and other value added services.
* [setCustom](methods__domains-dns__set-custom.md) — Sets domain to use custom DNS servers. NOTE: Services like URL forwarding, Email forwarding, Dynamic DNS will not work for domains using custom nameservers.
* [getList](methods__domains-dns__get-list.md) — Gets a list of DNS servers associated with the requested domain.
* [getHosts](methods__domains-dns__get-hosts.md) — Retrieves DNS host record settings for the requested domain.
* [getEmailForwarding](methods__domains-dns__get-email-forwarding.md) — Gets email forwarding settings for the requested domain
* [setEmailForwarding](methods__domains-dns__set-email-forwarding.md) — Sets email forwarding for a domain name.
* [setHosts](methods__domains-dns__set-hosts.md) — Sets DNS host records settings for the requested domain.

### domains.ns

* [create](methods__domains-ns__create.md) — Creates a new nameserver.
* [delete](methods__domains-ns__delete.md) — Deletes a nameserver associated with the requested domain.
* [getInfo](methods__domains-ns__getinfo.md) — Retrieves information about a registered nameserver.
* [update](methods__domains-ns__update.md) — Updates the IP address of a registered nameserver.

### domains.transfer

* [create](methods__domains-transfer__create.md) — Transfers a domain to Namecheap. You can only transfer .biz, .ca, .cc, .co, .co.uk, .com, .com.es, .com.pe, .es, .in, .info, .me, .me.uk, .mobi, .net, .net.pe, .nom.es, .org, .org.es, .org.pe, .org.uk, .pe, .tv, .us domains through API at this time.
* [getStatus](methods__domains-transfer__get-status.md) — Gets the status of a particular transfer.
* [updateStatus](methods__domains-transfer__update-status.md) — Updates the status of a particular transfer. Allows you to re-submit the transfer after releasing the registry lock.
* [getList](methods__domains-transfer__get-list.md) — Gets the list of domain transfers.

### ssl

* [create](methods__ssl__create.md) — Creates a new SSL certificate.
* [getList](methods__ssl__get-list.md) — Returns a list of SSL certificates for the particular user.
* [parseCSR](methods__ssl__parse-csr.md) — Parsers the CSR
* [getApproverEmailList](methods__ssl__get-approver-email-list.md) — Gets approver email list for the requested certificate.
* [activate](methods__ssl__activate.md) — Activates a newly purchased SSL certificate.
* [resendApproverEmail](methods__ssl__resend-approver-email.md) — Resends the approver email.
* [getInfo](methods__ssl__get-info.md) — Retrieves information about the requested SSL certificate
* [renew](methods__ssl__renew.md) — Renews an SSL certificate.
* [reissue](methods__ssl__reissue.md) — Reissues an SSL certificate.
* [resendfulfillmentemail](methods__ssl__resend-fulfillment-email.md) — Resends the fulfilment email containing the certificate.
* [purchasemoresans](methods__ssl__purchasemoresans.md) — Purchases more add-on domains for already purchased certificate.
* [revokecertificate](methods__ssl__revokecertificate.md) — Revokes a re-issued SSL certificate.
* [editDCVMethod](methods__ssl__editdcvmethod.md) — Sets new domain control validation (DCV) method for a certificate or serves as 'retry' mechanism

### users

* [getPricing](methods__users__get-pricing.md) — Returns pricing information for a requested product type.
* [getBalances](methods__users__get-balances.md) — Gets information about fund in the user's account.This method returns the following information: Available Balance, Account Balance, Earned Amount, Withdrawable Amount and Funds Required for AutoRenew.
* [changePassword](methods__users__change-password.md) — Changes password of the particular user's account.
* [update](methods__users__update.md) — Updates user account information for the particular user.
* [createaddfundsrequest](methods__users__create-add-funds-request.md) — Creates a request to add funds through a credit card
* [getAddFundsStatus](methods__users__get-add-funds-status.md) — Gets the status of add funds request.
* [create](methods__users__create.md) — Creates a new account at NameCheap under this ApiUser.
* [login](methods__users__login.md) — Validates the username and password of user accounts you have created using the API command namecheap.users.create.
* [resetPassword](methods__users__reset-password.md) — When you call this API, a link to reset password will be emailed to the end user's profile email id.The end user needs to click on the link to reset password.

### users.address

* [create](methods__users-address__create.md) — Creates a new address for the user
* [delete](methods__users-address__delete.md) — Deletes the particular address for the user.
* [getInfo](methods__users-address__get-info.md) — Gets information for the requested addressID.
* [getList](methods__users-address__get-list.md) — Gets a list of addressIDs and addressnames associated with the user account.
* [setDefault](methods__users-address__set-default.md) — Sets default address for the user.
* [update](methods__users-address__update.md) — Updates the particular address of the user

### domainprivacy

* [changeemailaddress](methods__domainprivacy__change-email-address.md) — Changes domain privacy email address
* [enable](methods__domainprivacy__enable.md) — Enables domain privacy protection.
* [disable](methods__domainprivacy__disable.md) — Disables domain privacy protection.
* [getList](methods__domainprivacy__getlist.md) — Gets the list of domain privacy protection.
* [renew](methods__domainprivacy__renew.md) — Renews domain privacy protection.
