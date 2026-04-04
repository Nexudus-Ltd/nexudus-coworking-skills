# CoworkerPaymentMethods

<!-- BEGIN:GENERATED entity=CoworkerPaymentMethods -->

CoworkerPaymentMethods support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerpaymentmethods list --agent` | List all coworkerpaymentmethods |
| `nexudus coworkerpaymentmethods list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerpaymentmethods list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerpaymentmethods list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerpaymentmethods list --coworker-id <value> --business-id <value> --agent` | Filter coworkerpaymentmethods by properties |
| `nexudus coworkerpaymentmethods list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerpaymentmethods get <id> --agent` | Get single coworkerpaymentmethod |
| `nexudus coworkerpaymentmethods create --coworker-id <value> --business-id <value> --agent` | Create coworkerpaymentmethod |
| `nexudus coworkerpaymentmethods update <id> --name "New Name" --agent` | Update coworkerpaymentmethod |
| `nexudus coworkerpaymentmethods delete <id> --yes --agent` | Delete coworkerpaymentmethod (no prompt) |

#### CoworkerPaymentMethod list filter options

`--coworker-id`, `--business-id`, `--regular-payment-provider`, `--method-id`, `--customer-id`, `--mandate-id`, `--card-number`, `--notes`

#### CoworkerPaymentMethod create options

`--coworker-id` (required), `--business-id` (required), `--regular-payment-provider`, `--method-id`, `--customer-id`, `--mandate-id`, `--card-number`, `--notes`

#### CoworkerPaymentMethod update options

`--coworker-id`, `--business-id`, `--regular-payment-provider`, `--method-id`, `--customer-id`, `--mandate-id`, `--card-number`, `--notes`

<!-- END:GENERATED entity=CoworkerPaymentMethods -->
