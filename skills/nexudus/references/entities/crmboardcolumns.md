# CrmBoardColumns

<!-- BEGIN:GENERATED entity=CrmBoardColumns -->

A **CrmBoardColumn** represents a stage (step) within a CRM board. In the Nexudus UI these are called **CRM Stages**.

Each stage has two main components:

- **Auto assignment** — controls which opportunities are automatically added to this stage. Enable one of the boolean triggers (e.g. `TourRequests`, `SignUps`, `Cancellations`, `ProductPurchased`) to auto-populate the stage when the corresponding event occurs.
- **Auto actions** — controls what happens when an opportunity reaches this stage. Assign a message macro (`CannedResponseId`), a task list (`TaskListId`), and/or an account action (`ActivateAccount`, `DeactivateAccount`, `DeleteAccount`, `ConfirmTour`, `WinOpportunity`, `LoseOpportunity`).

Stages are ordered by `Position` within their parent board. Opportunities move through stages either automatically (when conditions are met) or manually.

CrmBoardColumns support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmboardcolumns list --agent` | List all crmboardcolumns |
| `nexudus crmboardcolumns list --id <id> --agent` | Filter by single ID |
| `nexudus crmboardcolumns list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmboardcolumns list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmboardcolumns list --crm-board-name <value> --crm-board-business-name <value> --agent` | Filter crmboardcolumns by properties |
| `nexudus crmboardcolumns list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmboardcolumns list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus crmboardcolumns get <id> --agent` | Get single crmboardcolumn |
| `nexudus crmboardcolumns create --crm-board-id <value> --name <value> --position <value> --agent` | Create crmboardcolumn |
| `nexudus crmboardcolumns update <id> --name "New Name" --agent` | Update crmboardcolumn |
| `nexudus crmboardcolumns delete <id> --yes --agent` | Delete crmboardcolumn (no prompt) |

#### CrmBoardColumn list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-board-id` | long | ID of the crm board linked to this record |
| `--crm-board-name` | string | Parent CRM board name |
| `--crm-board-business-id` | int | Business ID of the parent CRM board |
| `--from-crm-board-business-id` | range | |
| `--to-crm-board-business-id` | range | |
| `--crm-board-business-name` | string | Business name of the parent CRM board |
| `--crm-board-business-currency-id` | int | Currency ID of the parent CRM board's business |
| `--from-crm-board-business-currency-id` | range | |
| `--to-crm-board-business-currency-id` | range | |
| `--crm-board-business-currency-code` | string | Currency code of the parent CRM board's business |
| `--name` | string | Stage name (e.g. 'Contract Signature', 'Keys Handout', 'Office Tour') |
| `--position` | int | Display order of this stage within the board (0-based) |
| `--from-position` | range | |
| `--to-position` | range | |
| `--tour-requests` | bool | Auto-assign: add anyone completing a tour request form to this stage |
| `--tours-confirmed` | bool | Auto-assign: add anyone confirming a tour to this stage |
| `--tour-completed` | bool | Auto-assign: add anyone completing a tour to this stage |
| `--win-opportunity` | bool | Auto-action: mark opportunity as won when added to this stage |
| `--lose-opportunity` | bool | Auto-action: mark opportunity as lost when added to this stage |
| `--sign-ups` | bool | Auto-assign: add anyone completing a sign-up form to this stage |
| `--bookings` | bool | Auto-assign: add anyone placing a booking to this stage |
| `--cancellations` | bool | Auto-assign: add anyone cancelling their contract to this stage |
| `--proposals-sent` | bool | Auto-assign: add anyone sent a proposal to this stage |
| `--proposals-accepted` | bool | Auto-assign: add anyone accepting a proposal to this stage |
| `--documents-signed` | bool | Auto-assign: add anyone e-signing a document to this stage |
| `--event-registrations` | bool | Auto-assign: add anyone registering for an event to this stage |
| `--contact-messages` | bool | Auto-assign: add anyone sending a contact message to this stage |
| `--canned-response-id` | long | Auto-action: message macro to send when an opportunity reaches this stage |
| `--task-list-id` | long | Auto-action: task list to create when an opportunity reaches this stage |
| `--use-task-list-as-responsible` | bool | Assign the task list's own responsible users instead of the opportunity owner |
| `--activate-account` | bool | Auto-action: activate the account of opportunities added to this stage |
| `--delete-account` | bool | Auto-action: permanently delete the account and all customer details of opportunities added to this stage |
| `--deactivate-account` | bool | Auto-action: deactivate the account of opportunities added to this stage |
| `--confirm-tour` | bool | Auto-action: confirm the tour of opportunities added to this stage |
| `--product-purchased` | bool | Auto-assign: add anyone purchasing a specific product to this stage. Requires Products list |
| `--resource-booked` | bool | Auto-assign: add anyone placing a booking for a specific resource to this stage. Requires Resources list |
| `--event-checkins` | bool | Auto-assign: add any event attendee who checks in for an event to this stage |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CrmBoardColumn sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Position` ascending. If no `--order-by` is specified, the API returns results ordered by `Position` (ascending).

#### CrmBoardColumn create options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-board-id` | long, required | ID of the crm board linked to this record |
| `--name` | string, required | Stage name (e.g. 'Contract Signature', 'Keys Handout', 'Office Tour') |
| `--position` | int, required | Display order of this stage within the board (0-based) |
| `--tour-requests` | bool | Auto-assign: add anyone completing a tour request form to this stage |
| `--tours-confirmed` | bool | Auto-assign: add anyone confirming a tour to this stage |
| `--tour-completed` | bool | Auto-assign: add anyone completing a tour to this stage |
| `--win-opportunity` | bool | Auto-action: mark opportunity as won when added to this stage |
| `--lose-opportunity` | bool | Auto-action: mark opportunity as lost when added to this stage |
| `--sign-ups` | bool | Auto-assign: add anyone completing a sign-up form to this stage |
| `--bookings` | bool | Auto-assign: add anyone placing a booking to this stage |
| `--cancellations` | bool | Auto-assign: add anyone cancelling their contract to this stage |
| `--proposals-sent` | bool | Auto-assign: add anyone sent a proposal to this stage |
| `--proposals-accepted` | bool | Auto-assign: add anyone accepting a proposal to this stage |
| `--documents-signed` | bool | Auto-assign: add anyone e-signing a document to this stage |
| `--event-registrations` | bool | Auto-assign: add anyone registering for an event to this stage |
| `--contact-messages` | bool | Auto-assign: add anyone sending a contact message to this stage |
| `--canned-response-id` | long | Auto-action: message macro to send when an opportunity reaches this stage |
| `--task-list-id` | long | Auto-action: task list to create when an opportunity reaches this stage |
| `--use-task-list-as-responsible` | bool | Assign the task list's own responsible users instead of the opportunity owner |
| `--activate-account` | bool | Auto-action: activate the account of opportunities added to this stage |
| `--delete-account` | bool | Auto-action: permanently delete the account and all customer details of opportunities added to this stage |
| `--deactivate-account` | bool | Auto-action: deactivate the account of opportunities added to this stage |
| `--confirm-tour` | bool | Auto-action: confirm the tour of opportunities added to this stage |
| `--product-purchased` | bool | Auto-assign: add anyone purchasing a specific product to this stage. Requires Products list |
| `--products` | list, repeat flag | Product IDs that trigger auto-assignment when ProductPurchased is enabled |
| `--added-products` | list, repeat flag | The added products value for this crm board column |
| `--removed-products` | list, repeat flag | The removed products value for this crm board column |
| `--resource-booked` | bool | Auto-assign: add anyone placing a booking for a specific resource to this stage. Requires Resources list |
| `--resources` | list, repeat flag | Resource IDs that trigger auto-assignment when ResourceBooked is enabled |
| `--added-resources` | list, repeat flag | The added resources value for this crm board column |
| `--removed-resources` | list, repeat flag | The removed resources value for this crm board column |
| `--event-checkins` | bool | Auto-assign: add any event attendee who checks in for an event to this stage |

