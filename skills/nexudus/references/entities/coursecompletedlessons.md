# CourseCompletedLessons

<!-- BEGIN:GENERATED entity=CourseCompletedLessons -->

A **CourseCompletedLesson** records that a specific `CourseMember` has completed a specific `CourseLesson`. Each record is the junction between a lesson and the enrolled member who finished it.

These records are typically created automatically by the Members Portal when a member meets the lesson's completion criteria (e.g. visiting the lesson page, clicking a completion button, or finishing a video). They can also be created or deleted manually via the API to manage progress programmatically.

Use this entity to query which lessons a member has completed, or to find all members who have completed a given lesson.

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

| Option | Type | Description |
| --- | --- | --- |
| `--course-lesson-id` | long | ID of the course lesson that was completed |
| `--course-member-id` | long | ID of the course enrolment (CourseMember) record for the member who completed the lesson |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseCompletedLesson create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-lesson-id` | long, required | ID of the course lesson that was completed |
| `--course-member-id` | long, required | ID of the course enrolment (CourseMember) record for the member who completed the lesson |

#### CourseCompletedLesson update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-lesson-id` | long | ID of the course lesson that was completed |
| `--course-member-id` | long | ID of the course enrolment (CourseMember) record for the member who completed the lesson |

<!-- END:GENERATED entity=CourseCompletedLessons -->
