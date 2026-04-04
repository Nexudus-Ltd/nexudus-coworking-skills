# CommunityGroups

<!-- BEGIN:GENERATED entity=CommunityGroups -->

CommunityGroups support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitygroups list --agent` | List all communitygroups |
| `nexudus communitygroups list --id <id> --agent` | Filter by single ID |
| `nexudus communitygroups list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitygroups list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitygroups list --business-id <value> --user-id <value> --agent` | Filter communitygroups by properties |
| `nexudus communitygroups list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitygroups get <id> --agent` | Get single communitygroup |
| `nexudus communitygroups create --business-id <value> --user-id <value> --name <value> --agent` | Create communitygroup |
| `nexudus communitygroups update <id> --name "New Name" --agent` | Update communitygroup |
| `nexudus communitygroups delete <id> --yes --agent` | Delete communitygroup (no prompt) |

#### CommunityGroup list filter options

`--business-id`, `--user-id`, `--name`, `--description`, `--group-access`, `--team-guid`, `--course-guid`

#### CommunityGroup create options

`--business-id` (required), `--user-id` (required), `--name` (required), `--description`, `--group-access`, `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag), `--community-threads` (list, repeat flag), `--added-community-threads` (list, repeat flag), `--removed-community-threads` (list, repeat flag), `--team-guid`, `--course-guid`

#### CommunityGroup update options

`--business-id`, `--user-id`, `--name`, `--description`, `--group-access`, `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag), `--community-threads` (list, repeat flag), `--added-community-threads` (list, repeat flag), `--removed-community-threads` (list, repeat flag), `--team-guid`, `--course-guid`

**List properties (only returned by `get`, not by `list`):** `Members`, `AddedMembers`, `RemovedMembers`, `CommunityThreads`, `AddedCommunityThreads`, `RemovedCommunityThreads`

<!-- END:GENERATED entity=CommunityGroups -->
