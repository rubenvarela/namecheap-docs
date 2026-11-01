<!-- source: https://www.namecheap.com/support/api/methods/ssl/resend-approver-email/ | fetched: 2026-11-01T03:14:02Z -->

## namecheap.ssl.resendApproverEmail

Resends the approver email
 *'Retries'* HTTP/ DNS validation after the file is uploaded / CNAME record created.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.ssl.resendapproveremail&ClientIp=192.168.1.109&CertificateID=500532
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be present in ***all*** requests.

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| CertificateID | String | 10 | Yes | The unique certificate ID that you get after calling ssl.create command |

### Example Response

```
<ApiResponse Status="OK">
<Errors/>
<RequestedCommand>namecheap.ssl.resendApproverEmail</RequestedCommand>
  <CommandResponse Type="namecheap.ssl.resendApproverEmail">
    <SSLResendApproverEmailResult ID="500532" IsSuccess="true"/>
  </CommandResponse>
<Server>SERVER-NAME</Server>
<GMTTimeDifference>+5:30</GMTTimeDifference>
<ExecutionTime>3.826</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| ID | The unique integer value that represents the SSL certificate |
| IsSuccess | Indicates whether the approver email was resent successfully |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2011294 | CertificateID is invalid |
| 2011331 | Status is invalid |
| 3011295 | ApproverEmail is invalid |
| 5050900 | Unhandled exceptions |
