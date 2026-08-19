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
| `nexudus reselleraccounts list --reseller-id <value> --reseller-currency-id <value> --agent` | Filter reselleraccounts by properties |
| `nexudus reselleraccounts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reselleraccounts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus reselleraccounts get <id> --agent` | Get single reselleraccount |
| `nexudus reselleraccounts create  --agent` | Create reselleraccount |
| `nexudus reselleraccounts update <id> --name "New Name" --agent` | Update reselleraccount |
| `nexudus reselleraccounts delete <id> --yes --agent` | Delete reselleraccount (no prompt) |

#### ResellerAccount list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--reseller-id` | long | ID of the reseller linked to this record |
| `--reseller-currency-id` | int | ID of the reseller currency associated with this record |
| `--from-reseller-currency-id` | range | |
| `--to-reseller-currency-id` | range | |
| `--reseller-currency-code` | string | The reseller currency code value for this reseller account |
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--business-pre-auth-id` | string | ID of the business pre auth associated with this record |
| `--business-last4-digits` | string | The business last4 digits value for this reseller account |
| `--business-pre-auth-last-error` | string | The business pre auth last error value for this reseller account |
| `--business-suspended` | bool | Whether business suspended is enabled |
| `--business-next-invoice` | DateTime | Date/time value for business next invoice |
| `--from-business-next-invoice` | range | |
| `--to-business-next-invoice` | range | |
| `--business-trial-expire-date` | DateTime | Date/time value for business trial expire date |
| `--from-business-trial-expire-date` | range | |
| `--to-business-trial-expire-date` | range | |
| `--business-support-tier` | string | The business support tier value for this reseller account |
| `--business-on-boarding-tier` | string | The business on boarding tier value for this reseller account |
| `--approved` | bool | Whether approved is enabled |
| `--comission-percentage` | decimal | The comission percentage value for this reseller account |
| `--from-comission-percentage` | range | |
| `--to-comission-percentage` | range | |
| `--next-payout-date` | DateTime | Date/time value for next payout date |
| `--from-next-payout-date` | range | |
| `--to-next-payout-date` | range | |
| `--expiration-date` | DateTime | Date/time value for expiration date |
| `--from-expiration-date` | range | |
| `--to-expiration-date` | range | |
| `--last-access` | DateTime | Date/time value for last access |
| `--from-last-access` | range | |
| `--to-last-access` | range | |
| `--last-invoice-amount` | decimal | The last invoice amount value for this reseller account |
| `--from-last-invoice-amount` | range | |
| `--to-last-invoice-amount` | range | |
| `--average-invoice-amount` | decimal | The average invoice amount value for this reseller account |
| `--from-average-invoice-amount` | range | |
| `--to-average-invoice-amount` | range | |
| `--can-manage-account` | bool | Whether can manage account is enabled |
| `--provides-first-line-support` | bool | Whether provides first line support is enabled |
| `--notes` | string | Optional notes or comments about this reseller account |
| `--scope-of-work` | string | The scope of work value for this reseller account |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResellerAccount sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

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
