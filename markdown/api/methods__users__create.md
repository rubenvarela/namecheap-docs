<!-- source: https://www.namecheap.com/support/api/methods/users/create/ | fetched: 2026-11-01T03:17:32Z -->

## namecheap.users.create

Creates a new account at NameCheap under this ApiUser.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiuser&Command=namecheap.users.create&ClientIp=192.168.1.109&newusername=user12&newuserpassword=newuser12&EmailAddress=apisample@gmail.com&FirstName=John&LastName=Pearl&AcceptTerms=1&AcceptNews=0&JobTitle=software%20developer&Organization=NC&Address1=8939%20S.%20cross%20Blvd&Address2=high%20street&City=California&StateProvince=CA&Zip=90045&Country=US&Phone=+1.6613102107&Fax=+1.6613102107
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| NewUserName | String | 20 | Yes | Username for the new user account |
| NewUserPassword | String | 20 | Yes | Password for the new user account |
| EmailAddress | String | 128 | Yes | Email address of the user |
| *IgnoreDuplicateEmailAddress* | String | 10 | *No* | By default, it ignores to check if the email address is already in use.   **Default Value:**  Yes |
| FirstName | String | 60 | Yes | First name of the user |
| LastName | String | 60 | Yes | Last name of the user |
| AcceptTerms | Number | 1 | Yes | Terms of agreement. The Value should be 1 for user account creation.   **Default Value:**  1 |
| *AcceptNews* | Number | 1 | *No* | Possible values are 0 and 1. Value should be 1 if the user wants to recieve newsletters else it should be 0. |
| *JobTitle* | String | 60 | *No* | Job designation of the user |
| *Organization* | String | 60 | *No* | Organization of the user |
| Address1 | String | 60 | Yes | StreetAddress1 of the user |
| *Address2* | String | 60 | *No* | StreetAddress2 of the user |
| City | String | 60 | Yes | City of the user |
| StateProvince | String | 60 | Yes | State/Province of the user |
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
  <RequestedCommand>namecheap.users.create</RequestedCommand>
  <CommandResponse Type="namecheap.users.create">
    <UserCreateResult Success="true" UserId="75" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>0.085</ExecutionTime>
</ApiResponse>
```

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2011153 | Email address is invalid |
| 2011163 | Phone is invalid |
| 2011165 | Fax is invalid |
| 2011151 | FirstName is invalid |
| 2011152 | LastName is invalid |
| 2011103 | UserName is invalid |
| 2033153 | Email address is already in use |
| 2015182 | The contact phone is invalid. The phone number format is +NNN.NNNNNNNNNN |
| 4011331 | StatusCode for create user is invalid |
| 4022103 | Failed to create user |
