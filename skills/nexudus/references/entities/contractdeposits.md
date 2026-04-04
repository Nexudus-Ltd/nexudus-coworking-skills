# ContractDeposits

<!-- BEGIN:GENERATED entity=ContractDeposits -->

A **ContractDeposit** represents a security deposit or retainer associated with a plan contract (`CoworkerContract`). Each deposit is based on a `Product` and is charged to the member either on the first invoice generated for the contract, or on the next invoice for any contract that has `IncludeSignupFee = true`.

ContractDeposits are created automatically when a contract is signed for a plan (`Tariff`) that includes one or more `TariffSignupProducts`. Each `TariffSignupProduct` on the plan becomes a corresponding `ContractDeposit` on the new contract.

When `Refundable = true`, cancelling the parent contract automatically generates a credit note for the deposit amount. That credit note can then be applied — fully or partially — against any outstanding fees or damage charges raised via a separate invoice.

ContractDeposits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractdeposits list --agent` | List all contractdeposits |
| `nexudus contractdeposits list --id <id> --agent` | Filter by single ID |
| `nexudus contractdeposits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractdeposits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractdeposits list --price <value> --refundable <value> --agent` | Filter contractdeposits by properties |
| `nexudus contractdeposits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractdeposits get <id> --agent` | Get single contractdeposit |
| `nexudus contractdeposits create --coworker-contract-id <value> --product-id <value> --agent` | Create contractdeposit |
| `nexudus contractdeposits update <id> --name "New Name" --agent` | Update contractdeposit |
| `nexudus contractdeposits delete <id> --yes --agent` | Delete contractdeposit (no prompt) |

#### ContractDeposit list filter options

`--coworker-contract-id`, `--product-id`, `--notes`, `--price`, `--refundable`

#### ContractDeposit create options

`--coworker-contract-id` (required), `--product-id` (required), `--notes`, `--price`, `--refundable`

#### ContractDeposit update options

`--coworker-contract-id`, `--product-id`, `--notes`, `--price`, `--refundable`

### ContractDeposit (key fields)

`Id`, `ProductName`, `Price`, `Refundable`, `Invoiced`

<!-- END:GENERATED entity=ContractDeposits -->
