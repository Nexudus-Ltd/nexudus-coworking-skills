# CoworkerDeliveries

<!-- BEGIN:GENERATED entity=CoworkerDeliveries -->

A delivery records mail, parcels, checks, publicity, or other items received at a location for a customer or contract contact. For ordinary customers, track collection only; for virtual-office customers, the handling preference selects a processing sequence and its completed lifecycle steps.

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
| `nexudus coworkerdeliveries list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerdeliveries get <id> --agent` | Get single coworkerdelivery |
| `nexudus coworkerdeliveries create --business-id <value> --name <value> --location <value> --delivery-type <value> --agent` | Create coworkerdelivery |
| `nexudus coworkerdeliveries update <id> --name "New Name" --agent` | Update coworkerdelivery |
| `nexudus coworkerdeliveries delete <id> --yes --agent` | Delete coworkerdelivery (no prompt) |
| `nexudus coworkerdeliveries run-command <key> <ids> --agent` | Run entity command |

#### CoworkerDelivery list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this delivery. Defaults to the current location when creating a delivery. |
| `--coworker-id` | long | ID of the customer this delivery is for. Use either CoworkerId or ContractContactId to identify the recipient. |
| `--contract-contact-id` | long | ID of the contract contact receiving this delivery when it is not assigned to a customer. |
| `--name` | string | Required short reference that identifies the delivery item. |
| `--location` | string | Required physical storage location for the delivery, such as a mailroom shelf. |
| `--received-by` | string | Name of the staff member who received the delivery. |
| `--notes` | string | Free-text operational notes about the delivery. |
| `--new-file-data-url` | string | URL of a new file to upload as the file data |
| `--clear-file-data-file` | bool | Set to true to remove the current file data file |
| `--new-signature-url` | string | URL of a new file to upload as the signature |
| `--clear-signature-file` | bool | Set to true to remove the current signature file |
| `--new-scanned-file-data-url` | string | URL of a new file to upload as the scanned file data |
| `--clear-scanned-file-data-file` | bool | Set to true to remove the current scanned file data file |
| `--new-forwarded-file-data-url` | string | URL of a new file to upload as the forwarded file data |
| `--clear-forwarded-file-data-file` | bool | Set to true to remove the current forwarded file data file |
| `--collected` | bool | Whether the customer has collected the delivery; set CollectedOn when recording collection. |
| `--requires-signature` | bool | Whether the customer must provide a signature when collecting the delivery. |
| `--signed` | bool | Whether the customer has signed for the delivery; attach the signature through NewSignatureUrl when available. |
| `--notified` | bool | Whether the system sent the delivery-received notification; maintained by delivery notification handlers. |
| `--collected-on` | DateTime | Date and time the customer collected the delivery; record it when marking Collected as true. |
| `--from-collected-on` | range | |
| `--to-collected-on` | range | |
| `--billed` | bool | Whether charges for delivery handling have been billed; maintained by the delivery processing workflow. |
| `--delivery-type` | enum | Type of delivery item: Mail, Parcel, Check, Publicity, or Other. It selects the default handling preference for virtual-office customers. |
| `--handling-preference` | enum | Virtual-office delivery workflow: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. It is not relevant for customers without a virtual-office contract; for virtual-office customers it defaults from the active contract by delivery type, falling back to StoreForCollection. |
| `--check-deposited` | bool | For a virtual-office DepositCheck workflow, whether the enclosed check has been deposited; record CheckDepositedOn when marking it complete. |
| `--forwarded` | bool | For a virtual-office forwarding workflow, whether the delivery has been forwarded to the customer; record ForwardedOn when marking it complete. |
| `--scanned` | bool | For a virtual-office open-and-scan workflow, whether the delivery contents have been scanned; record ScannedOn when marking it complete. |
| `--recycled` | bool | For a virtual-office recycling workflow, whether the delivery has been recycled; record RecycledOn when marking it complete. |
| `--shredded` | bool | For a virtual-office shredding workflow, whether the delivery has been shredded; record ShreddedOn when marking it complete. |
| `--stored-for-collection` | bool | For a virtual-office collection workflow, whether the delivery has been stored for customer collection; record StoredForCollectionOn when marking it complete. |
| `--returned-to-sender` | bool | For a virtual-office return workflow, whether the delivery has been returned to the sender; record ReturnedToSenderOn when marking it complete. |
| `--check-deposited-on` | DateTime | For a virtual-office DepositCheck workflow, date and time the check was deposited, recorded with CheckDeposited. |
| `--from-check-deposited-on` | range | |
| `--to-check-deposited-on` | range | |
| `--forwarded-on` | DateTime | For a virtual-office forwarding workflow, date and time the delivery was forwarded, recorded with Forwarded. |
| `--from-forwarded-on` | range | |
| `--to-forwarded-on` | range | |
| `--scanned-on` | DateTime | For a virtual-office open-and-scan workflow, date and time the delivery contents were scanned, recorded with Scanned. |
| `--from-scanned-on` | range | |
| `--to-scanned-on` | range | |
| `--recycled-on` | DateTime | For a virtual-office recycling workflow, date and time the delivery was recycled, recorded with Recycled. |
| `--from-recycled-on` | range | |
| `--to-recycled-on` | range | |
| `--shredded-on` | DateTime | For a virtual-office shredding workflow, date and time the delivery was shredded, recorded with Shredded. |
| `--from-shredded-on` | range | |
| `--to-shredded-on` | range | |
| `--stored-for-collection-on` | DateTime | For a virtual-office collection workflow, date and time the delivery was placed in storage for collection, recorded with StoredForCollection. |
| `--from-stored-for-collection-on` | range | |
| `--to-stored-for-collection-on` | range | |
| `--returned-to-sender-on` | DateTime | For a virtual-office return workflow, date and time the delivery was returned to the sender, recorded with ReturnedToSender. |
| `--from-returned-to-sender-on` | range | |
| `--to-returned-to-sender-on` | range | |
| `--forwarding-address-unique-id` | string | Unique ID of the nominated forwarding address; defaults from the virtual-office contract and is managed by the delivery workflow. |
| `--check-deposited-product-unique-id` | string | Unique ID of the product charge created for depositing a check; managed by the delivery workflow. |
| `--forwarded-product-unique-id` | string | Unique ID of the product charge created for forwarding; managed by the delivery workflow. |
| `--scanned-product-unique-id` | string | Unique ID of the product charge created for scanning; managed by the delivery workflow. |
| `--recycled-product-unique-id` | string | Unique ID of the product charge created for recycling; managed by the delivery workflow. |
| `--shredded-product-unique-id` | string | Unique ID of the product charge created for shredding; managed by the delivery workflow. |
| `--stored-for-collection-product-unique-id` | string | Unique ID of the product charge created for storage for collection; managed by the delivery workflow. |
| `--returned-to-sender-product-unique-id` | string | Unique ID of the product charge created for returning to sender; managed by the delivery workflow. |
| `--collected-product-unique-id` | string | Unique ID of the product charge created for collection; managed by the delivery workflow. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerDelivery sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerDelivery create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this delivery. Defaults to the current location when creating a delivery. |
| `--coworker-id` | long | ID of the customer this delivery is for. Use either CoworkerId or ContractContactId to identify the recipient. |
| `--contract-contact-id` | long | ID of the contract contact receiving this delivery when it is not assigned to a customer. |
| `--name` | string, required | Required short reference that identifies the delivery item. |
| `--location` | string, required | Required physical storage location for the delivery, such as a mailroom shelf. |
| `--received-by` | string | Name of the staff member who received the delivery. |
| `--notes` | string | Free-text operational notes about the delivery. |
| `--new-file-data-url` | string | URL of a new file to upload as the file data |
| `--clear-file-data-file` | bool | Set to true to remove the current file data file |
| `--new-signature-url` | string | URL of a new file to upload as the signature |
| `--clear-signature-file` | bool | Set to true to remove the current signature file |
| `--new-scanned-file-data-url` | string | URL of a new file to upload as the scanned file data |
| `--clear-scanned-file-data-file` | bool | Set to true to remove the current scanned file data file |
| `--new-forwarded-file-data-url` | string | URL of a new file to upload as the forwarded file data |
| `--clear-forwarded-file-data-file` | bool | Set to true to remove the current forwarded file data file |
| `--collected` | bool | Whether the customer has collected the delivery; set CollectedOn when recording collection. |
| `--requires-signature` | bool | Whether the customer must provide a signature when collecting the delivery. |
| `--signed` | bool | Whether the customer has signed for the delivery; attach the signature through NewSignatureUrl when available. |
| `--notified` | bool | Whether the system sent the delivery-received notification; maintained by delivery notification handlers. |
| `--collected-on` | DateTime | Date and time the customer collected the delivery; record it when marking Collected as true. |
| `--billed` | bool | Whether charges for delivery handling have been billed; maintained by the delivery processing workflow. |
| `--delivery-type` | enum, required | Type of delivery item: Mail, Parcel, Check, Publicity, or Other. It selects the default handling preference for virtual-office customers. |
| `--handling-preference` | enum | Virtual-office delivery workflow: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. It is not relevant for customers without a virtual-office contract; for virtual-office customers it defaults from the active contract by delivery type, falling back to StoreForCollection. |
| `--check-deposited` | bool | For a virtual-office DepositCheck workflow, whether the enclosed check has been deposited; record CheckDepositedOn when marking it complete. |
| `--forwarded` | bool | For a virtual-office forwarding workflow, whether the delivery has been forwarded to the customer; record ForwardedOn when marking it complete. |
| `--scanned` | bool | For a virtual-office open-and-scan workflow, whether the delivery contents have been scanned; record ScannedOn when marking it complete. |
| `--recycled` | bool | For a virtual-office recycling workflow, whether the delivery has been recycled; record RecycledOn when marking it complete. |
| `--shredded` | bool | For a virtual-office shredding workflow, whether the delivery has been shredded; record ShreddedOn when marking it complete. |
| `--stored-for-collection` | bool | For a virtual-office collection workflow, whether the delivery has been stored for customer collection; record StoredForCollectionOn when marking it complete. |
| `--returned-to-sender` | bool | For a virtual-office return workflow, whether the delivery has been returned to the sender; record ReturnedToSenderOn when marking it complete. |
| `--check-deposited-on` | DateTime | For a virtual-office DepositCheck workflow, date and time the check was deposited, recorded with CheckDeposited. |
| `--forwarded-on` | DateTime | For a virtual-office forwarding workflow, date and time the delivery was forwarded, recorded with Forwarded. |
| `--scanned-on` | DateTime | For a virtual-office open-and-scan workflow, date and time the delivery contents were scanned, recorded with Scanned. |
| `--recycled-on` | DateTime | For a virtual-office recycling workflow, date and time the delivery was recycled, recorded with Recycled. |
| `--shredded-on` | DateTime | For a virtual-office shredding workflow, date and time the delivery was shredded, recorded with Shredded. |
| `--stored-for-collection-on` | DateTime | For a virtual-office collection workflow, date and time the delivery was placed in storage for collection, recorded with StoredForCollection. |
| `--returned-to-sender-on` | DateTime | For a virtual-office return workflow, date and time the delivery was returned to the sender, recorded with ReturnedToSender. |
| `--forwarding-address-unique-id` | string | Unique ID of the nominated forwarding address; defaults from the virtual-office contract and is managed by the delivery workflow. |
| `--check-deposited-product-unique-id` | string | Unique ID of the product charge created for depositing a check; managed by the delivery workflow. |
| `--forwarded-product-unique-id` | string | Unique ID of the product charge created for forwarding; managed by the delivery workflow. |
| `--scanned-product-unique-id` | string | Unique ID of the product charge created for scanning; managed by the delivery workflow. |
| `--recycled-product-unique-id` | string | Unique ID of the product charge created for recycling; managed by the delivery workflow. |
| `--shredded-product-unique-id` | string | Unique ID of the product charge created for shredding; managed by the delivery workflow. |
| `--stored-for-collection-product-unique-id` | string | Unique ID of the product charge created for storage for collection; managed by the delivery workflow. |
| `--returned-to-sender-product-unique-id` | string | Unique ID of the product charge created for returning to sender; managed by the delivery workflow. |
| `--collected-product-unique-id` | string | Unique ID of the product charge created for collection; managed by the delivery workflow. |

