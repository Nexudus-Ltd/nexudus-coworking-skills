# TemplateVersions

<!-- BEGIN:GENERATED entity=TemplateVersions -->

A **TemplateVersion** represents a saved version of a website or email template, enabling version history and rollback of template changes.

TemplateVersions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus templateversions list --agent` | List all templateversions |
| `nexudus templateversions list --id <id> --agent` | Filter by single ID |
| `nexudus templateversions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus templateversions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus templateversions list --business-id <value> --name <value> --agent` | Filter templateversions by properties |
| `nexudus templateversions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus templateversions list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus templateversions get <id> --agent` | Get single templateversion |
| `nexudus templateversions create --business-id <value> --name <value> --agent` | Create templateversion |
| `nexudus templateversions update <id> --name "New Name" --agent` | Update templateversion |
| `nexudus templateversions delete <id> --yes --agent` | Delete templateversion (no prompt) |

#### TemplateVersion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this template version |
| `--description` | string | Free-text description of this template version |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TemplateVersion sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TemplateVersion create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this template version |
| `--description` | string | Free-text description of this template version |

#### TemplateVersion update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this template version |
| `--description` | string | Free-text description of this template version |

<!-- END:GENERATED entity=TemplateVersions -->
