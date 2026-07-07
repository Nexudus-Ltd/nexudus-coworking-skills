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
| `nexudus coworkerproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerproducts get <id> --agent` | Get single coworkerproduct |
| `nexudus coworkerproducts create --coworker-id <value> --business-id <value> --product-id <value> --quantity <value> --repeat-cycle <value> --credit-amount <value> --discount-amount <value> --agent` | Create coworkerproduct |
| `nexudus coworkerproducts update <id> --name "New Name" --agent` | Update coworkerproduct |
| `nexudus coworkerproducts delete <id> --yes --agent` | Delete coworkerproduct (no prompt) |

#### CoworkerProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--notes` | string | Optional notes or comments about this coworker product |
| `--purchase-order` | string | Purchase order |
| `--activate-now` | bool | Activate immediately, releasing any benefits (credits or passes) even before the product is invoiced and paid |
| `--invoice-this-coworker` | bool | Invoice this customer for this product instead of the paying member of their team |
| `--price` | decimal | Price override |
| `--from-price` | range | |
| `--to-price` | range | |
| `--quantity` | int | Number of units |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--repeat-cycle` | enum | Repeat cycle pattern. PricePlan can only be used if the customer has a main contract; prefer ContractProduct instead of CoworkerProducts repeating on PricePlan |
| `--repeat-unit` | int | Number of repeat units |
| `--from-repeat-unit` | range | |
| `--to-repeat-unit` | range | |
| `--invoice-on` | DateTime | Invoice on date |
| `--from-invoice-on` | range | |
| `--to-invoice-on` | range | |
| `--repeat-from` | DateTime | Repeat from date |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Repeat until date |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--sale-date` | DateTime | Sale date |
| `--from-sale-date` | range | |
| `--to-sale-date` | range | |
| `--due-date` | DateTime | Due date |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--invoiced` | bool | Whether it has been invoiced |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |
| `--apply-pro-rating` | bool | Apply pro-rating |
| `--proposal-unique-id` | string | ID of the proposal unique associated with this record |
| `--coworker-invoice-id` | int | Coworker invoice ID |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string | Coworker invoice number |
| `--coworker-invoice-paid` | bool | Whether coworker invoice is paid |
| `--credit-amount` | decimal | Credit amount |
| `--from-credit-amount` | range | |
| `--to-credit-amount` | range | |
| `--discount-amount` | decimal | Discount amount |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--refundable` | bool | Whether this product sale can be refunded |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerProduct sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### CoworkerProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--product-id` | long, required | ID of the product linked to this record |
| `--notes` | string | Optional notes or comments about this coworker product |
| `--purchase-order` | string | Purchase order |
| `--activate-now` | bool | Activate immediately, releasing any benefits (credits or passes) even before the product is invoiced and paid |
| `--invoice-this-coworker` | bool | Invoice this customer for this product instead of the paying member of their team |
| `--price` | decimal | Price override |
| `--quantity` | int, required | Number of units |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--repeat-cycle` | enum, required | Repeat cycle pattern. PricePlan can only be used if the customer has a main contract; prefer ContractProduct instead of CoworkerProducts repeating on PricePlan |
| `--repeat-unit` | int | Number of repeat units |
| `--invoice-on` | DateTime | Invoice on date |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |
| `--sale-date` | DateTime | Sale date |
| `--due-date` | DateTime | Due date |
| `--invoiced` | bool | Whether it has been invoiced |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |
| `--apply-pro-rating` | bool | Apply pro-rating |
| `--proposal-unique-id` | string | ID of the proposal unique associated with this record |
| `--coworker-invoice-id` | int | Coworker invoice ID |
| `--coworker-invoice-number` | string | Coworker invoice number |
| `--coworker-invoice-paid` | bool | Whether coworker invoice is paid |
| `--credit-amount` | decimal, required | Credit amount |
| `--discount-amount` | decimal, required | Discount amount |
| `--refundable` | bool | Whether this product sale can be refunded |

#### CoworkerProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--notes` | string | Optional notes or comments about this coworker product |
| `--purchase-order` | string | Purchase order |
| `--invoice-this-coworker` | bool | Invoice this customer for this product instead of the paying member of their team |
| `--price` | decimal | Price override |
| `--quantity` | int | Number of units |
| `--regular-charge` | bool | Whether this is a regular charge |
| `--repeat-cycle` | enum | Repeat cycle pattern. PricePlan can only be used if the customer has a main contract; prefer ContractProduct instead of CoworkerProducts repeating on PricePlan |
| `--repeat-unit` | int | Number of repeat units |
| `--invoice-on` | DateTime | Invoice on date |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |
| `--sale-date` | DateTime | Sale date |
| `--due-date` | DateTime | Due date |
| `--invoiced` | bool | Whether it has been invoiced |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |
| `--apply-pro-rating` | bool | Apply pro-rating |
| `--proposal-unique-id` | string | ID of the proposal unique associated with this record |
| `--coworker-invoice-id` | int | Coworker invoice ID |
| `--coworker-invoice-number` | string | Coworker invoice number |
| `--coworker-invoice-paid` | bool | Whether coworker invoice is paid |
| `--credit-amount` | decimal | Credit amount |
| `--discount-amount` | decimal | Discount amount |
| `--refundable` | bool | Whether this product sale can be refunded |

#### CoworkerProduct PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerproducts update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerProduct (key fields)

`Id`, `CoworkerFullName`, `ProductName`, `Activated`, `Price`, `Invoiced`

#### CoworkerProduct enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeat-cycle` | `1` PricePlan, `2` Day, `3` Week, `4` Month, `5` Year, `6` LastDayOfMonth |

<!-- END:GENERATED entity=CoworkerProducts -->
