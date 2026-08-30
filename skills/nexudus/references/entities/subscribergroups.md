# SubscriberGroups

<!-- BEGIN:GENERATED entity=SubscriberGroups -->

A newsletter subscriber group (SubscriberGroup) is a location-scoped audience segment for organising newsletter subscribers, either manually or through scheduled rules for members, contacts, attendees, visitors, and booking customers.

SubscriberGroups support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus subscribergroups list --agent` | List all subscribergroups |
| `nexudus subscribergroups list --id <id> --agent` | Filter by single ID |
| `nexudus subscribergroups list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus subscribergroups list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus subscribergroups list --business-id <value> --business-name <value> --agent` | Filter subscribergroups by properties |
| `nexudus subscribergroups list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus subscribergroups list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus subscribergroups get <id> --agent` | Get single subscribergroup |
| `nexudus subscribergroups create --business-id <value> --name <value> --agent` | Create subscribergroup |
| `nexudus subscribergroups update <id> --name "New Name" --agent` | Update subscribergroup |
| `nexudus subscribergroups delete <id> --yes --agent` | Delete subscribergroup (no prompt) |

#### SubscriberGroup list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this newsletter subscriber group. |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--name` | string | Required, unique name used to identify this newsletter subscriber group within the location. |
| `--auto-add-members` | bool | Whether the smart group automatically includes current members; enabled member criteria are reconciled on the smart-group update cycle. |
| `--auto-add-contacts` | bool | Whether the smart group automatically includes current contacts, meaning customers without an active contract. |
| `--auto-add-bookings` | bool | Whether the smart group automatically includes customers who have made a booking. |
| `--auto-add-events` | bool | Whether the smart group automatically includes event attendees. |
| `--auto-add-visitors` | bool | Whether the smart group automatically includes visitors to the location. |
| `--auto-add-paying-members` | bool | Whether the smart group automatically includes team paying members. |
| `--auto-membership` | bool | Whether this is a system-created membership group managed from location settings; read-only groups cannot be edited manually. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SubscriberGroup sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### SubscriberGroup create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this newsletter subscriber group. |
| `--name` | string, required | Required, unique name used to identify this newsletter subscriber group within the location. |
| `--news-letter-subscribers` | list, repeat flag | List of newsletter subscriber IDs manually assigned to this group; smart-group updates can also add or remove subscribers based on the enabled criteria. |
| `--added-news-letter-subscribers` | list, repeat flag | The added news letter subscribers value for this subscriber group |
| `--removed-news-letter-subscribers` | list, repeat flag | The removed news letter subscribers value for this subscriber group |
| `--auto-add-members` | bool | Whether the smart group automatically includes current members; enabled member criteria are reconciled on the smart-group update cycle. |
| `--auto-add-contacts` | bool | Whether the smart group automatically includes current contacts, meaning customers without an active contract. |
| `--auto-add-bookings` | bool | Whether the smart group automatically includes customers who have made a booking. |
| `--auto-add-events` | bool | Whether the smart group automatically includes event attendees. |
| `--auto-add-visitors` | bool | Whether the smart group automatically includes visitors to the location. |
| `--auto-add-paying-members` | bool | Whether the smart group automatically includes team paying members. |
| `--tariffs` | list, repeat flag | List of plan IDs used to restrict automatic member inclusion; an empty list means all member plan types, and the list is cleared unless automatic member inclusion or system-managed membership is enabled. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this subscriber group |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this subscriber group |

#### SubscriberGroup update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this newsletter subscriber group. |
| `--name` | string | Required, unique name used to identify this newsletter subscriber group within the location. |
| `--news-letter-subscribers` | list, repeat flag | List of newsletter subscriber IDs manually assigned to this group; smart-group updates can also add or remove subscribers based on the enabled criteria. |
| `--added-news-letter-subscribers` | list, repeat flag | The added news letter subscribers value for this subscriber group |
| `--removed-news-letter-subscribers` | list, repeat flag | The removed news letter subscribers value for this subscriber group |
| `--auto-add-members` | bool | Whether the smart group automatically includes current members; enabled member criteria are reconciled on the smart-group update cycle. |
| `--auto-add-contacts` | bool | Whether the smart group automatically includes current contacts, meaning customers without an active contract. |
| `--auto-add-bookings` | bool | Whether the smart group automatically includes customers who have made a booking. |
| `--auto-add-events` | bool | Whether the smart group automatically includes event attendees. |
| `--auto-add-visitors` | bool | Whether the smart group automatically includes visitors to the location. |
| `--auto-add-paying-members` | bool | Whether the smart group automatically includes team paying members. |
| `--tariffs` | list, repeat flag | List of plan IDs used to restrict automatic member inclusion; an empty list means all member plan types, and the list is cleared unless automatic member inclusion or system-managed membership is enabled. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this subscriber group |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this subscriber group |

**List properties (only returned by `get`, not by `list`):** `NewsLetterSubscribers`, `AddedNewsLetterSubscribers`, `RemovedNewsLetterSubscribers`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=SubscriberGroups -->
