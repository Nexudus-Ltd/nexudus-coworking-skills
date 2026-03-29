# Visitors

<!-- BEGIN:GENERATED entity=Visitors -->

Visitors support Search, Get, Create, Update, Delete.
Visitors also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus visitors list --agent` | List all visitors |
| `nexudus visitors list --query "search" --agent` | Search visitors by name |
| `nexudus visitors list --page 2 --size 10 --agent` | Paginated list |
| `nexudus visitors get <id> --agent` | Get single visitor |
| `nexudus visitors create --business <value> --full-name <value> --agent` | Create visitor |
| `nexudus visitors update <id> --name "New Name" --agent` | Update visitor |
| `nexudus visitors delete <id> --yes --agent` | Delete visitor (no prompt) |
| `nexudus visitors run-command <key> <ids> --agent` | Run entity command |

#### Visitor create options

`--business` (required), `--full-name` (required), `--email`, `--coworker-id`, `--visitor-source`, `--host-approval-status`, `--visitor-code`, `--checked-in-at`, `--notes`, `--customer-notes`, `--visit-reason`, `--company-name`, `--phone-number`, `--expected-arrival`, `--arrived`, `--arrival-date`, `--departure-date`, `--is-tour`, `--has-agreed-terms`, `--tour-confirmed`, `--check-in-now`

#### Visitor update options

`--full-name`, `--email`, `--coworker-id`, `--visitor-source`, `--host-approval-status`, `--visitor-code`, `--checked-in-at`, `--notes`, `--customer-notes`, `--visit-reason`, `--company-name`, `--phone-number`, `--expected-arrival`, `--arrived`, `--arrival-date`, `--departure-date`, `--is-tour`, `--has-agreed-terms`, `--tour-confirmed`, `--check-in-now`

### Visitor (key fields)

`Id`, `BusinessId`, `FullName`, `Email`, `CoworkerFullName`, `HostApprovalStatus`, `Arrived`

#### Visitor enum values

| Option | Valid values |
| ------ | ------------ |
| `--visitor-source` | `1` Administrator, `2` NexIO, `3` Customer |
| `--host-approval-status` | `1` NotRequired, `2` Requested, `3` Rejected, `4` AcceptedAndHold, `5` AcceptedAndGrant |

<!-- END:GENERATED entity=Visitors -->
