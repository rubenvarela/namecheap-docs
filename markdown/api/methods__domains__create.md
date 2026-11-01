<!-- source: https://www.namecheap.com/support/api/methods/domains/create/ | fetched: 2026-11-01T03:11:09Z -->

**IMPORTANT:**  Our privacy service provider recently changed to `WithheldforPrivacy`. We want to avoid service interruption for our API users, so please note that in some cases, you may still see `Whoisguard` in the API parameter names.

**UPDATE:** Free PositiveSSL is no longer supported. Please do not send the `AddFreePositiveSSL` parameter.

## namecheap.domains.create

Registers a new domain

###### Important

* We recommend using the `HTTP POST` method for this command.
* For successful registration of an IDN domain, you need to send the `IdnCode` parameter and provide the domain name in the Punycode format (Example: xn--sdkhjsdhfkdh.com), as we do not support native code.

### Example Requests

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.create&ClientIp=192.168.1.109&DomainName=aa.us.com&Years=1&AuxBillingFirstName=John&AuxBillingLastName=Smith&AuxBillingAddress1=8939%20S.cross%20Blv&AuxBillingStateProvince=CA&AuxBillingPostalCode=90045&AuxBillingCountry=US&AuxBillingPhone=+1.6613102107&AuxBillingEmailAddress=john@gmail.com&AuxBillingOrganizationName=NC&AuxBillingCity=CA&TechFirstName=John&TechLastName=Smith&TechAddress1=8939%20S.cross%20Blvd&TechStateProvince=CA&TechPostalCode=90045&TechCountry=US&TechPhone=+1.6613102107&TechEmailAddress=john@gmail.com&TechOrganizationName=NC&TechCity=CA&AdminFirstName=John&AdminLastName=Smith&AdminAddress1=8939%cross%20Blvd&AdminStateProvince=CA&AdminPostalCode=9004&AdminCountry=US&AdminPhone=+1.6613102107&AdminEmailAddress=joe@gmail.com&AdminOrganizationName=NC&AdminCity=CA&RegistrantFirstName=John&RegistrantLastName=Smith&RegistrantAddress1=8939%20S.cross%20Blvd&RegistrantStateProvince=CS&RegistrantPostalCode=90045&RegistrantCountry=US&RegistrantPhone=+1.6613102107&RegistrantEmailAddress=jo@gmail.com&RegistrantOrganizationName=NC&RegistrantCity=CA&AddFreeWhoisguard=no&WGEnabled=no&GenerateAdminOrderRefId=False&IsPremiumDomain=True&PremiumPrice=206.7&EapFee=0
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be
present in ***all*** requests.

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| DomainName | String | 70 | Yes | Domain name to register |
| Years | Number | 2 | Yes | Number of years to register  **Default Value:** 2 |
| *PromotionCode* | String | 20 | *No* | Promotional (coupon) code for the domain |
| *RegistrantOrganizationName* | String | 255 | *No* | Organization of the Registrant user |
| *RegistrantJobTitle* | String | 255 | *No* | Job title of the Registrant user |
| RegistrantFirstName | String | 255 | Yes | First name of the Registrant user |
| RegistrantLastName | String | 255 | Yes | Second name of the Registrant user |
| RegistrantAddress1 | String | 255 | Yes | Address1 of the Registrant user |
| *RegistrantAddress2* | String | 255 | *No* | Address2 of the Registrant user |
| RegistrantCity | String | 50 | Yes | City of the Registrant user |
| RegistrantStateProvince | String | 50 | Yes | State/Province of the Registrant user |
| *RegistrantStateProvinceChoice* | String | 50 | *No* | StateProvinceChoice of the Registrant user |
| RegistrantPostalCode | String | 50 | Yes | PostalCode of the Registrant user |
| RegistrantCountry | String | 50 | Yes | Country of the Registrant user |
| RegistrantPhone | String | 50 | Yes | Phone number in the format +NNN.NNNNNNNNNN |
| *RegistrantPhoneExt* | String | 50 | *No* | PhoneExt of the Registrant user |
| *RegistrantFax* | String | 50 | *No* | Fax number in the format +NNN.NNNNNNNNNN |
| RegistrantEmailAddress | String | 255 | Yes | Email address of the Registrant user |
| *TechOrganizationName* | String | 255 | *No* | Organization of the Tech user |
| *TechJobTitle* | String | 255 | *No* | Job title of the Tech user |
| TechFirstName | String | 255 | Yes | First name of the Tech user |
| TechLastName | String | 255 | Yes | Second name of the Tech user |
| TechAddress1 | String | 255 | Yes | Address1 of the Tech user |
| *TechAddress2* | String | 255 | *No* | Address2 of the Tech user |
| TechCity | String | 50 | Yes | City of the Tech user |
| TechStateProvince | String | 50 | Yes | State/Province of the Tech user |
| *TechStateProvinceChoice* | String | 50 | *No* | StateProvinceChoice of the Tech user |
| TechPostalCode | String | 50 | Yes | PostalCode of the Tech user |
| TechCountry | String | 50 | Yes | Country of the Tech user |
| TechPhone | String | 50 | Yes | Phone number in the format +NNN.NNNNNNNNNN |
| *TechPhoneExt* | String | 50 | *No* | PhoneExt of the Tech user |
| *TechFax* | String | 50 | *No* | Fax number in the format +NNN.NNNNNNNNNN |
| TechEmailAddress | String | 255 | Yes | Email address of the Tech user |
| *AdminOrganizationName* | String | 255 | *No* | Organization of the Admin user |
| *AdminJobTitle* | String | 255 | *No* | Job title of the Admin user |
| AdminFirstName | String | 255 | Yes | First name of the Admin user |
| AdminLastName | String | 255 | Yes | Second name of the Admin user |
| AdminAddress1 | String | 255 | Yes | Address1 of the Admin user |
| *AdminAddress2* | String | 255 | *No* | Address2 of the Admin user |
| AdminCity | String | 50 | Yes | City of the Admin user |
| AdminStateProvince | String | 50 | Yes | State/Province of the Admin user |
| *AdminStateProvinceChoice* | String | 50 | *No* | StateProvinceChoice of the Admin user |
| AdminPostalCode | String | 50 | Yes | PostalCode of the Admin user |
| AdminCountry | String | 50 | Yes | Country of the Admin user |
| AdminPhone | String | 50 | Yes | Phone number in the format +NNN.NNNNNNNNNN |
| *AdminPhoneExt* | String | 50 | *No* | PhoneExt of the Admin user |
| *AdminFax* | String | 50 | *No* | Fax number in the format +NNN.NNNNNNNNNN |
| AdminEmailAddress | String | 255 | Yes | Email address of the Admin user |
| *AuxBillingOrganizationName* | String | 255 | *No* | Organization of the AuxBilling user |
| *AuxBillingJobTitle* | String | 255 | *No* | Job title of the AuxBilling user |
| AuxBillingFirstName | String | 255 | Yes | First name of the AuxBilling user |
| AuxBillingLastName | String | 255 | Yes | Second name of the AuxBilling user |
| AuxBillingAddress1 | String | 255 | Yes | Address1 of the AuxBilling user |
| *AuxBillingAddress2* | String | 255 | *No* | Address2 of the AuxBilling user |
| AuxBillingCity | String | 50 | Yes | City of the AuxBilling user |
| AuxBillingStateProvince | String | 50 | Yes | State/Province of the AuxBilling user |
| *AuxBillingStateProvinceChoice* | String | 50 | *No* | StateProvinceChoice of the AuxBilling user |
| AuxBillingPostalCode | String | 50 | Yes | PostalCode of the AuxBilling user |
| AuxBillingCountry | String | 50 | Yes | Country of the AuxBilling user |
| AuxBillingPhone | String | 50 | Yes | Phone number in the format +NNN.NNNNNNNNNN |
| *AuxBillingPhoneExt* | String | 50 | *No* | PhoneExt of the AuxBilling user |
| *AuxBillingFax* | String | 50 | *No* | Fax number in the format +NNN.NNNNNNNNNN |
| AuxBillingEmailAddress | String | 255 | Yes | Email address of the AuxBilling user |
| *BillingFirstName* | String | 255 | *No* | First name of the Billing user |
| *BillingLastName* | String | 255 | *No* | Second name of the Billing user |
| *BillingAddress1* | String | 255 | *No* | Address1 of the Billing user |
| *BillingAddress2* | String | 255 | *No* | Address2 of the Billing user |
| *BillingCity* | String | 50 | *No* | City of the Billing user |
| *BillingStateProvince* | String | 50 | *No* | State/Province of the Billing user |
| *BillingStateProvinceChoice* | String | 50 | *No* | StateProvinceChoice of the Billing user |
| *BillingPostalCode* | String | 50 | *No* | PostalCode of the Billing user |
| *BillingCountry* | String | 50 | *No* | Country of the Billing user |
| *BillingPhone* | String | 50 | *No* | Phone number in the format +NNN.NNNNNNNNNN |
| *BillingPhoneExt* | String | 50 | *No* | PhoneExt of the Billing user |
| *BillingFax* | String | 50 | *No* | Fax number in the format +NNN.NNNNNNNNNN |
| *BillingEmailAddress* | String | 255 | *No* | Email address of the Billing user |
| *BillingTaxNumber* | String | 25 | *No* | Tax number of the Billing user |
| *IdnCode* | String | 100 | *No* | Code of Internationalized Domain Name (please refer to the note below) |
| Extended attributes | String | No | Yes | Required for [.us, .eu, .ca, .co.uk, .org.uk, .me.uk, .nu , .com.au, .net.au, .org.au, .es, .nom.es, .com.es, .org.es, .de, .fr](extended-attributes.md) TLDs only |
| *Nameservers* | String | No | *No* | Comma-separated list of custom nameservers to be associated with the domain name |
| *AddFreeWhoisguard* | String | 10 | *No* | Adds free domain privacy for the domain  **Default Value:** no |
| *WGEnabled* | String | 10 | *No* | Enables free domain privacy for the domain   **Default Value:** no |
| *IsPremiumDomain* | Boolean | 10 | *No* | Indication if the domain name is premium |
| *PremiumPrice* | Currency | 20 | *No* | Registration price for the premium domain |
| *EapFee* | Currency | 20 | *No* | Purchase fee for the premium domain during Early Access Program (EAP)\* |

