# DocumentTemplates

<!-- BEGIN:GENERATED entity=DocumentTemplates -->

A **DocumentTemplate** defines a reusable template for generating documents such as contracts, proposals, or invoices. Templates support HTML, Word, and binary output formats and can include dynamic merge fields populated from customer and business data.

DocumentTemplates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus documenttemplates list --agent` | List all documenttemplates |
| `nexudus documenttemplates list --id <id> --agent` | Filter by single ID |
| `nexudus documenttemplates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus documenttemplates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus documenttemplates list --business-id <value> --business-name <value> --agent` | Filter documenttemplates by properties |
| `nexudus documenttemplates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus documenttemplates list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus documenttemplates get <id> --agent` | Get single documenttemplate |
| `nexudus documenttemplates create --business-id <value> --name <value> --template-output-format <value> --agent` | Create documenttemplate |
| `nexudus documenttemplates update <id> --name "New Name" --agent` | Update documenttemplate |
| `nexudus documenttemplates delete <id> --yes --agent` | Delete documenttemplate (no prompt) |

#### DocumentTemplate list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--name` | string | The name value for this document template |
| `--document` | string | The document value for this document template |
| `--binary-document-file-name` | string | Current file name of the binary document (read-only; upload via the corresponding URL field) |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum | The template output format value for this document template |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### DocumentTemplate sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### DocumentTemplate create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this document template |
| `--document` | string | The document value for this document template |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum, required | The template output format value for this document template |

#### DocumentTemplate update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this document template |
| `--document` | string | The document value for this document template |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum | The template output format value for this document template |

#### DocumentTemplate enum values

| Option | Valid values |
| ------ | ------------ |
| `--template-output-format` | `1` Html, `2` Word, `3` Binary |

<!-- END:GENERATED entity=DocumentTemplates -->
