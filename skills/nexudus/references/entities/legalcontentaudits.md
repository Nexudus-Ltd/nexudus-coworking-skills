# LegalContentAudits

<!-- BEGIN:GENERATED entity=LegalContentAudits -->

A LegalContentAudit is a read-only version history of legal content for a location, including general, checkout, visitor, privacy, cookie, and plan terms.

LegalContentAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus legalcontentaudits list --agent` | List all legalcontentaudits |
| `nexudus legalcontentaudits list --id <id> --agent` | Filter by single ID |
| `nexudus legalcontentaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus legalcontentaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus legalcontentaudits list --business-id <value> --business-name <value> --agent` | Filter legalcontentaudits by properties |
| `nexudus legalcontentaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus legalcontentaudits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus legalcontentaudits get <id> --agent` | Get single legalcontentaudit |
| `nexudus legalcontentaudits create  --agent` | Create legalcontentaudit |
| `nexudus legalcontentaudits update <id> --name "New Name" --agent` | Update legalcontentaudit |
| `nexudus legalcontentaudits delete <id> --yes --agent` | Delete legalcontentaudit (no prompt) |

#### LegalContentAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location whose legal content version is recorded. |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--name` | string | System-generated version label using the next version number and the location-local creation date. |
| `--content` | string | Snapshot of the legal content text when this version was created. |
| `--author` | string | User name or system account recorded as creating this legal content version. |
| `--tariff-unique-id` | string | Unique ID of the plan whose terms this version snapshots; null for location-wide legal content. |
| `--legal-content-type` | enum | Type of legal content snapshot: GeneralTerms, VisitorTerms, CheckoutTerms, PrivacyPolicy, CookiesPolicy, or TariffTerms. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### LegalContentAudit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### LegalContentAudit create options

| Option | Type | Description |
| --- | --- | --- |

#### LegalContentAudit update options

| Option | Type | Description |
| --- | --- | --- |

<!-- END:GENERATED entity=LegalContentAudits -->
