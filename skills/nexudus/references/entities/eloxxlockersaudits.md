# EloxxLockersAudits

<!-- BEGIN:GENERATED entity=EloxxLockersAudits -->

An **EloxxLockersAudit** records an audit trail entry for Eloxx smart locker operations. Each record logs an action (unlock, release, or assign) along with its success or failure status, the associated customer, and a description of the event.

EloxxLockersAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eloxxlockersaudits list --agent` | List all eloxxlockersaudits |
| `nexudus eloxxlockersaudits list --id <id> --agent` | Filter by single ID |
| `nexudus eloxxlockersaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eloxxlockersaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eloxxlockersaudits list --business-id <value> --business-name <value> --agent` | Filter eloxxlockersaudits by properties |
| `nexudus eloxxlockersaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eloxxlockersaudits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus eloxxlockersaudits get <id> --agent` | Get single eloxxlockersaudit |
| `nexudus eloxxlockersaudits create --business-id <value> --floor-plan-desk-id <value> --coworker-id <value> --description <value> --action <value> --tile-audit-type <value> --agent` | Create eloxxlockersaudit |
| `nexudus eloxxlockersaudits update <id> --name "New Name" --agent` | Update eloxxlockersaudit |
| `nexudus eloxxlockersaudits delete <id> --yes --agent` | Delete eloxxlockersaudit (no prompt) |

#### EloxxLockersAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--floor-plan-desk-name` | string | Display name of the linked floor plan desk (read-only) |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-coworker-type` | string | The coworker coworker type value for this eloxx lockers audit |
| `--coworker-full-name` | string | Display name of the linked coworker full (read-only) |
| `--coworker-billing-name` | string | Display name of the linked coworker billing (read-only) |
| `--coworker-company-name` | string | Display name of the linked coworker company (read-only) |
| `--coworker-team-names` | string | The coworker team names value for this eloxx lockers audit |
| `--description` | string | Free-text description of this eloxx lockers audit |
| `--action-by` | string | The action by value for this eloxx lockers audit |
| `--action` | enum | The action value for this eloxx lockers audit |
| `--tile-audit-type` | enum | The tile audit type value for this eloxx lockers audit |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EloxxLockersAudit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EloxxLockersAudit create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--floor-plan-desk-id` | long, required | ID of the floor plan desk linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--description` | string, required | Free-text description of this eloxx lockers audit |
| `--action-by` | string | The action by value for this eloxx lockers audit |
| `--action` | enum, required | The action value for this eloxx lockers audit |
| `--tile-audit-type` | enum, required | The tile audit type value for this eloxx lockers audit |

#### EloxxLockersAudit update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--description` | string | Free-text description of this eloxx lockers audit |
| `--action-by` | string | The action by value for this eloxx lockers audit |
| `--action` | enum | The action value for this eloxx lockers audit |
| `--tile-audit-type` | enum | The tile audit type value for this eloxx lockers audit |

#### EloxxLockersAudit PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus eloxxlockersaudits update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### EloxxLockersAudit enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` Unlock, `3` Release, `4` Assign |
| `--tile-audit-type` | `1` Success, `2` Failure |

<!-- END:GENERATED entity=EloxxLockersAudits -->
