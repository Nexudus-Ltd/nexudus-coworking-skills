# Surveys

<!-- BEGIN:GENERATED entity=Surveys -->

Surveys support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveys list --agent` | List all surveys |
| `nexudus surveys list --id <id> --agent` | Filter by single ID |
| `nexudus surveys list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveys list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveys list --business-id <value> --name <value> --agent` | Filter surveys by properties |
| `nexudus surveys list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveys get <id> --agent` | Get single survey |
| `nexudus surveys create --business-id <value> --name <value> --description <value> --next-delivery-date <value> --delivery-rate <value> --delivery-rate-maximum <value> --agent` | Create survey |
| `nexudus surveys update <id> --name "New Name" --agent` | Update survey |
| `nexudus surveys delete <id> --yes --agent` | Delete survey (no prompt) |

#### Survey list filter options

`--business-id`, `--name`, `--description`, `--active`, `--next-delivery-date`, `--from-next-delivery-date` (range), `--to-next-delivery-date` (range), `--delivery-rate`, `--from-delivery-rate` (range), `--to-delivery-rate` (range), `--delivery-frequency`, `--delivery-rate-maximum`, `--from-delivery-rate-maximum` (range), `--to-delivery-rate-maximum` (range), `--delivery-frequency-maximum`, `--start-date`, `--from-start-date` (range), `--to-start-date` (range), `--only-for-contacts`, `--only-for-members`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Survey create options

`--business-id` (required), `--name` (required), `--description` (required), `--active`, `--next-delivery-date` (required), `--delivery-rate` (required), `--delivery-frequency`, `--delivery-rate-maximum` (required), `--delivery-frequency-maximum`, `--start-date`, `--only-for-contacts`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

#### Survey update options

`--business-id`, `--name`, `--description`, `--active`, `--next-delivery-date`, `--delivery-rate`, `--delivery-frequency`, `--delivery-rate-maximum`, `--delivery-frequency-maximum`, `--start-date`, `--only-for-contacts`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=Surveys -->
