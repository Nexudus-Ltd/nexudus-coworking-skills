# TemplateFiles

<!-- BEGIN:GENERATED entity=TemplateFiles -->

A **TemplateFile** represents a file asset (HTML, CSS, JavaScript, or image) used in website templates and email templates. Template files control the visual appearance and layout of customer-facing pages.

TemplateFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus templatefiles list --agent` | List all templatefiles |
| `nexudus templatefiles list --id <id> --agent` | Filter by single ID |
| `nexudus templatefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus templatefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus templatefiles list --business-id <value> --template-version-id <value> --agent` | Filter templatefiles by properties |
| `nexudus templatefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus templatefiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus templatefiles get <id> --agent` | Get single templatefile |
| `nexudus templatefiles create --business-id <value> --name <value> --permalink <value> --visibility <value> --agent` | Create templatefile |
| `nexudus templatefiles update <id> --name "New Name" --agent` | Update templatefile |
| `nexudus templatefiles delete <id> --yes --agent` | Delete templatefile (no prompt) |

#### TemplateFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--template-version-id` | long | ID of the template version linked to this record |
| `--name` | string | The name value for this template file |
| `--title` | string | The title value for this template file |
| `--description` | string | Free-text description of this template file |
| `--picture-file-name` | string | Current file name of the picture (read-only; upload via the corresponding URL field) |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--permalink` | string | The permalink value for this template file |
| `--file-language-id` | long | ID of the file language linked to this record |
| `--published` | bool | Whether published is enabled |
| `--visibility` | enum | The visibility value for this template file |
| `--password` | string | The password value for this template file |
| `--is-custom` | bool | Whether is custom is enabled |
| `--theme-name` | string | Display name of the linked theme (read-only) |
| `--file-contents` | string | The file contents value for this template file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TemplateFile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TemplateFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--template-version-id` | long | ID of the template version linked to this record |
| `--name` | string, required | The name value for this template file |
| `--title` | string | The title value for this template file |
| `--description` | string | Free-text description of this template file |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--permalink` | string, required | The permalink value for this template file |
| `--file-language-id` | long | ID of the file language linked to this record |
| `--published` | bool | Whether published is enabled |
| `--visibility` | enum, required | The visibility value for this template file |
| `--password` | string | The password value for this template file |
| `--file-contents` | string | The file contents value for this template file |

#### TemplateFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--template-version-id` | long | ID of the template version linked to this record |
| `--name` | string | The name value for this template file |
| `--title` | string | The title value for this template file |
| `--description` | string | Free-text description of this template file |
| `--new-picture-url` | string | URL of a new file to upload as the picture |
| `--clear-picture-file` | bool | Set to true to remove the current picture file |
| `--permalink` | string | The permalink value for this template file |
| `--file-language-id` | long | ID of the file language linked to this record |
| `--published` | bool | Whether published is enabled |
| `--visibility` | enum | The visibility value for this template file |
| `--password` | string | The password value for this template file |
| `--file-contents` | string | The file contents value for this template file |

#### TemplateFile enum values

| Option | Valid values |
| ------ | ------------ |
| `--visibility` | `1` Public, `2` Private, `3` PasswordProtected, `4` OnlyMembers |

<!-- END:GENERATED entity=TemplateFiles -->
