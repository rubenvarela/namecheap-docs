<!-- source: https://www.namecheap.com/support/api/methods/users-address/delete/ | fetched: 2026-11-01T03:15:51Z -->

## namecheap.users.address.delete

Deletes the particular address for the user.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db681944&UserName=apiuser&Command=namecheap.users.address.delete&ClientIp=192.168.1.109&AddressId=48
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| AddressId | Number | 20 | Yes | The unique AddressID to delete |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.users.address.delete</RequestedCommand>
  <CommandResponse Type="namecheap.users.address.delete">
    <AddressDeleteResult Success="true" ProfileId="48" UserName="apiuser" />
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>0.047</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| Success | Indicates whether the address was deleted successfully. |
| ProfileID | A unique integer value that represents the address profile. |
| Username | The username in question |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 4011331 | StatusCode for delete is invalid |
| 4025336 | Failed to delete user's address |
