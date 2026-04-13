# CoworkerDeliveries

<!-- BEGIN:GENERATED entity=CoworkerDeliveries -->

A **CoworkerDelivery** tracks a delivery (mail, parcel, check, or other item) received on behalf of a customer at a location, along with its current processing status and the customer's handling preference.

Each delivery records **who** it is for (`CoworkerId` or `ContractContactId`), **what** it is (`DeliveryType`), and **how** the customer wants it handled (`HandlingPreference`). Staff can then mark the delivery through its lifecycle — processed, collected, forwarded, scanned, recycled, shredded, or returned to sender — with corresponding timestamps.

Handling preferences control what happens to the delivery:

| HandlingPreference       | Meaning                                              |
| ------------------------ | ---------------------------------------------------- |
| StoreForCollection       | Hold for the customer to pick up                     |
| Forward                  | Forward to the customer's address                    |
| OpenScanForward          | Open, scan contents, then forward the original       |
| OpenScanRecycle          | Open, scan contents, then recycle the original       |
| OpenScanShred            | Open, scan contents, then shred the original         |
| OpenScanStoreForCollection | Open, scan contents, then hold for collection      |
| Recycle                  | Recycle the delivery                                 |
| ReturnToSender           | Return the delivery to the sender                    |
| Shred                    | Shred the delivery                                   |
| DepositCheck             | Deposit the enclosed check                           |

Deliveries can also have attached files — for example, a scanned copy of the contents (`NewScannedFileDataUrl`), a forwarding receipt (`NewForwardedFileDataUrl`), or a collection signature (`NewSignatureUrl`).

CoworkerDeliveries support Search, Get, Create, Update, Delete.
CoworkerDeliveries also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkerdeliveries list --agent` | List all coworkerdeliveries |
| `nexudus coworkerdeliveries list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerdeliveries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerdeliveries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerdeliveries list --name <value> --collected <value> --agent` | Filter coworkerdeliveries by properties |
| `nexudus coworkerdeliveries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerdeliveries get <id> --agent` | Get single coworkerdelivery |
| `nexudus coworkerdeliveries create --business-id <value> --name <value> --location <value> --delivery-type <value> --agent` | Create coworkerdelivery |
| `nexudus coworkerdeliveries update <id> --name "New Name" --agent` | Update coworkerdelivery |
| `nexudus coworkerdeliveries delete <id> --yes --agent` | Delete coworkerdelivery (no prompt) |
| `nexudus coworkerdeliveries run-command <key> <ids> --agent` | Run entity command |

#### CoworkerDelivery list filter options

`--business-id` (long), `--coworker-id` (long), `--contract-contact-id` (long), `--name`, `--location`, `--received-by`, `--notes`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--new-signature-url`, `--clear-signature-file` (bool), `--new-scanned-file-data-url`, `--clear-scanned-file-data-file` (bool), `--new-forwarded-file-data-url`, `--clear-forwarded-file-data-file` (bool), `--collected` (bool), `--requires-signature` (bool), `--signed` (bool), `--notified` (bool), `--collected-on` (DateTime), `--from-collected-on` (range), `--to-collected-on` (range), `--billed` (bool), `--delivery-type` (enum), `--handling-preference` (enum), `--check-deposited` (bool), `--forwarded` (bool), `--scanned` (bool), `--recycled` (bool), `--shredded` (bool), `--stored-for-collection` (bool), `--returned-to-sender` (bool), `--check-deposited-on` (DateTime), `--from-check-deposited-on` (range), `--to-check-deposited-on` (range), `--forwarded-on` (DateTime), `--from-forwarded-on` (range), `--to-forwarded-on` (range), `--scanned-on` (DateTime), `--from-scanned-on` (range), `--to-scanned-on` (range), `--recycled-on` (DateTime), `--from-recycled-on` (range), `--to-recycled-on` (range), `--shredded-on` (DateTime), `--from-shredded-on` (range), `--to-shredded-on` (range), `--stored-for-collection-on` (DateTime), `--from-stored-for-collection-on` (range), `--to-stored-for-collection-on` (range), `--returned-to-sender-on` (DateTime), `--from-returned-to-sender-on` (range), `--to-returned-to-sender-on` (range), `--forwarding-address-unique-id`, `--check-deposited-product-unique-id`, `--forwarded-product-unique-id`, `--scanned-product-unique-id`, `--recycled-product-unique-id`, `--shredded-product-unique-id`, `--stored-for-collection-product-unique-id`, `--returned-to-sender-product-unique-id`, `--collected-product-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerDelivery create options

`--business-id` (long, required), `--coworker-id` (long), `--contract-contact-id` (long), `--name` (required), `--location` (required), `--received-by`, `--notes`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--new-signature-url`, `--clear-signature-file` (bool), `--new-scanned-file-data-url`, `--clear-scanned-file-data-file` (bool), `--new-forwarded-file-data-url`, `--clear-forwarded-file-data-file` (bool), `--collected` (bool), `--requires-signature` (bool), `--signed` (bool), `--notified` (bool), `--collected-on` (DateTime), `--billed` (bool), `--delivery-type` (enum, required), `--handling-preference` (enum), `--check-deposited` (bool), `--forwarded` (bool), `--scanned` (bool), `--recycled` (bool), `--shredded` (bool), `--stored-for-collection` (bool), `--returned-to-sender` (bool), `--check-deposited-on` (DateTime), `--forwarded-on` (DateTime), `--scanned-on` (DateTime), `--recycled-on` (DateTime), `--shredded-on` (DateTime), `--stored-for-collection-on` (DateTime), `--returned-to-sender-on` (DateTime), `--forwarding-address-unique-id`, `--check-deposited-product-unique-id`, `--forwarded-product-unique-id`, `--scanned-product-unique-id`, `--recycled-product-unique-id`, `--shredded-product-unique-id`, `--stored-for-collection-product-unique-id`, `--returned-to-sender-product-unique-id`, `--collected-product-unique-id`

