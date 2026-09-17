# CrmBoardColumns

<!-- BEGIN:GENERATED entity=CrmBoardColumns -->

A CRM stage (CrmBoardColumn) is an ordered step in a location's CRM board that can automatically add customers after selected events and run message, task, account, tour, opportunity-status, or record-creation-workflow actions when an opportunity enters it.

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
| `--crm-board-id` | long | ID of the CRM board that owns this stage and determines its location access. |
| `--crm-board-name` | string | Display value for CrmBoard.Name. |
| `--crm-board-business-id` | int | Display value for CrmBoard.Business.Id. |
| `--from-crm-board-business-id` | range | |
| `--to-crm-board-business-id` | range | |
| `--crm-board-business-name` | string | Display value for CrmBoard.Business.Name. |
| `--crm-board-business-currency-id` | int | Display value for CrmBoard.Business.Currency.Id. |
| `--from-crm-board-business-currency-id` | range | |
| `--to-crm-board-business-currency-id` | range | |
| `--crm-board-business-currency-code` | string | Display value for CrmBoard.Business.Currency.Code. |
| `--name` | string | Required unique name for this CRM stage within its workflow, such as Contract Signature or Office Tour. |
| `--position` | int | Requested relative position in the board's stage sequence; the server normalizes saved positions to 1, 100, 200, and so on. |
| `--from-position` | range | |
| `--to-position` | range | |
| `--tour-requests` | bool | Whether customers who submit a tour request are automatically added to this stage while its board is active. |
| `--tours-confirmed` | bool | Whether customers who confirm a tour are automatically added to this stage while its board is active. |
| `--tour-completed` | bool | Whether customers who complete a tour are automatically added to this stage while its board is active. |
| `--win-opportunity` | bool | Whether moving an existing opportunity to this stage marks it won; when both WinOpportunity and LoseOpportunity are true, winning is applied last. |
| `--lose-opportunity` | bool | Whether moving an existing opportunity to this stage marks it lost; WinOpportunity overrides this final status when both are true. |
| `--sign-ups` | bool | Whether customers who complete sign-up are automatically added to this stage while its board is active. |
| `--bookings` | bool | Whether customers who make a booking are automatically added to this stage while its board is active. |
| `--cancellations` | bool | Whether customers who cancel are automatically added to this stage while its board is active. |
| `--proposals-sent` | bool | Whether customers who are sent a proposal are automatically added to this stage while its board is active. |
| `--proposals-accepted` | bool | Whether customers who accept a proposal are automatically added to this stage while its board is active. |
| `--documents-signed` | bool | Whether customers who electronically sign a document are automatically added to this stage while its board is active. |
| `--event-registrations` | bool | Whether customers who register for an event are automatically added to this stage while its board is active. |
| `--contact-messages` | bool | Whether customers who send a contact message are automatically added to this stage while its board is active. |
| `--canned-response-id` | long | Optional ID of the message macro sent to the customer when an opportunity enters this stage. |
| `--canned-response-name` | string | Display value for CannedResponse.Name. |
| `--task-list-id` | long | Optional ID of the task list whose tasks are created for the customer when an opportunity enters this stage. |
| `--task-list-name` | string | Display value for TaskList.Name. |
| `--use-task-list-as-responsible` | bool | Whether task-list tasks use the task list's configured assignees instead of the opportunity's responsible user; applies only when TaskList is set. |
| `--record-creation-workflow-trigger-id` | long | Read-only mirror of the enabled CRM stage workflow trigger that runs when an opportunity enters this stage. Set it by choosing this board and stage on the workflow trigger and enabling it, not by writing this field; disabling or repointing that trigger clears it. |
| `--record-creation-workflow-trigger-name` | string | Display value for RecordCreationWorkflowTrigger.Name. |
| `--activate-account` | bool | Whether arrival at this stage activates the customer's account and creates a user account when one is missing; DeactivateAccount runs afterward when also enabled. |
| `--delete-account` | bool | Whether arrival at this stage schedules permanent deletion of the customer's account and details shortly after the opportunity is moved. |
| `--deactivate-account` | bool | Whether arrival at this stage deactivates the customer's account; it runs after ActivateAccount when both are enabled. |
| `--confirm-tour` | bool | Whether arrival at this stage confirms every unconfirmed tour at this location matching the customer's email address. |
| `--product-purchased` | bool | Whether customers who purchase a selected product are automatically added to this stage; it is cleared when Products is empty or disabled. |
| `--resource-booked` | bool | Whether customers who book a selected resource are automatically added to this stage; it is cleared when Resources is empty or disabled. |
| `--event-checkins` | bool | Whether customers who check in to an event are automatically added to this stage while its board is active. |
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
| `--crm-board-id` | long, required | ID of the CRM board that owns this stage and determines its location access. |
| `--name` | string, required | Required unique name for this CRM stage within its workflow, such as Contract Signature or Office Tour. |
| `--position` | int, required | Requested relative position in the board's stage sequence; the server normalizes saved positions to 1, 100, 200, and so on. |
| `--tour-requests` | bool | Whether customers who submit a tour request are automatically added to this stage while its board is active. |
| `--tours-confirmed` | bool | Whether customers who confirm a tour are automatically added to this stage while its board is active. |
| `--tour-completed` | bool | Whether customers who complete a tour are automatically added to this stage while its board is active. |
| `--win-opportunity` | bool | Whether moving an existing opportunity to this stage marks it won; when both WinOpportunity and LoseOpportunity are true, winning is applied last. |
| `--lose-opportunity` | bool | Whether moving an existing opportunity to this stage marks it lost; WinOpportunity overrides this final status when both are true. |
| `--sign-ups` | bool | Whether customers who complete sign-up are automatically added to this stage while its board is active. |
| `--bookings` | bool | Whether customers who make a booking are automatically added to this stage while its board is active. |
| `--cancellations` | bool | Whether customers who cancel are automatically added to this stage while its board is active. |
| `--proposals-sent` | bool | Whether customers who are sent a proposal are automatically added to this stage while its board is active. |
| `--proposals-accepted` | bool | Whether customers who accept a proposal are automatically added to this stage while its board is active. |
| `--documents-signed` | bool | Whether customers who electronically sign a document are automatically added to this stage while its board is active. |
| `--event-registrations` | bool | Whether customers who register for an event are automatically added to this stage while its board is active. |
| `--contact-messages` | bool | Whether customers who send a contact message are automatically added to this stage while its board is active. |
| `--canned-response-id` | long | Optional ID of the message macro sent to the customer when an opportunity enters this stage. |
| `--task-list-id` | long | Optional ID of the task list whose tasks are created for the customer when an opportunity enters this stage. |
| `--use-task-list-as-responsible` | bool | Whether task-list tasks use the task list's configured assignees instead of the opportunity's responsible user; applies only when TaskList is set. |
| `--record-creation-workflow-trigger-id` | long | Read-only mirror of the enabled CRM stage workflow trigger that runs when an opportunity enters this stage. Set it by choosing this board and stage on the workflow trigger and enabling it, not by writing this field; disabling or repointing that trigger clears it. |
| `--activate-account` | bool | Whether arrival at this stage activates the customer's account and creates a user account when one is missing; DeactivateAccount runs afterward when also enabled. |
| `--delete-account` | bool | Whether arrival at this stage schedules permanent deletion of the customer's account and details shortly after the opportunity is moved. |
| `--deactivate-account` | bool | Whether arrival at this stage deactivates the customer's account; it runs after ActivateAccount when both are enabled. |
| `--confirm-tour` | bool | Whether arrival at this stage confirms every unconfirmed tour at this location matching the customer's email address. |
| `--product-purchased` | bool | Whether customers who purchase a selected product are automatically added to this stage; it is cleared when Products is empty or disabled. |
| `--products` | list, repeat flag | List of product IDs that trigger auto-assignment when ProductPurchased is enabled; the list must be non-empty and no product can trigger another stage in the same board. |
| `--added-products` | list, repeat flag | IDs added to the Products relationship. |
| `--removed-products` | list, repeat flag | IDs removed from the Products relationship. |
| `--resource-booked` | bool | Whether customers who book a selected resource are automatically added to this stage; it is cleared when Resources is empty or disabled. |
| `--resources` | list, repeat flag | List of resource IDs that trigger auto-assignment when ResourceBooked is enabled; the list must be non-empty and no resource can trigger another stage in the same board. |
| `--added-resources` | list, repeat flag | IDs added to the Resources relationship. |
| `--removed-resources` | list, repeat flag | IDs removed from the Resources relationship. |
| `--event-checkins` | bool | Whether customers who check in to an event are automatically added to this stage while its board is active. |

