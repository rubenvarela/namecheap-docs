<!-- source: https://www.namecheap.com/support/api/extended-attributes/ | fetched: 2026-11-01T03:17:05Z -->

## Extended Attributes

#### [.US Domains](https://www.namecheap.com/domains/registration/cctld/us.aspx)

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| RegistrantNexus | C11, C12, C21, C31, C32 | Yes | refer to notes below |
| *RegistrantNexusCountry* | No | *No* | Two-digit country code |
| RegistrantPurpose | P1, P2, P3, P4, P5 | Yes | refer to notes below |

###### `RegistrantNexus`

`C11` represents a natural person who is a US citizen; `C12` represents a natural person who is a permanent resident; `C21` represents an entity or an organization; `C31` represents a foreign organization; `C32` represents a foreign organization that has an office in US.

###### `RegistrantPurpose`

`P1` represents a business organization; `P2` represents a non-profit or religious organization or association; `P3` represents personal purpose; `P4` represents educational purpose; `P5` represents government purpose organization, etc.

#### .EU Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| EUAgreeWhoisPolicy | YES | Yes | refer to .EU Policy below |
| EUAgreeDeletePolicy | YES, NO | Yes | refer to .EU deletion rules below |
| *EUAdrLang* | BG, CS, DS, NL, EN, EL, PT ET, FI, FR, DE, HU, IT, LV, LI, MT, PL, RO, SK, SL, ES, SV | *No* | refer to note below |

###### .EU Policy

