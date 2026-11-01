<!-- source: https://www.namecheap.com/support/api/methods/domains-transfer/get-list/ | fetched: 2026-11-01T03:13:26Z -->

## namecheap.domains.transfer.getList

Gets the list of domain transfers.

### Example Request

```
http://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&command=namecheap.domains.Transfer.getlist&clientip=192.20.36.51&listtype=all&page=1&pagesize=10
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here for clarity, but should be present in ***all*** requests

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| *ListType* | String | 10 | *No* | Possible values are ALL,INPROGRESS, CANCELLED,COMPLETED  **Default Value:** ALL |
| *SearchTerm* | String | 70 | *No* | The keyword should be a domain name. |
| *Page* | Number | 10 | *No* | Page to return  **Default Value:** 1 |
| *PageSize* | Number | 10 | *No* | Number of transfer to be listed on a page. Minimum value: 10; Maximum value: 100  **Default Value:** 10 |
| *SortBy* | String | 50 | *No* | Possible values are DOMAINNAME, DOMAINNAME\_DESC,TRANSFERDATE, TRANSFERDATE\_DESC,STATUSDATE, STATUSDATE\_DESC  **Default Value:** DOMAINNAME |

### Example Response

```
<?xml version="1.0" encoding="utf-8"?>
<ApiResponse Status="OK">
  <Errors/>
  <Warnings/>
  <RequestedCommand>namecheap.domains.transfer.getList</RequestedCommand>
  <CommandResponse Type="namecheap.domains.transfer.getList">
    <TransferGetListResult>
      <Transfer ID="59" Domainname="domain1.com" User="apiexample" TransferDate="02/15/2010" OrderID="32060156"StatusID="20" Status="CANCELLED" StatusDate="03/27/2010" StatusDescription="Canceled - Domain is currently not registered and cannot be transferrred"/>
      <Transfer ID="75" Domainname="domain8.co.uk" User="apiexample" TransferDate="04/13/2010" OrderID="32060636" StatusID="4" Status="INPROGRESS" StatusDate="03/14/2010" StatusDescription="Canceled due to domain status"/>
      <Transfer ID="77" Domainname="domain18.com" User="apiexample" TransferDate="06/01/2010" OrderID="32061647" StatusID="15" Status="CANCELLED" StatusDate="07/05/2010" StatusDescription="Canceled - cannot obtain domain contacts from UWhois"/>
      <Transfer ID="78" Domainname="domain57.com" User="apiexample" TransferDate="06/05/2010" OrderID="32061629" StatusID="15" Status="CANCELLED" StatusDate="07/05/2010" StatusDescription="Canceled - cannot obtain domain contacts from UWhois"/>
    </TransferGetListResult>
    <Paging>
      <TotalItems>49</TotalItems>
      <CurrentPage>1</CurrentPage>
      <PageSize>10</PageSize>
    </Paging>
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>--7:00</GMTTimeDifference>
  <ExecutionTime>0.096</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| TransferID | A unique integer value that represents the transfer |
| Domainname | The domain name associated with the transferID |
| User | The user account to which the domain is transferred. |
| TransferDate | Indicates the date at which transfer was initiated |
| Order ID | A unique integer value that represents the order |
| StatusID | An integer value that indicates the current transfer status |
| Status | [Transfer status.](transfer-statuses.md) |
| Statusdate | The date at which the status was updated |
| StatusDescription | [Transfer status](transfer-statuses.md) description |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 4019329 | TransferStatus not available |
| 2010293 | No Action Specified |
| 5050900 | Unhandled exceptions |
