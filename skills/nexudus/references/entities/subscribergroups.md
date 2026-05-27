# SubscriberGroups

<!-- BEGIN:GENERATED entity=SubscriberGroups -->

A **SubscriberGroup** defines a segment or group of newsletter subscribers that can be targeted for specific communications or campaigns.

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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this subscriber group |
| `--auto-add-members` | bool | Whether auto add members is enabled |
| `--auto-add-contacts` | bool | Whether auto add contacts is enabled |
| `--auto-add-bookings` | bool | Whether auto add bookings is enabled |
| `--auto-add-events` | bool | Whether auto add events is enabled |
| `--auto-add-visitors` | bool | Whether auto add visitors is enabled |
| `--auto-add-paying-members` | bool | Whether auto add paying members is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SubscriberGroup create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this subscriber group |
| `--news-letter-subscribers` | list, repeat flag | List of news letter subscribers linked to this record |
| `--added-news-letter-subscribers` | list, repeat flag | The added news letter subscribers value for this subscriber group |
| `--removed-news-letter-subscribers` | list, repeat flag | The removed news letter subscribers value for this subscriber group |
| `--auto-add-members` | bool | Whether auto add members is enabled |
| `--auto-add-contacts` | bool | Whether auto add contacts is enabled |
| `--auto-add-bookings` | bool | Whether auto add bookings is enabled |
| `--auto-add-events` | bool | Whether auto add events is enabled |
| `--auto-add-visitors` | bool | Whether auto add visitors is enabled |
| `--auto-add-paying-members` | bool | Whether auto add paying members is enabled |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this subscriber group |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this subscriber group |

#### SubscriberGroup update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this subscriber group |
| `--news-letter-subscribers` | list, repeat flag | List of news letter subscribers linked to this record |
| `--added-news-letter-subscribers` | list, repeat flag | The added news letter subscribers value for this subscriber group |
| `--removed-news-letter-subscribers` | list, repeat flag | The removed news letter subscribers value for this subscriber group |
| `--auto-add-members` | bool | Whether auto add members is enabled |
| `--auto-add-contacts` | bool | Whether auto add contacts is enabled |
| `--auto-add-bookings` | bool | Whether auto add bookings is enabled |
| `--auto-add-events` | bool | Whether auto add events is enabled |
| `--auto-add-visitors` | bool | Whether auto add visitors is enabled |
| `--auto-add-paying-members` | bool | Whether auto add paying members is enabled |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this subscriber group |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this subscriber group |

**List properties (only returned by `get`, not by `list`):** `NewsLetterSubscribers`, `AddedNewsLetterSubscribers`, `RemovedNewsLetterSubscribers`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=SubscriberGroups -->
