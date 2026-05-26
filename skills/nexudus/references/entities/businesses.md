# Businesses

<!-- BEGIN:GENERATED entity=Businesses -->

A **Business** represents an individual location or a group of locations in Nexudus. Most records in the system are connected — directly or via other records — to a business, which controls access and visibility based on the locations a user or customer can access.

Businesses can be organised into a hierarchy using `RootLocationId`, which references the parent business of a given business. A business with no `RootLocationId` is a top-level location. Child businesses inherit certain configuration from their parent.

Each business defines its own address, contact details, currency, opening hours, and public-facing content (Passport profile, website text, branding images). Read-only properties such as opening hours, theme, and image URLs reflect the current configuration set through the Nexudus admin UI.

Businesses support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus businesses list --agent` | List all businesses |
| `nexudus businesses list --id <id> --agent` | Filter by single ID |
| `nexudus businesses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businesses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businesses list --name <value> --website <value> --agent` | Filter businesses by properties |
| `nexudus businesses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businesses get <id> --agent` | Get single business |
| `nexudus businesses update <id> --name "New Name" --agent` | Update business |

#### Business list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--visited-help-items` | enum |  |
| `--name` | string | Display name of the business location |
| `--default-language` | enum | Default language identifier for communications and UI |
| `--space-website-language-id` | long |  |
| `--website` | string | URL slug used for the business's public web address |
| `--default-payment-gateway-id` | long |  |
| `--terms` | string | Terms and conditions text for this business |
| `--short-intro` | string | Brief introduction shown on the business profile |
| `--about` | string | Extended 'About Us' text for the business profile |
| `--quote` | string | Highlight quote displayed on the business profile |
| `--privacy-url` | string | URL to the business's privacy policy |
| `--cookie-url` | string | URL to the business's cookie policy |
| `--web-contact` | string | Public-facing web contact URL |
| `--welcome-email` | string |  |
| `--address` | string | Street address of the business |
| `--phone` | string | Primary phone number displayed on the business profile |
| `--fax` | string | Fax number |
| `--email` | string | Primary email address displayed on the business profile |
| `--trial-expire-date` | DateTime |  |
| `--from-trial-expire-date` | range | |
| `--to-trial-expire-date` | range | |
| `--last-over-due-invoice-reminder` | DateTime |  |
| `--from-last-over-due-invoice-reminder` | range | |
| `--to-last-over-due-invoice-reminder` | range | |
| `--last-welcome-email` | DateTime |  |
| `--from-last-welcome-email` | range | |
| `--to-last-welcome-email` | range | |
| `--country-id` | long |  |
| `--currency-id` | long |  |
| `--simple-time-zone-id` | long |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |
| `--new-banner-image-url` | string |  |
| `--clear-banner-image-file` | bool |  |
| `--new-nex-io-banner-image-url` | string |  |
| `--clear-nex-io-banner-image-file` | bool |  |
| `--discount-percentage` | decimal |  |
| `--from-discount-percentage` | range | |
| `--to-discount-percentage` | range | |
| `--discount-amount` | decimal |  |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--last-language-token-update` | DateTime |  |
| `--from-last-language-token-update` | range | |
| `--to-last-language-token-update` | range | |
| `--has-created-default-file-templates` | bool |  |
| `--invoicing-period` | int |  |
| `--from-invoicing-period` | range | |
| `--to-invoicing-period` | range | |
| `--suspended` | bool |  |
| `--custom-passport-app` | bool |  |
| `--reminders-processed-on` | DateTime |  |
| `--from-reminders-processed-on` | range | |
| `--to-reminders-processed-on` | range | |
| `--pre-auth-id` | string |  |
| `--last4` | string | Last 4 digits of the payment card on file |
| `--preauth-error` | string | Most recent pre-authorisation error message |
| `--pre-auth-processed-on` | DateTime |  |
| `--from-pre-auth-processed-on` | range | |
| `--to-pre-auth-processed-on` | range | |
| `--last-charged-invoice` | int |  |
| `--from-last-charged-invoice` | range | |
| `--to-last-charged-invoice` | range | |
| `--last-charged-transaction` | int |  |
| `--from-last-charged-transaction` | range | |
| `--to-last-charged-transaction` | range | |
| `--last-charged-attendee` | int |  |
| `--from-last-charged-attendee` | range | |
| `--to-last-charged-attendee` | range | |
| `--passport-channels` | string | Passport channels this business is listed under |
| `--passport-only` | bool |  |
| `--passport-published` | bool | Whether this business is published and visible on Nexudus Passport |
| `--new-passport-banner-url` | string |  |
| `--clear-passport-banner-file` | bool |  |
| `--passport-name` | string | Display name shown on the Nexudus Passport listing |
| `--passport-tagline` | string | Tagline shown on the Nexudus Passport listing |
| `--venue-type` | enum | Type of venue (0 = default) |
| `--tags` | string | Comma-separated tags for categorising the business |
| `--floors` | int | Number of floors in the business premises |
| `--from-floors` | range | |
| `--to-floors` | range | |
| `--floor-space` | int | Total floor space of the business premises |
| `--from-floor-space` | range | |
| `--to-floor-space` | range | |
| `--floor-space-unit` | enum | Unit for FloorSpace (0 = default) |
| `--longitude` | decimal | Longitude coordinate for map positioning |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | Latitude coordinate for map positioning |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--passport-description` | string | Full description shown on the Nexudus Passport listing |
| `--city` | string | Town or city where the business is located |
| `--state` | string | State or province where the business is located |
| `--postcode` | string | Postal or ZIP code |
| `--street-name` | string | Street name component of the address |
| `--street-number` | string | Street number component of the address |
| `--neighborhood` | string | Neighborhood or district name |
| `--contact-phone` | string | Secondary contact phone number |
| `--contact-email` | string | Secondary contact email address |
| `--passport-members` | enum | Passport members directory access level |
| `--passport-events` | enum | Passport events listing access level |
| `--passport-community` | enum | Passport community board access level |
| `--passport-blog` | enum | Passport blog posts access level |
| `--mon-open` | int | Monday opening time (minutes from midnight) |
| `--from-mon-open` | range | |
| `--to-mon-open` | range | |
| `--mon-close` | int | Monday closing time (minutes from midnight) |
| `--from-mon-close` | range | |
| `--to-mon-close` | range | |
| `--tue-open` | int | Tuesday opening time (minutes from midnight) |
| `--from-tue-open` | range | |
| `--to-tue-open` | range | |
| `--tue-close` | int | Tuesday closing time (minutes from midnight) |
| `--from-tue-close` | range | |
| `--to-tue-close` | range | |
| `--wed-open` | int | Wednesday opening time (minutes from midnight) |
| `--from-wed-open` | range | |
| `--to-wed-open` | range | |
| `--wed-close` | int | Wednesday closing time (minutes from midnight) |
| `--from-wed-close` | range | |
| `--to-wed-close` | range | |
| `--thu-open` | int | Thursday opening time (minutes from midnight) |
| `--from-thu-open` | range | |
| `--to-thu-open` | range | |
| `--thu-close` | int | Thursday closing time (minutes from midnight) |
| `--from-thu-close` | range | |
| `--to-thu-close` | range | |
| `--fri-open` | int | Friday opening time (minutes from midnight) |
| `--from-fri-open` | range | |
| `--to-fri-open` | range | |
| `--fri-close` | int | Friday closing time (minutes from midnight) |
| `--from-fri-close` | range | |
| `--to-fri-close` | range | |
| `--sat-open` | int | Saturday opening time (minutes from midnight) |
| `--from-sat-open` | range | |
| `--to-sat-open` | range | |
| `--sat-close` | int | Saturday closing time (minutes from midnight) |
| `--from-sat-close` | range | |
| `--to-sat-close` | range | |
| `--sun-open` | int | Sunday opening time (minutes from midnight) |
| `--from-sun-open` | range | |
| `--to-sun-open` | range | |
| `--sun-close` | int | Sunday closing time (minutes from midnight) |
| `--from-sun-close` | range | |
| `--to-sun-close` | range | |
| `--mon-closed` | bool | Whether the business is closed on Mondays |
| `--tue-closed` | bool | Whether the business is closed on Tuesdays |
| `--wed-closed` | bool | Whether the business is closed on Wednesdays |
| `--thu-closed` | bool | Whether the business is closed on Thursdays |
| `--fri-closed` | bool | Whether the business is closed on Fridays |
| `--sat-closed` | bool | Whether the business is closed on Saturdays |
| `--sun-closed` | bool | Whether the business is closed on Sundays |
| `--same-opening` | bool | Whether all days share the same opening and closing times |
| `--current-back-end-version` | int |  |
| `--from-current-back-end-version` | range | |
| `--to-current-back-end-version` | range | |
| `--authentication-provider` | string |  |
| `--created-by` | string |  |
| `--default-payment-term` | int |  |
| `--from-default-payment-term` | range | |
| `--to-default-payment-term` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Business update options

