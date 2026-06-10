# Visitors

<!-- BEGIN:GENERATED entity=Visitors -->

A **Visitor** represents a person visiting a location who is not a member. Visitors are registered with their name, contact details, expected arrival time, and the host (customer) they are visiting. Visitor management includes check-in/check-out tracking and optional host approval workflows.

Visitors support Search, Get, Create, Update, Delete.
Visitors also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus visitors list --agent` | List all visitors |
| `nexudus visitors list --id <id> --agent` | Filter by single ID |
| `nexudus visitors list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus visitors list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus visitors list --full-name <value> --email <value> --agent` | Filter visitors by properties |
| `nexudus visitors list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus visitors list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus visitors get <id> --agent` | Get single visitor |
| `nexudus visitors create --business-id <value> --full-name <value> --email <value> --visitor-source <value> --host-approval-status <value> --expected-arrival <value> --agent` | Create visitor |
| `nexudus visitors update <id> --name "New Name" --agent` | Update visitor |
| `nexudus visitors delete <id> --yes --agent` | Delete visitor (no prompt) |
| `nexudus visitors run-command <key> <ids> --agent` | Run entity command |

#### Visitor list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--full-name` | string | Visitor full name |
| `--email` | string | Visitor email |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--visitor-source` | enum | Visitor source |
| `--host-approval-status` | enum | Host approval status |
| `--checked-in-at` | string | Location checked in at |
| `--notes` | string | Optional notes or comments about this visitor |
| `--customer-notes` | string | Customer notes |
| `--visit-reason` | string | Reason for visit |
| `--company-name` | string | Visitor company name |
| `--phone-number` | string | Visitor phone number |
| `--expected-arrival` | DateTime | Expected arrival date and time |
| `--from-expected-arrival` | range | |
| `--to-expected-arrival` | range | |
| `--arrived` | bool | Whether the visitor has arrived |
| `--arrival-date` | DateTime | Actual arrival date |
| `--from-arrival-date` | range | |
| `--to-arrival-date` | range | |
| `--departure-date` | DateTime | Departure date |
| `--from-departure-date` | range | |
| `--to-departure-date` | range | |
| `--notified` | bool | Whether notified is enabled |
| `--internal` | bool | Whether internal is enabled |
| `--is-tour` | bool | Whether this is a tour visit |
| `--has-agreed-terms` | bool | Whether the visitor has agreed to terms |
| `--tour-confirmed` | bool | Whether the tour is confirmed |
| `--access-control-scheduled-job-id` | string | ID of the access control scheduled job associated with this record |
| `--check-in-now` | bool | Check in the visitor now |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Visitor sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `ExpectedArrival` ascending. If no `--order-by` is specified, the API returns results ordered by `ExpectedArrival` (ascending).

#### Visitor create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--full-name` | string, required | Visitor full name |
| `--email` | string, required | Visitor email |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--visitor-source` | enum, required | Visitor source |
| `--host-approval-status` | enum, required | Host approval status |
| `--checked-in-at` | string | Location checked in at |
| `--notes` | string | Optional notes or comments about this visitor |
| `--customer-notes` | string | Customer notes |
| `--visit-reason` | string | Reason for visit |
| `--company-name` | string | Visitor company name |
| `--phone-number` | string | Visitor phone number |
| `--expected-arrival` | DateTime, required | Expected arrival date and time |
| `--arrived` | bool | Whether the visitor has arrived |
| `--arrival-date` | DateTime | Actual arrival date |
| `--departure-date` | DateTime | Departure date |
| `--notified` | bool | Whether notified is enabled |
| `--internal` | bool | Whether internal is enabled |
| `--is-tour` | bool | Whether this is a tour visit |
| `--has-agreed-terms` | bool | Whether the visitor has agreed to terms |
| `--tour-confirmed` | bool | Whether the tour is confirmed |
| `--access-control-scheduled-job-id` | string | ID of the access control scheduled job associated with this record |
| `--check-in-now` | bool | Check in the visitor now |

#### Visitor update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--full-name` | string | Visitor full name |
| `--email` | string | Visitor email |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--visitor-source` | enum | Visitor source |
| `--host-approval-status` | enum | Host approval status |
| `--checked-in-at` | string | Location checked in at |
| `--notes` | string | Optional notes or comments about this visitor |
| `--customer-notes` | string | Customer notes |
| `--visit-reason` | string | Reason for visit |
| `--company-name` | string | Visitor company name |
| `--phone-number` | string | Visitor phone number |
| `--expected-arrival` | DateTime | Expected arrival date and time |
| `--arrived` | bool | Whether the visitor has arrived |
| `--arrival-date` | DateTime | Actual arrival date |
| `--departure-date` | DateTime | Departure date |
| `--notified` | bool | Whether notified is enabled |
| `--internal` | bool | Whether internal is enabled |
| `--is-tour` | bool | Whether this is a tour visit |
| `--has-agreed-terms` | bool | Whether the visitor has agreed to terms |
| `--tour-confirmed` | bool | Whether the tour is confirmed |
| `--access-control-scheduled-job-id` | string | ID of the access control scheduled job associated with this record |

#### Visitor PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus visitors update <id> --full-name "«PII:NAME:a3f2b1c9»" --agent`

### Visitor (key fields)

`Id`, `FullName`, `Email`, `CoworkerFullName`, `HostApprovalStatus`, `Arrived`

#### Visitor enum values

| Option | Valid values |
| ------ | ------------ |
| `--visitor-source` | `1` Administrator, `2` NexIO, `3` Customer |
| `--host-approval-status` | `1` NotRequired, `2` Requested, `3` Rejected, `4` AcceptedAndHold, `5` AcceptedAndGrant |

<!-- END:GENERATED entity=Visitors -->
