# AccessTokens

<!-- BEGIN:GENERATED entity=AccessTokens -->

WiFi access tokens are location-scoped network access codes for customers, visitors, bookings, and events, with a WiFi-minute allowance and optional validity window or user limit.

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
| `nexudus accesstokens list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus accesstokens get <id> --agent` | Get single accesstoken |
| `nexudus accesstokens create --business-id <value> --access-code <value> --minutes-included <value> --agent` | Create accesstoken |
| `nexudus accesstokens update <id> --name "New Name" --agent` | Update accesstoken |
| `nexudus accesstokens delete <id> --yes --agent` | Delete accesstoken (no prompt) |
| `nexudus accesstokens run-command <key> <ids> --agent` | Run entity command |

#### AccessToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this WiFi access token. |
| `--access-code` | string | Required unique code used to authenticate to the location's WiFi network. |
| `--description` | string | Optional operator-facing label, such as the related visitor, booking, or event. |
| `--minutes-included` | int | Non-negative total number of WiFi minutes granted when the token is created. |
| `--from-minutes-included` | range | |
| `--to-minutes-included` | range | |
| `--valid-from` | DateTime | Optional UTC date and time after which the token can be used; no value allows use immediately. |
| `--from-valid-from` | range | |
| `--to-valid-from` | range | |
| `--valid-to` | DateTime | Optional UTC expiration date and time; no value means the token does not expire by date. |
| `--from-valid-to` | range | |
| `--to-valid-to` | range | |
| `--user-limit` | int | Optional minimum-one limit on users or devices permitted by the WiFi integration. |
| `--from-user-limit` | range | |
| `--to-user-limit` | range | |
| `--minutes-left` | int | Read-only remaining WiFi minutes, initialized from MinutesIncluded when the token is created and reduced by network use. |
| `--from-minutes-left` | range | |
| `--to-minutes-left` | range | |
| `--mac-address` | string | Optional comma-separated list of device MAC addresses associated with this token; stored in lowercase. |
| `--booking-guid` | string | Internal GUID linking this token to the booking that created it; set by booking automation, not by operators. |
| `--visitor-guid` | string | Internal GUID linking this token to the visitor that created it; set by visitor automation, not by operators. |
| `--last-access` | DateTime | Read-only UTC date and time when the token last accessed the WiFi network. |
| `--from-last-access` | range | |
| `--to-last-access` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AccessToken sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AccessToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this WiFi access token. |
| `--access-code` | string, required | Required unique code used to authenticate to the location's WiFi network. |
| `--description` | string | Optional operator-facing label, such as the related visitor, booking, or event. |
| `--minutes-included` | int, required | Non-negative total number of WiFi minutes granted when the token is created. |
| `--valid-from` | DateTime | Optional UTC date and time after which the token can be used; no value allows use immediately. |
| `--valid-to` | DateTime | Optional UTC expiration date and time; no value means the token does not expire by date. |
| `--user-limit` | int | Optional minimum-one limit on users or devices permitted by the WiFi integration. |
| `--mac-address` | string | Optional comma-separated list of device MAC addresses associated with this token; stored in lowercase. |
| `--booking-guid` | string | Internal GUID linking this token to the booking that created it; set by booking automation, not by operators. |
| `--visitor-guid` | string | Internal GUID linking this token to the visitor that created it; set by visitor automation, not by operators. |

#### AccessToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this WiFi access token. |
| `--access-code` | string | Required unique code used to authenticate to the location's WiFi network. |
| `--description` | string | Optional operator-facing label, such as the related visitor, booking, or event. |
| `--minutes-included` | int | Non-negative total number of WiFi minutes granted when the token is created. |
| `--valid-from` | DateTime | Optional UTC date and time after which the token can be used; no value allows use immediately. |
| `--valid-to` | DateTime | Optional UTC expiration date and time; no value means the token does not expire by date. |
| `--user-limit` | int | Optional minimum-one limit on users or devices permitted by the WiFi integration. |
| `--mac-address` | string | Optional comma-separated list of device MAC addresses associated with this token; stored in lowercase. |
| `--booking-guid` | string | Internal GUID linking this token to the booking that created it; set by booking automation, not by operators. |
| `--visitor-guid` | string | Internal GUID linking this token to the visitor that created it; set by visitor automation, not by operators. |

### AccessToken (key fields)

`Id`, `AccessCode`, `MinutesIncluded`, `ValidFrom`, `ValidTo`, `MinutesLeft`

<!-- END:GENERATED entity=AccessTokens -->
