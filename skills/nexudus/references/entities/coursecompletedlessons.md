# CourseCompletedLessons

<!-- BEGIN:GENERATED entity=CourseCompletedLessons -->

CourseCompletedLessons support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coursecompletedlessons list --agent` | List all coursecompletedlessons |
| `nexudus coursecompletedlessons list --id <id> --agent` | Filter by single ID |
| `nexudus coursecompletedlessons list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coursecompletedlessons list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coursecompletedlessons list --course-lesson-id <value> --course-member-id <value> --agent` | Filter coursecompletedlessons by properties |
| `nexudus coursecompletedlessons list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coursecompletedlessons get <id> --agent` | Get single coursecompletedlesson |
| `nexudus coursecompletedlessons create --course-lesson-id <value> --course-member-id <value> --agent` | Create coursecompletedlesson |
| `nexudus coursecompletedlessons update <id> --name "New Name" --agent` | Update coursecompletedlesson |
| `nexudus coursecompletedlessons delete <id> --yes --agent` | Delete coursecompletedlesson (no prompt) |

#### CourseCompletedLesson list filter options

`--course-lesson-id`, `--course-member-id`

#### CourseCompletedLesson create options

`--course-lesson-id` (required), `--course-member-id` (required)

#### CourseCompletedLesson update options

`--course-lesson-id`, `--course-member-id`

<!-- END:GENERATED entity=CourseCompletedLessons -->
