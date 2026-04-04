# SubscriberGroups

<!-- BEGIN:GENERATED entity=SubscriberGroups -->

SubscriberGroups support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus subscribergroups list --agent` | List all subscribergroups |
| `nexudus subscribergroups list --id <id> --agent` | Filter by single ID |
| `nexudus subscribergroups list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus subscribergroups list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus subscribergroups list --business-id <value> --name <value> --agent` | Filter subscribergroups by properties |
| `nexudus subscribergroups list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus subscribergroups get <id> --agent` | Get single subscribergroup |
| `nexudus subscribergroups create --business-id <value> --name <value> --agent` | Create subscribergroup |
| `nexudus subscribergroups update <id> --name "New Name" --agent` | Update subscribergroup |
| `nexudus subscribergroups delete <id> --yes --agent` | Delete subscribergroup (no prompt) |

#### SubscriberGroup list filter options

`--business-id`, `--name`, `--auto-add-members`, `--auto-add-contacts`, `--auto-add-bookings`, `--auto-add-events`, `--auto-add-visitors`, `--auto-add-paying-members`

#### SubscriberGroup create options

`--business-id` (required), `--name` (required), `--news-letter-subscribers` (list, repeat flag), `--added-news-letter-subscribers` (list, repeat flag), `--removed-news-letter-subscribers` (list, repeat flag), `--auto-add-members`, `--auto-add-contacts`, `--auto-add-bookings`, `--auto-add-events`, `--auto-add-visitors`, `--auto-add-paying-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

#### SubscriberGroup update options

`--business-id`, `--name`, `--news-letter-subscribers` (list, repeat flag), `--added-news-letter-subscribers` (list, repeat flag), `--removed-news-letter-subscribers` (list, repeat flag), `--auto-add-members`, `--auto-add-contacts`, `--auto-add-bookings`, `--auto-add-events`, `--auto-add-visitors`, `--auto-add-paying-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `NewsLetterSubscribers`, `AddedNewsLetterSubscribers`, `RemovedNewsLetterSubscribers`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=SubscriberGroups -->