#### CoworkerDelivery update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this delivery. Defaults to the current location when creating a delivery. |
| `--coworker-id` | long | ID of the customer this delivery is for. Use either CoworkerId or ContractContactId to identify the recipient. |
| `--contract-contact-id` | long | ID of the contract contact receiving this delivery when it is not assigned to a customer. |
| `--name` | string | Required short reference that identifies the delivery item. |
| `--location` | string | Required physical storage location for the delivery, such as a mailroom shelf. |
| `--received-by` | string | Name of the staff member who received the delivery. |
| `--notes` | string | Free-text operational notes about the delivery. |
| `--new-file-data-url` | string | URL of a new file to upload as the file data |
| `--clear-file-data-file` | bool | Set to true to remove the current file data file |
| `--new-signature-url` | string | URL of a new file to upload as the signature |
| `--clear-signature-file` | bool | Set to true to remove the current signature file |
| `--new-scanned-file-data-url` | string | URL of a new file to upload as the scanned file data |
| `--clear-scanned-file-data-file` | bool | Set to true to remove the current scanned file data file |
| `--new-forwarded-file-data-url` | string | URL of a new file to upload as the forwarded file data |
| `--clear-forwarded-file-data-file` | bool | Set to true to remove the current forwarded file data file |
| `--collected` | bool | Whether the customer has collected the delivery; set CollectedOn when recording collection. |
| `--requires-signature` | bool | Whether the customer must provide a signature when collecting the delivery. |
| `--signed` | bool | Whether the customer has signed for the delivery; attach the signature through NewSignatureUrl when available. |
| `--notified` | bool | Whether the system sent the delivery-received notification; maintained by delivery notification handlers. |
| `--collected-on` | DateTime | Date and time the customer collected the delivery; record it when marking Collected as true. |
| `--billed` | bool | Whether charges for delivery handling have been billed; maintained by the delivery processing workflow. |
| `--delivery-type` | enum | Type of delivery item: Mail, Parcel, Check, Publicity, or Other. It selects the default handling preference for virtual-office customers. |
| `--handling-preference` | enum | Virtual-office delivery workflow: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. It is not relevant for customers without a virtual-office contract; for virtual-office customers it defaults from the active contract by delivery type, falling back to StoreForCollection. |
| `--check-deposited` | bool | For a virtual-office DepositCheck workflow, whether the enclosed check has been deposited; record CheckDepositedOn when marking it complete. |
| `--forwarded` | bool | For a virtual-office forwarding workflow, whether the delivery has been forwarded to the customer; record ForwardedOn when marking it complete. |
| `--scanned` | bool | For a virtual-office open-and-scan workflow, whether the delivery contents have been scanned; record ScannedOn when marking it complete. |
| `--recycled` | bool | For a virtual-office recycling workflow, whether the delivery has been recycled; record RecycledOn when marking it complete. |
| `--shredded` | bool | For a virtual-office shredding workflow, whether the delivery has been shredded; record ShreddedOn when marking it complete. |
| `--stored-for-collection` | bool | For a virtual-office collection workflow, whether the delivery has been stored for customer collection; record StoredForCollectionOn when marking it complete. |
| `--returned-to-sender` | bool | For a virtual-office return workflow, whether the delivery has been returned to the sender; record ReturnedToSenderOn when marking it complete. |
| `--check-deposited-on` | DateTime | For a virtual-office DepositCheck workflow, date and time the check was deposited, recorded with CheckDeposited. |
| `--forwarded-on` | DateTime | For a virtual-office forwarding workflow, date and time the delivery was forwarded, recorded with Forwarded. |
| `--scanned-on` | DateTime | For a virtual-office open-and-scan workflow, date and time the delivery contents were scanned, recorded with Scanned. |
| `--recycled-on` | DateTime | For a virtual-office recycling workflow, date and time the delivery was recycled, recorded with Recycled. |
| `--shredded-on` | DateTime | For a virtual-office shredding workflow, date and time the delivery was shredded, recorded with Shredded. |
| `--stored-for-collection-on` | DateTime | For a virtual-office collection workflow, date and time the delivery was placed in storage for collection, recorded with StoredForCollection. |
| `--returned-to-sender-on` | DateTime | For a virtual-office return workflow, date and time the delivery was returned to the sender, recorded with ReturnedToSender. |
| `--forwarding-address-unique-id` | string | Unique ID of the nominated forwarding address; defaults from the virtual-office contract and is managed by the delivery workflow. |
| `--check-deposited-product-unique-id` | string | Unique ID of the product charge created for depositing a check; managed by the delivery workflow. |
| `--forwarded-product-unique-id` | string | Unique ID of the product charge created for forwarding; managed by the delivery workflow. |
| `--scanned-product-unique-id` | string | Unique ID of the product charge created for scanning; managed by the delivery workflow. |
| `--recycled-product-unique-id` | string | Unique ID of the product charge created for recycling; managed by the delivery workflow. |
| `--shredded-product-unique-id` | string | Unique ID of the product charge created for shredding; managed by the delivery workflow. |
| `--stored-for-collection-product-unique-id` | string | Unique ID of the product charge created for storage for collection; managed by the delivery workflow. |
| `--returned-to-sender-product-unique-id` | string | Unique ID of the product charge created for returning to sender; managed by the delivery workflow. |
| `--collected-product-unique-id` | string | Unique ID of the product charge created for collection; managed by the delivery workflow. |

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
| `--delivery-type` | `1` Mail, `2` Parcel, `3` Check, `4` Publicity, `5` Other |

<!-- END:GENERATED entity=CoworkerDeliveries -->
