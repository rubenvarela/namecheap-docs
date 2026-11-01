<!-- source: https://www.namecheap.com/support/api/methods/users/update/ | fetched: 2026-11-01T03:15:14Z -->

## namecheap.users.update

Updates user account information for the particular user.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiuser&Command=namecheap.users.update&ClientIp=192.168.1.109&JobTitle=software%20tester&FirstName=yourfirstname&LastName=yourlastname&Organization=NC&Address1=8939%High%20Street&City=CA&StateProvince=CA&Zip=90045&Country=US&EmailAddress=abc@apiexample.com&Phone=+1.6613102107&Fax=+1.6613102107
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| FirstName | String | 70 | Yes | First name of the user |
| LastName | String | 70 | Yes | Last name of the user |
| *JobTitle* | String | 60 | *No* | Job designation of the user |
| *Organization* | String | 60 | *No* | Organization of the user |
| Address1 | String | 60 | Yes | StreetAddress1 of the user |
| *Address2* | String | 60 | *No* | StreetAddress2 of the user |
| City | String | 60 | Yes | City of the user |
| StateProvince | String | 60 | Yes | State/Province of the user |
| Zip | String | 15 | Yes | Zip/Postal code of the user |
| Country | String | 2 | Yes | Two letter country code of the user |
| EmailAddress | String | 255 | Yes | Email address of the user |
| Phone | String | 20 | Yes | Phone number in the format +NNN.NNNNNNNNNN |
| *PhoneExt* | String | 10 | *No* | PhoneExt of the user |
| *Fax* | String | 20 | *No* | Fax number in the format +NNN.NNNNNNNNNN |

### Example Response

```
<?xml version="1.0" encoding="utf-8"?>
<ApiResponse Status="OK" xmlns="http://api.namecheap.com/xml.response">
  <Errors/>
  <RequestedCommand>namecheap.users.update</RequestedCommand>
  <CommandResponse Type="namecheap.users.update">
   <UserUpdateResult Success="true" UserId="123" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5:30</GMTTimeDifference>
  <ExecutionTime>0</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Success | Indicates if the password was updated successfully |
| UserID | A unique integer value that represents the username |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 4011331 | StatusCode for update is invalid |
| 4024103 | Failed to update user |
| 2015182 | The contact phone is invalid. The phone number format is +NNN.NNNNNNNNNN |
