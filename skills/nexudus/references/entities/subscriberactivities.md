# SubscriberActivities

<!-- BEGIN:GENERATED entity=SubscriberActivities -->

A **SubscriberActivity** records an interaction event for a newsletter subscriber, such as opening an email, clicking a link, or visiting a page.

SubscriberActivities support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus subscriberactivities list --agent` | List all subscriberactivities |
| `nexudus subscriberactivities list --id <id> --agent` | Filter by single ID |
| `nexudus subscriberactivities list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus subscriberactivities list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus subscriberactivities list --news-letter-subscriber-id <value> --news-letter-id <value> --agent` | Filter subscriberactivities by properties |
| `nexudus subscriberactivities list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus subscriberactivities list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus subscriberactivities get <id> --agent` | Get single subscriberactivity |

#### SubscriberActivity list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--news-letter-subscriber-id` | long | ID of the news letter subscriber linked to this record |
| `--news-letter-id` | long | ID of the news letter linked to this record |
| `--activiy-type` | enum | The activiy type value for this subscriber activity |
| `--data` | string | The data value for this subscriber activity |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--from-created-on-local` | range | |
| `--to-created-on-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SubscriberActivity sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### SubscriberActivity enum values

| Option | Valid values |
| ------ | ------------ |
| `--activiy-type` | `1` Open, `2` Click, `3` Visit |

<!-- END:GENERATED entity=SubscriberActivities -->
