# Charges

<!-- BEGIN:GENERATED entity=Charges -->

A charge (internal name CoworkerCharge) is a one-off debit billed to a customer at a location. It records the item, quantity, amount, optional tax, discount, credit, and invoicing timing; a recurring charge is eligible only when the customer's main contract is due for renewal.

Charges support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus charges list --agent` | List all charges |
| `nexudus charges list --id <id> --agent` | Filter by single ID |
| `nexudus charges list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus charges list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus charges list --charge-number <value> --description <value> --agent` | Filter charges by properties |
| `nexudus charges list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus charges list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus charges get <id> --agent` | Get single charge |
| `nexudus charges create --coworker-id <value> --business-id <value> --quantity <value> --total-amount <value> --agent` | Create charge |
| `nexudus charges update <id> --name "New Name" --agent` | Update charge |
| `nexudus charges delete <id> --yes --agent` | Delete charge (no prompt) |

#### Charge list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer billed for this charge; the customer's invoicing location controls access. |
| `--business-id` | long | ID of the location that issued this charge and whose currency applies. |
| `--business-name` | string | Display value for Business.Name. |
| `--business-currency-code` | string | Display value for Business.Currency.Code. |
| `--charge-number` | string | Read-only unique charge number assigned by the system after creation. |
| `--quantity` | int | Number of units billed by this charge; defaults to 1. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--description` | string | Description of the billed item or service. |
| `--invoice-line-display-as` | string | Optional customer-facing text to display for the resulting invoice line instead of Description. |
| `--regular-charge` | bool | Whether this recurring charge is invoiced only when the customer has a main contract due for renewal. |
| `--discount-code` | string | Read-only discount-code text copied to this charge when it is generated. |
| `--due-date` | DateTime | Optional UTC date and time before which this charge is not eligible to be invoiced. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--total-amount` | decimal | Total monetary amount charged to the customer. |
| `--from-total-amount` | range | |
| `--to-total-amount` | range | |
| `--purchase-order` | string | Optional purchase-order reference used for invoice grouping and billing. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied to this charge; required when the issuing location requires tax rates. |
| `--tax-rate-name` | string | Display value for TaxRate.Name. |
| `--financial-account-id` | long | Optional ID of the financial account that categorises this charge; required when the issuing location requires financial accounts. |
| `--financial-account-name` | string | Display value for FinancialAccount.Name. |
| `--invoiced` | bool | Whether this charge has been added to an invoice; changing an invoiced charge is blocked for locked periods and its amount cannot change after payment. |
| `--invoiced-on` | DateTime | Read-only UTC date and time set when this charge is marked invoiced. |
| `--from-invoiced-on` | range | |
| `--to-invoiced-on` | range | |
| `--sale-date` | DateTime | Optional UTC date and time when the underlying sale occurred. |
| `--from-sale-date` | range | |
| `--to-sale-date` | range | |
| `--coworker-extra-service-name` | string | System-maintained display name of the customer time credit associated with this charge. |
| `--coworker-time-pass-name` | string | System-maintained display name of the customer pass associated with this charge. |
| `--coworker-product-name` | string | System-maintained display name of the customer product sale associated with this charge. |
| `--tariff-name` | string | System-maintained name of the plan associated with this charge. |
| `--coworker-product-unique-id` | string | System-maintained GUID of the customer product sale that generated this charge, when applicable. |
| `--booking-unique-id` | string | System-maintained GUID of the booking that generated this charge, when applicable. |
| `--coworker-contract-unique-id` | string | Read-only GUID of the contract that generated this charge, when applicable. |
| `--coworker-extra-service-unique-id` | string | Read-only GUID of the customer time credit that generated this charge, when applicable. |
| `--extra-service-unique-id` | string | Read-only GUID of the underlying booking or printing rate associated with this charge, when applicable. |
| `--coworker-time-pass-unique-id` | string | Read-only GUID of the customer pass that generated this charge, when applicable. |
| `--coworker-charge-unique-id` | string | Read-only GUID of the related originating charge, when this charge was created from another charge. |
| `--event-attendee-unique-id` | string | Read-only GUID of the event attendance purchase that generated this charge, when applicable. |
| `--invoice-from-date` | DateTime | Read-only UTC start date and time of the billed invoice period, when applicable. |
| `--from-invoice-from-date` | range | |
| `--to-invoice-from-date` | range | |
| `--invoice-to-date` | DateTime | Read-only UTC end date and time of the billed invoice period, when applicable. |
| `--from-invoice-to-date` | range | |
| `--to-invoice-to-date` | range | |
| `--repeat-from` | DateTime | Optional UTC date and time from which this recurring charge may be invoiced. |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Optional UTC date and time after which this recurring charge must stop being invoiced. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--coworker-discount-code-unique-id` | string | Read-only GUID of the customer discount-code record that generated this charge's discount. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Charge sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Charge create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer billed for this charge; the customer's invoicing location controls access. |
| `--business-id` | long, required | ID of the location that issued this charge and whose currency applies. |
| `--quantity` | int, required | Number of units billed by this charge; defaults to 1. |
| `--description` | string | Description of the billed item or service. |
| `--invoice-line-display-as` | string | Optional customer-facing text to display for the resulting invoice line instead of Description. |
| `--regular-charge` | bool | Whether this recurring charge is invoiced only when the customer has a main contract due for renewal. |
| `--due-date` | DateTime | Optional UTC date and time before which this charge is not eligible to be invoiced. |
| `--total-amount` | decimal, required | Total monetary amount charged to the customer. |
| `--purchase-order` | string | Optional purchase-order reference used for invoice grouping and billing. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied to this charge; required when the issuing location requires tax rates. |
| `--financial-account-id` | long | Optional ID of the financial account that categorises this charge; required when the issuing location requires financial accounts. |
| `--invoiced` | bool | Whether this charge has been added to an invoice; changing an invoiced charge is blocked for locked periods and its amount cannot change after payment. |
| `--sale-date` | DateTime | Optional UTC date and time when the underlying sale occurred. |
| `--coworker-extra-service-name` | string | System-maintained display name of the customer time credit associated with this charge. |
| `--coworker-time-pass-name` | string | System-maintained display name of the customer pass associated with this charge. |
| `--coworker-product-name` | string | System-maintained display name of the customer product sale associated with this charge. |
| `--tariff-name` | string | System-maintained name of the plan associated with this charge. |
| `--coworker-product-unique-id` | string | System-maintained GUID of the customer product sale that generated this charge, when applicable. |
| `--booking-unique-id` | string | System-maintained GUID of the booking that generated this charge, when applicable. |
| `--repeat-from` | DateTime | Optional UTC date and time from which this recurring charge may be invoiced. |
| `--repeat-until` | DateTime | Optional UTC date and time after which this recurring charge must stop being invoiced. |

