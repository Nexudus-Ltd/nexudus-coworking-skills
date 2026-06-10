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
| `nexudus coworkers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
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
| `--salutation` | string | Title or salutation prefix (e.g. Mr, Mrs, Dr) |
| `--gender` | enum | Gender of the person |
| `--email` | string | Email address |
| `--create-user` | bool | Create user account. Grants portal and app access and sends a welcome email with the access details |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-banner-image-url` | string | URL of a new file to upload as the banner image |
| `--clear-banner-image-file` | bool | Set to true to remove the current banner image file |
| `--address` | string | Street address |
| `--post-code` | string | Post code |
| `--city` | string | City name |
| `--state` | string | State or province |
| `--country-id` | long | ID of the country linked to this record |
| `--simple-time-zone-id` | long | ID of the simple time zone linked to this record |
| `--mobile-phone` | string | Mobile phone |
| `--land-line` | string | Land line |
| `--date-of-birth` | DateTime | Date of birth |
| `--from-date-of-birth` | range | |
| `--to-date-of-birth` | range | |
| `--nick-name` | string | Nickname |
| `--business-area` | string | Business area |
| `--position` | string | Display order position or job title |
| `--company-name` | string | Company name |
| `--profile-website` | string | Profile website |
| `--profile-tags` | string | Profile tags |
| `--profile-summary` | string | Profile summary |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook profile |
| `--google` | string | The google value for this coworker |
| `--telegram` | string | Telegram handle |
| `--linkedin` | string | LinkedIn profile |
| `--skype` | string | Skype handle |
| `--github` | string | GitHub profile |
| `--pinterest` | string | The pinterest value for this coworker |
| `--flickr` | string | The flickr value for this coworker |
| `--instagram` | string | Instagram profile |
| `--vimeo` | string | The vimeo value for this coworker |
| `--tumblr` | string | The tumblr value for this coworker |
| `--blogger` | string | The blogger value for this coworker |
| `--profile-is-public` | bool | Profile is public |
| `--invoicing-business-id` | long | ID of the invoicing business linked to this record |
| `--billing-email` | string | Billing email |
| `--billing-name` | string | Billing name |
| `--billing-address` | string | Billing address |
| `--billing-post-code` | string | Billing post code |
| `--billing-city` | string | Billing city |
| `--billing-state` | string | Billing state |
| `--billing-country-id` | long | ID of the billing country linked to this record |
| `--billing-simple-time-zone-id` | long | ID of the billing simple time zone linked to this record |
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
| `--use-go-cardless-pro-payments` | bool | Whether use go cardless pro payments is enabled |
| `--gocardless-contract-number` | string | GoCardless contract number |
| `--stripe-bacs-d-d-payment-method-id` | string | ID of the stripe bacs dd payment method associated with this record |
| `--stripe-bacs-d-d-mandate-id` | string | ID of the stripe bacs dd mandate associated with this record |
| `--stripe-bacs-d-d-customer-token` | string | The stripe bacs dd customer token value for this coworker |
| `--stripe-bacs-d-d-enabled` | bool | Whether stripe bacs dd enabled is enabled |
| `--last-over-due-invoice-reminder` | DateTime | Date/time value for last over due invoice reminder |
| `--from-last-over-due-invoice-reminder` | range | |
| `--to-last-over-due-invoice-reminder` | range | |
| `--last-low-credit-reminder` | DateTime | Date/time value for last low credit reminder |
| `--from-last-low-credit-reminder` | range | |
| `--to-last-low-credit-reminder` | range | |
| `--referer-guid` | string | Unique identifier (GUID) for the referer |
| `--regular-payment-provider` | enum | Regular payment provider |
| `--regular-payment-contract-number` | string | Regular payment contract number |
| `--do-not-auto-process-invoices` | bool | Do not process invoices automatically |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--access-card-id` | string | Access card ID |
| `--access-pincode` | string | Access PIN code |
| `--key-fob-number` | string | Key fob number |
| `--notify-on-delivery` | bool | Notify on delivery |
| `--ezeep-user-id` | string | ID of the ezeep user associated with this record |
| `--ezeep-free-printing` | bool | Whether ezeep free printing is enabled |
| `--ezeep-blue-user-id` | string | ID of the ezeep blue user associated with this record |
| `--ezeep-blue-free-printing` | bool | Whether ezeep blue free printing is enabled |
| `--ezeep-blue-printing-enabled` | bool | Whether ezeep blue printing enabled is enabled |
| `--paper-cut-pay-as-you-print` | bool | Whether paper cut pay as you print is enabled |
| `--paper-cut-free-printing` | bool | Whether paper cut free printing is enabled |
| `--paper-cut-user-id` | string | ID of the paper cut user associated with this record |
| `--can-make-bookings` | bool | Can make bookings |
| `--can-book-for-team` | bool | Can book for team |
| `--can-purchase-products` | bool | Can purchase products |
| `--can-purchase-events` | bool | Can purchase events |
| `--can-access-community` | bool | Can access community |
| `--reference-number` | string | Reference number |
| `--tag` | string | Free-form tag for categorising or filtering |
| `--notes` | string | Optional notes or comments about this coworker |
| `--show-alert` | bool | Show alert |
| `--alert-note` | string | Alert note |
| `--user-id` | long | ID of the user linked to this record |
| `--active` | bool | Whether this coworker is currently active |
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
| `--last-renewal` | DateTime | Date/time value for last renewal |
| `--from-last-renewal` | range | |
| `--to-last-renewal` | range | |
| `--last-invoice-attempt` | DateTime | Date/time value for last invoice attempt |
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
| `--next-invoice-local` | DateTime | Date/time value for next invoice local |
| `--from-next-invoice-local` | range | |
| `--to-next-invoice-local` | range | |
| `--next-auto-invoice-local` | DateTime | Date/time value for next auto invoice local |
| `--from-next-auto-invoice-local` | range | |
| `--to-next-auto-invoice-local` | range | |
| `--registration-date-local` | DateTime | Date/time value for registration date local |
| `--from-registration-date-local` | range | |
| `--to-registration-date-local` | range | |
| `--access-control-debounce-time` | DateTime | Date/time value for access control debounce time |
| `--from-access-control-debounce-time` | range | |
| `--to-access-control-debounce-time` | range | |
| `--office365-access-token` | string | The office365 access token value for this coworker |
| `--office365-refresh-token` | string | The office365 refresh token value for this coworker |
| `--zoom-access-token` | string | The zoom access token value for this coworker |
| `--zoom-refresh-token` | string | The zoom refresh token value for this coworker |
| `--zoom-user-id` | string | ID of the zoom user associated with this record |
| `--doordeck-private-key` | string | The doordeck private key value for this coworker |
| `--doordeck-public-key` | string | The doordeck public key value for this coworker |
| `--doordeck-user-guid` | string | Unique identifier (GUID) for the doordeck user |
| `--office365-subscription-id` | string | ID of the office365 subscription associated with this record |
| `--salto-v2-access-token` | string | The salto v2 access token value for this coworker |
| `--stripe-a-c-h-bank-token` | string | The stripe ach bank token value for this coworker |
| `--stripe-a-c-h-customer-token` | string | The stripe ach customer token value for this coworker |
| `--has-accepted-stripe-a-c-h-agreement` | bool | Whether has accepted stripe ach agreement is enabled |
| `--has-verified-stripe-a-c-h-deposits` | bool | Whether has verified stripe ach deposits is enabled |
| `--purchase-order` | string | Purchase order |
| `--sync-to-square` | bool | Whether sync to square is enabled |
| `--notify-on-deliveries-email` | string | Notify on deliveries email |
| `--access-control-error-notification-sent` | bool | Whether access control error notification sent is enabled |
| `--sync-to-paper-cut-due` | bool | Whether sync to paper cut due is enabled |
| `--google-api-token` | string | The google api token value for this coworker |
| `--google-subscription-id` | string | ID of the google subscription associated with this record |
| `--invoice-segregation-override` | bool | Whether invoice segregation override is enabled |
| `--invoice-segregate-contracts` | bool | Whether invoice segregate contracts is enabled |
| `--invoice-segregate-bookings` | bool | Whether invoice segregate bookings is enabled |
| `--invoice-segregate-products` | bool | Whether invoice segregate products is enabled |
| `--invoice-segregate-time-passes` | bool | Whether invoice segregate time passes is enabled |
| `--invoice-segregate-tickets` | bool | Whether invoice segregate tickets is enabled |
| `--is-default-profile` | bool | Whether is default profile is enabled |
| `--invoice-segregate-charges` | bool | Whether invoice segregate charges is enabled |
| `--brivo-user-id` | int | ID of the brivo user associated with this record |
| `--from-brivo-user-id` | range | |
| `--to-brivo-user-id` | range | |
| `--ezeep-printing-enabled` | bool | Whether ezeep printing enabled is enabled |
| `--invoice-due-date-day` | int | The invoice due date day value for this coworker |
| `--from-invoice-due-date-day` | range | |
| `--to-invoice-due-date-day` | range | |
| `--monday-attendance` | enum | Monday attendance |
| `--tuesday-attendance` | enum | Tuesday attendance |
| `--wednesday-attendance` | enum | Wednesday attendance |
| `--thursday-attendance` | enum | Thursday attendance |
| `--friday-attendance` | enum | Friday attendance |
| `--saturday-attendance` | enum | Saturday attendance |
| `--sunday-attendance` | enum | Sunday attendance |
| `--longitude` | decimal | GPS longitude coordinate |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | GPS latitude coordinate |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--billing-longitude` | decimal | Billing longitude |
| `--from-billing-longitude` | range | |
| `--to-billing-longitude` | range | |
| `--billing-latitude` | decimal | Billing latitude |
| `--from-billing-latitude` | range | |
| `--to-billing-latitude` | range | |
| `--archived` | bool | Whether this coworker is archived and hidden from active lists |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Coworker sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `FullName` ascending. If no `--order-by` is specified, the API returns results ordered by `FullName` (ascending).

