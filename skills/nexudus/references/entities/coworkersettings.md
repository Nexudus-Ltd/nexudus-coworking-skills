# CoworkerSettings

<!-- BEGIN:GENERATED entity=CoworkerSettings -->

A **CoworkerSetting** is a simple name/value pair attached to a customer. It acts as a key-value store for arbitrary custom data that is only accessible via the API — there is no corresponding UI in the Nexudus platform.

Typical uses include storing integration-specific identifiers, feature flags, or any metadata an external system needs to associate with a customer.

Each setting is uniquely identified by the combination of `CoworkerId` and `Name`. Values can be stored as plain text (`Value`) or encrypted (`EncryptedValue`) for sensitive data.

CoworkerSettings support Search, Get, Create, Update, Delete.
CoworkerSettings also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkersettings list --agent` | List all coworkersettings |
| `nexudus coworkersettings list --query "search" --agent` | Search coworkersettings by name |
| `nexudus coworkersettings list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkersettings get <id> --agent` | Get single coworkersetting |
| `nexudus coworkersettings create --coworker-id <value> --name <value> --agent` | Create coworkersetting |
| `nexudus coworkersettings update <id> --name "New Name" --agent` | Update coworkersetting |
| `nexudus coworkersettings delete <id> --yes --agent` | Delete coworkersetting (no prompt) |
| `nexudus coworkersettings run-command <key> <ids> --agent` | Run entity command |

#### CoworkerSetting create options

`--coworker-id` (required), `--name` (required), `--value`, `--encrypted-value`

#### CoworkerSetting update options

`--coworker-id`, `--name`, `--value`, `--encrypted-value`

### CoworkerSetting (key fields)

`Id`, `CoworkerId`, `Name`

<!-- END:GENERATED entity=CoworkerSettings -->