#### Charge update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer billed for this charge; the customer's invoicing location controls access. |
| `--business-id` | long | ID of the location that issued this charge and whose currency applies. |
| `--quantity` | int | Number of units billed by this charge; defaults to 1. |
| `--description` | string | Description of the billed item or service. |
| `--invoice-line-display-as` | string | Optional customer-facing text to display for the resulting invoice line instead of Description. |
| `--regular-charge` | bool | Whether this recurring charge is invoiced only when the customer has a main contract due for renewal. |
| `--due-date` | DateTime | Optional UTC date and time before which this charge is not eligible to be invoiced. |
| `--total-amount` | decimal | Total monetary amount charged to the customer. |
| `--purchase-order` | string | Optional purchase-order reference used for invoice grouping and billing. |
| `--tax-rate-id` | long | Optional ID of the tax rate applied to this charge; required when the issuing location requires tax rates. |
| `--financial-account-id` | long | Optional ID of the financial account that categorises this charge; required when the issuing location requires financial accounts. |
| `--invoiced` | bool | Whether this charge has been added to an invoice; changing an invoiced charge is blocked for locked periods and its amount cannot change after payment. |
| `--sale-date` | DateTime | Optional UTC date and time when the underlying sale occurred. |
| `--coworker-extra-service-name` | string | System-maintained display name of the customer time credit associated with this charge. |
| `--coworker-time-pass-name` | string | System-maintained display name of the customer pass associated with this charge. |
| `--coworker-product-name` | string | System-maintained display name of the customer product sale associated with this charge. |
| `--tariff-name` | string | System-maintained name of the plan associated with this charge. |
| `--coworker-product-unique-id` | string | System-maintained GUID of the customer product sale that generated this charge, when applicable. |
| `--booking-unique-id` | string | System-maintained GUID of the booking that generated this charge, when applicable. |
| `--repeat-from` | DateTime | Optional UTC date and time from which this recurring charge may be invoiced. |
| `--repeat-until` | DateTime | Optional UTC date and time after which this recurring charge must stop being invoiced. |

### Charge (key fields)

`Id`, `ChargeNumber`, `Description`, `TotalAmount`, `Invoiced`

<!-- END:GENERATED entity=Charges -->
