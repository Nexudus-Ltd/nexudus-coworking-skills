# Tariffs

<!-- BEGIN:GENERATED entity=Tariffs -->

A **Tariff** (also called a Plan) is a membership plan that customers can sign up to in exchange for access to a coworking space and other benefits. Tariffs are the foundation for contracts — every time a customer signs up to a plan, Nexudus generates a `CoworkerContract` for that member based on the plan's settings.

Plans define billing frequency (in months or weeks via `InvoiceEvery` / `InvoiceEveryWeeks`), pricing, cancellation rules, and limits on check-ins, booking minutes, visitor passes, and hours. Members are invoiced at the end of each billing cycle. Plans can include benefits such as day passes, booking credits, and money credits — these are configured through `CoworkerExtraService` and `Product` entities linked to the contract.

Use `SystemTariffType` to categorise the plan (e.g. FullTimeHotDesk, VirtualOffice, Storage). Use `Visible` to control whether the plan appears on the members portal. Plans can optionally require identity checks before activation, enforce contract terms, support pausing, and define delivery handling preferences for virtual office mail.

When you edit a plan, changes impact all members signed up to that plan. To customise settings for an individual member, edit their `CoworkerContract` instead.

Tariffs support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffs list --agent` | List all tariffs |
| `nexudus tariffs list --id <id> --agent` | Filter by single ID |
| `nexudus tariffs list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffs list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffs list --name <value> --system-tariff-type <value> --agent` | Filter tariffs by properties |
| `nexudus tariffs list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffs list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tariffs get <id> --agent` | Get single tariff |
| `nexudus tariffs create --business-id <value> --name <value> --system-tariff-type <value> --price <value> --currency-id <value> --cancellation-period <value> --display-order <value> --invoice-every <value> --invoice-every-weeks <value> --booking-due-date-strategy <value> --address-identity-check-provider <value> --address-identity-check-repeat-pattern <value> --identity-check-provider <value> --identity-check-repeat-pattern <value> --delivery-preferences-mail <value> --delivery-preferences-parcels <value> --delivery-preferences-checks <value> --delivery-preferences-publicity <value> --delivery-preferences-other <value> --agent` | Create tariff |
| `nexudus tariffs update <id> --name "New Name" --agent` | Update tariff |
| `nexudus tariffs delete <id> --yes --agent` | Delete tariff (no prompt) |

#### Tariff list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Plan name |
| `--system-tariff-type` | enum | Category of the plan: FullTimePrivateOffice, PartTimePrivateOffice, FullTimeDedicatedDesk, PartTimeDedicatedDesk, FullTimeHotDesk, PartTimeHotDesk, FullTimeOther, PartTimeOther, Storage, VirtualOffice, Virtual, or Other |
| `--price` | decimal | Recurring price charged per billing cycle |
| `--from-price` | range | |
| `--to-price` | range | |
| `--default-invoicing-day` | int | Day of the month on which invoices are generated for members on this plan |
| `--from-default-invoicing-day` | range | |
| `--to-default-invoicing-day` | range | |
| `--visible` | bool | Whether the plan is visible to customers on the members portal and mobile app |
| `--available-to-ai` | bool | Whether this plan is available to any AI channels (Email, Chat or WhatsApp) for recommendations for private offices; |
| `--notes-for-ai` | string | Custom notes provided to the AI assistant when describing this plan |
| `--show-price-for-ai` | bool | Whether to show the plan price to the AI assistant |
| `--price-for-ai` | decimal | Custom price shown to the AI assistant instead of the actual price |
| `--from-price-for-ai` | range | |
| `--to-price-for-ai` | range | |
| `--use-time-passes` | bool | Whether this plan uses time passes for check-in access |
| `--description` | string | Plan description shown to customers |
| `--invoice-line-display-as` | string | Custom text shown on the invoice line instead of the plan name |
| `--sign-up-fee` | decimal | One-off fee charged when a customer first signs up to this plan |
| `--from-sign-up-fee` | range | |
| `--to-sign-up-fee` | range | |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | Standard tax rate applied to charges on this plan |
| `--reduced-tax-rate-id` | long | Reduced tax rate applied when applicable |
| `--exempt-tax-rate-id` | long | Tax-exempt rate applied when applicable |
| `--financial-account-id` | long | Financial account used for revenue tracking |
| `--terms-and-conditions` | string | Terms and conditions text that members must accept when signing up |
| `--new-contract-document-url` | string | URL to upload a new contract document template |
| `--clear-contract-document-file` | bool | Set to true to remove the uploaded contract document file |
| `--cancellation-period` | int | Number of days' notice required before a contract can be cancelled |
| `--from-cancellation-period` | range | |
| `--to-cancellation-period` | range | |
| `--display-order` | int | Display order on the members portal (lower numbers appear first) |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--group-name` | string | Group name used to visually group plans together on the members portal |
| `--disable-portal-cancellations` | bool | Prevents members from cancelling this plan through the members portal |
| `--subscribers-limit` | int | Maximum number of members that can be signed up to this plan at any time |
| `--from-subscribers-limit` | range | |
| `--to-subscribers-limit` | range | |
| `--cancellation-limit-days` | int | Minimum number of days a contract must be active before it can be cancelled |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--default-contract-term` | int | Default minimum contract term in months for new sign-ups |
| `--from-default-contract-term` | range | |
| `--to-default-contract-term` | range | |
| `--cancel-member-account-after` | int | Number of days after contract cancellation before the member account is deactivated |
| `--from-cancel-member-account-after` | range | |
| `--to-cancel-member-account-after` | range | |
| `--checkin-price-plan-limit` | int | Maximum number of check-ins included per billing cycle |
| `--from-checkin-price-plan-limit` | range | |
| `--to-checkin-price-plan-limit` | range | |
| `--checkin-month-limit` | int | Maximum number of check-ins allowed per month |
| `--from-checkin-month-limit` | range | |
| `--to-checkin-month-limit` | range | |
| `--checkin-week-limit` | int | Maximum number of check-ins allowed per week |
| `--from-checkin-week-limit` | range | |
| `--to-checkin-week-limit` | range | |
| `--visitor-month-limit` | int | Maximum number of visitor passes allowed per month |
| `--from-visitor-month-limit` | range | |
| `--to-visitor-month-limit` | range | |
| `--visitor-week-limit` | int | Maximum number of visitor passes allowed per week |
| `--from-visitor-week-limit` | range | |
| `--to-visitor-week-limit` | range | |
| `--visitor-day-limit` | int | Maximum number of visitor passes allowed per day |
| `--from-visitor-day-limit` | range | |
| `--to-visitor-day-limit` | range | |
| `--hours-price-plan-limit` | int | Maximum number of hours included per billing cycle |
| `--from-hours-price-plan-limit` | range | |
| `--to-hours-price-plan-limit` | range | |
| `--hours-month-limit` | int | Maximum number of hours allowed per month |
| `--from-hours-month-limit` | range | |
| `--to-hours-month-limit` | range | |
| `--hours-week-limit` | int | Maximum number of hours allowed per week |
| `--from-hours-week-limit` | range | |
| `--to-hours-week-limit` | range | |
| `--booking-minute-week-limit` | int | Maximum booking minutes allowed per week |
| `--from-booking-minute-week-limit` | range | |
| `--to-booking-minute-week-limit` | range | |
| `--booking-minute-month-limit` | int | Maximum booking minutes allowed per month |
| `--from-booking-minute-month-limit` | range | |
| `--to-booking-minute-month-limit` | range | |
| `--discount-extra-services` | decimal | Discount percentage for extra services |
| `--from-discount-extra-services` | range | |
| `--to-discount-extra-services` | range | |
| `--discount-time-passes` | decimal | Discount percentage for time passes |
| `--from-discount-time-passes` | range | |
| `--to-discount-time-passes` | range | |
| `--discount-charges` | decimal | Discount percentage for charges |
| `--from-discount-charges` | range | |
| `--to-discount-charges` | range | |
| `--invoice-every` | int | Billing cycle length in months. Set to 0 if billing by weeks instead |
| `--from-invoice-every` | range | |
| `--to-invoice-every` | range | |
| `--invoice-every-weeks` | int | Billing cycle length in weeks. Set to 0 if billing by months instead |
| `--from-invoice-every-weeks` | range | |
| `--to-invoice-every-weeks` | range | |
| `--auto-cancel-after` | int | Number of days after which the contract is automatically cancelled if not paid |
| `--from-auto-cancel-after` | range | |
| `--to-auto-cancel-after` | range | |
| `--advance-invoice-cycles` | int | Number of billing cycles to invoice in advance |
| `--from-advance-invoice-cycles` | range | |
| `--to-advance-invoice-cycles` | range | |
| `--prorate-day-of-month` | int | Day of the month used to align billing cycles when prorating |
| `--from-prorate-day-of-month` | range | |
| `--to-prorate-day-of-month` | range | |
| `--prorate-days-before` | int | Number of days before the prorate day to start prorating |
| `--from-prorate-days-before` | range | |
| `--to-prorate-days-before` | range | |
| `--prorate-cancellations` | bool | Whether to prorate the final invoice when a contract is cancelled mid-cycle |
| `--charge-and-extend` | int | Number of days to extend a contract after payment is received |
| `--from-charge-and-extend` | range | |
| `--to-charge-and-extend` | range | |
| `--exclude-from-invoice` | bool | Whether to exclude this plan's charges from member invoices |
| `--auto-raise-invoices` | bool | Whether to automatically generate invoices at the end of each billing cycle |
| `--raise-invoice-every` | int | Raise invoice every N months |
| `--from-raise-invoice-every` | range | |
| `--to-raise-invoice-every` | range | |
| `--raise-invoice-every-weeks` | int | Raise invoice every N weeks |
| `--from-raise-invoice-every-weeks` | range | |
| `--to-raise-invoice-every-weeks` | range | |
| `--minimum-price` | decimal | Minimum total amount charged per billing cycle regardless of usage |
| `--from-minimum-price` | range | |
| `--to-minimum-price` | range | |
| `--minimum-price-include-time-passes` | bool | Whether time pass charges count towards the minimum price |
| `--minimum-price-include-extra-services` | bool | Whether extra service charges count towards the minimum price |
| `--minimum-price-include-events` | bool | Whether event charges count towards the minimum price |
| `--archived` | bool | Whether the plan is archived and no longer available for new sign-ups |
| `--starred` | bool | Whether the plan is starred (highlighted) on the members portal |
| `--keep-new-accounts-on-hold` | bool | Whether new sign-ups are kept on hold until manually approved |
| `--can-be-paused` | bool | Whether members can pause their contract on this plan |
| `--pause-yearly-limit` | int | Maximum number of times a contract can be paused per year |
| `--from-pause-yearly-limit` | range | |
| `--to-pause-yearly-limit` | range | |
| `--pause-cycles-limit` | int | Maximum number of billing cycles a contract can be paused for |
| `--from-pause-cycles-limit` | range | |
| `--to-pause-cycles-limit` | range | |
| `--booking-due-date-strategy` | enum | Strategy for determining when booking charges are due: RenewalDate, BookingEndDate, BookingCreationDate, or NextNthOfMonth |
| `--booking-due-date-day-of-month` | int | Day of the month used when BookingDueDateStrategy is NextNthOfMonth |
| `--from-booking-due-date-day-of-month` | range | |
| `--to-booking-due-date-day-of-month` | range | |
| `--is-virtual-office` | bool | Whether this is a virtual office plan with mail handling features |
| `--wait-for-identity-checks-to-activate` | bool | Whether to keep the contract on hold until all required identity checks are completed |
| `--request-address-identity-check` | bool | Whether to request an address identity check from members signing up to this plan |
| `--address-identity-check-description` | string | Instructions shown to members when completing the address identity check |
| `--address-identity-check-provider` | enum | Provider used for address identity checks: Manual or StripeIdentity |
| `--keep-paused-if-address-mismatch` | bool | Whether to keep the contract paused if the address identity check reveals a mismatch |
| `--address-identity-check-repeat-pattern` | enum | How often to repeat the address identity check: Never, Every3Months, Every6Months, Every12Months, or Every24Months |
| `--request-identity-check` | bool | Whether to request an identity (ID document) check from members signing up to this plan |
| `--identity-check-provider` | enum | Provider used for identity checks: Manual or StripeIdentity |
| `--identity-check-repeat-pattern` | enum | How often to repeat the identity check: Never, Every3Months, Every6Months, Every12Months, or Every24Months |
| `--identity-check-description` | string | Instructions shown to members when completing the identity check |
| `--request-aml-check` | bool | Whether to request an AML check from members signing up to this plan |
| `--aml-check-open-sanctions-enabled` | bool | Whether to enable AML checks against the OpenSanctions dataset |
| `--aml-check-pappers-enabled` | bool | Whether to enable AML checks against the Pappers dataset |
| `--aml-check-open-sanctions-dataset` | string | Which OpenSanctions dataset to check against for AML screening (e.g. 'default') |
| `--aml-check-score-threshold` | decimal | Score threshold for AML checks, between 0 and 1. Matches with a score above this threshold will be considered a positive match. Default is 0.7 |
| `--from-aml-check-score-threshold` | range | |
| `--to-aml-check-score-threshold` | range | |
| `--send-onboarding-form-by-email` | bool | Whether to email the onboarding form to new members signing up to this plan |
| `--form-page-id` | long | ID of the onboarding form page sent to new members |
| `--delivery-preferences-mail` | enum | Allowed handling preferences for mail deliveries (virtual office) |
| `--delivery-preferences-parcels` | enum | Allowed handling preferences for parcel deliveries (virtual office) |
| `--delivery-preferences-checks` | enum | Allowed handling preferences for check deliveries (virtual office) |
| `--delivery-preferences-publicity` | enum | Allowed handling preferences for publicity deliveries (virtual office) |
| `--delivery-preferences-other` | enum | Allowed handling preferences for other deliveries (virtual office) |
| `--maximum-delivery-storage-days` | int | Maximum number of days deliveries are stored before being returned (virtual office) |
| `--from-maximum-delivery-storage-days` | range | |
| `--to-maximum-delivery-storage-days` | range | |
| `--maximum-company-aliases` | int | Maximum number of company name aliases allowed for mail handling (virtual office) |
| `--from-maximum-company-aliases` | range | |
| `--to-maximum-company-aliases` | range | |
| `--maximum-recipients` | int | Maximum number of mail recipients allowed (virtual office) |
| `--from-maximum-recipients` | range | |
| `--to-maximum-recipients` | range | |
| `--maximum-addresses` | int | Maximum number of forwarding addresses allowed (virtual office) |
| `--from-maximum-addresses` | range | |
| `--to-maximum-addresses` | range | |
| `--transfer-products-to-contract` | bool | Whether to automatically transfer mail handling products to the member's contract |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Tariff sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### Tariff create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Plan name |
| `--system-tariff-type` | enum, required | Category of the plan: FullTimePrivateOffice, PartTimePrivateOffice, FullTimeDedicatedDesk, PartTimeDedicatedDesk, FullTimeHotDesk, PartTimeHotDesk, FullTimeOther, PartTimeOther, Storage, VirtualOffice, Virtual, or Other |
| `--price` | decimal, required | Recurring price charged per billing cycle |
| `--default-invoicing-day` | int | Day of the month on which invoices are generated for members on this plan |
| `--visible` | bool | Whether the plan is visible to customers on the members portal and mobile app |
| `--available-to-ai` | bool | Whether this plan is available to any AI channels (Email, Chat or WhatsApp) for recommendations for private offices; |
| `--notes-for-ai` | string | Custom notes provided to the AI assistant when describing this plan |
| `--show-price-for-ai` | bool | Whether to show the plan price to the AI assistant |
| `--price-for-ai` | decimal | Custom price shown to the AI assistant instead of the actual price |
| `--use-time-passes` | bool | Whether this plan uses time passes for check-in access |
| `--description` | string | Plan description shown to customers |
| `--invoice-line-display-as` | string | Custom text shown on the invoice line instead of the plan name |
| `--sign-up-fee` | decimal | One-off fee charged when a customer first signs up to this plan |
| `--currency-id` | long, required | ID of the currency linked to this record |
| `--tax-rate-id` | long | Standard tax rate applied to charges on this plan |
| `--reduced-tax-rate-id` | long | Reduced tax rate applied when applicable |
| `--exempt-tax-rate-id` | long | Tax-exempt rate applied when applicable |
| `--financial-account-id` | long | Financial account used for revenue tracking |
| `--terms-and-conditions` | string | Terms and conditions text that members must accept when signing up |
| `--new-contract-document-url` | string | URL to upload a new contract document template |
| `--clear-contract-document-file` | bool | Set to true to remove the uploaded contract document file |
| `--cancellation-period` | int, required | Number of days' notice required before a contract can be cancelled |
| `--display-order` | int, required | Display order on the members portal (lower numbers appear first) |
| `--group-name` | string | Group name used to visually group plans together on the members portal |
| `--disable-portal-cancellations` | bool | Prevents members from cancelling this plan through the members portal |
| `--subscribers-limit` | int | Maximum number of members that can be signed up to this plan at any time |
| `--cancellation-limit-days` | int | Minimum number of days a contract must be active before it can be cancelled |
| `--default-contract-term` | int | Default minimum contract term in months for new sign-ups |
| `--cancel-member-account-after` | int | Number of days after contract cancellation before the member account is deactivated |
| `--checkin-price-plan-limit` | int | Maximum number of check-ins included per billing cycle |
| `--checkin-month-limit` | int | Maximum number of check-ins allowed per month |
| `--checkin-week-limit` | int | Maximum number of check-ins allowed per week |
| `--visitor-month-limit` | int | Maximum number of visitor passes allowed per month |
| `--visitor-week-limit` | int | Maximum number of visitor passes allowed per week |
| `--visitor-day-limit` | int | Maximum number of visitor passes allowed per day |
| `--hours-price-plan-limit` | int | Maximum number of hours included per billing cycle |
| `--hours-month-limit` | int | Maximum number of hours allowed per month |
| `--hours-week-limit` | int | Maximum number of hours allowed per week |
| `--booking-minute-week-limit` | int | Maximum booking minutes allowed per week |
| `--booking-minute-month-limit` | int | Maximum booking minutes allowed per month |
| `--discount-extra-services` | decimal | Discount percentage for extra services |
| `--discount-time-passes` | decimal | Discount percentage for time passes |
| `--discount-charges` | decimal | Discount percentage for charges |
| `--invoice-every` | int, required | Billing cycle length in months. Set to 0 if billing by weeks instead |
| `--invoice-every-weeks` | int, required | Billing cycle length in weeks. Set to 0 if billing by months instead |
| `--auto-cancel-after` | int | Number of days after which the contract is automatically cancelled if not paid |
| `--advance-invoice-cycles` | int | Number of billing cycles to invoice in advance |
| `--prorate-day-of-month` | int | Day of the month used to align billing cycles when prorating |
| `--prorate-days-before` | int | Number of days before the prorate day to start prorating |
| `--prorate-cancellations` | bool | Whether to prorate the final invoice when a contract is cancelled mid-cycle |
| `--charge-and-extend` | int | Number of days to extend a contract after payment is received |
| `--exclude-from-invoice` | bool | Whether to exclude this plan's charges from member invoices |
| `--auto-raise-invoices` | bool | Whether to automatically generate invoices at the end of each billing cycle |
| `--raise-invoice-every` | int | Raise invoice every N months |
| `--raise-invoice-every-weeks` | int | Raise invoice every N weeks |
| `--minimum-price` | decimal | Minimum total amount charged per billing cycle regardless of usage |
| `--minimum-price-include-time-passes` | bool | Whether time pass charges count towards the minimum price |
| `--minimum-price-include-extra-services` | bool | Whether extra service charges count towards the minimum price |
| `--minimum-price-include-events` | bool | Whether event charges count towards the minimum price |
| `--archived` | bool | Whether the plan is archived and no longer available for new sign-ups |
| `--starred` | bool | Whether the plan is starred (highlighted) on the members portal |
| `--keep-new-accounts-on-hold` | bool | Whether new sign-ups are kept on hold until manually approved |
| `--can-be-paused` | bool | Whether members can pause their contract on this plan |
| `--pause-yearly-limit` | int | Maximum number of times a contract can be paused per year |
| `--pause-cycles-limit` | int | Maximum number of billing cycles a contract can be paused for |
| `--booking-due-date-strategy` | enum, required | Strategy for determining when booking charges are due: RenewalDate, BookingEndDate, BookingCreationDate, or NextNthOfMonth |
| `--booking-due-date-day-of-month` | int | Day of the month used when BookingDueDateStrategy is NextNthOfMonth |
| `--is-virtual-office` | bool | Whether this is a virtual office plan with mail handling features |
| `--wait-for-identity-checks-to-activate` | bool | Whether to keep the contract on hold until all required identity checks are completed |
| `--request-address-identity-check` | bool | Whether to request an address identity check from members signing up to this plan |
| `--address-identity-check-description` | string | Instructions shown to members when completing the address identity check |
| `--address-identity-check-provider` | enum, required | Provider used for address identity checks: Manual or StripeIdentity |
| `--keep-paused-if-address-mismatch` | bool | Whether to keep the contract paused if the address identity check reveals a mismatch |
| `--address-identity-check-repeat-pattern` | enum, required | How often to repeat the address identity check: Never, Every3Months, Every6Months, Every12Months, or Every24Months |
| `--request-identity-check` | bool | Whether to request an identity (ID document) check from members signing up to this plan |
| `--identity-check-provider` | enum, required | Provider used for identity checks: Manual or StripeIdentity |
| `--identity-check-repeat-pattern` | enum, required | How often to repeat the identity check: Never, Every3Months, Every6Months, Every12Months, or Every24Months |
| `--identity-check-description` | string | Instructions shown to members when completing the identity check |
| `--request-aml-check` | bool | Whether to request an AML check from members signing up to this plan |
| `--aml-check-open-sanctions-enabled` | bool | Whether to enable AML checks against the OpenSanctions dataset |
| `--aml-check-pappers-enabled` | bool | Whether to enable AML checks against the Pappers dataset |
| `--aml-check-open-sanctions-dataset` | string | Which OpenSanctions dataset to check against for AML screening (e.g. 'default') |
| `--aml-check-score-threshold` | decimal | Score threshold for AML checks, between 0 and 1. Matches with a score above this threshold will be considered a positive match. Default is 0.7 |
| `--send-onboarding-form-by-email` | bool | Whether to email the onboarding form to new members signing up to this plan |
| `--form-page-id` | long | ID of the onboarding form page sent to new members |
| `--products-store` | list, repeat flag | Product IDs for mail stored for collection (virtual office) |
| `--added-products-store` | list, repeat flag | The added products store value for this tariff |
| `--removed-products-store` | list, repeat flag | The removed products store value for this tariff |
| `--products-forward` | list, repeat flag | Product IDs for mail forwarding (virtual office) |
| `--added-products-forward` | list, repeat flag | The added products forward value for this tariff |
| `--removed-products-forward` | list, repeat flag | The removed products forward value for this tariff |
| `--products-recycle` | list, repeat flag | Product IDs for mail recycling (virtual office) |
| `--added-products-recycle` | list, repeat flag | The added products recycle value for this tariff |
| `--removed-products-recycle` | list, repeat flag | The removed products recycle value for this tariff |
| `--products-shred` | list, repeat flag | Product IDs for mail shredding (virtual office) |
| `--added-products-shred` | list, repeat flag | The added products shred value for this tariff |
| `--removed-products-shred` | list, repeat flag | The removed products shred value for this tariff |
| `--products-scan` | list, repeat flag | Product IDs for mail scanning (virtual office) |
| `--added-products-scan` | list, repeat flag | The added products scan value for this tariff |
| `--removed-products-scan` | list, repeat flag | The removed products scan value for this tariff |
| `--products-return` | list, repeat flag | Product IDs for returning mail to sender (virtual office) |
| `--added-products-return` | list, repeat flag | The added products return value for this tariff |
| `--removed-products-return` | list, repeat flag | The removed products return value for this tariff |
| `--products-deposit` | list, repeat flag | Product IDs for check deposits (virtual office) |
| `--added-products-deposit` | list, repeat flag | The added products deposit value for this tariff |
| `--removed-products-deposit` | list, repeat flag | The removed products deposit value for this tariff |
| `--products-collect` | list, repeat flag | Product IDs for mail collection (virtual office) |
| `--added-products-collect` | list, repeat flag | The added products collect value for this tariff |
| `--removed-products-collect` | list, repeat flag | The removed products collect value for this tariff |
| `--delivery-preferences-mail` | enum, required | Allowed handling preferences for mail deliveries (virtual office) |
| `--delivery-preferences-parcels` | enum, required | Allowed handling preferences for parcel deliveries (virtual office) |
| `--delivery-preferences-checks` | enum, required | Allowed handling preferences for check deliveries (virtual office) |
| `--delivery-preferences-publicity` | enum, required | Allowed handling preferences for publicity deliveries (virtual office) |
| `--delivery-preferences-other` | enum, required | Allowed handling preferences for other deliveries (virtual office) |
| `--maximum-delivery-storage-days` | int | Maximum number of days deliveries are stored before being returned (virtual office) |
| `--maximum-company-aliases` | int | Maximum number of company name aliases allowed for mail handling (virtual office) |
| `--maximum-recipients` | int | Maximum number of mail recipients allowed (virtual office) |
| `--maximum-addresses` | int | Maximum number of forwarding addresses allowed (virtual office) |
| `--transfer-products-to-contract` | bool | Whether to automatically transfer mail handling products to the member's contract |

#### Tariff update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Plan name |
| `--system-tariff-type` | enum | Category of the plan: FullTimePrivateOffice, PartTimePrivateOffice, FullTimeDedicatedDesk, PartTimeDedicatedDesk, FullTimeHotDesk, PartTimeHotDesk, FullTimeOther, PartTimeOther, Storage, VirtualOffice, Virtual, or Other |
| `--price` | decimal | Recurring price charged per billing cycle |
| `--default-invoicing-day` | int | Day of the month on which invoices are generated for members on this plan |
| `--visible` | bool | Whether the plan is visible to customers on the members portal and mobile app |
| `--available-to-ai` | bool | Whether this plan is available to any AI channels (Email, Chat or WhatsApp) for recommendations for private offices; |
| `--notes-for-ai` | string | Custom notes provided to the AI assistant when describing this plan |
| `--show-price-for-ai` | bool | Whether to show the plan price to the AI assistant |
| `--price-for-ai` | decimal | Custom price shown to the AI assistant instead of the actual price |
| `--use-time-passes` | bool | Whether this plan uses time passes for check-in access |
| `--description` | string | Plan description shown to customers |
| `--invoice-line-display-as` | string | Custom text shown on the invoice line instead of the plan name |
| `--sign-up-fee` | decimal | One-off fee charged when a customer first signs up to this plan |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | Standard tax rate applied to charges on this plan |
| `--reduced-tax-rate-id` | long | Reduced tax rate applied when applicable |
| `--exempt-tax-rate-id` | long | Tax-exempt rate applied when applicable |
| `--financial-account-id` | long | Financial account used for revenue tracking |
| `--terms-and-conditions` | string | Terms and conditions text that members must accept when signing up |
| `--new-contract-document-url` | string | URL to upload a new contract document template |
| `--clear-contract-document-file` | bool | Set to true to remove the uploaded contract document file |
| `--cancellation-period` | int | Number of days' notice required before a contract can be cancelled |
| `--display-order` | int | Display order on the members portal (lower numbers appear first) |
| `--group-name` | string | Group name used to visually group plans together on the members portal |
| `--disable-portal-cancellations` | bool | Prevents members from cancelling this plan through the members portal |
| `--subscribers-limit` | int | Maximum number of members that can be signed up to this plan at any time |
| `--cancellation-limit-days` | int | Minimum number of days a contract must be active before it can be cancelled |
| `--default-contract-term` | int | Default minimum contract term in months for new sign-ups |
| `--cancel-member-account-after` | int | Number of days after contract cancellation before the member account is deactivated |
| `--checkin-price-plan-limit` | int | Maximum number of check-ins included per billing cycle |
| `--checkin-month-limit` | int | Maximum number of check-ins allowed per month |
| `--checkin-week-limit` | int | Maximum number of check-ins allowed per week |
| `--visitor-month-limit` | int | Maximum number of visitor passes allowed per month |
| `--visitor-week-limit` | int | Maximum number of visitor passes allowed per week |
| `--visitor-day-limit` | int | Maximum number of visitor passes allowed per day |
| `--hours-price-plan-limit` | int | Maximum number of hours included per billing cycle |
| `--hours-month-limit` | int | Maximum number of hours allowed per month |
| `--hours-week-limit` | int | Maximum number of hours allowed per week |
| `--booking-minute-week-limit` | int | Maximum booking minutes allowed per week |
| `--booking-minute-month-limit` | int | Maximum booking minutes allowed per month |
| `--discount-extra-services` | decimal | Discount percentage for extra services |
| `--discount-time-passes` | decimal | Discount percentage for time passes |
| `--discount-charges` | decimal | Discount percentage for charges |
| `--invoice-every` | int | Billing cycle length in months. Set to 0 if billing by weeks instead |
| `--invoice-every-weeks` | int | Billing cycle length in weeks. Set to 0 if billing by months instead |
| `--auto-cancel-after` | int | Number of days after which the contract is automatically cancelled if not paid |
| `--advance-invoice-cycles` | int | Number of billing cycles to invoice in advance |
| `--prorate-day-of-month` | int | Day of the month used to align billing cycles when prorating |
| `--prorate-days-before` | int | Number of days before the prorate day to start prorating |
| `--prorate-cancellations` | bool | Whether to prorate the final invoice when a contract is cancelled mid-cycle |
| `--charge-and-extend` | int | Number of days to extend a contract after payment is received |
| `--exclude-from-invoice` | bool | Whether to exclude this plan's charges from member invoices |
| `--auto-raise-invoices` | bool | Whether to automatically generate invoices at the end of each billing cycle |
| `--raise-invoice-every` | int | Raise invoice every N months |
| `--raise-invoice-every-weeks` | int | Raise invoice every N weeks |
| `--minimum-price` | decimal | Minimum total amount charged per billing cycle regardless of usage |
| `--minimum-price-include-time-passes` | bool | Whether time pass charges count towards the minimum price |
| `--minimum-price-include-extra-services` | bool | Whether extra service charges count towards the minimum price |
| `--minimum-price-include-events` | bool | Whether event charges count towards the minimum price |
| `--archived` | bool | Whether the plan is archived and no longer available for new sign-ups |
| `--starred` | bool | Whether the plan is starred (highlighted) on the members portal |
| `--keep-new-accounts-on-hold` | bool | Whether new sign-ups are kept on hold until manually approved |
| `--can-be-paused` | bool | Whether members can pause their contract on this plan |
| `--pause-yearly-limit` | int | Maximum number of times a contract can be paused per year |
| `--pause-cycles-limit` | int | Maximum number of billing cycles a contract can be paused for |
| `--booking-due-date-strategy` | enum | Strategy for determining when booking charges are due: RenewalDate, BookingEndDate, BookingCreationDate, or NextNthOfMonth |
| `--booking-due-date-day-of-month` | int | Day of the month used when BookingDueDateStrategy is NextNthOfMonth |
| `--is-virtual-office` | bool | Whether this is a virtual office plan with mail handling features |
| `--wait-for-identity-checks-to-activate` | bool | Whether to keep the contract on hold until all required identity checks are completed |
| `--request-address-identity-check` | bool | Whether to request an address identity check from members signing up to this plan |
| `--address-identity-check-description` | string | Instructions shown to members when completing the address identity check |
| `--address-identity-check-provider` | enum | Provider used for address identity checks: Manual or StripeIdentity |
| `--keep-paused-if-address-mismatch` | bool | Whether to keep the contract paused if the address identity check reveals a mismatch |
| `--address-identity-check-repeat-pattern` | enum | How often to repeat the address identity check: Never, Every3Months, Every6Months, Every12Months, or Every24Months |
| `--request-identity-check` | bool | Whether to request an identity (ID document) check from members signing up to this plan |
| `--identity-check-provider` | enum | Provider used for identity checks: Manual or StripeIdentity |
| `--identity-check-repeat-pattern` | enum | How often to repeat the identity check: Never, Every3Months, Every6Months, Every12Months, or Every24Months |
| `--identity-check-description` | string | Instructions shown to members when completing the identity check |
| `--request-aml-check` | bool | Whether to request an AML check from members signing up to this plan |
| `--aml-check-open-sanctions-enabled` | bool | Whether to enable AML checks against the OpenSanctions dataset |
| `--aml-check-pappers-enabled` | bool | Whether to enable AML checks against the Pappers dataset |
| `--aml-check-open-sanctions-dataset` | string | Which OpenSanctions dataset to check against for AML screening (e.g. 'default') |
| `--aml-check-score-threshold` | decimal | Score threshold for AML checks, between 0 and 1. Matches with a score above this threshold will be considered a positive match. Default is 0.7 |
| `--send-onboarding-form-by-email` | bool | Whether to email the onboarding form to new members signing up to this plan |
| `--form-page-id` | long | ID of the onboarding form page sent to new members |
| `--products-store` | list, repeat flag | Product IDs for mail stored for collection (virtual office) |
| `--added-products-store` | list, repeat flag | The added products store value for this tariff |
| `--removed-products-store` | list, repeat flag | The removed products store value for this tariff |
| `--products-forward` | list, repeat flag | Product IDs for mail forwarding (virtual office) |
| `--added-products-forward` | list, repeat flag | The added products forward value for this tariff |
| `--removed-products-forward` | list, repeat flag | The removed products forward value for this tariff |
| `--products-recycle` | list, repeat flag | Product IDs for mail recycling (virtual office) |
| `--added-products-recycle` | list, repeat flag | The added products recycle value for this tariff |
| `--removed-products-recycle` | list, repeat flag | The removed products recycle value for this tariff |
| `--products-shred` | list, repeat flag | Product IDs for mail shredding (virtual office) |
| `--added-products-shred` | list, repeat flag | The added products shred value for this tariff |
| `--removed-products-shred` | list, repeat flag | The removed products shred value for this tariff |
| `--products-scan` | list, repeat flag | Product IDs for mail scanning (virtual office) |
| `--added-products-scan` | list, repeat flag | The added products scan value for this tariff |
| `--removed-products-scan` | list, repeat flag | The removed products scan value for this tariff |
| `--products-return` | list, repeat flag | Product IDs for returning mail to sender (virtual office) |
| `--added-products-return` | list, repeat flag | The added products return value for this tariff |
| `--removed-products-return` | list, repeat flag | The removed products return value for this tariff |
| `--products-deposit` | list, repeat flag | Product IDs for check deposits (virtual office) |
| `--added-products-deposit` | list, repeat flag | The added products deposit value for this tariff |
| `--removed-products-deposit` | list, repeat flag | The removed products deposit value for this tariff |
| `--products-collect` | list, repeat flag | Product IDs for mail collection (virtual office) |
| `--added-products-collect` | list, repeat flag | The added products collect value for this tariff |
| `--removed-products-collect` | list, repeat flag | The removed products collect value for this tariff |
| `--delivery-preferences-mail` | enum | Allowed handling preferences for mail deliveries (virtual office) |
| `--delivery-preferences-parcels` | enum | Allowed handling preferences for parcel deliveries (virtual office) |
| `--delivery-preferences-checks` | enum | Allowed handling preferences for check deliveries (virtual office) |
| `--delivery-preferences-publicity` | enum | Allowed handling preferences for publicity deliveries (virtual office) |
| `--delivery-preferences-other` | enum | Allowed handling preferences for other deliveries (virtual office) |
| `--maximum-delivery-storage-days` | int | Maximum number of days deliveries are stored before being returned (virtual office) |
| `--maximum-company-aliases` | int | Maximum number of company name aliases allowed for mail handling (virtual office) |
| `--maximum-recipients` | int | Maximum number of mail recipients allowed (virtual office) |
| `--maximum-addresses` | int | Maximum number of forwarding addresses allowed (virtual office) |
| `--transfer-products-to-contract` | bool | Whether to automatically transfer mail handling products to the member's contract |

#### Tariff PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--send-onboarding-form-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus tariffs update <id> --send-onboarding-form-by-email "«PII:EMAIL:a3f2b1c9»" --agent`

