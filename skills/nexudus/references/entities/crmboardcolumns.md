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
| `nexudus crmboardcolumns list --name <value> --position <value> --agent` | Filter crmboardcolumns by properties |
| `nexudus crmboardcolumns list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmboardcolumns get <id> --agent` | Get single crmboardcolumn |
| `nexudus crmboardcolumns create --crm-board-id <value> --name <value> --position <value> --agent` | Create crmboardcolumn |
| `nexudus crmboardcolumns update <id> --name "New Name" --agent` | Update crmboardcolumn |
| `nexudus crmboardcolumns delete <id> --yes --agent` | Delete crmboardcolumn (no prompt) |

#### CrmBoardColumn list filter options

`--crm-board-id` (long), `--name`, `--position` (int), `--from-position` (range), `--to-position` (range), `--tour-requests` (bool), `--tours-confirmed` (bool), `--tour-completed` (bool), `--win-opportunity` (bool), `--lose-opportunity` (bool), `--sign-ups` (bool), `--bookings` (bool), `--cancellations` (bool), `--proposals-sent` (bool), `--proposals-accepted` (bool), `--documents-signed` (bool), `--event-registrations` (bool), `--contact-messages` (bool), `--canned-response-id` (long), `--task-list-id` (long), `--use-task-list-as-responsible` (bool), `--activate-account` (bool), `--delete-account` (bool), `--deactivate-account` (bool), `--confirm-tour` (bool), `--product-purchased` (bool), `--resource-booked` (bool), `--event-checkins` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CrmBoardColumn create options

`--crm-board-id` (long, required), `--name` (required), `--position` (int, required), `--tour-requests` (bool), `--tours-confirmed` (bool), `--tour-completed` (bool), `--win-opportunity` (bool), `--lose-opportunity` (bool), `--sign-ups` (bool), `--bookings` (bool), `--cancellations` (bool), `--proposals-sent` (bool), `--proposals-accepted` (bool), `--documents-signed` (bool), `--event-registrations` (bool), `--contact-messages` (bool), `--canned-response-id` (long), `--task-list-id` (long), `--use-task-list-as-responsible` (bool), `--activate-account` (bool), `--delete-account` (bool), `--deactivate-account` (bool), `--confirm-tour` (bool), `--product-purchased` (bool), `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--resource-booked` (bool), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--event-checkins` (bool)

#### CrmBoardColumn update options

`--crm-board-id` (long), `--name`, `--position` (int), `--tour-requests` (bool), `--tours-confirmed` (bool), `--tour-completed` (bool), `--win-opportunity` (bool), `--lose-opportunity` (bool), `--sign-ups` (bool), `--bookings` (bool), `--cancellations` (bool), `--proposals-sent` (bool), `--proposals-accepted` (bool), `--documents-signed` (bool), `--event-registrations` (bool), `--contact-messages` (bool), `--canned-response-id` (long), `--task-list-id` (long), `--use-task-list-as-responsible` (bool), `--activate-account` (bool), `--delete-account` (bool), `--deactivate-account` (bool), `--confirm-tour` (bool), `--product-purchased` (bool), `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--resource-booked` (bool), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--event-checkins` (bool)

### CrmBoardColumn (key fields)

`Id`, `CrmBoardName`, `CrmBoardBusinessName`, `CrmBoardBusinessCurrencyCode`, `Name`, `Position`

**List properties (only returned by `get`, not by `list`):** `Products`, `AddedProducts`, `RemovedProducts`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=CrmBoardColumns -->
