# ReportDefinitions

<!-- BEGIN:GENERATED entity=ReportDefinitions -->

A saved self-service report: a ReportQuery JSON document plus a visualization. Use report_catalog to discover fields, report_query to test a query before saving it, and report_run to execute a saved report.

ReportDefinitions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reportdefinitions list --agent` | List all reportdefinitions |
| `nexudus reportdefinitions list --id <id> --agent` | Filter by single ID |
| `nexudus reportdefinitions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reportdefinitions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reportdefinitions list --business-id <value> --name <value> --agent` | Filter reportdefinitions by properties |
| `nexudus reportdefinitions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reportdefinitions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus reportdefinitions get <id> --agent` | Get single reportdefinition |
| `nexudus reportdefinitions create --business-id <value> --name <value> --query-json <value> --agent` | Create reportdefinition |
| `nexudus reportdefinitions update <id> --name "New Name" --agent` | Update reportdefinition |
| `nexudus reportdefinitions delete <id> --yes --agent` | Delete reportdefinition (no prompt) |

#### ReportDefinition list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business that owns this report |
| `--name` | string | Report name shown in the library |
| `--description` | string | Optional description of what the report shows |
| `--folder` | string | Folder used to group reports in the library (e.g. Bookings, Billing) |
| `--entity-name` | string | Root entity of the query; derived from QueryJson on save |
| `--visualization-type` | string | Visualization type (table, number, bar, line, area, pie); derived from VisualizationJson on save |
| `--query-json` | string | ReportQuery JSON document (version 1). Use report_catalog to discover entities and field paths and report_query to test the query before saving. |
| `--visualization-json` | string | VisualizationDocument JSON: { "type": "table|number|bar|line|area|pie", "settings": { ... } } |
| `--is-shared` | bool | Visible to every user of the business; when false only the owner sees it |
| `--owner-full-name` | string | Display value for Owner.FullName. |
| `--owner-email` | string | Display value for Owner.Email. |
| `--template-key` | string | Key of the built-in template this report was copied from, if any |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ReportDefinition sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### ReportDefinition create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business that owns this report |
| `--name` | string, required | Report name shown in the library |
| `--description` | string | Optional description of what the report shows |
| `--folder` | string | Folder used to group reports in the library (e.g. Bookings, Billing) |
| `--query-json` | string, required | ReportQuery JSON document (version 1). Use report_catalog to discover entities and field paths and report_query to test the query before saving. |
| `--visualization-json` | string | VisualizationDocument JSON: { "type": "table|number|bar|line|area|pie", "settings": { ... } } |
| `--is-shared` | bool | Visible to every user of the business; when false only the owner sees it |

#### ReportDefinition update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business that owns this report |
| `--name` | string | Report name shown in the library |
| `--description` | string | Optional description of what the report shows |
| `--folder` | string | Folder used to group reports in the library (e.g. Bookings, Billing) |
| `--query-json` | string | ReportQuery JSON document (version 1). Use report_catalog to discover entities and field paths and report_query to test the query before saving. |
| `--visualization-json` | string | VisualizationDocument JSON: { "type": "table|number|bar|line|area|pie", "settings": { ... } } |
| `--is-shared` | bool | Visible to every user of the business; when false only the owner sees it |

#### ReportDefinition PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--owner-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--owner-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus reportdefinitions update <id> --owner-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=ReportDefinitions -->
