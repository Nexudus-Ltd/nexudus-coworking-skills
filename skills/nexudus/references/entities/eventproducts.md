# EventProducts

<!-- BEGIN:GENERATED entity=EventProducts -->

An **EventProduct** links a product to a calendar event, allowing products to be sold as part of event registration (e.g. event tickets, catering add-ons).

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

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--name` | string | The name value for this event product |
| `--description` | string | Free-text description of this event product |
| `--ticket-notes` | string | The ticket notes value for this event product |
| `--visible` | bool | Whether visible is enabled |
| `--display-order` | int | The display order value for this event product |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--start-date` | DateTime | Date/time value for start date |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--end-date` | DateTime | Date/time value for end date |
| `--from-end-date` | range | |
| `--to-end-date` | range | |
| `--allocation` | int | The allocation value for this event product |
| `--from-allocation` | range | |
| `--to-allocation` | range | |
| `--max-tickets-per-attendee` | int | The max tickets per attendee value for this event product |
| `--from-max-tickets-per-attendee` | range | |
| `--to-max-tickets-per-attendee` | range | |
| `--price` | decimal | Unit price amount |
| `--from-price` | range | |
| `--to-price` | range | |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long, required | ID of the calendar event linked to this record |
| `--name` | string, required | The name value for this event product |
| `--description` | string | Free-text description of this event product |
| `--ticket-notes` | string | The ticket notes value for this event product |
| `--visible` | bool | Whether visible is enabled |
| `--display-order` | int, required | The display order value for this event product |
| `--start-date` | DateTime, required | Date/time value for start date |
| `--end-date` | DateTime, required | Date/time value for end date |
| `--allocation` | int | The allocation value for this event product |
| `--max-tickets-per-attendee` | int | The max tickets per attendee value for this event product |
| `--price` | decimal, required | Unit price amount |
| `--currency-id` | long, required | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this event product |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this event product |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |

#### EventProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--name` | string | The name value for this event product |
| `--description` | string | Free-text description of this event product |
| `--ticket-notes` | string | The ticket notes value for this event product |
| `--visible` | bool | Whether visible is enabled |
| `--display-order` | int | The display order value for this event product |
| `--start-date` | DateTime | Date/time value for start date |
| `--end-date` | DateTime | Date/time value for end date |
| `--allocation` | int | The allocation value for this event product |
| `--max-tickets-per-attendee` | int | The max tickets per attendee value for this event product |
| `--price` | decimal | Unit price amount |
| `--currency-id` | long | ID of the currency linked to this record |
| `--tax-rate-id` | long | ID of the tax rate linked to this record |
| `--financial-account-id` | long | ID of the financial account linked to this record |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this event product |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this event product |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=EventProducts -->
