<!-- source: https://www.namecheap.com/support/api/methods/domains/get-list/ | fetched: 2026-11-01T03:10:57Z -->

**IMPORTANT:**  Our privacy service provider recently changed to `WithheldforPrivacy`. We want to avoid service interruption for our API users, so please note that in some cases, you may still see `Whoisguard` in the API parameter names.

## namecheap.domains.getList

Returns a list of domains for the particular user

### Example Request

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.domains.getList&ClientIp=192.168.1.109
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be present in ***all*** requests.

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| *ListType* | String | 10 | *No* | Possible values are ALL, EXPIRING, or EXPIRED  **Default Value:** ALL |
| *SearchTerm* | String | 70 | *No* | Keyword to look for in the domain list |
| *Page* | Number | 10 | *No* | Page to return  **Default Value:** 1 |
| *PageSize* | Number | 10 | *No* | Number of domains to be listed on a page. Minimum value is 10, and maximum value is 100.  **Default Value:** 20 |
| *SortBy* | String | 50 | *No* | Possible values are NAME, NAME\_DESC, EXPIREDATE, EXPIREDATE\_DESC, CREATEDATE, CREATEDATE\_DESC |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse xmlns="http://api.namecheap.com/xml.response" Status="OK">
  <Errors />
  <RequestedCommand>namecheap.domains.getList</RequestedCommand>
  <CommandResponse Type="namecheap.domains.getList">
    <DomainGetListResult>
      <Domain ID="127" Name="domain1.com" User="owner" Created="02/15/2016" Expires="02/15/2022" IsExpired="false" IsLocked="false" AutoRenew="false" WhoisGuard="ENABLED" IsPremium="true" IsOurDNS="true"/>
      <Domain ID="381" Name="domain2.com" User="owner" Created="04/28/2016" Expires="04/28/2023" IsExpired="false" IsLocked="false" AutoRenew="true" WhoisGuard="NOTPRESENT" IsPremium="false" IsOurDNS="true"/>
      <Domain ID="385" Name="domain3.com" User="owner" Created="05/22/2016" Expires="05/22/2023" IsExpired="false" IsLocked="false" AutoRenew="true" WhoisGuard="ENABLED" IsPremium="false" IsOurDNS="false"/>
    </DomainGetListResult>
    <Paging>
      <TotalItems>2</TotalItems>
      <CurrentPage>1</CurrentPage>
      <PageSize>10</PageSize>
    </Paging>
  </CommandResponse>
  <Server>SERVER-NAME</Server>
  <GMTTimeDifference>+5</GMTTimeDifference>
  <ExecutionTime>0.078</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| ID | Unique integer value that represents the domain |
| Name | Registered domain name |
| User | User account under which the domain is registered |
| Created | Domain creation date |
| Expires | Domain expiration date |
| IsExpired | Possible responses: True, False. Indicates whether the domain is expired |
| IsLocked | Possible responses: True, False. Indicates whether the domain is locked. When Islocked=true, domain changes are not allowed. |
| AutoRenew | Possible responses: True, False. Indicates whether the domain is set for auto-renew |
| WhoisGuard | Returns the domain privacy status |
| IsPremium | Indicates whether the domain name is premium |
| IsOurDNS | Returns true if Namecheap BasicDNS or Namecheap PremiumDNS are used; if something else, returns false |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 5050169 | Unknown exceptions |
