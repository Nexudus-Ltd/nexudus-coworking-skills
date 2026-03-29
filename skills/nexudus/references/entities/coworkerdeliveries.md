# CoworkerDeliveries

<!-- BEGIN:GENERATED entity=CoworkerDeliveries -->

CoworkerDeliveries support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerdeliveries list --agent` | List all coworkerdeliveries |
| `nexudus coworkerdeliveries list --query "search" --agent` | Search coworkerdeliveries by name |
| `nexudus coworkerdeliveries list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkerdeliveries get <id> --agent` | Get single coworkerdelivery |
| `nexudus coworkerdeliveries create --business <value> --name <value> --agent` | Create coworkerdelivery |
| `nexudus coworkerdeliveries update <id> --name "New Name" --agent` | Update coworkerdelivery |
| `nexudus coworkerdeliveries delete <id> --yes --agent` | Delete coworkerdelivery (no prompt) |

#### CoworkerDelivery create options

`--business` (required), `--coworker-id`, `--contract-contact-id`, `--name` (required), `--location`, `--received-by`, `--notes`, `--processed`, `--collected`, `--requires-signature`, `--signed`, `--collected-on`, `--delivery-type`, `--handling-preference`, `--check-deposited`, `--forwarded`, `--scanned`, `--recycled`, `--shredded`, `--stored-for-collection`, `--returned-to-sender`, `--check-deposited-on`, `--forwarded-on`, `--scanned-on`, `--recycled-on`, `--shredded-on`, `--stored-for-collection-on`, `--returned-to-sender-on`, `--file-url`, `--clear-file`, `--signature-url`, `--clear-signature`, `--scanned-file-url`, `--clear-scanned-file`, `--forwarded-file-url`, `--clear-forwarded-file`

#### CoworkerDelivery update options

`--coworker-id`, `--contract-contact-id`, `--name`, `--location`, `--received-by`, `--notes`, `--processed`, `--collected`, `--requires-signature`, `--signed`, `--collected-on`, `--delivery-type`, `--handling-preference`, `--check-deposited`, `--forwarded`, `--scanned`, `--recycled`, `--shredded`, `--stored-for-collection`, `--returned-to-sender`, `--check-deposited-on`, `--forwarded-on`, `--scanned-on`, `--recycled-on`, `--shredded-on`, `--stored-for-collection-on`, `--returned-to-sender-on`, `--file-url`, `--clear-file`, `--signature-url`, `--clear-signature`, `--scanned-file-url`, `--clear-scanned-file`, `--forwarded-file-url`, `--clear-forwarded-file`

### CoworkerDelivery (key fields)

`Id`, `BusinessId`, `CoworkerId`, `CoworkerFullName`, `Name`, `Processed`, `Collected`, `DeliveryType`

#### CoworkerDelivery enum values

| Option | Valid values |
| ------ | ------------ |
| `--delivery-type` | `1` Mail, `2` Parcel, `3` Check, `4` Publicity, `5` Other |
| `--handling-preference` | `1` StoreForCollection, `2` Forward, `3` OpenScanForward, `4` OpenScanRecycle, `5` OpenScanShred, `6` OpenScanStoreForCollection, `7` Recycle, `8` ReturnToSender, `9` Shred, `10` DepositCheck, `11` Unknown |

<!-- END:GENERATED entity=CoworkerDeliveries -->
