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

`--coworker-id`, `--form-page-id`, `--sent-on`, `--submitted`

#### FormPageRequest create options

`--coworker-id` (required), `--form-page-id` (required), `--sent-on`, `--submitted`, `--form-page-answers` (list, repeat flag), `--added-form-page-answers` (list, repeat flag), `--removed-form-page-answers` (list, repeat flag)

#### FormPageRequest update options

`--coworker-id`, `--form-page-id`, `--sent-on`, `--submitted`, `--form-page-answers` (list, repeat flag), `--added-form-page-answers` (list, repeat flag), `--removed-form-page-answers` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `FormPageAnswers`, `AddedFormPageAnswers`, `RemovedFormPageAnswers`

<!-- END:GENERATED entity=FormPageRequests -->
