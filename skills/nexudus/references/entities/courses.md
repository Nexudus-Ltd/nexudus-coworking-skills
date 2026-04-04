# Courses

<!-- BEGIN:GENERATED entity=Courses -->

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
| `nexudus courses create --business-id <value> --host-id <value> --title <value> --display-order <value> --agent` | Create course |
| `nexudus courses update <id> --name "New Name" --agent` | Update course |
| `nexudus courses delete <id> --yes --agent` | Delete course (no prompt) |

#### Course list filter options

`--business-id`, `--host-id`, `--title`, `--summary-text`, `--full-description`, `--show-overview`, `--has-community-group`, `--overview-text`, `--new-image-url`, `--clear-image`, `--new-large-image-url`, `--clear-large-image`, `--active`, `--group-name`, `--display-order`, `--show-in-home-page`, `--visibility`, `--tariff-id`

#### Course create options

`--business-id` (required), `--host-id` (required), `--title` (required), `--summary-text`, `--full-description`, `--show-overview`, `--has-community-group`, `--overview-text`, `--new-image-url`, `--clear-image`, `--new-large-image-url`, `--clear-large-image`, `--active`, `--group-name`, `--display-order` (required), `--show-in-home-page`, `--visibility`, `--tariff-id`, `--lessons` (list, repeat flag), `--added-lessons` (list, repeat flag), `--removed-lessons` (list, repeat flag), `--sections` (list, repeat flag), `--added-sections` (list, repeat flag), `--removed-sections` (list, repeat flag), `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag)

#### Course update options

`--business-id`, `--host-id`, `--title`, `--summary-text`, `--full-description`, `--show-overview`, `--has-community-group`, `--overview-text`, `--new-image-url`, `--clear-image`, `--new-large-image-url`, `--clear-large-image`, `--active`, `--group-name`, `--display-order`, `--show-in-home-page`, `--visibility`, `--tariff-id`, `--lessons` (list, repeat flag), `--added-lessons` (list, repeat flag), `--removed-lessons` (list, repeat flag), `--sections` (list, repeat flag), `--added-sections` (list, repeat flag), `--removed-sections` (list, repeat flag), `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Lessons`, `AddedLessons`, `RemovedLessons`, `Sections`, `AddedSections`, `RemovedSections`, `Members`, `AddedMembers`, `RemovedMembers`

<!-- END:GENERATED entity=Courses -->
