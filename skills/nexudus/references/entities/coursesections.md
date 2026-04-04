# CourseSections

<!-- BEGIN:GENERATED entity=CourseSections -->

CourseSections support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coursesections list --agent` | List all coursesections |
| `nexudus coursesections list --id <id> --agent` | Filter by single ID |
| `nexudus coursesections list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coursesections list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coursesections list --course-id <value> --title <value> --agent` | Filter coursesections by properties |
| `nexudus coursesections list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coursesections get <id> --agent` | Get single coursesection |
| `nexudus coursesections create --course-id <value> --title <value> --display-order <value> --unlock-after-days <value> --agent` | Create coursesection |
| `nexudus coursesections update <id> --name "New Name" --agent` | Update coursesection |
| `nexudus coursesections delete <id> --yes --agent` | Delete coursesection (no prompt) |

#### CourseSection list filter options

`--course-id`, `--title`, `--section-contents`, `--active`, `--display-order`, `--unlock-type`, `--new-image-url`, `--clear-image-file`, `--unlock-after-days`

#### CourseSection create options

`--course-id` (required), `--title` (required), `--section-contents`, `--active`, `--display-order` (required), `--unlock-type`, `--new-image-url`, `--clear-image-file`, `--unlock-after-days` (required)

#### CourseSection update options

`--course-id`, `--title`, `--section-contents`, `--active`, `--display-order`, `--unlock-type`, `--new-image-url`, `--clear-image-file`, `--unlock-after-days`

<!-- END:GENERATED entity=CourseSections -->
