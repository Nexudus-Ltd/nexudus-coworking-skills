# CommunityGroups

<!-- BEGIN:GENERATED entity=CommunityGroups -->

A community group is a named customer group that controls who can view and post in Discussion Board conversations assigned to it.

CommunityGroups support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitygroups list --agent` | List all communitygroups |
| `nexudus communitygroups list --id <id> --agent` | Filter by single ID |
| `nexudus communitygroups list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitygroups list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitygroups list --business-name <value> --name <value> --agent` | Filter communitygroups by properties |
| `nexudus communitygroups list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitygroups list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitygroups get <id> --agent` | Get single communitygroup |
| `nexudus communitygroups create --business-id <value> --user-id <value> --name <value> --group-access <value> --agent` | Create communitygroup |
| `nexudus communitygroups update <id> --name "New Name" --agent` | Update communitygroup |
| `nexudus communitygroups delete <id> --yes --agent` | Delete communitygroup (no prompt) |

#### CommunityGroup list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this community group belongs to |
| `--business-name` | string | Location name |
| `--user-id` | long | ID of the user account that administers this group; the administrator can always view and post in it |
| `--name` | string | Required display name of the community group |
| `--description` | string | Optional description of the community group's purpose shown to customers |
| `--group-access` | enum | Access level for conversations assigned to this group: Restricted (1) lets all customers view but only the administrator and members post; Public (2) lets all customers view and post; Private (3) lets only the administrator and members view and post |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityGroup sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityGroup create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this community group belongs to |
| `--user-id` | long, required | ID of the user account that administers this group; the administrator can always view and post in it |
| `--name` | string, required | Required display name of the community group |
| `--description` | string | Optional description of the community group's purpose shown to customers |
| `--group-access` | enum, required | Access level for conversations assigned to this group: Restricted (1) lets all customers view but only the administrator and members post; Public (2) lets all customers view and post; Private (3) lets only the administrator and members view and post |
| `--members` | list, repeat flag | List of user IDs whose customers are group members; they can post in Restricted groups and view and post in Private groups, while the administrator always has access |
| `--added-members` | list, repeat flag | Customer IDs to add as members (used in partial updates) |
| `--removed-members` | list, repeat flag | Customer IDs to remove as members (used in partial updates) |

#### CommunityGroup update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this community group belongs to |
| `--user-id` | long | ID of the user account that administers this group; the administrator can always view and post in it |
| `--name` | string | Required display name of the community group |
| `--description` | string | Optional description of the community group's purpose shown to customers |
| `--group-access` | enum | Access level for conversations assigned to this group: Restricted (1) lets all customers view but only the administrator and members post; Public (2) lets all customers view and post; Private (3) lets only the administrator and members view and post |
| `--members` | list, repeat flag | List of user IDs whose customers are group members; they can post in Restricted groups and view and post in Private groups, while the administrator always has access |
| `--added-members` | list, repeat flag | Customer IDs to add as members (used in partial updates) |
| `--removed-members` | list, repeat flag | Customer IDs to remove as members (used in partial updates) |

### CommunityGroup (key fields)

`Id`, `BusinessName`, `Name`

**List properties (only returned by `get`, not by `list`):** `Members`, `AddedMembers`, `RemovedMembers`

#### CommunityGroup enum values

| Option | Valid values |
| ------ | ------------ |
| `--group-access` | `1` Restricted, `2` Public, `3` Private |

<!-- END:GENERATED entity=CommunityGroups -->
