<!-- source: https://www.namecheap.com/support/api/methods/users-address/update/ | fetched: 2026-11-01T03:16:12Z -->

### namecheap.users.address.update

Updates the particular address of the user

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiuser&Command=namecheap.users.address.update&ClientIp=192.168.1.109&AddressId=48&AddressName=address_test&EmailAddress=apidemo@gmail.com&FirstName=John&LastName=Smith&JobTitle=software%20developer&Organization=NC&Address1=High%20Street&City=California&Zip=90045&Country=US&Phone=+1.6613102107&Fax=+1.6613102107&StateProvince=CA&StateProvinceChoice=P
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| AddressId | Number | 20 | Yes | The unique address ID to update |
| AddressName | String | 20 | Yes | The AddressName to update |
| *DefaultYN* | Number | 128 | *No* | Possible values are 0 and 1. If the value of this parameter is set to 1, the updated address is also set as default address for the user. |
| EmailAddress | String | 128 | Yes | Email address of the user |
| FirstName | String | 60 | Yes | First name of the user |
| LastName | String | 60 | Yes | Last name of the user |
| *JobTitle* | String | 60 | *No* | Job designation of the user |
| *Organization* | String | 60 | *No* | Organization of the user |
| Address1 | String | 60 | Yes | StreetAddress1 of the user |
| *Address2* | String | 60 | *No* | StreetAddress2 of the user |
| City | String | 60 | Yes | City of the user |
| StateProvince | String | 60 | Yes | State/Province of the user |
| StateProvinceChoice | String | 60 | Yes | State/Province choice of the user |
| Zip | String | 15 | Yes | Zip/Postal code of the user |
| Country | String | 2 | Yes | Two letter country code of the user |
| Phone | String | 20 | Yes | Phone number in the format +NNN.NNNNNNNNNN |
| *PhoneExt* | String | 10 | *No* | PhoneExt of the user |
| *Fax* | String | 20 | *No* | Fax number in the format +NNN.NNNNNNNNNN |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.users.address.update</RequestedCommand>
  <CommandResponse Type="namecheap.users.address.update">
    <AddressUpdateResult Success="true" AddressId="48" AddressName="address_test" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>0.047</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Success | Indicates whether the default address was updated successfully. |
| AddressID | A unique integer value that represents the address profile |
| AddressName | The name of the address profile |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 4011331 | StatusCode for update is invalid |
| 4024336 | Failed to update user's address |
| 2015182 | The contact phone is invalid. The phone number format is +NNN.NNNNNNNNNN |
