# FormPageRequests

<!-- BEGIN:GENERATED entity=FormPageRequests -->

FormPageRequests support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpagerequests list --agent` | List all formpagerequests |
| `nexudus formpagerequests list --id <id> --agent` | Filter by single ID |
| `nexudus formpagerequests list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpagerequests list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpagerequests list --coworker-id <value> --form-page-id <value> --agent` | Filter formpagerequests by properties |
| `nexudus formpagerequests list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpagerequests get <id> --agent` | Get single formpagerequest |
| `nexudus formpagerequests create --coworker-id <value> --form-page-id <value> --agent` | Create formpagerequest |
| `nexudus formpagerequests update <id> --name "New Name" --agent` | Update formpagerequest |
| `nexudus formpagerequests delete <id> --yes --agent` | Delete formpagerequest (no prompt) |

#### FormPageRequest list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long |  |
| `--form-page-id` | long |  |
| `--sent-on` | DateTime |  |
| `--from-sent-on` | range | |
| `--to-sent-on` | range | |
| `--submitted` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPageRequest create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required |  |
| `--form-page-id` | long, required |  |
| `--sent-on` | DateTime |  |
| `--submitted` | bool |  |

#### FormPageRequest update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long |  |
| `--form-page-id` | long |  |
| `--sent-on` | DateTime |  |
| `--submitted` | bool |  |

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
