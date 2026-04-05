# BusinessBackgroundJobs

<!-- BEGIN:GENERATED entity=BusinessBackgroundJobs -->

A **BusinessBackgroundJob** is an internal, read-only entity representing background jobs used for bulk edits or imports. It is not intended for direct use by end users.

Each record tracks a single asynchronous job: who triggered it, its current status, a human-readable description, and any result data produced when the job completes.

BusinessBackgroundJobs support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus businessbackgroundjobs list --agent` | List all businessbackgroundjobs |
| `nexudus businessbackgroundjobs list --id <id> --agent` | Filter by single ID |
| `nexudus businessbackgroundjobs list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus businessbackgroundjobs list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus businessbackgroundjobs list --business-id <value> --user-id <value> --agent` | Filter businessbackgroundjobs by properties |
| `nexudus businessbackgroundjobs list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus businessbackgroundjobs get <id> --agent` | Get single businessbackgroundjob |

#### BusinessBackgroundJob list filter options

`--business-id`, `--user-id`, `--job-id`, `--description`, `--files`, `--status`, `--result-data`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

<!-- END:GENERATED entity=BusinessBackgroundJobs -->
