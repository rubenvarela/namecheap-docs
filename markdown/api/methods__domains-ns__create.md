<!-- source: https://www.namecheap.com/support/api/methods/domains-ns/create/ | fetched: 2026-11-01T03:12:44Z -->

## namecheap.domains.ns.create

Creates a new nameserver.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexmple&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.ns.create&ClientIp=192.168.1.109&SLD=domain&TLD=com&Nameserver=ns1.domain.com&IP=192.165.15.103
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| SLD | String | 70 | Yes | SLD of the DomainName |
| TLD | String | 10 | Yes | TLD of the DomainName |
| Nameserver | String | 150 | Yes | Nameserver to create |
| IP | String | 15 | Yes | Nameserver IP address |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.ns.create</RequestedCommand>
  <CommandResponse Type="namecheap.domains.ns.create">
    <DomainNSCreateResult Domain="domain.com" Nameserver="ns1.domain.com" IP="12.23.23.23" IsSuccess="true" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>32.76</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | The domain name for which you are trying to create nameserver. |
| Nameserver | Returns the nameserver that was created. |
| IP | Returns the IP address set for the nameserver. |
| IsSuccess | Indicates whether the nameserver was set successfully. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2019166 | Domain not found |
| 2016166 | Domain is not associated with your account |
| 3031510 | Error From Enom when Errorcount <> 0 |
| 3050900 | Unknown error from Enom |
