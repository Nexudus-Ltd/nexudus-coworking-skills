# CoworkerTimePasses

<!-- BEGIN:GENERATED entity=CoworkerTimePasses -->

A customer pass (CoworkerTimePass) is an issued check-in allowance for a customer, tracking its remaining uses, use status, price, expiry, and invoicing status.

CoworkerTimePasses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkertimepasses list --agent` | List all coworkertimepasses |
| `nexudus coworkertimepasses list --id <id> --agent` | Filter by single ID |
| `nexudus coworkertimepasses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkertimepasses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkertimepasses list --coworker-id <value> --business-id <value> --agent` | Filter coworkertimepasses by properties |
| `nexudus coworkertimepasses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkertimepasses list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkertimepasses get <id> --agent` | Get single coworkertimepass |
| `nexudus coworkertimepasses create --coworker-id <value> --business-id <value> --time-pass-id <value> --create-multiple <value> --agent` | Create coworkertimepass |
| `nexudus coworkertimepasses update <id> --name "New Name" --agent` | Update coworkertimepass |
| `nexudus coworkertimepasses delete <id> --yes --agent` | Delete coworkertimepass (no prompt) |

#### CoworkerTimePass list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer assigned this pass |
| `--business-id` | long | ID of the location that owns this pass |
| `--time-pass-id` | long | ID of the pass definition to issue; it determines the included number of uses and default price |
| `--notes` | string | Optional internal notes about this issued pass |
| `--purchase-order` | string | Optional purchase-order reference for this pass |
| `--used` | bool | Whether the customer has used this pass; update-only operational status |
| `--free` | bool | Whether no charge is due for this issued pass; when true its calculated price is zero |
| `--price` | decimal | Optional monetary price override for this issued pass; when omitted, the selected pass calculates the price for the customer |
| `--from-price` | range | |
| `--to-price` | range | |
| `--create-multiple` | int | Number of identical passes to issue in this request, including this one; a customer cannot hold more than 500 passes |
| `--from-create-multiple` | range | |
| `--to-create-multiple` | range | |
| `--expire-date` | DateTime | Optional UTC expiration date and time; an expired pass is excluded from access-control updates |
| `--from-expire-date` | range | |
| `--to-expire-date` | range | |
| `--tariff-time-pass-unique-id` | string | Internal GUID linking this pass to the plan allocation that created it; do not set or use this field |
| `--coworker-product-unique-id` | string | Internal GUID linking this pass to the customer product purchase that created it; do not set or use this field |
| `--coworker-contract-unique-id` | string | Internal GUID linking this pass to the customer contract that created it; do not set or use this field |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerTimePass sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerTimePass create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer assigned this pass |
| `--business-id` | long, required | ID of the location that owns this pass |
| `--time-pass-id` | long, required | ID of the pass definition to issue; it determines the included number of uses and default price |
| `--notes` | string | Optional internal notes about this issued pass |
| `--purchase-order` | string | Optional purchase-order reference for this pass |
| `--used` | bool | Whether the customer has used this pass; update-only operational status |
| `--free` | bool | Whether no charge is due for this issued pass; when true its calculated price is zero |
| `--price` | decimal | Optional monetary price override for this issued pass; when omitted, the selected pass calculates the price for the customer |
| `--create-multiple` | int, required | Number of identical passes to issue in this request, including this one; a customer cannot hold more than 500 passes |
| `--expire-date` | DateTime | Optional UTC expiration date and time; an expired pass is excluded from access-control updates |
| `--tariff-time-pass-unique-id` | string | Internal GUID linking this pass to the plan allocation that created it; do not set or use this field |
| `--coworker-product-unique-id` | string | Internal GUID linking this pass to the customer product purchase that created it; do not set or use this field |
| `--coworker-contract-unique-id` | string | Internal GUID linking this pass to the customer contract that created it; do not set or use this field |

#### CoworkerTimePass update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer assigned this pass |
| `--business-id` | long | ID of the location that owns this pass |
| `--time-pass-id` | long | ID of the pass definition to issue; it determines the included number of uses and default price |
| `--notes` | string | Optional internal notes about this issued pass |
| `--purchase-order` | string | Optional purchase-order reference for this pass |
| `--used` | bool | Whether the customer has used this pass; update-only operational status |
| `--free` | bool | Whether no charge is due for this issued pass; when true its calculated price is zero |
| `--price` | decimal | Optional monetary price override for this issued pass; when omitted, the selected pass calculates the price for the customer |
| `--expire-date` | DateTime | Optional UTC expiration date and time; an expired pass is excluded from access-control updates |
| `--tariff-time-pass-unique-id` | string | Internal GUID linking this pass to the plan allocation that created it; do not set or use this field |
| `--coworker-product-unique-id` | string | Internal GUID linking this pass to the customer product purchase that created it; do not set or use this field |
| `--coworker-contract-unique-id` | string | Internal GUID linking this pass to the customer contract that created it; do not set or use this field |

#### CoworkerTimePass PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkertimepasses update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=CoworkerTimePasses -->
