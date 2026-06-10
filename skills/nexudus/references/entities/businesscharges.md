# BusinessCharges

<!-- BEGIN:GENERATED entity=BusinessCharges -->

A **BusinessCharge** represents a charge issued by Nexudus to a specific location for platform services or subscription fees. Only Nexudus staff can create or manage these charges.

Charges can be one-off or recurring. Set `--recurrent` to `true` and provide `--repeat-from` and `--repeat-until` to define the recurrence window.

A charge moves through an approval workflow before it is invoiced. Use `--approved-by-business` and `--approved-by-sender` to reflect the approval state. Once invoiced, the `--invoiced` flag will be set and `--invoiced-on` will record the date.

BusinessCharges support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus businesscharges list --agent` | List all businesscharges |
| `nexudus businesscharges list --id <id> --agent` | Filter by single ID |
| `nexudus businesscharges list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businesscharges list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businesscharges list --description <value> --total-amount <value> --agent` | Filter businesscharges by properties |
| `nexudus businesscharges list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businesscharges list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus businesscharges get <id> --agent` | Get single businesscharge |
| `nexudus businesscharges create --business-id <value> --description <value> --callback-url <value> --percentage-discount <value> --total-amount <value> --tax-amount <value> --agent` | Create businesscharge |
| `nexudus businesscharges update <id> --name "New Name" --agent` | Update businesscharge |
| `nexudus businesscharges delete <id> --yes --agent` | Delete businesscharge (no prompt) |

#### BusinessCharge list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--application-id` | long | ID of the application linked to this record |
| `--description` | string | Human-readable description of what this charge is for |
| `--callback-url` | string | URL that Nexudus will call back once the charge is processed or its status changes |
| `--due-date` | DateTime | Date by which the charge must be paid |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--percentage-discount` | decimal | Percentage discount to apply to the charge amount (0–100) |
| `--from-percentage-discount` | range | |
| `--to-percentage-discount` | range | |
| `--total-amount` | decimal | Total amount of the charge before tax |
| `--from-total-amount` | range | |
| `--to-total-amount` | range | |
| `--tax-amount` | decimal | Tax amount applied to this charge |
| `--from-tax-amount` | range | |
| `--to-tax-amount` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BusinessCharge sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BusinessCharge create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--application-id` | long | ID of the application linked to this record |
| `--description` | string, required | Human-readable description of what this charge is for |
| `--callback-url` | string, required | URL that Nexudus will call back once the charge is processed or its status changes |
| `--due-date` | DateTime | Date by which the charge must be paid |
| `--percentage-discount` | decimal, required | Percentage discount to apply to the charge amount (0–100) |
| `--total-amount` | decimal, required | Total amount of the charge before tax |
| `--tax-amount` | decimal, required | Tax amount applied to this charge |

#### BusinessCharge update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--application-id` | long | ID of the application linked to this record |
| `--callback-url` | string | URL that Nexudus will call back once the charge is processed or its status changes |

### BusinessCharge (key fields)

`Id`, `Description`, `TotalAmount`, `Invoiced`

<!-- END:GENERATED entity=BusinessCharges -->
