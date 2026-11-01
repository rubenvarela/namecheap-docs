<!-- source: https://www.namecheap.com/support/api/global-parameters/ | fetched: 2026-11-01T03:17:00Z -->

## Namecheap API Global Parameters

For each API call, a set of parameters are required. These parameters include information like `APIUser`, `APIKey`, etc., and should be present in ***all*** the requests.

## Global Request Parameters

| Name | Type | MaxLength | Required? | Description |
| --- | --- | --- | --- | --- |
| ApiUser | String | 20 | Yes | Username required to access the API |
| ApiKey | String | 50 | Yes | Password required used to access the API |
| Command | String | 80 | Yes | Command for execution |
| UserName | String | 20 | Yes | The Username on which a command is executed.Generally, the values of `ApiUser` and `UserName` parameters are the same. |
| ClientIp | String | 15 | Yes | An IP address of the server from which our system receives API calls (only IPv4 can be used). |

### Global Error Codes

| Number | Description |
| --- | --- |
| 1010101 | Parameter `APIUser` is missing |
| 1030408 | Unsupported authentication type |
| 1010104 | Parameter `Command` is missing |
| 1010102, 1011102 | Parameter `APIKey` is missing |
| 1010105, 1011105 | Parameter `ClientIP` is missing |
| 1050900 | Unknown error when validating `APIUser` |
| 1011150 | Parameter `RequestIP` is invalid |
| 1017150 | Parameter `RequestIP` is disabled or locked |
| 1017105 | Parameter `ClientIP` is disabled or locked |
| 1017101 | Parameter `ApiUser` is disabled or locked |
| 1017410 | Too many declined payments |
| 1017411 | Too many login attempts |
| 1019103 | Parameter `UserName` is not available |
| 1016103 | Parameter `UserName` is unauthorized |
| 1017103 | Parameter `UserName` is disabled or locked |
