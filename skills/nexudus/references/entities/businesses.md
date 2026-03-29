# Businesses

<!-- BEGIN:GENERATED entity=Businesses -->

A **Business** represents an individual location or a group of locations in Nexudus. Most records in the system are connected — directly or via other records — to a business, which controls access and visibility based on the locations a user or customer can access.

Businesses can be organised into a hierarchy using `RootLocationId`, which references the parent business of a given business. A business with no `RootLocationId` is a top-level location. Child businesses inherit certain configuration from their parent.

Each business defines its own address, contact details, currency, opening hours, and public-facing content (Passport profile, website text, branding images). Read-only properties such as opening hours, theme, and image URLs reflect the current configuration set through the Nexudus admin UI.

Businesses support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus businesses list --agent` | List all businesses |
| `nexudus businesses list --query "search" --agent` | Search businesses by name |
| `nexudus businesses list --page 2 --size 10 --agent` | Paginated list |
| `nexudus businesses get <id> --agent` | Get single business |
| `nexudus businesses update <id> --name "New Name" --agent` | Update business |

#### Business update options

`--name`, `--address`, `--city`, `--state`, `--postcode`, `--country-id`, `--phone`, `--email`, `--website`, `--currency-id`, `--tags`, `--passport-published`, `--venue-type`, `--short-intro`, `--about`, `--quote`, `--terms`, `--web-contact`, `--privacy-url`, `--cookie-url`, `--street-name`, `--street-number`, `--neighborhood`, `--longitude`, `--latitude`, `--fax`, `--contact-phone`, `--contact-email`, `--timezone-id`, `--default-language`, `--floors`, `--floor-space`, `--floor-space-unit`, `--passport-name`, `--passport-tagline`, `--passport-description`

### Business (key fields)

`Id`, `Name`, `Address`, `TownCity`, `State`, `PostalCode`, `CountryName`, `Phone`, `EmailContact`, `WebAddress`, `CurrencyCode`, `Tags`, `PassportPublished`, `VenueType`

<!-- END:GENERATED entity=Businesses -->
