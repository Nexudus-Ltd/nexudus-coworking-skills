# CrmOpportunities

<!-- BEGIN:GENERATED entity=CrmOpportunities -->

A CRM opportunity (CrmOpportunity) is a potential customer deal in a location's CRM board, assigned to one CRM stage and tracked from enquiry through an in-progress, won, or lost outcome; moving it to a stage can run that stage's configured automation.

CrmOpportunities support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmopportunities list --agent` | List all crmopportunities |
| `nexudus crmopportunities list --id <id> --agent` | Filter by single ID |
| `nexudus crmopportunities list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmopportunities list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmopportunities list --name <value> --crm-board-column-name <value> --agent` | Filter crmopportunities by properties |
| `nexudus crmopportunities list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmopportunities list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus crmopportunities get <id> --agent` | Get single crmopportunity |
| `nexudus crmopportunities create --crm-board-column-id <value> --coworker-id <value> --status <value> --position <value> --agent` | Create crmopportunity |
| `nexudus crmopportunities update <id> --name "New Name" --agent` | Update crmopportunity |
| `nexudus crmopportunities delete <id> --yes --agent` | Delete crmopportunity (no prompt) |

#### CrmOpportunity list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Optional operator-facing label for this opportunity, useful when a customer has opportunities in multiple CRM boards. |
| `--crm-board-column-id` | long | ID of the CRM stage that contains this opportunity and determines its location access; changing it moves the opportunity and runs that stage's arrival actions. |
| `--crm-board-column-name` | string | Display value for CrmBoardColumn.Name. |
| `--crm-board-column-crm-board-id` | int | Display value for CrmBoardColumn.CrmBoard.Id. |
| `--from-crm-board-column-crm-board-id` | range | |
| `--to-crm-board-column-crm-board-id` | range | |
| `--crm-board-column-crm-board-name` | string | Display value for CrmBoardColumn.CrmBoard.Name. |
| `--crm-board-column-crm-board-business-id` | int | Display value for CrmBoardColumn.CrmBoard.Business.Id. |
| `--from-crm-board-column-crm-board-business-id` | range | |
| `--to-crm-board-column-crm-board-business-id` | range | |
| `--crm-board-column-crm-board-business-name` | string | Display value for CrmBoardColumn.CrmBoard.Business.Name. |
| `--crm-board-column-crm-board-business-currency-id` | int | Display value for CrmBoardColumn.CrmBoard.Business.Currency.Id. |
| `--from-crm-board-column-crm-board-business-currency-id` | range | |
| `--to-crm-board-column-crm-board-business-currency-id` | range | |
| `--crm-board-column-crm-board-business-currency-code` | string | Display value for CrmBoardColumn.CrmBoard.Business.Currency.Code. |
| `--coworker-id` | long | ID of the customer this opportunity tracks; a customer is required by backend validation even though the relationship metadata is nullable. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-email` | string | Display value for Coworker.Email. |
| `--team-id` | long | Optional ID of the team associated with this opportunity. |
| `--team-name` | string | Display value for Team.Name. |
| `--team-description` | string | Display value for Team.Description. |
| `--team-profile-website` | string | Display value for Team.ProfileWebsite. |
| `--opportunity-type-id` | long | Optional ID of the opportunity type used to categorize this CRM opportunity. |
| `--opportunity-type-name` | string | Display value for OpportunityType.Name. |
| `--responsible-id` | long | Optional ID of the staff user responsible for following up this opportunity. |
| `--responsible-full-name` | string | Display value for Responsible.FullName. |
| `--referrer-id` | long | Optional ID of the customer who referred this opportunity. |
| `--agent-id` | long | Optional ID of the customer record representing the referring agent or broker. |
| `--notes` | string | Optional internal notes about this opportunity and its follow-up. |
| `--completed` | bool | Whether this opportunity is marked complete; use Status to record whether it was won or lost. |
| `--due-date` | DateTime | Optional date and time by which this opportunity requires follow-up; the backend compares it against UTC for overdue CRM counts. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--value` | decimal | Optional expected revenue amount if this opportunity is won, in the parent CRM board location's currency. |
| `--from-value` | range | |
| `--to-value` | range | |
| `--reminded` | bool | Whether a follow-up reminder has already been sent for this opportunity; this internal state is not exposed to Admin Tool schemas. |
| `--lead-source` | enum | Optional acquisition source: Web, Phone, Webinar, Referral, PrintAdvert, PurchasedList, WordOfMouth, DirectEmail, EmailMarketing, Broker, PropertyAgent, Facebook, Linkedin, Instagram, Twitter, HubbleHq, LiquidSpace, GoogleSearch, SpacePool, InstantOffices, OfficeFreedom, FlexiOffices, Workthere, Kontor, Valve, OtherSocialNetwork, or Other. |
| `--loss-reason` | enum | Optional reason for a lost opportunity: Timing, Need, PoorQualification, Price, Feature, LostMomentum, Competition, ContractTerm, Duplicate, Waitlist, NotReturningCalls, LackOfFacilities, NoPetPolicy, NoRightFit, Location, Entrance, Errors, Archived, SearchOnHold, RelocationOnHold, or Other; use only when Status is Lost. |
| `--status` | enum | Lifecycle status: InProgress (1) is active, Won (2) records a successful outcome, and Lost (3) records an unsuccessful outcome; setting Won or Lost stamps the matching terminal timestamp if it is empty. |
| `--won-on` | DateTime | Read-only UTC timestamp set when Status first becomes Won; change Status rather than setting this date directly. |
| `--from-won-on` | range | |
| `--to-won-on` | range | |
| `--lost-on` | DateTime | Read-only UTC timestamp set when Status first becomes Lost; change Status rather than setting this date directly. |
| `--from-lost-on` | range | |
| `--to-lost-on` | range | |
| `--crm-updated-on` | DateTime | Read-only UTC timestamp automatically updated after CRM changes, including a stage move. |
| `--from-crm-updated-on` | range | |
| `--to-crm-updated-on` | range | |
| `--position` | int | Requested relative display order among in-progress opportunities in the current stage; the server normalizes the stage order after create or update. |
| `--from-position` | range | |
| `--to-position` | range | |
| `--utm-source` | string | Optional UTM source attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-medium` | string | Optional UTM medium attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-campaign` | string | Optional UTM campaign attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-content` | string | Optional UTM content attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-term` | string | Optional UTM search-term attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CrmOpportunity sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CrmOpportunity create options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Optional operator-facing label for this opportunity, useful when a customer has opportunities in multiple CRM boards. |
| `--crm-board-column-id` | long, required | ID of the CRM stage that contains this opportunity and determines its location access; changing it moves the opportunity and runs that stage's arrival actions. |
| `--coworker-id` | long, required | ID of the customer this opportunity tracks; a customer is required by backend validation even though the relationship metadata is nullable. |
| `--team-id` | long | Optional ID of the team associated with this opportunity. |
| `--opportunity-type-id` | long | Optional ID of the opportunity type used to categorize this CRM opportunity. |
| `--responsible-id` | long | Optional ID of the staff user responsible for following up this opportunity. |
| `--referrer-id` | long | Optional ID of the customer who referred this opportunity. |
| `--agent-id` | long | Optional ID of the customer record representing the referring agent or broker. |
| `--notes` | string | Optional internal notes about this opportunity and its follow-up. |
| `--completed` | bool | Whether this opportunity is marked complete; use Status to record whether it was won or lost. |
| `--due-date` | DateTime | Optional date and time by which this opportunity requires follow-up; the backend compares it against UTC for overdue CRM counts. |
| `--value` | decimal | Optional expected revenue amount if this opportunity is won, in the parent CRM board location's currency. |
| `--reminded` | bool | Whether a follow-up reminder has already been sent for this opportunity; this internal state is not exposed to Admin Tool schemas. |
| `--lead-source` | enum | Optional acquisition source: Web, Phone, Webinar, Referral, PrintAdvert, PurchasedList, WordOfMouth, DirectEmail, EmailMarketing, Broker, PropertyAgent, Facebook, Linkedin, Instagram, Twitter, HubbleHq, LiquidSpace, GoogleSearch, SpacePool, InstantOffices, OfficeFreedom, FlexiOffices, Workthere, Kontor, Valve, OtherSocialNetwork, or Other. |
| `--loss-reason` | enum | Optional reason for a lost opportunity: Timing, Need, PoorQualification, Price, Feature, LostMomentum, Competition, ContractTerm, Duplicate, Waitlist, NotReturningCalls, LackOfFacilities, NoPetPolicy, NoRightFit, Location, Entrance, Errors, Archived, SearchOnHold, RelocationOnHold, or Other; use only when Status is Lost. |
| `--status` | enum, required | Lifecycle status: InProgress (1) is active, Won (2) records a successful outcome, and Lost (3) records an unsuccessful outcome; setting Won or Lost stamps the matching terminal timestamp if it is empty. |
| `--won-on` | DateTime | Read-only UTC timestamp set when Status first becomes Won; change Status rather than setting this date directly. |
| `--lost-on` | DateTime | Read-only UTC timestamp set when Status first becomes Lost; change Status rather than setting this date directly. |
| `--position` | int, required | Requested relative display order among in-progress opportunities in the current stage; the server normalizes the stage order after create or update. |
| `--utm-source` | string | Optional UTM source attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-medium` | string | Optional UTM medium attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-campaign` | string | Optional UTM campaign attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-content` | string | Optional UTM content attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-term` | string | Optional UTM search-term attribution captured from the URL used to submit the originating contact or sign-up form. |

#### CrmOpportunity update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | Optional operator-facing label for this opportunity, useful when a customer has opportunities in multiple CRM boards. |
| `--crm-board-column-id` | long | ID of the CRM stage that contains this opportunity and determines its location access; changing it moves the opportunity and runs that stage's arrival actions. |
| `--coworker-id` | long | ID of the customer this opportunity tracks; a customer is required by backend validation even though the relationship metadata is nullable. |
| `--team-id` | long | Optional ID of the team associated with this opportunity. |
| `--opportunity-type-id` | long | Optional ID of the opportunity type used to categorize this CRM opportunity. |
| `--responsible-id` | long | Optional ID of the staff user responsible for following up this opportunity. |
| `--referrer-id` | long | Optional ID of the customer who referred this opportunity. |
| `--agent-id` | long | Optional ID of the customer record representing the referring agent or broker. |
| `--notes` | string | Optional internal notes about this opportunity and its follow-up. |
| `--completed` | bool | Whether this opportunity is marked complete; use Status to record whether it was won or lost. |
| `--due-date` | DateTime | Optional date and time by which this opportunity requires follow-up; the backend compares it against UTC for overdue CRM counts. |
| `--value` | decimal | Optional expected revenue amount if this opportunity is won, in the parent CRM board location's currency. |
| `--reminded` | bool | Whether a follow-up reminder has already been sent for this opportunity; this internal state is not exposed to Admin Tool schemas. |
| `--lead-source` | enum | Optional acquisition source: Web, Phone, Webinar, Referral, PrintAdvert, PurchasedList, WordOfMouth, DirectEmail, EmailMarketing, Broker, PropertyAgent, Facebook, Linkedin, Instagram, Twitter, HubbleHq, LiquidSpace, GoogleSearch, SpacePool, InstantOffices, OfficeFreedom, FlexiOffices, Workthere, Kontor, Valve, OtherSocialNetwork, or Other. |
| `--loss-reason` | enum | Optional reason for a lost opportunity: Timing, Need, PoorQualification, Price, Feature, LostMomentum, Competition, ContractTerm, Duplicate, Waitlist, NotReturningCalls, LackOfFacilities, NoPetPolicy, NoRightFit, Location, Entrance, Errors, Archived, SearchOnHold, RelocationOnHold, or Other; use only when Status is Lost. |
| `--status` | enum | Lifecycle status: InProgress (1) is active, Won (2) records a successful outcome, and Lost (3) records an unsuccessful outcome; setting Won or Lost stamps the matching terminal timestamp if it is empty. |
| `--won-on` | DateTime | Read-only UTC timestamp set when Status first becomes Won; change Status rather than setting this date directly. |
| `--lost-on` | DateTime | Read-only UTC timestamp set when Status first becomes Lost; change Status rather than setting this date directly. |
| `--position` | int | Requested relative display order among in-progress opportunities in the current stage; the server normalizes the stage order after create or update. |
| `--utm-source` | string | Optional UTM source attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-medium` | string | Optional UTM medium attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-campaign` | string | Optional UTM campaign attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-content` | string | Optional UTM content attribution captured from the URL used to submit the originating contact or sign-up form. |
| `--utm-term` | string | Optional UTM search-term attribution captured from the URL used to submit the originating contact or sign-up form. |

#### CrmOpportunity PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus crmopportunities update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CrmOpportunity (key fields)

`Id`, `Name`, `CrmBoardColumnName`, `CrmBoardColumnCrmBoardName`, `CrmBoardColumnCrmBoardBusinessName`, `CrmBoardColumnCrmBoardBusinessCurrencyCode`, `CoworkerFullName`, `CoworkerCompanyName`, `CoworkerEmail`, `TeamName`, `OpportunityTypeName`, `ResponsibleFullName`, `Notes`, `DueDate`, `Value`

#### CrmOpportunity enum values

| Option | Valid values |
| ------ | ------------ |
| `--status` | `1` InProgress, `2` Won, `3` Lost |

<!-- END:GENERATED entity=CrmOpportunities -->
