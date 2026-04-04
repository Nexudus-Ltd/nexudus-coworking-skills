# CommunityPerks

<!-- BEGIN:GENERATED entity=CommunityPerks -->

CommunityPerks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communityperks list --agent` | List all communityperks |
| `nexudus communityperks list --id <id> --agent` | Filter by single ID |
| `nexudus communityperks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communityperks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communityperks list --business-id <value> --title <value> --agent` | Filter communityperks by properties |
| `nexudus communityperks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communityperks get <id> --agent` | Get single communityperk |
| `nexudus communityperks create --business-id <value> --title <value> --display-order <value> --click-count <value> --agent` | Create communityperk |
| `nexudus communityperks update <id> --name "New Name" --agent` | Update communityperk |
| `nexudus communityperks delete <id> --yes --agent` | Delete communityperk (no prompt) |

#### CommunityPerk list filter options

`--business-id`, `--title`, `--perk-url`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image`, `--new-large-image-url`, `--clear-large-image`, `--active`, `--group-name`, `--display-order`, `--show-in-home-page`, `--click-count`, `--only-for-contacts`, `--only-for-members`

#### CommunityPerk create options

`--business-id` (required), `--title` (required), `--perk-url`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image`, `--new-large-image-url`, `--clear-large-image`, `--active`, `--group-name`, `--display-order` (required), `--show-in-home-page`, `--click-count` (required), `--only-for-contacts`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

#### CommunityPerk update options

`--business-id`, `--title`, `--perk-url`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image`, `--new-large-image-url`, `--clear-large-image`, `--active`, `--group-name`, `--display-order`, `--show-in-home-page`, `--click-count`, `--only-for-contacts`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=CommunityPerks -->
