# SubscriberGroups

<!-- BEGIN:GENERATED entity=SubscriberGroups -->

A newsletter subscriber group (SubscriberGroup) is a location-scoped audience segment used to target newsletters; subscribers are either assigned manually or collected by smart-group criteria for members, contacts, event attendees, visitors, team paying members, and booking customers, which a background job reconciles every 12 hours.

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
| `--business-id` | long | ID of the location that owns this newsletter subscriber group; a group name only has to be unique within this location, and smart-group criteria only look at customers, bookings, and resources belonging to it. |
| `--business-name` | string | Display value for Business.Name. |
| `--name` | string | Required name of the group, shown when picking an audience for a newsletter and unique per location; for system-managed membership groups it mirrors the plan name and is maintained automatically. |
| `--auto-add-members` | bool | Whether the group automatically collects current members, meaning active customers who hold an active contract at this location; when Tariffs lists plans, only contracts on those plans are collected. |
| `--auto-add-contacts` | bool | Whether the group automatically collects current contacts, meaning active customers at this location who have no active contract. |
| `--auto-add-bookings` | bool | Whether the group automatically collects active customers who have made a booking for a resource belonging to this location. |
| `--auto-add-events` | bool | Whether the group automatically collects customers registered as event attendees, subscribing the email address held on the attendee record. |
| `--auto-add-visitors` | bool | Whether the group automatically collects active customers who have a visitor record, subscribing the email address held on the visitor record. |
| `--auto-add-paying-members` | bool | Whether the group automatically collects active customers who are the paying member of a team that is billed with a single team invoice; the Tariffs plan restriction does not apply to this criterion. |
| `--auto-membership` | bool | Whether this group is system-managed: one such group is created per plan while the location's Newsletter.AutoGroupMembership setting is on, named after the plan and linked to it through Tariffs, and it is renamed, emptied, and removed automatically; it cannot be set here, and these groups should not be edited at all because the admin UI blocks editing them. |
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
| `--business-id` | long, required | ID of the location that owns this newsletter subscriber group; a group name only has to be unique within this location, and smart-group criteria only look at customers, bookings, and resources belonging to it. |
| `--name` | string, required | Required name of the group, shown when picking an audience for a newsletter and unique per location; for system-managed membership groups it mirrors the plan name and is maintained automatically. |
| `--news-letter-subscribers` | list, repeat flag | List of newsletter subscriber IDs in this group; the relationship is owned by the subscriber side, so change group membership through the NewsLetterSubscriber record (its Groups list) rather than here, and note that on a group with any smart-group criterion enabled the 12-hourly update removes every subscriber who no longer matches, including manually added ones. |
| `--added-news-letter-subscribers` | list, repeat flag | IDs added to the NewsLetterSubscribers relationship. |
| `--removed-news-letter-subscribers` | list, repeat flag | IDs removed from the NewsLetterSubscribers relationship. |
| `--auto-add-members` | bool | Whether the group automatically collects current members, meaning active customers who hold an active contract at this location; when Tariffs lists plans, only contracts on those plans are collected. |
| `--auto-add-contacts` | bool | Whether the group automatically collects current contacts, meaning active customers at this location who have no active contract. |
| `--auto-add-bookings` | bool | Whether the group automatically collects active customers who have made a booking for a resource belonging to this location. |
| `--auto-add-events` | bool | Whether the group automatically collects customers registered as event attendees, subscribing the email address held on the attendee record. |
| `--auto-add-visitors` | bool | Whether the group automatically collects active customers who have a visitor record, subscribing the email address held on the visitor record. |
| `--auto-add-paying-members` | bool | Whether the group automatically collects active customers who are the paying member of a team that is billed with a single team invoice; the Tariffs plan restriction does not apply to this criterion. |
| `--tariffs` | list, repeat flag | List of plan IDs restricting which members are collected automatically; it applies only to the members criterion (AutoAddMembers) and to system-managed membership groups, an empty list means every plan, and the list is cleared on save when neither AutoAddMembers nor AutoMembership is enabled. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |

#### SubscriberGroup update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this newsletter subscriber group; a group name only has to be unique within this location, and smart-group criteria only look at customers, bookings, and resources belonging to it. |
| `--name` | string | Required name of the group, shown when picking an audience for a newsletter and unique per location; for system-managed membership groups it mirrors the plan name and is maintained automatically. |
| `--news-letter-subscribers` | list, repeat flag | List of newsletter subscriber IDs in this group; the relationship is owned by the subscriber side, so change group membership through the NewsLetterSubscriber record (its Groups list) rather than here, and note that on a group with any smart-group criterion enabled the 12-hourly update removes every subscriber who no longer matches, including manually added ones. |
| `--added-news-letter-subscribers` | list, repeat flag | IDs added to the NewsLetterSubscribers relationship. |
| `--removed-news-letter-subscribers` | list, repeat flag | IDs removed from the NewsLetterSubscribers relationship. |
| `--auto-add-members` | bool | Whether the group automatically collects current members, meaning active customers who hold an active contract at this location; when Tariffs lists plans, only contracts on those plans are collected. |
| `--auto-add-contacts` | bool | Whether the group automatically collects current contacts, meaning active customers at this location who have no active contract. |
| `--auto-add-bookings` | bool | Whether the group automatically collects active customers who have made a booking for a resource belonging to this location. |
| `--auto-add-events` | bool | Whether the group automatically collects customers registered as event attendees, subscribing the email address held on the attendee record. |
| `--auto-add-visitors` | bool | Whether the group automatically collects active customers who have a visitor record, subscribing the email address held on the visitor record. |
| `--auto-add-paying-members` | bool | Whether the group automatically collects active customers who are the paying member of a team that is billed with a single team invoice; the Tariffs plan restriction does not apply to this criterion. |
| `--tariffs` | list, repeat flag | List of plan IDs restricting which members are collected automatically; it applies only to the members criterion (AutoAddMembers) and to system-managed membership groups, an empty list means every plan, and the list is cleared on save when neither AutoAddMembers nor AutoMembership is enabled. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |

**List properties (only returned by `get`, not by `list`):** `NewsLetterSubscribers`, `AddedNewsLetterSubscribers`, `RemovedNewsLetterSubscribers`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=SubscriberGroups -->
