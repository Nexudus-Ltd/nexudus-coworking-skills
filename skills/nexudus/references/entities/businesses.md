# Businesses

<!-- BEGIN:GENERATED entity=Businesses -->

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
