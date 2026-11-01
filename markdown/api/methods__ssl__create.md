<!-- source: https://www.namecheap.com/support/api/methods/ssl/create/ | fetched: 2026-11-01T03:13:36Z -->

Both HTTP GET and POST are supported by this method.

## namecheap.ssl.create

Creates a new SSL certificate

### Example request for single-domain certificate

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.ssl.create&ClientIp=192.168.1.109&Years=2&Type=PositiveSSL
```

### Example request for multi-domain certificate

```
https://api.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=56b4c87ef4fd49cb96d915c0db68194&UserName=apiexample&Command=namecheap.ssl.create&ClientIp=192.168.1.109&Years=2&Type=Multi%20Domain%20SSL&SANStoAdd=15
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be present in ***all*** requests.

| Parameter | Data Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| Years | Number | 1 | Yes | Number of years SSL will be issued for  Allowed values: 1,2,3,4,5 |
| Type | String | 50 | Yes | SSL product name. See "Possible values for *Type* parameter" below this table. |
| *SANStoADD* | Number | 2 | *No* | Defines number of add-on domains to be purchased in addition to the default number of domains included into a *multi-domain certificate*. |
| *PromotionCode* | String | 20 | *No* | Promotional (coupon) code for the certificate |

######

###### Possible values for *Type* parameter starting July 11, 2026:

Standard SSL SSLcom, Standard Wildcard SSL SSLcom, SAN Certificate SSL SSLcom, High Assurance SSL SSLcom, OV Wildcard SSL SSLcom, OV Multi-domain SSL SSLcom, EV SSL SSLcom, EV Multi Domain SSL SSLcom.

###### The following values will be deprecated on July 11, 2026:

PositiveSSL, EssentialSSL, InstantSSL, InstantSSL Pro, PremiumSSL, PositiveSSL Wildcard, EssentialSSL Wildcard, PremiumSSL Wildcard, PositiveSSL Multi Domain, Multi Domain SSL, Unified Communications, EV SSL, EV Multi Domain SSL.

**Note:** To maintain backward compatibility, automatic product replacement is applied to deprecated *Type* values. A request specifying a deprecated product will not fail — an equivalent SSL type will be issued and returned in the response instead. Starting July 11, 2026, we recommend specifying one of the new product names when purchasing a certificate via the *create* method.

###### SSL certificates classification by domain coverage and validation type:

Single-domain:

* Domain Validation (DV): PositiveSSL, EssentialSSL, Standard SSL SSLcom
* Organization Validation (OV): InstantSSL, InstantSSL Pro, PremiumSSL, High Assurance SSL SSLcom
* Extended Validation (EV): EV SSL, EV SSL SSLcom

Wildcard:

* Domain Validation (DV): PositiveSSL Wildcard, EssentialSSL Wildcard, Standard Wildcard SSL SSLcom
* Organization Validation (OV):  PremiumSSL Wildcard, OV Wildcard SSL SSLcom

Multi-domain:

* Domain Validation (DV): PositiveSSL Multi Domain, SAN Certificate SSL SSLcom
* Organization Validation (OV): Multi Domain SSL, Unified Communications, OV Multi-domain SSL SSLcom
* Extended Validation (EV): EV Multi Domain SSL, EV Multi Domain SSL SSLcom

All multi-domain certificates have a default number of domains included in the basic setup (without SANS), a max total number of domains, and a max SANStoAdd value

| Domains included | Max total domains | Max *SANStoADD* value |
| --- | --- | --- |
| 3 | 100 | 97 |

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse Status="OK" xmlns="http://api.namecheap.com/xml.response">
 <Errors/>
 <Warnings/>
 <RequestedCommand>namecheap.ssl.create</RequestedCommand>
 <CommandResponse Type="namecheap.ssl.create">
  <SSLCreateResult IsSuccess="true" OrderId="1234567" TransactionId="1234567" ChargedAmount="908.1600">
   <SSLCertificate CertificateID="123456" Created="02/20/2018" SSLType="Multi Domain SSL" Years="2" Status="NewPurchase"/>
  </SSLCreateResult>
 </CommandResponse>
 <Server>202005e9484c</Server>
 <GMTTimeDifference>--5:00</GMTTimeDifference>
 <ExecutionTime>2.608</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| IsSuccess | Indicates whether SSL order was successful |
| Order ID | A unique integer value that represents the order |
| TransactionID | A unique integer value that represents the transaction |
| ChargedAmount | The amount charged for the order |
| CertificateID | A unique integer value that represents the SSL |
| Created | The date on which the certificate is created |
| SSLType | Type of SSL cerificate |
| Years | Number of years for which the certificate will be issued |
| Status | The current status of SSL certificate |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 2010167 | Parameter Years is Missing |
| 2010298 | Parameter Type is Missing |
| 2011167 | Parameter Years is Invalid |
| 2011170 | using const PROMOTION\_CODE\_ERRORS as custom text for this error |
| 2011301 | Parameter Type is not valid |
| 2011301 | We\'re sorry, the requested SSL type has been discontinued |
| 2011767 | Addon details is not available for the SSLType |
| 2011767 | Number of SANS To add is not within the limit. |
| 2011900 | Parameter SANSToAdd is Invalid |
| 2013167 | Parameter Years is OutOfRange |
| 2013170 | Parameter PromotionCode is TooLong |
| 2013900 | Parameter SANSToAdd is OutOfRange |
| 2015167 | Number of years should be maximum 3 |
| 2032409 | Some error occurred during authentication phase' |
| 2528166 | Order creation failed |
| 2528166 | ORDER CREATION FAILED; Failed to Create Order;;Oops! Internal error occurred while creating order. Please try again. If problem persist, please contact support. Error Details:-CALCULATIONERROR |
| 2528166 | ORDER CREATION FAILED; INSUFFICIENTFUNDS;Insufficient funds in account; Sorry! Your available balance is insufficient to cover the current billing amount; |
| 4080167 | Due to recent CA/B Forum updates, it is no longer possible to purchase 4- and 5-year certificates after March 1, 2015. Please contact our support team. |
| 4080167 | Due to revised CA/B Forum regulations, it is no longer possible to purchase 3-, 4- and 5-year certificates after March 1, 2018. Please contact our support team. |
