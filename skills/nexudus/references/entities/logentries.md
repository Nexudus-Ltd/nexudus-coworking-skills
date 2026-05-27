# LogEntries

<!-- BEGIN:GENERATED entity=LogEntries -->

A **LogEntry** records a system event or error for diagnostic and auditing purposes. Log entries are categorised by type (error, warning, information, payment error, integration error, etc.) and linked to the business where they occurred.

LogEntries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus logentries list --agent` | List all logentries |
| `nexudus logentries list --id <id> --agent` | Filter by single ID |
| `nexudus logentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus logentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus logentries list --business-id <value> --log-entry-type <value> --agent` | Filter logentries by properties |
| `nexudus logentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus logentries get <id> --agent` | Get single logentry |

#### LogEntry list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--log-entry-type` | enum | The log entry type value for this log entry |
| `--description` | string | Free-text description of this log entry |
| `--action-by` | string | The action by value for this log entry |
| `--entity-name` | string | The entity name value for this log entry |
| `--entity-id` | int | ID of the entity associated with this record |
| `--from-entity-id` | range | |
| `--to-entity-id` | range | |
| `--obsolete` | bool | Whether obsolete is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### LogEntry enum values

| Option | Valid values |
| ------ | ------------ |
| `--log-entry-type` | `1` Error, `2` Warning, `3` Information, `4` InvoicingError, `5` PaymentError, `6` IntegrationError, `7` AccessIntegrationError, `99` Other |

<!-- END:GENERATED entity=LogEntries -->
