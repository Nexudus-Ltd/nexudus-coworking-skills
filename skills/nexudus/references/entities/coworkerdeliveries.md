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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--coworker-id` | long |  |
| `--contract-contact-id` | long |  |
| `--name` | string | Short label or description identifying the delivery item |
| `--location` | string | Physical location where the delivery is being stored (e.g. mailroom shelf) |
| `--received-by` | string | Name of the staff member who received the delivery |
| `--notes` | string | Free-text notes about the delivery |
| `--new-file-data-url` | string |  |
| `--clear-file-data-file` | bool |  |
| `--new-signature-url` | string |  |
| `--clear-signature-file` | bool |  |
| `--new-scanned-file-data-url` | string |  |
| `--clear-scanned-file-data-file` | bool |  |
| `--new-forwarded-file-data-url` | string |  |
| `--clear-forwarded-file-data-file` | bool |  |
| `--collected` | bool | Whether the customer has collected the delivery |
| `--requires-signature` | bool | Whether the customer must sign upon collection |
| `--signed` | bool | Whether the customer has signed for the delivery |
| `--notified` | bool |  |
| `--collected-on` | DateTime | Date and time the customer collected the delivery |
| `--from-collected-on` | range | |
| `--to-collected-on` | range | |
| `--billed` | bool |  |
| `--delivery-type` | enum | Type of delivery item (Mail, Parcel, Check, Publicity, or Other) |
| `--handling-preference` | enum | How the customer wants this delivery handled (e.g. StoreForCollection, Forward, Shred) |
| `--check-deposited` | bool | Whether the enclosed check has been deposited |
| `--forwarded` | bool | Whether the delivery has been forwarded to the customer |
| `--scanned` | bool | Whether the delivery contents have been scanned |
| `--recycled` | bool | Whether the delivery has been recycled |
| `--shredded` | bool | Whether the delivery has been shredded |
| `--stored-for-collection` | bool | Whether the delivery is being held for customer collection |
| `--returned-to-sender` | bool | Whether the delivery has been returned to sender |
| `--check-deposited-on` | DateTime | Date and time the check was deposited |
| `--from-check-deposited-on` | range | |
| `--to-check-deposited-on` | range | |
| `--forwarded-on` | DateTime | Date and time the delivery was forwarded |
| `--from-forwarded-on` | range | |
| `--to-forwarded-on` | range | |
| `--scanned-on` | DateTime | Date and time the delivery contents were scanned |
| `--from-scanned-on` | range | |
| `--to-scanned-on` | range | |
| `--recycled-on` | DateTime | Date and time the delivery was recycled |
| `--from-recycled-on` | range | |
| `--to-recycled-on` | range | |
| `--shredded-on` | DateTime | Date and time the delivery was shredded |
| `--from-shredded-on` | range | |
| `--to-shredded-on` | range | |
| `--stored-for-collection-on` | DateTime | Date and time the delivery was placed in storage for collection |
| `--from-stored-for-collection-on` | range | |
| `--to-stored-for-collection-on` | range | |
| `--returned-to-sender-on` | DateTime | Date and time the delivery was returned to sender |
| `--from-returned-to-sender-on` | range | |
| `--to-returned-to-sender-on` | range | |
| `--forwarding-address-unique-id` | string |  |
| `--check-deposited-product-unique-id` | string |  |
| `--forwarded-product-unique-id` | string |  |
| `--scanned-product-unique-id` | string |  |
| `--recycled-product-unique-id` | string |  |
| `--shredded-product-unique-id` | string |  |
| `--stored-for-collection-product-unique-id` | string |  |
| `--returned-to-sender-product-unique-id` | string |  |
| `--collected-product-unique-id` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerDelivery create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--coworker-id` | long |  |
| `--contract-contact-id` | long |  |
| `--name` | string, required | Short label or description identifying the delivery item |
| `--location` | string, required | Physical location where the delivery is being stored (e.g. mailroom shelf) |
| `--received-by` | string | Name of the staff member who received the delivery |
| `--notes` | string | Free-text notes about the delivery |
| `--new-file-data-url` | string |  |
| `--clear-file-data-file` | bool |  |
| `--new-signature-url` | string |  |
| `--clear-signature-file` | bool |  |
| `--new-scanned-file-data-url` | string |  |
| `--clear-scanned-file-data-file` | bool |  |
| `--new-forwarded-file-data-url` | string |  |
| `--clear-forwarded-file-data-file` | bool |  |
| `--collected` | bool | Whether the customer has collected the delivery |
| `--requires-signature` | bool | Whether the customer must sign upon collection |
| `--signed` | bool | Whether the customer has signed for the delivery |
| `--notified` | bool |  |
| `--collected-on` | DateTime | Date and time the customer collected the delivery |
| `--billed` | bool |  |
| `--delivery-type` | enum, required | Type of delivery item (Mail, Parcel, Check, Publicity, or Other) |
| `--handling-preference` | enum | How the customer wants this delivery handled (e.g. StoreForCollection, Forward, Shred) |
| `--check-deposited` | bool | Whether the enclosed check has been deposited |
| `--forwarded` | bool | Whether the delivery has been forwarded to the customer |
| `--scanned` | bool | Whether the delivery contents have been scanned |
| `--recycled` | bool | Whether the delivery has been recycled |
| `--shredded` | bool | Whether the delivery has been shredded |
| `--stored-for-collection` | bool | Whether the delivery is being held for customer collection |
| `--returned-to-sender` | bool | Whether the delivery has been returned to sender |
| `--check-deposited-on` | DateTime | Date and time the check was deposited |
| `--forwarded-on` | DateTime | Date and time the delivery was forwarded |
| `--scanned-on` | DateTime | Date and time the delivery contents were scanned |
| `--recycled-on` | DateTime | Date and time the delivery was recycled |
| `--shredded-on` | DateTime | Date and time the delivery was shredded |
| `--stored-for-collection-on` | DateTime | Date and time the delivery was placed in storage for collection |
| `--returned-to-sender-on` | DateTime | Date and time the delivery was returned to sender |
| `--forwarding-address-unique-id` | string |  |
| `--check-deposited-product-unique-id` | string |  |
| `--forwarded-product-unique-id` | string |  |
| `--scanned-product-unique-id` | string |  |
| `--recycled-product-unique-id` | string |  |
| `--shredded-product-unique-id` | string |  |
| `--stored-for-collection-product-unique-id` | string |  |
| `--returned-to-sender-product-unique-id` | string |  |
| `--collected-product-unique-id` | string |  |

