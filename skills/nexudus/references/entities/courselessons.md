# CourseLessons

<!-- BEGIN:GENERATED entity=CourseLessons -->

A **CourseLesson** is an individual learning unit within a Course. Lessons are the building blocks that customers complete to work through a course's content. Each lesson belongs to a `Course` and optionally to a `CourseSection` that groups related lessons together.

Lessons have two key behavioural settings:

**`UnlockType`** — controls when a lesson becomes available to enrolled members:

| Value      | Meaning |
| ---------- | ------- |
| Immediate  | Available as soon as the member enrols |
| Sequential | Unlocked only after the previous lesson is completed |
| Timed      | Unlocked after a number of days specified by `UnlockAfterDays` |

**`CompletionType`** — defines what action marks the lesson as done:

| Value   | Meaning |
| ------- | ------- |
| None    | No completion tracking |
| Visited | Marked complete when the member opens the lesson |
| Button  | Member must click a completion button |
| Video   | Member must finish watching the embedded video (must be hosted on YouTube) |

CourseLessons support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus courselessons list --agent` | List all courselessons |
| `nexudus courselessons list --id <id> --agent` | Filter by single ID |
| `nexudus courselessons list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus courselessons list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus courselessons list --course-id <value> --course-title <value> --agent` | Filter courselessons by properties |
| `nexudus courselessons list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus courselessons list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus courselessons get <id> --agent` | Get single courselesson |
| `nexudus courselessons create --course-id <value> --title <value> --display-order <value> --unlock-type <value> --unlock-after-days <value> --completion-type <value> --agent` | Create courselesson |
| `nexudus courselessons update <id> --name "New Name" --agent` | Update courselesson |
| `nexudus courselessons delete <id> --yes --agent` | Delete courselesson (no prompt) |

#### CourseLesson list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course this lesson belongs to |
| `--course-title` | string | Title of the parent course |
| `--section-id` | long | ID of the course section this lesson belongs to (optional; lessons without a section appear ungrouped) |
| `--section-display-order` | int | Display order of the parent section |
| `--from-section-display-order` | range | |
| `--to-section-display-order` | range | |
| `--section-title` | string | Title of the parent section |
| `--instructor-id` | long | ID of the coworker attributed as instructor for this lesson (optional; overrides the course-level host for this lesson) |
| `--instructor-full-name` | string | Instructor full name |
| `--instructor-company-name` | string | Instructor company name |
| `--instructor-team-names` | string | Comma-separated list of teams the instructor belongs to |
| `--title` | string | Lesson title displayed to members |
| `--summary-text` | string | Short summary shown in the lesson listing |
| `--lesson-contents` | string | Full HTML or rich-text body of the lesson displayed to members when they open it |
| `--active` | bool | Whether the lesson is active and visible to enrolled members |
| `--display-order` | int | Position of the lesson within its section (or the course if unsectioned); lower numbers appear first |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--unlock-type` | enum | When the lesson becomes available: Immediate (1), after the previous lesson is done — Sequential (2), or after a set number of days — Timed (3) |
| `--image-file-name` | string | Stored filename of the lesson thumbnail image (read-only; use --new-image-url to set) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Number of days after enrolment before the lesson unlocks; only used when UnlockType is Timed (3) |
| `--from-unlock-after-days` | range | |
| `--to-unlock-after-days` | range | |
| `--completion-type` | enum | How completion is tracked: None (1), Visited (2), completion Button (3), or Video watched (4). Video completion requires the lesson to embed a YouTube-hosted video. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseLesson sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CourseLesson create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long, required | ID of the course this lesson belongs to |
| `--section-id` | long | ID of the course section this lesson belongs to (optional; lessons without a section appear ungrouped) |
| `--instructor-id` | long | ID of the coworker attributed as instructor for this lesson (optional; overrides the course-level host for this lesson) |
| `--title` | string, required | Lesson title displayed to members |
| `--summary-text` | string | Short summary shown in the lesson listing |
| `--lesson-contents` | string | Full HTML or rich-text body of the lesson displayed to members when they open it |
| `--active` | bool | Whether the lesson is active and visible to enrolled members |
| `--display-order` | int, required | Position of the lesson within its section (or the course if unsectioned); lower numbers appear first |
| `--unlock-type` | enum, required | When the lesson becomes available: Immediate (1), after the previous lesson is done — Sequential (2), or after a set number of days — Timed (3) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int, required | Number of days after enrolment before the lesson unlocks; only used when UnlockType is Timed (3) |
| `--completion-type` | enum, required | How completion is tracked: None (1), Visited (2), completion Button (3), or Video watched (4). Video completion requires the lesson to embed a YouTube-hosted video. |

#### CourseLesson update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course this lesson belongs to |
| `--section-id` | long | ID of the course section this lesson belongs to (optional; lessons without a section appear ungrouped) |
| `--instructor-id` | long | ID of the coworker attributed as instructor for this lesson (optional; overrides the course-level host for this lesson) |
| `--title` | string | Lesson title displayed to members |
| `--summary-text` | string | Short summary shown in the lesson listing |
| `--lesson-contents` | string | Full HTML or rich-text body of the lesson displayed to members when they open it |
| `--active` | bool | Whether the lesson is active and visible to enrolled members |
| `--display-order` | int | Position of the lesson within its section (or the course if unsectioned); lower numbers appear first |
| `--unlock-type` | enum | When the lesson becomes available: Immediate (1), after the previous lesson is done — Sequential (2), or after a set number of days — Timed (3) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Number of days after enrolment before the lesson unlocks; only used when UnlockType is Timed (3) |
| `--completion-type` | enum | How completion is tracked: None (1), Visited (2), completion Button (3), or Video watched (4). Video completion requires the lesson to embed a YouTube-hosted video. |

#### CourseLesson PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--instructor-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--instructor-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus courselessons update <id> --instructor-full-name "«PII:NAME:a3f2b1c9»" --agent`

#### CourseLesson enum values

| Option | Valid values |
| ------ | ------------ |
| `--unlock-type` | `1` Immediate, `2` Sequential, `3` Timed |
| `--completion-type` | `1` None, `2` Visited, `3` Button, `4` Video |

<!-- END:GENERATED entity=CourseLessons -->
