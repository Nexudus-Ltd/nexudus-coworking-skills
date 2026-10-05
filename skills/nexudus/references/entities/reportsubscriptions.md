# ReportSubscriptions

<!-- BEGIN:GENERATED entity=ReportSubscriptions -->

A scheduled email delivery of a saved report or dashboard: the data is attached as CSV, the body carries an AI summary and a link to open it in the dashboard. Use report_definition_list / report_dashboard_list to find the report or dashboard to schedule.

ReportSubscriptions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reportsubscriptions list --agent` | List all reportsubscriptions |
| `nexudus reportsubscriptions list --id <id> --agent` | Filter by single ID |
| `nexudus reportsubscriptions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reportsubscriptions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reportsubscriptions list --business-id <value> --name <value> --agent` | Filter reportsubscriptions by properties |
| `nexudus reportsubscriptions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reportsubscriptions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus reportsubscriptions get <id> --agent` | Get single reportsubscription |
| `nexudus reportsubscriptions create --business-id <value> --name <value> --recipients <value> --frequency <value> --day-of-week <value> --day-of-month <value> --hour-of-day <value> --agent` | Create reportsubscription |
| `nexudus reportsubscriptions update <id> --name "New Name" --agent` | Update reportsubscription |
| `nexudus reportsubscriptions delete <id> --yes --agent` | Delete reportsubscription (no prompt) |

#### ReportSubscription list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business the schedule belongs to |
| `--name` | string | Name of the schedule, e.g. Weekly revenue to finance |
| `--report-definition-id` | long | Saved report to send (exactly one of ReportDefinitionId, ReportDashboardId, TemplateKey or DashboardTemplateKey) |
| `--report-definition-name` | string | Display value for ReportDefinition.Name. |
| `--report-dashboard-id` | long | Saved dashboard to send: every report tile is attached as CSV (set either ReportDefinitionId or ReportDashboardId) |
| `--report-dashboard-name` | string | Display value for ReportDashboard.Name. |
| `--template-key` | string | Built-in report template to send (key from report_templates), instead of a saved report |
| `--dashboard-template-key` | string | Built-in dashboard template to send (key from report_templates kind=dashboard), instead of a saved dashboard |
| `--recipients` | string | Email addresses separated by commas or semicolons |
| `--subject` | string | Optional email subject; defaults to the report or dashboard name |
| `--language` | string | Language of the email, the CSV attachment headers and the AI summary: en, es or fr. Defaults to the app language of the user who creates the schedule |
| `--frequency` | enum | Daily, Weekly or Monthly |
| `--day-of-week` | int | Weekly schedules: 1 = Monday ... 7 = Sunday |
| `--from-day-of-week` | range | |
| `--to-day-of-week` | range | |
| `--day-of-month` | int | Monthly schedules: day of the month (1-28) |
| `--from-day-of-month` | range | |
| `--to-day-of-month` | range | |
| `--hour-of-day` | int | Hour of the day to send (0-23) in the business time zone |
| `--from-hour-of-day` | range | |
| `--to-hour-of-day` | range | |
| `--include-attachment` | bool | Attach the report data as CSV files |
| `--include-summary` | bool | Include an AI-written summary of the results in the email body |
| `--parameters-json` | string | Optional JSON: for reports an array of prompt filter overrides [{field, op, value}], for dashboards an object of parameter values keyed by parameter id |
| `--active` | bool | Paused schedules are kept but not sent |
| `--owner-full-name` | string | Display value for Owner.FullName. |
| `--owner-email` | string | Display value for Owner.Email. |
| `--next-run-on` | DateTime | UTC time of the next delivery (computed from the schedule) |
| `--from-next-run-on` | range | |
| `--to-next-run-on` | range | |
| `--last-run-on` | DateTime | UTC time of the last delivery attempt |
| `--from-last-run-on` | range | |
| `--to-last-run-on` | range | |
| `--last-run-status` | string | Sent or Failed |
| `--last-error` | string | Error message of the last failed delivery |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ReportSubscription sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### ReportSubscription create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business the schedule belongs to |
| `--name` | string, required | Name of the schedule, e.g. Weekly revenue to finance |
| `--report-definition-id` | long | Saved report to send (exactly one of ReportDefinitionId, ReportDashboardId, TemplateKey or DashboardTemplateKey) |
| `--report-dashboard-id` | long | Saved dashboard to send: every report tile is attached as CSV (set either ReportDefinitionId or ReportDashboardId) |
| `--template-key` | string | Built-in report template to send (key from report_templates), instead of a saved report |
| `--dashboard-template-key` | string | Built-in dashboard template to send (key from report_templates kind=dashboard), instead of a saved dashboard |
| `--recipients` | string, required | Email addresses separated by commas or semicolons |
| `--subject` | string | Optional email subject; defaults to the report or dashboard name |
| `--language` | string | Language of the email, the CSV attachment headers and the AI summary: en, es or fr. Defaults to the app language of the user who creates the schedule |
| `--frequency` | enum, required | Daily, Weekly or Monthly |
| `--day-of-week` | int, required | Weekly schedules: 1 = Monday ... 7 = Sunday |
| `--day-of-month` | int, required | Monthly schedules: day of the month (1-28) |
| `--hour-of-day` | int, required | Hour of the day to send (0-23) in the business time zone |
| `--include-attachment` | bool | Attach the report data as CSV files |
| `--include-summary` | bool | Include an AI-written summary of the results in the email body |
| `--parameters-json` | string | Optional JSON: for reports an array of prompt filter overrides [{field, op, value}], for dashboards an object of parameter values keyed by parameter id |
| `--active` | bool | Paused schedules are kept but not sent |

#### ReportSubscription update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business the schedule belongs to |
| `--name` | string | Name of the schedule, e.g. Weekly revenue to finance |
| `--report-definition-id` | long | Saved report to send (exactly one of ReportDefinitionId, ReportDashboardId, TemplateKey or DashboardTemplateKey) |
| `--report-dashboard-id` | long | Saved dashboard to send: every report tile is attached as CSV (set either ReportDefinitionId or ReportDashboardId) |
| `--template-key` | string | Built-in report template to send (key from report_templates), instead of a saved report |
| `--dashboard-template-key` | string | Built-in dashboard template to send (key from report_templates kind=dashboard), instead of a saved dashboard |
| `--recipients` | string | Email addresses separated by commas or semicolons |
| `--subject` | string | Optional email subject; defaults to the report or dashboard name |
| `--language` | string | Language of the email, the CSV attachment headers and the AI summary: en, es or fr. Defaults to the app language of the user who creates the schedule |
| `--frequency` | enum | Daily, Weekly or Monthly |
| `--day-of-week` | int | Weekly schedules: 1 = Monday ... 7 = Sunday |
| `--day-of-month` | int | Monthly schedules: day of the month (1-28) |
| `--hour-of-day` | int | Hour of the day to send (0-23) in the business time zone |
| `--include-attachment` | bool | Attach the report data as CSV files |
| `--include-summary` | bool | Include an AI-written summary of the results in the email body |
| `--parameters-json` | string | Optional JSON: for reports an array of prompt filter overrides [{field, op, value}], for dashboards an object of parameter values keyed by parameter id |
| `--active` | bool | Paused schedules are kept but not sent |

#### ReportSubscription PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--owner-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--owner-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus reportsubscriptions update <id> --owner-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### ReportSubscription enum values

| Option | Valid values |
| ------ | ------------ |
| `--frequency` | `1` Daily, `2` Weekly, `3` Monthly |

<!-- END:GENERATED entity=ReportSubscriptions -->
