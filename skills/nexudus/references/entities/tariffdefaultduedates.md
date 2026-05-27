# TariffDefaultDueDates

<!-- BEGIN:GENERATED entity=TariffDefaultDueDates -->

A **TariffDefaultDueDate** configures the default invoice due date settings for a pricing plan (tariff). This controls when invoices generated for customers on this plan are due for payment.

TariffDefaultDueDates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffdefaultduedates list --agent` | List all tariffdefaultduedates |
| `nexudus tariffdefaultduedates list --id <id> --agent` | Filter by single ID |
| `nexudus tariffdefaultduedates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffdefaultduedates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffdefaultduedates list --auto-collect-on <value> --auto-collect-after <value> --agent` | Filter tariffdefaultduedates by properties |
| `nexudus tariffdefaultduedates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffdefaultduedates get <id> --agent` | Get single tariffdefaultduedate |
| `nexudus tariffdefaultduedates create --business-id <value> --agent` | Create tariffdefaultduedate |
| `nexudus tariffdefaultduedates update <id> --name "New Name" --agent` | Update tariffdefaultduedate |
| `nexudus tariffdefaultduedates delete <id> --yes --agent` | Delete tariffdefaultduedate (no prompt) |

#### TariffDefaultDueDate list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--auto-collect-on` | int | Day of month to auto collect |
| `--from-auto-collect-on` | range | |
| `--to-auto-collect-on` | range | |
| `--auto-collect-after` | int | Days after invoice to auto collect |
| `--from-auto-collect-after` | range | |
| `--to-auto-collect-after` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffDefaultDueDate create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this tariff default due date |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this tariff default due date |
| `--auto-collect-on` | int | Day of month to auto collect |
| `--auto-collect-after` | int | Days after invoice to auto collect |

#### TariffDefaultDueDate update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this tariff default due date |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this tariff default due date |
| `--auto-collect-on` | int | Day of month to auto collect |
| `--auto-collect-after` | int | Days after invoice to auto collect |

### TariffDefaultDueDate (key fields)

`Id`, `AutoCollectOn`, `AutoCollectAfter`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TariffDefaultDueDates -->
