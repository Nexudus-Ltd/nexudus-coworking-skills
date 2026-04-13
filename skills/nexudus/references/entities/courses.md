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
| `nexudus courses list --business-id <value> --host-id <value> --agent` | Filter courses by properties |
| `nexudus courses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus courses get <id> --agent` | Get single course |
| `nexudus courses create --business-id <value> --host-id <value> --title <value> --display-order <value> --visibility <value> --agent` | Create course |
| `nexudus courses update <id> --name "New Name" --agent` | Update course |
| `nexudus courses delete <id> --yes --agent` | Delete course (no prompt) |

#### Course list filter options

`--business-id` (long), `--host-id` (long), `--title`, `--summary-text`, `--full-description`, `--show-overview` (bool), `--has-community-group` (bool), `--overview-text`, `--new-image-url`, `--clear-image-file` (bool), `--new-large-image-url`, `--clear-large-image-file` (bool), `--active` (bool), `--group-name`, `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--show-in-home-page` (bool), `--visibility` (enum), `--tariff-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Course create options

`--business-id` (long, required), `--host-id` (long, required), `--title` (required), `--summary-text`, `--full-description`, `--show-overview` (bool), `--has-community-group` (bool), `--overview-text`, `--new-image-url`, `--clear-image-file` (bool), `--new-large-image-url`, `--clear-large-image-file` (bool), `--active` (bool), `--group-name`, `--display-order` (int, required), `--show-in-home-page` (bool), `--visibility` (enum, required), `--tariff-id` (long)

#### Course update options

`--business-id` (long), `--host-id` (long), `--title`, `--summary-text`, `--full-description`, `--show-overview` (bool), `--has-community-group` (bool), `--overview-text`, `--new-image-url`, `--clear-image-file` (bool), `--new-large-image-url`, `--clear-large-image-file` (bool), `--active` (bool), `--group-name`, `--display-order` (int), `--show-in-home-page` (bool), `--visibility` (enum), `--tariff-id` (long)

#### Course enum values

| Option | Valid values |
| ------ | ------------ |
| `--visibility` | `1` Public, `2` Hidden, `3` Private, `4` Paid |

<!-- END:GENERATED entity=Courses -->
