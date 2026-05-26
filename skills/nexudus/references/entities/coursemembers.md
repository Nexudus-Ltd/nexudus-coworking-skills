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

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course the member is enrolled in |
| `--coworker-id` | long | ID of the customer enrolled in the course |
| `--approved` | bool | Whether the member has been approved to access the course content |
| `--blocked` | bool | Whether the member has been blocked from accessing the course |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseMember create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long, required | ID of the course the member is enrolled in |
| `--coworker-id` | long, required | ID of the customer enrolled in the course |
| `--approved` | bool | Whether the member has been approved to access the course content |
| `--blocked` | bool | Whether the member has been blocked from accessing the course |

#### CourseMember update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course the member is enrolled in |
| `--coworker-id` | long | ID of the customer enrolled in the course |
| `--approved` | bool | Whether the member has been approved to access the course content |
| `--blocked` | bool | Whether the member has been blocked from accessing the course |

#### CourseMember PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coursemembers update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=CourseMembers -->
