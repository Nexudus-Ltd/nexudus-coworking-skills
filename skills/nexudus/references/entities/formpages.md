# FormPages

<!-- BEGIN:GENERATED entity=FormPages -->

A **FormPage** represents a custom form that can be presented to customers during sign-up, check-in, or other workflows. Forms collect structured data through configurable questions and can be linked to specific pricing plans or events.

FormPages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpages list --agent` | List all formpages |
| `nexudus formpages list --id <id> --agent` | Filter by single ID |
| `nexudus formpages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpages list --business-id <value> --name <value> --agent` | Filter formpages by properties |
| `nexudus formpages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus formpages get <id> --agent` | Get single formpage |
| `nexudus formpages create --business-id <value> --name <value> --description <value> --agent` | Create formpage |
| `nexudus formpages update <id> --name "New Name" --agent` | Update formpage |
| `nexudus formpages delete <id> --yes --agent` | Delete formpage (no prompt) |

#### FormPage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this form page |
| `--description` | string | Free-text description of this form page |
| `--active` | bool | Whether this form page is currently active |
| `--crm-board-column-id` | long | ID of the crm board column linked to this record |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FormPage create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this form page |
| `--description` | string, required | Free-text description of this form page |
| `--active` | bool | Whether this form page is currently active |
| `--crm-board-column-id` | long | ID of the crm board column linked to this record |
| `--responsible-id` | long | ID of the responsible linked to this record |

#### FormPage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this form page |
| `--description` | string | Free-text description of this form page |
| `--active` | bool | Whether this form page is currently active |
| `--crm-board-column-id` | long | ID of the crm board column linked to this record |
| `--responsible-id` | long | ID of the responsible linked to this record |

#### FormPage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus formpages update <id> --responsible-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=FormPages -->
