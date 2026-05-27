# FailedCheckins

<!-- BEGIN:GENERATED entity=FailedCheckins -->

A **FailedCheckin** records an unsuccessful check-in attempt by a coworker (see `Checkin` entity). Each record captures the coworker involved, the location where the attempt occurred, the reason for the failure, and contextual details such as the coworker's teams and tariff at the time.

Failed check-ins are read-only and generated automatically by the system when a check-in is rejected — for example, due to access restrictions, an inactive plan, or an unrecognised device. Use the `Description` field to inspect the specific failure reason.

The `Source` field indicates how the check-in was initiated (e.g. manual, Wi-Fi, app) and matches the `eCheckinSource` enum used by the `Checkin` entity.

FailedCheckins support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus failedcheckins list --agent` | List all failedcheckins |
| `nexudus failedcheckins list --id <id> --agent` | Filter by single ID |
| `nexudus failedcheckins list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus failedcheckins list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus failedcheckins list --coworker-id <value> --business-id <value> --agent` | Filter failedcheckins by properties |
| `nexudus failedcheckins list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus failedcheckins get <id> --agent` | Get single failedcheckin |
| `nexudus failedcheckins create --business-id <value> --checkin-attempt-time <value> --agent` | Create failedcheckin |
| `nexudus failedcheckins update <id> --name "New Name" --agent` | Update failedcheckin |
| `nexudus failedcheckins delete <id> --yes --agent` | Delete failedcheckin (no prompt) |

#### FailedCheckin list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--checkin-attempt-time` | DateTime | Date and time when the check-in attempt occurred |
| `--from-checkin-attempt-time` | range | |
| `--to-checkin-attempt-time` | range | |
| `--mac-addresses` | string | MAC addresses of the device used during the check-in attempt, if available |
| `--teams-at-the-time-of-checkin` | string | Comma-separated list of teams the coworker belonged to at the time of the failed check-in |
| `--tariff-at-the-time-of-checkin` | string | Name of the pricing plan (tariff) assigned to the coworker at the time of the failed check-in |
| `--description` | string | Reason or explanation for why the check-in attempt failed |
| `--checkin-attempt-time-local` | DateTime | Date/time value for checkin attempt time local |
| `--from-checkin-attempt-time-local` | range | |
| `--to-checkin-attempt-time-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FailedCheckin create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--checkin-attempt-time` | DateTime, required | Date and time when the check-in attempt occurred |
| `--mac-addresses` | string | MAC addresses of the device used during the check-in attempt, if available |
| `--teams-at-the-time-of-checkin` | string | Comma-separated list of teams the coworker belonged to at the time of the failed check-in |
| `--tariff-at-the-time-of-checkin` | string | Name of the pricing plan (tariff) assigned to the coworker at the time of the failed check-in |
| `--description` | string | Reason or explanation for why the check-in attempt failed |
| `--checkin-attempt-time-local` | DateTime | Date/time value for checkin attempt time local |

#### FailedCheckin update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--checkin-attempt-time` | DateTime | Date and time when the check-in attempt occurred |
| `--mac-addresses` | string | MAC addresses of the device used during the check-in attempt, if available |
| `--teams-at-the-time-of-checkin` | string | Comma-separated list of teams the coworker belonged to at the time of the failed check-in |
| `--tariff-at-the-time-of-checkin` | string | Name of the pricing plan (tariff) assigned to the coworker at the time of the failed check-in |
| `--description` | string | Reason or explanation for why the check-in attempt failed |
| `--checkin-attempt-time-local` | DateTime | Date/time value for checkin attempt time local |

#### FailedCheckin PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus failedcheckins update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### FailedCheckin (key fields)

`Id`, `CoworkerFullName`, `BusinessName`

<!-- END:GENERATED entity=FailedCheckins -->
