# CoworkerInvoiceLines

<!-- BEGIN:GENERATED entity=CoworkerInvoiceLines -->

An invoice line is an individual billed item on a customer invoice. It records the billed description, quantity, net amount, calculated tax, and provenance from the originating contract, booking, charge, pass, time credit, product sale, or event purchase; lines are created and removed through billing workflows, then corrected only while the invoice remains unpaid.

CoworkerInvoiceLines support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkerinvoicelines list --agent` | List all coworkerinvoicelines |
| `nexudus coworkerinvoicelines list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinvoicelines list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinvoicelines list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinvoicelines list --invoice-number <value> --description <value> --agent` | Filter coworkerinvoicelines by properties |
| `nexudus coworkerinvoicelines list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinvoicelines list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerinvoicelines get <id> --agent` | Get single coworkerinvoiceline |
| `nexudus coworkerinvoicelines update <id> --name "New Name" --agent` | Update coworkerinvoiceline |

#### CoworkerInvoiceLine list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the invoice that contains this line; it determines the customer, location, currency, and payment state. |
| `--invoice-number` | string | Invoice number of the parent invoice |
| `--invoice-paid` | bool | Whether the parent invoice has been fully paid |
| `--coworker-invoice-paid-on` | DateTime | Date/time value for coworker invoice paid on |
| `--from-coworker-invoice-paid-on` | range | |
| `--to-coworker-invoice-paid-on` | range | |
| `--invoice-credit-note` | bool | Whether the parent invoice is a credit note |
| `--invoice-currency-code` | string | Currency code of the parent invoice (e.g. USD, EUR) |
| `--coworker-invoice-due-date` | DateTime | Date/time value for coworker invoice due date |
| `--from-coworker-invoice-due-date` | range | |
| `--to-coworker-invoice-due-date` | range | |
| `--description` | string | Required line-item description; shown on the invoice unless DisplayAs supplies replacement printed text. |
| `--display-as` | string | Optional customer-facing text displayed on printed and emailed invoices instead of Description. |
| `--tax-category-name` | string | Optional tax-category name used to resolve the line tax rate; otherwise the customer's personal rate or the location default applies. |
| `--quantity` | int | Number of units on the line; changes the linked product quantity when the line originated from a product sale. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--sub-total` | decimal | Net line amount before tax; changing it recalculates tax and invoice totals and may update the linked charge, pass, time credit, or product sale. |
| `--from-sub-total` | range | |
| `--to-sub-total` | range | |
| `--tax-amount` | decimal | Calculated tax amount for this line, derived from SubTotal and the resolved TaxCategoryName, customer, or location tax rate; do not set directly. |
| `--from-tax-amount` | range | |
| `--to-tax-amount` | range | |
| `--tax-rate` | decimal | Calculated tax percentage applied to this line; resolved from TaxCategoryName, the customer's personal rate, or the location default; do not set directly. |
| `--from-tax-rate` | range | |
| `--to-tax-rate` | range | |
| `--coworker-contract-unique-id` | string | Read-only GUID of the contract that generated this line, when it originated from contract billing. |
| `--contract-deposit-unique-id` | string | Read-only GUID of the contract deposit that generated this line, when applicable. |
| `--booking-unique-id` | string | Read-only GUID of the booking that generated this line, when applicable. |
| `--coworker-extra-service-unique-id` | string | Read-only GUID of the customer's time credit that generated this line, when applicable. |
| `--extra-service-unique-id` | string | Read-only GUID of the underlying booking or printing rate associated with this line, when applicable. |
| `--coworker-time-pass-unique-id` | string | Read-only GUID of the customer's pass that generated this line, when applicable. |
| `--coworker-charge-unique-id` | string | Read-only GUID of the one-off charge that generated this line, when applicable. |
| `--coworker-product-unique-id` | string | Read-only GUID of the customer's product sale that generated this line, when applicable. |
| `--event-attendee-unique-id` | string | Read-only GUID of the event attendance purchase that generated this line, when applicable. |
| `--grouped-line-unique-id` | string | Read-only GUID linking this line to a related grouped invoice line; deleting the parent line also deletes its grouped lines. |
| `--refunded-amount` | decimal | Read-only gross amount already refunded for this line, including tax; it limits further refunds. |
| `--from-refunded-amount` | range | |
| `--to-refunded-amount` | range | |
| `--refunded` | bool | Whether a refund workflow has refunded this line; inspect RefundedAmount for the refunded amount. |
| `--refunded-on` | DateTime | Read-only UTC date and time when a refund workflow refunded this line. |
| `--from-refunded-on` | range | |
| `--to-refunded-on` | range | |
| `--sale-date` | DateTime | Read-only UTC date and time when the underlying sale occurred. |
| `--from-sale-date` | range | |
| `--to-sale-date` | range | |
| `--discount-code` | string | Read-only discount-code text applied when this line was generated. |
| `--discount-amount` | decimal | Read-only discount amount deducted from this line when it was generated. |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--coworker-extra-service-name` | string | Read-only display name of the linked customer time credit. |
| `--coworker-time-pass-name` | string | Read-only display name of the linked customer pass. |
| `--coworker-product-name` | string | Read-only display name of the linked customer product sale. |
| `--event-attendee-product-name` | string | Display name of the linked event attendee product (read-only) |
| `--tariff-name` | string | Read-only name of the plan associated with this line. |
| `--financial-account-code` | string | Financial-account code that categorises this line's revenue for accounting. |
| `--financial-account-name` | string | Financial-account name that categorises this line's revenue for accounting. |
| `--issued-by-unique-id` | string | GUID of the entity that issued this line, such as the issuing contract or location; retain for provenance rather than setting manually. |
| `--cancelled-coworker-invoice-line-unique-id` | string | GUID of the original line cancelled by this line; maintained by cancellation workflows and used when reversing cancellation. |
| `--position` | int | Read-only display order assigned when invoice lines are ordered. |
| `--from-position` | range | |
| `--to-position` | range | |
| `--is-hidden` | bool | Whether this system-created line is hidden from the customer-facing invoice, for example because it is grouped under another line. |
| `--is-universal-credit` | bool | Whether this line represents a universal credit applied to the invoice; maintained from the originating credit configuration. |
| `--purchase-order` | string | Optional purchase-order reference for this line, used when billing splits or groups items by purchase order. |
| `--is-prorated-contract` | bool | Whether this is a system-generated prorated contract adjustment for a mid-cycle change. |
| `--coworker-discount-code-unique-id` | string | Read-only GUID of the customer discount-code record that generated this line's discount. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInvoiceLine sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### CoworkerInvoiceLine update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the invoice that contains this line; it determines the customer, location, currency, and payment state. |
| `--description` | string | Required line-item description; shown on the invoice unless DisplayAs supplies replacement printed text. |
| `--display-as` | string | Optional customer-facing text displayed on printed and emailed invoices instead of Description. |
| `--tax-category-name` | string | Optional tax-category name used to resolve the line tax rate; otherwise the customer's personal rate or the location default applies. |
| `--quantity` | int | Number of units on the line; changes the linked product quantity when the line originated from a product sale. |
| `--sub-total` | decimal | Net line amount before tax; changing it recalculates tax and invoice totals and may update the linked charge, pass, time credit, or product sale. |
| `--tax-amount` | decimal | Calculated tax amount for this line, derived from SubTotal and the resolved TaxCategoryName, customer, or location tax rate; do not set directly. |
| `--tax-rate` | decimal | Calculated tax percentage applied to this line; resolved from TaxCategoryName, the customer's personal rate, or the location default; do not set directly. |
| `--financial-account-code` | string | Financial-account code that categorises this line's revenue for accounting. |
| `--financial-account-name` | string | Financial-account name that categorises this line's revenue for accounting. |
| `--issued-by-unique-id` | string | GUID of the entity that issued this line, such as the issuing contract or location; retain for provenance rather than setting manually. |
| `--cancelled-coworker-invoice-line-unique-id` | string | GUID of the original line cancelled by this line; maintained by cancellation workflows and used when reversing cancellation. |
| `--purchase-order` | string | Optional purchase-order reference for this line, used when billing splits or groups items by purchase order. |

### CoworkerInvoiceLine (key fields)

`Id`, `CoworkerInvoiceInvoiceNumber`, `Description`, `Quantity`, `SubTotal`

<!-- END:GENERATED entity=CoworkerInvoiceLines -->
