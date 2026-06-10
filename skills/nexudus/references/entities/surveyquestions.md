# SurveyQuestions

<!-- BEGIN:GENERATED entity=SurveyQuestions -->

A **SurveyQuestion** defines a single question within a survey, including its type (text, boolean, long text, date, dropdown, or binary), label, and display order.

SurveyQuestions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveyquestions list --agent` | List all surveyquestions |
| `nexudus surveyquestions list --id <id> --agent` | Filter by single ID |
| `nexudus surveyquestions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveyquestions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveyquestions list --survey-id <value> --text <value> --agent` | Filter surveyquestions by properties |
| `nexudus surveyquestions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveyquestions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus surveyquestions get <id> --agent` | Get single surveyquestion |
| `nexudus surveyquestions create --survey-id <value> --text <value> --description <value> --display-order <value> --question-type <value> --agent` | Create surveyquestion |
| `nexudus surveyquestions update <id> --name "New Name" --agent` | Update surveyquestion |
| `nexudus surveyquestions delete <id> --yes --agent` | Delete surveyquestion (no prompt) |

#### SurveyQuestion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--survey-id` | long | ID of the survey linked to this record |
| `--text` | string | The text value for this survey question |
| `--description` | string | Free-text description of this survey question |
| `--available-options` | string | The available options value for this survey question |
| `--active` | bool | Whether this survey question is currently active |
| `--display-order` | int | The display order value for this survey question |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--allow-multiple-options` | bool | Whether allow multiple options is enabled |
| `--question-type` | enum | The question type value for this survey question |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SurveyQuestion sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### SurveyQuestion create options

| Option | Type | Description |
| --- | --- | --- |
| `--survey-id` | long, required | ID of the survey linked to this record |
| `--text` | string, required | The text value for this survey question |
| `--description` | string, required | Free-text description of this survey question |
| `--available-options` | string | The available options value for this survey question |
| `--active` | bool | Whether this survey question is currently active |
| `--display-order` | int, required | The display order value for this survey question |
| `--allow-multiple-options` | bool | Whether allow multiple options is enabled |
| `--question-type` | enum, required | The question type value for this survey question |

#### SurveyQuestion update options

| Option | Type | Description |
| --- | --- | --- |
| `--survey-id` | long | ID of the survey linked to this record |
| `--text` | string | The text value for this survey question |
| `--description` | string | Free-text description of this survey question |
| `--available-options` | string | The available options value for this survey question |
| `--active` | bool | Whether this survey question is currently active |
| `--display-order` | int | The display order value for this survey question |
| `--allow-multiple-options` | bool | Whether allow multiple options is enabled |
| `--question-type` | enum | The question type value for this survey question |

#### SurveyQuestion enum values

| Option | Valid values |
| ------ | ------------ |
| `--question-type` | `1` Text, `2` Boolean, `3` LongText, `4` Date, `5` Dropdown, `6` Binary |

<!-- END:GENERATED entity=SurveyQuestions -->
