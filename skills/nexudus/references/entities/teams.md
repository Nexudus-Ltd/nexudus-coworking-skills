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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Team name |
| `--description` | string | Team description |
| `--tunnel-private-group-id` | string | Tunnel private group ID |
| `--create-single-invoice-for-team` | bool | Create a single invoice for the team |
| `--use-special-prices` | bool | Use special prices |
| `--paying-member-id` | long |  |
| `--default-member-tariff-id` | long |  |
| `--max-team-member-count` | decimal | Maximum team member count |
| `--from-max-team-member-count` | range | |
| `--to-max-team-member-count` | range | |
| `--transfer-credits-to-paying-member` | bool | Transfer credits to paying member |
| `--share-time-passes` | bool | Share time passes |
| `--share-extra-services` | bool | Share extra services |
| `--share-booking-credit` | bool | Share booking credit |
| `--discount-extra-services` | decimal | Discount for extra services |
| `--from-discount-extra-services` | range | |
| `--to-discount-extra-services` | range | |
| `--discount-time-passes` | decimal | Discount for time passes |
| `--from-discount-time-passes` | range | |
| `--to-discount-time-passes` | range | |
| `--discount-charges` | decimal | Discount for charges |
| `--from-discount-charges` | range | |
| `--to-discount-charges` | range | |
| `--discount-tariffs` | decimal | Discount for tariffs |
| `--from-discount-tariffs` | range | |
| `--to-discount-tariffs` | range | |
| `--profile-summary` | string | Profile summary |
| `--profile-tags` | string | Profile tags |
| `--profile-website` | string | Profile website |
| `--google-maps-link` | string | Google Maps link |
| `--profile-is-public` | bool | Whether the profile is public |
| `--has-community-group` | bool | Whether the team has a community group |
| `--new-team-logo-url` | string |  |
| `--clear-team-logo-file` | bool |  |
| `--new-team-image1-url` | string |  |
| `--clear-team-image1-file` | bool |  |
| `--new-team-image2-url` | string |  |
| `--clear-team-image2-file` | bool |  |
| `--new-team-image3-url` | string |  |
| `--clear-team-image3-file` | bool |  |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook URL |
| `--linkedin` | string | LinkedIn URL |
| `--skype` | string | Skype handle |
| `--telegram` | string | Telegram handle |
| `--github` | string | GitHub URL |
| `--pinterest` | string | Pinterest URL |
| `--flickr` | string | Flickr URL |
| `--instagram` | string | Instagram URL |
| `--vimeo` | string | Vimeo URL |
| `--tumblr` | string | Tumblr URL |
| `--blogger` | string | Blogger URL |
| `--disable-attendance-dashboard` | bool | Disable attendance dashboard |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Team create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required | Team name |
| `--description` | string | Team description |
| `--tunnel-private-group-id` | string | Tunnel private group ID |
| `--team-members` | list, repeat flag |  |
| `--added-team-members` | list, repeat flag |  |
| `--removed-team-members` | list, repeat flag |  |
| `--team-administrators` | list, repeat flag |  |
| `--added-team-administrators` | list, repeat flag |  |
| `--removed-team-administrators` | list, repeat flag |  |
| `--create-single-invoice-for-team` | bool | Create a single invoice for the team |
| `--use-special-prices` | bool | Use special prices |
| `--paying-member-id` | long |  |
| `--default-member-tariff-id` | long |  |
| `--max-team-member-count` | decimal | Maximum team member count |
| `--transfer-credits-to-paying-member` | bool | Transfer credits to paying member |
| `--share-time-passes` | bool | Share time passes |
| `--share-extra-services` | bool | Share extra services |
| `--share-booking-credit` | bool | Share booking credit |
| `--discount-extra-services` | decimal | Discount for extra services |
| `--discount-time-passes` | decimal | Discount for time passes |
| `--discount-charges` | decimal | Discount for charges |
| `--discount-tariffs` | decimal | Discount for tariffs |
| `--profile-summary` | string | Profile summary |
| `--profile-tags` | string | Profile tags |
| `--profile-website` | string | Profile website |
| `--google-maps-link` | string | Google Maps link |
| `--profile-is-public` | bool | Whether the profile is public |
| `--has-community-group` | bool | Whether the team has a community group |
| `--new-team-logo-url` | string |  |
| `--clear-team-logo-file` | bool |  |
| `--new-team-image1-url` | string |  |
| `--clear-team-image1-file` | bool |  |
| `--new-team-image2-url` | string |  |
| `--clear-team-image2-file` | bool |  |
| `--new-team-image3-url` | string |  |
| `--clear-team-image3-file` | bool |  |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook URL |
| `--linkedin` | string | LinkedIn URL |
| `--skype` | string | Skype handle |
| `--telegram` | string | Telegram handle |
| `--github` | string | GitHub URL |
| `--pinterest` | string | Pinterest URL |
| `--flickr` | string | Flickr URL |
| `--instagram` | string | Instagram URL |
| `--vimeo` | string | Vimeo URL |
| `--tumblr` | string | Tumblr URL |
| `--blogger` | string | Blogger URL |
| `--disable-attendance-dashboard` | bool | Disable attendance dashboard |
| `--extra-services` | list, repeat flag |  |
| `--added-extra-services` | list, repeat flag |  |
| `--removed-extra-services` | list, repeat flag |  |