I hereby agree that the Registry is entitled to transfer the data contained in this application to third parties (i) if ordered to do so by a public authority, carrying out its legitimate tasks; and (ii) upon demand of an ADR Provider as mentioned in section 16 of the [.EU Terms and Conditions](http://www.eurid.eu) and (iii) as provided in Section 2 (WHOIS look-up facility) of the [.EU Domain Name WHOIS Policy](http://www.eurid.eu).

###### .EU Deletion Rules

I agree and acknowledge to the special renewal and expiration terms set forth below for this domain name, including those terms set forth in the Registration Agreement. I understand that unless I have set this domain for autorenewal, this domain name must be explicitly renewed by the expiration date or the 20th of the month of expiration, whichever is sooner. (e.g. If the name expires on Sept 4th, 2008, then a manual renewal must be received by Sept 4th, 2008. If name expires on Sep 27th, 2008, the renewal request must be received prior to Sep 20th, 2008). If the name is not manually renewed or previously set to autorenew, a delete request will be issued by Namecheap. When a delete request is issued, the name will remain fully functional in my account until expiration, but will no longer be renewable nor will I be able to make any modifications to the name. These terms are subject to change.

###### `EUAdrLang`

`BG` stands for Bulgaria; `CS` stands for Czech; `DS` stands for Danish; `NL` stands for Dutch; `EN` stands for English; `ET` stands for Estonian; `FI` stands for Finnish; `FR` stands for French; `DE` stands for German; `EL` stands for Greek; `HU` stands for Hungarian; `IT` stands for Italian; `LV` stands for Latvian; `LI` stands for Lithuanian; `MT` stands for Maltese; `PL` stands for Polish; `RO` stands for Romania; `SK` stands for Slovak; `SL` stands for Slovenian; `ES` stands for Spanish; `SV` stands for Swedish.

#### .NU Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| NUOrgNo | No | Yes | Personal Identification Number |
| *NUvatNo* | No | *No* | Swedish Organization in addition to Corporation ID, user can also optionally provide additional Tax/VAT Number. |

For `NUOrgNo` parameter, the Swedish Resident, should provide a valid

* Personal Identification Number, if registrant is an individual
* Organization Identification Number, if the registrant is a corporation registered in Sweden.

#### [.CA Domains](https://www.namecheap.com/domains/registration/cctld/ca.aspx)

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| CIRALegalType | CCO, CCT, RES, GOV, EDU, ASS, HOP, PRT, TDM, TRD, PLT, LAM, TRS, ABO, INB, LGR, OMK, MAJ | Yes | Legal Type of Registrant Contact |
| CIRAWhoisDisplay | Full, Private | Yes | Individuals (CCT, RES, ABO, LGR) may keep their Registrant contact information private in CIRA’s Whois; non-individuals must show their full Registrant information. |
| CIRAAgreementVersion | 2.0 | Yes | Version of the CIRA Registrant Agreement to which Registrant is agreeing. |
| CIRAAgreementValue | Y | Yes | This value should be Y (agreed to agreement) for the domain to be registered. Passing other values will fail the registration. |
| *CIRALanguage* | en, fr | *No* | Language in which to communicate with he contact.  **Default:** en |

###### `CIRALegalType`

`CCO` represents a Corporation; `CCT` represents a Canadian citizen; `RES` represents a Canadian resident; `GOV` represents a Government entity; `EDU` represents an Educational; `ASS` represents a Unincorporated Association; `HOP` represents a Hospital; `PRT` represents a Partnership; `TDM` represents a Trade-mark; `TRD` represents a Trade Union; `PLT` represents a Political Party; `LAM` represents Libraries, Archives and Museums; `TRS` represents a Trust; `ABO` represents Aboriginal Peoples; `INB` represents Indian Band; `LGR` represents Legal Representative; `OMK` represents an Official Mark; `MAJ` represents The Queen.

#### .CO.UK Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| COUKLegalType | IND, FIND, LTD\*, PLC\*, PTNR, LLP\*, IP, STRA, SCH, FOTHER, RCHAR\*, GOV, OTHER, CRC, FCORP, STAT, FOTHER | Yes | Legal Type of Registrant Contact |
| *COUKCompanyID* | No | *No* | Company Identification Number |
| COUKRegisteredfor | No | Yes | Company or Person the domain is registered for |

###### `COUKLegalType`

`IND` represents a UK individual; `FIND` represents a Non-UK individual; `LTD` represents a UK Limited Company\*; `PLC` represents a UK Public Limited Company\*; `PTNR` represents UK Partnership; `LLP` represents UK Limited Liability Partnership\*; `IP` represents UK Industrial/Provident Registered Company; `STRA` represents UK Sole Trader; `SCH` represents UK School; `RCHAR` represents UK Registered Charity\*; `GOV` represents UK Government Body; `OTHER` represents UK Entity (other); `CRC` represents UK Corporation by Royal Charter; `FCORP` represents Foreign Organization; `STAT` represents UK Statutory Body FIND; `FOTHER` represents Other Foreign Organizations.

For values marked with \* symbol, the `COUKCompanyID` parameter (company identification number) is required.

#### .ME.UK Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| MEUKLegalType | IND, FIND, LTD\*, PLC\*, PTNR, LLP\*, IP, STRA, SCH, FOTHER, RCHAR\*, GOV, OTHER, CRC, FCORP, STAT, FOTHER | Yes | Legal Type of Registrant Contact |
| *MEUKCompanyID* | No | *No* | Company Identification Number |
| MEUKRegisteredfor | No | Yes | Company or Person the domain is registered for |

###### `MEUKLegalType`

`IND` represents a UK individual; `FIND` represents a Non-UK individual; `LTD` represents a UK Limited Company\*; `PLC` represents a UK Public Limited Company\*; `PTNR` represents UK Partnership; `LLP` represents UK Limited Liability Partnership\*; `IP` represents UK Industrial/Provident Registered Company; `STRA` represents UK Sole Trader; `SCH` represents UK School; `RCHAR` represents UK Registered Charity\*; `GOV` represents UK Government Body; `OTHER` represents UK Entity (other); `CRC` represents UK Corporation by Royal Charter; `FCORP` represents Foreign Organization; `STAT` represents UK Statutory Body FIND; `FOTHER` represents Other Foreign Organizations.

For values marked with \* symbol, the `MEUKCompanyID` parameter (company identification number) is required.

#### .ORG.UK Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| ORGUKLegalType | IND, FIND, LTD\*, PLC\*, PTNR, LLP\*, IP, STRA, SCH, FOTHER, RCHAR\*, GOV, OTHER, CRC, FCORP, STAT, FOTHER | Yes | Legal Type of Registrant Contact |
| *ORGUKCompanyID* | No | *No* | Company Identification Number |
| ORGUKRegisteredfor | No | Yes | Company or Person the domain is registered for |

###### `ORGUKLegalType`

`IND` represents a UK individual; `FIND` represents a Non-UK individual; `LTD` represents a UK Limited Company\*; `PLC` represents a UK Public Limited Company\*; `PTNR` represents UK Partnership; `LLP` represents UK Limited Liability Partnership\*; `IP` represents UK Industrial/Provident Registered Company; `STRA` represents UK Sole Trader; `SCH` represents UK School; `RCHAR` represents UK Registered Charity\*; `GOV` *represents* UK Government Body; `OTHER` represents UK Entity (other); `CRC` represents UK Corporation by Royal Charter; `FCORP` represents Foreign Organization; `STAT` represents UK Statutory Body FIND; `FOTHER` represents Other Foreign Organizations.

For values marked with \* symbol, the `ORGUKCompanyID` parameter (company identification number) is required.

#### .COM.AU Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| COMAURegistrantId | No | Yes | Id of the registrant |
| COMAURegistrantIdType | ABN, ACN, RBN, TM | Yes | The registrant type |

###### `COMAURegistrantIdType`

`ABN` represents Australian Business Number; `ACN` represents Australian Company Number; `RBN` represents Business Registration Number; `TM` represents a Trademark Number.

#### .NET.AU Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| NETAURegistrantId | No | Yes | Id of the registrant |
| NETAURegistrantIdType | ABN, ACN, RBN, TM | Yes | The registrant type |

###### `NETAURegistrantIdType`

`ABN` represents Australian Business Number; `ACN` represents Australian Company Number; `RBN` represents Business Registration Number; `TM` represents a Trademark Number.

#### .ORG.AU Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| ORGAURegistrantId | No | Yes | Id of the registrant |
| ORGAURegistrantIdType | ABN, ACN, RBN, TM | Yes | The registrant type |

###### `ORGAURegistrantIdType`

`ABN` represents Australian Business Number; `ACN` represents Australian Company Number; `RBN` represents Business Registration Number; `TM` represents a Trademark Number.

#### .ES Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| ESRegistrantId | No | Yes | Id of the registrant |
| ESRegistrantIdType | ALIENID, GENERICID, VATID | Yes | The registrant type |
| ESLegalFormType | Association, CentralGovernmentBody, CivilSociety, CommunityofOwners, CommunityProperty, Consulate, Cooperative, DesignationofOriginSupervisoryCouncil, EconomicInterestGroup, Embassy, EntityManagingNaturalAreas, FarmPartnership,Foundation, GeneralandLimitedPartnership, GeneralPartnership, Individual, LimitedCompany, LocalAuthority, LocalPublicEntity, MutualInsuranceCompany, NationalPublicEntity, OrderorReligiousInstitution, Others, PoliticalParty, ProfessionalAssociation, PublicLawAssociation, PublicLimitedCompany, RegionalGovernmentBody, RegionalPublicEntity, SavingsBank, SpanishOffice, SportsAssociation, Sports\_Association, SportsFederation, TemporaryAllianceofEnterprises, TradeUnion, WorkerownedCompany, WorkerownedLimitedCompany | Yes | The legal form type |
| ESAdminIdType | GENERICID, NATIONALIDENTITY, ALIENID | Yes | Admin ID type |
| EsAdminID | No | Yes | ID of the Admin |
| ESAcceptAgreement | Yes, No | Yes | To agree the terms for the domain name |

#### .NOM.ES Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| NOMESRegistrantId | No | Yes | Id of the registrant |
| NOMESRegistrantIdType | ALIENID, GENERICID, VATID | Yes | The registrant type |
| NOMESLegalFormType | Association, CentralGovernmentBody, CivilSociety, CommunityofOwners, CommunityProperty, Consulate, Cooperative, DesignationofOriginSupervisoryCouncil, EconomicInterestGroup, Embassy, EntityManagingNaturalAreas, FarmPartnership,Foundation, GeneralandLimitedPartnership, GeneralPartnership, Individual, LimitedCompany, LocalAuthority, LocalPublicEntity, MutualInsuranceCompany, NationalPublicEntity, OrderorReligiousInstitution, Others, PoliticalParty, ProfessionalAssociation, PublicLawAssociation, PublicLimitedCompany, RegionalGovernmentBody, RegionalPublicEntity, SavingsBank, SpanishOffice, SportsAssociation, Sports\_Association, SportsFederation, TemporaryAllianceofEnterprises, TradeUnion, WorkerownedCompany, WorkerownedLimitedCompany | Yes | The legal form type |

#### .COM.ES Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| COMESRegistrantId | No | Yes | Id of the registrant |
| COMESRegistrantIdType | ALIENID, GENERICID, VATID | Yes | The registrant type |
| COMESLegalFormType | Association, CentralGovernmentBody, CivilSociety, CommunityofOwners, CommunityProperty, Consulate, Cooperative, DesignationofOriginSupervisoryCouncil, EconomicInterestGroup, Embassy, EntityManagingNaturalAreas, FarmPartnership,Foundation, GeneralandLimitedPartnership, GeneralPartnership, Individual, LimitedCompany, LocalAuthority, LocalPublicEntity, MutualInsuranceCompany, NationalPublicEntity, OrderorReligiousInstitution, Others, PoliticalParty, ProfessionalAssociation, PublicLawAssociation, PublicLimitedCompany, RegionalGovernmentBody, RegionalPublicEntity, SavingsBank, SpanishOffice, SportsAssociation, Sports\_Association, SportsFederation, TemporaryAllianceofEnterprises, TradeUnion, WorkerownedCompany, WorkerownedLimitedCompany | Yes | The legal form type |

#### .ORG.ES Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| ORGESRegistrantId | No | Yes | Id of the registrant |
| ORGESRegistrantIdType | ALIENID, GENERICID, VATID | Yes | The registrant type |
| ORGESLegalFormType | Association, CentralGovernmentBody, CivilSociety, CommunityofOwners, CommunityProperty, Consulate, Cooperative, DesignationofOriginSupervisoryCouncil, EconomicInterestGroup, Embassy, EntityManagingNaturalAreas, FarmPartnership,Foundation, GeneralandLimitedPartnership, GeneralPartnership, Individual, LimitedCompany, LocalAuthority, LocalPublicEntity, MutualInsuranceCompany, NationalPublicEntity, OrderorReligiousInstitution, Others, PoliticalParty, ProfessionalAssociation, PublicLawAssociation, PublicLimitedCompany, RegionalGovernmentBody, RegionalPublicEntity, SavingsBank, SpanishOffice, SportsAssociation, Sports\_Association, SportsFederation, TemporaryAllianceofEnterprises, TradeUnion, WorkerownedCompany, WorkerownedLimitedCompany | Yes | The legal form type |

#### .DE Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| DEConfirmAddress | DE | Yes | To confirm the Administrative address is a valid German address |
| DEAgreeDelete | Yes, No | Yes | To agree the renewal terms for the domain name |
|

#### .FR Domains

| Parameter | Possible Values | Required? | Description |
| --- | --- | --- | --- |
| FRRegistrantBirthDate | No | Yes | Required only when `FRLegalType=Individual` |
| FRRegistrantBirthplace | No | Yes | Required only when `FRLegalType=Individual` |
| FRRegistrantLegalId | No | Yes | Required only when `FRLegalType=Company`. French company with a SIREN or SIRET number should continue to provide this number instead as legal id. The SIREN number is the first part of the SIRET NUMBER and consists of 9 digits. The SIRET number is a unique identification number with 14 digits. |
| FRRegistrantTradeNumber | No | Yes | Required only when `FRLegalType=Company`. Companies with a European trademark:For companies with a European trademark can additionally add their trademark number using this extension. |
| FRRegistrantDunsNumber | No | Yes | Required only when `FRLegalType=Company`. The DUNS number is a nine-digit number, issued by Dun Bradstreet. DUNS is the abbreviation of Data Universal Numbering System. Companies with a valid DUNS number are still obliged having their head office in the territory of the European Union. The DUNS number can be provided using this extension. |
| FRRegistrantLocalId | No | Yes | Required only when `FRLegalType=Company`. Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this extension. |
| FRRegistrantJoDateDec | No | Yes | Required only when `FRLegalType=Company`. French associations listed with the Journal Officiel de la République Francaise - The official gazette of the French Republic: The Journal Official Associations publishes notices of creations, breakup or substantial changes with nonprofit associations in France. Using the website http://www.societe.com and the database they provide, query for the respective data below to register a .FR domain name. - The date of declaration of the association in the form YYYY-MM-DD. |
| FRRegistrantJoDatePub | No | Yes | Required only when `FRLegalType=Company`. The date of publication in the Journal Official in the form YYYY-MM-DD |
| FRRegistrantJoNumber | No | Yes | Required only when `FRLegalType=Company`. The number of the Journal Official |
| FRRegistrantJoPage | No | Yes | Required only when `FRLegalType=Company`. The page of the announcement in the Journal Official |
| FRLegalType | Company, Individual | Yes | Registrant type |
