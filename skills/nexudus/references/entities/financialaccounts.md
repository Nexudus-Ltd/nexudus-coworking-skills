# FinancialAccounts

<!-- BEGIN:GENERATED entity=FinancialAccounts -->

A **FinancialAccount** represents a bookkeeping account used for categorising revenue and payments.

Financial accounts can be assigned to Products, EventProducts, TimePasses, ExtraServices (resource prices), Tariffs and Charges to control how income is tracked and reported.

Each account has a `Code` (typically matching an external accounting system reference), a `Name`, and an `AccountType` that determines where it appears:

| AccountType | Value | Purpose |
| ----------- | ----- | ------- |
| Sales       | 1     | Revenue from products, services and bookings |
| Payments    | 2     | Incoming payment receipts |
| Deposits    | 3     | Security deposits held against contracts |

**Important:** Changing a financial account's details or reassigning it to different items has no effect on existing invoices. The financial account recorded on each invoice line is captured at the time the invoice is issued and is never updated retroactively.

FinancialAccounts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus financialaccounts list --agent` | List all financialaccounts |
| `nexudus financialaccounts list --id <id> --agent` | Filter by single ID |
| `nexudus financialaccounts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus financialaccounts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus financialaccounts list --name <value> --code <value> --agent` | Filter financialaccounts by properties |
| `nexudus financialaccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus financialaccounts get <id> --agent` | Get single financialaccount |
| `nexudus financialaccounts create --business-id <value> --name <value> --code <value> --account-type <value> --agent` | Create financialaccount |
| `nexudus financialaccounts update <id> --name "New Name" --agent` | Update financialaccount |
| `nexudus financialaccounts delete <id> --yes --agent` | Delete financialaccount (no prompt) |

#### FinancialAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Display name for this financial account |
| `--code` | string | Short reference code, typically matching the account code in an external accounting system |
| `--description` | string | Optional free-text description of the account's purpose |
| `--account-type` | enum | Category of the account: Sales (1), Payments (2) or Deposits (3) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FinancialAccount create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required | Display name for this financial account |
| `--code` | string, required | Short reference code, typically matching the account code in an external accounting system |
| `--description` | string | Optional free-text description of the account's purpose |
| `--account-type` | enum, required | Category of the account: Sales (1), Payments (2) or Deposits (3) |

#### FinancialAccount update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Display name for this financial account |
| `--code` | string | Short reference code, typically matching the account code in an external accounting system |
| `--description` | string | Optional free-text description of the account's purpose |
| `--account-type` | enum | Category of the account: Sales (1), Payments (2) or Deposits (3) |

### FinancialAccount (key fields)

`Id`, `Name`, `Code`, `AccountType`

#### FinancialAccount enum values

| Option | Valid values |
| ------ | ------------ |
| `--account-type` | `0` None, `1` Sales, `2` Payments, `3` Deposits |

<!-- END:GENERATED entity=FinancialAccounts -->
