<!-- source: https://www.namecheap.com/support/api/methods/domains/set-registrar-lock/ | fetched: 2026-11-01T03:11:46Z -->

## namecheap.domains.setRegistrarLock

Sets the Registrar Lock status for a domain

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.setRegistrarLock&ClientIp=192.168.1.109&DomainName=domain1.com&LockAction=unlock
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be present in ***all*** requests.

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| DomainName | String | 70 | Yes | Domain name to set status for |
| *LockAction* | String | 70 | *No* | Possible values: LOCK, UNLOCK.  **Default Value:** LOCK. |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.setRegistrarLock</RequestedCommand>
  <CommandResponse Type="namecheap.domains.setRegistrarLock">
    <DomainSetRegistrarLockResult Domain="domain1.com" IsSuccess="true" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5:30</GMTTimeDifference>
  <ExecutionTime>1.422</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Domain | The domain name you wish to set registrar lock for |
| IsSuccess | Indicates whether registrar lock was set successfully |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2015278 | Invalid data specified for LockAction |
| 2019166 | Domain not found |
| 2016166 | Domain is not associated with your account |
| 3031510 | Error from Enom when Errorcount <> 0 |
| 2030166 | Edit permission for domain is not supported |
| 3050900 | Unknown error response from Enom |
| 5050900 | Unknown exceptions |
