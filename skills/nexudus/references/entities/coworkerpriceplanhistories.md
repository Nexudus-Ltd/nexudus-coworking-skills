# CoworkerPricePlanHistories

<!-- BEGIN:GENERATED entity=CoworkerPricePlanHistories -->

A **CoworkerPricePlanHistory** is an audit record of the different contracts (for different plans - Tariff entity) a customer has had. Each entry captures a plan change — recording the previous and new plan names, their values, and whether the change was an upgrade.

This entity is read-only and is created automatically by the system whenever a customer's plan changes.

CoworkerPricePlanHistories support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkerpriceplanhistories list --agent` | List all coworkerpriceplanhistories |
| `nexudus coworkerpriceplanhistories list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerpriceplanhistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerpriceplanhistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerpriceplanhistories list --old-tariff-name <value> --new-tariff-name <value> --agent` | Filter coworkerpriceplanhistories by properties |
| `nexudus coworkerpriceplanhistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerpriceplanhistories get <id> --agent` | Get single coworkerpriceplanhistory |

#### CoworkerPricePlanHistory list filter options

`--coworker-id`, `--old-tariff-name`, `--new-tariff-name`, `--old-tariff-unique-id`, `--new-tariff-unique-id`, `--old-contract-unique-id`, `--new-contract-unique-id`, `--is-upgrade`, `--notes`, `--old-value`, `--from-old-value` (range), `--to-old-value` (range), `--new-value`, `--from-new-value` (range), `--to-new-value` (range), `--old-quantity`, `--from-old-quantity` (range), `--to-old-quantity` (range), `--new-quantity`, `--from-new-quantity` (range), `--to-new-quantity` (range), `--created-on-local`, `--from-created-on-local` (range), `--to-created-on-local` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

### CoworkerPricePlanHistory (key fields)

`Id`, `OldTariffName`, `NewTariffName`

<!-- END:GENERATED entity=CoworkerPricePlanHistories -->
