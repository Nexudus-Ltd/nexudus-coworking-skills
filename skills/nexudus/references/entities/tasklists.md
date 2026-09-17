# TaskLists

<!-- BEGIN:GENERATED entity=TaskLists -->

A task list is a reusable checklist of task templates that is applied to a customer in one step - manually, from a CRM board column or help desk department, or automatically when a contact is created, a contract is activated or a contract is cancelled - creating one customer task per active item in the list.

TaskLists support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tasklists list --agent` | List all tasklists |
| `nexudus tasklists list --id <id> --agent` | Filter by single ID |
| `nexudus tasklists list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tasklists list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tasklists list --business-id <value> --business-name <value> --agent` | Filter tasklists by properties |
| `nexudus tasklists list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tasklists list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tasklists get <id> --agent` | Get single tasklist |
| `nexudus tasklists create --business-id <value> --name <value> --agent` | Create tasklist |
| `nexudus tasklists update <id> --name "New Name" --agent` | Update tasklist |
| `nexudus tasklists delete <id> --yes --agent` | Delete tasklist (no prompt) |

#### TaskList list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this task list; the list is also available to the other locations in the same network when tasks are assigned automatically |
| `--business-name` | string | Display value for Business.Name. |
| `--name` | string | Name of the task list, shown to operators when they pick a list to apply and copied onto every task created from it |
| `--active` | bool | Whether this list takes part in automatic assignment; when false the Assign To New Contacts, Assign To New Members and Assign To Cancellations rules are skipped, but the list can still be applied by hand, by a CRM board column or by a help desk department, none of which check this flag |
| `--assign-to-new-contacts` | bool | Whether the tasks in this list are assigned automatically when a customer is created without a plan (a contact); only applies while Active is true |
| `--assign-to-new-members` | bool | Whether the tasks in this list are assigned automatically when a customer contract is activated, limited to the plans in Tariffs; only applies while Active is true |
| `--assign-to-cancellations` | bool | Whether the tasks in this list are assigned automatically when a customer cancels their last remaining contract, limited to the plans in Tariffs; only applies while Active is true |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TaskList sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TaskList create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this task list; the list is also available to the other locations in the same network when tasks are assigned automatically |
| `--name` | string, required | Name of the task list, shown to operators when they pick a list to apply and copied onto every task created from it |
| `--active` | bool | Whether this list takes part in automatic assignment; when false the Assign To New Contacts, Assign To New Members and Assign To Cancellations rules are skipped, but the list can still be applied by hand, by a CRM board column or by a help desk department, none of which check this flag |
| `--tariffs` | list, repeat flag | List of plan IDs this list is restricted to when it is assigned automatically to new members or on cancellation; an empty list means every plan qualifies, and the new-contact rule ignores this restriction because contacts have no plan |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--assign-to-new-contacts` | bool | Whether the tasks in this list are assigned automatically when a customer is created without a plan (a contact); only applies while Active is true |
| `--assign-to-new-members` | bool | Whether the tasks in this list are assigned automatically when a customer contract is activated, limited to the plans in Tariffs; only applies while Active is true |
| `--assign-to-cancellations` | bool | Whether the tasks in this list are assigned automatically when a customer cancels their last remaining contract, limited to the plans in Tariffs; only applies while Active is true |

#### TaskList update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this task list; the list is also available to the other locations in the same network when tasks are assigned automatically |
| `--name` | string | Name of the task list, shown to operators when they pick a list to apply and copied onto every task created from it |
| `--active` | bool | Whether this list takes part in automatic assignment; when false the Assign To New Contacts, Assign To New Members and Assign To Cancellations rules are skipped, but the list can still be applied by hand, by a CRM board column or by a help desk department, none of which check this flag |
| `--tariffs` | list, repeat flag | List of plan IDs this list is restricted to when it is assigned automatically to new members or on cancellation; an empty list means every plan qualifies, and the new-contact rule ignores this restriction because contacts have no plan |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--assign-to-new-contacts` | bool | Whether the tasks in this list are assigned automatically when a customer is created without a plan (a contact); only applies while Active is true |
| `--assign-to-new-members` | bool | Whether the tasks in this list are assigned automatically when a customer contract is activated, limited to the plans in Tariffs; only applies while Active is true |
| `--assign-to-cancellations` | bool | Whether the tasks in this list are assigned automatically when a customer cancels their last remaining contract, limited to the plans in Tariffs; only applies while Active is true |

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TaskLists -->
