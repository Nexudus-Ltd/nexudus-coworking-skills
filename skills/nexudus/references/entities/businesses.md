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

`--visited-help-items`, `--name`, `--default-language`, `--space-website-language-id`, `--website`, `--default-payment-gateway-id`, `--terms`, `--short-intro`, `--about`, `--quote`, `--privacy-url`, `--cookie-url`, `--web-contact`, `--welcome-email`, `--address`, `--phone`, `--fax`, `--email`, `--trial-expire-date`, `--last-over-due-invoice-reminder`, `--last-welcome-email`, `--country-id`, `--currency-id`, `--simple-time-zone-id`, `--new-logo-url`, `--clear-logo`, `--new-banner-image-url`, `--clear-banner-image`, `--new-nex-io-banner-image-url`, `--clear-nex-io-banner-image`, `--discount-percentage`, `--discount-amount`, `--last-language-token-update`, `--has-created-default-file-templates`, `--invoicing-period`, `--suspended`, `--custom-passport-app`, `--reminders-processed-on`, `--pre-auth-id`, `--last4`, `--preauth-error`, `--pre-auth-processed-on`, `--last-charged-invoice`, `--last-charged-transaction`, `--last-charged-attendee`, `--passport-channels`, `--passport-only`, `--passport-published`, `--new-passport-banner-url`, `--clear-passport-banner`, `--passport-name`, `--passport-tagline`, `--venue-type`, `--tags`, `--floors`, `--floor-space`, `--floor-space-unit`, `--longitude`, `--latitude`, `--passport-description`, `--city`, `--state`, `--postcode`, `--street-name`, `--street-number`, `--neighborhood`, `--contact-phone`, `--contact-email`, `--passport-members`, `--passport-events`, `--passport-community`, `--passport-blog`, `--mon-open`, `--mon-close`, `--tue-open`, `--tue-close`, `--wed-open`, `--wed-close`, `--thu-open`, `--thu-close`, `--fri-open`, `--fri-close`, `--sat-open`, `--sat-close`, `--sun-open`, `--sun-close`, `--mon-closed`, `--tue-closed`, `--wed-closed`, `--thu-closed`, `--fri-closed`, `--sat-closed`, `--sun-closed`, `--same-opening`, `--current-back-end-version`, `--authentication-provider`, `--created-by`, `--default-payment-term`

#### Business update options

`--visited-help-items`, `--name`, `--default-language`, `--space-website-language-id`, `--website`, `--default-payment-gateway-id`, `--terms`, `--short-intro`, `--about`, `--quote`, `--privacy-url`, `--cookie-url`, `--web-contact`, `--welcome-email`, `--address`, `--phone`, `--fax`, `--email`, `--trial-expire-date`, `--last-over-due-invoice-reminder`, `--last-welcome-email`, `--country-id`, `--currency-id`, `--simple-time-zone-id`, `--new-logo-url`, `--clear-logo`, `--new-banner-image-url`, `--clear-banner-image`, `--new-nex-io-banner-image-url`, `--clear-nex-io-banner-image`, `--discount-percentage`, `--discount-amount`, `--last-language-token-update`, `--invoices` (list, repeat flag), `--added-invoices` (list, repeat flag), `--removed-invoices` (list, repeat flag), `--languages` (list, repeat flag), `--added-languages` (list, repeat flag), `--removed-languages` (list, repeat flag), `--businesses` (list, repeat flag), `--added-businesses` (list, repeat flag), `--removed-businesses` (list, repeat flag), `--apps` (list, repeat flag), `--added-apps` (list, repeat flag), `--removed-apps` (list, repeat flag), `--has-created-default-file-templates`, `--additional-domains` (list, repeat flag), `--added-additional-domains` (list, repeat flag), `--removed-additional-domains` (list, repeat flag), `--invoicing-period`, `--suspended`, `--custom-passport-app`, `--reminders-processed-on`, `--pre-auth-id`, `--last4`, `--preauth-error`, `--pre-auth-processed-on`, `--last-charged-invoice`, `--last-charged-transaction`, `--last-charged-attendee`, `--added-settings` (list, repeat flag), `--removed-settings` (list, repeat flag), `--passport-channels`, `--passport-only`, `--passport-published`, `--new-passport-banner-url`, `--clear-passport-banner`, `--passport-name`, `--passport-tagline`, `--venue-type`, `--tags`, `--floors`, `--floor-space`, `--floor-space-unit`, `--longitude`, `--latitude`, `--passport-description`, `--city`, `--state`, `--postcode`, `--street-name`, `--street-number`, `--neighborhood`, `--contact-phone`, `--contact-email`, `--passport-members`, `--passport-events`, `--passport-community`, `--passport-blog`, `--time-slots` (list, repeat flag), `--added-time-slots` (list, repeat flag), `--removed-time-slots` (list, repeat flag), `--mon-open`, `--mon-close`, `--tue-open`, `--tue-close`, `--wed-open`, `--wed-close`, `--thu-open`, `--thu-close`, `--fri-open`, `--fri-close`, `--sat-open`, `--sat-close`, `--sun-open`, `--sun-close`, `--mon-closed`, `--tue-closed`, `--wed-closed`, `--thu-closed`, `--fri-closed`, `--sat-closed`, `--sun-closed`, `--same-opening`, `--current-back-end-version`, `--authentication-provider`, `--created-by`, `--default-payment-term`

### Business (key fields)

`Id`, `Name`, `WebAddress`, `Address`, `Phone`, `EmailContact`, `CountryName`, `CurrencyCode`, `PassportPublished`, `VenueType`, `Tags`, `TownCity`, `State`, `PostalCode`

**List properties (only returned by `get`, not by `list`):** `Invoices`, `AddedInvoices`, `RemovedInvoices`, `Languages`, `AddedLanguages`, `RemovedLanguages`, `Businesses`, `AddedBusinesses`, `RemovedBusinesses`, `Apps`, `AddedApps`, `RemovedApps`, `AdditionalDomains`, `AddedAdditionalDomains`, `RemovedAdditionalDomains`, `AddedSettings`, `RemovedSettings`, `TimeSlots`, `AddedTimeSlots`, `RemovedTimeSlots`

<!-- END:GENERATED entity=Businesses -->
