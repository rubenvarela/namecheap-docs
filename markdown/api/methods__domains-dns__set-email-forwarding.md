<!-- source: https://www.namecheap.com/support/api/methods/domains-dns/set-email-forwarding/ | fetched: 2026-11-01T03:12:28Z -->

## namecheap.domains.dns.setEmailForwarding

Sets email forwarding for a domain name.

**NOTE:** The [ ] brackets are used to represent optional values (e.g.[1...n]). Do not include the [ ] brackets in your API requests.Please refer to the example API request given below.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.dns.setEmailForwarding&ClientIp=192.168.1.109&DomainName=domain.com&mailbox1=info&ForwardTo1=domaininfo@gmail.com&mailbox2=careers&ForwardTo2=domaincareer@gmail.com
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| DomainName | String | 70 | Yes | Domain name to set settings |
| MailBox[1..n] | String | No | Yes | MailBox for which you wish to set email forwarding. For example:example@namecheap.com |
| ForwardTo[1..n] | String | No | Yes | Email address to forwardto.For example:example@gmail.com |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.dns.setEmailForwarding</RequestedCommand>
  <CommandResponse Type="namecheap.domains.dns.setEmailForwarding">
    <DomainDNSSetEmailForwardingResult Domain="domain.com" IsSuccess="true" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>--5:00</GMTTimeDifference>
  <ExecutionTime>0.13</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | The domain name for which you are trying to set emailforwarding. |
| IsSuccess | Indicates whether email forwarding were set successfully. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2019166 | Domain not found |
| 2016166 | Domain is not associated with your account |
| 2030288 | Cannot complete this command as this domain is not using proper DNS servers |
| 2030166 | Edit Permission for domain is not supported |
| 3013288 | Too many records |
| 3031510 | Error From Enom when Errorcount <> 0 |
| 3050900 | Unknown error from Enom |
| 4022228 | Unable to get nameserver list |
