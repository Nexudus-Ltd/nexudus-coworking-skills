# FormPages

<!-- BEGIN:GENERATED entity=FormPages -->

A form page (FormPage) is a location-specific set of questions that administrators can send to customers or publish online for completion. Submissions can add customers to a CRM stage and create a task for a responsible user.

FormPages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpages list --agent` | List all formpages |
| `nexudus formpages list --id <id> --agent` | Filter by single ID |
| `nexudus formpages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpages list --business-id <value> --business-name <value> --agent` | Filter formpages by properties |
| `nexudus formpages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus formpages get <id> --agent` | Get single formpage |
| `nexudus formpages create --business-id <value> --name <value> --description <value> --agent` | Create formpage |
| `nexudus formpages update <id> --name "New Name" --agent` | Update formpage |
| `nexudus formpages delete <id> --yes --agent` | Delete formpage (no prompt) |

#### FormPage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this form page; the Admin Tool normally supplies it from the current location context |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--business-web-address` | string |  |
| `--name` | string | Required name used by administrators to identify this form page |
| `--description` | string | Required free-text description explaining the purpose of this form |
| `--active` | bool | Whether this form is active and available for use |
| `--crm-board-column-id` | long | ID of the optional CRM board column that receives customers when they submit this form |
| `--crm-board-column-name` | string | Display name of the linked crm board column (read-only) |
| `--crm-board-column-crm-board-id` | int | ID of the crm board column crm board associated with this record |
| `--from-crm-board-column-crm-board-id` | range | |
| `--to-crm-board-column-crm-board-id` | range | |
| `--crm-board-column-crm-board-name` | string | Display name of the linked crm board column crm board (read-only) |
| `--responsible-id` | long | ID of the optional user assigned an email-notified customer task when this form is submitted |
| `--responsible-full-name` | string | Display name of the linked responsible full (read-only) |
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
| `--business-id` | long, required | ID of the location that owns this form page; the Admin Tool normally supplies it from the current location context |
| `--name` | string, required | Required name used by administrators to identify this form page |
| `--description` | string, required | Required free-text description explaining the purpose of this form |
| `--active` | bool | Whether this form is active and available for use |
| `--crm-board-column-id` | long | ID of the optional CRM board column that receives customers when they submit this form |
| `--responsible-id` | long | ID of the optional user assigned an email-notified customer task when this form is submitted |

#### FormPage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this form page; the Admin Tool normally supplies it from the current location context |
| `--name` | string | Required name used by administrators to identify this form page |
| `--description` | string | Required free-text description explaining the purpose of this form |
| `--active` | bool | Whether this form is active and available for use |
| `--crm-board-column-id` | long | ID of the optional CRM board column that receives customers when they submit this form |
| `--responsible-id` | long | ID of the optional user assigned an email-notified customer task when this form is submitted |

#### FormPage PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus formpages update <id> --responsible-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=FormPages -->
