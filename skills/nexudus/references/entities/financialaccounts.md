# FinancialAccounts

<!-- BEGIN:GENERATED entity=FinancialAccounts -->

A financial account is a location-specific bookkeeping category used to track revenue, incoming payments, or security deposits when it is assigned to items and services sold by the location. Issued invoice lines retain a snapshot of the account's code and name, so later changes to or deletion of the account do not alter them.

FinancialAccounts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus financialaccounts list --agent` | List all financialaccounts |
| `nexudus financialaccounts list --id <id> --agent` | Filter by single ID |
| `nexudus financialaccounts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus financialaccounts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus financialaccounts list --name <value> --code <value> --agent` | Filter financialaccounts by properties |
| `nexudus financialaccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus financialaccounts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus financialaccounts get <id> --agent` | Get single financialaccount |
| `nexudus financialaccounts create --business-id <value> --name <value> --code <value> --account-type <value> --agent` | Create financialaccount |
| `nexudus financialaccounts update <id> --name "New Name" --agent` | Update financialaccount |
| `nexudus financialaccounts delete <id> --yes --agent` | Delete financialaccount (no prompt) |

#### FinancialAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this financial account. |
| `--name` | string | Required display name for this financial account, up to 150 characters. |
| `--code` | string | Required accounting reference code, up to 50 characters and unique within the location; it can match an external accounting system's account code. |
| `--description` | string | Optional free-text explanation of this account's purpose, up to 254 characters. |
| `--account-type` | enum | Category that controls the account's use: Sales (1) for revenue, Payments (2) for incoming payments, or Deposits (3) for security deposits; defaults to Sales. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FinancialAccount sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FinancialAccount create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this financial account. |
| `--name` | string, required | Required display name for this financial account, up to 150 characters. |
| `--code` | string, required | Required accounting reference code, up to 50 characters and unique within the location; it can match an external accounting system's account code. |
| `--description` | string | Optional free-text explanation of this account's purpose, up to 254 characters. |
| `--account-type` | enum, required | Category that controls the account's use: Sales (1) for revenue, Payments (2) for incoming payments, or Deposits (3) for security deposits; defaults to Sales. |

#### FinancialAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this financial account. |
| `--name` | string | Required display name for this financial account, up to 150 characters. |
| `--code` | string | Required accounting reference code, up to 50 characters and unique within the location; it can match an external accounting system's account code. |
| `--description` | string | Optional free-text explanation of this account's purpose, up to 254 characters. |
| `--account-type` | enum | Category that controls the account's use: Sales (1) for revenue, Payments (2) for incoming payments, or Deposits (3) for security deposits; defaults to Sales. |

### FinancialAccount (key fields)

`Id`, `Name`, `Code`, `AccountType`

#### FinancialAccount enum values

| Option | Valid values |
| ------ | ------------ |
| `--account-type` | `1` Sales, `2` Payments, `3` Deposits |

<!-- END:GENERATED entity=FinancialAccounts -->