\*Currently, Namecheap does not support registration of premium domains during EAP.

###### Possible values for the `IdnCode` parameter

afr, alb, ara, arg, arm, asm, ast, ave, awa, aze, bak, bal, ban, baq, bas, bel, ben, bho, bos, bul, bur, car, cat, che, chi, chv, cop, cos, cze, dan, div, doi, dut, eng, est, fao, fij, fin, fre, fry, geo, ger, gla, gle, gon, gre, guj, heb, hin, hun, inc, ind, inh, isl, ita, jav, jpn, kas, kaz, khm, kir, kor, kur, lao, lav, lit, ltz, mal, mkd, mlt, mol, mon, mri, msa, nep, nor, ori, oss, pan, per, pol, por, pus, raj, rum, rus, san, scr, sin, slo, slv, smo, snd, som, spa, srd, srp, swa, swe, syr, tam, tel, tgk, tha, tib, tur, ukr, urd, uzb, vie, wel, yid

### Example Response

```
<?xml version="1.0" encoding="utf-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
<Errors/>
<Warnings/>
<RequestedCommand>namecheap.domains.create</RequestedCommand>
<CommandResponse Type="namecheap.domains.create">
<DomainCreateResult Domain="aa.us.com" Registered="true" ChargedAmount="200.8700" DomainID="103877" OrderID="22158" TransactionID="51284" WhoisguardEnable="false" NonRealTimeDomain="false"/>
</CommandResponse>
<Server>NC-DEV07</Server>
<GMTTimeDifference>+2:59</GMTTimeDifference>
<ExecutionTime>29.914</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | Domain name that you are trying to register. |
| Registered | Possible responses: True, False. Indicates whether the domain was registered. |
| ChargedAmount | Total amount charged for registration. |
| DomainID | Unique integer value that represents the domain. |
| OrderID | Unique integer value that represents the order. |
| TransactionID | Unique integer value that represents the transaction. |
| WhoisguardEnable | Possible responses: True, False. Indicates whether domain privacy protection is enabled for the domain. |
| NonRealTimeDomain | Possible responses: True, False. Indicates whether the domain registration is instant (real-time) or not. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2033409 | Possibly a logical error at the authentication phase. The order chargeable for the Username is not found |
| 2033407, 2033270 | Cannot enable domain privacy when AddWhoisguard is set to NO |
| 2015182 | Contact phone is invalid. The phone number format is +NNN.NNNNNNNNNN |
| 2015267 | EUAgreeDelete option should not be set to NO |
| 2011170 | Validation error from PromotionCode |
| 2011280 | Validation error from TLD |
| 2015167 | Validation error from Years |
| 2030280 | TLD is not supported in API |
| 2011168 | Nameservers are not valid |
| 2011322 | Extended Attributes are not valid |
| 2010323 | Check the required field for billing domain contacts |
| 2528166 | Order creation failed |
| 3019166, 4019166 | Domain not available |
| 3031166 | Error while getting information from the provider |
| 3028166 | Error from Enom ( Errcount <> 0 ) |
| 3031900 | Unknown response from the provider |
| 4023271 | Error while adding a free PositiveSSL for the domain |
| 3031166 | Error while getting a domain status from Enom |
| 4023166 | Error while adding a domain |
| 5050900 | Unknown error while adding a domain to your account |
| 4026312 | Error in refunding funds |
| 5026900 | Unknown exceptions error while refunding funds |
| 2515610 | Prices do not match |
| 2515623 | Domain is premium while considered regular or is regular while considered premium |
| 2005 | Country name is not valid |
