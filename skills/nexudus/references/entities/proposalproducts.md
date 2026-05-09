# ProposalProducts

<!-- BEGIN:GENERATED entity=ProposalProducts -->

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
| `--proposal-id` | long |  |
| `--product-id` | long |  |
| `--quantity` | int | Quantity |
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
| `--notes` | string | Notes |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProposalProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long, required |  |
| `--product-id` | long, required |  |
| `--quantity` | int, required | Quantity |
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
| `--notes` | string | Notes |

#### ProposalProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long |  |
| `--product-id` | long |  |
| `--quantity` | int | Quantity |
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
| `--notes` | string | Notes |

### ProposalProduct (key fields)

`Id`, `ProposalCoworkerFullName`, `ProductName`, `Quantity`, `Price`

<!-- END:GENERATED entity=ProposalProducts -->
