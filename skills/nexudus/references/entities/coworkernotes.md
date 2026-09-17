# CoworkerNotes

<!-- BEGIN:GENERATED entity=CoworkerNotes -->

A customer note (CoworkerNote) is an internal staff note attached to a customer record; it supports searching, adding, editing, and deleting customer-specific notes and is not shown to the customer.

CoworkerNotes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkernotes list --agent` | List all coworkernotes |
| `nexudus coworkernotes list --id <id> --agent` | Filter by single ID |
| `nexudus coworkernotes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkernotes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkernotes list --coworker-id <value> --coworker-full-name <value> --agent` | Filter coworkernotes by properties |
| `nexudus coworkernotes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkernotes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkernotes get <id> --agent` | Get single coworkernote |
| `nexudus coworkernotes create --coworker-id <value> --notes <value> --agent` | Create coworkernote |
| `nexudus coworkernotes update <id> --name "New Name" --agent` | Update coworkernote |
| `nexudus coworkernotes delete <id> --yes --agent` | Delete coworkernote (no prompt) |

#### CoworkerNote list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this internal note belongs to; location access is determined through the customer's InvoicingBusiness. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--notes` | string | Required internal note text for location staff; this content is not shown to the customer. |
| `--added-by` | string | Optional name of the staff member or integration that added the note; normally populated with the signed-in staff member's full name. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerNote sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerNote create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer this internal note belongs to; location access is determined through the customer's InvoicingBusiness. |
| `--notes` | string, required | Required internal note text for location staff; this content is not shown to the customer. |
| `--added-by` | string | Optional name of the staff member or integration that added the note; normally populated with the signed-in staff member's full name. |

#### CoworkerNote update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer this internal note belongs to; location access is determined through the customer's InvoicingBusiness. |
| `--notes` | string | Required internal note text for location staff; this content is not shown to the customer. |
| `--added-by` | string | Optional name of the staff member or integration that added the note; normally populated with the signed-in staff member's full name. |

#### CoworkerNote PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkernotes update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=CoworkerNotes -->
