# Visitors

<!-- BEGIN:GENERATED entity=Visitors -->

A Visitor is a guest expected at a location, optionally hosted by a customer. Visitors can be registered by an administrator or Admin Agent, from the customer portal, app, AI assistant, or NexIO reception tablet, as guests on a booking, or as public tour requests; the record tracks contact details, arrival, tours, and host approval.

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
| `--business-id` | long | ID of the location this visitor is visiting; required. |
| `--full-name` | string | Visitor's full name; required. |
| `--email` | string | Visitor's email address; required and validated as an email address. |
| `--coworker-id` | long | ID of the customer hosting this visitor; required. |
| `--coworker-type` | string | Host coworker type |
| `--coworker-full-name` | string | Host coworker full name |
| `--coworker-company-name` | string | Host coworker company name |
| `--coworker-billing-name` | string | Host coworker billing name |
| `--coworker-email` | string | Host coworker email |
| `--coworker-team-names` | string | Host coworker team names |
| `--visitor-source` | enum | How the visitor was registered: Administrator for staff and Admin Agent registrations, Customer for registrations from the customer portal, app, or AI assistant, or NexIO for the reception tablet app; booking guests are synchronized from their booking. |
| `--host-approval-status` | enum | Host approval workflow state: NotRequired, Requested, Rejected, AcceptedAndHold, or AcceptedAndGrant; manage pending approvals with the dedicated visitor approval tool. |
| `--visitor-code` | string | System-generated visitor access code, created for eligible upcoming visits and used to locate the visitor at the location. |
| `--checked-in-at` | string | Check-in location/value; use Arrived, ArrivalDate, and DepartureDate for the visitor's current visit status. |
| `--notes` | string | Optional internal staff notes about the visitor, limited to 1,024 characters and not shown to the visitor. |
| `--customer-notes` | string | Optional notes supplied by the hosting customer, limited to 1,024 characters; read-only for administrators. |
| `--visit-reason` | string | Optional reason the visitor is coming to the location. |
| `--company-name` | string | Optional company or organization the visitor represents. |
| `--phone-number` | string | Optional phone number for contacting the visitor. |
| `--expected-arrival` | DateTime | Expected arrival date and time, stored in UTC and required when creating a visitor. |
| `--from-expected-arrival` | range | |
| `--to-expected-arrival` | range | |
| `--arrived` | bool | Whether the visitor is currently checked in; maintained by the visitor check-in and check-out workflow. |
| `--arrival-date` | DateTime | UTC timestamp when the visitor checked in, maintained by the check-in workflow. |
| `--from-arrival-date` | range | |
| `--to-arrival-date` | range | |
| `--departure-date` | DateTime | UTC timestamp when the visitor checked out, maintained by the check-out workflow. |
| `--from-departure-date` | range | |
| `--to-departure-date` | range | |
| `--internal` | bool | Internal booking-visitor classification set when the visitor matches a customer and the location excludes known customers from visitor registration. |
| `--is-tour` | bool | Whether this visit is a tour; tour requests from the public portal or AI assistant create tour visitors, which require a hosting customer and use the tour confirmation workflow. |
| `--has-agreed-terms` | bool | Whether the visitor has accepted the applicable terms; maintained by the visitor-facing legal flow. |
| `--tour-confirmed` | bool | Whether a tour visit has been confirmed; maintained by the dedicated tour confirmation workflow and set automatically on check-in. |
| `--check-in-now` | bool | Whether to check the visitor in immediately when creating the record; also sets ArrivalDate to the current UTC time and clears any departure time. |
| `--is-customer` | bool | Internal flag set for booking visitors whose email already belongs to a customer at the location. |
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
| `--business-id` | long, required | ID of the location this visitor is visiting; required. |
| `--full-name` | string, required | Visitor's full name; required. |
| `--email` | string, required | Visitor's email address; required and validated as an email address. |
| `--coworker-id` | long | ID of the customer hosting this visitor; required. |
| `--visitor-source` | enum, required | How the visitor was registered: Administrator for staff and Admin Agent registrations, Customer for registrations from the customer portal, app, or AI assistant, or NexIO for the reception tablet app; booking guests are synchronized from their booking. |
| `--host-approval-status` | enum, required | Host approval workflow state: NotRequired, Requested, Rejected, AcceptedAndHold, or AcceptedAndGrant; manage pending approvals with the dedicated visitor approval tool. |
| `--checked-in-at` | string | Check-in location/value; use Arrived, ArrivalDate, and DepartureDate for the visitor's current visit status. |
| `--notes` | string | Optional internal staff notes about the visitor, limited to 1,024 characters and not shown to the visitor. |
| `--visit-reason` | string | Optional reason the visitor is coming to the location. |
| `--company-name` | string | Optional company or organization the visitor represents. |
| `--phone-number` | string | Optional phone number for contacting the visitor. |
| `--expected-arrival` | DateTime, required | Expected arrival date and time, stored in UTC and required when creating a visitor. |
| `--internal` | bool | Internal booking-visitor classification set when the visitor matches a customer and the location excludes known customers from visitor registration. |
| `--is-tour` | bool | Whether this visit is a tour; tour requests from the public portal or AI assistant create tour visitors, which require a hosting customer and use the tour confirmation workflow. |
| `--check-in-now` | bool | Whether to check the visitor in immediately when creating the record; also sets ArrivalDate to the current UTC time and clears any departure time. |
| `--is-customer` | bool | Internal flag set for booking visitors whose email already belongs to a customer at the location. |

#### Visitor update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this visitor is visiting; required. |
| `--full-name` | string | Visitor's full name; required. |
| `--email` | string | Visitor's email address; required and validated as an email address. |
| `--coworker-id` | long | ID of the customer hosting this visitor; required. |
| `--visitor-source` | enum | How the visitor was registered: Administrator for staff and Admin Agent registrations, Customer for registrations from the customer portal, app, or AI assistant, or NexIO for the reception tablet app; booking guests are synchronized from their booking. |
| `--host-approval-status` | enum | Host approval workflow state: NotRequired, Requested, Rejected, AcceptedAndHold, or AcceptedAndGrant; manage pending approvals with the dedicated visitor approval tool. |
| `--checked-in-at` | string | Check-in location/value; use Arrived, ArrivalDate, and DepartureDate for the visitor's current visit status. |
| `--notes` | string | Optional internal staff notes about the visitor, limited to 1,024 characters and not shown to the visitor. |
| `--visit-reason` | string | Optional reason the visitor is coming to the location. |
| `--company-name` | string | Optional company or organization the visitor represents. |
| `--phone-number` | string | Optional phone number for contacting the visitor. |
| `--expected-arrival` | DateTime | Expected arrival date and time, stored in UTC and required when creating a visitor. |
| `--internal` | bool | Internal booking-visitor classification set when the visitor matches a customer and the location excludes known customers from visitor registration. |
| `--is-tour` | bool | Whether this visit is a tour; tour requests from the public portal or AI assistant create tour visitors, which require a hosting customer and use the tour confirmation workflow. |
| `--is-customer` | bool | Internal flag set for booking visitors whose email already belongs to a customer at the location. |

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
