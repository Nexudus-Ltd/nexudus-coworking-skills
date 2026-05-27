# SurveyRuns

<!-- BEGIN:GENERATED entity=SurveyRuns -->

A **SurveyRun** represents a single delivery instance of a survey to a customer. Each run tracks when the survey was sent, whether it was completed, and links to the collected answers.

SurveyRuns support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveyruns list --agent` | List all surveyruns |
| `nexudus surveyruns list --id <id> --agent` | Filter by single ID |
| `nexudus surveyruns list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveyruns list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveyruns list --coworker-id <value> --survey-id <value> --agent` | Filter surveyruns by properties |
| `nexudus surveyruns list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveyruns get <id> --agent` | Get single surveyrun |
| `nexudus surveyruns create --coworker-id <value> --survey-id <value> --agent` | Create surveyrun |
| `nexudus surveyruns update <id> --name "New Name" --agent` | Update surveyrun |
| `nexudus surveyruns delete <id> --yes --agent` | Delete surveyrun (no prompt) |

#### SurveyRun list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--survey-id` | long | ID of the survey linked to this record |
| `--mailing-date` | DateTime | Date/time value for mailing date |
| `--from-mailing-date` | range | |
| `--to-mailing-date` | range | |
| `--submitted` | bool | Whether submitted is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SurveyRun create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--survey-id` | long, required | ID of the survey linked to this record |
| `--mailing-date` | DateTime | Date/time value for mailing date |
| `--submitted` | bool | Whether submitted is enabled |

#### SurveyRun update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--survey-id` | long | ID of the survey linked to this record |
| `--mailing-date` | DateTime | Date/time value for mailing date |
| `--submitted` | bool | Whether submitted is enabled |

<!-- END:GENERATED entity=SurveyRuns -->
