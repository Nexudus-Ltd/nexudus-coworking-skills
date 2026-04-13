# CoworkerLegalContentAudits

<!-- BEGIN:GENERATED entity=CoworkerLegalContentAudits -->

A **CoworkerLegalContentAudit** records when a customer accepted a specific version of a legal document at a location. Each record captures the type of legal content accepted (e.g. general terms, privacy policy, or plan-specific terms) along with the unique version identifier that was in effect at the time of acceptance.

Use these records to demonstrate compliance and to determine exactly which version of a document a customer agreed to. For tariff-specific terms (`LegalContentType = TariffTerms`), `TariffUniqueId` identifies the pricing plan whose terms were accepted. `LegalContentAuditUniqueId` identifies the precise version of the document that was shown to and accepted by the customer.

CoworkerLegalContentAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerlegalcontentaudits list --agent` | List all coworkerlegalcontentaudits |
| `nexudus coworkerlegalcontentaudits list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerlegalcontentaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerlegalcontentaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerlegalcontentaudits list --name <value> --agent` | Filter coworkerlegalcontentaudits by properties |
| `nexudus coworkerlegalcontentaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerlegalcontentaudits get <id> --agent` | Get single coworkerlegalcontentaudit |
| `nexudus coworkerlegalcontentaudits create --business-id <value> --name <value> --agent` | Create coworkerlegalcontentaudit |
| `nexudus coworkerlegalcontentaudits update <id> --name "New Name" --agent` | Update coworkerlegalcontentaudit |
| `nexudus coworkerlegalcontentaudits delete <id> --yes --agent` | Delete coworkerlegalcontentaudit (no prompt) |

#### CoworkerLegalContentAudit list filter options

`--business-id` (long), `--name`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerLegalContentAudit create options

`--business-id` (long, required), `--name` (required)

#### CoworkerLegalContentAudit update options

`--business-id` (long), `--name`

### CoworkerLegalContentAudit (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=CoworkerLegalContentAudits -->
