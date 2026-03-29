# Coworkers

<!-- BEGIN:GENERATED entity=Coworkers -->

Coworkers support Search, Get, Create, Update, Delete.
Coworkers also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkers list --agent` | List all coworkers |
| `nexudus coworkers list --query "search" --agent` | Search coworkers by name |
| `nexudus coworkers list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkers get <id> --agent` | Get single coworker |
| `nexudus coworkers create --full-name <value> --email <value> --agent` | Create coworker |
| `nexudus coworkers update <id> --name "New Name" --agent` | Update coworker |
| `nexudus coworkers delete <id> --yes --agent` | Delete coworker (no prompt) |
| `nexudus coworkers commands --agent` | List available entity commands |
| `nexudus coworkers run-command <key> <ids> --agent` | Run entity command |

#### Coworker create options

`--coworker-type`, `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--full-name` (required), `--salutation`, `--gender`, `--email` (required), `--create-user`, `--address`, `--post-code`, `--city`, `--state`, `--country-id`, `--timezone-id`, `--mobile-phone`, `--land-line`, `--date-of-birth`, `--nick-name`, `--business-area`, `--position`, `--company-name`, `--profile-website`, `--profile-tags`, `--profile-summary`, `--twitter`, `--facebook`, `--telegram`, `--linkedin`, `--skype`, `--github`, `--instagram`, `--profile-is-public`, `--invoicing-business-id`, `--billing-email`, `--billing-name`, `--billing-address`, `--billing-post-code`, `--billing-city`, `--billing-state`, `--billing-country-id`, `--billing-timezone-id`, `--tax-rate-type`, `--tax-rate`, `--tax-id-number`, `--bank-name`, `--bank-account`, `--bank-branch`, `--notify-on-new-invoice`, `--notify-on-new-payment`, `--notify-on-failed-payment`, `--show-paying-member-invoices`, `--enable-gocardless`, `--gocardless-contract-number`, `--regular-payment-provider`, `--regular-payment-contract-number`, `--card-number`, `--do-not-auto-process-invoices`, `--allow-network-checkin`, `--access-card-id`, `--access-pincode`, `--key-fob-number`, `--notify-on-delivery`, `--can-make-bookings`, `--can-book-for-team`, `--can-purchase-products`, `--can-purchase-events`, `--can-access-community`, `--reference-number`, `--tag`, `--notes`, `--show-alert`, `--alert-note`, `--active`, `--invoice-due-date-period`, `--registration-date`, `--general-terms-accepted`, `--custom1`, `--custom2`, `--custom3`, `--custom4`, `--custom5`, `--custom6`, `--custom7`, `--custom8`, `--custom9`, `--custom10`, `--custom11`, `--custom12`, `--custom13`, `--custom14`, `--custom15`, `--custom16`, `--custom17`, `--custom18`, `--custom19`, `--custom20`, `--custom21`, `--custom22`, `--custom23`, `--custom24`, `--custom25`, `--custom26`, `--custom27`, `--custom28`, `--custom29`, `--custom30`, `--purchase-order`, `--notify-on-deliveries-email`, `--billing-day`, `--tariff-id`, `--tariff-invoice-every`, `--tariff-invoice-every-weeks`, `--renewal-date`, `--monday-attendance`, `--tuesday-attendance`, `--wednesday-attendance`, `--thursday-attendance`, `--friday-attendance`, `--saturday-attendance`, `--sunday-attendance`, `--longitude`, `--latitude`, `--billing-longitude`, `--billing-latitude`, `--archived`, `--avatar-url`, `--clear-avatar`, `--banner-url`, `--clear-banner`

#### Coworker update options

`--coworker-type`, `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--full-name`, `--salutation`, `--gender`, `--email`, `--create-user`, `--address`, `--post-code`, `--city`, `--state`, `--country-id`, `--timezone-id`, `--mobile-phone`, `--land-line`, `--date-of-birth`, `--nick-name`, `--business-area`, `--position`, `--company-name`, `--profile-website`, `--profile-tags`, `--profile-summary`, `--twitter`, `--facebook`, `--telegram`, `--linkedin`, `--skype`, `--github`, `--instagram`, `--profile-is-public`, `--invoicing-business-id`, `--billing-email`, `--billing-name`, `--billing-address`, `--billing-post-code`, `--billing-city`, `--billing-state`, `--billing-country-id`, `--billing-timezone-id`, `--tax-rate-type`, `--tax-rate`, `--tax-id-number`, `--bank-name`, `--bank-account`, `--bank-branch`, `--notify-on-new-invoice`, `--notify-on-new-payment`, `--notify-on-failed-payment`, `--show-paying-member-invoices`, `--enable-gocardless`, `--gocardless-contract-number`, `--regular-payment-provider`, `--regular-payment-contract-number`, `--card-number`, `--do-not-auto-process-invoices`, `--allow-network-checkin`, `--access-card-id`, `--access-pincode`, `--key-fob-number`, `--notify-on-delivery`, `--can-make-bookings`, `--can-book-for-team`, `--can-purchase-products`, `--can-purchase-events`, `--can-access-community`, `--reference-number`, `--tag`, `--notes`, `--show-alert`, `--alert-note`, `--active`, `--invoice-due-date-period`, `--registration-date`, `--general-terms-accepted`, `--custom1`, `--custom2`, `--custom3`, `--custom4`, `--custom5`, `--custom6`, `--custom7`, `--custom8`, `--custom9`, `--custom10`, `--custom11`, `--custom12`, `--custom13`, `--custom14`, `--custom15`, `--custom16`, `--custom17`, `--custom18`, `--custom19`, `--custom20`, `--custom21`, `--custom22`, `--custom23`, `--custom24`, `--custom25`, `--custom26`, `--custom27`, `--custom28`, `--custom29`, `--custom30`, `--purchase-order`, `--notify-on-deliveries-email`, `--billing-day`, `--tariff-id`, `--tariff-invoice-every`, `--tariff-invoice-every-weeks`, `--renewal-date`, `--monday-attendance`, `--tuesday-attendance`, `--wednesday-attendance`, `--thursday-attendance`, `--friday-attendance`, `--saturday-attendance`, `--sunday-attendance`, `--longitude`, `--latitude`, `--billing-longitude`, `--billing-latitude`, `--archived`, `--avatar-url`, `--clear-avatar`, `--banner-url`, `--clear-banner`

### Coworker (key fields)

`Id`, `CoworkerType`, `FullName`, `Email`, `CompanyName`, `Active`, `RegistrationDate`, `TeamNames`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Teams`, `AddedTeams`, `RemovedTeams`

#### Coworker enum values

| Option | Valid values |
| ------ | ------------ |
| `--coworker-type` | `1` Individual, `2` Company |
| `--gender` | `1` NotSet, `2` Male, `3` Female, `4` Other, `5` RatherNotSay |
| `--tax-rate-type` | `1` Default, `2` Reduced, `3` Exempt |
| `--regular-payment-provider` | `0` None, `1` MultiGateway, `2` Stripe, `3` Forte, `4` AuthorizeNetSubscription, `5` PaypalStandardSubscription, `6` PayPalAdaptive, `7` EPay, `8` Braintree, `9` EziDebit, `10` LiqPay, `11` StripeACH, `12` GoCardless, `13` StripeBACS, `94` CreditNote, `95` GiftCard, `96` BankTransfer, `97` Cash, `98` Check, `99` Other |
| `--monday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--tuesday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--wednesday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--thursday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--friday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--saturday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--sunday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |

<!-- END:GENERATED entity=Coworkers -->
