# FormPageAnswers

<!-- BEGIN:GENERATED entity=FormPageAnswers -->

A **FormPageAnswer** stores a customer's response to a single question on a form page. Each answer links to a specific form page question and the request (submission) that contains it.

FormPageAnswers support Search, Get, Create, Update (no Delete via API).

| Command | Description |
| --- | --- |
| `nexudus formpageanswers list --agent` | List all formpageanswers |
| `nexudus formpageanswers list --id <id> --agent` | Filter by single ID |
| `nexudus formpageanswers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpageanswers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpageanswers list --form-page-request-id <value> --form-page-question-id <value> --agent` | Filter formpageanswers by properties |
| `nexudus formpageanswers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpageanswers get <id> --agent` | Get single formpageanswer |
| `nexudus formpageanswers create --form-page-question-id <value> --agent` | Create formpageanswer |
| `nexudus formpageanswers update <id> --name "New Name" --agent` | Update formpageanswer |

#### FormPageAnswer list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-request-id` | long | ID of the form page request linked to this record |
| `--form-page-question-id` | long | ID of the form page question linked to this record |
| `--value` | string | The value value for this form page answer |
| `--new-file-value-url` | string | URL of a new file to upload as the file value |
| `--clear-file-value-file` | bool | Set to true to remove the current file value file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPageAnswer create options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-request-id` | long | ID of the form page request linked to this record |
| `--form-page-question-id` | long, required | ID of the form page question linked to this record |
| `--value` | string | The value value for this form page answer |
| `--new-file-value-url` | string | URL of a new file to upload as the file value |
| `--clear-file-value-file` | bool | Set to true to remove the current file value file |

#### FormPageAnswer update options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-request-id` | long | ID of the form page request linked to this record |
| `--form-page-question-id` | long | ID of the form page question linked to this record |
| `--value` | string | The value value for this form page answer |
| `--new-file-value-url` | string | URL of a new file to upload as the file value |
| `--clear-file-value-file` | bool | Set to true to remove the current file value file |

#### FormPageAnswer PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--form-page-request-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--form-page-request-coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus formpageanswers update <id> --form-page-request-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=FormPageAnswers -->
