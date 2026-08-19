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
| `nexudus coworkerlegalcontentaudits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerlegalcontentaudits get <id> --agent` | Get single coworkerlegalcontentaudit |
| `nexudus coworkerlegalcontentaudits create --business-id <value> --name <value> --agent` | Create coworkerlegalcontentaudit |
| `nexudus coworkerlegalcontentaudits update <id> --name "New Name" --agent` | Update coworkerlegalcontentaudit |
| `nexudus coworkerlegalcontentaudits delete <id> --yes --agent` | Delete coworkerlegalcontentaudit (no prompt) |

#### CoworkerLegalContentAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer who accepted the legal content |
| `--business-id` | long | ID of the location where the legal content was accepted |
| `--name` | string | Name of the legal content document that was accepted |
| `--legal-content-type` | enum | Type of legal document accepted: GeneralTerms, VisitorTerms, CheckoutTerms, PrivacyPolicy, CookiesPolicy, or TariffTerms |
| `--tariff-unique-id` | string | Unique identifier of the pricing plan whose terms were accepted; only set when LegalContentType is TariffTerms |
| `--legal-content-audit-unique-id` | string | Unique identifier of the specific version of the legal document that was in effect and accepted by the customer at the time of acceptance |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerLegalContentAudit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerLegalContentAudit create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location where the legal content was accepted |
| `--name` | string, required | Name of the legal content document that was accepted |

#### CoworkerLegalContentAudit update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location where the legal content was accepted |
| `--name` | string | Name of the legal content document that was accepted |

### CoworkerLegalContentAudit (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=CoworkerLegalContentAudits -->
