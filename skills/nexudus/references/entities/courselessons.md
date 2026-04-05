# CourseLessons

<!-- BEGIN:GENERATED entity=CourseLessons -->

CourseLessons support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus courselessons list --agent` | List all courselessons |
| `nexudus courselessons list --id <id> --agent` | Filter by single ID |
| `nexudus courselessons list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus courselessons list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus courselessons list --course-id <value> --section-id <value> --agent` | Filter courselessons by properties |
| `nexudus courselessons list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus courselessons get <id> --agent` | Get single courselesson |
| `nexudus courselessons create --course-id <value> --title <value> --display-order <value> --unlock-after-days <value> --agent` | Create courselesson |
| `nexudus courselessons update <id> --name "New Name" --agent` | Update courselesson |
| `nexudus courselessons delete <id> --yes --agent` | Delete courselesson (no prompt) |

#### CourseLesson list filter options

`--course-id`, `--section-id`, `--instructor-id`, `--title`, `--summary-text`, `--lesson-contents`, `--active`, `--display-order`, `--from-display-order` (range), `--to-display-order` (range), `--unlock-type`, `--new-image-url`, `--clear-image-file`, `--unlock-after-days`, `--from-unlock-after-days` (range), `--to-unlock-after-days` (range), `--completion-type`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CourseLesson create options

`--course-id` (required), `--section-id`, `--instructor-id`, `--title` (required), `--summary-text`, `--lesson-contents`, `--active`, `--display-order` (required), `--unlock-type`, `--new-image-url`, `--clear-image-file`, `--unlock-after-days` (required), `--completion-type`

#### CourseLesson update options

`--course-id`, `--section-id`, `--instructor-id`, `--title`, `--summary-text`, `--lesson-contents`, `--active`, `--display-order`, `--unlock-type`, `--new-image-url`, `--clear-image-file`, `--unlock-after-days`, `--completion-type`

<!-- END:GENERATED entity=CourseLessons -->
