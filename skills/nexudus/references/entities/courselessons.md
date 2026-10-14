# CourseLessons

<!-- BEGIN:GENERATED entity=CourseLessons -->

A course lesson (CourseLesson) is one step of a course that members open and complete on the Members Portal. It belongs to a course and optionally a section; UnlockType decides when a member can open it and CompletionType how it counts as done.

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
| `--course-id` | long | ID of the course this lesson belongs to; the course's location determines access to the lesson |
| `--course-title` | string | Display value for Course.Title. |
| `--section-id` | long | Optional ID of a section of the same course that groups this lesson; lessons without a section are listed before all sections |
| `--section-display-order` | int | Display value for Section.DisplayOrder. |
| `--from-section-display-order` | range | |
| `--to-section-display-order` | range | |
| `--section-title` | string | Display value for Section.Title. |
| `--instructor-id` | long | Optional ID of the customer credited as this lesson's instructor; stored with the lesson and does not replace the course host shown on the course page |
| `--instructor-full-name` | string | Display value for Instructor.FullName. |
| `--instructor-company-name` | string | Display value for Instructor.CompanyName. |
| `--instructor-team-names` | string | Display value for Instructor.TeamNames. |
| `--title` | string | Required lesson title shown in the Members Portal course menu |
| `--summary-text` | string | Short plain-text summary shown with the lesson in the course's lesson list |
| `--lesson-contents` | string | Lesson body in HTML, shown when a member opens the lesson; embed YouTube videos here when CompletionType is Video |
| `--active` | bool | Whether the lesson is part of the course; inactive lessons are hidden from members and left out of progress and course completion |
| `--display-order` | int | Course-wide position of the lesson: members see lessons without a section first, then each section's lessons in this order, and Sequential unlocking follows it, so keep it rising in step with the section order. A new lesson is added last; the system renumbers the course's lessons in steps of 100 after each save |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--unlock-type` | enum | When a course member can open the lesson: Immediate (1, as soon as they join), Sequential (2, once they complete the lesson before it), or Timed (3, UnlockAfterDays after they joined); defaults to Immediate, and the course's first lesson is always open |
| `--image-file-name` | string | Stored filename of the lesson thumbnail image (read-only; use --new-image-url to set) |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Days after a member joins the course before a Timed lesson opens, counted from the start of the joining day in the location's time zone; ignored for other unlock types |
| `--from-unlock-after-days` | range | |
| `--to-unlock-after-days` | range | |
| `--completion-type` | enum | How a member completes the lesson: None (1, can never be completed, so the course can never be finished), Visited (2, completed on opening), Button (3, the member clicks Complete), or Video (4, Complete unlocks after 95% of the lesson's embedded YouTube videos are watched; without one it behaves like Button); defaults to None |
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
| `--course-id` | long, required | ID of the course this lesson belongs to; the course's location determines access to the lesson |
| `--section-id` | long | Optional ID of a section of the same course that groups this lesson; lessons without a section are listed before all sections |
| `--instructor-id` | long | Optional ID of the customer credited as this lesson's instructor; stored with the lesson and does not replace the course host shown on the course page |
| `--title` | string, required | Required lesson title shown in the Members Portal course menu |
| `--summary-text` | string | Short plain-text summary shown with the lesson in the course's lesson list |
| `--lesson-contents` | string | Lesson body in HTML, shown when a member opens the lesson; embed YouTube videos here when CompletionType is Video |
| `--active` | bool | Whether the lesson is part of the course; inactive lessons are hidden from members and left out of progress and course completion |
| `--display-order` | int, required | Course-wide position of the lesson: members see lessons without a section first, then each section's lessons in this order, and Sequential unlocking follows it, so keep it rising in step with the section order. A new lesson is added last; the system renumbers the course's lessons in steps of 100 after each save |
| `--unlock-type` | enum, required | When a course member can open the lesson: Immediate (1, as soon as they join), Sequential (2, once they complete the lesson before it), or Timed (3, UnlockAfterDays after they joined); defaults to Immediate, and the course's first lesson is always open |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int, required | Days after a member joins the course before a Timed lesson opens, counted from the start of the joining day in the location's time zone; ignored for other unlock types |
| `--completion-type` | enum, required | How a member completes the lesson: None (1, can never be completed, so the course can never be finished), Visited (2, completed on opening), Button (3, the member clicks Complete), or Video (4, Complete unlocks after 95% of the lesson's embedded YouTube videos are watched; without one it behaves like Button); defaults to None |

#### CourseLesson update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course this lesson belongs to; the course's location determines access to the lesson |
| `--section-id` | long | Optional ID of a section of the same course that groups this lesson; lessons without a section are listed before all sections |
| `--instructor-id` | long | Optional ID of the customer credited as this lesson's instructor; stored with the lesson and does not replace the course host shown on the course page |
| `--title` | string | Required lesson title shown in the Members Portal course menu |
| `--summary-text` | string | Short plain-text summary shown with the lesson in the course's lesson list |
| `--lesson-contents` | string | Lesson body in HTML, shown when a member opens the lesson; embed YouTube videos here when CompletionType is Video |
| `--active` | bool | Whether the lesson is part of the course; inactive lessons are hidden from members and left out of progress and course completion |
| `--display-order` | int | Course-wide position of the lesson: members see lessons without a section first, then each section's lessons in this order, and Sequential unlocking follows it, so keep it rising in step with the section order. A new lesson is added last; the system renumbers the course's lessons in steps of 100 after each save |
| `--unlock-type` | enum | When a course member can open the lesson: Immediate (1, as soon as they join), Sequential (2, once they complete the lesson before it), or Timed (3, UnlockAfterDays after they joined); defaults to Immediate, and the course's first lesson is always open |
| `--new-image-url` | string | URL of a new thumbnail image to upload (JPG/JPEG, PNG, or GIF, max 10 MB) |
| `--clear-image-file` | bool | Set to true to remove the existing thumbnail image |
| `--unlock-after-days` | int | Days after a member joins the course before a Timed lesson opens, counted from the start of the joining day in the location's time zone; ignored for other unlock types |
| `--completion-type` | enum | How a member completes the lesson: None (1, can never be completed, so the course can never be finished), Visited (2, completed on opening), Button (3, the member clicks Complete), or Video (4, Complete unlocks after 95% of the lesson's embedded YouTube videos are watched; without one it behaves like Button); defaults to None |

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
