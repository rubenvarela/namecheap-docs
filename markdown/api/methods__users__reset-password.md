<!-- source: https://www.namecheap.com/support/api/methods/users/reset-password/ | fetched: 2026-11-01T03:15:35Z -->

## namecheap.users.resetPassword

When you call this API, a link to reset password will be emailed to the end user's profile email id.The end user needs to click on the link to reset password.

**NOTE:** `UserName` should be omitted for this API call.All other Global parameters must be included.

### Example Requests

```
https://api.namecheap.com/xml.response?APIUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&clientip=61.11.95.68&command=namecheap.users.resetpassword&findby=username&findbyvalue=sampleuser
```

```
https://api.namecheap.com/xml.response?APIUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&clientip=61.11.95.68&command=namecheap.users.resetpassword&findby=username&findbyvalue=sampleuser&URLPattern=http://www.somedomain.com/ownformat/resetpassword/[RESETCODE]&EmailFromName=sampleusername&EmailFrom=sampleuser@somedomain.com
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| FindBy | String | 20 | Yes | Possible values:EMAILADDRESS, DOMAINNAME,USERNAME |
| FindByValue | String | 20 | Yes | The username/email address/domain of the user |
| *EmailFromName* | String | 20 | *No* | Enter a different value to overwrite the default value   **Default Value:**  namecheap.com |
| *EmailFrom* | String | 20 | *No* | Enter a different value to overwrite the default value   **Default Value:**  support@namecheap.com |
| *URLPattern* | String | 20 | *No* | Enter a different URL to overwrite namecheap.com. Refer Example Request#2   **Default Value:**  http://namecheap.com [RESETCODE] |

### Example Response

```
<?xml version="1.0" encoding="utf-8"?>
<ApiResponse Status="OK" xmlns="http://api.namecheap.com/xml.response">
 <Errors />
 <RequestedCommand>namecheap.users.resetPassword</RequestedCommand>
 <CommandResponse Type="namecheap.users.resetPassword">
   <UserResetPasswordResult Success="true">
     <Email>contact@useremail.com</Email>
   </UserResetPasswordResult>
 </CommandResponse>
<Server>SERVER159</Server>
<GMTTimeDifference>--5:00</GMTTimeDifference>
<ExecutionTime>0.742</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Success | Indicates whether the password was reset successfully |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2011315 | FindBy is invalid |
| 4027153 | Failed to send email |
| 4022335 | Unable to reset password |
| 5050900 | Unknown exceptions |