### Tariff (key fields)

`Id`, `Name`, `SystemTariffType`, `Price`, `Visible`, `Archived`

**List properties (only returned by `get`, not by `list`):** `ProductsStore`, `AddedProductsStore`, `RemovedProductsStore`, `ProductsForward`, `AddedProductsForward`, `RemovedProductsForward`, `ProductsRecycle`, `AddedProductsRecycle`, `RemovedProductsRecycle`, `ProductsShred`, `AddedProductsShred`, `RemovedProductsShred`, `ProductsScan`, `AddedProductsScan`, `RemovedProductsScan`, `ProductsReturn`, `AddedProductsReturn`, `RemovedProductsReturn`, `ProductsDeposit`, `AddedProductsDeposit`, `RemovedProductsDeposit`, `ProductsCollect`, `AddedProductsCollect`, `RemovedProductsCollect`

#### Tariff enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-tariff-type` | `1` FullTimePrivateOffice, `2` PartTimePrivateOffice, `3` FullTimeDedicatedDesk, `4` PartTimeDedicatedDesk, `5` FullTimeHotDesk, `6` PartTimeHotDesk, `7` FullTimeOther, `8` PartTimeOther, `9` Storage, `10` VirtualOffice, `11` Virtual, `99` Other |
| `--booking-due-date-strategy` | `1` RenewalDate, `2` BookingEndDate, `3` BookingCreationDate, `4` NextNthOfMonth |
| `--address-identity-check-provider` | `1` Manual, `2` StripeIdentity |
| `--address-identity-check-repeat-pattern` | `1` Never, `2` Every3Months, `3` Every6Months, `4` Every12Months, `5` Every24Months |
| `--identity-check-provider` | `1` Manual, `2` StripeIdentity |
| `--identity-check-repeat-pattern` | `1` Never, `2` Every3Months, `3` Every6Months, `4` Every12Months, `5` Every24Months |

<!-- END:GENERATED entity=Tariffs -->
