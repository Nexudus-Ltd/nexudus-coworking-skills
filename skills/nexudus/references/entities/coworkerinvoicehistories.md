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
| `nexudus coworkerinvoicehistories get <id> --agent` | Get single coworkerinvoicehistory |
| `nexudus coworkerinvoicehistories create --coworker-invoice-id <value> --name <value> --description <value> --agent` | Create coworkerinvoicehistory |
| `nexudus coworkerinvoicehistories update <id> --name "New Name" --agent` | Update coworkerinvoicehistory |
| `nexudus coworkerinvoicehistories delete <id> --yes --agent` | Delete coworkerinvoicehistory (no prompt) |

#### CoworkerInvoiceHistory list filter options

`--coworker-invoice-id`, `--name`, `--description`, `--is-problem`, `--notify`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerInvoiceHistory create options

`--coworker-invoice-id` (required), `--name` (required), `--description` (required), `--is-problem`, `--notify`

#### CoworkerInvoiceHistory update options

`--coworker-invoice-id`, `--name`, `--description`, `--is-problem`, `--notify`

### CoworkerInvoiceHistory (key fields)

`Id`, `CoworkerInvoiceInvoiceNumber`, `Name`, `Description`, `IsProblem`

<!-- END:GENERATED entity=CoworkerInvoiceHistories -->
