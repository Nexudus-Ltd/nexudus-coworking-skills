# Courses

<!-- BEGIN:GENERATED entity=Courses -->

A **Course** is a structured learning module published to customers through the Members Portal. Courses are organised into **sections** (milestones) and **lessons** (individual content units). They can be used for internal training, community building, or self-learning offers.

Courses belong to a Location and are assigned a Host (a customer or administrator) who is responsible for its content. You can control who can access a course using the `Visibility` field:

| Visibility | Meaning |
| ---------- | ------- |
| Public     | Visible and accessible to everyone on the Members Portal |
| Hidden     | Not listed on the Members Portal but accessible via a direct link |
| Private    | Only accessible to members who have been explicitly added |
| Paid       | Requires purchase via the linked `TariffId` pricing plan |

Courses can optionally display a community discussion group (`HasCommunityGroup`), be featured on the portal home page (`ShowInHomePage`), and be grouped together under a `GroupName` for easier navigation.

Courses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus courses list --agent` | List all courses |
| `nexudus courses list --id <id> --agent` | Filter by single ID |
| `nexudus courses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus courses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus courses list --business-id <value> --business-name <value> --agent` | Filter courses by properties |
| `nexudus courses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus courses list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus courses get <id> --agent` | Get single course |
| `nexudus courses create --business-id <value> --host-id <value> --title <value> --display-order <value> --visibility <value> --agent` | Create course |
| `nexudus courses update <id> --name "New Name" --agent` | Update course |
| `nexudus courses delete <id> --yes --agent` | Delete course (no prompt) |

#### Course list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the Location this course belongs to |
| `--business-name` | string | Location name |
| `--business-address` | string | Location address |
| `--business-town-city` | string | Location town or city |
| `--business-postal-code` | string | Location postal code |
| `--host-id` | long | ID of the coworker or administrator who hosts this course |
| `--host-full-name` | string | Host full name |
| `--host-company-name` | string | Host company name |
| `--host-team-names` | string | Comma-separated list of teams the host belongs to |
| `--title` | string | Course title displayed on the Members Portal |
| `--summary-text` | string | Short summary displayed under the course title on the Members Portal (up to ~400 characters) |
| `--full-description` | string | Full course description shown in the 'What's this course about?' section when customers open the course |
| `--show-overview` | bool | Whether to display the overview section on the course page |
| `--has-community-group` | bool | Whether the course has an associated community discussion group on the Members Portal |
| `--overview-text` | string | Overview text displayed below the full description on the course page |
| `--image-file-name` | string | Stored filename of the course thumbnail image (read-only; use --new-image-url to set) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--large-image-file-name` | string | Stored filename of the course banner/large image (read-only; use --new-large-image-url to set) |
| `--new-large-image-url` | string | URL of a new banner/large image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-large-image-file` | bool | Set to true to remove the existing banner/large image |
| `--active` | bool | Whether the course is active and available to customers |
| `--group-name` | string | Optional group label used to cluster related courses together on the Members Portal |
| `--display-order` | int | Position of the course in listing pages; lower numbers appear first |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--show-in-home-page` | bool | Whether the course is featured on the Members Portal home page |
| `--visibility` | enum | Access control for the course: Public (1), Hidden from listing but accessible via link (2), Private/invite-only (3), or Paid via TariffId (4) |
| `--tariff-id` | long | ID of the pricing plan (tariff) required to access this course when Visibility is Paid |
| `--tariff-name` | string | Pricing plan name |
| `--tariff-invoice-every` | int | Billing frequency of the pricing plan (in months) |
| `--from-tariff-invoice-every` | range | |
| `--to-tariff-invoice-every` | range | |
| `--tariff-invoice-every-weeks` | int | Billing frequency of the pricing plan (in weeks) |
| `--from-tariff-invoice-every-weeks` | range | |
| `--to-tariff-invoice-every-weeks` | range | |
| `--tariff-price` | decimal | Price of the pricing plan |
| `--from-tariff-price` | range | |
| `--to-tariff-price` | range | |
| `--tariff-currency-code` | string | Currency code of the pricing plan (e.g. USD, GBP) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Course sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Course create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the Location this course belongs to |
| `--host-id` | long, required | ID of the coworker or administrator who hosts this course |
| `--title` | string, required | Course title displayed on the Members Portal |
| `--summary-text` | string | Short summary displayed under the course title on the Members Portal (up to ~400 characters) |
| `--full-description` | string | Full course description shown in the 'What's this course about?' section when customers open the course |
| `--show-overview` | bool | Whether to display the overview section on the course page |
| `--has-community-group` | bool | Whether the course has an associated community discussion group on the Members Portal |
| `--overview-text` | string | Overview text displayed below the full description on the course page |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--new-large-image-url` | string | URL of a new banner/large image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-large-image-file` | bool | Set to true to remove the existing banner/large image |
| `--active` | bool | Whether the course is active and available to customers |
| `--group-name` | string | Optional group label used to cluster related courses together on the Members Portal |
| `--display-order` | int, required | Position of the course in listing pages; lower numbers appear first |
| `--show-in-home-page` | bool | Whether the course is featured on the Members Portal home page |
| `--visibility` | enum, required | Access control for the course: Public (1), Hidden from listing but accessible via link (2), Private/invite-only (3), or Paid via TariffId (4) |
| `--tariff-id` | long | ID of the pricing plan (tariff) required to access this course when Visibility is Paid |

#### Course update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the Location this course belongs to |
| `--host-id` | long | ID of the coworker or administrator who hosts this course |
| `--title` | string | Course title displayed on the Members Portal |
| `--summary-text` | string | Short summary displayed under the course title on the Members Portal (up to ~400 characters) |
| `--full-description` | string | Full course description shown in the 'What's this course about?' section when customers open the course |
| `--show-overview` | bool | Whether to display the overview section on the course page |
| `--has-community-group` | bool | Whether the course has an associated community discussion group on the Members Portal |
| `--overview-text` | string | Overview text displayed below the full description on the course page |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--new-large-image-url` | string | URL of a new banner/large image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-large-image-file` | bool | Set to true to remove the existing banner/large image |
| `--active` | bool | Whether the course is active and available to customers |
| `--group-name` | string | Optional group label used to cluster related courses together on the Members Portal |
| `--display-order` | int | Position of the course in listing pages; lower numbers appear first |
| `--show-in-home-page` | bool | Whether the course is featured on the Members Portal home page |
| `--visibility` | enum | Access control for the course: Public (1), Hidden from listing but accessible via link (2), Private/invite-only (3), or Paid via TariffId (4) |
| `--tariff-id` | long | ID of the pricing plan (tariff) required to access this course when Visibility is Paid |

#### Course PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--host-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--host-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus courses update <id> --host-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### Course enum values

| Option | Valid values |
| ------ | ------------ |
| `--visibility` | `1` Public, `2` Hidden, `3` Private, `4` Paid |

<!-- END:GENERATED entity=Courses -->
