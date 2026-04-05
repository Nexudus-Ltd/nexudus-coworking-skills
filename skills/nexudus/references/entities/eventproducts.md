# EventProducts

<!-- BEGIN:GENERATED entity=EventProducts -->

EventProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventproducts list --agent` | List all eventproducts |
| `nexudus eventproducts list --id <id> --agent` | Filter by single ID |
| `nexudus eventproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventproducts list --calendar-event-id <value> --name <value> --agent` | Filter eventproducts by properties |
| `nexudus eventproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventproducts get <id> --agent` | Get single eventproduct |
| `nexudus eventproducts create --calendar-event-id <value> --name <value> --display-order <value> --start-date <value> --end-date <value> --price <value> --currency-id <value> --agent` | Create eventproduct |
| `nexudus eventproducts update <id> --name "New Name" --agent` | Update eventproduct |
| `nexudus eventproducts delete <id> --yes --agent` | Delete eventproduct (no prompt) |

#### EventProduct list filter options

`--calendar-event-id`, `--name`, `--description`, `--ticket-notes`, `--visible`, `--display-order`, `--from-display-order` (range), `--to-display-order` (range), `--start-date`, `--from-start-date` (range), `--to-start-date` (range), `--end-date`, `--from-end-date` (range), `--to-end-date` (range), `--allocation`, `--from-allocation` (range), `--to-allocation` (range), `--max-tickets-per-attendee`, `--from-max-tickets-per-attendee` (range), `--to-max-tickets-per-attendee` (range), `--price`, `--from-price` (range), `--to-price` (range), `--currency-id`, `--tax-rate-id`, `--financial-account-id`, `--only-for-contacts`, `--only-for-members`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EventProduct create options

`--calendar-event-id` (required), `--name` (required), `--description`, `--ticket-notes`, `--visible`, `--display-order` (required), `--start-date` (required), `--end-date` (required), `--allocation`, `--max-tickets-per-attendee`, `--price` (required), `--currency-id` (required), `--tax-rate-id`, `--financial-account-id`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--only-for-contacts`, `--only-for-members`

#### EventProduct update options

`--calendar-event-id`, `--name`, `--description`, `--ticket-notes`, `--visible`, `--display-order`, `--start-date`, `--end-date`, `--allocation`, `--max-tickets-per-attendee`, `--price`, `--currency-id`, `--tax-rate-id`, `--financial-account-id`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--only-for-contacts`, `--only-for-members`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=EventProducts -->
