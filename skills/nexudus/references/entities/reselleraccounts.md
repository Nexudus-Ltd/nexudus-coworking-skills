# ResellerAccounts

<!-- BEGIN:GENERATED entity=ResellerAccounts -->

A **ResellerAccount** represents the financial account associated with a reseller, tracking commissions, payouts, and billing between Nexudus and the reseller partner.

ResellerAccounts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reselleraccounts list --agent` | List all reselleraccounts |
| `nexudus reselleraccounts list --id <id> --agent` | Filter by single ID |
| `nexudus reselleraccounts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reselleraccounts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reselleraccounts list --notes <value> --scope-of-work <value> --agent` | Filter reselleraccounts by properties |
| `nexudus reselleraccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reselleraccounts get <id> --agent` | Get single reselleraccount |
| `nexudus reselleraccounts create  --agent` | Create reselleraccount |
| `nexudus reselleraccounts update <id> --name "New Name" --agent` | Update reselleraccount |
| `nexudus reselleraccounts delete <id> --yes --agent` | Delete reselleraccount (no prompt) |

#### ResellerAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string | Optional notes or comments about this reseller account |
| `--scope-of-work` | string | The scope of work value for this reseller account |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResellerAccount create options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string | Optional notes or comments about this reseller account |
| `--scope-of-work` | string | The scope of work value for this reseller account |

#### ResellerAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string | Optional notes or comments about this reseller account |
| `--scope-of-work` | string | The scope of work value for this reseller account |

#### ResellerAccount PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus reselleraccounts update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=ResellerAccounts -->
