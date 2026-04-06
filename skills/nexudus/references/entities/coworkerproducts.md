# CoworkerProducts

<!-- BEGIN:GENERATED entity=CoworkerProducts -->

A **CoworkerProduct** is a record of a product sold to a customer as a one-off or on a recurrent basis.

`RepeatCycle` can only be set to `PricePlan` if the customer has a contract set as their main contract. In general, it is best to use `ContractProduct` instead of adding CoworkerProducts repeating based on `PricePlan`.

`InvoiceThisCoworker` indicates this customer should be invoiced for this product instead of the paying member of their team.

`ActivateNow` releases any benefits (credits or passes) even before the product is invoiced and paid.

`ProductApplyProRating` indicates the sold product is configured to prorate the price of this sale based on the prorating rules of the main contract of the customer: it adjusts the price based on the number of days left between the current date and the next invoice date (`RenewalDate`) of the customer's main contract.

Properties ending in `UniqueId` link the sale to the originating record using its GUID `UniqueId` property (not the integer ID). Only one of these will be populated per record:

| UniqueId property                | Source entity        |
| -------------------------------- | -------------------- |
| `CoworkerContractUniqueId`       | CoworkerContract     |
| `ContractDepositUniqueId`        | ContractDeposit      |
| `ContractProductUniqueId`        | ContractProduct      |
| `BookingUniqueId`                | Booking              |
| `CoworkerDeliveryUniqueId`       | CoworkerDelivery     |

CoworkerProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerproducts list --agent` | List all coworkerproducts |
| `nexudus coworkerproducts list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerproducts list --price <value> --invoiced <value> --agent` | Filter coworkerproducts by properties |
| `nexudus coworkerproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerproducts get <id> --agent` | Get single coworkerproduct |
| `nexudus coworkerproducts create --coworker-id <value> --business-id <value> --product-id <value> --quantity <value> --repeat-cycle <value> --credit-amount <value> --discount-amount <value> --agent` | Create coworkerproduct |
| `nexudus coworkerproducts update <id> --name "New Name" --agent` | Update coworkerproduct |
| `nexudus coworkerproducts delete <id> --yes --agent` | Delete coworkerproduct (no prompt) |

#### CoworkerProduct list filter options

`--coworker-id`, `--business-id`, `--product-id`, `--notes`, `--purchase-order`, `--activate-now`, `--invoice-this-coworker`, `--price`, `--from-price` (range), `--to-price` (range), `--quantity`, `--from-quantity` (range), `--to-quantity` (range), `--regular-charge`, `--repeat-cycle`, `--repeat-unit`, `--from-repeat-unit` (range), `--to-repeat-unit` (range), `--invoice-on`, `--from-invoice-on` (range), `--to-invoice-on` (range), `--repeat-from`, `--from-repeat-from` (range), `--to-repeat-from` (range), `--repeat-until`, `--from-repeat-until` (range), `--to-repeat-until` (range), `--sale-date`, `--from-sale-date` (range), `--to-sale-date` (range), `--due-date`, `--from-due-date` (range), `--to-due-date` (range), `--invoiced`, `--mrm-reminded`, `--apply-pro-rating`, `--proposal-unique-id`, `--coworker-invoice-id`, `--from-coworker-invoice-id` (range), `--to-coworker-invoice-id` (range), `--coworker-invoice-number`, `--coworker-invoice-paid`, `--credit-amount`, `--from-credit-amount` (range), `--to-credit-amount` (range), `--discount-amount`, `--from-discount-amount` (range), `--to-discount-amount` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerProduct create options

`--coworker-id` (required), `--business-id` (required), `--product-id` (required), `--notes`, `--purchase-order`, `--activate-now`, `--invoice-this-coworker`, `--price`, `--quantity` (required), `--regular-charge`, `--repeat-cycle` (required), `--repeat-unit`, `--invoice-on`, `--repeat-from`, `--repeat-until`, `--sale-date`, `--due-date`, `--invoiced`, `--mrm-reminded`, `--apply-pro-rating`, `--proposal-unique-id`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--credit-amount` (required), `--discount-amount` (required)

#### CoworkerProduct update options

`--coworker-id`, `--business-id`, `--product-id`, `--notes`, `--purchase-order`, `--invoice-this-coworker`, `--price`, `--quantity`, `--regular-charge`, `--repeat-cycle`, `--repeat-unit`, `--invoice-on`, `--repeat-from`, `--repeat-until`, `--sale-date`, `--due-date`, `--invoiced`, `--mrm-reminded`, `--apply-pro-rating`, `--proposal-unique-id`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--credit-amount`, `--discount-amount`

### CoworkerProduct (key fields)

`Id`, `CoworkerFullName`, `ProductName`, `Activated`, `Price`, `Invoiced`

#### CoworkerProduct enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeat-cycle` | `1` PricePlan, `2` Day, `3` Week, `4` Month, `5` Year, `6` LastDayOfMonth |

<!-- END:GENERATED entity=CoworkerProducts -->
