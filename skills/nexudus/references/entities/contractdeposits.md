# ContractDeposits

<!-- BEGIN:GENERATED entity=ContractDeposits -->

A contract deposit (internally ContractDeposit) is a one-time product charge attached to a customer's contract, normally created from a plan's sign-up products. Creating a new contract from a plan with sign-up products creates one deposit for each product and sets the contract's IncludeSignupFee flag to true. Deposits are charged on the next eligible contract invoice only while IncludeSignupFee is true; that invoicing run then resets the flag to false. A deposit marked InvoiceDuringOnlineCheckout is instead charged during the customer's online checkout. A refundable deposit can be processed through the dedicated refund workflow after the contract ends.

ContractDeposits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractdeposits list --agent` | List all contractdeposits |
| `nexudus contractdeposits list --id <id> --agent` | Filter by single ID |
| `nexudus contractdeposits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractdeposits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractdeposits list --price <value> --refundable <value> --agent` | Filter contractdeposits by properties |
| `nexudus contractdeposits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractdeposits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus contractdeposits get <id> --agent` | Get single contractdeposit |
| `nexudus contractdeposits create --coworker-contract-id <value> --product-id <value> --agent` | Create contractdeposit |
| `nexudus contractdeposits update <id> --name "New Name" --agent` | Update contractdeposit |
| `nexudus contractdeposits delete <id> --yes --agent` | Delete contractdeposit (no prompt) |

#### ContractDeposit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the customer's contract; it determines this deposit's location, customer, plan, and invoice cycle. |
| `--product-id` | long | ID of the location product charged for this deposit; its current price is used when Price is null. |
| `--notes` | string | Optional operator notes about this deposit. |
| `--price` | decimal | Optional deposit amount in the location's currency; when null, the linked product's current price is used. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--refundable` | bool | Whether cancelling the contract makes this deposit eligible for the dedicated refund workflow, which creates a negative sale that can be included in a credit note. |
| `--invoice-during-online-checkout` | bool | Whether this deposit is charged during the customer's online checkout instead of waiting for the contract's next eligible invoice. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractDeposit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ContractDeposit create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required | ID of the customer's contract; it determines this deposit's location, customer, plan, and invoice cycle. |
| `--product-id` | long, required | ID of the location product charged for this deposit; its current price is used when Price is null. |
| `--notes` | string | Optional operator notes about this deposit. |
| `--price` | decimal | Optional deposit amount in the location's currency; when null, the linked product's current price is used. |
| `--refundable` | bool | Whether cancelling the contract makes this deposit eligible for the dedicated refund workflow, which creates a negative sale that can be included in a credit note. |
| `--invoice-during-online-checkout` | bool | Whether this deposit is charged during the customer's online checkout instead of waiting for the contract's next eligible invoice. |

#### ContractDeposit update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the customer's contract; it determines this deposit's location, customer, plan, and invoice cycle. |
| `--product-id` | long | ID of the location product charged for this deposit; its current price is used when Price is null. |
| `--notes` | string | Optional operator notes about this deposit. |
| `--price` | decimal | Optional deposit amount in the location's currency; when null, the linked product's current price is used. |
| `--refundable` | bool | Whether cancelling the contract makes this deposit eligible for the dedicated refund workflow, which creates a negative sale that can be included in a credit note. |
| `--invoice-during-online-checkout` | bool | Whether this deposit is charged during the customer's online checkout instead of waiting for the contract's next eligible invoice. |

#### ContractDeposit PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-contract-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-contract-coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus contractdeposits update <id> --coworker-contract-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### ContractDeposit (key fields)

`Id`, `ProductName`, `Price`, `Refundable`, `Invoiced`

<!-- END:GENERATED entity=ContractDeposits -->
