# CancelledBookings

<!-- BEGIN:GENERATED entity=CancelledBookings -->

CancelledBookings support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus cancelledbookings list --agent` | List all cancelledbookings |
| `nexudus cancelledbookings list --query "search" --agent` | Search cancelledbookings by name |
| `nexudus cancelledbookings list --page 2 --size 10 --agent` | Paginated list |
| `nexudus cancelledbookings get <id> --agent` | Get single cancelledbooking |

### CancelledBooking (key fields)

`Id`, `ResourceId`, `ResourceName`, `CoworkerId`, `CoworkerFullName`, `FromTime`, `ToTime`, `CancellationReason`, `CancelledOn`

<!-- END:GENERATED entity=CancelledBookings -->
