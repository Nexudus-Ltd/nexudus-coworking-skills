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
| `nexudus bookingproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus bookingproducts get <id> --agent` | Get single bookingproduct |
| `nexudus bookingproducts create --booking-id <value> --product-id <value> --quantity <value> --agent` | Create bookingproduct |
| `nexudus bookingproducts update <id> --name "New Name" --agent` | Update bookingproduct |
| `nexudus bookingproducts delete <id> --yes --agent` | Delete bookingproduct (no prompt) |
| `nexudus bookingproducts run-command <key> <ids> --agent` | Run entity command |

#### BookingProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long | ID of the booking linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--invoice-in-minutes` | bool | Whether to invoice this product based on the booking duration in minutes |
| `--quantity` | int | The number of units of this product to include in the booking |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BookingProduct sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BookingProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long, required | ID of the booking linked to this record |
| `--product-id` | long, required | ID of the product linked to this record |
| `--invoice-in-minutes` | bool | Whether to invoice this product based on the booking duration in minutes |
| `--quantity` | int, required | The number of units of this product to include in the booking |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |

#### BookingProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long | ID of the booking linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--invoice-in-minutes` | bool | Whether to invoice this product based on the booking duration in minutes |
| `--quantity` | int | The number of units of this product to include in the booking |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |

### BookingProduct (key fields)

`Id`, `ProductName`, `ProductPrice`, `Quantity`

<!-- END:GENERATED entity=BookingProducts -->
