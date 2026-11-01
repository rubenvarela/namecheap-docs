<!-- source: https://www.namecheap.com/support/api/methods/domains-ns/update/ | fetched: 2026-11-01T03:13:00Z -->

## namecheap.domains.ns.update

Updates the IP address of a registered nameserver.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.ns.update&ClientIp=192.168.1.109&SLD=domain&TLD=com&Nameserver=ns1.domain.com&OldIP=192.165.15.103&IP=12.45.63.32
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| SLD | String | 70 | Yes | SLD of the Domain Name |
| TLD | String | 10 | Yes | TLD of the Domain Name |
| Nameserver | String | 150 | Yes | Nameserver |
| OldIP | String | 15 | Yes | Existing IP address |
| IP | String | 15 | Yes | New IP address |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.ns.update</RequestedCommand>
  <CommandResponse Type="namecheap.domains.ns.update">
    <DomainNSUpdateResult Domain="domain.com" Nameserver="ns1.domain.com" IsSuccess="true" />
  </CommandResponse>
  <Server>SEVER-ONE</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>32.76</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | The domain name for which you are trying to update nameserver details. |
| Nameserver | Returns the nameserver that was updated. |
| IsSuccess | Indicates whether the nameserver was updated successfully. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2019166 | Domain not found |
| 2016166 | Domain is not associated with your account |
| 3031510 | Error From Enom when Errorcount <> 0 |
| 3050900 | Unknown error from Enom |