#### CrmBoardColumn update options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-board-id` | long | ID of the crm board linked to this record |
| `--name` | string | Stage name (e.g. 'Contract Signature', 'Keys Handout', 'Office Tour') |
| `--position` | int | Display order of this stage within the board (0-based) |
| `--tour-requests` | bool | Auto-assign: add anyone completing a tour request form to this stage |
| `--tours-confirmed` | bool | Auto-assign: add anyone confirming a tour to this stage |
| `--tour-completed` | bool | Auto-assign: add anyone completing a tour to this stage |
| `--win-opportunity` | bool | Auto-action: mark opportunity as won when added to this stage |
| `--lose-opportunity` | bool | Auto-action: mark opportunity as lost when added to this stage |
| `--sign-ups` | bool | Auto-assign: add anyone completing a sign-up form to this stage |
| `--bookings` | bool | Auto-assign: add anyone placing a booking to this stage |
| `--cancellations` | bool | Auto-assign: add anyone cancelling their contract to this stage |
| `--proposals-sent` | bool | Auto-assign: add anyone sent a proposal to this stage |
| `--proposals-accepted` | bool | Auto-assign: add anyone accepting a proposal to this stage |
| `--documents-signed` | bool | Auto-assign: add anyone e-signing a document to this stage |
| `--event-registrations` | bool | Auto-assign: add anyone registering for an event to this stage |
| `--contact-messages` | bool | Auto-assign: add anyone sending a contact message to this stage |
| `--canned-response-id` | long | Auto-action: message macro to send when an opportunity reaches this stage |
| `--task-list-id` | long | Auto-action: task list to create when an opportunity reaches this stage |
| `--use-task-list-as-responsible` | bool | Assign the task list's own responsible users instead of the opportunity owner |
| `--activate-account` | bool | Auto-action: activate the account of opportunities added to this stage |
| `--delete-account` | bool | Auto-action: permanently delete the account and all customer details of opportunities added to this stage |
| `--deactivate-account` | bool | Auto-action: deactivate the account of opportunities added to this stage |
| `--confirm-tour` | bool | Auto-action: confirm the tour of opportunities added to this stage |
| `--product-purchased` | bool | Auto-assign: add anyone purchasing a specific product to this stage. Requires Products list |
| `--products` | list, repeat flag | Product IDs that trigger auto-assignment when ProductPurchased is enabled |
| `--added-products` | list, repeat flag | The added products value for this crm board column |
| `--removed-products` | list, repeat flag | The removed products value for this crm board column |
| `--resource-booked` | bool | Auto-assign: add anyone placing a booking for a specific resource to this stage. Requires Resources list |
| `--resources` | list, repeat flag | Resource IDs that trigger auto-assignment when ResourceBooked is enabled |
| `--added-resources` | list, repeat flag | The added resources value for this crm board column |
| `--removed-resources` | list, repeat flag | The removed resources value for this crm board column |
| `--event-checkins` | bool | Auto-assign: add any event attendee who checks in for an event to this stage |

### CrmBoardColumn (key fields)

`Id`, `CrmBoardName`, `CrmBoardBusinessName`, `CrmBoardBusinessCurrencyCode`, `Name`, `Position`

**List properties (only returned by `get`, not by `list`):** `Products`, `AddedProducts`, `RemovedProducts`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=CrmBoardColumns -->
