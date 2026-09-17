# ReportDashboards

<!-- BEGIN:GENERATED entity=ReportDashboards -->

A self-service reporting dashboard: an ordered grid of tiles that reference saved reports (report_definition) or built-in templates, with dashboard-level parameters (date range, locations) bound to each tile's filters.

ReportDashboards support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reportdashboards list --agent` | List all reportdashboards |
| `nexudus reportdashboards list --id <id> --agent` | Filter by single ID |
| `nexudus reportdashboards list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reportdashboards list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reportdashboards list --business-id <value> --name <value> --agent` | Filter reportdashboards by properties |
| `nexudus reportdashboards list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reportdashboards list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus reportdashboards get <id> --agent` | Get single reportdashboard |
| `nexudus reportdashboards create --business-id <value> --name <value> --layout-json <value> --refresh-interval-seconds <value> --agent` | Create reportdashboard |
| `nexudus reportdashboards update <id> --name "New Name" --agent` | Update reportdashboard |
| `nexudus reportdashboards delete <id> --yes --agent` | Delete reportdashboard (no prompt) |

#### ReportDashboard list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business that owns this dashboard |
| `--name` | string | Dashboard name |
| `--description` | string | Optional description |
| `--layout-json` | string | DashboardLayout JSON (version 1): { version, parameters: [{ id, type: date_range|business_scope|enum|text, label, default }], widgets: [{ id, kind: report|heading|text, reportDefinitionId?, templateKey?, title?, size: { w: 1-4, h: 1-3 }, bindings: { parameterId: fieldPath | "*" }, visualizationOverride? }], refreshIntervalSeconds? } |
| `--is-shared` | bool | Visible to every user of the business; when false only the owner sees it |
| `--owner-full-name` | string | Display value for Owner.FullName. |
| `--owner-email` | string | Display value for Owner.Email. |
| `--template-key` | string | Key of the built-in template this dashboard was copied from, if any |
| `--is-default` | bool | Shown first in the Dashboards library for this business |
| `--refresh-interval-seconds` | int | Auto-refresh interval in seconds (0 = manual) |
| `--from-refresh-interval-seconds` | range | |
| `--to-refresh-interval-seconds` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ReportDashboard sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### ReportDashboard create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business that owns this dashboard |
| `--name` | string, required | Dashboard name |
| `--description` | string | Optional description |
| `--layout-json` | string, required | DashboardLayout JSON (version 1): { version, parameters: [{ id, type: date_range|business_scope|enum|text, label, default }], widgets: [{ id, kind: report|heading|text, reportDefinitionId?, templateKey?, title?, size: { w: 1-4, h: 1-3 }, bindings: { parameterId: fieldPath | "*" }, visualizationOverride? }], refreshIntervalSeconds? } |
| `--is-shared` | bool | Visible to every user of the business; when false only the owner sees it |
| `--is-default` | bool | Shown first in the Dashboards library for this business |
| `--refresh-interval-seconds` | int, required | Auto-refresh interval in seconds (0 = manual) |

#### ReportDashboard update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business that owns this dashboard |
| `--name` | string | Dashboard name |
| `--description` | string | Optional description |
| `--layout-json` | string | DashboardLayout JSON (version 1): { version, parameters: [{ id, type: date_range|business_scope|enum|text, label, default }], widgets: [{ id, kind: report|heading|text, reportDefinitionId?, templateKey?, title?, size: { w: 1-4, h: 1-3 }, bindings: { parameterId: fieldPath | "*" }, visualizationOverride? }], refreshIntervalSeconds? } |
| `--is-shared` | bool | Visible to every user of the business; when false only the owner sees it |
| `--is-default` | bool | Shown first in the Dashboards library for this business |
| `--refresh-interval-seconds` | int | Auto-refresh interval in seconds (0 = manual) |

#### ReportDashboard PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--owner-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--owner-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus reportdashboards update <id> --owner-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=ReportDashboards -->
