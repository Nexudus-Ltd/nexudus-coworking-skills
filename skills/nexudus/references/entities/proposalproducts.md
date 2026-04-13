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

`--proposal-id` (long), `--product-id` (long), `--quantity` (int), `--from-quantity` (range), `--to-quantity` (range), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--is-deposit` (bool), `--is-contract-product` (bool), `--regular-charge` (bool), `--repeat-cycle` (enum), `--invoice-on` (DateTime), `--from-invoice-on` (range), `--to-invoice-on` (range), `--repeat-from` (DateTime), `--from-repeat-from` (range), `--to-repeat-from` (range), `--repeat-until` (DateTime), `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-unit` (int), `--from-repeat-unit` (range), `--to-repeat-unit` (range), `--apply-pro-rating` (bool), `--notes`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ProposalProduct create options

`--proposal-id` (long, required), `--product-id` (long, required), `--quantity` (int, required), `--price` (decimal), `--is-deposit` (bool), `--is-contract-product` (bool), `--regular-charge` (bool), `--repeat-cycle` (enum, required), `--invoice-on` (DateTime), `--repeat-from` (DateTime), `--repeat-until` (DateTime), `--repeat-unit` (int), `--apply-pro-rating` (bool), `--notes`

#### ProposalProduct update options

`--proposal-id` (long), `--product-id` (long), `--quantity` (int), `--price` (decimal), `--is-deposit` (bool), `--is-contract-product` (bool), `--regular-charge` (bool), `--repeat-cycle` (enum), `--invoice-on` (DateTime), `--repeat-from` (DateTime), `--repeat-until` (DateTime), `--repeat-unit` (int), `--apply-pro-rating` (bool), `--notes`

### ProposalProduct (key fields)

`Id`, `ProposalCoworkerFullName`, `ProductName`, `Quantity`, `Price`

<!-- END:GENERATED entity=ProposalProducts -->
