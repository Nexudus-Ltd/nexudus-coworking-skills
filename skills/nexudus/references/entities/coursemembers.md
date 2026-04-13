# CourseMembers

<!-- BEGIN:GENERATED entity=CourseMembers -->

A **CourseMember** represents a customer's enrolment in a `Course`. When a customer signs up to a course through the Members Portal they are automatically added as a CourseMember. Members can also be added manually via the Admin Panel or the API.

Each CourseMember record tracks the member's progress (`LastCompletedLessonId`, `LastAccess`) and their access status:

- `Approved` — the member has been approved to access the course content. For public courses this is set automatically on sign-up; for private or paid courses an administrator may need to approve the enrolment.
- `Blocked` — the member has been blocked from accessing the course.

Use `CourseCompletedLesson` records to query which individual lessons a member has completed.

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

`--course-id` (long), `--coworker-id` (long), `--approved` (bool), `--blocked` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CourseMember create options

`--course-id` (long, required), `--coworker-id` (long, required), `--approved` (bool), `--blocked` (bool)

#### CourseMember update options

`--course-id` (long), `--coworker-id` (long), `--approved` (bool), `--blocked` (bool)

<!-- END:GENERATED entity=CourseMembers -->
