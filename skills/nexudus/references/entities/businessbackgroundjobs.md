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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--user-id` | long |  |
| `--job-id` | string | Unique identifier (GUID) of the background job |
| `--description` | string | Human-readable description of what the job does |
| `--files` | string | Files associated with the job (e.g. import files) |
| `--status` | string | Current status of the background job |
| `--result-data` | string | Result data produced when the job completes |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BusinessBackgroundJob PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--user-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:


<!-- END:GENERATED entity=BusinessBackgroundJobs -->
