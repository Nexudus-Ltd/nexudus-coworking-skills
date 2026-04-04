# CoworkerMessages

<!-- BEGIN:GENERATED entity=CoworkerMessages -->

CoworkerMessages support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkermessages list --agent` | List all coworkermessages |
| `nexudus coworkermessages list --id <id> --agent` | Filter by single ID |
| `nexudus coworkermessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkermessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkermessages list --coworker-id <value> --email-account-id <value> --agent` | Filter coworkermessages by properties |
| `nexudus coworkermessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkermessages get <id> --agent` | Get single coworkermessage |

#### CoworkerMessage list filter options

`--coworker-id`, `--email-account-id`, `--subject`, `--body`, `--message-id`, `--reminder-unique-id`

<!-- END:GENERATED entity=CoworkerMessages -->
