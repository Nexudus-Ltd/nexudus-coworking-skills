# Coworkers

<!-- BEGIN:GENERATED entity=Coworkers -->

A customer is a person or company that uses a location; members have an active contract and contacts do not.

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
| `--coworker-type` | enum | Whether this customer record represents an Individual or a Company. |
| `--full-name` | string | Customer's full name; required and limited to 254 characters. |
| `--salutation` | string | Optional preferred form of address, such as 'Dr Adrian'; include how the customer wants to be addressed and never use a title alone, limited to 254 characters. |
| `--gender` | enum | Optional customer gender: NotSet, Male, Female, Other, or RatherNotSay. |
| `--email` | string | Customer email address; required by entity validation and used when creating an associated user account. |
| `--create-user` | bool | Whether to create the associated user account when this customer is first created; create-only. |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-banner-image-url` | string | URL of a new file to upload as the banner image |
| `--clear-banner-image-file` | bool | Set to true to remove the current banner image file |
| `--address` | string | Customer contact street address. |
| `--post-code` | string | Customer contact postal or ZIP code, limited to 15 characters. |
| `--city` | string | Customer contact city, limited to 50 characters. |
| `--state` | string | Customer contact state, province, or region, limited to 255 characters. |
| `--country-id` | long | ID of the customer's contact country; global reference data and required by entity validation. |
| `--simple-time-zone-id` | long | ID of the customer's time zone; global reference data and required by entity validation. |
| `--mobile-phone` | string | Customer mobile telephone number, limited to 255 characters. |
| `--land-line` | string | Customer landline or office telephone number, limited to 255 characters. |
| `--date-of-birth` | DateTime | Optional customer date of birth. |
| `--from-date-of-birth` | range | |
| `--to-date-of-birth` | range | |
| `--nick-name` | string | Optional informal customer name, limited to 254 characters. |
| `--business-area` | string | Customer's professional sector or business area, limited to 254 characters. |
| `--position` | string | Customer's job title or role, limited to 254 characters. |
| `--company-name` | string | Customer's employer or company name. |
| `--profile-website` | string | Customer's profile or company website URL, limited to 254 characters. |
| `--profile-tags` | string | Customer profile tags as a text value, limited to 254 characters. |
| `--profile-summary` | string | Customer's public profile summary or biography, limited to 4,096 characters. |
| `--twitter` | string | Customer's Twitter profile or handle, limited to 254 characters. |
| `--facebook` | string | Customer's Facebook profile or handle, limited to 254 characters. |
| `--google` | string | Customer's Google profile or handle, limited to 254 characters. |
| `--telegram` | string | Customer's Telegram profile or handle, limited to 254 characters. |
| `--linkedin` | string | Customer's LinkedIn profile or handle, limited to 254 characters. |
| `--skype` | string | Customer's Skype profile or handle, limited to 254 characters. |
| `--github` | string | Customer's GitHub profile or handle, limited to 254 characters. |
| `--pinterest` | string | Customer's Pinterest profile or handle, limited to 254 characters. |
| `--flickr` | string | Customer's Flickr profile or handle, limited to 254 characters. |
| `--instagram` | string | Customer's Instagram profile or handle, limited to 254 characters. |
| `--vimeo` | string | Customer's Vimeo profile or handle, limited to 254 characters. |
| `--tumblr` | string | Customer's Tumblr profile or handle, limited to 254 characters. |
| `--blogger` | string | Customer's Blogger profile or handle, limited to 254 characters. |
| `--profile-is-public` | bool | Whether the customer's profile is visible in the public member directory. |
| `--invoicing-business-id` | long | ID of the location that owns this customer (their home location) and issues their invoices unless invoice split by location is enabled; defaults to the current location when omitted on create. |
| `--billing-email` | string | Email address to receive this customer's invoices, limited to 254 characters. |
| `--billing-name` | string | Legal or trading name printed on invoices; when empty, invoices use the company name for Company customers or FullName otherwise. |
| `--billing-address` | string | Billing street address; when empty, invoices use the contact address. |
| `--billing-post-code` | string | Billing postal or ZIP code; when empty, invoices use the contact postal code. |
| `--billing-city` | string | Billing city; when empty, invoices use the contact city. |
| `--billing-state` | string | Billing state, province, or region; when empty, invoices use the contact state. |
| `--billing-country-id` | long | ID of the country for invoice addresses; global reference data, with the contact country and then the location country used as fallbacks. |
| `--billing-simple-time-zone-id` | long | ID of the time zone used for billing details; global reference data. |
| `--tax-rate-type` | enum | Tax treatment for this customer: Default, Reduced, or Exempt. |
| `--tax-rate` | decimal | Optional non-negative tax percentage override for this customer. |
| `--from-tax-rate` | range | |
| `--to-tax-rate` | range | |
| `--tax-id-number` | string | Customer tax or VAT identification number, limited to 255 characters. |
| `--bank-name` | string | Bank name used for this customer's regular-payment arrangement, limited to 255 characters. |
| `--bank-account` | string | Customer bank account identifier for a regular-payment arrangement; do not expose or set it through the agent. |
| `--bank-branch` | string | Customer bank branch or sort code for a regular-payment arrangement; do not expose or set it through the agent. |
| `--notify-on-new-invoice` | bool | Whether to notify the customer when a new invoice is created. |
| `--notify-on-new-payment` | bool | Whether to notify the customer when a payment is received. |
| `--notify-on-failed-payment` | bool | Whether to notify the customer when an automatic payment fails. |
| `--show-paying-member-invoices` | bool | Whether this customer can view invoices of their paying member when one exists. |
| `--enable-gocardless` | bool | Whether GoCardless regular payments are enabled for this customer. |
| `--use-go-cardless-pro-payments` | bool | Internal GoCardless Pro integration flag; managed by payment integration setup. |
| `--gocardless-contract-number` | string | External GoCardless mandate or contract identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-payment-method-id` | string | Stripe BACS payment-method identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-mandate-id` | string | Stripe BACS mandate identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-customer-token` | string | Stripe BACS customer token; security-sensitive integration credential not exposed to the agent. |
| `--stripe-bacs-d-d-enabled` | bool | Whether Stripe BACS direct-debit payments are enabled for this customer. |
| `--last-over-due-invoice-reminder` | DateTime | Timestamp of the last overdue-invoice reminder; maintained by reminder processing and not exposed to the agent. |
| `--from-last-over-due-invoice-reminder` | range | |
| `--to-last-over-due-invoice-reminder` | range | |
| `--last-low-credit-reminder` | DateTime | Timestamp of the last low-credit reminder; maintained by reminder processing and not exposed to the agent. |
| `--from-last-low-credit-reminder` | range | |
| `--to-last-low-credit-reminder` | range | |
| `--referer-guid` | string | Internal referral tracking identifier; not exposed to the agent. |
| `--regular-payment-provider` | enum | Regular-payment provider selected for this customer; set by the supported payment flow rather than by manual provider assignment. |
| `--regular-payment-contract-number` | string | External regular-payment contract or mandate identifier managed by the payment provider. |
| `--card-number` | string | Read-only last four digits of the customer's payment card; supplied by the payment provider and not exposed to the agent. |
| `--do-not-auto-process-invoices` | bool | Whether automatic invoice payment processing is disabled for this customer. |
| `--allow-network-checkin` | bool | Whether this customer may check in through the network check-in integration. |
| `--access-card-id` | string | Physical access-card identifier; managed through access control and not exposed to the agent. |
| `--access-pincode` | string | Access-control PIN; security-sensitive and not exposed to the agent. |
| `--key-fob-number` | string | Physical access key-fob identifier; managed through access control and not exposed to the agent. |
| `--notify-on-delivery` | bool | Whether to notify this customer about deliveries for their team. |
| `--ezeep-user-id` | string | External Ezeep user ID used by the printing integration. |
| `--ezeep-free-printing` | bool | Whether this customer can print for free through Ezeep. |
| `--ezeep-blue-user-id` | string | External Ezeep Blue user ID used by the printing integration. |
| `--ezeep-blue-free-printing` | bool | Whether this customer can print for free through Ezeep Blue. |
| `--ezeep-blue-printing-enabled` | bool | Internal Ezeep Blue printing synchronization flag; managed by the integration. |
| `--paper-cut-pay-as-you-print` | bool | Whether PaperCut pay-as-you-print is enabled for this customer. |
| `--paper-cut-free-printing` | bool | Whether this customer can print for free through PaperCut. |
| `--paper-cut-user-id` | string | External PaperCut user identifier used by the printing integration. |
| `--can-make-bookings` | bool | Whether this customer may make bookings. |
| `--can-book-for-team` | bool | Whether this customer may make bookings on behalf of their team. |
| `--can-purchase-products` | bool | Whether this customer may purchase products. |
| `--can-purchase-events` | bool | Whether this customer may purchase event tickets. |
| `--can-access-community` | bool | Whether this customer may access the community feature. |
| `--reference-number` | string | Optional external or internal reference number for this customer. |
| `--tag` | string | Optional free-text tag used to classify this customer. |
| `--notes` | string | Internal notes about this customer. |
| `--show-alert` | bool | Whether an alert should be shown when staff open this customer's record. |
| `--alert-note` | string | Alert message displayed to staff when ShowAlert is enabled. |
| `--user-id` | long | ID of the optional user account linked to this customer; update-only because creating the account uses CreateUser. |
| `--active` | bool | Whether this customer record is active. |
| `--next-auto-invoice` | DateTime | Next scheduled automatic-invoice date; recalculated from active contracts and maintained by invoicing processing. |
| `--from-next-auto-invoice` | range | |
| `--to-next-auto-invoice` | range | |
| `--invoice-due-date-period` | int | Optional number of days after issue date before this customer's invoices are due. |
| `--from-invoice-due-date-period` | range | |
| `--to-invoice-due-date-period` | range | |
| `--registration-date` | DateTime | Optional customer registration date. |
| `--from-registration-date` | range | |
| `--to-registration-date` | range | |
| `--general-terms-accepted` | bool | Whether the customer has accepted the location's general terms and conditions. |
| `--last-renewal` | DateTime | Timestamp used by allowance-renewal processing; maintained by the system and not exposed to the agent. |
| `--from-last-renewal` | range | |
| `--to-last-renewal` | range | |
| `--last-invoice-attempt` | DateTime | Timestamp of the latest invoice-processing attempt; maintained by the system and not exposed to the agent. |
| `--from-last-invoice-attempt` | range | |
| `--to-last-invoice-attempt` | range | |
| `--custom1` | string | Optional custom customer field 1; its meaning is configured by the location. |
| `--custom2` | string | Optional custom customer field 2; its meaning is configured by the location. |
| `--custom3` | string | Optional custom customer field 3; its meaning is configured by the location. |
| `--custom4` | string | Optional custom customer field 4; its meaning is configured by the location. |
| `--custom5` | string | Optional custom customer field 5; its meaning is configured by the location. |
| `--custom6` | string | Optional custom customer field 6; its meaning is configured by the location. |
| `--custom7` | string | Optional custom customer field 7; its meaning is configured by the location. |
| `--custom8` | string | Optional custom customer field 8; its meaning is configured by the location. |
| `--custom9` | string | Optional custom customer field 9; its meaning is configured by the location. |
| `--custom10` | string | Optional custom customer field 10; its meaning is configured by the location. |
| `--custom11` | string | Optional custom customer field 11; its meaning is configured by the location. |
| `--custom12` | string | Optional custom customer field 12; its meaning is configured by the location. |
| `--custom13` | string | Optional custom customer field 13; its meaning is configured by the location. |
| `--custom14` | string | Optional custom customer field 14; its meaning is configured by the location. |
| `--custom15` | string | Optional custom customer field 15; its meaning is configured by the location. |
| `--custom16` | string | Optional custom customer field 16; its meaning is configured by the location. |
| `--custom17` | string | Optional custom customer field 17; its meaning is configured by the location. |
| `--custom18` | string | Optional custom customer field 18; its meaning is configured by the location. |
| `--custom19` | string | Optional custom customer field 19; its meaning is configured by the location. |
| `--custom20` | string | Optional custom customer field 20; its meaning is configured by the location. |
| `--custom21` | string | Optional custom customer field 21; its meaning is configured by the location. |
| `--custom22` | string | Optional custom customer field 22; its meaning is configured by the location. |
| `--custom23` | string | Optional custom customer field 23; its meaning is configured by the location. |
| `--custom24` | string | Optional custom customer field 24; its meaning is configured by the location. |
| `--custom25` | string | Optional custom customer field 25; its meaning is configured by the location. |
| `--custom26` | string | Optional custom customer field 26; its meaning is configured by the location. |
| `--custom27` | string | Optional custom customer field 27; its meaning is configured by the location. |
| `--custom28` | string | Optional custom customer field 28; its meaning is configured by the location. |
| `--custom29` | string | Optional custom customer field 29; its meaning is configured by the location. |
| `--custom30` | string | Optional custom customer field 30; its meaning is configured by the location. |
| `--next-invoice-local` | DateTime | Localized invoice schedule value derived by the application; not exposed to the agent. |
| `--from-next-invoice-local` | range | |
| `--to-next-invoice-local` | range | |
| `--next-auto-invoice-local` | DateTime | Localized next automatic-invoice value derived by the application; not exposed to the agent. |
| `--from-next-auto-invoice-local` | range | |
| `--to-next-auto-invoice-local` | range | |
| `--registration-date-local` | DateTime | Localized registration-date value derived by the application; not exposed to the agent. |
| `--from-registration-date-local` | range | |
| `--to-registration-date-local` | range | |
| `--access-control-debounce-time` | DateTime | Internal access-control debounce timestamp; not exposed to the agent. |
| `--from-access-control-debounce-time` | range | |
| `--to-access-control-debounce-time` | range | |
| `--office365-access-token` | string | Microsoft 365 OAuth access token; security-sensitive credential not exposed to the agent. |
| `--office365-refresh-token` | string | Microsoft 365 OAuth refresh token; security-sensitive credential not exposed to the agent. |
| `--zoom-access-token` | string | Zoom OAuth access token; security-sensitive credential not exposed to the agent. |
| `--zoom-refresh-token` | string | Zoom OAuth refresh token; security-sensitive credential not exposed to the agent. |
| `--zoom-user-id` | string | External Zoom user ID managed by the calendar integration. |
| `--doordeck-private-key` | string | Doordeck private key; security-sensitive credential not exposed to the agent. |
| `--doordeck-public-key` | string | Doordeck public key used by the access integration; not exposed through customer administration. |
| `--doordeck-user-guid` | string | External Doordeck user ID managed by the access integration. |
| `--office365-subscription-id` | string | Microsoft 365 calendar subscription ID managed by the calendar integration. |
| `--salto-v2-access-token` | string | Salto access-control token; security-sensitive credential not exposed to the agent. |
| `--stripe-a-c-h-bank-token` | string | Stripe ACH bank token; security-sensitive payment credential not exposed to the agent. |
| `--stripe-a-c-h-customer-token` | string | Stripe ACH customer token; security-sensitive payment credential not exposed to the agent. |
| `--has-accepted-stripe-a-c-h-agreement` | bool | Internal Stripe ACH agreement status; maintained by the payment flow and not exposed to the agent. |
| `--has-verified-stripe-a-c-h-deposits` | bool | Internal Stripe ACH deposit-verification status; maintained by the payment flow and not exposed to the agent. |
| `--purchase-order` | string | Optional purchase-order reference used for this customer's billing. |
| `--sync-to-square` | bool | Internal Square synchronization flag; maintained by the integration and not exposed to the agent. |
| `--notify-on-deliveries-email` | string | Email address for delivery notifications, limited to 254 characters. |
| `--access-control-error-notification-sent` | bool | Internal marker that an access-control error notification was sent; not exposed to the agent. |
| `--sync-to-paper-cut-due` | bool | Internal PaperCut synchronization marker; not exposed to the agent. |
| `--google-api-token` | string | Google OAuth token; security-sensitive credential not exposed to the agent. |
| `--google-subscription-id` | string | Google calendar subscription ID managed by the calendar integration. |
| `--invoice-segregation-override` | bool | Whether customer-specific invoice-segregation settings override the location-level settings. |
| `--invoice-segregate-contracts` | bool | Whether charges for contracts other than the main contract are invoiced separately from main-contract charges when invoice segregation is enabled. |
| `--invoice-segregate-bookings` | bool | Whether booking charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-products` | bool | Whether product charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-time-passes` | bool | Whether pass charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-tickets` | bool | Whether event-ticket charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--is-default-profile` | bool | Whether this is the active customer profile when the linked user account has multiple customer profiles. |
| `--invoice-segregate-charges` | bool | Whether one-off charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--brivo-user-id` | int | External Brivo access-control user ID managed by the integration. |
| `--from-brivo-user-id` | range | |
| `--to-brivo-user-id` | range | |
| `--ezeep-printing-enabled` | bool | Internal Ezeep printing synchronization flag; managed by the integration. |
| `--invoice-due-date-day` | int | Day of the month used to calculate the customer-specific invoice due date. |
| `--from-invoice-due-date-day` | range | |
| `--to-invoice-due-date-day` | range | |
| `--monday-attendance` | enum | Expected Monday attendance: WorkingFromOffice or WorkingRemotely. |
| `--tuesday-attendance` | enum | Expected Tuesday attendance: WorkingFromOffice or WorkingRemotely. |
| `--wednesday-attendance` | enum | Expected Wednesday attendance: WorkingFromOffice or WorkingRemotely. |
| `--thursday-attendance` | enum | Expected Thursday attendance: WorkingFromOffice or WorkingRemotely. |
| `--friday-attendance` | enum | Expected Friday attendance: WorkingFromOffice or WorkingRemotely. |
| `--saturday-attendance` | enum | Expected Saturday attendance: WorkingFromOffice or WorkingRemotely. |
| `--sunday-attendance` | enum | Expected Sunday attendance: WorkingFromOffice or WorkingRemotely. |
| `--longitude` | decimal | Optional geographic longitude for the contact address. |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | Optional geographic latitude for the contact address. |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--billing-longitude` | decimal | Optional geographic longitude for the billing address. |
| `--from-billing-longitude` | range | |
| `--to-billing-longitude` | range | |
| `--billing-latitude` | decimal | Optional geographic latitude for the billing address. |
| `--from-billing-latitude` | range | |
| `--to-billing-latitude` | range | |
| `--archived` | bool | Whether this customer is archived. |
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
| `--coworker-type` | enum, required | Whether this customer record represents an Individual or a Company. |
| `--businesses` | list, repeat flag | List of location IDs where this customer is registered; replacing the list replaces all registrations. |
| `--added-businesses` | list, repeat flag | The added businesses value for this coworker |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this coworker |
| `--teams` | list, repeat flag | List of team IDs this customer belongs to; replacing the list replaces all team memberships. |
| `--added-teams` | list, repeat flag | The added teams value for this coworker |
| `--removed-teams` | list, repeat flag | The removed teams value for this coworker |
| `--full-name` | string, required | Customer's full name; required and limited to 254 characters. |
| `--salutation` | string | Optional preferred form of address, such as 'Dr Adrian'; include how the customer wants to be addressed and never use a title alone, limited to 254 characters. |
| `--gender` | enum, required | Optional customer gender: NotSet, Male, Female, Other, or RatherNotSay. |
| `--email` | string, required | Customer email address; required by entity validation and used when creating an associated user account. |
| `--create-user` | bool | Whether to create the associated user account when this customer is first created; create-only. |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-banner-image-url` | string | URL of a new file to upload as the banner image |
| `--clear-banner-image-file` | bool | Set to true to remove the current banner image file |
| `--address` | string | Customer contact street address. |
| `--post-code` | string | Customer contact postal or ZIP code, limited to 15 characters. |
| `--city` | string | Customer contact city, limited to 50 characters. |
| `--state` | string | Customer contact state, province, or region, limited to 255 characters. |
| `--country-id` | long, required | ID of the customer's contact country; global reference data and required by entity validation. |
| `--simple-time-zone-id` | long, required | ID of the customer's time zone; global reference data and required by entity validation. |
| `--mobile-phone` | string | Customer mobile telephone number, limited to 255 characters. |
| `--land-line` | string | Customer landline or office telephone number, limited to 255 characters. |
| `--date-of-birth` | DateTime | Optional customer date of birth. |
| `--nick-name` | string | Optional informal customer name, limited to 254 characters. |
| `--business-area` | string | Customer's professional sector or business area, limited to 254 characters. |
| `--position` | string | Customer's job title or role, limited to 254 characters. |
| `--company-name` | string | Customer's employer or company name. |
| `--profile-website` | string | Customer's profile or company website URL, limited to 254 characters. |
| `--profile-tags` | string | Customer profile tags as a text value, limited to 254 characters. |
| `--profile-summary` | string | Customer's public profile summary or biography, limited to 4,096 characters. |
| `--twitter` | string | Customer's Twitter profile or handle, limited to 254 characters. |
| `--facebook` | string | Customer's Facebook profile or handle, limited to 254 characters. |
| `--google` | string | Customer's Google profile or handle, limited to 254 characters. |
| `--telegram` | string | Customer's Telegram profile or handle, limited to 254 characters. |
| `--linkedin` | string | Customer's LinkedIn profile or handle, limited to 254 characters. |
| `--skype` | string | Customer's Skype profile or handle, limited to 254 characters. |
| `--github` | string | Customer's GitHub profile or handle, limited to 254 characters. |
| `--pinterest` | string | Customer's Pinterest profile or handle, limited to 254 characters. |
| `--flickr` | string | Customer's Flickr profile or handle, limited to 254 characters. |
| `--instagram` | string | Customer's Instagram profile or handle, limited to 254 characters. |
| `--vimeo` | string | Customer's Vimeo profile or handle, limited to 254 characters. |
| `--tumblr` | string | Customer's Tumblr profile or handle, limited to 254 characters. |
| `--blogger` | string | Customer's Blogger profile or handle, limited to 254 characters. |
| `--profile-is-public` | bool | Whether the customer's profile is visible in the public member directory. |
| `--invoicing-business-id` | long | ID of the location that owns this customer (their home location) and issues their invoices unless invoice split by location is enabled; defaults to the current location when omitted on create. |
| `--billing-email` | string | Email address to receive this customer's invoices, limited to 254 characters. |
| `--billing-name` | string | Legal or trading name printed on invoices; when empty, invoices use the company name for Company customers or FullName otherwise. |
| `--billing-address` | string | Billing street address; when empty, invoices use the contact address. |
| `--billing-post-code` | string | Billing postal or ZIP code; when empty, invoices use the contact postal code. |
| `--billing-city` | string | Billing city; when empty, invoices use the contact city. |
| `--billing-state` | string | Billing state, province, or region; when empty, invoices use the contact state. |
| `--billing-country-id` | long | ID of the country for invoice addresses; global reference data, with the contact country and then the location country used as fallbacks. |
| `--billing-simple-time-zone-id` | long | ID of the time zone used for billing details; global reference data. |
| `--tax-rate-type` | enum, required | Tax treatment for this customer: Default, Reduced, or Exempt. |
| `--tax-rate` | decimal | Optional non-negative tax percentage override for this customer. |
| `--tax-id-number` | string | Customer tax or VAT identification number, limited to 255 characters. |
| `--bank-name` | string | Bank name used for this customer's regular-payment arrangement, limited to 255 characters. |
| `--bank-account` | string | Customer bank account identifier for a regular-payment arrangement; do not expose or set it through the agent. |
| `--bank-branch` | string | Customer bank branch or sort code for a regular-payment arrangement; do not expose or set it through the agent. |
| `--notify-on-new-invoice` | bool | Whether to notify the customer when a new invoice is created. |
| `--notify-on-new-payment` | bool | Whether to notify the customer when a payment is received. |
| `--notify-on-failed-payment` | bool | Whether to notify the customer when an automatic payment fails. |
| `--show-paying-member-invoices` | bool | Whether this customer can view invoices of their paying member when one exists. |
| `--enable-gocardless` | bool | Whether GoCardless regular payments are enabled for this customer. |
| `--use-go-cardless-pro-payments` | bool | Internal GoCardless Pro integration flag; managed by payment integration setup. |
| `--gocardless-contract-number` | string | External GoCardless mandate or contract identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-payment-method-id` | string | Stripe BACS payment-method identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-mandate-id` | string | Stripe BACS mandate identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-customer-token` | string | Stripe BACS customer token; security-sensitive integration credential not exposed to the agent. |
| `--stripe-bacs-d-d-enabled` | bool | Whether Stripe BACS direct-debit payments are enabled for this customer. |
| `--last-over-due-invoice-reminder` | DateTime | Timestamp of the last overdue-invoice reminder; maintained by reminder processing and not exposed to the agent. |
| `--last-low-credit-reminder` | DateTime | Timestamp of the last low-credit reminder; maintained by reminder processing and not exposed to the agent. |
| `--referer-guid` | string | Internal referral tracking identifier; not exposed to the agent. |
| `--regular-payment-provider` | enum | Regular-payment provider selected for this customer; set by the supported payment flow rather than by manual provider assignment. |
| `--regular-payment-contract-number` | string | External regular-payment contract or mandate identifier managed by the payment provider. |
| `--card-number` | string | Read-only last four digits of the customer's payment card; supplied by the payment provider and not exposed to the agent. |
| `--do-not-auto-process-invoices` | bool | Whether automatic invoice payment processing is disabled for this customer. |
| `--allow-network-checkin` | bool | Whether this customer may check in through the network check-in integration. |
| `--access-card-id` | string | Physical access-card identifier; managed through access control and not exposed to the agent. |
| `--access-pincode` | string | Access-control PIN; security-sensitive and not exposed to the agent. |
| `--key-fob-number` | string | Physical access key-fob identifier; managed through access control and not exposed to the agent. |
| `--notify-on-delivery` | bool | Whether to notify this customer about deliveries for their team. |
| `--ezeep-user-id` | string | External Ezeep user ID used by the printing integration. |
| `--ezeep-free-printing` | bool | Whether this customer can print for free through Ezeep. |
| `--ezeep-blue-user-id` | string | External Ezeep Blue user ID used by the printing integration. |
| `--ezeep-blue-free-printing` | bool | Whether this customer can print for free through Ezeep Blue. |
| `--ezeep-blue-printing-enabled` | bool | Internal Ezeep Blue printing synchronization flag; managed by the integration. |
| `--paper-cut-pay-as-you-print` | bool | Whether PaperCut pay-as-you-print is enabled for this customer. |
| `--paper-cut-free-printing` | bool | Whether this customer can print for free through PaperCut. |
| `--paper-cut-user-id` | string | External PaperCut user identifier used by the printing integration. |
| `--can-make-bookings` | bool | Whether this customer may make bookings. |
| `--can-book-for-team` | bool | Whether this customer may make bookings on behalf of their team. |
| `--can-purchase-products` | bool | Whether this customer may purchase products. |
| `--can-purchase-events` | bool | Whether this customer may purchase event tickets. |
| `--can-access-community` | bool | Whether this customer may access the community feature. |
| `--reference-number` | string | Optional external or internal reference number for this customer. |
| `--tag` | string | Optional free-text tag used to classify this customer. |
| `--notes` | string | Internal notes about this customer. |
| `--show-alert` | bool | Whether an alert should be shown when staff open this customer's record. |
| `--alert-note` | string | Alert message displayed to staff when ShowAlert is enabled. |
| `--user-id` | long | ID of the optional user account linked to this customer; update-only because creating the account uses CreateUser. |
| `--active` | bool | Whether this customer record is active. |
| `--next-auto-invoice` | DateTime | Next scheduled automatic-invoice date; recalculated from active contracts and maintained by invoicing processing. |
| `--invoice-due-date-period` | int | Optional number of days after issue date before this customer's invoices are due. |
| `--registration-date` | DateTime | Optional customer registration date. |
| `--general-terms-accepted` | bool | Whether the customer has accepted the location's general terms and conditions. |
| `--last-renewal` | DateTime | Timestamp used by allowance-renewal processing; maintained by the system and not exposed to the agent. |
| `--last-invoice-attempt` | DateTime | Timestamp of the latest invoice-processing attempt; maintained by the system and not exposed to the agent. |
| `--custom1` | string | Optional custom customer field 1; its meaning is configured by the location. |
| `--custom2` | string | Optional custom customer field 2; its meaning is configured by the location. |
| `--custom3` | string | Optional custom customer field 3; its meaning is configured by the location. |
| `--custom4` | string | Optional custom customer field 4; its meaning is configured by the location. |
| `--custom5` | string | Optional custom customer field 5; its meaning is configured by the location. |
| `--custom6` | string | Optional custom customer field 6; its meaning is configured by the location. |
| `--custom7` | string | Optional custom customer field 7; its meaning is configured by the location. |
| `--custom8` | string | Optional custom customer field 8; its meaning is configured by the location. |
| `--custom9` | string | Optional custom customer field 9; its meaning is configured by the location. |
| `--custom10` | string | Optional custom customer field 10; its meaning is configured by the location. |
| `--custom11` | string | Optional custom customer field 11; its meaning is configured by the location. |
| `--custom12` | string | Optional custom customer field 12; its meaning is configured by the location. |
| `--custom13` | string | Optional custom customer field 13; its meaning is configured by the location. |
| `--custom14` | string | Optional custom customer field 14; its meaning is configured by the location. |
| `--custom15` | string | Optional custom customer field 15; its meaning is configured by the location. |
| `--custom16` | string | Optional custom customer field 16; its meaning is configured by the location. |
| `--custom17` | string | Optional custom customer field 17; its meaning is configured by the location. |
| `--custom18` | string | Optional custom customer field 18; its meaning is configured by the location. |
| `--custom19` | string | Optional custom customer field 19; its meaning is configured by the location. |
| `--custom20` | string | Optional custom customer field 20; its meaning is configured by the location. |
| `--custom21` | string | Optional custom customer field 21; its meaning is configured by the location. |
| `--custom22` | string | Optional custom customer field 22; its meaning is configured by the location. |
| `--custom23` | string | Optional custom customer field 23; its meaning is configured by the location. |
| `--custom24` | string | Optional custom customer field 24; its meaning is configured by the location. |
| `--custom25` | string | Optional custom customer field 25; its meaning is configured by the location. |
| `--custom26` | string | Optional custom customer field 26; its meaning is configured by the location. |
| `--custom27` | string | Optional custom customer field 27; its meaning is configured by the location. |
| `--custom28` | string | Optional custom customer field 28; its meaning is configured by the location. |
| `--custom29` | string | Optional custom customer field 29; its meaning is configured by the location. |
| `--custom30` | string | Optional custom customer field 30; its meaning is configured by the location. |
| `--next-invoice-local` | DateTime | Localized invoice schedule value derived by the application; not exposed to the agent. |
| `--next-auto-invoice-local` | DateTime | Localized next automatic-invoice value derived by the application; not exposed to the agent. |
| `--registration-date-local` | DateTime | Localized registration-date value derived by the application; not exposed to the agent. |
| `--access-control-debounce-time` | DateTime | Internal access-control debounce timestamp; not exposed to the agent. |
| `--office365-access-token` | string | Microsoft 365 OAuth access token; security-sensitive credential not exposed to the agent. |
| `--office365-refresh-token` | string | Microsoft 365 OAuth refresh token; security-sensitive credential not exposed to the agent. |
| `--zoom-access-token` | string | Zoom OAuth access token; security-sensitive credential not exposed to the agent. |
| `--zoom-refresh-token` | string | Zoom OAuth refresh token; security-sensitive credential not exposed to the agent. |
| `--zoom-user-id` | string | External Zoom user ID managed by the calendar integration. |
| `--doordeck-private-key` | string | Doordeck private key; security-sensitive credential not exposed to the agent. |
| `--doordeck-public-key` | string | Doordeck public key used by the access integration; not exposed through customer administration. |
| `--doordeck-user-guid` | string | External Doordeck user ID managed by the access integration. |
| `--office365-subscription-id` | string | Microsoft 365 calendar subscription ID managed by the calendar integration. |
| `--salto-v2-access-token` | string | Salto access-control token; security-sensitive credential not exposed to the agent. |
| `--stripe-a-c-h-bank-token` | string | Stripe ACH bank token; security-sensitive payment credential not exposed to the agent. |
| `--stripe-a-c-h-customer-token` | string | Stripe ACH customer token; security-sensitive payment credential not exposed to the agent. |
| `--has-accepted-stripe-a-c-h-agreement` | bool | Internal Stripe ACH agreement status; maintained by the payment flow and not exposed to the agent. |
| `--has-verified-stripe-a-c-h-deposits` | bool | Internal Stripe ACH deposit-verification status; maintained by the payment flow and not exposed to the agent. |
| `--purchase-order` | string | Optional purchase-order reference used for this customer's billing. |
| `--sync-to-square` | bool | Internal Square synchronization flag; maintained by the integration and not exposed to the agent. |
| `--notify-on-deliveries-email` | string | Email address for delivery notifications, limited to 254 characters. |
| `--access-control-error-notification-sent` | bool | Internal marker that an access-control error notification was sent; not exposed to the agent. |
| `--sync-to-paper-cut-due` | bool | Internal PaperCut synchronization marker; not exposed to the agent. |
| `--google-api-token` | string | Google OAuth token; security-sensitive credential not exposed to the agent. |
| `--google-subscription-id` | string | Google calendar subscription ID managed by the calendar integration. |
| `--invoice-segregation-override` | bool | Whether customer-specific invoice-segregation settings override the location-level settings. |
| `--invoice-segregate-contracts` | bool | Whether charges for contracts other than the main contract are invoiced separately from main-contract charges when invoice segregation is enabled. |
| `--invoice-segregate-bookings` | bool | Whether booking charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-products` | bool | Whether product charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-time-passes` | bool | Whether pass charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-tickets` | bool | Whether event-ticket charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--is-default-profile` | bool | Whether this is the active customer profile when the linked user account has multiple customer profiles. |
| `--invoice-segregate-charges` | bool | Whether one-off charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--brivo-user-id` | int | External Brivo access-control user ID managed by the integration. |
| `--ezeep-printing-enabled` | bool | Internal Ezeep printing synchronization flag; managed by the integration. |
| `--invoice-due-date-day` | int | Day of the month used to calculate the customer-specific invoice due date. |
| `--monday-attendance` | enum, required | Expected Monday attendance: WorkingFromOffice or WorkingRemotely. |
| `--tuesday-attendance` | enum, required | Expected Tuesday attendance: WorkingFromOffice or WorkingRemotely. |
| `--wednesday-attendance` | enum, required | Expected Wednesday attendance: WorkingFromOffice or WorkingRemotely. |
| `--thursday-attendance` | enum, required | Expected Thursday attendance: WorkingFromOffice or WorkingRemotely. |
| `--friday-attendance` | enum, required | Expected Friday attendance: WorkingFromOffice or WorkingRemotely. |
| `--saturday-attendance` | enum, required | Expected Saturday attendance: WorkingFromOffice or WorkingRemotely. |
| `--sunday-attendance` | enum, required | Expected Sunday attendance: WorkingFromOffice or WorkingRemotely. |
| `--longitude` | decimal | Optional geographic longitude for the contact address. |
| `--latitude` | decimal | Optional geographic latitude for the contact address. |
| `--billing-longitude` | decimal | Optional geographic longitude for the billing address. |
| `--billing-latitude` | decimal | Optional geographic latitude for the billing address. |
| `--archived` | bool | Whether this customer is archived. |

#### Coworker update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-type` | enum | Whether this customer record represents an Individual or a Company. |
| `--businesses` | list, repeat flag | List of location IDs where this customer is registered; replacing the list replaces all registrations. |
| `--added-businesses` | list, repeat flag | The added businesses value for this coworker |
| `--removed-businesses` | list, repeat flag | The removed businesses value for this coworker |
| `--teams` | list, repeat flag | List of team IDs this customer belongs to; replacing the list replaces all team memberships. |
| `--added-teams` | list, repeat flag | The added teams value for this coworker |
| `--removed-teams` | list, repeat flag | The removed teams value for this coworker |
| `--full-name` | string | Customer's full name; required and limited to 254 characters. |
| `--salutation` | string | Optional preferred form of address, such as 'Dr Adrian'; include how the customer wants to be addressed and never use a title alone, limited to 254 characters. |
| `--gender` | enum | Optional customer gender: NotSet, Male, Female, Other, or RatherNotSay. |
| `--email` | string | Customer email address; required by entity validation and used when creating an associated user account. |
| `--new-avatar-url` | string | URL of a new file to upload as the avatar |
| `--clear-avatar-file` | bool | Set to true to remove the current avatar file |
| `--new-banner-image-url` | string | URL of a new file to upload as the banner image |
| `--clear-banner-image-file` | bool | Set to true to remove the current banner image file |
| `--address` | string | Customer contact street address. |
| `--post-code` | string | Customer contact postal or ZIP code, limited to 15 characters. |
| `--city` | string | Customer contact city, limited to 50 characters. |
| `--state` | string | Customer contact state, province, or region, limited to 255 characters. |
| `--country-id` | long | ID of the customer's contact country; global reference data and required by entity validation. |
| `--simple-time-zone-id` | long | ID of the customer's time zone; global reference data and required by entity validation. |
| `--mobile-phone` | string | Customer mobile telephone number, limited to 255 characters. |
| `--land-line` | string | Customer landline or office telephone number, limited to 255 characters. |
| `--date-of-birth` | DateTime | Optional customer date of birth. |
| `--nick-name` | string | Optional informal customer name, limited to 254 characters. |
| `--business-area` | string | Customer's professional sector or business area, limited to 254 characters. |
| `--position` | string | Customer's job title or role, limited to 254 characters. |
| `--company-name` | string | Customer's employer or company name. |
| `--profile-website` | string | Customer's profile or company website URL, limited to 254 characters. |
| `--profile-tags` | string | Customer profile tags as a text value, limited to 254 characters. |
| `--profile-summary` | string | Customer's public profile summary or biography, limited to 4,096 characters. |
| `--twitter` | string | Customer's Twitter profile or handle, limited to 254 characters. |
| `--facebook` | string | Customer's Facebook profile or handle, limited to 254 characters. |
| `--google` | string | Customer's Google profile or handle, limited to 254 characters. |
| `--telegram` | string | Customer's Telegram profile or handle, limited to 254 characters. |
| `--linkedin` | string | Customer's LinkedIn profile or handle, limited to 254 characters. |
| `--skype` | string | Customer's Skype profile or handle, limited to 254 characters. |
| `--github` | string | Customer's GitHub profile or handle, limited to 254 characters. |
| `--pinterest` | string | Customer's Pinterest profile or handle, limited to 254 characters. |
| `--flickr` | string | Customer's Flickr profile or handle, limited to 254 characters. |
| `--instagram` | string | Customer's Instagram profile or handle, limited to 254 characters. |
| `--vimeo` | string | Customer's Vimeo profile or handle, limited to 254 characters. |
| `--tumblr` | string | Customer's Tumblr profile or handle, limited to 254 characters. |
| `--blogger` | string | Customer's Blogger profile or handle, limited to 254 characters. |
| `--profile-is-public` | bool | Whether the customer's profile is visible in the public member directory. |
| `--invoicing-business-id` | long | ID of the location that owns this customer (their home location) and issues their invoices unless invoice split by location is enabled; defaults to the current location when omitted on create. |
| `--billing-email` | string | Email address to receive this customer's invoices, limited to 254 characters. |
| `--billing-name` | string | Legal or trading name printed on invoices; when empty, invoices use the company name for Company customers or FullName otherwise. |
| `--billing-address` | string | Billing street address; when empty, invoices use the contact address. |
| `--billing-post-code` | string | Billing postal or ZIP code; when empty, invoices use the contact postal code. |
| `--billing-city` | string | Billing city; when empty, invoices use the contact city. |
| `--billing-state` | string | Billing state, province, or region; when empty, invoices use the contact state. |
| `--billing-country-id` | long | ID of the country for invoice addresses; global reference data, with the contact country and then the location country used as fallbacks. |
| `--billing-simple-time-zone-id` | long | ID of the time zone used for billing details; global reference data. |
| `--tax-rate-type` | enum | Tax treatment for this customer: Default, Reduced, or Exempt. |
| `--tax-rate` | decimal | Optional non-negative tax percentage override for this customer. |
| `--tax-id-number` | string | Customer tax or VAT identification number, limited to 255 characters. |
| `--bank-name` | string | Bank name used for this customer's regular-payment arrangement, limited to 255 characters. |
| `--bank-account` | string | Customer bank account identifier for a regular-payment arrangement; do not expose or set it through the agent. |
| `--bank-branch` | string | Customer bank branch or sort code for a regular-payment arrangement; do not expose or set it through the agent. |
| `--notify-on-new-invoice` | bool | Whether to notify the customer when a new invoice is created. |
| `--notify-on-new-payment` | bool | Whether to notify the customer when a payment is received. |
| `--notify-on-failed-payment` | bool | Whether to notify the customer when an automatic payment fails. |
| `--show-paying-member-invoices` | bool | Whether this customer can view invoices of their paying member when one exists. |
| `--enable-gocardless` | bool | Whether GoCardless regular payments are enabled for this customer. |
| `--use-go-cardless-pro-payments` | bool | Internal GoCardless Pro integration flag; managed by payment integration setup. |
| `--gocardless-contract-number` | string | External GoCardless mandate or contract identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-payment-method-id` | string | Stripe BACS payment-method identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-mandate-id` | string | Stripe BACS mandate identifier; managed by the payment integration and not exposed to the agent. |
| `--stripe-bacs-d-d-customer-token` | string | Stripe BACS customer token; security-sensitive integration credential not exposed to the agent. |
| `--stripe-bacs-d-d-enabled` | bool | Whether Stripe BACS direct-debit payments are enabled for this customer. |
| `--last-over-due-invoice-reminder` | DateTime | Timestamp of the last overdue-invoice reminder; maintained by reminder processing and not exposed to the agent. |
| `--last-low-credit-reminder` | DateTime | Timestamp of the last low-credit reminder; maintained by reminder processing and not exposed to the agent. |
| `--referer-guid` | string | Internal referral tracking identifier; not exposed to the agent. |
| `--regular-payment-provider` | enum | Regular-payment provider selected for this customer; set by the supported payment flow rather than by manual provider assignment. |
| `--regular-payment-contract-number` | string | External regular-payment contract or mandate identifier managed by the payment provider. |
| `--card-number` | string | Read-only last four digits of the customer's payment card; supplied by the payment provider and not exposed to the agent. |
| `--do-not-auto-process-invoices` | bool | Whether automatic invoice payment processing is disabled for this customer. |
| `--allow-network-checkin` | bool | Whether this customer may check in through the network check-in integration. |
| `--access-card-id` | string | Physical access-card identifier; managed through access control and not exposed to the agent. |
| `--access-pincode` | string | Access-control PIN; security-sensitive and not exposed to the agent. |
| `--key-fob-number` | string | Physical access key-fob identifier; managed through access control and not exposed to the agent. |
| `--notify-on-delivery` | bool | Whether to notify this customer about deliveries for their team. |
| `--ezeep-user-id` | string | External Ezeep user ID used by the printing integration. |
| `--ezeep-free-printing` | bool | Whether this customer can print for free through Ezeep. |
| `--ezeep-blue-user-id` | string | External Ezeep Blue user ID used by the printing integration. |
| `--ezeep-blue-free-printing` | bool | Whether this customer can print for free through Ezeep Blue. |
| `--ezeep-blue-printing-enabled` | bool | Internal Ezeep Blue printing synchronization flag; managed by the integration. |
| `--paper-cut-pay-as-you-print` | bool | Whether PaperCut pay-as-you-print is enabled for this customer. |
| `--paper-cut-free-printing` | bool | Whether this customer can print for free through PaperCut. |
| `--paper-cut-user-id` | string | External PaperCut user identifier used by the printing integration. |
| `--can-make-bookings` | bool | Whether this customer may make bookings. |
| `--can-book-for-team` | bool | Whether this customer may make bookings on behalf of their team. |
| `--can-purchase-products` | bool | Whether this customer may purchase products. |
| `--can-purchase-events` | bool | Whether this customer may purchase event tickets. |
| `--can-access-community` | bool | Whether this customer may access the community feature. |
| `--reference-number` | string | Optional external or internal reference number for this customer. |
| `--tag` | string | Optional free-text tag used to classify this customer. |
| `--notes` | string | Internal notes about this customer. |
| `--show-alert` | bool | Whether an alert should be shown when staff open this customer's record. |
| `--alert-note` | string | Alert message displayed to staff when ShowAlert is enabled. |
| `--user-id` | long | ID of the optional user account linked to this customer; update-only because creating the account uses CreateUser. |
| `--active` | bool | Whether this customer record is active. |
| `--next-auto-invoice` | DateTime | Next scheduled automatic-invoice date; recalculated from active contracts and maintained by invoicing processing. |
| `--invoice-due-date-period` | int | Optional number of days after issue date before this customer's invoices are due. |
| `--registration-date` | DateTime | Optional customer registration date. |
| `--general-terms-accepted` | bool | Whether the customer has accepted the location's general terms and conditions. |
| `--last-renewal` | DateTime | Timestamp used by allowance-renewal processing; maintained by the system and not exposed to the agent. |
| `--last-invoice-attempt` | DateTime | Timestamp of the latest invoice-processing attempt; maintained by the system and not exposed to the agent. |
| `--custom1` | string | Optional custom customer field 1; its meaning is configured by the location. |
| `--custom2` | string | Optional custom customer field 2; its meaning is configured by the location. |
| `--custom3` | string | Optional custom customer field 3; its meaning is configured by the location. |
| `--custom4` | string | Optional custom customer field 4; its meaning is configured by the location. |
| `--custom5` | string | Optional custom customer field 5; its meaning is configured by the location. |
| `--custom6` | string | Optional custom customer field 6; its meaning is configured by the location. |
| `--custom7` | string | Optional custom customer field 7; its meaning is configured by the location. |
| `--custom8` | string | Optional custom customer field 8; its meaning is configured by the location. |
| `--custom9` | string | Optional custom customer field 9; its meaning is configured by the location. |
| `--custom10` | string | Optional custom customer field 10; its meaning is configured by the location. |
| `--custom11` | string | Optional custom customer field 11; its meaning is configured by the location. |
| `--custom12` | string | Optional custom customer field 12; its meaning is configured by the location. |
| `--custom13` | string | Optional custom customer field 13; its meaning is configured by the location. |
| `--custom14` | string | Optional custom customer field 14; its meaning is configured by the location. |
| `--custom15` | string | Optional custom customer field 15; its meaning is configured by the location. |
| `--custom16` | string | Optional custom customer field 16; its meaning is configured by the location. |
| `--custom17` | string | Optional custom customer field 17; its meaning is configured by the location. |
| `--custom18` | string | Optional custom customer field 18; its meaning is configured by the location. |
| `--custom19` | string | Optional custom customer field 19; its meaning is configured by the location. |
| `--custom20` | string | Optional custom customer field 20; its meaning is configured by the location. |
| `--custom21` | string | Optional custom customer field 21; its meaning is configured by the location. |
| `--custom22` | string | Optional custom customer field 22; its meaning is configured by the location. |
| `--custom23` | string | Optional custom customer field 23; its meaning is configured by the location. |
| `--custom24` | string | Optional custom customer field 24; its meaning is configured by the location. |
| `--custom25` | string | Optional custom customer field 25; its meaning is configured by the location. |
| `--custom26` | string | Optional custom customer field 26; its meaning is configured by the location. |
| `--custom27` | string | Optional custom customer field 27; its meaning is configured by the location. |
| `--custom28` | string | Optional custom customer field 28; its meaning is configured by the location. |
| `--custom29` | string | Optional custom customer field 29; its meaning is configured by the location. |
| `--custom30` | string | Optional custom customer field 30; its meaning is configured by the location. |
| `--next-invoice-local` | DateTime | Localized invoice schedule value derived by the application; not exposed to the agent. |
| `--next-auto-invoice-local` | DateTime | Localized next automatic-invoice value derived by the application; not exposed to the agent. |
| `--registration-date-local` | DateTime | Localized registration-date value derived by the application; not exposed to the agent. |
| `--access-control-debounce-time` | DateTime | Internal access-control debounce timestamp; not exposed to the agent. |
| `--office365-access-token` | string | Microsoft 365 OAuth access token; security-sensitive credential not exposed to the agent. |
| `--office365-refresh-token` | string | Microsoft 365 OAuth refresh token; security-sensitive credential not exposed to the agent. |
| `--zoom-access-token` | string | Zoom OAuth access token; security-sensitive credential not exposed to the agent. |
| `--zoom-refresh-token` | string | Zoom OAuth refresh token; security-sensitive credential not exposed to the agent. |
| `--zoom-user-id` | string | External Zoom user ID managed by the calendar integration. |
| `--doordeck-private-key` | string | Doordeck private key; security-sensitive credential not exposed to the agent. |
| `--doordeck-public-key` | string | Doordeck public key used by the access integration; not exposed through customer administration. |
| `--doordeck-user-guid` | string | External Doordeck user ID managed by the access integration. |
| `--office365-subscription-id` | string | Microsoft 365 calendar subscription ID managed by the calendar integration. |
| `--salto-v2-access-token` | string | Salto access-control token; security-sensitive credential not exposed to the agent. |
| `--stripe-a-c-h-bank-token` | string | Stripe ACH bank token; security-sensitive payment credential not exposed to the agent. |
| `--stripe-a-c-h-customer-token` | string | Stripe ACH customer token; security-sensitive payment credential not exposed to the agent. |
| `--has-accepted-stripe-a-c-h-agreement` | bool | Internal Stripe ACH agreement status; maintained by the payment flow and not exposed to the agent. |
| `--has-verified-stripe-a-c-h-deposits` | bool | Internal Stripe ACH deposit-verification status; maintained by the payment flow and not exposed to the agent. |
| `--purchase-order` | string | Optional purchase-order reference used for this customer's billing. |
| `--sync-to-square` | bool | Internal Square synchronization flag; maintained by the integration and not exposed to the agent. |
| `--notify-on-deliveries-email` | string | Email address for delivery notifications, limited to 254 characters. |
| `--access-control-error-notification-sent` | bool | Internal marker that an access-control error notification was sent; not exposed to the agent. |
| `--sync-to-paper-cut-due` | bool | Internal PaperCut synchronization marker; not exposed to the agent. |
| `--google-api-token` | string | Google OAuth token; security-sensitive credential not exposed to the agent. |
| `--google-subscription-id` | string | Google calendar subscription ID managed by the calendar integration. |
| `--invoice-segregation-override` | bool | Whether customer-specific invoice-segregation settings override the location-level settings. |
| `--invoice-segregate-contracts` | bool | Whether charges for contracts other than the main contract are invoiced separately from main-contract charges when invoice segregation is enabled. |
| `--invoice-segregate-bookings` | bool | Whether booking charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-products` | bool | Whether product charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-time-passes` | bool | Whether pass charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--invoice-segregate-tickets` | bool | Whether event-ticket charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--is-default-profile` | bool | Whether this is the active customer profile when the linked user account has multiple customer profiles. |
| `--invoice-segregate-charges` | bool | Whether one-off charges are invoiced separately from plan and contract charges when invoice segregation is enabled. |
| `--brivo-user-id` | int | External Brivo access-control user ID managed by the integration. |
| `--ezeep-printing-enabled` | bool | Internal Ezeep printing synchronization flag; managed by the integration. |
| `--invoice-due-date-day` | int | Day of the month used to calculate the customer-specific invoice due date. |
| `--monday-attendance` | enum | Expected Monday attendance: WorkingFromOffice or WorkingRemotely. |
| `--tuesday-attendance` | enum | Expected Tuesday attendance: WorkingFromOffice or WorkingRemotely. |
| `--wednesday-attendance` | enum | Expected Wednesday attendance: WorkingFromOffice or WorkingRemotely. |
| `--thursday-attendance` | enum | Expected Thursday attendance: WorkingFromOffice or WorkingRemotely. |
| `--friday-attendance` | enum | Expected Friday attendance: WorkingFromOffice or WorkingRemotely. |
| `--saturday-attendance` | enum | Expected Saturday attendance: WorkingFromOffice or WorkingRemotely. |
| `--sunday-attendance` | enum | Expected Sunday attendance: WorkingFromOffice or WorkingRemotely. |
| `--longitude` | decimal | Optional geographic longitude for the contact address. |
| `--latitude` | decimal | Optional geographic latitude for the contact address. |
| `--billing-longitude` | decimal | Optional geographic longitude for the billing address. |
| `--billing-latitude` | decimal | Optional geographic latitude for the billing address. |
| `--archived` | bool | Whether this customer is archived. |

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
| `--gender` | `1` NotSet, `2` Male, `3` Female, `4` Other, `5` RatherNotSay |
| `--tax-rate-type` | `1` Default, `2` Reduced, `3` Exempt |
| `--monday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--tuesday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--wednesday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--thursday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--friday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--saturday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |
| `--sunday-attendance` | `1` WorkingFromOffice, `2` WorkingFromHome, `3` WorkingFromAbroad, `4` NotWorking, `5` Undefined |

<!-- END:GENERATED entity=Coworkers -->
