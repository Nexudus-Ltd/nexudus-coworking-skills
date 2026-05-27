# ProposalProducts

<!-- BEGIN:GENERATED entity=ProposalProducts -->

A **ProposalProduct** links a product to a proposal, defining additional items or services included in the offer with their pricing and recurrence settings.

ProposalProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalproducts list --agent` | List all proposalproducts |
| `nexudus proposalproducts list --id <id> --agent` | Filter by single ID |
| `nexudus proposalproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalproducts list --quantity <value> --price <value> --agent` | Filter proposalproducts by properties |
| `nexudus proposalproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalproducts get <id> --agent` | Get single proposalproduct |
| `nexudus proposalproducts create --proposal-id <value> --product-id <value> --quantity <value> --repeat-cycle <value> --agent` | Create proposalproduct |
| `nexudus proposalproducts update <id> --name "New Name" --agent` | Update proposalproduct |
| `nexudus proposalproducts delete <id> --yes --agent` | Delete proposalproduct (no prompt) |

#### ProposalProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--quantity` | int | Number of units |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--price` | decimal | Price override |
| `--from-price` | range | |
| `--to-price` | range | |
| `--is-deposit` | bool | Whether this is a deposit |
| `--is-contract-product` | bool | Whether this is a contract product |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--repeat-cycle` | enum | Repeat cycle pattern |
| `--invoice-on` | DateTime | Invoice on date |
| `--from-invoice-on` | range | |
| `--to-invoice-on` | range | |
| `--repeat-from` | DateTime | Repeat from date |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Repeat until date |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-unit` | int | Number of repeat units |
| `--from-repeat-unit` | range | |
| `--to-repeat-unit` | range | |
| `--apply-pro-rating` | bool | Apply pro-rating |
| `--notes` | string | Optional notes or comments about this proposal product |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProposalProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long, required | ID of the proposal linked to this record |
| `--product-id` | long, required | ID of the product linked to this record |
| `--quantity` | int, required | Number of units |
| `--price` | decimal | Price override |
| `--is-deposit` | bool | Whether this is a deposit |
| `--is-contract-product` | bool | Whether this is a contract product |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--repeat-cycle` | enum, required | Repeat cycle pattern |
| `--invoice-on` | DateTime | Invoice on date |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |
| `--repeat-unit` | int | Number of repeat units |
| `--apply-pro-rating` | bool | Apply pro-rating |
| `--notes` | string | Optional notes or comments about this proposal product |

#### ProposalProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--quantity` | int | Number of units |
| `--price` | decimal | Price override |
| `--is-deposit` | bool | Whether this is a deposit |
| `--is-contract-product` | bool | Whether this is a contract product |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--repeat-cycle` | enum | Repeat cycle pattern |
| `--invoice-on` | DateTime | Invoice on date |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |
| `--repeat-unit` | int | Number of repeat units |
| `--apply-pro-rating` | bool | Apply pro-rating |
| `--notes` | string | Optional notes or comments about this proposal product |

#### ProposalProduct PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--proposal-coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--proposal-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus proposalproducts update <id> --proposal-coworker-email "«PII:EMAIL:a3f2b1c9»" --agent`

### ProposalProduct (key fields)

`Id`, `ProposalCoworkerFullName`, `ProductName`, `Quantity`, `Price`

#### ProposalProduct enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeat-cycle` | `1` PricePlan, `2` Day, `3` Week, `4` Month, `5` Year, `6` LastDayOfMonth |

<!-- END:GENERATED entity=ProposalProducts -->
