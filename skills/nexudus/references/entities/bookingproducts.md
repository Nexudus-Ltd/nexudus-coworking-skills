# BookingProducts

<!-- BEGIN:GENERATED entity=BookingProducts -->

A **BookingProduct** links a `Product` to a `Booking`. Only products that are associated with the resource being booked (via `ResourceProduct`) can be used.

For example, if a meeting room resource has a "Catering" product linked through `ResourceProduct`, that product can be added to bookings for that room as a `BookingProduct`.

BookingProducts support Search, Get, Create, Update, Delete.
BookingProducts also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookingproducts list --agent` | List all bookingproducts |
| `nexudus bookingproducts list --query "search" --agent` | Search bookingproducts by name |
| `nexudus bookingproducts list --page 2 --size 10 --agent` | Paginated list |
| `nexudus bookingproducts get <id> --agent` | Get single bookingproduct |
| `nexudus bookingproducts create --booking-id <value> --product-id <value> --agent` | Create bookingproduct |
| `nexudus bookingproducts update <id> --name "New Name" --agent` | Update bookingproduct |
| `nexudus bookingproducts delete <id> --yes --agent` | Delete bookingproduct (no prompt) |
| `nexudus bookingproducts run-command <key> <ids> --agent` | Run entity command |

#### BookingProduct create options

`--booking-id` (required), `--product-id` (required), `--invoice-in-minutes`, `--quantity`

#### BookingProduct update options

`--booking-id`, `--product-id`, `--invoice-in-minutes`, `--quantity`

### BookingProduct (key fields)

`Id`, `BookingId`, `ProductId`, `ProductName`, `ProductPrice`, `Quantity`

<!-- END:GENERATED entity=BookingProducts -->
