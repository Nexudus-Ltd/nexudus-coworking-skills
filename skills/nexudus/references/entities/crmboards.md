# CrmBoards

<!-- BEGIN:GENERATED entity=CrmBoards -->

A CRM board is a location-scoped workflow, such as a sales pipeline or customer onboarding process, that organizes opportunities into stages managed as separate CRM stage records.

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
| `--business-id` | long | ID of the location that owns this CRM board. |
| `--name` | string | Required unique name that identifies this CRM workflow board, such as Sales Pipeline or Onboarding. |
| `--archived` | bool | Whether this board is archived; changing it from false to true archives its opportunities, and automated CRM triggers generally ignore its stages. |
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
| `--business-id` | long, required | ID of the location that owns this CRM board. |
| `--name` | string, required | Required unique name that identifies this CRM workflow board, such as Sales Pipeline or Onboarding. |
| `--archived` | bool | Whether this board is archived; changing it from false to true archives its opportunities, and automated CRM triggers generally ignore its stages. |

#### CrmBoard update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this CRM board. |
| `--name` | string | Required unique name that identifies this CRM workflow board, such as Sales Pipeline or Onboarding. |
| `--archived` | bool | Whether this board is archived; changing it from false to true archives its opportunities, and automated CRM triggers generally ignore its stages. |

### CrmBoard (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=CrmBoards -->
