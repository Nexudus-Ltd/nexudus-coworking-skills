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
| `nexudus businesscharges get <id> --agent` | Get single businesscharge |
| `nexudus businesscharges create --business-id <value> --description <value> --callback-url <value> --percentage-discount <value> --total-amount <value> --tax-amount <value> --agent` | Create businesscharge |
| `nexudus businesscharges update <id> --name "New Name" --agent` | Update businesscharge |
| `nexudus businesscharges delete <id> --yes --agent` | Delete businesscharge (no prompt) |

#### BusinessCharge list filter options

`--business-id`, `--application-id`, `--description`, `--callback-url`, `--due-date`, `--from-due-date` (range), `--to-due-date` (range), `--percentage-discount`, `--from-percentage-discount` (range), `--to-percentage-discount` (range), `--total-amount`, `--from-total-amount` (range), `--to-total-amount` (range), `--tax-amount`, `--from-tax-amount` (range), `--to-tax-amount` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BusinessCharge create options

`--business-id` (required), `--application-id`, `--description` (required), `--callback-url` (required), `--due-date`, `--percentage-discount` (required), `--total-amount` (required), `--tax-amount` (required)

#### BusinessCharge update options

`--business-id`, `--application-id`, `--callback-url`

### BusinessCharge (key fields)

`Id`, `Description`, `TotalAmount`, `Invoiced`

<!-- END:GENERATED entity=BusinessCharges -->
