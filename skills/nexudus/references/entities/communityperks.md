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
| `nexudus communityperks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communityperks get <id> --agent` | Get single communityperk |
| `nexudus communityperks create --business-id <value> --title <value> --display-order <value> --click-count <value> --agent` | Create communityperk |
| `nexudus communityperks update <id> --name "New Name" --agent` | Update communityperk |
| `nexudus communityperks delete <id> --yes --agent` | Delete communityperk (no prompt) |

#### CommunityPerk list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this perk belongs to |
| `--title` | string | Name of the perk as displayed on the Members Portal and the Admin Panel |
| `--perk-url` | string | URL where customers are redirected when clicking the Claim button. If blank, no Claim button is shown. Must start with https:// |
| `--summary-text` | string | Short description shown under the perk title on the Perks listing page of the Members Portal |
| `--full-text` | string | Full description of the perk, displayed when a customer clicks on it from the Perks listing page |
| `--image-file-name` | string | File name of the small image shown on the Perks listing page alongside other perks |
| `--new-image-url` | string | URL of a new small image to upload for this perk |
| `--clear-image-file` | bool | Set to true to remove the current small image from this perk |
| `--large-image-file-name` | string | File name of the large image displayed under the perk title on the perk detail page |
| `--new-large-image-url` | string | URL of a new large image to upload for this perk |
| `--clear-large-image-file` | bool | Set to true to remove the current large image from this perk |
| `--active` | bool | Whether this perk is published and visible to customers on the Members Portal. When false, the perk is only visible on the Admin Panel |
| `--group-name` | string | Group or category this perk belongs to, used to organise perks on the Members Portal |
| `--display-order` | int | Position of this perk in the list relative to other perks. Lower values appear first |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--show-in-home-page` | bool | Whether to feature this perk on the Members Portal home page after users log in |
| `--click-count` | int | Number of times customers have clicked on this perk |
| `--from-click-count` | range | |
| `--to-click-count` | range | |
| `--only-for-contacts` | bool | Whether this perk is only available to contacts. Set both OnlyForContacts and OnlyForMembers to false to make the perk available to all customers |
| `--only-for-members` | bool | Whether this perk is only available to members. Set both OnlyForContacts and OnlyForMembers to false to make the perk available to all customers |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityPerk sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityPerk create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this perk belongs to |
| `--title` | string, required | Name of the perk as displayed on the Members Portal and the Admin Panel |
| `--perk-url` | string | URL where customers are redirected when clicking the Claim button. If blank, no Claim button is shown. Must start with https:// |
| `--summary-text` | string | Short description shown under the perk title on the Perks listing page of the Members Portal |
| `--full-text` | string | Full description of the perk, displayed when a customer clicks on it from the Perks listing page |
| `--new-image-url` | string | URL of a new small image to upload for this perk |
| `--clear-image-file` | bool | Set to true to remove the current small image from this perk |
| `--new-large-image-url` | string | URL of a new large image to upload for this perk |
| `--clear-large-image-file` | bool | Set to true to remove the current large image from this perk |
| `--active` | bool | Whether this perk is published and visible to customers on the Members Portal. When false, the perk is only visible on the Admin Panel |
| `--group-name` | string | Group or category this perk belongs to, used to organise perks on the Members Portal |
| `--display-order` | int, required | Position of this perk in the list relative to other perks. Lower values appear first |
| `--show-in-home-page` | bool | Whether to feature this perk on the Members Portal home page after users log in |
| `--click-count` | int, required | Number of times customers have clicked on this perk |
| `--only-for-contacts` | bool | Whether this perk is only available to contacts. Set both OnlyForContacts and OnlyForMembers to false to make the perk available to all customers |
| `--only-for-members` | bool | Whether this perk is only available to members. Set both OnlyForContacts and OnlyForMembers to false to make the perk available to all customers |
| `--tariffs` | list, repeat flag | IDs of the pricing plans (tariffs) whose members can see and claim this perk. Leave empty to make the perk available regardless of pricing plan |
| `--added-tariffs` | list, repeat flag | IDs of pricing plans to add to this perk's allowed tariffs |
| `--removed-tariffs` | list, repeat flag | IDs of pricing plans to remove from this perk's allowed tariffs |

#### CommunityPerk update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this perk belongs to |
| `--title` | string | Name of the perk as displayed on the Members Portal and the Admin Panel |
| `--perk-url` | string | URL where customers are redirected when clicking the Claim button. If blank, no Claim button is shown. Must start with https:// |
| `--summary-text` | string | Short description shown under the perk title on the Perks listing page of the Members Portal |
| `--full-text` | string | Full description of the perk, displayed when a customer clicks on it from the Perks listing page |
| `--new-image-url` | string | URL of a new small image to upload for this perk |
| `--clear-image-file` | bool | Set to true to remove the current small image from this perk |
| `--new-large-image-url` | string | URL of a new large image to upload for this perk |
| `--clear-large-image-file` | bool | Set to true to remove the current large image from this perk |
| `--active` | bool | Whether this perk is published and visible to customers on the Members Portal. When false, the perk is only visible on the Admin Panel |
| `--group-name` | string | Group or category this perk belongs to, used to organise perks on the Members Portal |
| `--display-order` | int | Position of this perk in the list relative to other perks. Lower values appear first |
| `--show-in-home-page` | bool | Whether to feature this perk on the Members Portal home page after users log in |
| `--click-count` | int | Number of times customers have clicked on this perk |
| `--only-for-contacts` | bool | Whether this perk is only available to contacts. Set both OnlyForContacts and OnlyForMembers to false to make the perk available to all customers |
| `--only-for-members` | bool | Whether this perk is only available to members. Set both OnlyForContacts and OnlyForMembers to false to make the perk available to all customers |
| `--tariffs` | list, repeat flag | IDs of the pricing plans (tariffs) whose members can see and claim this perk. Leave empty to make the perk available regardless of pricing plan |
| `--added-tariffs` | list, repeat flag | IDs of pricing plans to add to this perk's allowed tariffs |
| `--removed-tariffs` | list, repeat flag | IDs of pricing plans to remove from this perk's allowed tariffs |

### CommunityPerk (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=CommunityPerks -->
