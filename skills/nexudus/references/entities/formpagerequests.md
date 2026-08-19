# FormPageRequests

<!-- BEGIN:GENERATED entity=FormPageRequests -->

A form request (FormPageRequest) sends a location's form to a customer and tracks its submission. Creating a request sends an invitation unless it is already submitted; submitted answers are stored as separate records.

FormPageRequests support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpagerequests list --agent` | List all formpagerequests |
| `nexudus formpagerequests list --id <id> --agent` | Filter by single ID |
| `nexudus formpagerequests list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpagerequests list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpagerequests list --coworker-id <value> --coworker-coworker-type <value> --agent` | Filter formpagerequests by properties |
| `nexudus formpagerequests list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpagerequests list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus formpagerequests get <id> --agent` | Get single formpagerequest |
| `nexudus formpagerequests create --coworker-id <value> --form-page-id <value> --agent` | Create formpagerequest |
| `nexudus formpagerequests update <id> --name "New Name" --agent` | Update formpagerequest |
| `nexudus formpagerequests delete <id> --yes --agent` | Delete formpagerequest (no prompt) |

#### FormPageRequest list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer invited to complete this form; cannot be changed after the request is created |
| `--coworker-coworker-type` | string | The coworker coworker type value for this form page request |
| `--coworker-full-name` | string | Display name of the linked coworker full (read-only) |
| `--coworker-company-name` | string | Display name of the linked coworker company (read-only) |
| `--coworker-billing-name` | string | Display name of the linked coworker billing (read-only) |
| `--coworker-email` | string | The coworker email value for this form page request |
| `--form-page-id` | long | ID of the form sent to the customer; the form's location owns this request |
| `--form-page-name` | string | Display name of the linked form page (read-only) |
| `--form-page-business-name` | string | Display name of the linked form page business (read-only) |
| `--sent-on` | DateTime | UTC timestamp set automatically when the request is created and the invitation is sent |
| `--from-sent-on` | range | |
| `--to-sent-on` | range | |
| `--submitted` | bool | Whether the customer has submitted the form; set automatically by the public submission workflow |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPageRequest sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FormPageRequest create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer invited to complete this form; cannot be changed after the request is created |
| `--form-page-id` | long, required | ID of the form sent to the customer; the form's location owns this request |

#### FormPageRequest update options

| Option | Type | Description |
| --- | --- | --- |

#### FormPageRequest PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus formpagerequests update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=FormPageRequests -->
