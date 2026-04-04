# CoworkerDiscountCodes

<!-- BEGIN:GENERATED entity=CoworkerDiscountCodes -->

CoworkerDiscountCodes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdiscountcodes list --agent` | List all coworkerdiscountcodes |
| `nexudus coworkerdiscountcodes list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerdiscountcodes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerdiscountcodes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerdiscountcodes list --coworker-id <value> --business-id <value> --agent` | Filter coworkerdiscountcodes by properties |
| `nexudus coworkerdiscountcodes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerdiscountcodes get <id> --agent` | Get single coworkerdiscountcode |
| `nexudus coworkerdiscountcodes create --coworker-id <value> --business-id <value> --discount-code-id <value> --agent` | Create coworkerdiscountcode |
| `nexudus coworkerdiscountcodes update <id> --name "New Name" --agent` | Update coworkerdiscountcode |
| `nexudus coworkerdiscountcodes delete <id> --yes --agent` | Delete coworkerdiscountcode (no prompt) |

#### CoworkerDiscountCode list filter options

`--coworker-id`, `--business-id`, `--discount-code-id`, `--notes`, `--valid-from`, `--expires-on`, `--referer-guid`, `--booking-unique-id`

#### CoworkerDiscountCode create options

`--coworker-id` (required), `--business-id` (required), `--discount-code-id` (required), `--notes`, `--valid-from`, `--expires-on`, `--referer-guid`, `--booking-unique-id`

#### CoworkerDiscountCode update options

`--coworker-id`, `--business-id`, `--discount-code-id`, `--notes`, `--valid-from`, `--expires-on`, `--referer-guid`, `--booking-unique-id`

<!-- END:GENERATED entity=CoworkerDiscountCodes -->
