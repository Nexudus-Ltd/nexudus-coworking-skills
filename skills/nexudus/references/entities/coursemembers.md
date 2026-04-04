# CourseMembers

<!-- BEGIN:GENERATED entity=CourseMembers -->

CourseMembers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coursemembers list --agent` | List all coursemembers |
| `nexudus coursemembers list --id <id> --agent` | Filter by single ID |
| `nexudus coursemembers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coursemembers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coursemembers list --course-id <value> --coworker-id <value> --agent` | Filter coursemembers by properties |
| `nexudus coursemembers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coursemembers get <id> --agent` | Get single coursemember |
| `nexudus coursemembers create --course-id <value> --coworker-id <value> --agent` | Create coursemember |
| `nexudus coursemembers update <id> --name "New Name" --agent` | Update coursemember |
| `nexudus coursemembers delete <id> --yes --agent` | Delete coursemember (no prompt) |

#### CourseMember list filter options

`--course-id`, `--coworker-id`, `--approved`, `--blocked`

#### CourseMember create options

`--course-id` (required), `--coworker-id` (required), `--approved`, `--blocked`, `--completed-lessons` (list, repeat flag), `--added-completed-lessons` (list, repeat flag), `--removed-completed-lessons` (list, repeat flag)

#### CourseMember update options

`--course-id`, `--coworker-id`, `--approved`, `--blocked`, `--completed-lessons` (list, repeat flag), `--added-completed-lessons` (list, repeat flag), `--removed-completed-lessons` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `CompletedLessons`, `AddedCompletedLessons`, `RemovedCompletedLessons`

<!-- END:GENERATED entity=CourseMembers -->
