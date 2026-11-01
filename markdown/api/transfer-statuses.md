<!-- source: https://www.namecheap.com/support/api/transfer-statuses/ | fetched: 2026-11-01T03:17:11Z -->

## Transfer Statuses and Description

Possible transfer statuses: `WAITINGFOREPP`, `CANCELED`, `COMPLETED`

#### Status ID and Description from provider

| StatusID | Description |
| --- | --- |
| 0 | Transfer request created - awaiting fax |
| 1 | WhoIs information matches |
| 2 | Canceled due to WhoIs error |
| 3 | Pending due to domain status |
| 4 | Canceled due to domain status |
| 5 | Transferred and paid successfully |
| 6 | Transfer incomplete - charge problem |
| 7 | Frozen due to charge problem |
| 8 | NSI rejected transfer |
| 9 | Awaiting auto verification of transfer request |
| 10 | Transfer in Process - Acquiring Current Whois for Transfer Verification |
| 11 | Auto verification of transfer request initiated |
| 12 | Awaiting for auto transfer string validation |
| 13 | Domain awaiting transfer initiation |
| 14 | Domain transfer initiated and awaiting approval |
| 15 | Canceled - cannot obtain domain contacts from Whois |
| 16 | Canceled - domain contacts did not respond to verification e-mail |
| 17 | Canceled - domain contacts did not approve transfer of domain |
| 18 | Canceled - domain validation string is invalid |
| 19 | Canceled - Whois information provided does not match current registrant |
| 20 | Canceled - Domain is currently not registered and cannot be transferred |
| 21 | Canceled - Domain is already registered in account and cannot be transferred |
| 22 | Canceled - Domain is locked at current registrar, or is not yet 60 days old |
| 23 | Canceled - Transfer already initiated for this domain |
| 24 | Canceled - Unable to transfer due to unknown error |
| 25 | Canceled - The current registrar has rejected transfer (please contact them for details) |
| 26 | Canceled - Transfer authorization fax not received |
| 27 | Canceled by customer |
| 28 | Fax received - awaiting registrant verification |
| 29 | Awaiting manual fax verification |
| 30 | Canceled - Domain name is invalid or is Invalid for Transfers |
| 31 | Canceled - Domain is currently undergoing transfer by another Registrar |
| 32 | Canceled - Invalid EPP/authorization key - Please contact current registrar to obtain correct key |
| 33 | Canceled - Cannot transfer domain from name-only account |
| 34 | Unable to complete transfer. Transfers must include a change in registrar |
| 35 | Transfer request not yet submitted |
| 36 | Canceled - Account is not authorized to perform domain transfers |
| 37 | Canceled - Domain was not retagged or not retagged in time by losing registrar |
| 45 | Order canceled |
| 48 | Canceled - registrant to registrant transfer only allowed into Retail accounts |
| 49 | Canceled - Maximum registration period exceeded |
| 50 | Canceled - Cannot transfer premium name |
| 51 | Canceled - Registrant info is missing |

#### Status ID and Description from Namecheap

| StatusID | Description |
| --- | --- |
| -4 | Canceled - Domain is locked at current registrar, or is not yet 60 days old |
| -22 | Canceled - Invalid entry |
| -1 | EPP Provided. Queued for Transfer |
| -5 | Authorization mail will be sent shortly |
| -2 | Resubmitted - Queued for transfer |
| -1 | Queued for submission or Queued for Transfer or EPP Provided |
| -202 | Unable to retrieve expiration date from Whois database |
| -22 | Waiting for EPP Transfer Code from Customer |
