# CrmBoards

<!-- BEGIN:GENERATED entity=CrmBoards -->

A **CrmBoard** represents a Customer Relationship Management board used to automate processes and communication with current and potential customers.

Each board represents a common sales or operational scenario (e.g. onboarding new members, offboarding cancellations, or managing a sales pipeline). Boards contain CRM stages (`CrmBoardColumn` entity) that define the steps opportunities move through, and each stage can trigger actions such as sending message macros or creating task lists.

Nexudus provides built-in templates (e.g. sales pipeline with or without digital signature) that can be used as-is or customised by adding, removing, or editing stages. Boards can also be built from scratch.

CrmBoards support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmboards list --agent` | List all crmboards |
| `nexudus crmboards list --id <id> --agent` | Filter by single ID |
| `nexudus crmboards list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmboards list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmboards list --name <value> --agent` | Filter crmboards by properties |
| `nexudus crmboards list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmboards list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus crmboards get <id> --agent` | Get single crmboard |
| `nexudus crmboards create --business-id <value> --name <value> --agent` | Create crmboard |
| `nexudus crmboards update <id> --name "New Name" --agent` | Update crmboard |
| `nexudus crmboards delete <id> --yes --agent` | Delete crmboard (no prompt) |

#### CrmBoard list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Board name identifying the CRM process (e.g. 'Sales Pipeline', 'Onboarding') |
| `--archived` | bool | Whether the board is archived. Archived boards are hidden from the active board list but retain their data |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CrmBoard sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CrmBoard create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Board name identifying the CRM process (e.g. 'Sales Pipeline', 'Onboarding') |
| `--archived` | bool | Whether the board is archived. Archived boards are hidden from the active board list but retain their data |

#### CrmBoard update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Board name identifying the CRM process (e.g. 'Sales Pipeline', 'Onboarding') |
| `--archived` | bool | Whether the board is archived. Archived boards are hidden from the active board list but retain their data |

### CrmBoard (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=CrmBoards -->
