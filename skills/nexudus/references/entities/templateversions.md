# TemplateVersions

<!-- BEGIN:GENERATED entity=TemplateVersions -->

TemplateVersions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus templateversions list --agent` | List all templateversions |
| `nexudus templateversions list --id <id> --agent` | Filter by single ID |
| `nexudus templateversions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus templateversions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus templateversions list --business-id <value> --name <value> --agent` | Filter templateversions by properties |
| `nexudus templateversions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus templateversions get <id> --agent` | Get single templateversion |
| `nexudus templateversions create --business-id <value> --name <value> --agent` | Create templateversion |
| `nexudus templateversions update <id> --name "New Name" --agent` | Update templateversion |
| `nexudus templateversions delete <id> --yes --agent` | Delete templateversion (no prompt) |

#### TemplateVersion list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--description` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TemplateVersion create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--description` | string |  |

#### TemplateVersion update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--description` | string |  |

<!-- END:GENERATED entity=TemplateVersions -->