#### CoworkerDelivery update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--coworker-id` | long |  |
| `--contract-contact-id` | long |  |
| `--name` | string | Short label or description identifying the delivery item |
| `--location` | string | Physical location where the delivery is being stored (e.g. mailroom shelf) |
| `--received-by` | string | Name of the staff member who received the delivery |
| `--notes` | string | Free-text notes about the delivery |
| `--new-file-data-url` | string |  |
| `--clear-file-data-file` | bool |  |
| `--new-signature-url` | string |  |
| `--clear-signature-file` | bool |  |
| `--new-scanned-file-data-url` | string |  |
| `--clear-scanned-file-data-file` | bool |  |
| `--new-forwarded-file-data-url` | string |  |
| `--clear-forwarded-file-data-file` | bool |  |
| `--collected` | bool | Whether the customer has collected the delivery |
| `--requires-signature` | bool | Whether the customer must sign upon collection |
| `--signed` | bool | Whether the customer has signed for the delivery |
| `--notified` | bool |  |
| `--collected-on` | DateTime | Date and time the customer collected the delivery |
| `--billed` | bool |  |
| `--delivery-type` | enum | Type of delivery item (Mail, Parcel, Check, Publicity, or Other) |
| `--handling-preference` | enum | How the customer wants this delivery handled (e.g. StoreForCollection, Forward, Shred) |
| `--check-deposited` | bool | Whether the enclosed check has been deposited |
| `--forwarded` | bool | Whether the delivery has been forwarded to the customer |
| `--scanned` | bool | Whether the delivery contents have been scanned |
| `--recycled` | bool | Whether the delivery has been recycled |
| `--shredded` | bool | Whether the delivery has been shredded |
| `--stored-for-collection` | bool | Whether the delivery is being held for customer collection |
| `--returned-to-sender` | bool | Whether the delivery has been returned to sender |
| `--check-deposited-on` | DateTime | Date and time the check was deposited |
| `--forwarded-on` | DateTime | Date and time the delivery was forwarded |
| `--scanned-on` | DateTime | Date and time the delivery contents were scanned |
| `--recycled-on` | DateTime | Date and time the delivery was recycled |
| `--shredded-on` | DateTime | Date and time the delivery was shredded |
| `--stored-for-collection-on` | DateTime | Date and time the delivery was placed in storage for collection |
| `--returned-to-sender-on` | DateTime | Date and time the delivery was returned to sender |
| `--forwarding-address-unique-id` | string |  |
| `--check-deposited-product-unique-id` | string |  |
| `--forwarded-product-unique-id` | string |  |
| `--scanned-product-unique-id` | string |  |
| `--recycled-product-unique-id` | string |  |
| `--shredded-product-unique-id` | string |  |
| `--stored-for-collection-product-unique-id` | string |  |
| `--returned-to-sender-product-unique-id` | string |  |
| `--collected-product-unique-id` | string |  |

#### CoworkerDelivery PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--contract-contact-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--contract-contact-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerdeliveries update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerDelivery (key fields)

`Id`, `CoworkerFullName`, `Name`, `Processed`, `Collected`, `DeliveryType`

#### CoworkerDelivery enum values

| Option | Valid values |
| ------ | ------------ |
| `--delivery-type` | `0` None, `1` Mail, `2` Parcel, `3` Check, `4` Publicity, `5` Other |

<!-- END:GENERATED entity=CoworkerDeliveries -->
