# CourseCompletedLessons

<!-- BEGIN:GENERATED entity=CourseCompletedLessons -->

A completed lesson (CourseCompletedLesson) records that a course member finished a lesson. The Members Portal creates it when the lesson's completion rule is met; create one to mark a lesson done for a member, or delete it to reset that lesson. Completed lessons drive progress, Sequential unlocking and course completion.

CourseCompletedLessons support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coursecompletedlessons list --agent` | List all coursecompletedlessons |
| `nexudus coursecompletedlessons list --id <id> --agent` | Filter by single ID |
| `nexudus coursecompletedlessons list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coursecompletedlessons list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coursecompletedlessons list --course-lesson-id <value> --course-lesson-title <value> --agent` | Filter coursecompletedlessons by properties |
| `nexudus coursecompletedlessons list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coursecompletedlessons list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coursecompletedlessons get <id> --agent` | Get single coursecompletedlesson |
| `nexudus coursecompletedlessons create --course-lesson-id <value> --course-member-id <value> --agent` | Create coursecompletedlesson |
| `nexudus coursecompletedlessons update <id> --name "New Name" --agent` | Update coursecompletedlesson |
| `nexudus coursecompletedlessons delete <id> --yes --agent` | Delete coursecompletedlesson (no prompt) |

#### CourseCompletedLesson list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--course-lesson-id` | long | ID of the completed lesson; it must belong to the same course as the course member |
| `--course-lesson-title` | string | Display value for CourseLesson.Title. |
| `--course-member-id` | long | ID of the course member (the customer's enrolment) who completed the lesson |
| `--course-member-coworker-full-name` | string | Display value for CourseMember.Coworker.FullName. |
| `--course-member-coworker-company-name` | string | Display value for CourseMember.Coworker.CompanyName. |
| `--course-member-coworker-team-names` | string | Display value for CourseMember.Coworker.TeamNames. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseCompletedLesson sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CourseCompletedLesson create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-lesson-id` | long, required | ID of the completed lesson; it must belong to the same course as the course member |
| `--course-member-id` | long, required | ID of the course member (the customer's enrolment) who completed the lesson |

#### CourseCompletedLesson update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-lesson-id` | long | ID of the completed lesson; it must belong to the same course as the course member |
| `--course-member-id` | long | ID of the course member (the customer's enrolment) who completed the lesson |

#### CourseCompletedLesson PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--course-member-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--course-member-coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coursecompletedlessons update <id> --course-member-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=CourseCompletedLessons -->
