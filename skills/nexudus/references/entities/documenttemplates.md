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
| `nexudus documenttemplates list --business-id <value> --name <value> --agent` | Filter documenttemplates by properties |
| `nexudus documenttemplates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus documenttemplates get <id> --agent` | Get single documenttemplate |
| `nexudus documenttemplates create --business-id <value> --name <value> --template-output-format <value> --agent` | Create documenttemplate |
| `nexudus documenttemplates update <id> --name "New Name" --agent` | Update documenttemplate |
| `nexudus documenttemplates delete <id> --yes --agent` | Delete documenttemplate (no prompt) |

#### DocumentTemplate list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this document template |
| `--document` | string | The document value for this document template |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum | The template output format value for this document template |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

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
