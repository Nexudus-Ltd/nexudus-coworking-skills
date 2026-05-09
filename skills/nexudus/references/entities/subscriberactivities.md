# SubscriberActivities

<!-- BEGIN:GENERATED entity=SubscriberActivities -->

SubscriberActivities support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus subscriberactivities list --agent` | List all subscriberactivities |
| `nexudus subscriberactivities list --id <id> --agent` | Filter by single ID |
| `nexudus subscriberactivities list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus subscriberactivities list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus subscriberactivities list --news-letter-subscriber-id <value> --news-letter-id <value> --agent` | Filter subscriberactivities by properties |
| `nexudus subscriberactivities list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus subscriberactivities get <id> --agent` | Get single subscriberactivity |

#### SubscriberActivity list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--news-letter-subscriber-id` | long |  |
| `--news-letter-id` | long |  |
| `--activiy-type` | enum |  |
| `--data` | string |  |
| `--created-on-local` | DateTime |  |
| `--from-created-on-local` | range | |
| `--to-created-on-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

<!-- END:GENERATED entity=SubscriberActivities -->