#### Team update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Team name |
| `--description` | string | Team description |
| `--tunnel-private-group-id` | string | Tunnel private group ID |
| `--team-members` | list, repeat flag |  |
| `--added-team-members` | list, repeat flag |  |
| `--removed-team-members` | list, repeat flag |  |
| `--team-administrators` | list, repeat flag |  |
| `--added-team-administrators` | list, repeat flag |  |
| `--removed-team-administrators` | list, repeat flag |  |
| `--create-single-invoice-for-team` | bool | Create a single invoice for the team |
| `--use-special-prices` | bool | Use special prices |
| `--paying-member-id` | long |  |
| `--default-member-tariff-id` | long |  |
| `--max-team-member-count` | decimal | Maximum team member count |
| `--transfer-credits-to-paying-member` | bool | Transfer credits to paying member |
| `--share-time-passes` | bool | Share time passes |
| `--share-extra-services` | bool | Share extra services |
| `--share-booking-credit` | bool | Share booking credit |
| `--discount-extra-services` | decimal | Discount for extra services |
| `--discount-time-passes` | decimal | Discount for time passes |
| `--discount-charges` | decimal | Discount for charges |
| `--discount-tariffs` | decimal | Discount for tariffs |
| `--profile-summary` | string | Profile summary |
| `--profile-tags` | string | Profile tags |
| `--profile-website` | string | Profile website |
| `--google-maps-link` | string | Google Maps link |
| `--profile-is-public` | bool | Whether the profile is public |
| `--has-community-group` | bool | Whether the team has a community group |
| `--new-team-logo-url` | string |  |
| `--clear-team-logo-file` | bool |  |
| `--new-team-image1-url` | string |  |
| `--clear-team-image1-file` | bool |  |
| `--new-team-image2-url` | string |  |
| `--clear-team-image2-file` | bool |  |
| `--new-team-image3-url` | string |  |
| `--clear-team-image3-file` | bool |  |
| `--twitter` | string | Twitter handle |
| `--facebook` | string | Facebook URL |
| `--linkedin` | string | LinkedIn URL |
| `--skype` | string | Skype handle |
| `--telegram` | string | Telegram handle |
| `--github` | string | GitHub URL |
| `--pinterest` | string | Pinterest URL |
| `--flickr` | string | Flickr URL |
| `--instagram` | string | Instagram URL |
| `--vimeo` | string | Vimeo URL |
| `--tumblr` | string | Tumblr URL |
| `--blogger` | string | Blogger URL |
| `--disable-attendance-dashboard` | bool | Disable attendance dashboard |
| `--extra-services` | list, repeat flag |  |
| `--added-extra-services` | list, repeat flag |  |
| `--removed-extra-services` | list, repeat flag |  |

### Team (key fields)

`Id`, `BusinessName`, `Name`

**List properties (only returned by `get`, not by `list`):** `TeamMembers`, `AddedTeamMembers`, `RemovedTeamMembers`, `TeamAdministrators`, `AddedTeamAdministrators`, `RemovedTeamAdministrators`, `ExtraServices`, `AddedExtraServices`, `RemovedExtraServices`

<!-- END:GENERATED entity=Teams -->
