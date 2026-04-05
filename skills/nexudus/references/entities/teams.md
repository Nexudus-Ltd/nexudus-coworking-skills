# Teams

<!-- BEGIN:GENERATED entity=Teams -->

Teams support Search, Get, Create, Update, Delete.
Teams also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus teams list --agent` | List all teams |
| `nexudus teams list --id <id> --agent` | Filter by single ID |
| `nexudus teams list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus teams list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus teams list --name <value> --agent` | Filter teams by properties |
| `nexudus teams list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus teams get <id> --agent` | Get single team |
| `nexudus teams create --business-id <value> --name <value> --agent` | Create team |
| `nexudus teams update <id> --name "New Name" --agent` | Update team |
| `nexudus teams delete <id> --yes --agent` | Delete team (no prompt) |
| `nexudus teams run-command <key> <ids> --agent` | Run entity command |

#### Team list filter options

`--business-id`, `--name`, `--description`, `--tunnel-private-group-id`, `--create-single-invoice-for-team`, `--use-special-prices`, `--paying-member-id`, `--default-member-tariff-id`, `--max-team-member-count`, `--from-max-team-member-count` (range), `--to-max-team-member-count` (range), `--transfer-credits-to-paying-member`, `--share-time-passes`, `--share-extra-services`, `--share-booking-credit`, `--discount-extra-services`, `--from-discount-extra-services` (range), `--to-discount-extra-services` (range), `--discount-time-passes`, `--from-discount-time-passes` (range), `--to-discount-time-passes` (range), `--discount-charges`, `--from-discount-charges` (range), `--to-discount-charges` (range), `--discount-tariffs`, `--from-discount-tariffs` (range), `--to-discount-tariffs` (range), `--profile-summary`, `--profile-tags`, `--profile-website`, `--google-maps-link`, `--profile-is-public`, `--has-community-group`, `--new-team-logo-url`, `--clear-team-logo-file`, `--new-team-image1-url`, `--clear-team-image1-file`, `--new-team-image2-url`, `--clear-team-image2-file`, `--new-team-image3-url`, `--clear-team-image3-file`, `--twitter`, `--facebook`, `--linkedin`, `--skype`, `--telegram`, `--github`, `--pinterest`, `--flickr`, `--instagram`, `--vimeo`, `--tumblr`, `--blogger`, `--disable-attendance-dashboard`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Team create options

`--business-id` (required), `--name` (required), `--description`, `--tunnel-private-group-id`, `--team-members` (list, repeat flag), `--added-team-members` (list, repeat flag), `--removed-team-members` (list, repeat flag), `--team-administrators` (list, repeat flag), `--added-team-administrators` (list, repeat flag), `--removed-team-administrators` (list, repeat flag), `--create-single-invoice-for-team`, `--use-special-prices`, `--paying-member-id`, `--default-member-tariff-id`, `--max-team-member-count`, `--transfer-credits-to-paying-member`, `--share-time-passes`, `--share-extra-services`, `--share-booking-credit`, `--discount-extra-services`, `--discount-time-passes`, `--discount-charges`, `--discount-tariffs`, `--profile-summary`, `--profile-tags`, `--profile-website`, `--google-maps-link`, `--profile-is-public`, `--has-community-group`, `--new-team-logo-url`, `--clear-team-logo-file`, `--new-team-image1-url`, `--clear-team-image1-file`, `--new-team-image2-url`, `--clear-team-image2-file`, `--new-team-image3-url`, `--clear-team-image3-file`, `--twitter`, `--facebook`, `--linkedin`, `--skype`, `--telegram`, `--github`, `--pinterest`, `--flickr`, `--instagram`, `--vimeo`, `--tumblr`, `--blogger`, `--disable-attendance-dashboard`, `--extra-services` (list, repeat flag), `--added-extra-services` (list, repeat flag), `--removed-extra-services` (list, repeat flag)

#### Team update options

`--business-id`, `--name`, `--description`, `--tunnel-private-group-id`, `--team-members` (list, repeat flag), `--added-team-members` (list, repeat flag), `--removed-team-members` (list, repeat flag), `--team-administrators` (list, repeat flag), `--added-team-administrators` (list, repeat flag), `--removed-team-administrators` (list, repeat flag), `--create-single-invoice-for-team`, `--use-special-prices`, `--paying-member-id`, `--default-member-tariff-id`, `--max-team-member-count`, `--transfer-credits-to-paying-member`, `--share-time-passes`, `--share-extra-services`, `--share-booking-credit`, `--discount-extra-services`, `--discount-time-passes`, `--discount-charges`, `--discount-tariffs`, `--profile-summary`, `--profile-tags`, `--profile-website`, `--google-maps-link`, `--profile-is-public`, `--has-community-group`, `--new-team-logo-url`, `--clear-team-logo-file`, `--new-team-image1-url`, `--clear-team-image1-file`, `--new-team-image2-url`, `--clear-team-image2-file`, `--new-team-image3-url`, `--clear-team-image3-file`, `--twitter`, `--facebook`, `--linkedin`, `--skype`, `--telegram`, `--github`, `--pinterest`, `--flickr`, `--instagram`, `--vimeo`, `--tumblr`, `--blogger`, `--disable-attendance-dashboard`, `--extra-services` (list, repeat flag), `--added-extra-services` (list, repeat flag), `--removed-extra-services` (list, repeat flag)

### Team (key fields)

`Id`, `BusinessName`, `Name`

**List properties (only returned by `get`, not by `list`):** `TeamMembers`, `AddedTeamMembers`, `RemovedTeamMembers`, `TeamAdministrators`, `AddedTeamAdministrators`, `RemovedTeamAdministrators`, `ExtraServices`, `AddedExtraServices`, `RemovedExtraServices`

<!-- END:GENERATED entity=Teams -->
