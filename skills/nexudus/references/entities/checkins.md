# Checkins

<!-- BEGIN:GENERATED entity=Checkins -->

A **Checkin** records when a customer accessed a location. To check in, a customer must hold a valid pass (`TimePass` entity) that covers the location and the time of the check-in.

If the customer does not have a valid pass but the location or network has one or more **Pay As You Go** passes configured, a pass is automatically assigned and charged to the customer at check-in time.

Check-ins can be created manually, or opened and closed automatically by **NexIO** (the front-desk Nexudus tablet app), door-access systems, or IT-network integrations. The `Source` field indicates how the check-in was created.

Checkins support Search, Get, Create, Update, Delete.
Checkins also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus checkins list --agent` | List all checkins |
| `nexudus checkins list --id <id> --agent` | Filter by single ID |
| `nexudus checkins list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus checkins list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus checkins list --from-time <value> --to-time <value> --agent` | Filter checkins by properties |
| `nexudus checkins list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus checkins get <id> --agent` | Get single checkin |
| `nexudus checkins create --business-id <value> --from-time <value> --agent` | Create checkin |
| `nexudus checkins update <id> --name "New Name" --agent` | Update checkin |
| `nexudus checkins delete <id> --yes --agent` | Delete checkin (no prompt) |
| `nexudus checkins run-command <key> <ids> --agent` | Run entity command |

#### Checkin list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--from-time` | DateTime | Date and time the customer checked in |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | Date and time the customer checked out. Null while the check-in is still open |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--counts-towards-plan-limits` | bool | Whether counts towards plan limits is enabled |
| `--coworker-time-pass-guid` | string | Unique identifier (GUID) for the coworker time pass |
| `--auto-checkout` | bool | Whether auto checkout is enabled |
| `--last-activity` | DateTime | Date/time value for last activity |
| `--from-last-activity` | range | |
| `--to-last-activity` | range | |
| `--mac-addresses` | string | MAC addresses of devices detected during a network-activity check-in |
| `--teams-at-checkin` | string | Teams the customer belonged to when the check-in was recorded |
| `--tariff-at-checkin` | string | Product (tariff) assigned to the customer when the check-in was recorded |
| `--validate-checkin-job-id` | string | ID of the validate checkin job associated with this record |
| `--from-time-local` | DateTime | Date/time value for from time local |
| `--from-from-time-local` | range | |
| `--to-from-time-local` | range | |
| `--to-time-local` | DateTime | Date/time value for to time local |
| `--from-to-time-local` | range | |
| `--to-to-time-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Checkin create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--from-time` | DateTime, required | Date and time the customer checked in |
| `--to-time` | DateTime | Date and time the customer checked out. Null while the check-in is still open |
| `--counts-towards-plan-limits` | bool | Whether counts towards plan limits is enabled |
| `--coworker-time-pass-guid` | string | Unique identifier (GUID) for the coworker time pass |
| `--auto-checkout` | bool | Whether auto checkout is enabled |
| `--last-activity` | DateTime | Date/time value for last activity |
| `--mac-addresses` | string | MAC addresses of devices detected during a network-activity check-in |
| `--teams-at-checkin` | string | Teams the customer belonged to when the check-in was recorded |
| `--tariff-at-checkin` | string | Product (tariff) assigned to the customer when the check-in was recorded |
| `--validate-checkin-job-id` | string | ID of the validate checkin job associated with this record |
| `--from-time-local` | DateTime | Date/time value for from time local |
| `--to-time-local` | DateTime | Date/time value for to time local |

#### Checkin update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--from-time` | DateTime | Date and time the customer checked in |
| `--to-time` | DateTime | Date and time the customer checked out. Null while the check-in is still open |
| `--counts-towards-plan-limits` | bool | Whether counts towards plan limits is enabled |
| `--coworker-time-pass-guid` | string | Unique identifier (GUID) for the coworker time pass |
| `--auto-checkout` | bool | Whether auto checkout is enabled |
| `--last-activity` | DateTime | Date/time value for last activity |
| `--mac-addresses` | string | MAC addresses of devices detected during a network-activity check-in |
| `--teams-at-checkin` | string | Teams the customer belonged to when the check-in was recorded |
| `--tariff-at-checkin` | string | Product (tariff) assigned to the customer when the check-in was recorded |
| `--validate-checkin-job-id` | string | ID of the validate checkin job associated with this record |
| `--from-time-local` | DateTime | Date/time value for from time local |
| `--to-time-local` | DateTime | Date/time value for to time local |

#### Checkin PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus checkins update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### Checkin (key fields)

`Id`, `CoworkerFullName`, `BusinessName`, `Source`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=Checkins -->
