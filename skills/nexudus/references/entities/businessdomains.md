# BusinessDomains

<!-- BEGIN:GENERATED entity=BusinessDomains -->

A **BusinessDomain** represents a custom domain or subdomain configured for a location's Members Portal.

By default each location gets a `<name>.spaces.nexudus.com` address. A BusinessDomain lets you replace that with your own domain (e.g. `coworking.com`) or subdomain (e.g. `london.coworking.com`).

- For custom **domains**, an SSL proxy (e.g. CloudFlare) must be configured and `SslProxy` must be set to `true`.
- For custom **subdomains**, a CNAME record pointing to Nexudus is required. `SslProxy` must still be set to `true`.

Use `ActiveFrom` and `ActiveTo` to schedule when the domain mapping takes effect. Changes typically propagate within two to three days.

BusinessDomains support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businessdomains list --agent` | List all businessdomains |
| `nexudus businessdomains list --id <id> --agent` | Filter by single ID |
| `nexudus businessdomains list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businessdomains list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businessdomains list --name <value> --domain-url <value> --agent` | Filter businessdomains by properties |
| `nexudus businessdomains list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businessdomains get <id> --agent` | Get single businessdomain |
| `nexudus businessdomains create --business-id <value> --name <value> --domain-url <value> --agent` | Create businessdomain |
| `nexudus businessdomains update <id> --name "New Name" --agent` | Update businessdomain |
| `nexudus businessdomains delete <id> --yes --agent` | Delete businessdomain (no prompt) |

#### BusinessDomain list filter options

`--business-id`, `--name`, `--domain-url`, `--active`, `--ssl-proxy`, `--active-from`, `--from-active-from` (range), `--to-active-from` (range), `--active-to`, `--from-active-to` (range), `--to-active-to` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BusinessDomain create options

`--business-id` (required), `--name` (required), `--domain-url` (required), `--active`, `--ssl-proxy`, `--active-from`, `--active-to`

#### BusinessDomain update options

`--business-id`, `--name`, `--domain-url`, `--active`, `--ssl-proxy`, `--active-from`, `--active-to`

### BusinessDomain (key fields)

`Id`, `Name`, `DomainURL`, `Active`

<!-- END:GENERATED entity=BusinessDomains -->