#### CoworkerDelivery update options

`--business-id` (long), `--coworker-id` (long), `--contract-contact-id` (long), `--name`, `--location`, `--received-by`, `--notes`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--new-signature-url`, `--clear-signature-file` (bool), `--new-scanned-file-data-url`, `--clear-scanned-file-data-file` (bool), `--new-forwarded-file-data-url`, `--clear-forwarded-file-data-file` (bool), `--collected` (bool), `--requires-signature` (bool), `--signed` (bool), `--notified` (bool), `--collected-on` (DateTime), `--billed` (bool), `--delivery-type` (enum), `--handling-preference` (enum), `--check-deposited` (bool), `--forwarded` (bool), `--scanned` (bool), `--recycled` (bool), `--shredded` (bool), `--stored-for-collection` (bool), `--returned-to-sender` (bool), `--check-deposited-on` (DateTime), `--forwarded-on` (DateTime), `--scanned-on` (DateTime), `--recycled-on` (DateTime), `--shredded-on` (DateTime), `--stored-for-collection-on` (DateTime), `--returned-to-sender-on` (DateTime), `--forwarding-address-unique-id`, `--check-deposited-product-unique-id`, `--forwarded-product-unique-id`, `--scanned-product-unique-id`, `--recycled-product-unique-id`, `--shredded-product-unique-id`, `--stored-for-collection-product-unique-id`, `--returned-to-sender-product-unique-id`, `--collected-product-unique-id`

### CoworkerDelivery (key fields)

`Id`, `CoworkerFullName`, `Name`, `Processed`, `Collected`, `DeliveryType`

#### CoworkerDelivery enum values

| Option | Valid values |
| ------ | ------------ |
| `--delivery-type` | `0` None, `1` Mail, `2` Parcel, `3` Check, `4` Publicity, `5` Other |

<!-- END:GENERATED entity=CoworkerDeliveries -->
