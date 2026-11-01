<!-- source: https://www.namecheap.com/support/api/methods/domainprivacy/enable/ | fetched: 2026-11-01T03:16:43Z -->

**IMPORTANT:**  Our privacy service provider recently changed to `WithheldforPrivacy`. We want to avoid service interruption for our API users, so please note that in some cases, you may still see `Whoisguard` in the API parameter names.

## namecheap.whoisguard.enable

Enables domain privacy protection for the WhoisguardID.

### Example Request

```
http://api.namecheap.com/xml.response?apiuser=demo&apikey=d41474b94e7d4536baabb074a09c96bd&username=demo&Command=Namecheap.Whoisguard.enable&ClientIp=192.168.1.109&whoisguardid=5924316&forwardedtoemail=xyz@gmail.com
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| WhoisguardID | Number | 10 | Yes | The unique domain privacy ID which you get |
| ForwardedToEmail | String | 70 | Yes | The email address to which domain privacy emails are to be forwarded |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <Warnings />
  <RequestedCommand>namecheap.whoisguard.enable</RequestedCommand>
  <CommandResponse Type="namecheap.whoisguard.enable">
    <WhoisguardEnableResult DomainName="domain1.com" IsSuccess="true" />
  </CommandResponse>
  <Server>API02</Server>
  <GMTTimeDifference>--5:00</GMTTimeDifference>
  <ExecutionTime>0.92</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| DomainName | The domain name for which you are trying to enable domain privacy |
| IsSuccess | Indicates whether the domain privacy was enabled successfully. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2011331 | Domain privacy does not exists (or) domain privacy is already enabled (or) domain privacy is not associated with any domain or) domain privacy is not associated with this user |
| 2011369 | Error domain privacy forwarded Email address is not valid |
