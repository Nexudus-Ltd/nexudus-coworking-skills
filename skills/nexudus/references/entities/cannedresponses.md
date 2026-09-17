# CannedResponses

<!-- BEGIN:GENERATED entity=CannedResponses -->

A CannedResponse, also called a message macro, is a reusable CRM message template owned by a location and identified by a required name, optional subject, and optional HTML body.

CannedResponses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus cannedresponses list --agent` | List all cannedresponses |
| `nexudus cannedresponses list --id <id> --agent` | Filter by single ID |
| `nexudus cannedresponses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus cannedresponses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus cannedresponses list --business-name <value> --name <value> --agent` | Filter cannedresponses by properties |
| `nexudus cannedresponses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus cannedresponses list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus cannedresponses get <id> --agent` | Get single cannedresponse |
| `nexudus cannedresponses create --business-id <value> --name <value> --agent` | Create cannedresponse |
| `nexudus cannedresponses update <id> --name "New Name" --agent` | Update cannedresponse |
| `nexudus cannedresponses delete <id> --yes --agent` | Delete cannedresponse (no prompt) |

#### CannedResponse list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this message macro; the user must have access to the location |
| `--business-name` | string | Display value for Business.Name. |
| `--name` | string | Required name used to identify this reusable message macro |
| `--subject` | string | Optional subject line for the message macro |
| `--message-text` | string | Optional HTML body content for the reusable message macro |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CannedResponse sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CannedResponse create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this message macro; the user must have access to the location |
| `--name` | string, required | Required name used to identify this reusable message macro |
| `--subject` | string | Optional subject line for the message macro |
| `--message-text` | string | Optional HTML body content for the reusable message macro |

#### CannedResponse update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this message macro; the user must have access to the location |
| `--name` | string | Required name used to identify this reusable message macro |
| `--subject` | string | Optional subject line for the message macro |
| `--message-text` | string | Optional HTML body content for the reusable message macro |

### CannedResponse (key fields)

`Id`, `BusinessName`, `Name`

<!-- END:GENERATED entity=CannedResponses -->
