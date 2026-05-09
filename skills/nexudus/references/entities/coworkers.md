# Coworkers

<!-- BEGIN:GENERATED entity=Coworkers -->

A **Coworker** represents a customer in Nexudus. Coworkers can be individuals or companies and hold all personal, billing, access-control, and plan information for a customer.

When creating a coworker, set `--create-user` to grant portal and app access — this also sends a welcome email with access details.

To assign a plan at creation time, pass `--tariff-id` with the plan ID. Combine with `--billing-day` to fix the billing day (defaults to the current day or the plan's default billing day) and `--renewal-date` to set the date when the plan starts and will first be invoiced.

Coworkers support Search, Get, Create, Update (no Delete via API).
Coworkers also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkers list --agent` | List all coworkers |
| `nexudus coworkers list --id <id> --agent` | Filter by single ID |
| `nexudus coworkers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkers list --coworker-type <value> --full-name <value> --agent` | Filter coworkers by properties |
| `nexudus coworkers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkers get <id> --agent` | Get single coworker |
| `nexudus coworkers create --coworker-type <value> --full-name <value> --gender <value> --email <value> --country-id <value> --simple-time-zone-id <value> --tax-rate-type <value> --monday-attendance <value> --tuesday-attendance <value> --wednesday-attendance <value> --thursday-attendance <value> --friday-attendance <value> --saturday-attendance <value> --sunday-attendance <value> --agent` | Create coworker |
| `nexudus coworkers update <id> --name "New Name" --agent` | Update coworker |
| `nexudus coworkers commands --agent` | List available entity commands |
| `nexudus coworkers run-command <key> <ids> --agent` | Run entity command |

#### Coworker list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-type` | enum | Coworker type |
| `--full-name` | string | Full name |
| `--salutation` | string | Salutation |
| `--gender` | enum | Gender |
| `--email` | string | Email address |
| `--create-user` | bool | Create user account. Grants portal and app access and sends a welcome email with the access details |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--new-banner-image-url` | string |  |
| `--clear-banner-image-file` | bool |  |
| `--address` | string | Address |
| `--post-code` | string | Post code |
| `--city` | string | City name |
| `--state` | string | State |
| `--country-id` | long |  |
| `--simple-time-zone-id` | long |  |
| `--mobile-phone` | string | Mobile phone |
| `--land-line` | string | Land line |
| `--date-of-birth` | DateTime | Date of birth |
| `--from-date-of-birth` | range | |
| `--to-date-of-birth` | range | |
| `--nick-name` | string | Nickname |
| `--business-area` | string | Business area |
| `--position` | string | Position |
| `--company-name` | string | Company name |
| `--profile-website` | string | Profile website |
| `--profile-tags` | string | Profile tags |
| `--profile-summary` | string | Profile summary |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook profile |
| `--google` | string |  |
| `--telegram` | string | Telegram handle |
| `--linkedin` | string | LinkedIn profile |
| `--skype` | string | Skype handle |
| `--github` | string | GitHub profile |
| `--pinterest` | string |  |
| `--flickr` | string |  |
| `--instagram` | string | Instagram profile |
| `--vimeo` | string |  |
| `--tumblr` | string |  |
| `--blogger` | string |  |
| `--profile-is-public` | bool | Profile is public |
| `--invoicing-business-id` | long |  |
| `--billing-email` | string | Billing email |
| `--billing-name` | string | Billing name |
| `--billing-address` | string | Billing address |
| `--billing-post-code` | string | Billing post code |
| `--billing-city` | string | Billing city |
| `--billing-state` | string | Billing state |
| `--billing-country-id` | long |  |
| `--billing-simple-time-zone-id` | long |  |
| `--tax-rate-type` | enum | Tax rate type |
| `--tax-rate` | decimal | Tax rate |
| `--from-tax-rate` | range | |
| `--to-tax-rate` | range | |
| `--tax-id-number` | string | Tax ID number |
| `--bank-name` | string | Bank name |
| `--bank-account` | string | Bank account |
| `--bank-branch` | string | Bank branch |
| `--notify-on-new-invoice` | bool | Notify on new invoice |
| `--notify-on-new-payment` | bool | Notify on new payment |
| `--notify-on-failed-payment` | bool | Notify on failed payment |
| `--show-paying-member-invoices` | bool | Show paying member invoices |
| `--enable-gocardless` | bool | Enable GoCardless payments |
| `--use-go-cardless-pro-payments` | bool |  |
| `--gocardless-contract-number` | string | GoCardless contract number |
| `--stripe-bacs-d-d-payment-method-id` | string |  |
| `--stripe-bacs-d-d-mandate-id` | string |  |
| `--stripe-bacs-d-d-customer-token` | string |  |
| `--stripe-bacs-d-d-enabled` | bool |  |
| `--last-over-due-invoice-reminder` | DateTime |  |
| `--from-last-over-due-invoice-reminder` | range | |
| `--to-last-over-due-invoice-reminder` | range | |
| `--last-low-credit-reminder` | DateTime |  |
| `--from-last-low-credit-reminder` | range | |
| `--to-last-low-credit-reminder` | range | |
| `--referer-guid` | string |  |
| `--regular-payment-provider` | enum | Regular payment provider |
| `--regular-payment-contract-number` | string | Regular payment contract number |
| `--do-not-auto-process-invoices` | bool | Do not process invoices automatically |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--access-card-id` | string | Access card ID |
| `--access-pincode` | string | Access PIN code |
| `--key-fob-number` | string | Key fob number |
| `--notify-on-delivery` | bool | Notify on delivery |
| `--ezeep-user-id` | string |  |
| `--ezeep-free-printing` | bool |  |
| `--ezeep-blue-user-id` | string |  |
| `--ezeep-blue-free-printing` | bool |  |
| `--ezeep-blue-printing-enabled` | bool |  |
| `--paper-cut-pay-as-you-print` | bool |  |
| `--paper-cut-free-printing` | bool |  |
| `--paper-cut-user-id` | string |  |
| `--can-make-bookings` | bool | Can make bookings |
| `--can-book-for-team` | bool | Can book for team |
| `--can-purchase-products` | bool | Can purchase products |
| `--can-purchase-events` | bool | Can purchase events |
| `--can-access-community` | bool | Can access community |
| `--reference-number` | string | Reference number |
| `--tag` | string | Tag |
| `--notes` | string | Notes |
| `--show-alert` | bool | Show alert |
| `--alert-note` | string | Alert note |
| `--user-id` | long |  |
| `--active` | bool | Active |
| `--next-auto-invoice` | DateTime | Next auto invoice date |
| `--from-next-auto-invoice` | range | |
| `--to-next-auto-invoice` | range | |
| `--invoice-due-date-period` | int | Invoice due date period |
| `--from-invoice-due-date-period` | range | |
| `--to-invoice-due-date-period` | range | |
| `--registration-date` | DateTime | Registration date |
| `--from-registration-date` | range | |
| `--to-registration-date` | range | |
| `--general-terms-accepted` | bool | General terms accepted |
| `--last-renewal` | DateTime |  |
| `--from-last-renewal` | range | |
| `--to-last-renewal` | range | |
| `--last-invoice-attempt` | DateTime |  |
| `--from-last-invoice-attempt` | range | |
| `--to-last-invoice-attempt` | range | |
| `--custom1` | string | Custom field 1 |
| `--custom2` | string | Custom field 2 |
| `--custom3` | string | Custom field 3 |
| `--custom4` | string | Custom field 4 |
| `--custom5` | string | Custom field 5 |
| `--custom6` | string | Custom field 6 |
| `--custom7` | string | Custom field 7 |
| `--custom8` | string | Custom field 8 |
| `--custom9` | string | Custom field 9 |
| `--custom10` | string | Custom field 10 |
| `--custom11` | string | Custom field 11 |
| `--custom12` | string | Custom field 12 |
| `--custom13` | string | Custom field 13 |
| `--custom14` | string | Custom field 14 |
| `--custom15` | string | Custom field 15 |
| `--custom16` | string | Custom field 16 |
| `--custom17` | string | Custom field 17 |
| `--custom18` | string | Custom field 18 |
| `--custom19` | string | Custom field 19 |
| `--custom20` | string | Custom field 20 |
| `--custom21` | string | Custom field 21 |
| `--custom22` | string | Custom field 22 |
| `--custom23` | string | Custom field 23 |
| `--custom24` | string | Custom field 24 |
| `--custom25` | string | Custom field 25 |
| `--custom26` | string | Custom field 26 |
| `--custom27` | string | Custom field 27 |
| `--custom28` | string | Custom field 28 |
| `--custom29` | string | Custom field 29 |
| `--custom30` | string | Custom field 30 |
| `--next-invoice-local` | DateTime |  |
| `--from-next-invoice-local` | range | |
| `--to-next-invoice-local` | range | |
| `--next-auto-invoice-local` | DateTime |  |
| `--from-next-auto-invoice-local` | range | |
| `--to-next-auto-invoice-local` | range | |
| `--registration-date-local` | DateTime |  |
| `--from-registration-date-local` | range | |
| `--to-registration-date-local` | range | |
| `--access-control-debounce-time` | DateTime |  |
| `--from-access-control-debounce-time` | range | |
| `--to-access-control-debounce-time` | range | |
| `--office365-access-token` | string |  |
| `--office365-refresh-token` | string |  |
| `--zoom-access-token` | string |  |
| `--zoom-refresh-token` | string |  |
| `--zoom-user-id` | string |  |
| `--doordeck-private-key` | string |  |
| `--doordeck-public-key` | string |  |
| `--doordeck-user-guid` | string |  |
| `--office365-subscription-id` | string |  |
| `--salto-v2-access-token` | string |  |
| `--stripe-a-c-h-bank-token` | string |  |
| `--stripe-a-c-h-customer-token` | string |  |
| `--has-accepted-stripe-a-c-h-agreement` | bool |  |
| `--has-verified-stripe-a-c-h-deposits` | bool |  |
| `--purchase-order` | string | Purchase order |
| `--sync-to-square` | bool |  |
| `--notify-on-deliveries-email` | string | Notify on deliveries email |
| `--access-control-error-notification-sent` | bool |  |
| `--sync-to-paper-cut-due` | bool |  |
| `--google-api-token` | string |  |
| `--google-subscription-id` | string |  |
| `--invoice-segregation-override` | bool |  |
| `--invoice-segregate-contracts` | bool |  |
| `--invoice-segregate-bookings` | bool |  |
| `--invoice-segregate-products` | bool |  |
| `--invoice-segregate-time-passes` | bool |  |
| `--invoice-segregate-tickets` | bool |  |
| `--is-default-profile` | bool |  |
| `--invoice-segregate-charges` | bool |  |
| `--brivo-user-id` | int |  |
| `--from-brivo-user-id` | range | |
| `--to-brivo-user-id` | range | |
| `--ezeep-printing-enabled` | bool |  |
| `--invoice-due-date-day` | int |  |
| `--from-invoice-due-date-day` | range | |
| `--to-invoice-due-date-day` | range | |
| `--monday-attendance` | enum | Monday attendance |
| `--tuesday-attendance` | enum | Tuesday attendance |
| `--wednesday-attendance` | enum | Wednesday attendance |
| `--thursday-attendance` | enum | Thursday attendance |
| `--friday-attendance` | enum | Friday attendance |
| `--saturday-attendance` | enum | Saturday attendance |
| `--sunday-attendance` | enum | Sunday attendance |
| `--longitude` | decimal | Longitude |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | Latitude |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--billing-longitude` | decimal | Billing longitude |
| `--from-billing-longitude` | range | |
| `--to-billing-longitude` | range | |
| `--billing-latitude` | decimal | Billing latitude |
| `--from-billing-latitude` | range | |
| `--to-billing-latitude` | range | |
| `--archived` | bool | Archived |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Coworker create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-type` | enum, required | Coworker type |
| `--businesses` | list, repeat flag |  |
| `--added-businesses` | list, repeat flag |  |
| `--removed-businesses` | list, repeat flag |  |
| `--teams` | list, repeat flag |  |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |
| `--full-name` | string, required | Full name |
| `--salutation` | string | Salutation |
| `--gender` | enum, required | Gender |
| `--email` | string, required | Email address |
| `--create-user` | bool | Create user account. Grants portal and app access and sends a welcome email with the access details |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--new-banner-image-url` | string |  |
| `--clear-banner-image-file` | bool |  |
| `--address` | string | Address |
| `--post-code` | string | Post code |
| `--city` | string | City name |
| `--state` | string | State |
| `--country-id` | long, required |  |
| `--simple-time-zone-id` | long, required |  |
| `--mobile-phone` | string | Mobile phone |
| `--land-line` | string | Land line |
| `--date-of-birth` | DateTime | Date of birth |
| `--nick-name` | string | Nickname |
| `--business-area` | string | Business area |
| `--position` | string | Position |
| `--company-name` | string | Company name |
| `--profile-website` | string | Profile website |
| `--profile-tags` | string | Profile tags |
| `--profile-summary` | string | Profile summary |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook profile |
| `--google` | string |  |
| `--telegram` | string | Telegram handle |
| `--linkedin` | string | LinkedIn profile |
| `--skype` | string | Skype handle |
| `--github` | string | GitHub profile |
| `--pinterest` | string |  |
| `--flickr` | string |  |
| `--instagram` | string | Instagram profile |
| `--vimeo` | string |  |
| `--tumblr` | string |  |
| `--blogger` | string |  |
| `--profile-is-public` | bool | Profile is public |
| `--invoicing-business-id` | long |  |
| `--billing-email` | string | Billing email |
| `--billing-name` | string | Billing name |
| `--billing-address` | string | Billing address |
| `--billing-post-code` | string | Billing post code |
| `--billing-city` | string | Billing city |
| `--billing-state` | string | Billing state |
| `--billing-country-id` | long |  |
| `--billing-simple-time-zone-id` | long |  |
| `--tax-rate-type` | enum, required | Tax rate type |
| `--tax-rate` | decimal | Tax rate |
| `--tax-id-number` | string | Tax ID number |
| `--bank-name` | string | Bank name |
| `--bank-account` | string | Bank account |
| `--bank-branch` | string | Bank branch |
| `--notify-on-new-invoice` | bool | Notify on new invoice |
| `--notify-on-new-payment` | bool | Notify on new payment |
| `--notify-on-failed-payment` | bool | Notify on failed payment |
| `--show-paying-member-invoices` | bool | Show paying member invoices |
| `--enable-gocardless` | bool | Enable GoCardless payments |
| `--use-go-cardless-pro-payments` | bool |  |
| `--gocardless-contract-number` | string | GoCardless contract number |
| `--stripe-bacs-d-d-payment-method-id` | string |  |
| `--stripe-bacs-d-d-mandate-id` | string |  |
| `--stripe-bacs-d-d-customer-token` | string |  |
| `--stripe-bacs-d-d-enabled` | bool |  |
| `--last-over-due-invoice-reminder` | DateTime |  |
| `--last-low-credit-reminder` | DateTime |  |
| `--referer-guid` | string |  |
| `--regular-payment-provider` | enum | Regular payment provider |
| `--regular-payment-contract-number` | string | Regular payment contract number |
| `--do-not-auto-process-invoices` | bool | Do not process invoices automatically |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--access-card-id` | string | Access card ID |
| `--access-pincode` | string | Access PIN code |
| `--key-fob-number` | string | Key fob number |
| `--notify-on-delivery` | bool | Notify on delivery |
| `--ezeep-user-id` | string |  |
| `--ezeep-free-printing` | bool |  |
| `--ezeep-blue-user-id` | string |  |
| `--ezeep-blue-free-printing` | bool |  |
| `--ezeep-blue-printing-enabled` | bool |  |
| `--paper-cut-pay-as-you-print` | bool |  |
| `--paper-cut-free-printing` | bool |  |
| `--paper-cut-user-id` | string |  |
| `--can-make-bookings` | bool | Can make bookings |
| `--can-book-for-team` | bool | Can book for team |
| `--can-purchase-products` | bool | Can purchase products |
| `--can-purchase-events` | bool | Can purchase events |
| `--can-access-community` | bool | Can access community |
| `--reference-number` | string | Reference number |
| `--tag` | string | Tag |
| `--notes` | string | Notes |
| `--show-alert` | bool | Show alert |
| `--alert-note` | string | Alert note |
| `--user-id` | long |  |
| `--active` | bool | Active |
| `--next-auto-invoice` | DateTime | Next auto invoice date |
| `--invoice-due-date-period` | int | Invoice due date period |
| `--registration-date` | DateTime | Registration date |
| `--general-terms-accepted` | bool | General terms accepted |
| `--last-renewal` | DateTime |  |
| `--last-invoice-attempt` | DateTime |  |
| `--custom1` | string | Custom field 1 |
| `--custom2` | string | Custom field 2 |
| `--custom3` | string | Custom field 3 |
| `--custom4` | string | Custom field 4 |
| `--custom5` | string | Custom field 5 |
| `--custom6` | string | Custom field 6 |
| `--custom7` | string | Custom field 7 |
| `--custom8` | string | Custom field 8 |
| `--custom9` | string | Custom field 9 |
| `--custom10` | string | Custom field 10 |
| `--custom11` | string | Custom field 11 |
| `--custom12` | string | Custom field 12 |
| `--custom13` | string | Custom field 13 |
| `--custom14` | string | Custom field 14 |
| `--custom15` | string | Custom field 15 |
| `--custom16` | string | Custom field 16 |
| `--custom17` | string | Custom field 17 |
| `--custom18` | string | Custom field 18 |
| `--custom19` | string | Custom field 19 |
| `--custom20` | string | Custom field 20 |
| `--custom21` | string | Custom field 21 |
| `--custom22` | string | Custom field 22 |
| `--custom23` | string | Custom field 23 |
| `--custom24` | string | Custom field 24 |
| `--custom25` | string | Custom field 25 |
| `--custom26` | string | Custom field 26 |
| `--custom27` | string | Custom field 27 |
| `--custom28` | string | Custom field 28 |
| `--custom29` | string | Custom field 29 |
| `--custom30` | string | Custom field 30 |
| `--next-invoice-local` | DateTime |  |
| `--next-auto-invoice-local` | DateTime |  |
| `--registration-date-local` | DateTime |  |
| `--access-control-debounce-time` | DateTime |  |
| `--office365-access-token` | string |  |
| `--office365-refresh-token` | string |  |
| `--zoom-access-token` | string |  |
| `--zoom-refresh-token` | string |  |
| `--zoom-user-id` | string |  |
| `--doordeck-private-key` | string |  |
| `--doordeck-public-key` | string |  |
| `--doordeck-user-guid` | string |  |
| `--office365-subscription-id` | string |  |
| `--salto-v2-access-token` | string |  |
| `--stripe-a-c-h-bank-token` | string |  |
| `--stripe-a-c-h-customer-token` | string |  |
| `--has-accepted-stripe-a-c-h-agreement` | bool |  |
| `--has-verified-stripe-a-c-h-deposits` | bool |  |
| `--purchase-order` | string | Purchase order |
| `--sync-to-square` | bool |  |
| `--notify-on-deliveries-email` | string | Notify on deliveries email |
| `--access-control-error-notification-sent` | bool |  |
| `--sync-to-paper-cut-due` | bool |  |
| `--google-api-token` | string |  |
| `--google-subscription-id` | string |  |
| `--invoice-segregation-override` | bool |  |
| `--invoice-segregate-contracts` | bool |  |
| `--invoice-segregate-bookings` | bool |  |
| `--invoice-segregate-products` | bool |  |
| `--invoice-segregate-time-passes` | bool |  |
| `--invoice-segregate-tickets` | bool |  |
| `--is-default-profile` | bool |  |
| `--invoice-segregate-charges` | bool |  |
| `--brivo-user-id` | int |  |
| `--ezeep-printing-enabled` | bool |  |
| `--invoice-due-date-day` | int |  |
| `--monday-attendance` | enum, required | Monday attendance |
| `--tuesday-attendance` | enum, required | Tuesday attendance |
| `--wednesday-attendance` | enum, required | Wednesday attendance |
| `--thursday-attendance` | enum, required | Thursday attendance |
| `--friday-attendance` | enum, required | Friday attendance |
| `--saturday-attendance` | enum, required | Saturday attendance |
| `--sunday-attendance` | enum, required | Sunday attendance |
| `--longitude` | decimal | Longitude |
| `--latitude` | decimal | Latitude |
| `--billing-longitude` | decimal | Billing longitude |
| `--billing-latitude` | decimal | Billing latitude |
| `--archived` | bool | Archived |

#### Coworker update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-type` | enum | Coworker type |
| `--businesses` | list, repeat flag |  |
| `--added-businesses` | list, repeat flag |  |
| `--removed-businesses` | list, repeat flag |  |
| `--teams` | list, repeat flag |  |
| `--added-teams` | list, repeat flag |  |
| `--removed-teams` | list, repeat flag |  |
| `--full-name` | string | Full name |
| `--salutation` | string | Salutation |
| `--gender` | enum | Gender |
| `--email` | string | Email address |
| `--new-avatar-url` | string |  |
| `--clear-avatar-file` | bool |  |
| `--new-banner-image-url` | string |  |
| `--clear-banner-image-file` | bool |  |
| `--address` | string | Address |
| `--post-code` | string | Post code |
| `--city` | string | City name |
| `--state` | string | State |
| `--country-id` | long |  |
| `--simple-time-zone-id` | long |  |
| `--mobile-phone` | string | Mobile phone |
| `--land-line` | string | Land line |
| `--date-of-birth` | DateTime | Date of birth |
| `--nick-name` | string | Nickname |
| `--business-area` | string | Business area |
| `--position` | string | Position |
| `--company-name` | string | Company name |
| `--profile-website` | string | Profile website |
| `--profile-tags` | string | Profile tags |
| `--profile-summary` | string | Profile summary |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook profile |
| `--google` | string |  |
| `--telegram` | string | Telegram handle |
| `--linkedin` | string | LinkedIn profile |
| `--skype` | string | Skype handle |
| `--github` | string | GitHub profile |
| `--pinterest` | string |  |
| `--flickr` | string |  |
| `--instagram` | string | Instagram profile |
| `--vimeo` | string |  |
| `--tumblr` | string |  |
| `--blogger` | string |  |
| `--profile-is-public` | bool | Profile is public |
| `--invoicing-business-id` | long |  |
| `--billing-email` | string | Billing email |
| `--billing-name` | string | Billing name |
| `--billing-address` | string | Billing address |
| `--billing-post-code` | string | Billing post code |
| `--billing-city` | string | Billing city |
| `--billing-state` | string | Billing state |
| `--billing-country-id` | long |  |
| `--billing-simple-time-zone-id` | long |  |
| `--tax-rate-type` | enum | Tax rate type |
| `--tax-rate` | decimal | Tax rate |
| `--tax-id-number` | string | Tax ID number |
| `--bank-name` | string | Bank name |
| `--bank-account` | string | Bank account |
| `--bank-branch` | string | Bank branch |
| `--notify-on-new-invoice` | bool | Notify on new invoice |
| `--notify-on-new-payment` | bool | Notify on new payment |
| `--notify-on-failed-payment` | bool | Notify on failed payment |
| `--show-paying-member-invoices` | bool | Show paying member invoices |
| `--enable-gocardless` | bool | Enable GoCardless payments |
| `--use-go-cardless-pro-payments` | bool |  |
| `--gocardless-contract-number` | string | GoCardless contract number |
| `--stripe-bacs-d-d-payment-method-id` | string |  |
| `--stripe-bacs-d-d-mandate-id` | string |  |
| `--stripe-bacs-d-d-customer-token` | string |  |
| `--stripe-bacs-d-d-enabled` | bool |  |
| `--last-over-due-invoice-reminder` | DateTime |  |
| `--last-low-credit-reminder` | DateTime |  |
| `--referer-guid` | string |  |
| `--regular-payment-provider` | enum | Regular payment provider |
| `--regular-payment-contract-number` | string | Regular payment contract number |
| `--do-not-auto-process-invoices` | bool | Do not process invoices automatically |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--access-card-id` | string | Access card ID |
| `--access-pincode` | string | Access PIN code |
| `--key-fob-number` | string | Key fob number |
| `--notify-on-delivery` | bool | Notify on delivery |
| `--ezeep-user-id` | string |  |
| `--ezeep-free-printing` | bool |  |
| `--ezeep-blue-user-id` | string |  |
| `--ezeep-blue-free-printing` | bool |  |
| `--ezeep-blue-printing-enabled` | bool |  |
| `--paper-cut-pay-as-you-print` | bool |  |
| `--paper-cut-free-printing` | bool |  |
| `--paper-cut-user-id` | string |  |
| `--can-make-bookings` | bool | Can make bookings |
| `--can-book-for-team` | bool | Can book for team |
| `--can-purchase-products` | bool | Can purchase products |
| `--can-purchase-events` | bool | Can purchase events |
| `--can-access-community` | bool | Can access community |
| `--reference-number` | string | Reference number |
| `--tag` | string | Tag |
| `--notes` | string | Notes |
| `--show-alert` | bool | Show alert |
| `--alert-note` | string | Alert note |
| `--user-id` | long |  |
| `--active` | bool | Active |
| `--next-auto-invoice` | DateTime | Next auto invoice date |
| `--invoice-due-date-period` | int | Invoice due date period |
| `--registration-date` | DateTime | Registration date |
| `--general-terms-accepted` | bool | General terms accepted |
| `--last-renewal` | DateTime |  |
| `--last-invoice-attempt` | DateTime |  |
| `--custom1` | string | Custom field 1 |
| `--custom2` | string | Custom field 2 |
| `--custom3` | string | Custom field 3 |
| `--custom4` | string | Custom field 4 |
| `--custom5` | string | Custom field 5 |
| `--custom6` | string | Custom field 6 |
| `--custom7` | string | Custom field 7 |
| `--custom8` | string | Custom field 8 |
| `--custom9` | string | Custom field 9 |
| `--custom10` | string | Custom field 10 |
| `--custom11` | string | Custom field 11 |
| `--custom12` | string | Custom field 12 |
| `--custom13` | string | Custom field 13 |
| `--custom14` | string | Custom field 14 |
| `--custom15` | string | Custom field 15 |
| `--custom16` | string | Custom field 16 |
| `--custom17` | string | Custom field 17 |
| `--custom18` | string | Custom field 18 |
| `--custom19` | string | Custom field 19 |
| `--custom20` | string | Custom field 20 |
| `--custom21` | string | Custom field 21 |
| `--custom22` | string | Custom field 22 |
| `--custom23` | string | Custom field 23 |
| `--custom24` | string | Custom field 24 |
| `--custom25` | string | Custom field 25 |
| `--custom26` | string | Custom field 26 |
| `--custom27` | string | Custom field 27 |
| `--custom28` | string | Custom field 28 |
| `--custom29` | string | Custom field 29 |
| `--custom30` | string | Custom field 30 |
| `--next-invoice-local` | DateTime |  |
| `--next-auto-invoice-local` | DateTime |  |
| `--registration-date-local` | DateTime |  |
| `--access-control-debounce-time` | DateTime |  |
| `--office365-access-token` | string |  |
| `--office365-refresh-token` | string |  |
| `--zoom-access-token` | string |  |
| `--zoom-refresh-token` | string |  |
| `--zoom-user-id` | string |  |
| `--doordeck-private-key` | string |  |
| `--doordeck-public-key` | string |  |
| `--doordeck-user-guid` | string |  |
| `--office365-subscription-id` | string |  |
| `--salto-v2-access-token` | string |  |
| `--stripe-a-c-h-bank-token` | string |  |
| `--stripe-a-c-h-customer-token` | string |  |
| `--has-accepted-stripe-a-c-h-agreement` | bool |  |
| `--has-verified-stripe-a-c-h-deposits` | bool |  |
| `--purchase-order` | string | Purchase order |
| `--sync-to-square` | bool |  |
| `--notify-on-deliveries-email` | string | Notify on deliveries email |
| `--access-control-error-notification-sent` | bool |  |
| `--sync-to-paper-cut-due` | bool |  |
| `--google-api-token` | string |  |
| `--google-subscription-id` | string |  |
| `--invoice-segregation-override` | bool |  |
| `--invoice-segregate-contracts` | bool |  |
| `--invoice-segregate-bookings` | bool |  |
| `--invoice-segregate-products` | bool |  |
| `--invoice-segregate-time-passes` | bool |  |
| `--invoice-segregate-tickets` | bool |  |
| `--is-default-profile` | bool |  |
| `--invoice-segregate-charges` | bool |  |
| `--brivo-user-id` | int |  |
| `--ezeep-printing-enabled` | bool |  |
| `--invoice-due-date-day` | int |  |
| `--monday-attendance` | enum | Monday attendance |
| `--tuesday-attendance` | enum | Tuesday attendance |
| `--wednesday-attendance` | enum | Wednesday attendance |
| `--thursday-attendance` | enum | Thursday attendance |
| `--friday-attendance` | enum | Friday attendance |
| `--saturday-attendance` | enum | Saturday attendance |
| `--sunday-attendance` | enum | Sunday attendance |
| `--longitude` | decimal | Longitude |
| `--latitude` | decimal | Latitude |
| `--billing-longitude` | decimal | Billing longitude |
| `--billing-latitude` | decimal | Billing latitude |
| `--archived` | bool | Archived |

### Coworker (key fields)

`Id`, `CoworkerType`, `FullName`, `Email`, `CompanyName`, `Active`, `RegistrationDate`, `TeamNames`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Teams`, `AddedTeams`, `RemovedTeams`

#### Coworker enum values

| Option | Valid values |
| ------ | ------------ |
| `--coworker-type` | `1` Individual, `2` Company |
| `--gender` | `0` None, `1` NotSet, `2` Male, `3` Female, `4` Other, `5` RatherNotSay |
| `--tax-rate-type` | `1` Default, `2` Reduced, `3` Exempt |
| `--monday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--tuesday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--wednesday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--thursday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--friday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--saturday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--sunday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |

<!-- END:GENERATED entity=Coworkers -->
