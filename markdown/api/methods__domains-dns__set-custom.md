<!-- source: https://www.namecheap.com/support/api/methods/domains-dns/set-custom/ | fetched: 2026-11-01T03:12:06Z -->

## namecheap.domains.dns.setCustom

Sets domain to use custom DNS servers.

**NOTE:** Services like URL forwarding, Email forwarding, Dynamic DNS will not work for domains using custom nameservers

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.dns.setCustom&ClientIp=192.168.1.109&SLD=domain&TLD=com&NameServers=dns1.name-servers.com,dns2.name-servers.com
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| SLD | String | 70 | Yes | SLD of the DomainName |
| TLD | String | 10 | Yes | TLD of the DomainName |
| Nameservers | String | 1200 | Yes | A comma-separated list of name servers to be associated with this domain |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.dns.setCustom</RequestedCommand>
  <CommandResponse Type="namecheap.domains.dns.setCustom">
    <DomainDNSSetCustomResult Domain="domain.com" Updated="true" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>32.76</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | The domain name that you are trying to set custom nameservers for. |
| Updated | Indicates whether the custom nameservers were set successfully. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2019166 | Domain not found |
| 2016166 | Domain is not associated with your account |
| 2030166 | Edit permission for domain is not supported |
| 3031510 | Error From Enom when Errorcount <> 0 |
| 3050900 | Unknown error from Enom |
| 4022288 | Unable to get nameserver list |
