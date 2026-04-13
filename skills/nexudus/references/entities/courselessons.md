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
| `nexudus courselessons list --course-id <value> --section-id <value> --agent` | Filter courselessons by properties |
| `nexudus courselessons list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus courselessons get <id> --agent` | Get single courselesson |
| `nexudus courselessons create --course-id <value> --title <value> --display-order <value> --unlock-type <value> --unlock-after-days <value> --completion-type <value> --agent` | Create courselesson |
| `nexudus courselessons update <id> --name "New Name" --agent` | Update courselesson |
| `nexudus courselessons delete <id> --yes --agent` | Delete courselesson (no prompt) |

#### CourseLesson list filter options

`--course-id` (long), `--section-id` (long), `--instructor-id` (long), `--title`, `--summary-text`, `--lesson-contents`, `--active` (bool), `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--unlock-type` (enum), `--new-image-url`, `--clear-image-file` (bool), `--unlock-after-days` (int), `--from-unlock-after-days` (range), `--to-unlock-after-days` (range), `--completion-type` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CourseLesson create options

`--course-id` (long, required), `--section-id` (long), `--instructor-id` (long), `--title` (required), `--summary-text`, `--lesson-contents`, `--active` (bool), `--display-order` (int, required), `--unlock-type` (enum, required), `--new-image-url`, `--clear-image-file` (bool), `--unlock-after-days` (int, required), `--completion-type` (enum, required)

#### CourseLesson update options

`--course-id` (long), `--section-id` (long), `--instructor-id` (long), `--title`, `--summary-text`, `--lesson-contents`, `--active` (bool), `--display-order` (int), `--unlock-type` (enum), `--new-image-url`, `--clear-image-file` (bool), `--unlock-after-days` (int), `--completion-type` (enum)

#### CourseLesson enum values

| Option | Valid values |
| ------ | ------------ |
| `--unlock-type` | `1` Immediate, `2` Sequential, `3` Timed |
| `--completion-type` | `1` None, `2` Visited, `3` Button, `4` Video |

<!-- END:GENERATED entity=CourseLessons -->
