# CourseMembers

<!-- BEGIN:GENERATED entity=CourseMembers -->

A course member (CourseMember) is a customer's enrolment in a course. Customers join from the Members Portal or an administrator adds them; when the course has a plan, creating the enrolment also adds a contract for that plan to the customer. Approved and Blocked control access, and completed lessons record progress.

CourseMembers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coursemembers list --agent` | List all coursemembers |
| `nexudus coursemembers list --id <id> --agent` | Filter by single ID |
| `nexudus coursemembers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coursemembers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coursemembers list --course-id <value> --course-title <value> --agent` | Filter coursemembers by properties |
| `nexudus coursemembers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coursemembers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coursemembers get <id> --agent` | Get single coursemember |
| `nexudus coursemembers create --course-id <value> --coworker-id <value> --agent` | Create coursemember |
| `nexudus coursemembers update <id> --name "New Name" --agent` | Update coursemember |
| `nexudus coursemembers delete <id> --yes --agent` | Delete coursemember (no prompt) |

#### CourseMember list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course the customer is enrolled in; the course's location determines access to the enrolment |
| `--course-title` | string | Display value for Course.Title. |
| `--coworker-id` | long | Required ID of the enrolled customer; enrol each customer in a course only once |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-team-names` | string | Display value for Coworker.TeamNames. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--last-completed-lesson-title` | string | Display value for LastCompletedLesson.Title. |
| `--approved` | bool | Whether the member can open the course content on the Members Portal. The system sets it when the enrolment is created, overriding the value sent: approved at once unless the course plan has a price, in which case it stays false until the plan invoice is paid. Set it later to approve or revoke access |
| `--blocked` | bool | Whether the member is blocked; it stops them accepting an invitation to the course and keeps it out of some Members Portal course lists, but only Approved = false stops them opening its content, so set both to remove access |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CourseMember sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CourseMember create options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long, required | ID of the course the customer is enrolled in; the course's location determines access to the enrolment |
| `--coworker-id` | long, required | Required ID of the enrolled customer; enrol each customer in a course only once |
| `--approved` | bool | Whether the member can open the course content on the Members Portal. The system sets it when the enrolment is created, overriding the value sent: approved at once unless the course plan has a price, in which case it stays false until the plan invoice is paid. Set it later to approve or revoke access |
| `--blocked` | bool | Whether the member is blocked; it stops them accepting an invitation to the course and keeps it out of some Members Portal course lists, but only Approved = false stops them opening its content, so set both to remove access |

#### CourseMember update options

| Option | Type | Description |
| --- | --- | --- |
| `--course-id` | long | ID of the course the customer is enrolled in; the course's location determines access to the enrolment |
| `--coworker-id` | long | Required ID of the enrolled customer; enrol each customer in a course only once |
| `--approved` | bool | Whether the member can open the course content on the Members Portal. The system sets it when the enrolment is created, overriding the value sent: approved at once unless the course plan has a price, in which case it stays false until the plan invoice is paid. Set it later to approve or revoke access |
| `--blocked` | bool | Whether the member is blocked; it stops them accepting an invitation to the course and keeps it out of some Members Portal course lists, but only Approved = false stops them opening its content, so set both to remove access |

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
