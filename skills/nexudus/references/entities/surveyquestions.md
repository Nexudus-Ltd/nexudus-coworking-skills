# SurveyQuestions

<!-- BEGIN:GENERATED entity=SurveyQuestions -->

A survey question (SurveyQuestion) is an ordered question within a location's customer survey. It defines the customer-facing label, explanation, input type, optional choices, and whether the question is shown.

SurveyQuestions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveyquestions list --agent` | List all surveyquestions |
| `nexudus surveyquestions list --id <id> --agent` | Filter by single ID |
| `nexudus surveyquestions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveyquestions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveyquestions list --survey-id <value> --survey-name <value> --agent` | Filter surveyquestions by properties |
| `nexudus surveyquestions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveyquestions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus surveyquestions get <id> --agent` | Get single surveyquestion |
| `nexudus surveyquestions create --survey-id <value> --text <value> --description <value> --display-order <value> --question-type <value> --agent` | Create surveyquestion |
| `nexudus surveyquestions update <id> --name "New Name" --agent` | Update surveyquestion |
| `nexudus surveyquestions delete <id> --yes --agent` | Delete surveyquestion (no prompt) |

#### SurveyQuestion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--survey-id` | long | ID of the survey that contains this question; the survey's location determines access to the question |
| `--survey-name` | string | Display name of the linked survey (read-only) |
| `--text` | string | Required question label shown to customers |
| `--description` | string | Required explanatory text shown below the question to customers |
| `--available-options` | string | Comma-separated choices for a Dropdown question; leave empty for other question types |
| `--active` | bool | Whether this question appears in the customer-facing survey |
| `--display-order` | int | Integer position for displaying this question; lower values appear first and the system renumbers questions after create or update |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--allow-multiple-options` | bool | Whether customers can select more than one choice for a Dropdown question |
| `--question-type` | enum | Controls the customer input: Text, Boolean (Yes/No), LongText, Date, Dropdown, or Binary file upload; defaults to Text |
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
| `--survey-id` | long, required | ID of the survey that contains this question; the survey's location determines access to the question |
| `--text` | string, required | Required question label shown to customers |
| `--description` | string, required | Required explanatory text shown below the question to customers |
| `--available-options` | string | Comma-separated choices for a Dropdown question; leave empty for other question types |
| `--active` | bool | Whether this question appears in the customer-facing survey |
| `--display-order` | int, required | Integer position for displaying this question; lower values appear first and the system renumbers questions after create or update |
| `--allow-multiple-options` | bool | Whether customers can select more than one choice for a Dropdown question |
| `--question-type` | enum, required | Controls the customer input: Text, Boolean (Yes/No), LongText, Date, Dropdown, or Binary file upload; defaults to Text |

#### SurveyQuestion update options

| Option | Type | Description |
| --- | --- | --- |
| `--survey-id` | long | ID of the survey that contains this question; the survey's location determines access to the question |
| `--text` | string | Required question label shown to customers |
| `--description` | string | Required explanatory text shown below the question to customers |
| `--available-options` | string | Comma-separated choices for a Dropdown question; leave empty for other question types |
| `--active` | bool | Whether this question appears in the customer-facing survey |
| `--display-order` | int | Integer position for displaying this question; lower values appear first and the system renumbers questions after create or update |
| `--allow-multiple-options` | bool | Whether customers can select more than one choice for a Dropdown question |
| `--question-type` | enum | Controls the customer input: Text, Boolean (Yes/No), LongText, Date, Dropdown, or Binary file upload; defaults to Text |

#### SurveyQuestion enum values

| Option | Valid values |
| ------ | ------------ |
| `--question-type` | `1` Text, `2` Boolean, `3` LongText, `4` Date, `5` Dropdown, `6` Binary |

<!-- END:GENERATED entity=SurveyQuestions -->
