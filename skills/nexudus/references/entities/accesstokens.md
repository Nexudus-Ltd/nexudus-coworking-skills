# AccessTokens

<!-- BEGIN:GENERATED entity=AccessTokens -->

> **WiFi Access Tokens** provide unique network access codes for customers and visitors. They work alongside the Mikrotik, IronWifi, and Layer8 integrations. Access tokens can be shared with customers and visitors as part of visitor and booking confirmation emails. Each token includes a number of minutes of WiFi access and, optionally, an expiration date and user limit.

AccessTokens support Search, Get, Create, Update, Delete.
AccessTokens also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus accesstokens list --agent` | List all accesstokens |
| `nexudus accesstokens list --id <id> --agent` | Filter by single ID |
| `nexudus accesstokens list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus accesstokens list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus accesstokens list --access-code <value> --minutes-included <value> --agent` | Filter accesstokens by properties |
| `nexudus accesstokens list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus accesstokens get <id> --agent` | Get single accesstoken |
| `nexudus accesstokens create --business-id <value> --access-code <value> --minutes-included <value> --agent` | Create accesstoken |
| `nexudus accesstokens update <id> --name "New Name" --agent` | Update accesstoken |
| `nexudus accesstokens delete <id> --yes --agent` | Delete accesstoken (no prompt) |
| `nexudus accesstokens run-command <key> <ids> --agent` | Run entity command |

#### AccessToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--access-code` | string | Unique network access code used to connect to WiFi |
| `--description` | string | Free-text description of this access token |
| `--minutes-included` | int | Total minutes of WiFi access included in this token |
| `--from-minutes-included` | range | |
| `--to-minutes-included` | range | |
| `--valid-from` | DateTime | Start date from which this token can be used |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--valid-to` | DateTime | Expiration date after which this token is no longer valid |
| `--from-valid-to` | range | |
| `--to-valid-to` | range | |
| `--user-limit` | int | Maximum number of users that can use this token simultaneously |
| `--from-user-limit` | range | |
| `--to-user-limit` | range | |
| `--mac-address` | string | MAC address of the device associated with this token |
| `--booking-guid` | string |  |
| `--visitor-guid` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AccessToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--access-code` | string, required | Unique network access code used to connect to WiFi |
| `--description` | string | Free-text description of this access token |
| `--minutes-included` | int, required | Total minutes of WiFi access included in this token |
| `--valid-from` | DateTime | Start date from which this token can be used |
| `--valid-to` | DateTime | Expiration date after which this token is no longer valid |
| `--user-limit` | int | Maximum number of users that can use this token simultaneously |
| `--mac-address` | string | MAC address of the device associated with this token |
| `--booking-guid` | string |  |
| `--visitor-guid` | string |  |

#### AccessToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--access-code` | string | Unique network access code used to connect to WiFi |
| `--description` | string | Free-text description of this access token |
| `--minutes-included` | int | Total minutes of WiFi access included in this token |
| `--valid-from` | DateTime | Start date from which this token can be used |
| `--valid-to` | DateTime | Expiration date after which this token is no longer valid |
| `--user-limit` | int | Maximum number of users that can use this token simultaneously |
| `--mac-address` | string | MAC address of the device associated with this token |
| `--booking-guid` | string |  |
| `--visitor-guid` | string |  |

### AccessToken (key fields)

`Id`, `AccessCode`, `MinutesIncluded`, `ValidFrom`, `ValidTo`, `MinutesLeft`

<!-- END:GENERATED entity=AccessTokens -->
