# CommunityPerks

<!-- BEGIN:GENERATED entity=CommunityPerks -->

A **CommunityPerk** represents a perk, discount, or benefit that a location offers to its customers in partnership with other businesses.

Perks can be discounts, free trials, or any other benefit negotiated with a partner business — for example, 50% off a car rental or a free hot drink at a nearby café. They are published on the Members Portal where customers can view and claim them.

Use `Active` to control visibility — when `false`, the perk is only visible on the Admin Panel. Use `ShowInHomePage` to feature a perk on the Members Portal home page after users log in.

Availability can be restricted via `OnlyForContacts` and `OnlyForMembers`. If neither flag is set, the perk is available to all customers. Use `Tariffs` to further restrict access to customers on specific pricing plans.

Which perks are listed in a location is also controlled by the `Access.Data.Perks` **BusinessSetting**, whose value is an `eDataVisibilityCriteria` enum integer. This determines which locations' perks are visible to customers at a given location — for example `ThisLocationOnly` (7) shows only perks belonging to the current location, while `AllLocations` (3) shows perks from all locations in the network.

CommunityPerks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communityperks list --agent` | List all communityperks |
| `nexudus communityperks list --id <id> --agent` | Filter by single ID |
| `nexudus communityperks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communityperks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communityperks list --title <value> --agent` | Filter communityperks by properties |
| `nexudus communityperks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communityperks get <id> --agent` | Get single communityperk |
| `nexudus communityperks create --business-id <value> --title <value> --display-order <value> --click-count <value> --agent` | Create communityperk |
| `nexudus communityperks update <id> --name "New Name" --agent` | Update communityperk |
| `nexudus communityperks delete <id> --yes --agent` | Delete communityperk (no prompt) |

#### CommunityPerk list filter options

`--business-id` (long), `--title`, `--perk-url`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image-file` (bool), `--new-large-image-url`, `--clear-large-image-file` (bool), `--active` (bool), `--group-name`, `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--show-in-home-page` (bool), `--click-count` (int), `--from-click-count` (range), `--to-click-count` (range), `--only-for-contacts` (bool), `--only-for-members` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityPerk create options

`--business-id` (long, required), `--title` (required), `--perk-url`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image-file` (bool), `--new-large-image-url`, `--clear-large-image-file` (bool), `--active` (bool), `--group-name`, `--display-order` (int, required), `--show-in-home-page` (bool), `--click-count` (int, required), `--only-for-contacts` (bool), `--only-for-members` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

#### CommunityPerk update options

`--business-id` (long), `--title`, `--perk-url`, `--summary-text`, `--full-text`, `--new-image-url`, `--clear-image-file` (bool), `--new-large-image-url`, `--clear-large-image-file` (bool), `--active` (bool), `--group-name`, `--display-order` (int), `--show-in-home-page` (bool), `--click-count` (int), `--only-for-contacts` (bool), `--only-for-members` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag)

### CommunityPerk (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=CommunityPerks -->
