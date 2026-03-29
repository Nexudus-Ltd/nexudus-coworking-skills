# Teams

<!-- BEGIN:GENERATED entity=Teams -->

Teams support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus teams list --agent` | List all teams |
| `nexudus teams list --query "search" --agent` | Search teams by name |
| `nexudus teams list --page 2 --size 10 --agent` | Paginated list |
| `nexudus teams get <id> --agent` | Get single team |
| `nexudus teams create --business <value> --name <value> --agent` | Create team |
| `nexudus teams update <id> --name "New Name" --agent` | Update team |
| `nexudus teams delete <id> --yes --agent` | Delete team (no prompt) |

#### Team create options

`--business` (required), `--name` (required), `--description`, `--tunnel-private-group-id`, `--team-members` (list, repeat flag), `--added-team-members` (list, repeat flag), `--removed-team-members` (list, repeat flag), `--team-administrators` (list, repeat flag), `--added-team-administrators` (list, repeat flag), `--removed-team-administrators` (list, repeat flag), `--create-single-invoice-for-team`, `--use-special-prices`, `--paying-member-id`, `--default-member-tariff-id`, `--max-team-member-count`, `--transfer-credits-to-paying-member`, `--share-time-passes`, `--share-extra-services`, `--share-booking-credit`, `--discount-extra-services`, `--discount-time-passes`, `--discount-charges`, `--discount-tariffs`, `--profile-summary`, `--profile-tags`, `--profile-website`, `--google-maps-link`, `--profile-is-public`, `--has-community-group`, `--twitter`, `--facebook`, `--linkedin`, `--skype`, `--telegram`, `--github`, `--pinterest`, `--flickr`, `--instagram`, `--vimeo`, `--tumblr`, `--blogger`, `--disable-attendance-dashboard`, `--extra-services` (list, repeat flag), `--added-extra-services` (list, repeat flag), `--removed-extra-services` (list, repeat flag), `--new-team-logo-url`, `--clear-team-logo-file`, `--new-team-image-1-url`, `--clear-team-image-1-file`, `--new-team-image-2-url`, `--clear-team-image-2-file`, `--new-team-image-3-url`, `--clear-team-image-3-file`

#### Team update options

`--name`, `--description`, `--tunnel-private-group-id`, `--team-members` (list, repeat flag), `--added-team-members` (list, repeat flag), `--removed-team-members` (list, repeat flag), `--team-administrators` (list, repeat flag), `--added-team-administrators` (list, repeat flag), `--removed-team-administrators` (list, repeat flag), `--create-single-invoice-for-team`, `--use-special-prices`, `--paying-member-id`, `--default-member-tariff-id`, `--max-team-member-count`, `--transfer-credits-to-paying-member`, `--share-time-passes`, `--share-extra-services`, `--share-booking-credit`, `--discount-extra-services`, `--discount-time-passes`, `--discount-charges`, `--discount-tariffs`, `--profile-summary`, `--profile-tags`, `--profile-website`, `--google-maps-link`, `--profile-is-public`, `--has-community-group`, `--twitter`, `--facebook`, `--linkedin`, `--skype`, `--telegram`, `--github`, `--pinterest`, `--flickr`, `--instagram`, `--vimeo`, `--tumblr`, `--blogger`, `--disable-attendance-dashboard`, `--extra-services` (list, repeat flag), `--added-extra-services` (list, repeat flag), `--removed-extra-services` (list, repeat flag), `--new-team-logo-url`, `--clear-team-logo-file`, `--new-team-image-1-url`, `--clear-team-image-1-file`, `--new-team-image-2-url`, `--clear-team-image-2-file`, `--new-team-image-3-url`, `--clear-team-image-3-file`

### Team (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`

**List properties (only returned by `get`, not by `list`):** `TeamMembers`, `AddedTeamMembers`, `RemovedTeamMembers`, `TeamAdministrators`, `AddedTeamAdministrators`, `RemovedTeamAdministrators`, `ExtraServices`, `AddedExtraServices`, `RemovedExtraServices`

<!-- END:GENERATED entity=Teams -->
