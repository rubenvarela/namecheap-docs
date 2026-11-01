<!-- source: https://www.namecheap.com/support/api/methods/domains-transfer/get-status/ | fetched: 2026-11-01T03:13:15Z -->

## namecheap.domains.transfer.getStatus

Gets the status of a particular transfer.

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.transfer.getStatus&ClientIp=192.168.1.109&TransferID=15
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| TransferID | Number | 10 | Yes | The unique Transfer ID which you get after placing a transfer request |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.transfer.getStatus</RequestedCommand>
  <CommandResponse Type="namecheap.domains.transfer.getstatus">
    <DomainTransferGetStatusResult TransferID="15" Status="Queued for submission" StatusID="-1" />
  </CommandResponse>
  <Server>EV1SERVE-3CQ3CC</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>0.031</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| TransferID | A unique integer value that represents the transfer |
| StatusID | An integer value that indicates the current [transfer status.](transfer-statuses.md) |
| Status | [Transfer status](transfer-statuses.md) description. |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 4019329 | TransferStatus not available |
| 5050900 | Unhandled exceptions |
