# CoworkerProducts

<!-- BEGIN:GENERATED entity=CoworkerProducts -->

A product sale (CoworkerProduct) records a product sold to a customer, either as a one-off purchase or a recurring charge, and can grant the product's included passes, time credit, and booking credit.

CoworkerProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerproducts list --agent` | List all coworkerproducts |
| `nexudus coworkerproducts list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerproducts list --price <value> --agent` | Filter coworkerproducts by properties |
| `nexudus coworkerproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerproducts get <id> --agent` | Get single coworkerproduct |
| `nexudus coworkerproducts create --coworker-id <value> --business-id <value> --product-id <value> --quantity <value> --repeat-cycle <value> --discount-amount <value> --agent` | Create coworkerproduct |
| `nexudus coworkerproducts update <id> --name "New Name" --agent` | Update coworkerproduct |
| `nexudus coworkerproducts delete <id> --yes --agent` | Delete coworkerproduct (no prompt) |

#### CoworkerProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer purchasing this product; the customer must be accessible at the selected location. |
| `--business-id` | long | ID of the location that owns and issues this product sale; set automatically from the tool's location context. |
| `--product-id` | long | ID of the product being sold; the product must be available to the selected customer at this location. |
| `--notes` | string | Optional internal notes about this product sale. |
| `--purchase-order` | string | Optional customer purchase-order reference for this sale. |
| `--activate-now` | bool | Whether to activate included passes, time credit, and booking credit immediately, before the sale is invoiced or paid. |
| `--invoice-this-coworker` | bool | Whether to invoice this customer directly instead of the paying customer in their team. |
| `--price` | decimal | Optional unit-price override in the product currency; when omitted, the product's current price is used, then multiplied by Quantity. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--quantity` | int | Number of product units to sell; must be at least 1 and multiplies price and included benefits. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--regular-charge` | bool | Whether this is a recurring product sale rather than a one-off sale; requires scheduling values for non-PricePlan repeat cycles. |
| `--repeat-cycle` | enum | Recurring schedule pattern: PricePlan, Day, Week, Month, Year, or LastDayOfMonth. PricePlan follows the customer's main contract; prefer ContractProduct for plan-linked recurring products. |
| `--repeat-unit` | int | Positive number of RepeatCycle units between recurring charges; required when RegularCharge is true and RepeatCycle is not PricePlan. |
| `--from-repeat-unit` | range | |
| `--to-repeat-unit` | range | |
| `--invoice-on` | DateTime | Date and time when this sale is next due for invoicing; required for recurring sales whose RepeatCycle is not PricePlan. |
| `--from-invoice-on` | range | |
| `--to-invoice-on` | range | |
| `--repeat-from` | DateTime | Optional date and time from which recurring invoicing begins; a future value delays activation until that date. |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Optional exclusive end date for recurring invoicing; no later charge is created when the next invoicing date reaches this value. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--sale-date` | DateTime | Optional sale date for this product sale; when omitted, reports use the record creation date. |
| `--from-sale-date` | range | |
| `--to-sale-date` | range | |
| `--due-date` | DateTime | Optional date and time by which payment is due; benefits can auto-activate when it has passed and the discounted price is zero. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--mrm-reminded` | bool | Internal reminder-processing flag set after product reminders are handled. |
| `--apply-pro-rating` | bool | Whether the sale price is prorated against the customer's main contract billing period; the product's prorating setting can also apply. |
| `--proposal-unique-id` | string | Internal GUID link to the proposal that created this sale; manage the proposal instead. |
| `--discount-amount` | decimal | Monetary discount amount applied to this sale in the invoice currency. |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--refundable` | bool | Whether the deposit represented by this sale is refunded when its connected contract is cancelled; applies only to deposit products. |
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
| `--coworker-id` | long, required | ID of the customer purchasing this product; the customer must be accessible at the selected location. |
| `--business-id` | long, required | ID of the location that owns and issues this product sale; set automatically from the tool's location context. |
| `--product-id` | long, required | ID of the product being sold; the product must be available to the selected customer at this location. |
| `--notes` | string | Optional internal notes about this product sale. |
| `--purchase-order` | string | Optional customer purchase-order reference for this sale. |
| `--activate-now` | bool | Whether to activate included passes, time credit, and booking credit immediately, before the sale is invoiced or paid. |
| `--invoice-this-coworker` | bool | Whether to invoice this customer directly instead of the paying customer in their team. |
| `--price` | decimal | Optional unit-price override in the product currency; when omitted, the product's current price is used, then multiplied by Quantity. |
| `--quantity` | int, required | Number of product units to sell; must be at least 1 and multiplies price and included benefits. |
| `--regular-charge` | bool | Whether this is a recurring product sale rather than a one-off sale; requires scheduling values for non-PricePlan repeat cycles. |
| `--repeat-cycle` | enum, required | Recurring schedule pattern: PricePlan, Day, Week, Month, Year, or LastDayOfMonth. PricePlan follows the customer's main contract; prefer ContractProduct for plan-linked recurring products. |
| `--repeat-unit` | int | Positive number of RepeatCycle units between recurring charges; required when RegularCharge is true and RepeatCycle is not PricePlan. |
| `--invoice-on` | DateTime | Date and time when this sale is next due for invoicing; required for recurring sales whose RepeatCycle is not PricePlan. |
| `--repeat-from` | DateTime | Optional date and time from which recurring invoicing begins; a future value delays activation until that date. |
| `--repeat-until` | DateTime | Optional exclusive end date for recurring invoicing; no later charge is created when the next invoicing date reaches this value. |
| `--sale-date` | DateTime | Optional sale date for this product sale; when omitted, reports use the record creation date. |
| `--due-date` | DateTime | Optional date and time by which payment is due; benefits can auto-activate when it has passed and the discounted price is zero. |
| `--mrm-reminded` | bool | Internal reminder-processing flag set after product reminders are handled. |
| `--apply-pro-rating` | bool | Whether the sale price is prorated against the customer's main contract billing period; the product's prorating setting can also apply. |
| `--proposal-unique-id` | string | Internal GUID link to the proposal that created this sale; manage the proposal instead. |
| `--discount-amount` | decimal, required | Monetary discount amount applied to this sale in the invoice currency. |
| `--refundable` | bool | Whether the deposit represented by this sale is refunded when its connected contract is cancelled; applies only to deposit products. |

#### CoworkerProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer purchasing this product; the customer must be accessible at the selected location. |
| `--business-id` | long | ID of the location that owns and issues this product sale; set automatically from the tool's location context. |
| `--product-id` | long | ID of the product being sold; the product must be available to the selected customer at this location. |
| `--notes` | string | Optional internal notes about this product sale. |
| `--purchase-order` | string | Optional customer purchase-order reference for this sale. |
| `--invoice-this-coworker` | bool | Whether to invoice this customer directly instead of the paying customer in their team. |
| `--price` | decimal | Optional unit-price override in the product currency; when omitted, the product's current price is used, then multiplied by Quantity. |
| `--quantity` | int | Number of product units to sell; must be at least 1 and multiplies price and included benefits. |
| `--regular-charge` | bool | Whether this is a recurring product sale rather than a one-off sale; requires scheduling values for non-PricePlan repeat cycles. |
| `--repeat-cycle` | enum | Recurring schedule pattern: PricePlan, Day, Week, Month, Year, or LastDayOfMonth. PricePlan follows the customer's main contract; prefer ContractProduct for plan-linked recurring products. |
| `--repeat-unit` | int | Positive number of RepeatCycle units between recurring charges; required when RegularCharge is true and RepeatCycle is not PricePlan. |
| `--invoice-on` | DateTime | Date and time when this sale is next due for invoicing; required for recurring sales whose RepeatCycle is not PricePlan. |
| `--repeat-from` | DateTime | Optional date and time from which recurring invoicing begins; a future value delays activation until that date. |
| `--repeat-until` | DateTime | Optional exclusive end date for recurring invoicing; no later charge is created when the next invoicing date reaches this value. |
| `--sale-date` | DateTime | Optional sale date for this product sale; when omitted, reports use the record creation date. |
| `--due-date` | DateTime | Optional date and time by which payment is due; benefits can auto-activate when it has passed and the discounted price is zero. |
| `--mrm-reminded` | bool | Internal reminder-processing flag set after product reminders are handled. |
| `--apply-pro-rating` | bool | Whether the sale price is prorated against the customer's main contract billing period; the product's prorating setting can also apply. |
| `--proposal-unique-id` | string | Internal GUID link to the proposal that created this sale; manage the proposal instead. |
| `--discount-amount` | decimal | Monetary discount amount applied to this sale in the invoice currency. |
| `--refundable` | bool | Whether the deposit represented by this sale is refunded when its connected contract is cancelled; applies only to deposit products. |

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
