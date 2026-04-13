# SurveyQuestions

<!-- BEGIN:GENERATED entity=SurveyQuestions -->

SurveyQuestions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveyquestions list --agent` | List all surveyquestions |
| `nexudus surveyquestions list --id <id> --agent` | Filter by single ID |
| `nexudus surveyquestions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveyquestions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveyquestions list --survey-id <value> --text <value> --agent` | Filter surveyquestions by properties |
| `nexudus surveyquestions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveyquestions get <id> --agent` | Get single surveyquestion |
| `nexudus surveyquestions create --survey-id <value> --text <value> --description <value> --display-order <value> --question-type <value> --agent` | Create surveyquestion |
| `nexudus surveyquestions update <id> --name "New Name" --agent` | Update surveyquestion |
| `nexudus surveyquestions delete <id> --yes --agent` | Delete surveyquestion (no prompt) |

#### SurveyQuestion list filter options

`--survey-id` (long), `--text`, `--description`, `--available-options`, `--active` (bool), `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--allow-multiple-options` (bool), `--question-type` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### SurveyQuestion create options

`--survey-id` (long, required), `--text` (required), `--description` (required), `--available-options`, `--active` (bool), `--display-order` (int, required), `--allow-multiple-options` (bool), `--question-type` (enum, required)

#### SurveyQuestion update options

`--survey-id` (long), `--text`, `--description`, `--available-options`, `--active` (bool), `--display-order` (int), `--allow-multiple-options` (bool), `--question-type` (enum)

<!-- END:GENERATED entity=SurveyQuestions -->
