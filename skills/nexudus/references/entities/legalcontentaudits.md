# LegalContentAudits

<!-- BEGIN:GENERATED entity=LegalContentAudits -->

LegalContentAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus legalcontentaudits list --agent` | List all legalcontentaudits |
| `nexudus legalcontentaudits list --id <id> --agent` | Filter by single ID |
| `nexudus legalcontentaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus legalcontentaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus legalcontentaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus legalcontentaudits get <id> --agent` | Get single legalcontentaudit |
| `nexudus legalcontentaudits create  --agent` | Create legalcontentaudit |
| `nexudus legalcontentaudits update <id> --name "New Name" --agent` | Update legalcontentaudit |
| `nexudus legalcontentaudits delete <id> --yes --agent` | Delete legalcontentaudit (no prompt) |

#### LegalContentAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### LegalContentAudit create options

| Option | Type | Description |
| --- | --- | --- |

#### LegalContentAudit update options

| Option | Type | Description |
| --- | --- | --- |

<!-- END:GENERATED entity=LegalContentAudits -->
