# Teams

<!-- BEGIN:GENERATED entity=Teams -->

A Team is a group of customers at one location that can consolidate invoices under a paying customer and share selected credits, passes, booking credit, and access-related benefits.

Teams support Search, Get, Create, Update, Delete.
Teams also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus teams list --agent` | List all teams |
| `nexudus teams list --id <id> --agent` | Filter by single ID |
| `nexudus teams list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus teams list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus teams list --business-name <value> --name <value> --agent` | Filter teams by properties |
| `nexudus teams list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus teams list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus teams get <id> --agent` | Get single team |
| `nexudus teams create --business-id <value> --name <value> --agent` | Create team |
| `nexudus teams update <id> --name "New Name" --agent` | Update team |
| `nexudus teams delete <id> --yes --agent` | Delete team (no prompt) |
| `nexudus teams run-command <key> <ids> --agent` | Run entity command |

#### Team list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this team belongs to |
| `--business-name` | string | Business name |
| `--name` | string | Required team name, unique within the location and limited to 254 characters |
| `--description` | string | Optional internal description of the team |
| `--tunnel-private-group-id` | string | Optional private network or VLAN group identifier used by supported access-control and WiFi integrations |
| `--create-single-invoice-for-team` | bool | Whether the designated paying customer receives consolidated invoices for the other team members; requires a paying customer who belongs to the team |
| `--use-special-prices` | bool | Whether members use the designated paying customer's special prices |
| `--paying-member-id` | long | ID of the customer who pays for this team; required and must be a team member when consolidated invoices or credit pooling is enabled |
| `--paying-member-full-name` | string | Paying member full name |
| `--paying-member-coworker-type` | string | Paying member coworker type |
| `--paying-member-billing-name` | string | Paying member billing name |
| `--paying-member-company-name` | string | Paying member company name |
| `--default-member-tariff-id` | long | Optional ID of the plan proposed as the default for team members when a customer is added to the team by a team administrator. |
| `--default-member-tariff-name` | string | Default member tariff name |
| `--max-team-member-count` | decimal | Optional maximum number of customers for this team |
| `--from-max-team-member-count` | range | |
| `--to-max-team-member-count` | range | |
| `--transfer-credits-to-paying-member` | bool | Whether team members' credits are pooled with the paying customer; requires a paying customer and supports teams of up to 50 customers |
| `--share-time-passes` | bool | Whether team members share passes through the paying customer; with credit pooling enabled, their combined included passes cannot exceed 500 |
| `--share-extra-services` | bool | Whether team members share time credits and printing credits through the paying customer |
| `--share-booking-credit` | bool | Whether team members can use the paying customer's booking credit for their bookings |
| `--discount-extra-services` | decimal | Optional percentage discount on booking rates; the highest applicable team or plan discount is used |
| `--from-discount-extra-services` | range | |
| `--to-discount-extra-services` | range | |
| `--discount-time-passes` | decimal | Optional percentage discount on passes; the highest applicable team or plan discount is used |
| `--from-discount-time-passes` | range | |
| `--to-discount-time-passes` | range | |
| `--discount-charges` | decimal | Optional percentage discount on one-off charges; the highest applicable team or plan discount is used |
| `--from-discount-charges` | range | |
| `--to-discount-charges` | range | |
| `--discount-tariffs` | decimal | Optional percentage discount on plans; the highest discount configured on any of the customer's teams is used |
| `--from-discount-tariffs` | range | |
| `--to-discount-tariffs` | range | |
| `--profile-summary` | string | Optional HTML profile summary displayed in the public team directory |
| `--profile-tags` | string | Optional public-directory tags used to find this team, limited to 254 characters |
| `--profile-website` | string | Optional website URL displayed on the public team profile, limited to 254 characters |
| `--google-maps-link` | string | Optional Google Maps URL displayed on the public team profile, limited to 1024 characters |
| `--profile-is-public` | bool | Whether this team's profile can appear in the public directory |
| `--has-community-group` | bool | Whether Nexudus automatically creates and maintains a discussion-board community group for this team |
| `--team-logo-file-name` | string | Current file name of the team logo (read-only; upload via the corresponding URL field) |
| `--new-team-logo-url` | string | URL of a new file to upload as the team logo |
| `--clear-team-logo-file` | bool | Set to true to remove the current team logo file |
| `--team-image1-file-name` | string | Current file name of the team image1 (read-only; upload via the corresponding URL field) |
| `--new-team-image1-url` | string | URL of a new file to upload as the team image1 |
| `--clear-team-image1-file` | bool | Set to true to remove the current team image1 file |
| `--team-image2-file-name` | string | Current file name of the team image2 (read-only; upload via the corresponding URL field) |
| `--new-team-image2-url` | string | URL of a new file to upload as the team image2 |
| `--clear-team-image2-file` | bool | Set to true to remove the current team image2 file |
| `--team-image3-file-name` | string | Current file name of the team image3 (read-only; upload via the corresponding URL field) |
| `--new-team-image3-url` | string | URL of a new file to upload as the team image3 |
| `--clear-team-image3-file` | bool | Set to true to remove the current team image3 file |
| `--twitter` | string | Optional X or Twitter profile URL, limited to 254 characters |
| `--facebook` | string | Optional Facebook profile URL, limited to 254 characters |
| `--linkedin` | string | Optional LinkedIn profile URL, limited to 254 characters |
| `--skype` | string | Optional Skype handle or URL, limited to 254 characters |
| `--telegram` | string | Optional Telegram handle or URL, limited to 254 characters |
| `--github` | string | Optional GitHub profile or organization URL, limited to 254 characters |
| `--pinterest` | string | Optional Pinterest profile URL, limited to 254 characters |
| `--flickr` | string | Optional Flickr profile URL, limited to 254 characters |
| `--instagram` | string | Optional Instagram profile URL, limited to 254 characters |
| `--vimeo` | string | Optional Vimeo profile URL, limited to 254 characters |
| `--tumblr` | string | Optional Tumblr profile URL, limited to 254 characters |
| `--blogger` | string | Optional Blogger profile URL, limited to 254 characters |
| `--active-contracts` | int | Read-only count of active contracts across the team's members, refreshed after membership and contract changes |
| `--from-active-contracts` | range | |
| `--to-active-contracts` | range | |
| `--avg-churn-probability` | decimal | Read-only average churn probability predicted by the analytics process for the team's customers |
| `--from-avg-churn-probability` | range | |
| `--to-avg-churn-probability` | range | |
| `--engagement-level` | string | Read-only engagement classification calculated by the analytics process for the team |
| `--disable-attendance-dashboard` | bool | Whether to hide this team's attendance dashboard from its customers |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Team sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Team create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this team belongs to |
| `--name` | string, required | Required team name, unique within the location and limited to 254 characters |
| `--description` | string | Optional internal description of the team |
| `--tunnel-private-group-id` | string | Optional private network or VLAN group identifier used by supported access-control and WiFi integrations |
| `--team-members` | list, repeat flag | List of customer IDs belonging to this team; the paying customer must be included when consolidated invoices or credit pooling is enabled |
| `--added-team-members` | list, repeat flag | The added team members value for this team |
| `--removed-team-members` | list, repeat flag | The removed team members value for this team |
| `--team-administrators` | list, repeat flag | List of customer IDs designated as team administrators |
| `--added-team-administrators` | list, repeat flag | The added team administrators value for this team |
| `--removed-team-administrators` | list, repeat flag | The removed team administrators value for this team |
| `--create-single-invoice-for-team` | bool | Whether the designated paying customer receives consolidated invoices for the other team members; requires a paying customer who belongs to the team |
| `--use-special-prices` | bool | Whether members use the designated paying customer's special prices |
| `--paying-member-id` | long | ID of the customer who pays for this team; required and must be a team member when consolidated invoices or credit pooling is enabled |
| `--default-member-tariff-id` | long | Optional ID of the plan proposed as the default for team members when a customer is added to the team by a team administrator. |
| `--max-team-member-count` | decimal | Optional maximum number of customers for this team |
| `--transfer-credits-to-paying-member` | bool | Whether team members' credits are pooled with the paying customer; requires a paying customer and supports teams of up to 50 customers |
| `--share-time-passes` | bool | Whether team members share passes through the paying customer; with credit pooling enabled, their combined included passes cannot exceed 500 |
| `--share-extra-services` | bool | Whether team members share time credits and printing credits through the paying customer |
| `--share-booking-credit` | bool | Whether team members can use the paying customer's booking credit for their bookings |
| `--discount-extra-services` | decimal | Optional percentage discount on booking rates; the highest applicable team or plan discount is used |
| `--discount-time-passes` | decimal | Optional percentage discount on passes; the highest applicable team or plan discount is used |
| `--discount-charges` | decimal | Optional percentage discount on one-off charges; the highest applicable team or plan discount is used |
| `--discount-tariffs` | decimal | Optional percentage discount on plans; the highest discount configured on any of the customer's teams is used |
| `--profile-summary` | string | Optional HTML profile summary displayed in the public team directory |
| `--profile-tags` | string | Optional public-directory tags used to find this team, limited to 254 characters |
| `--profile-website` | string | Optional website URL displayed on the public team profile, limited to 254 characters |
| `--google-maps-link` | string | Optional Google Maps URL displayed on the public team profile, limited to 1024 characters |
| `--profile-is-public` | bool | Whether this team's profile can appear in the public directory |
| `--has-community-group` | bool | Whether Nexudus automatically creates and maintains a discussion-board community group for this team |
| `--new-team-logo-url` | string | URL of a new file to upload as the team logo |
| `--clear-team-logo-file` | bool | Set to true to remove the current team logo file |
| `--new-team-image1-url` | string | URL of a new file to upload as the team image1 |
| `--clear-team-image1-file` | bool | Set to true to remove the current team image1 file |
| `--new-team-image2-url` | string | URL of a new file to upload as the team image2 |
| `--clear-team-image2-file` | bool | Set to true to remove the current team image2 file |
| `--new-team-image3-url` | string | URL of a new file to upload as the team image3 |
| `--clear-team-image3-file` | bool | Set to true to remove the current team image3 file |
| `--twitter` | string | Optional X or Twitter profile URL, limited to 254 characters |
| `--facebook` | string | Optional Facebook profile URL, limited to 254 characters |
| `--linkedin` | string | Optional LinkedIn profile URL, limited to 254 characters |
| `--skype` | string | Optional Skype handle or URL, limited to 254 characters |
| `--telegram` | string | Optional Telegram handle or URL, limited to 254 characters |
| `--github` | string | Optional GitHub profile or organization URL, limited to 254 characters |
| `--pinterest` | string | Optional Pinterest profile URL, limited to 254 characters |
| `--flickr` | string | Optional Flickr profile URL, limited to 254 characters |
| `--instagram` | string | Optional Instagram profile URL, limited to 254 characters |
| `--vimeo` | string | Optional Vimeo profile URL, limited to 254 characters |
| `--tumblr` | string | Optional Tumblr profile URL, limited to 254 characters |
| `--blogger` | string | Optional Blogger profile URL, limited to 254 characters |
| `--disable-attendance-dashboard` | bool | Whether to hide this team's attendance dashboard from its customers |
| `--extra-services` | list, repeat flag | List of booking rate IDs linked to this team |
| `--added-extra-services` | list, repeat flag | The added extra services value for this team |
| `--removed-extra-services` | list, repeat flag | The removed extra services value for this team |

#### Team update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this team belongs to |
| `--name` | string | Required team name, unique within the location and limited to 254 characters |
| `--description` | string | Optional internal description of the team |
| `--tunnel-private-group-id` | string | Optional private network or VLAN group identifier used by supported access-control and WiFi integrations |
| `--team-members` | list, repeat flag | List of customer IDs belonging to this team; the paying customer must be included when consolidated invoices or credit pooling is enabled |
| `--added-team-members` | list, repeat flag | The added team members value for this team |
| `--removed-team-members` | list, repeat flag | The removed team members value for this team |
| `--team-administrators` | list, repeat flag | List of customer IDs designated as team administrators |
| `--added-team-administrators` | list, repeat flag | The added team administrators value for this team |
| `--removed-team-administrators` | list, repeat flag | The removed team administrators value for this team |
| `--create-single-invoice-for-team` | bool | Whether the designated paying customer receives consolidated invoices for the other team members; requires a paying customer who belongs to the team |
| `--use-special-prices` | bool | Whether members use the designated paying customer's special prices |
| `--paying-member-id` | long | ID of the customer who pays for this team; required and must be a team member when consolidated invoices or credit pooling is enabled |
| `--default-member-tariff-id` | long | Optional ID of the plan proposed as the default for team members when a customer is added to the team by a team administrator. |
| `--max-team-member-count` | decimal | Optional maximum number of customers for this team |
| `--transfer-credits-to-paying-member` | bool | Whether team members' credits are pooled with the paying customer; requires a paying customer and supports teams of up to 50 customers |
| `--share-time-passes` | bool | Whether team members share passes through the paying customer; with credit pooling enabled, their combined included passes cannot exceed 500 |
| `--share-extra-services` | bool | Whether team members share time credits and printing credits through the paying customer |
| `--share-booking-credit` | bool | Whether team members can use the paying customer's booking credit for their bookings |
| `--discount-extra-services` | decimal | Optional percentage discount on booking rates; the highest applicable team or plan discount is used |
| `--discount-time-passes` | decimal | Optional percentage discount on passes; the highest applicable team or plan discount is used |
| `--discount-charges` | decimal | Optional percentage discount on one-off charges; the highest applicable team or plan discount is used |
| `--discount-tariffs` | decimal | Optional percentage discount on plans; the highest discount configured on any of the customer's teams is used |
| `--profile-summary` | string | Optional HTML profile summary displayed in the public team directory |
| `--profile-tags` | string | Optional public-directory tags used to find this team, limited to 254 characters |
| `--profile-website` | string | Optional website URL displayed on the public team profile, limited to 254 characters |
| `--google-maps-link` | string | Optional Google Maps URL displayed on the public team profile, limited to 1024 characters |
| `--profile-is-public` | bool | Whether this team's profile can appear in the public directory |
| `--has-community-group` | bool | Whether Nexudus automatically creates and maintains a discussion-board community group for this team |
| `--new-team-logo-url` | string | URL of a new file to upload as the team logo |
| `--clear-team-logo-file` | bool | Set to true to remove the current team logo file |
| `--new-team-image1-url` | string | URL of a new file to upload as the team image1 |
| `--clear-team-image1-file` | bool | Set to true to remove the current team image1 file |
| `--new-team-image2-url` | string | URL of a new file to upload as the team image2 |
| `--clear-team-image2-file` | bool | Set to true to remove the current team image2 file |
| `--new-team-image3-url` | string | URL of a new file to upload as the team image3 |
| `--clear-team-image3-file` | bool | Set to true to remove the current team image3 file |
| `--twitter` | string | Optional X or Twitter profile URL, limited to 254 characters |
| `--facebook` | string | Optional Facebook profile URL, limited to 254 characters |
| `--linkedin` | string | Optional LinkedIn profile URL, limited to 254 characters |
| `--skype` | string | Optional Skype handle or URL, limited to 254 characters |
| `--telegram` | string | Optional Telegram handle or URL, limited to 254 characters |
| `--github` | string | Optional GitHub profile or organization URL, limited to 254 characters |
| `--pinterest` | string | Optional Pinterest profile URL, limited to 254 characters |
| `--flickr` | string | Optional Flickr profile URL, limited to 254 characters |
| `--instagram` | string | Optional Instagram profile URL, limited to 254 characters |
| `--vimeo` | string | Optional Vimeo profile URL, limited to 254 characters |
| `--tumblr` | string | Optional Tumblr profile URL, limited to 254 characters |
| `--blogger` | string | Optional Blogger profile URL, limited to 254 characters |
| `--disable-attendance-dashboard` | bool | Whether to hide this team's attendance dashboard from its customers |
| `--extra-services` | list, repeat flag | List of booking rate IDs linked to this team |
| `--added-extra-services` | list, repeat flag | The added extra services value for this team |
| `--removed-extra-services` | list, repeat flag | The removed extra services value for this team |

#### Team PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--paying-member-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--paying-member-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--paying-member-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--profile-summary` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--profile-website` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--twitter` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--facebook` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--linkedin` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--skype` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--telegram` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--github` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--pinterest` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--flickr` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--instagram` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--vimeo` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--tumblr` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |
| `--blogger` | `SOCIAL` | `«PII:SOCIAL:a3f2b1c9»` |

Example:

`nexudus teams update <id> --paying-member-full-name "«PII:NAME:a3f2b1c9»" --agent`

### Team (key fields)

`Id`, `BusinessName`, `Name`

**List properties (only returned by `get`, not by `list`):** `TeamMembers`, `AddedTeamMembers`, `RemovedTeamMembers`, `TeamAdministrators`, `AddedTeamAdministrators`, `RemovedTeamAdministrators`, `ExtraServices`, `AddedExtraServices`, `RemovedExtraServices`

<!-- END:GENERATED entity=Teams -->
