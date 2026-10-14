# CourseSections

<!-- BEGIN:GENERATED entity=CourseSections -->

A course section (CourseSection) is an ordered heading that groups lessons within a course on the Members Portal. Lessons join a section through their SectionId; lessons without a section are listed before all sections.

CourseSections support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coursesections list --agent` | List all coursesections |
| `nexudus coursesections list --id <id> --agent` | Filter by single ID |
| `nexudus coursesections list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coursesections list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coursesections list --course-id <value> --course-title <value> --agent` | Filter coursesections by properties |
| `nexudus coursesections list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coursesections list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coursesections get <id> --agent` | Get single coursesection |
| `nexudus coursesections create --course-id <value> --title <value> --display-order <value> --unlock-type <value> --unlock-after-days <value> --agent` | Create coursesection |
| `nexudus coursesections update <id> --name "New Name" --agent` | Update coursesection |
| `nexudus coursesections delete <id> --yes --agent` | Delete coursesection (no prompt) |

#### CourseSection list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course that contains this section; the course's location determines access to the section |
| `--course-title` | string | Display value for Course.Title. |
| `--title` | string | Required section heading shown above its lessons in the Members Portal course menu |
| `--section-contents` | string | Optional section summary returned to the Members Portal with the course's lessons |
| `--active` | bool | Stored flag for whether the section is in use; the Members Portal still shows an inactive section and its lessons, so set the lessons' Active to false to hide them |
| `--display-order` | int | Position of the section within its course; sections appear in ascending order after any lessons that have no section. On create it is an insert index (0 puts the section first, a large number puts it last), and the system renumbers the course's sections in steps of 100 after each save |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--unlock-type` | enum | Stored unlock rule for the section: Immediate, Sequential or Timed; defaults to Immediate. Members Portal access is decided by each lesson's own UnlockType, so set the lessons' unlock rules to control when they open |
| `--image-file-name` | string | Stored filename of the section thumbnail image (read-only; use --new-image-url to set) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Days after a member joins before a Timed section unlocks; stored with UnlockType and, like it, not applied to the section's lessons |
| `--from-unlock-after-days` | range | |
| `--to-unlock-after-days` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseSection sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CourseSection create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long, required | ID of the course that contains this section; the course's location determines access to the section |
| `--title` | string, required | Required section heading shown above its lessons in the Members Portal course menu |
| `--section-contents` | string | Optional section summary returned to the Members Portal with the course's lessons |
| `--active` | bool | Stored flag for whether the section is in use; the Members Portal still shows an inactive section and its lessons, so set the lessons' Active to false to hide them |
| `--display-order` | int, required | Position of the section within its course; sections appear in ascending order after any lessons that have no section. On create it is an insert index (0 puts the section first, a large number puts it last), and the system renumbers the course's sections in steps of 100 after each save |
| `--unlock-type` | enum, required | Stored unlock rule for the section: Immediate, Sequential or Timed; defaults to Immediate. Members Portal access is decided by each lesson's own UnlockType, so set the lessons' unlock rules to control when they open |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int, required | Days after a member joins before a Timed section unlocks; stored with UnlockType and, like it, not applied to the section's lessons |

#### CourseSection update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course that contains this section; the course's location determines access to the section |
| `--title` | string | Required section heading shown above its lessons in the Members Portal course menu |
| `--section-contents` | string | Optional section summary returned to the Members Portal with the course's lessons |
| `--active` | bool | Stored flag for whether the section is in use; the Members Portal still shows an inactive section and its lessons, so set the lessons' Active to false to hide them |
| `--display-order` | int | Position of the section within its course; sections appear in ascending order after any lessons that have no section. On create it is an insert index (0 puts the section first, a large number puts it last), and the system renumbers the course's sections in steps of 100 after each save |
| `--unlock-type` | enum | Stored unlock rule for the section: Immediate, Sequential or Timed; defaults to Immediate. Members Portal access is decided by each lesson's own UnlockType, so set the lessons' unlock rules to control when they open |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Days after a member joins before a Timed section unlocks; stored with UnlockType and, like it, not applied to the section's lessons |

#### CourseSection enum values

| Option | Valid values |
| ------ | ------------ |
| `--unlock-type` | `1` Immediate, `2` Sequential, `3` Timed |

<!-- END:GENERATED entity=CourseSections -->
