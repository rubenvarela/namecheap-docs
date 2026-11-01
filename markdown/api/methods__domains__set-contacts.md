<!-- source: https://www.namecheap.com/support/api/methods/domains/set-contacts/ | fetched: 2026-11-01T03:11:19Z -->

## namecheap.domains.setContacts

Sets contact information for the requested domain

### Example Requests

```
https://api.namecheap.com/xml.response?ApiUser=apisample&ApiKey=a0936a701e8b4789820301235080105&UserName=apisample&Command=namecheap.domains.setContacts&ClientIp=192.168.1.109&DomainName=domain1.com&AuxBillingFirstName=Daisy&AuxBillingLastName=Smith&AuxBillingAddress1=8939%20S.cross%20Blvd&AuxBillingCity=califonia&AuxBillingOrganizationName=Org1&AuxBillingStateProvince=CA&AuxBillingPostalCode=90045&AuxBillingCountry=US&AuxBillingPhone=+1.6613102107&AuxBillingEmailAddress=john@gmail.com&TechFirstName=Daisy&TechLastName=Smith&TechAddress1=8939%20S.cross%20Blvd&TechStateProvince=CA&TechCity=california&TechPostalCode=90045&TechOrganizationName=Org1&TechCountry=US&TechPhone=+1.6613102107&TechEmailAddress=john@gmail.com&AdminFirstName=Daisy&AdminLastName=Smith&AdminAddress1=8939%20S.cross%20Blvd&AdminStateProvince=CA&AdminPostalCode=90045&AdminOrganizationName=org1&AdminCountry=US&AdminPhone=+1.6613102107&AdminCity=california&AdminEmailAddress=john@gmail.com&RegistrantFirstName=Daisy&RegistrantLastName=Smith&RegistrantAddress1=8939%20S.cross%20Blvd&RegistrantStateProvince=CA&RegistrantPostalCode=90045&RegistrantCountry=US&RegistrantPhone=+1.6613102107&RegistrantEmailAddress=john@gmail.com&RegistrantCity=california&RegistrantOrganizationName=Org1
```

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.setContacts&ClientIp=192.168.1.109&DomainName=domain1.us&AuxBillingFirstName=Dan&AuxBillingLastName=Smith&AuxBillingAddress1=8939%20S.cross%20Bl&AuxBillingStateProvince=CA&AuxBillingPostalCode=90045&AuxBillingCountry=US&AuxBillingPhone=+1.6613102107&AuxBillingEmailAddress=john@gmail.com&AuxBillingOrganizationName=NC&AuxBillingCity=California&TechFirstName=John&TechLastName=Smith&TechAddress1=8939%20S.cross%20Bl&TechStateProvince=CA&TechPostalCode=90045&TechCountry=US&TechPhone=+1.6613102107&TechEmailAddress=john@gmail.com&TechOrganizationName=NC&TechCity=California&AdminFirstName=John&AdminLastName=Smith&AdminAddress1=8939%20S.cross%20Blvd&AdminStateProvince=CA&AdminPostalCode=9009&AdminCountry=US&AdminPhone=+1.6613102107&AdminEmailAddress=john@gmail.com&AdminOrganizationName=NC&AdminCity=California&RegistrantFirstName=John&RegistrantLastName=Smith&RegistrantAddress1=8939%20S.cross%20Blvd&RegistrantStateProvince=CS&RegistrantPostalCode=90045&RegistrantCountry=US&RegistrantPhone=+1.6613102107&RegistrantEmailAddress=jo@gmail.com&RegistrantOrganizationName=NC&RegistrantCity=California&RegistrantNexus=C11&RegistrantNexusCountry=In&RegistrantPurpose=P1
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be present in ***all*** requests.

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| DomainName | String | 70 | Yes | The domain name to register |
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
| Extended attributes | String | No | Yes | Required for [.us, .eu, .ca, .co.uk, .org.uk, .me.uk, .nu , .asia, .com.au, .net.au, .org.au, .es, .nom.es, .com.es, .org.es, .de, .fr](extended-attributes.md) TLDs only |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.setContacts</RequestedCommand>
  <CommandResponse Type="namecheap.domains.setContacts">
    <DomainSetContactResult Domain="domain1.com" IsSuccess="true" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>0.078</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | The registered domain name |
| IsSuccess | Indicates whether contact details were set successfully |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2019166 | Domain not found |
| 2030166 | Edit permission for domain is not supported |
| 2010324 | Registrant contacts such as firstname, lastname etc. are missing |
| 2010325 | Tech contacts such as firstname, lastname etc. are missing |
| 2010326 | Admin contacts such as firstname, lastname etc. are missing |
| 2015182 | The contact phone is invalid. The phone number format is +NNN.NNNNNNNNNN |
| 2010327 | AuxBilling contacts such as firstname, lastname etc. are missing |
| 2016166 | Domain is not associated with your account |
| 2011280 | Cannot see the contact information for your TLD |
| 4022323 | Error retrieving domain Contacts |
| 2011323 | Error retrieving domain Contacts from Enom (invalid errors) |
| 3031510 | Error from Enom when error count <>0 |
| 3050900 | Unknown error from Enom |