#### Coworker create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-type` | enum, required | Coworker type |
| `--businesses` | list, repeat flag | List of businesses linked to this record |
| `--added-businesses` | list, repeat flag | The added businesses value for this coworker |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this coworker |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this coworker |
| `--removed-teams` | list, repeat flag | The removed teams value for this coworker |
| `--full-name` | string, required | Full name |
| `--salutation` | string | Title or salutation prefix (e.g. Mr, Mrs, Dr) |
| `--gender` | enum, required | Gender of the person |
| `--email` | string, required | Email address |
| `--create-user` | bool | Create user account. Grants portal and app access and sends a welcome email with the access details |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-banner-image-url` | string | URL of a new file to upload as the banner image |
| `--clear-banner-image-file` | bool | Set to true to remove the current banner image file |
| `--address` | string | Street address |
| `--post-code` | string | Post code |
| `--city` | string | City name |
| `--state` | string | State or province |
| `--country-id` | long, required | ID of the country linked to this record |
| `--simple-time-zone-id` | long, required | ID of the simple time zone linked to this record |
| `--mobile-phone` | string | Mobile phone |
| `--land-line` | string | Land line |
| `--date-of-birth` | DateTime | Date of birth |
| `--nick-name` | string | Nickname |
| `--business-area` | string | Business area |
| `--position` | string | Display order position or job title |
| `--company-name` | string | Company name |
| `--profile-website` | string | Profile website |
| `--profile-tags` | string | Profile tags |
| `--profile-summary` | string | Profile summary |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook profile |
| `--google` | string | The google value for this coworker |
| `--telegram` | string | Telegram handle |
| `--linkedin` | string | LinkedIn profile |
| `--skype` | string | Skype handle |
| `--github` | string | GitHub profile |
| `--pinterest` | string | The pinterest value for this coworker |
| `--flickr` | string | The flickr value for this coworker |
| `--instagram` | string | Instagram profile |
| `--vimeo` | string | The vimeo value for this coworker |
| `--tumblr` | string | The tumblr value for this coworker |
| `--blogger` | string | The blogger value for this coworker |
| `--profile-is-public` | bool | Profile is public |
| `--invoicing-business-id` | long | ID of the invoicing business linked to this record |
| `--billing-email` | string | Billing email |
| `--billing-name` | string | Billing name |
| `--billing-address` | string | Billing address |
| `--billing-post-code` | string | Billing post code |
| `--billing-city` | string | Billing city |
| `--billing-state` | string | Billing state |
| `--billing-country-id` | long | ID of the billing country linked to this record |
| `--billing-simple-time-zone-id` | long | ID of the billing simple time zone linked to this record |
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
| `--use-go-cardless-pro-payments` | bool | Whether use go cardless pro payments is enabled |
| `--gocardless-contract-number` | string | GoCardless contract number |
| `--stripe-bacs-d-d-payment-method-id` | string | ID of the stripe bacs dd payment method associated with this record |
| `--stripe-bacs-d-d-mandate-id` | string | ID of the stripe bacs dd mandate associated with this record |
| `--stripe-bacs-d-d-customer-token` | string | The stripe bacs dd customer token value for this coworker |
| `--stripe-bacs-d-d-enabled` | bool | Whether stripe bacs dd enabled is enabled |
| `--last-over-due-invoice-reminder` | DateTime | Date/time value for last over due invoice reminder |
| `--last-low-credit-reminder` | DateTime | Date/time value for last low credit reminder |
| `--referer-guid` | string | Unique identifier (GUID) for the referer |
| `--regular-payment-provider` | enum | Regular payment provider |
| `--regular-payment-contract-number` | string | Regular payment contract number |
| `--do-not-auto-process-invoices` | bool | Do not process invoices automatically |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--access-card-id` | string | Access card ID |
| `--access-pincode` | string | Access PIN code |
| `--key-fob-number` | string | Key fob number |
| `--notify-on-delivery` | bool | Notify on delivery |
| `--ezeep-user-id` | string | ID of the ezeep user associated with this record |
| `--ezeep-free-printing` | bool | Whether ezeep free printing is enabled |
| `--ezeep-blue-user-id` | string | ID of the ezeep blue user associated with this record |
| `--ezeep-blue-free-printing` | bool | Whether ezeep blue free printing is enabled |
| `--ezeep-blue-printing-enabled` | bool | Whether ezeep blue printing enabled is enabled |
| `--paper-cut-pay-as-you-print` | bool | Whether paper cut pay as you print is enabled |
| `--paper-cut-free-printing` | bool | Whether paper cut free printing is enabled |
| `--paper-cut-user-id` | string | ID of the paper cut user associated with this record |
| `--can-make-bookings` | bool | Can make bookings |
| `--can-book-for-team` | bool | Can book for team |
| `--can-purchase-products` | bool | Can purchase products |
| `--can-purchase-events` | bool | Can purchase events |
| `--can-access-community` | bool | Can access community |
| `--reference-number` | string | Reference number |
| `--tag` | string | Free-form tag for categorising or filtering |
| `--notes` | string | Optional notes or comments about this coworker |
| `--show-alert` | bool | Show alert |
| `--alert-note` | string | Alert note |
| `--user-id` | long | ID of the user linked to this record |
| `--active` | bool | Whether this coworker is currently active |
| `--next-auto-invoice` | DateTime | Next auto invoice date |
| `--invoice-due-date-period` | int | Invoice due date period |
| `--registration-date` | DateTime | Registration date |
| `--general-terms-accepted` | bool | General terms accepted |
| `--last-renewal` | DateTime | Date/time value for last renewal |
| `--last-invoice-attempt` | DateTime | Date/time value for last invoice attempt |
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
| `--next-invoice-local` | DateTime | Date/time value for next invoice local |
| `--next-auto-invoice-local` | DateTime | Date/time value for next auto invoice local |
| `--registration-date-local` | DateTime | Date/time value for registration date local |
| `--access-control-debounce-time` | DateTime | Date/time value for access control debounce time |
| `--office365-access-token` | string | The office365 access token value for this coworker |
| `--office365-refresh-token` | string | The office365 refresh token value for this coworker |
| `--zoom-access-token` | string | The zoom access token value for this coworker |
| `--zoom-refresh-token` | string | The zoom refresh token value for this coworker |
| `--zoom-user-id` | string | ID of the zoom user associated with this record |
| `--doordeck-private-key` | string | The doordeck private key value for this coworker |
| `--doordeck-public-key` | string | The doordeck public key value for this coworker |
| `--doordeck-user-guid` | string | Unique identifier (GUID) for the doordeck user |
| `--office365-subscription-id` | string | ID of the office365 subscription associated with this record |
| `--salto-v2-access-token` | string | The salto v2 access token value for this coworker |
| `--stripe-a-c-h-bank-token` | string | The stripe ach bank token value for this coworker |
| `--stripe-a-c-h-customer-token` | string | The stripe ach customer token value for this coworker |
| `--has-accepted-stripe-a-c-h-agreement` | bool | Whether has accepted stripe ach agreement is enabled |
| `--has-verified-stripe-a-c-h-deposits` | bool | Whether has verified stripe ach deposits is enabled |
| `--purchase-order` | string | Purchase order |
| `--sync-to-square` | bool | Whether sync to square is enabled |
| `--notify-on-deliveries-email` | string | Notify on deliveries email |
| `--access-control-error-notification-sent` | bool | Whether access control error notification sent is enabled |
| `--sync-to-paper-cut-due` | bool | Whether sync to paper cut due is enabled |
| `--google-api-token` | string | The google api token value for this coworker |
| `--google-subscription-id` | string | ID of the google subscription associated with this record |
| `--invoice-segregation-override` | bool | Whether invoice segregation override is enabled |
| `--invoice-segregate-contracts` | bool | Whether invoice segregate contracts is enabled |
| `--invoice-segregate-bookings` | bool | Whether invoice segregate bookings is enabled |
| `--invoice-segregate-products` | bool | Whether invoice segregate products is enabled |
| `--invoice-segregate-time-passes` | bool | Whether invoice segregate time passes is enabled |
| `--invoice-segregate-tickets` | bool | Whether invoice segregate tickets is enabled |
| `--is-default-profile` | bool | Whether is default profile is enabled |
| `--invoice-segregate-charges` | bool | Whether invoice segregate charges is enabled |
| `--brivo-user-id` | int | ID of the brivo user associated with this record |
| `--ezeep-printing-enabled` | bool | Whether ezeep printing enabled is enabled |
| `--invoice-due-date-day` | int | The invoice due date day value for this coworker |
| `--monday-attendance` | enum, required | Monday attendance |
| `--tuesday-attendance` | enum, required | Tuesday attendance |
| `--wednesday-attendance` | enum, required | Wednesday attendance |
| `--thursday-attendance` | enum, required | Thursday attendance |
| `--friday-attendance` | enum, required | Friday attendance |
| `--saturday-attendance` | enum, required | Saturday attendance |
| `--sunday-attendance` | enum, required | Sunday attendance |
| `--longitude` | decimal | GPS longitude coordinate |
| `--latitude` | decimal | GPS latitude coordinate |
| `--billing-longitude` | decimal | Billing longitude |
| `--billing-latitude` | decimal | Billing latitude |
| `--archived` | bool | Whether this coworker is archived and hidden from active lists |

