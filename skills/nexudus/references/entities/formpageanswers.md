# FormPageAnswers

<!-- BEGIN:GENERATED entity=FormPageAnswers -->

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

`--form-page-request-id` (long), `--form-page-question-id` (long), `--value`, `--new-file-value-url`, `--clear-file-value-file` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FormPageAnswer create options

`--form-page-request-id` (long), `--form-page-question-id` (long, required), `--value`, `--new-file-value-url`, `--clear-file-value-file` (bool)

#### FormPageAnswer update options

`--form-page-request-id` (long), `--form-page-question-id` (long), `--value`, `--new-file-value-url`, `--clear-file-value-file` (bool)

<!-- END:GENERATED entity=FormPageAnswers -->
