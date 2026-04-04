# Visitors

<!-- BEGIN:GENERATED entity=Visitors -->

Visitors support Search, Get, Create, Update, Delete.
Visitors also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus visitors list --agent` | List all visitors |
| `nexudus visitors list --id <id> --agent` | Filter by single ID |
| `nexudus visitors list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus visitors list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus visitors list --full-name <value> --email <value> --agent` | Filter visitors by properties |
| `nexudus visitors list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus visitors get <id> --agent` | Get single visitor |
| `nexudus visitors create --business-id <value> --full-name <value> --email <value> --expected-arrival <value> --agent` | Create visitor |
| `nexudus visitors update <id> --name "New Name" --agent` | Update visitor |
| `nexudus visitors delete <id> --yes --agent` | Delete visitor (no prompt) |
| `nexudus visitors run-command <key> <ids> --agent` | Run entity command |

#### Visitor list filter options

`--business-id`, `--full-name`, `--email`, `--coworker-id`, `--visitor-source`, `--host-approval-status`, `--checked-in-at`, `--notes`, `--customer-notes`, `--visit-reason`, `--company-name`, `--phone-number`, `--expected-arrival`, `--arrived`, `--arrival-date`, `--departure-date`, `--notified`, `--internal`, `--is-tour`, `--has-agreed-terms`, `--tour-confirmed`, `--access-control-scheduled-job-id`, `--check-in-now`

#### Visitor create options

`--business-id` (required), `--full-name` (required), `--email` (required), `--coworker-id`, `--visitor-source`, `--host-approval-status`, `--checked-in-at`, `--notes`, `--customer-notes`, `--visit-reason`, `--company-name`, `--phone-number`, `--expected-arrival` (required), `--arrived`, `--arrival-date`, `--departure-date`, `--notified`, `--internal`, `--is-tour`, `--has-agreed-terms`, `--tour-confirmed`, `--access-control-scheduled-job-id`, `--check-in-now`

#### Visitor update options

`--business-id`, `--full-name`, `--email`, `--coworker-id`, `--visitor-source`, `--host-approval-status`, `--checked-in-at`, `--notes`, `--customer-notes`, `--visit-reason`, `--company-name`, `--phone-number`, `--expected-arrival`, `--arrived`, `--arrival-date`, `--departure-date`, `--notified`, `--internal`, `--is-tour`, `--has-agreed-terms`, `--tour-confirmed`, `--access-control-scheduled-job-id`

### Visitor (key fields)

`Id`, `FullName`, `Email`, `CoworkerFullName`, `HostApprovalStatus`, `Arrived`

#### Visitor enum values

| Option | Valid values |
| ------ | ------------ |
| `--visitor-source` | `1` Administrator, `2` NexIO, `3` Customer |
| `--host-approval-status` | `1` NotRequired, `2` Requested, `3` Rejected, `4` AcceptedAndHold, `5` AcceptedAndGrant |

<!-- END:GENERATED entity=Visitors -->
