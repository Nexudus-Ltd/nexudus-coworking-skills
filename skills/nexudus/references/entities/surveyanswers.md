# SurveyAnswers

<!-- BEGIN:GENERATED entity=SurveyAnswers -->

SurveyAnswers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveyanswers list --agent` | List all surveyanswers |
| `nexudus surveyanswers list --id <id> --agent` | Filter by single ID |
| `nexudus surveyanswers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveyanswers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveyanswers list --survey-run-id <value> --survey-question-id <value> --agent` | Filter surveyanswers by properties |
| `nexudus surveyanswers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveyanswers get <id> --agent` | Get single surveyanswer |
| `nexudus surveyanswers create --survey-question-id <value> --agent` | Create surveyanswer |
| `nexudus surveyanswers update <id> --name "New Name" --agent` | Update surveyanswer |
| `nexudus surveyanswers delete <id> --yes --agent` | Delete surveyanswer (no prompt) |

#### SurveyAnswer list filter options

`--survey-run-id` (long), `--survey-question-id` (long), `--value`, `--new-file-value-url`, `--clear-file-value-file` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### SurveyAnswer create options

`--survey-run-id` (long), `--survey-question-id` (long, required), `--value`, `--new-file-value-url`, `--clear-file-value-file` (bool)

#### SurveyAnswer update options

`--survey-run-id` (long), `--survey-question-id` (long), `--value`, `--new-file-value-url`, `--clear-file-value-file` (bool)

<!-- END:GENERATED entity=SurveyAnswers -->
