# CourseSections

<!-- BEGIN:GENERATED entity=CourseSections -->

A **CourseSection** is a structural grouping that organises lessons within a `Course`. Sections represent milestones or learning stages — each section should bring the member one step closer to the course's overall learning goal.

Sections are ordered by `DisplayOrder` and can be set to unlock immediately or after a delay, using the same `UnlockType` / `UnlockAfterDays` mechanism as individual lessons:

| UnlockType | Meaning |
| ---------- | ------- |
| Immediate  | Section is available as soon as the member enrols |
| Sequential | Unlocked only after the previous section is completed |
| Timed      | Unlocked after the number of days specified by `UnlockAfterDays` |

Sections are optional — lessons can belong directly to a course without a section. However, using sections can help create a clearer learning path for members, and allows you to unlock groups of lessons at once.

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
| `nexudus coursesections create --course-id <value> --title <value> --display-order <value> --unlock-type <value> --unlock-after-days <value> --agent` | Create coursesection |
| `nexudus coursesections update <id> --name "New Name" --agent` | Update coursesection |
| `nexudus coursesections delete <id> --yes --agent` | Delete coursesection (no prompt) |

#### CourseSection list filter options

`--course-id` (long), `--title`, `--section-contents`, `--active` (bool), `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--unlock-type` (enum), `--new-image-url`, `--clear-image-file` (bool), `--unlock-after-days` (int), `--from-unlock-after-days` (range), `--to-unlock-after-days` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CourseSection create options

`--course-id` (long, required), `--title` (required), `--section-contents`, `--active` (bool), `--display-order` (int, required), `--unlock-type` (enum, required), `--new-image-url`, `--clear-image-file` (bool), `--unlock-after-days` (int, required)

#### CourseSection update options

`--course-id` (long), `--title`, `--section-contents`, `--active` (bool), `--display-order` (int), `--unlock-type` (enum), `--new-image-url`, `--clear-image-file` (bool), `--unlock-after-days` (int)

<!-- END:GENERATED entity=CourseSections -->
