# CoworkerInvoiceHistories

<!-- BEGIN:GENERATED entity=CoworkerInvoiceHistories -->

A **CoworkerInvoiceHistory** records a history entry for a customer invoice. Each entry captures an activity or event that occurred on that invoice, such as the invoice being sent, an e-invoicing action, a payment receipt, or a payment error.

Use `--is-problem` to flag entries that represent errors or issues (e.g. a failed payment attempt). Set `--notify` to trigger a notification when the history entry is created.

CoworkerInvoiceHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerinvoicehistories list --agent` | List all coworkerinvoicehistories |
| `nexudus coworkerinvoicehistories list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinvoicehistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinvoicehistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinvoicehistories list --name <value> --description <value> --agent` | Filter coworkerinvoicehistories by properties |
| `nexudus coworkerinvoicehistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinvoicehistories list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerinvoicehistories get <id> --agent` | Get single coworkerinvoicehistory |
| `nexudus coworkerinvoicehistories create --coworker-invoice-id <value> --name <value> --description <value> --agent` | Create coworkerinvoicehistory |
| `nexudus coworkerinvoicehistories update <id> --name "New Name" --agent` | Update coworkerinvoicehistory |
| `nexudus coworkerinvoicehistories delete <id> --yes --agent` | Delete coworkerinvoicehistory (no prompt) |

#### CoworkerInvoiceHistory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the coworker invoice linked to this record |
| `--name` | string | Short title of the history entry (e.g. 'Invoice sent', 'Payment received') |
| `--description` | string | Detailed description of the activity or event recorded by this history entry |
| `--is-problem` | bool | Flags this history entry as an error or issue (e.g. a failed payment attempt or e-invoicing error) |
| `--notify` | bool | Whether to send a notification when this history entry is created |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInvoiceHistory sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### CoworkerInvoiceHistory create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long, required | ID of the coworker invoice linked to this record |
| `--name` | string, required | Short title of the history entry (e.g. 'Invoice sent', 'Payment received') |
| `--description` | string, required | Detailed description of the activity or event recorded by this history entry |
| `--is-problem` | bool | Flags this history entry as an error or issue (e.g. a failed payment attempt or e-invoicing error) |
| `--notify` | bool | Whether to send a notification when this history entry is created |

#### CoworkerInvoiceHistory update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the coworker invoice linked to this record |
| `--name` | string | Short title of the history entry (e.g. 'Invoice sent', 'Payment received') |
| `--description` | string | Detailed description of the activity or event recorded by this history entry |
| `--is-problem` | bool | Flags this history entry as an error or issue (e.g. a failed payment attempt or e-invoicing error) |
| `--notify` | bool | Whether to send a notification when this history entry is created |

#### CoworkerInvoiceHistory PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkerinvoicehistories update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerInvoiceHistory (key fields)

`Id`, `CoworkerInvoiceInvoiceNumber`, `Name`, `Description`, `IsProblem`

<!-- END:GENERATED entity=CoworkerInvoiceHistories -->
