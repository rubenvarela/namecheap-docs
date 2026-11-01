<!-- source: https://www.namecheap.com/support/api/methods/ssl/revokecertificate/ | fetched: 2026-11-01T03:14:42Z -->

**Important:** This function is currently supported for Comodo certificates only.

## namecheap.ssl.revokecertificate

Revokes a reissued SSL certificate

This command is needed to revoke SSL certificates that were reissued and replaced in order to avoid usage of outdated certs with potentially compromised keys.

### Example Request

```
http://api.sandbox.namecheap.com/xml.response?ApiUser=apiexample&ApiKey=123456123456&UserName=apiexample&Command=namecheap.ssl.revokecertificate&certificatetype=positivessl&ClientIp=192.168.1.1&CertificateID=8111110
```

## Request Parameters

[Global parameters](global-parameters.md) are not shown here (for clarity), but they should be present in ***all*** requests.

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| CertificateID | Number | 10 | Yes | ID of the certificate for you wish to revoke  **Default Value:** 1 |
| CertificateType | String | 50 | Yes | Type of SSL Certificate |

###### Possible values for *Type* parameter:

InstantSSL, PositiveSSL, PositiveSSL Wildcard, EssentialSSL, EssentialSSL Wildcard, InstantSSL Pro, PremiumSSL Wildcard, EV SSL, EV Multi Domain SSL, Multi Domain SSL, PositiveSSL Multi Domain, Unified Communications.

###### Available starting July 11, 2026:

Standard SSL SSLcom, Standard Wildcard SSL SSLcom, SAN Certificate SSL SSLcom, High Assurance SSL SSLcom, OV Wildcard SSL SSLcom, OV Multi-domain SSL SSLcom, EV SSL SSLcom, EV Multi Domain SSL SSLcom.

### Example Response

```
<?xml version="1.0" encoding="UTF-8"?>
<ApiResponse Status="OK">
<Errors />
<Warnings />
<RequestedCommand>namecheap.ssl.revokecertificate</RequestedCommand>
<CommandResponse Type="namecheap.ssl.revokecertificate">
<RevokeCertificateResult IsSuccess="true" ID="8111110" >
</CommandResponse>
<Server>API02</Server>
<GMTTimeDifference>--5:00</GMTTimeDifference>
<ExecutionTime>0.874</ExecutionTime>
</ApiResponse>
```

### Response Parameters

| Name | Description |
| --- | --- |
| IsSuccess | Indicates whether the certificate was revoked successfully |
| CertificateID | A unique integer value that represents the certificate |

### Error Codes

Specifies the error codes that might be returned from this method

| Number | Description |
| --- | --- |
| 4011331 | Status is invalid |
| 2011300 | Wrong SSL certificate selection. The type provided is not supported by command. |
