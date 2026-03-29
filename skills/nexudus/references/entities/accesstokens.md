# AccessTokens

<!-- BEGIN:GENERATED entity=AccessTokens -->

> **WiFi Access Tokens** provide unique network access codes for customers and visitors. They work alongside the Mikrotik, IronWifi, and Layer8 integrations. Access tokens can be shared with customers and visitors as part of visitor and booking confirmation emails. Each token includes a number of minutes of WiFi access and, optionally, an expiration date and user limit.

AccessTokens support Search, Get, Create, Update, Delete.
AccessTokens also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus accesstokens list --agent` | List all accesstokens |
| `nexudus accesstokens list --query "search" --agent` | Search accesstokens by name |
| `nexudus accesstokens list --page 2 --size 10 --agent` | Paginated list |
| `nexudus accesstokens get <id> --agent` | Get single accesstoken |
| `nexudus accesstokens create --business <value> --agent` | Create accesstoken |
| `nexudus accesstokens update <id> --name "New Name" --agent` | Update accesstoken |
| `nexudus accesstokens delete <id> --yes --agent` | Delete accesstoken (no prompt) |
| `nexudus accesstokens run-command <key> <ids> --agent` | Run entity command |

#### AccessToken create options

`--business` (required), `--access-code`, `--description`, `--minutes-included`, `--valid-from`, `--valid-to`, `--user-limit`, `--mac-address`

#### AccessToken update options

`--access-code`, `--description`, `--minutes-included`, `--valid-from`, `--valid-to`, `--user-limit`, `--mac-address`

### AccessToken (key fields)

`Id`, `BusinessId`, `AccessCode`, `MinutesIncluded`, `ValidFrom`, `ValidTo`, `MinutesLeft`

<!-- END:GENERATED entity=AccessTokens -->