#### CrmBoardColumn update options

| Option | Type | Description |
| --- | --- | --- |
| `--crm-board-id` | long | ID of the CRM board that owns this stage and determines its location access. |
| `--name` | string | Required unique name for this CRM stage within its workflow, such as Contract Signature or Office Tour. |
| `--position` | int | Requested relative position in the board's stage sequence; the server normalizes saved positions to 1, 100, 200, and so on. |
| `--tour-requests` | bool | Whether customers who submit a tour request are automatically added to this stage while its board is active. |
| `--tours-confirmed` | bool | Whether customers who confirm a tour are automatically added to this stage while its board is active. |
| `--tour-completed` | bool | Whether customers who complete a tour are automatically added to this stage while its board is active. |
| `--win-opportunity` | bool | Whether moving an existing opportunity to this stage marks it won; when both WinOpportunity and LoseOpportunity are true, winning is applied last. |
| `--lose-opportunity` | bool | Whether moving an existing opportunity to this stage marks it lost; WinOpportunity overrides this final status when both are true. |
| `--sign-ups` | bool | Whether customers who complete sign-up are automatically added to this stage while its board is active. |
| `--bookings` | bool | Whether customers who make a booking are automatically added to this stage while its board is active. |
| `--cancellations` | bool | Whether customers who cancel are automatically added to this stage while its board is active. |
| `--proposals-sent` | bool | Whether customers who are sent a proposal are automatically added to this stage while its board is active. |
| `--proposals-accepted` | bool | Whether customers who accept a proposal are automatically added to this stage while its board is active. |
| `--documents-signed` | bool | Whether customers who electronically sign a document are automatically added to this stage while its board is active. |
| `--event-registrations` | bool | Whether customers who register for an event are automatically added to this stage while its board is active. |
| `--contact-messages` | bool | Whether customers who send a contact message are automatically added to this stage while its board is active. |
| `--canned-response-id` | long | Optional ID of the message macro sent to the customer when an opportunity enters this stage. |
| `--task-list-id` | long | Optional ID of the task list whose tasks are created for the customer when an opportunity enters this stage. |
| `--use-task-list-as-responsible` | bool | Whether task-list tasks use the task list's configured assignees instead of the opportunity's responsible user; applies only when TaskList is set. |
| `--record-creation-workflow-trigger-id` | long | Read-only mirror of the enabled CRM stage workflow trigger that runs when an opportunity enters this stage. Set it by choosing this board and stage on the workflow trigger and enabling it, not by writing this field; disabling or repointing that trigger clears it. |
| `--activate-account` | bool | Whether arrival at this stage activates the customer's account and creates a user account when one is missing; DeactivateAccount runs afterward when also enabled. |
| `--delete-account` | bool | Whether arrival at this stage schedules permanent deletion of the customer's account and details shortly after the opportunity is moved. |
| `--deactivate-account` | bool | Whether arrival at this stage deactivates the customer's account; it runs after ActivateAccount when both are enabled. |
| `--confirm-tour` | bool | Whether arrival at this stage confirms every unconfirmed tour at this location matching the customer's email address. |
| `--product-purchased` | bool | Whether customers who purchase a selected product are automatically added to this stage; it is cleared when Products is empty or disabled. |
| `--products` | list, repeat flag | List of product IDs that trigger auto-assignment when ProductPurchased is enabled; the list must be non-empty and no product can trigger another stage in the same board. |
| `--added-products` | list, repeat flag | IDs added to the Products relationship. |
| `--removed-products` | list, repeat flag | IDs removed from the Products relationship. |
| `--resource-booked` | bool | Whether customers who book a selected resource are automatically added to this stage; it is cleared when Resources is empty or disabled. |
| `--resources` | list, repeat flag | List of resource IDs that trigger auto-assignment when ResourceBooked is enabled; the list must be non-empty and no resource can trigger another stage in the same board. |
| `--added-resources` | list, repeat flag | IDs added to the Resources relationship. |
| `--removed-resources` | list, repeat flag | IDs removed from the Resources relationship. |
| `--event-checkins` | bool | Whether customers who check in to an event are automatically added to this stage while its board is active. |

### CrmBoardColumn (key fields)

`Id`, `CrmBoardName`, `CrmBoardBusinessName`, `CrmBoardBusinessCurrencyCode`, `Name`, `Position`

**List properties (only returned by `get`, not by `list`):** `Products`, `AddedProducts`, `RemovedProducts`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=CrmBoardColumns -->
