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

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course this section belongs to |
| `--title` | string | Section title displayed to members |
| `--section-contents` | string | Optional HTML or rich-text introductory content shown at the top of the section |
| `--active` | bool | Whether the section is active and visible to enrolled members |
| `--display-order` | int | Position of the section within the course; lower numbers appear first |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--unlock-type` | enum | When the section becomes available: Immediate (1), after the previous section is done — Sequential (2), or after a set number of days — Timed (3) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Number of days after enrolment before the section unlocks; only used when UnlockType is Timed (3) |
| `--from-unlock-after-days` | range | |
| `--to-unlock-after-days` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseSection create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long, required | ID of the course this section belongs to |
| `--title` | string, required | Section title displayed to members |
| `--section-contents` | string | Optional HTML or rich-text introductory content shown at the top of the section |
| `--active` | bool | Whether the section is active and visible to enrolled members |
| `--display-order` | int, required | Position of the section within the course; lower numbers appear first |
| `--unlock-type` | enum, required | When the section becomes available: Immediate (1), after the previous section is done — Sequential (2), or after a set number of days — Timed (3) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int, required | Number of days after enrolment before the section unlocks; only used when UnlockType is Timed (3) |

#### CourseSection update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course this section belongs to |
| `--title` | string | Section title displayed to members |
| `--section-contents` | string | Optional HTML or rich-text introductory content shown at the top of the section |
| `--active` | bool | Whether the section is active and visible to enrolled members |
| `--display-order` | int | Position of the section within the course; lower numbers appear first |
| `--unlock-type` | enum | When the section becomes available: Immediate (1), after the previous section is done — Sequential (2), or after a set number of days — Timed (3) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Number of days after enrolment before the section unlocks; only used when UnlockType is Timed (3) |

#### CourseSection enum values

| Option | Valid values |
| ------ | ------------ |
| `--unlock-type` | `1` Immediate, `2` Sequential, `3` Timed |

<!-- END:GENERATED entity=CourseSections -->
