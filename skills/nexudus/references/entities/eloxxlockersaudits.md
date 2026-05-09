# EloxxLockersAudits

<!-- BEGIN:GENERATED entity=EloxxLockersAudits -->

EloxxLockersAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eloxxlockersaudits list --agent` | List all eloxxlockersaudits |
| `nexudus eloxxlockersaudits list --id <id> --agent` | Filter by single ID |
| `nexudus eloxxlockersaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eloxxlockersaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eloxxlockersaudits list --business-id <value> --floor-plan-desk-id <value> --agent` | Filter eloxxlockersaudits by properties |
| `nexudus eloxxlockersaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eloxxlockersaudits get <id> --agent` | Get single eloxxlockersaudit |
| `nexudus eloxxlockersaudits create --business-id <value> --floor-plan-desk-id <value> --coworker-id <value> --description <value> --action <value> --tile-audit-type <value> --agent` | Create eloxxlockersaudit |
| `nexudus eloxxlockersaudits update <id> --name "New Name" --agent` | Update eloxxlockersaudit |
| `nexudus eloxxlockersaudits delete <id> --yes --agent` | Delete eloxxlockersaudit (no prompt) |

#### EloxxLockersAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--description` | string |  |
| `--action-by` | string |  |
| `--action` | enum |  |
| `--tile-audit-type` | enum |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EloxxLockersAudit create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--floor-plan-desk-id` | long, required |  |
| `--coworker-id` | long, required |  |
| `--description` | string, required |  |
| `--action-by` | string |  |
| `--action` | enum, required |  |
| `--tile-audit-type` | enum, required |  |

#### EloxxLockersAudit update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--description` | string |  |
| `--action-by` | string |  |
| `--action` | enum |  |
| `--tile-audit-type` | enum |  |

<!-- END:GENERATED entity=EloxxLockersAudits -->