#### Coworker update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-type` | enum | Coworker type |
| `--businesses` | list, repeat flag | List of businesses linked to this record |
| `--added-businesses` | list, repeat flag | The added businesses value for this coworker |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this coworker |
| `--teams` | list, repeat flag | List of teams linked to this record |
| `--added-teams` | list, repeat flag | The added teams value for this coworker |
| `--removed-teams` | list, repeat flag | The removed teams value for this coworker |
| `--full-name` | string | Full name |
| `--salutation` | string | Title or salutation prefix (e.g. Mr, Mrs, Dr) |
| `--gender` | enum | Gender of the person |
| `--email` | string | Email address |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-banner-image-url` | string | URL of a new file to upload as the banner image |
| `--clear-banner-image-file` | bool | Set to true to remove the current banner image file |
| `--address` | string | Street address |
| `--post-code` | string | Post code |
| `--city` | string | City name |
| `--state` | string | State or province |
| `--country-id` | long | ID of the country linked to this record |
| `--simple-time-zone-id` | long | ID of the simple time zone linked to this record |
| `--mobile-phone` | string | Mobile phone |
| `--land-line` | string | Land line |
| `--date-of-birth` | DateTime | Date of birth |
| `--nick-name` | string | Nickname |
| `--business-area` | string | Business area |
| `--position` | string | Display order position or job title |
| `--company-name` | string | Company name |
| `--profile-website` | string | Profile website |
| `--profile-tags` | string | Profile tags |
| `--profile-summary` | string | Profile summary |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook profile |
| `--google` | string | The google value for this coworker |
| `--telegram` | string | Telegram handle |
| `--linkedin` | string | LinkedIn profile |
| `--skype` | string | Skype handle |
| `--github` | string | GitHub profile |
| `--pinterest` | string | The pinterest value for this coworker |
| `--flickr` | string | The flickr value for this coworker |
| `--instagram` | string | Instagram profile |
| `--vimeo` | string | The vimeo value for this coworker |
| `--tumblr` | string | The tumblr value for this coworker |
| `--blogger` | string | The blogger value for this coworker |
| `--profile-is-public` | bool | Profile is public |
| `--invoicing-business-id` | long | ID of the invoicing business linked to this record |
| `--billing-email` | string | Billing email |
| `--billing-name` | string | Billing name |
| `--billing-address` | string | Billing address |
| `--billing-post-code` | string | Billing post code |
| `--billing-city` | string | Billing city |
| `--billing-state` | string | Billing state |
| `--billing-country-id` | long | ID of the billing country linked to this record |
| `--billing-simple-time-zone-id` | long | ID of the billing simple time zone linked to this record |
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
| `--use-go-cardless-pro-payments` | bool | Whether use go cardless pro payments is enabled |
| `--gocardless-contract-number` | string | GoCardless contract number |
| `--stripe-bacs-d-d-payment-method-id` | string | ID of the stripe bacs dd payment method associated with this record |
| `--stripe-bacs-d-d-mandate-id` | string | ID of the stripe bacs dd mandate associated with this record |
| `--stripe-bacs-d-d-customer-token` | string | The stripe bacs dd customer token value for this coworker |
| `--stripe-bacs-d-d-enabled` | bool | Whether stripe bacs dd enabled is enabled |
| `--last-over-due-invoice-reminder` | DateTime | Date/time value for last over due invoice reminder |
| `--last-low-credit-reminder` | DateTime | Date/time value for last low credit reminder |
| `--referer-guid` | string | Unique identifier (GUID) for the referer |
| `--regular-payment-provider` | enum | Regular payment provider |
| `--regular-payment-contract-number` | string | Regular payment contract number |
| `--do-not-auto-process-invoices` | bool | Do not process invoices automatically |
| `--allow-network-checkin` | bool | Allow network check-in |
| `--access-card-id` | string | Access card ID |
| `--access-pincode` | string | Access PIN code |
| `--key-fob-number` | string | Key fob number |
| `--notify-on-delivery` | bool | Notify on delivery |
| `--ezeep-user-id` | string | ID of the ezeep user associated with this record |
| `--ezeep-free-printing` | bool | Whether ezeep free printing is enabled |
| `--ezeep-blue-user-id` | string | ID of the ezeep blue user associated with this record |
| `--ezeep-blue-free-printing` | bool | Whether ezeep blue free printing is enabled |
| `--ezeep-blue-printing-enabled` | bool | Whether ezeep blue printing enabled is enabled |
| `--paper-cut-pay-as-you-print` | bool | Whether paper cut pay as you print is enabled |
| `--paper-cut-free-printing` | bool | Whether paper cut free printing is enabled |
| `--paper-cut-user-id` | string | ID of the paper cut user associated with this record |
| `--can-make-bookings` | bool | Can make bookings |
| `--can-book-for-team` | bool | Can book for team |
| `--can-purchase-products` | bool | Can purchase products |
| `--can-purchase-events` | bool | Can purchase events |
| `--can-access-community` | bool | Can access community |
| `--reference-number` | string | Reference number |
| `--tag` | string | Free-form tag for categorising or filtering |
| `--notes` | string | Optional notes or comments about this coworker |
| `--show-alert` | bool | Show alert |
| `--alert-note` | string | Alert note |
| `--user-id` | long | ID of the user linked to this record |
| `--active` | bool | Whether this coworker is currently active |
| `--next-auto-invoice` | DateTime | Next auto invoice date |
| `--invoice-due-date-period` | int | Invoice due date period |
| `--registration-date` | DateTime | Registration date |
| `--general-terms-accepted` | bool | General terms accepted |
| `--last-renewal` | DateTime | Date/time value for last renewal |
| `--last-invoice-attempt` | DateTime | Date/time value for last invoice attempt |
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
| `--next-invoice-local` | DateTime | Date/time value for next invoice local |
| `--next-auto-invoice-local` | DateTime | Date/time value for next auto invoice local |
| `--registration-date-local` | DateTime | Date/time value for registration date local |
| `--access-control-debounce-time` | DateTime | Date/time value for access control debounce time |
| `--office365-access-token` | string | The office365 access token value for this coworker |
| `--office365-refresh-token` | string | The office365 refresh token value for this coworker |
| `--zoom-access-token` | string | The zoom access token value for this coworker |
| `--zoom-refresh-token` | string | The zoom refresh token value for this coworker |
| `--zoom-user-id` | string | ID of the zoom user associated with this record |
| `--doordeck-private-key` | string | The doordeck private key value for this coworker |
| `--doordeck-public-key` | string | The doordeck public key value for this coworker |
| `--doordeck-user-guid` | string | Unique identifier (GUID) for the doordeck user |
| `--office365-subscription-id` | string | ID of the office365 subscription associated with this record |
| `--salto-v2-access-token` | string | The salto v2 access token value for this coworker |
| `--stripe-a-c-h-bank-token` | string | The stripe ach bank token value for this coworker |
| `--stripe-a-c-h-customer-token` | string | The stripe ach customer token value for this coworker |
| `--has-accepted-stripe-a-c-h-agreement` | bool | Whether has accepted stripe ach agreement is enabled |
| `--has-verified-stripe-a-c-h-deposits` | bool | Whether has verified stripe ach deposits is enabled |
| `--purchase-order` | string | Purchase order |
| `--sync-to-square` | bool | Whether sync to square is enabled |
| `--notify-on-deliveries-email` | string | Notify on deliveries email |
| `--access-control-error-notification-sent` | bool | Whether access control error notification sent is enabled |
| `--sync-to-paper-cut-due` | bool | Whether sync to paper cut due is enabled |
| `--google-api-token` | string | The google api token value for this coworker |
| `--google-subscription-id` | string | ID of the google subscription associated with this record |
| `--invoice-segregation-override` | bool | Whether invoice segregation override is enabled |
| `--invoice-segregate-contracts` | bool | Whether invoice segregate contracts is enabled |
| `--invoice-segregate-bookings` | bool | Whether invoice segregate bookings is enabled |
| `--invoice-segregate-products` | bool | Whether invoice segregate products is enabled |
| `--invoice-segregate-time-passes` | bool | Whether invoice segregate time passes is enabled |
| `--invoice-segregate-tickets` | bool | Whether invoice segregate tickets is enabled |
| `--is-default-profile` | bool | Whether is default profile is enabled |
| `--invoice-segregate-charges` | bool | Whether invoice segregate charges is enabled |
| `--brivo-user-id` | int | ID of the brivo user associated with this record |
| `--ezeep-printing-enabled` | bool | Whether ezeep printing enabled is enabled |
| `--invoice-due-date-day` | int | The invoice due date day value for this coworker |
| `--monday-attendance` | enum | Monday attendance |
| `--tuesday-attendance` | enum | Tuesday attendance |
| `--wednesday-attendance` | enum | Wednesday attendance |
| `--thursday-attendance` | enum | Thursday attendance |
| `--friday-attendance` | enum | Friday attendance |
| `--saturday-attendance` | enum | Saturday attendance |
| `--sunday-attendance` | enum | Sunday attendance |
| `--longitude` | decimal | GPS longitude coordinate |
| `--latitude` | decimal | GPS latitude coordinate |
| `--billing-longitude` | decimal | Billing longitude |
| `--billing-latitude` | decimal | Billing latitude |
| `--archived` | bool | Whether this coworker is archived and hidden from active lists |

#### Coworker PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--salutation` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--gender` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--address` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--post-code` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--city` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--state` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--mobile-phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--land-line` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--date-of-birth` | `DOB` | `«PII:DOB:a3f2b1c9»` |
| `--nick-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--profile-website` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--profile-summary` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--twitter` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--facebook` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--google` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--telegram` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--linkedin` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--skype` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--github` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--pinterest` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--flickr` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--instagram` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--vimeo` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--tumblr` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--blogger` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--invoicing-business-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--billing-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--billing-address` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--billing-post-code` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--billing-city` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--billing-state` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--tax-id-number` | `FINANCIAL` | `«PII:FINANCIAL:a3f2b1c9»` |
| `--bank-name` | `FINANCIAL` | `«PII:FINANCIAL:a3f2b1c9»` |
| `--bank-account` | `FINANCIAL` | `«PII:FINANCIAL:a3f2b1c9»` |
| `--bank-branch` | `FINANCIAL` | `«PII:FINANCIAL:a3f2b1c9»` |
| `--card-number` | `FINANCIAL` | `«PII:FINANCIAL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notify-on-deliveries-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus coworkers update <id> --full-name "«PII:NAME:a3f2b1c9»" --agent`

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
