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

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long |  |
| `--product-id` | long |  |
| `--notes` | string | Optional notes or internal comments about this deposit |
| `--price` | decimal | Deposit amount to charge. When set, overrides the default price of the linked product |
| `--from-price` | range | |
| `--to-price` | range | |
| `--refundable` | bool | When true, cancelling the parent contract automatically generates a credit note for the deposit amount, which can be applied against outstanding fees or damages |
| `--invoice-during-online-checkout` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractDeposit create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required |  |
| `--product-id` | long, required |  |
| `--notes` | string | Optional notes or internal comments about this deposit |
| `--price` | decimal | Deposit amount to charge. When set, overrides the default price of the linked product |
| `--refundable` | bool | When true, cancelling the parent contract automatically generates a credit note for the deposit amount, which can be applied against outstanding fees or damages |
| `--invoice-during-online-checkout` | bool |  |

#### ContractDeposit update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long |  |
| `--product-id` | long |  |
| `--notes` | string | Optional notes or internal comments about this deposit |
| `--price` | decimal | Deposit amount to charge. When set, overrides the default price of the linked product |
| `--refundable` | bool | When true, cancelling the parent contract automatically generates a credit note for the deposit amount, which can be applied against outstanding fees or damages |
| `--invoice-during-online-checkout` | bool |  |

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
