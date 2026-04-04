# CrmBoardColumns

<!-- BEGIN:GENERATED entity=CrmBoardColumns -->

CrmBoardColumns support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmboardcolumns list --agent` | List all crmboardcolumns |
| `nexudus crmboardcolumns list --id <id> --agent` | Filter by single ID |
| `nexudus crmboardcolumns list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmboardcolumns list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmboardcolumns list --crm-board-id <value> --name <value> --agent` | Filter crmboardcolumns by properties |
| `nexudus crmboardcolumns list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmboardcolumns get <id> --agent` | Get single crmboardcolumn |
| `nexudus crmboardcolumns create --crm-board-id <value> --name <value> --position <value> --agent` | Create crmboardcolumn |
| `nexudus crmboardcolumns update <id> --name "New Name" --agent` | Update crmboardcolumn |
| `nexudus crmboardcolumns delete <id> --yes --agent` | Delete crmboardcolumn (no prompt) |

#### CrmBoardColumn list filter options

`--crm-board-id`, `--name`, `--position`, `--tour-requests`, `--tours-confirmed`, `--tour-completed`, `--win-opportunity`, `--lose-opportunity`, `--sign-ups`, `--bookings`, `--cancellations`, `--proposals-sent`, `--proposals-accepted`, `--documents-signed`, `--event-registrations`, `--contact-messages`, `--canned-response-id`, `--task-list-id`, `--use-task-list-as-responsible`, `--activate-account`, `--delete-account`, `--deactivate-account`, `--confirm-tour`, `--product-purchased`, `--resource-booked`, `--event-checkins`

#### CrmBoardColumn create options

`--crm-board-id` (required), `--name` (required), `--position` (required), `--tour-requests`, `--tours-confirmed`, `--tour-completed`, `--win-opportunity`, `--lose-opportunity`, `--sign-ups`, `--bookings`, `--cancellations`, `--proposals-sent`, `--proposals-accepted`, `--documents-signed`, `--event-registrations`, `--contact-messages`, `--opportunities` (list, repeat flag), `--added-opportunities` (list, repeat flag), `--removed-opportunities` (list, repeat flag), `--canned-response-id`, `--task-list-id`, `--use-task-list-as-responsible`, `--activate-account`, `--delete-account`, `--deactivate-account`, `--confirm-tour`, `--product-purchased`, `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--resource-booked`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--event-checkins`

#### CrmBoardColumn update options

`--crm-board-id`, `--name`, `--position`, `--tour-requests`, `--tours-confirmed`, `--tour-completed`, `--win-opportunity`, `--lose-opportunity`, `--sign-ups`, `--bookings`, `--cancellations`, `--proposals-sent`, `--proposals-accepted`, `--documents-signed`, `--event-registrations`, `--contact-messages`, `--opportunities` (list, repeat flag), `--added-opportunities` (list, repeat flag), `--removed-opportunities` (list, repeat flag), `--canned-response-id`, `--task-list-id`, `--use-task-list-as-responsible`, `--activate-account`, `--delete-account`, `--deactivate-account`, `--confirm-tour`, `--product-purchased`, `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--resource-booked`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--event-checkins`

**List properties (only returned by `get`, not by `list`):** `Opportunities`, `AddedOpportunities`, `RemovedOpportunities`, `Products`, `AddedProducts`, `RemovedProducts`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=CrmBoardColumns -->
