# BookingProducts

<!-- BEGIN:GENERATED entity=BookingProducts -->

A **BookingProduct** links a `Product` to a `Booking`. Only products that are associated with the resource being booked (via `ResourceProduct`) can be used.

For example, if a meeting room resource has a "Catering" product linked through `ResourceProduct`, that product can be added to bookings for that room as a `BookingProduct`.

BookingProducts support Search, Get, Create, Update, Delete.
BookingProducts also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookingproducts list --agent` | List all bookingproducts |
| `nexudus bookingproducts list --id <id> --agent` | Filter by single ID |
| `nexudus bookingproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus bookingproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus bookingproducts list --quantity <value> --agent` | Filter bookingproducts by properties |
| `nexudus bookingproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus bookingproducts get <id> --agent` | Get single bookingproduct |
| `nexudus bookingproducts create --booking-id <value> --product-id <value> --quantity <value> --agent` | Create bookingproduct |
| `nexudus bookingproducts update <id> --name "New Name" --agent` | Update bookingproduct |
| `nexudus bookingproducts delete <id> --yes --agent` | Delete bookingproduct (no prompt) |
| `nexudus bookingproducts run-command <key> <ids> --agent` | Run entity command |

#### BookingProduct list filter options

`--booking-id` (long), `--product-id` (long), `--invoice-in-minutes` (bool), `--quantity` (int), `--from-quantity` (range), `--to-quantity` (range), `--mrm-reminded` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BookingProduct create options

`--booking-id` (long, required), `--product-id` (long, required), `--invoice-in-minutes` (bool), `--quantity` (int, required), `--mrm-reminded` (bool)

#### BookingProduct update options

`--booking-id` (long), `--product-id` (long), `--invoice-in-minutes` (bool), `--quantity` (int), `--mrm-reminded` (bool)

### BookingProduct (key fields)

`Id`, `ProductName`, `ProductPrice`, `Quantity`

<!-- END:GENERATED entity=BookingProducts -->