| Option | Type | Description |
| --- | --- | --- |
| `--visited-help-items` | enum |  |
| `--name` | string | Display name of the business location |
| `--default-language` | enum | Default language identifier for communications and UI |
| `--space-website-language-id` | long |  |
| `--website` | string | URL slug used for the business's public web address |
| `--default-payment-gateway-id` | long |  |
| `--terms` | string | Terms and conditions text for this business |
| `--short-intro` | string | Brief introduction shown on the business profile |
| `--about` | string | Extended 'About Us' text for the business profile |
| `--quote` | string | Highlight quote displayed on the business profile |
| `--privacy-url` | string | URL to the business's privacy policy |
| `--cookie-url` | string | URL to the business's cookie policy |
| `--web-contact` | string | Public-facing web contact URL |
| `--welcome-email` | string |  |
| `--address` | string | Street address of the business |
| `--phone` | string | Primary phone number displayed on the business profile |
| `--fax` | string | Fax number |
| `--email` | string | Primary email address displayed on the business profile |
| `--trial-expire-date` | DateTime |  |
| `--last-over-due-invoice-reminder` | DateTime |  |
| `--last-welcome-email` | DateTime |  |
| `--country-id` | long |  |
| `--currency-id` | long |  |
| `--simple-time-zone-id` | long |  |
| `--new-logo-url` | string |  |
| `--clear-logo-file` | bool |  |
| `--new-banner-image-url` | string |  |
| `--clear-banner-image-file` | bool |  |
| `--new-nex-io-banner-image-url` | string |  |
| `--clear-nex-io-banner-image-file` | bool |  |
| `--discount-percentage` | decimal |  |
| `--discount-amount` | decimal |  |
| `--last-language-token-update` | DateTime |  |
| `--has-created-default-file-templates` | bool |  |
| `--invoicing-period` | int |  |
| `--suspended` | bool |  |
| `--custom-passport-app` | bool |  |
| `--reminders-processed-on` | DateTime |  |
| `--pre-auth-id` | string |  |
| `--last4` | string | Last 4 digits of the payment card on file |
| `--preauth-error` | string | Most recent pre-authorisation error message |
| `--pre-auth-processed-on` | DateTime |  |
| `--last-charged-invoice` | int |  |
| `--last-charged-transaction` | int |  |
| `--last-charged-attendee` | int |  |
| `--passport-channels` | string | Passport channels this business is listed under |
| `--passport-only` | bool |  |
| `--passport-published` | bool | Whether this business is published and visible on Nexudus Passport |
| `--new-passport-banner-url` | string |  |
| `--clear-passport-banner-file` | bool |  |
| `--passport-name` | string | Display name shown on the Nexudus Passport listing |
| `--passport-tagline` | string | Tagline shown on the Nexudus Passport listing |
| `--venue-type` | enum | Type of venue (0 = default) |
| `--tags` | string | Comma-separated tags for categorising the business |
| `--floors` | int | Number of floors in the business premises |
| `--floor-space` | int | Total floor space of the business premises |
| `--floor-space-unit` | enum | Unit for FloorSpace (0 = default) |
| `--longitude` | decimal | Longitude coordinate for map positioning |
| `--latitude` | decimal | Latitude coordinate for map positioning |
| `--passport-description` | string | Full description shown on the Nexudus Passport listing |
| `--city` | string | Town or city where the business is located |
| `--state` | string | State or province where the business is located |
| `--postcode` | string | Postal or ZIP code |
| `--street-name` | string | Street name component of the address |
| `--street-number` | string | Street number component of the address |
| `--neighborhood` | string | Neighborhood or district name |
| `--contact-phone` | string | Secondary contact phone number |
| `--contact-email` | string | Secondary contact email address |
| `--passport-members` | enum | Passport members directory access level |
| `--passport-events` | enum | Passport events listing access level |
| `--passport-community` | enum | Passport community board access level |
| `--passport-blog` | enum | Passport blog posts access level |
| `--mon-open` | int | Monday opening time (minutes from midnight) |
| `--mon-close` | int | Monday closing time (minutes from midnight) |
| `--tue-open` | int | Tuesday opening time (minutes from midnight) |
| `--tue-close` | int | Tuesday closing time (minutes from midnight) |
| `--wed-open` | int | Wednesday opening time (minutes from midnight) |
| `--wed-close` | int | Wednesday closing time (minutes from midnight) |
| `--thu-open` | int | Thursday opening time (minutes from midnight) |
| `--thu-close` | int | Thursday closing time (minutes from midnight) |
| `--fri-open` | int | Friday opening time (minutes from midnight) |
| `--fri-close` | int | Friday closing time (minutes from midnight) |
| `--sat-open` | int | Saturday opening time (minutes from midnight) |
| `--sat-close` | int | Saturday closing time (minutes from midnight) |
| `--sun-open` | int | Sunday opening time (minutes from midnight) |
| `--sun-close` | int | Sunday closing time (minutes from midnight) |
| `--mon-closed` | bool | Whether the business is closed on Mondays |
| `--tue-closed` | bool | Whether the business is closed on Tuesdays |
| `--wed-closed` | bool | Whether the business is closed on Wednesdays |
| `--thu-closed` | bool | Whether the business is closed on Thursdays |
| `--fri-closed` | bool | Whether the business is closed on Fridays |
| `--sat-closed` | bool | Whether the business is closed on Saturdays |
| `--sun-closed` | bool | Whether the business is closed on Sundays |
| `--same-opening` | bool | Whether all days share the same opening and closing times |
| `--current-back-end-version` | int |  |
| `--authentication-provider` | string |  |
| `--created-by` | string |  |
| `--default-payment-term` | int |  |

#### Business PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--welcome-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--address` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--fax` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--last-welcome-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--state` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--contact-phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--contact-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus businesses update <id> --welcome-email "«PII:EMAIL:a3f2b1c9»" --agent`

### Business (key fields)

`Id`, `Name`, `WebAddress`, `Address`, `Phone`, `EmailContact`, `CountryName`, `CurrencyCode`, `PassportPublished`, `VenueType`, `Tags`, `TownCity`, `State`, `PostalCode`

<!-- END:GENERATED entity=Businesses -->
