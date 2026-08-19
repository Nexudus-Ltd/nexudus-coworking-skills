# FormPageAnswers

<!-- BEGIN:GENERATED entity=FormPageAnswers -->

A form answer (FormPageAnswer) is a read-only customer response to one form question. Answers are created by the public submission workflow and can be reviewed with their request, question, and associated event or contract context.

FormPageAnswers support Search, Get, Create, Update (no Delete via API).

| Command | Description |
| --- | --- |
| `nexudus formpageanswers list --agent` | List all formpageanswers |
| `nexudus formpageanswers list --id <id> --agent` | Filter by single ID |
| `nexudus formpageanswers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpageanswers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpageanswers list --form-page-request-id <value> --form-page-request-coworker-full-name <value> --agent` | Filter formpageanswers by properties |
| `nexudus formpageanswers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpageanswers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus formpageanswers get <id> --agent` | Get single formpageanswer |
| `nexudus formpageanswers create --form-page-question-id <value> --agent` | Create formpageanswer |
| `nexudus formpageanswers update <id> --name "New Name" --agent` | Update formpageanswer |

#### FormPageAnswer list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-request-id` | long | ID of the form request that contains this submitted answer |
| `--form-page-request-coworker-full-name` | string | Display name of the linked form page request coworker full (read-only) |
| `--form-page-request-coworker-id` | int | ID of the form page request coworker associated with this record |
| `--from-form-page-request-coworker-id` | range | |
| `--to-form-page-request-coworker-id` | range | |
| `--form-page-request-coworker-email` | string | The form page request coworker email value for this form page answer |
| `--form-page-question-id` | long | ID of the form question answered by the customer; the question's form location owns this answer |
| `--form-page-question-text` | string | The form page question text value for this form page answer |
| `--form-page-question-question-type` | string | The form page question question type value for this form page answer |
| `--form-page-question-display-order` | int | The form page question display order value for this form page answer |
| `--from-form-page-question-display-order` | range | |
| `--to-form-page-question-display-order` | range | |
| `--form-page-question-form-page-name` | string | Display name of the linked form page question form page (read-only) |
| `--form-page-question-form-page-id` | int | ID of the form page question form page associated with this record |
| `--from-form-page-question-form-page-id` | range | |
| `--to-form-page-question-form-page-id` | range | |
| `--form-page-question-form-page-business-id` | int | ID of the form page question form page business associated with this record |
| `--from-form-page-question-form-page-business-id` | range | |
| `--to-form-page-question-form-page-business-id` | range | |
| `--form-page-question-form-page-business-name` | string | Display name of the linked form page question form page business (read-only) |
| `--value` | string | Customer's submitted answer text; for a Binary question this is the stored filename rather than file content |
| `--file-value-file-name` | string | Current file name of the file value (read-only; upload via the corresponding URL field) |
| `--new-file-value-url` | string | URL of a new file to upload as the file value |
| `--clear-file-value-file` | bool | Set to true to remove the current file value file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FormPageAnswer sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FormPageAnswer create options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-request-id` | long | ID of the form request that contains this submitted answer |
| `--form-page-question-id` | long, required | ID of the form question answered by the customer; the question's form location owns this answer |
| `--new-file-value-url` | string | URL of a new file to upload as the file value |
| `--clear-file-value-file` | bool | Set to true to remove the current file value file |

#### FormPageAnswer update options

| Option | Type | Description |
| --- | --- | --- |
| `--form-page-request-id` | long | ID of the form request that contains this submitted answer |
| `--form-page-question-id` | long | ID of the form question answered by the customer; the question's form location owns this answer |
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
