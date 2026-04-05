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
| `nexudus proposalproducts create --proposal-id <value> --product-id <value> --quantity <value> --agent` | Create proposalproduct |
| `nexudus proposalproducts update <id> --name "New Name" --agent` | Update proposalproduct |
| `nexudus proposalproducts delete <id> --yes --agent` | Delete proposalproduct (no prompt) |

#### ProposalProduct list filter options

`--proposal-id`, `--product-id`, `--quantity`, `--from-quantity` (range), `--to-quantity` (range), `--price`, `--from-price` (range), `--to-price` (range), `--is-deposit`, `--is-contract-product`, `--regular-charge`, `--repeat-cycle`, `--invoice-on`, `--from-invoice-on` (range), `--to-invoice-on` (range), `--repeat-from`, `--from-repeat-from` (range), `--to-repeat-from` (range), `--repeat-until`, `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-unit`, `--from-repeat-unit` (range), `--to-repeat-unit` (range), `--apply-pro-rating`, `--notes`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ProposalProduct create options

`--proposal-id` (required), `--product-id` (required), `--quantity` (required), `--price`, `--is-deposit`, `--is-contract-product`, `--regular-charge`, `--repeat-cycle`, `--invoice-on`, `--repeat-from`, `--repeat-until`, `--repeat-unit`, `--apply-pro-rating`, `--notes`

#### ProposalProduct update options

`--proposal-id`, `--product-id`, `--quantity`, `--price`, `--is-deposit`, `--is-contract-product`, `--regular-charge`, `--repeat-cycle`, `--invoice-on`, `--repeat-from`, `--repeat-until`, `--repeat-unit`, `--apply-pro-rating`, `--notes`

### ProposalProduct (key fields)

`Id`, `ProposalCoworkerFullName`, `ProductName`, `Quantity`, `Price`

<!-- END:GENERATED entity=ProposalProducts -->
