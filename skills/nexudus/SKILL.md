---
name: nexudus
description: Manage Nexudus coworking spaces via the `nexudus` CLI — businesses, products, authentication, and configuration.
metadata:
  triggers:
    - nexudus
    - coworking
    - business management
    - product management
    - spaces
user-invocable: true
---

# Nexudus CLI Agent Skill

You can manage Nexudus coworking spaces through the `nexudus` CLI tool. This skill teaches you how to authenticate, query data, and perform CRUD operations against the Nexudus platform API.

## Agent Invariants

1. **Always use `--agent` flag** on every CLI call. This returns a structured JSON envelope optimised for machine consumption.
2. **Parse the JSON envelope** before acting on results. The envelope has this shape:
   ```json
   {
     "ok": true,
     "data": { ... },
     "summary": "Human-readable summary",
     "breadcrumbs": ["entity", "action"],
     "meta": { "total": 10, "page": 1, "pageSize": 25, "totalPages": 1 }
   }
   ```
3. **Check `ok` first.** If `ok` is `false`, read `summary` for the error message and stop.
4. **Never prompt the user for credentials interactively.** If `ok` is `false` with an auth error, tell the user to run `nexudus login` manually.
5. **Use `--yes` or `-y` on delete commands** to skip interactive confirmation prompts.
6. **Use `--json` when you need raw data for scripting.** Use `--agent` when you want the envelope with summary.
7. **List responses omit collection properties.** The API only returns list/array fields (e.g., `Tariffs`, `Teams`, `LinkedResources`) when fetching a **single entity by ID** (`get <id>`). List commands return a simplified projection without these fields. If you need to read or verify a collection property, always fetch the individual entity first.
8. **Use the current user's defaults for business, currency, country, and timezone.** Before creating or updating entities that require a business (location), currency, country, or timezone, run `nexudus whoami --agent` and use the defaults from the response:
   - `DefaultBusinessId` — use as `--business` when creating entities scoped to a location.
   - `DefaultCurrencyId` — use as `--currency-id` when a currency is needed.
   - `DefaultCurrencyCode` — for display/reference purposes.
   - `DefaultCountryId` — use as `--country-id` when a country is needed.
   - `DefaultSimpleTimeZoneId` — use as `--timezone-id` when a timezone is needed.

   Only ask the user to specify these values if they explicitly want to override the defaults.

9. **Prefer `--{list}` over `--added-{list}` / `--removed-{list}` for list properties.** When setting a list field (e.g., `--tariffs`, `--resource-types`, `--teams`, `--linked-resources`), use the plain `--{list}` flag to replace the entire list with the supplied values. Only use `--added-{list}` or `--removed-{list}` when you specifically need to add or remove individual items from the existing list without touching the rest of its contents. Passing `--added-{list}` when you mean to set the full list is a common mistake that leaves stale entries in place.
10. **When unsure about a field, run `--help` first.** If the entity or option is not fully documented in this skill file, run `nexudus <entity> <command> --help` to discover available options and their descriptions before constructing the command.
11. **DateTime values must use ISO 8601 format.** All DateTime fields must be passed as `YYYY-MM-DDTHH:MM:SSZ` (UTC) — for example `2025-06-15T09:00:00Z`. Never use locale-specific formats like `June 15, 2025`, `15/06/2025`, or Unix timestamps. Entity reference files annotate DateTime options with `(DateTime)` so you can identify them.
12. **Always pass telemetry context flags** on every CLI call. See the [Telemetry Context](#telemetry-context) section below for the required flags and how to generate values.

## Bootstrapping

Run diagnostics first to verify the CLI is ready:

```shell
nexudus doctor --agent
```

This returns CLI version, .NET runtime, OS, credential status, config file location, API connectivity, and all available commands. Check `data.CredentialsStored` and `data.ApiStatus` before proceeding.

If credentials are missing, instruct the user:

> Run `nexudus login` to authenticate with your Nexudus account.

## CLI Introspection

Discover available commands and options at any time:

```shell
nexudus --help
nexudus businesses --help
nexudus products --help
nexudus config --help
```

Each command also supports `--help` for detailed option information:

```shell
nexudus businesses update --help
nexudus products create --help
```

## Command Reference

### Authentication

| Command          | Description                       |
| ---------------- | --------------------------------- |
| `nexudus login`  | Authenticate (interactive prompt) |
| `nexudus logout` | Clear stored credentials          |
| `nexudus whoami` | Show current authenticated user   |

### Configuration

| Command                            | Description         |
| ---------------------------------- | ------------------- |
| `nexudus config get <key>`         | Read a config value |
| `nexudus config set <key> <value>` | Set a config value  |

Config keys: `base-url`

### Diagnostics

```shell
nexudus doctor --agent
```

### Global Flags

| Flag                | Description                                            |
| ------------------- | ------------------------------------------------------ |
| `--agent`           | JSON envelope with summary (use this)                  |
| `--json`            | Raw JSON envelope                                      |
| `--md`              | Markdown output                                        |
| `--base-url <url>`  | Override API base URL                                  |
| `--trace-id <uuid>` | Trace ID to correlate commands within a single task    |
| `--caller <name>`   | Name of the invoking agent (e.g., `copilot`, `claude`) |
| `--intent <text>`   | One-line summary of the user's request                 |
| `--attempt <n>`     | Attempt number for this command (1 = first try)        |

## Telemetry Context

Every CLI call from an agent **must** include the four telemetry flags so command usage can be tracked, correlated, and debugged.

| Flag         | How to set                                                                                                      | Example                                                |
| ------------ | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| `--trace-id` | Generate **one UUID per user task** and reuse it for every CLI call in that task.                               | `--trace-id a1b2c3d4-e5f6-7890-abcd-ef1234567890`      |
| `--caller`   | A fixed string identifying your agent. Use your agent name in lowercase.                                        | `--caller copilot`                                     |
| `--intent`   | A short (≤120 char) summary of **what the user asked for**. Same for all calls in the task. Quote spaces.       | `--intent "list all products for the London business"` |
| `--attempt`  | Start at `1`. Increment if you retry the **same command** after a failure. Reset to `1` for different commands. | `--attempt 1`                                          |

### Example: full call with telemetry

```shell
nexudus products list --agent --trace-id a1b2c3d4-e5f6-7890-abcd-ef1234567890 --caller copilot --intent "list all products" --attempt 1
```

### Rules

- **Same `--trace-id`** for every call within the same user task / conversation turn.
- **Increment `--attempt`** only when retrying the exact same command after a failure.
- **`--caller`** must stay constant for the agent's lifetime (e.g., `copilot`, `claude`, `custom-bot`).
- **`--intent`** should be the user's original request, not the CLI command description.
- When `--agent` is set and telemetry flags are present, the response envelope includes a `telemetry` object with `traceId`, `durationMs`, and `attempt` for your reference.

## Output Envelope

All commands produce a JSON envelope when `--agent` or `--json` is used:

```json
{
  "ok": true,
  "data": [ ... ],
  "summary": "Found 3 businesses (page 1/1)",
  "breadcrumbs": ["businesses", "list"],
  "meta": {
    "total": 3,
    "page": 1,
    "pageSize": 25,
    "totalPages": 1
  }
}
```

- **`ok`**: `true` on success, `false` on failure.
- **`data`**: The response payload — an object for single-entity operations, an array for lists, or null on some failures.
- **`summary`**: Human-readable result description.
- **`breadcrumbs`**: Command path that produced the output (e.g., `["products", "create"]`).
- **`meta`**: Pagination metadata for list operations (present only on list commands).

### Error envelope

```json
{
  "ok": false,
  "data": null,
  "summary": "Not logged in. Run 'nexudus login' first.",
  "breadcrumbs": ["businesses", "list"]
}
```

## Decision Trees

### "Find and display a business"

1. `nexudus businesses list --agent` (or use filter options like `--name "value"` if searching)
2. Parse `data` array, find the target business
3. `nexudus businesses get <id> --agent` for full details

### "Create a entity"

1. First find the business ID: `nexudus businesses list --agent`
2. `nexudus <entity> create --name "Day Pass" --price 25.00 --business <businessId> --agent`
3. Check `ok` is `true`, read `data.Id` for the new entity ID

### "Update a entity property"

1. `nexudus <entity> get <id> --agent` to verify the entity exists
2. `nexudus <entity> update <id> --<property> <value> --agent`
3. Verify the update by checking the returned `data`

### "Delete a entity"

1. `nexudus <entity> get <id> --agent` to confirm the entity exists
2. `nexudus <entity> delete <id> --yes --agent`
3. Check `ok` is `true`

### "List entity for a specific business"

1. `nexudus <entity> list --business <businessId> --agent`
2. For pagination: add `--page-number N --page-size M`

### "Run an entity command on entity"

1. `nexudus <entity> commands --agent` to discover available commands
2. `nexudus <entity> run-command <commandKey> <id1,id2> --agent`
3. Add parameters with `-p Name=Value` if the command requires them

### "Check CLI health"

1. `nexudus doctor --agent`
2. Verify `data.CredentialsStored` is `true`
3. Verify `data.ApiStatus` is `"OK"`

> **Entity-specific workflows** (e.g., adding passes to a product, setting up pricing) are documented in the corresponding entity reference file under `references/entities/`.

## Error Handling

| Error                                            | Meaning                  | Action                                        |
| ------------------------------------------------ | ------------------------ | --------------------------------------------- |
| `ok: false`, summary contains "Not logged in"    | No stored credentials    | Tell user to run `nexudus login`              |
| `ok: false`, summary contains "Unauthorized"     | Invalid credentials      | Tell user to run `nexudus login` again        |
| `ok: false`, summary contains "Forbidden"        | Insufficient permissions | Inform user they lack API permissions         |
| `ok: false`, summary contains "not found"        | Entity doesn't exist     | Check the ID and try again                    |
| `ok: false`, summary contains "Failed to create" | Create validation error  | Check required fields (name, business, price) |
| Non-zero exit code                               | Command failed           | Read stderr or the JSON envelope for details  |

## Entity Index

Before working with an entity, load its reference file for full details (commands, options, key fields, enum values, and entity-specific workflows).

<!-- BEGIN:GENERATED-INDEX -->

| Entity                             | CLI command                           | Operations                                  | Reference                                                                                              |
| ---------------------------------- | ------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| AccessToken                        | `accesstokens`                        | list, get, create, update, delete           | [accesstokens.md](./references/entities/accesstokens.md)                                               |
| Application                        | `applications`                        | list, get, create, update, delete           | [applications.md](./references/entities/applications.md)                                               |
| AudioFile                          | `audiofiles`                          | list, get, create, update, delete           | [audiofiles.md](./references/entities/audiofiles.md)                                                   |
| AuditTrailEntry                    | `audittrailentries`                   | list, get                                   | [audittrailentries.md](./references/entities/audittrailentries.md)                                     |
| AutomationTile                     | `automationtiles`                     | list, get, create, update, delete           | [automationtiles.md](./references/entities/automationtiles.md)                                         |
| AutomationTileAudit                | `automationtileaudits`                | list, get, create, update, delete           | [automationtileaudits.md](./references/entities/automationtileaudits.md)                               |
| BasketSession                      | `basketsessions`                      | list, get, create, update, delete           | [basketsessions.md](./references/entities/basketsessions.md)                                           |
| BlogCategory                       | `blogcategories`                      | list, get, create, update, delete           | [blogcategories.md](./references/entities/blogcategories.md)                                           |
| BlogPost                           | `blogposts`                           | list, get, create, update, delete           | [blogposts.md](./references/entities/blogposts.md)                                                     |
| BlogPostComment                    | `blogpostcomments`                    | list, get, create, update, delete           | [blogpostcomments.md](./references/entities/blogpostcomments.md)                                       |
| Booking                            | `bookings`                            | list, get, create, update, delete           | [bookings.md](./references/entities/bookings.md)                                                       |
| BookingAvailabilityException       | `bookingavailabilityexceptions`       | list, get, create, update, delete           | [bookingavailabilityexceptions.md](./references/entities/bookingavailabilityexceptions.md)             |
| BookingNote                        | `bookingnotes`                        | list, get, create, update, delete           | [bookingnotes.md](./references/entities/bookingnotes.md)                                               |
| BookingProduct                     | `bookingproducts`                     | list, get, create, update, delete           | [bookingproducts.md](./references/entities/bookingproducts.md)                                         |
| BookingVisitor                     | `bookingvisitors`                     | list, get, create, update, delete           | [bookingvisitors.md](./references/entities/bookingvisitors.md)                                         |
| Business                           | `businesses`                          | list, get, update                           | [businesses.md](./references/entities/businesses.md)                                                   |
| BusinessAnnouncement               | `businessannouncements`               | list, get, create, update, delete           | [businessannouncements.md](./references/entities/businessannouncements.md)                             |
| BusinessBackgroundJob              | `businessbackgroundjobs`              | list, get                                   | [businessbackgroundjobs.md](./references/entities/businessbackgroundjobs.md)                           |
| BusinessCharge                     | `businesscharges`                     | list, get, create, update, delete           | [businesscharges.md](./references/entities/businesscharges.md)                                         |
| BusinessDomain                     | `businessdomains`                     | list, get, create, update, delete           | [businessdomains.md](./references/entities/businessdomains.md)                                         |
| BusinessRedirection                | `businessredirections`                | list, get, create, update, delete           | [businessredirections.md](./references/entities/businessredirections.md)                               |
| BusinessSetting                    | `businesssettings`                    | list, get, create, update, delete           | [businesssettings.md](./references/entities/businesssettings.md)                                       |
| BusinessTimeSlot                   | `businesstimeslots`                   | list, get, create, update, delete           | [businesstimeslots.md](./references/entities/businesstimeslots.md)                                     |
| CalendarEvent                      | `calendarevents`                      | list, get, create, update, delete           | [calendarevents.md](./references/entities/calendarevents.md)                                           |
| CalendarEventCategory              | `calendareventcategories`             | list, get, create, update, delete           | [calendareventcategories.md](./references/entities/calendareventcategories.md)                         |
| CancelledBooking                   | `cancelledbookings`                   | list, get, create, update, delete           | [cancelledbookings.md](./references/entities/cancelledbookings.md)                                     |
| CannedResponse                     | `cannedresponses`                     | list, get, create, update, delete           | [cannedresponses.md](./references/entities/cannedresponses.md)                                         |
| Charge                             | `charges`                             | list, get, create, update, delete           | [charges.md](./references/entities/charges.md)                                                         |
| ChatRoom                           | `chatrooms`                           | list, get, create, update, delete           | [chatrooms.md](./references/entities/chatrooms.md)                                                     |
| ChatUserMessage                    | `chatusermessages`                    | list, get, create, update, delete           | [chatusermessages.md](./references/entities/chatusermessages.md)                                       |
| Checkin                            | `checkins`                            | list, get, create, update, delete           | [checkins.md](./references/entities/checkins.md)                                                       |
| CommunityGroup                     | `communitygroups`                     | list, get, create, update, delete           | [communitygroups.md](./references/entities/communitygroups.md)                                         |
| CommunityMessage                   | `communitymessages`                   | list, get, create, update, delete           | [communitymessages.md](./references/entities/communitymessages.md)                                     |
| CommunityMessageLike               | `communitymessagelikes`               | list, get, create, update, delete           | [communitymessagelikes.md](./references/entities/communitymessagelikes.md)                             |
| CommunityPerk                      | `communityperks`                      | list, get, create, update, delete           | [communityperks.md](./references/entities/communityperks.md)                                           |
| CommunityThread                    | `communitythreads`                    | list, get, create, update, delete           | [communitythreads.md](./references/entities/communitythreads.md)                                       |
| CommunityThreadFile                | `communitythreadfiles`                | list, get, create, update, delete           | [communitythreadfiles.md](./references/entities/communitythreadfiles.md)                               |
| CommunityThreadFollow              | `communitythreadfollows`              | list, get, create, update, delete           | [communitythreadfollows.md](./references/entities/communitythreadfollows.md)                           |
| CommunityThreadLike                | `communitythreadlikes`                | list, get, create, update, delete           | [communitythreadlikes.md](./references/entities/communitythreadlikes.md)                               |
| CommunityThreadMute                | `communitythreadmutes`                | list, get, create, update, delete           | [communitythreadmutes.md](./references/entities/communitythreadmutes.md)                               |
| ContractContact                    | `contractcontacts`                    | list, get, create, update, delete           | [contractcontacts.md](./references/entities/contractcontacts.md)                                       |
| ContractDeposit                    | `contractdeposits`                    | list, get, create, update, delete           | [contractdeposits.md](./references/entities/contractdeposits.md)                                       |
| ContractPausedPeriod               | `contractpausedperiods`               | list, get, create, update, delete           | [contractpausedperiods.md](./references/entities/contractpausedperiods.md)                             |
| ContractProduct                    | `contractproducts`                    | list, get, create, update, delete           | [contractproducts.md](./references/entities/contractproducts.md)                                       |
| ContractSchedule                   | `contractschedules`                   | list, get, create, update, delete           | [contractschedules.md](./references/entities/contractschedules.md)                                     |
| Country                            | `countries`                           | list, get                                   | [countries.md](./references/entities/countries.md)                                                     |
| Course                             | `courses`                             | list, get, create, update, delete           | [courses.md](./references/entities/courses.md)                                                         |
| CourseCompletedLesson              | `coursecompletedlessons`              | list, get, create, update, delete           | [coursecompletedlessons.md](./references/entities/coursecompletedlessons.md)                           |
| CourseLesson                       | `courselessons`                       | list, get, create, update, delete           | [courselessons.md](./references/entities/courselessons.md)                                             |
| CourseMember                       | `coursemembers`                       | list, get, create, update, delete           | [coursemembers.md](./references/entities/coursemembers.md)                                             |
| CourseSection                      | `coursesections`                      | list, get, create, update, delete           | [coursesections.md](./references/entities/coursesections.md)                                           |
| Coworker                           | `coworkers`                           | list, get, create, update, commands         | [coworkers.md](./references/entities/coworkers.md)                                                     |
| CoworkerAccessControlAudit         | `coworkeraccesscontrolaudits`         | list, get, create, update, delete           | [coworkeraccesscontrolaudits.md](./references/entities/coworkeraccesscontrolaudits.md)                 |
| CoworkerBookingCredit              | `coworkerbookingcredits`              | list, get, create, update, delete           | [coworkerbookingcredits.md](./references/entities/coworkerbookingcredits.md)                           |
| CoworkerBookingCreditUseHistory    | `coworkerbookingcreditusehistories`   | list, get, create, update                   | [coworkerbookingcreditusehistories.md](./references/entities/coworkerbookingcreditusehistories.md)     |
| CoworkerContract                   | `coworkercontracts`                   | list, get, create, update, delete           | [coworkercontracts.md](./references/entities/coworkercontracts.md)                                     |
| CoworkerDataFile                   | `coworkerdatafiles`                   | list, get, create, update, delete           | [coworkerdatafiles.md](./references/entities/coworkerdatafiles.md)                                     |
| CoworkerDelivery                   | `coworkerdeliveries`                  | list, get, create, update, delete           | [coworkerdeliveries.md](./references/entities/coworkerdeliveries.md)                                   |
| CoworkerDiscountCode               | `coworkerdiscountcodes`               | list, get, create, update, delete           | [coworkerdiscountcodes.md](./references/entities/coworkerdiscountcodes.md)                             |
| CoworkerExtraService               | `coworkerextraservices`               | list, get, create, update, delete           | [coworkerextraservices.md](./references/entities/coworkerextraservices.md)                             |
| CoworkerExtraServiceUseHistory     | `coworkerextraserviceusehistories`    | list, get, create, update, delete           | [coworkerextraserviceusehistories.md](./references/entities/coworkerextraserviceusehistories.md)       |
| CoworkerGoogleCalendar             | `coworkergooglecalendars`             | list, get, create, update, delete           | [coworkergooglecalendars.md](./references/entities/coworkergooglecalendars.md)                         |
| CoworkerIdentityCheck              | `coworkeridentitychecks`              | list, get, create, update, delete           | [coworkeridentitychecks.md](./references/entities/coworkeridentitychecks.md)                           |
| CoworkerIdentityCheckDocument      | `coworkeridentitycheckdocuments`      | list, get, create, update, delete           | [coworkeridentitycheckdocuments.md](./references/entities/coworkeridentitycheckdocuments.md)           |
| CoworkerInventoryAsset             | `coworkerinventoryassets`             | list, get, create, update, delete           | [coworkerinventoryassets.md](./references/entities/coworkerinventoryassets.md)                         |
| CoworkerInvoice                    | `coworkerinvoices`                    | list, get, update                           | [coworkerinvoices.md](./references/entities/coworkerinvoices.md)                                       |
| CoworkerInvoiceHistory             | `coworkerinvoicehistories`            | list, get, create, update, delete           | [coworkerinvoicehistories.md](./references/entities/coworkerinvoicehistories.md)                       |
| CoworkerInvoiceLine                | `coworkerinvoicelines`                | list, get, update                           | [coworkerinvoicelines.md](./references/entities/coworkerinvoicelines.md)                               |
| CoworkerInvoicePaymentToken        | `coworkerinvoicepaymenttokens`        | list, get, create, update, delete           | [coworkerinvoicepaymenttokens.md](./references/entities/coworkerinvoicepaymenttokens.md)               |
| CoworkerLedgerEntry                | `coworkerledgerentries`               | list, get, create, update, delete           | [coworkerledgerentries.md](./references/entities/coworkerledgerentries.md)                             |
| CoworkerLegalContentAudit          | `coworkerlegalcontentaudits`          | list, get, create, update, delete           | [coworkerlegalcontentaudits.md](./references/entities/coworkerlegalcontentaudits.md)                   |
| CoworkerMessage                    | `coworkermessages`                    | list, get                                   | [coworkermessages.md](./references/entities/coworkermessages.md)                                       |
| CoworkerMsOfficeCalendar           | `coworkermsofficecalendars`           | list, get, create, update, delete           | [coworkermsofficecalendars.md](./references/entities/coworkermsofficecalendars.md)                     |
| CoworkerNote                       | `coworkernotes`                       | list, get, create, update, delete           | [coworkernotes.md](./references/entities/coworkernotes.md)                                             |
| CoworkerNotification               | `coworkernotifications`               | list, get, create, update, delete           | [coworkernotifications.md](./references/entities/coworkernotifications.md)                             |
| CoworkerPaymentMethod              | `coworkerpaymentmethods`              | list, get, create, update, delete           | [coworkerpaymentmethods.md](./references/entities/coworkerpaymentmethods.md)                           |
| CoworkerPricePlanHistory           | `coworkerpriceplanhistories`          | list, get                                   | [coworkerpriceplanhistories.md](./references/entities/coworkerpriceplanhistories.md)                   |
| CoworkerProduct                    | `coworkerproducts`                    | list, get, create, update, delete           | [coworkerproducts.md](./references/entities/coworkerproducts.md)                                       |
| CoworkerReminderAudit              | `coworkerreminderaudits`              | list, get, create, update, delete           | [coworkerreminderaudits.md](./references/entities/coworkerreminderaudits.md)                           |
| CoworkerSetting                    | `coworkersettings`                    | list, get, create, update, delete           | [coworkersettings.md](./references/entities/coworkersettings.md)                                       |
| CoworkerTask                       | `coworkertasks`                       | list, get, create, update, delete           | [coworkertasks.md](./references/entities/coworkertasks.md)                                             |
| CoworkerTimePass                   | `coworkertimepasses`                  | list, get, create, update, delete           | [coworkertimepasses.md](./references/entities/coworkertimepasses.md)                                   |
| CrmBoard                           | `crmboards`                           | list, get, create, update, delete           | [crmboards.md](./references/entities/crmboards.md)                                                     |
| CrmBoardColumn                     | `crmboardcolumns`                     | list, get, create, update, delete           | [crmboardcolumns.md](./references/entities/crmboardcolumns.md)                                         |
| CrmOpportunity                     | `crmopportunities`                    | list, get, create, update, delete           | [crmopportunities.md](./references/entities/crmopportunities.md)                                       |
| CrmOpportunityHistory              | `crmopportunityhistories`             | list, get, create, update, delete           | [crmopportunityhistories.md](./references/entities/crmopportunityhistories.md)                         |
| CrmOpportunityImportFile           | `crmopportunityimportfiles`           | list, get, create, update, delete           | [crmopportunityimportfiles.md](./references/entities/crmopportunityimportfiles.md)                     |
| Currency                           | `currencies`                          | list, get                                   | [currencies.md](./references/entities/currencies.md)                                                   |
| CustomField                        | `customfields`                        | list, get, create, update, delete           | [customfields.md](./references/entities/customfields.md)                                               |
| DataFile                           | `datafiles`                           | list, get, create, update, delete           | [datafiles.md](./references/entities/datafiles.md)                                                     |
| DiscountCode                       | `discountcodes`                       | list, get, create, update, delete           | [discountcodes.md](./references/entities/discountcodes.md)                                             |
| DocumentTemplate                   | `documenttemplates`                   | list, get, create, update, delete           | [documenttemplates.md](./references/entities/documenttemplates.md)                                     |
| EloxxLockersAudit                  | `eloxxlockersaudits`                  | list, get, create, update, delete           | [eloxxlockersaudits.md](./references/entities/eloxxlockersaudits.md)                                   |
| EmailAccount                       | `emailaccounts`                       | list, get, create, update, delete           | [emailaccounts.md](./references/entities/emailaccounts.md)                                             |
| EmailQueueItem                     | `emailqueueitems`                     | list, get                                   | [emailqueueitems.md](./references/entities/emailqueueitems.md)                                         |
| EmailQueueItemAttachment           | `emailqueueitemattachments`           | list, get, update                           | [emailqueueitemattachments.md](./references/entities/emailqueueitemattachments.md)                     |
| EmailTemplateFile                  | `emailtemplatefiles`                  | list, get, create, update, delete           | [emailtemplatefiles.md](./references/entities/emailtemplatefiles.md)                                   |
| EventAttendee                      | `eventattendees`                      | list, get, create, update, delete           | [eventattendees.md](./references/entities/eventattendees.md)                                           |
| EventComment                       | `eventcomments`                       | list, get, create, update, delete           | [eventcomments.md](./references/entities/eventcomments.md)                                             |
| EventProduct                       | `eventproducts`                       | list, get, create, update, delete           | [eventproducts.md](./references/entities/eventproducts.md)                                             |
| EventWaitingAttendee               | `eventwaitingattendees`               | list, get, create, update, delete           | [eventwaitingattendees.md](./references/entities/eventwaitingattendees.md)                             |
| ExtraService                       | `extraservices`                       | list, get, create, update, delete           | [extraservices.md](./references/entities/extraservices.md)                                             |
| ExtraServicePrice                  | `extraserviceprices`                  | list, get, create, update, delete           | [extraserviceprices.md](./references/entities/extraserviceprices.md)                                   |
| ExtraServiceTimeSlot               | `extraservicetimeslots`               | list, get, create, update, delete           | [extraservicetimeslots.md](./references/entities/extraservicetimeslots.md)                             |
| FailedCheckin                      | `failedcheckins`                      | list, get, create, update, delete           | [failedcheckins.md](./references/entities/failedcheckins.md)                                           |
| FaqArticle                         | `faqarticles`                         | list, get, create, update, delete           | [faqarticles.md](./references/entities/faqarticles.md)                                                 |
| FinancialAccount                   | `financialaccounts`                   | list, get, create, update, delete           | [financialaccounts.md](./references/entities/financialaccounts.md)                                     |
| FloorPlan                          | `floorplans`                          | list, get, create, update, delete           | [floorplans.md](./references/entities/floorplans.md)                                                   |
| FloorPlanAsset                     | `floorplanassets`                     | list, get                                   | [floorplanassets.md](./references/entities/floorplanassets.md)                                         |
| FloorPlanDesk                      | `floorplandesks`                      | list, get, create, update, delete           | [floorplandesks.md](./references/entities/floorplandesks.md)                                           |
| FloorPlanDeskVariant               | `floorplandeskvariants`               | list, get, create, update, delete           | [floorplandeskvariants.md](./references/entities/floorplandeskvariants.md)                             |
| FloorPlanLayout                    | `floorplanlayouts`                    | list, get, create, update, delete           | [floorplanlayouts.md](./references/entities/floorplanlayouts.md)                                       |
| FloorPlanLayoutArea                | `floorplanlayoutareas`                | list, get, create, update, delete           | [floorplanlayoutareas.md](./references/entities/floorplanlayoutareas.md)                               |
| FloorPlanLayoutAsset               | `floorplanlayoutassets`               | list, get, create, update, delete           | [floorplanlayoutassets.md](./references/entities/floorplanlayoutassets.md)                             |
| FloorPlanLayoutEdge                | `floorplanlayoutedges`                | list, get, create, update, delete           | [floorplanlayoutedges.md](./references/entities/floorplanlayoutedges.md)                               |
| FloorPlanLayoutNode                | `floorplanlayoutnodes`                | list, get, create, update, delete           | [floorplanlayoutnodes.md](./references/entities/floorplanlayoutnodes.md)                               |
| FloorPlanLayoutOpening             | `floorplanlayoutopenings`             | list, get, create, update, delete           | [floorplanlayoutopenings.md](./references/entities/floorplanlayoutopenings.md)                         |
| FloorplanLayoutTransition          | `floorplanlayouttransitions`          | list, get, create, update, delete           | [floorplanlayouttransitions.md](./references/entities/floorplanlayouttransitions.md)                   |
| FormPage                           | `formpages`                           | list, get, create, update, delete           | [formpages.md](./references/entities/formpages.md)                                                     |
| FormPageAnswer                     | `formpageanswers`                     | list, get, create, update                   | [formpageanswers.md](./references/entities/formpageanswers.md)                                         |
| FormPageQuestion                   | `formpagequestions`                   | list, get, create, update, delete           | [formpagequestions.md](./references/entities/formpagequestions.md)                                     |
| FormPageRequest                    | `formpagerequests`                    | list, get, create, update, delete           | [formpagerequests.md](./references/entities/formpagerequests.md)                                       |
| GlobalChatMessage                  | `globalchatmessages`                  | list, get, create, update, delete           | [globalchatmessages.md](./references/entities/globalchatmessages.md)                                   |
| HelpDeskComment                    | `helpdeskcomments`                    | list, get, create, update, delete           | [helpdeskcomments.md](./references/entities/helpdeskcomments.md)                                       |
| HelpDeskDepartment                 | `helpdeskdepartments`                 | list, get, create, update, delete           | [helpdeskdepartments.md](./references/entities/helpdeskdepartments.md)                                 |
| HelpDeskMessage                    | `helpdeskmessages`                    | list, get, create, update, delete           | [helpdeskmessages.md](./references/entities/helpdeskmessages.md)                                       |
| ImageFile                          | `imagefiles`                          | list, get, create, update, delete           | [imagefiles.md](./references/entities/imagefiles.md)                                                   |
| InstalledApplication               | `installedapplications`               | list, get, create, update, delete           | [installedapplications.md](./references/entities/installedapplications.md)                             |
| InstalledMarketPlaceApplication    | `installedmarketplaceapplications`    | list, get, create, update, delete           | [installedmarketplaceapplications.md](./references/entities/installedmarketplaceapplications.md)       |
| InventoryAsset                     | `inventoryassets`                     | list, get, create, update, delete           | [inventoryassets.md](./references/entities/inventoryassets.md)                                         |
| Invoice                            | `invoices`                            | list, get, update                           | [invoices.md](./references/entities/invoices.md)                                                       |
| Language                           | `languages`                           | list, get, create, update, delete           | [languages.md](./references/entities/languages.md)                                                     |
| LanguageToken                      | `languagetokens`                      | list, get, create, update, delete           | [languagetokens.md](./references/entities/languagetokens.md)                                           |
| LedgerEntry                        | `ledgerentries`                       | list, get                                   | [ledgerentries.md](./references/entities/ledgerentries.md)                                             |
| LegalContentAudit                  | `legalcontentaudits`                  | list, get, create, update, delete           | [legalcontentaudits.md](./references/entities/legalcontentaudits.md)                                   |
| LogEntry                           | `logentries`                          | list, get                                   | [logentries.md](./references/entities/logentries.md)                                                   |
| MarketPlaceApplication             | `marketplaceapplications`             | list, get, create, update, delete           | [marketplaceapplications.md](./references/entities/marketplaceapplications.md)                         |
| MsOfficeAdminCalendar              | `msofficeadmincalendars`              | list, get, create, update, delete           | [msofficeadmincalendars.md](./references/entities/msofficeadmincalendars.md)                           |
| NewsLetter                         | `newsletters`                         | list, get, create, update, delete           | [newsletters.md](./references/entities/newsletters.md)                                                 |
| NewsLetterSubscriber               | `newslettersubscribers`               | list, get, create, update, delete           | [newslettersubscribers.md](./references/entities/newslettersubscribers.md)                             |
| OpenAiChatMessage                  | `openaichatmessages`                  | list, get, create, update, delete           | [openaichatmessages.md](./references/entities/openaichatmessages.md)                                   |
| OpportunityType                    | `opportunitytypes`                    | list, get, create, update, delete           | [opportunitytypes.md](./references/entities/opportunitytypes.md)                                       |
| PassportCard                       | `passportcards`                       | list, get, create, update, delete           | [passportcards.md](./references/entities/passportcards.md)                                             |
| PaymentGateway                     | `paymentgateways`                     | list, get, create, update, delete           | [paymentgateways.md](./references/entities/paymentgateways.md)                                         |
| PayoutInvoice                      | `payoutinvoices`                      | list, get, create, update, delete           | [payoutinvoices.md](./references/entities/payoutinvoices.md)                                           |
| PlatformChangeMessage              | `platformchangemessages`              | list, get, create, update, delete           | [platformchangemessages.md](./references/entities/platformchangemessages.md)                           |
| Product                            | `products`                            | list, get, create, update, delete, commands | [products.md](./references/entities/products.md)                                                       |
| ProductBookingCredit               | `productbookingcredits`               | list, get, create, update, delete           | [productbookingcredits.md](./references/entities/productbookingcredits.md)                             |
| ProductExtraService                | `productextraservices`                | list, get, create, update, delete           | [productextraservices.md](./references/entities/productextraservices.md)                               |
| ProductTimePass                    | `producttimepasses`                   | list, get, create, update, delete           | [producttimepasses.md](./references/entities/producttimepasses.md)                                     |
| Proposal                           | `proposals`                           | list, get, create, update, delete           | [proposals.md](./references/entities/proposals.md)                                                     |
| ProposalContract                   | `proposalcontracts`                   | list, get, create, update, delete           | [proposalcontracts.md](./references/entities/proposalcontracts.md)                                     |
| ProposalContractSchedule           | `proposalcontractschedules`           | list, get, create, update, delete           | [proposalcontractschedules.md](./references/entities/proposalcontractschedules.md)                     |
| ProposalProduct                    | `proposalproducts`                    | list, get, create, update, delete           | [proposalproducts.md](./references/entities/proposalproducts.md)                                       |
| ProposalSchedule                   | `proposalschedules`                   | list, get, create, update, delete           | [proposalschedules.md](./references/entities/proposalschedules.md)                                     |
| RadiusServer                       | `radiusservers`                       | list, get, create, update, delete           | [radiusservers.md](./references/entities/radiusservers.md)                                             |
| RefreshToken                       | `refreshtokens`                       | list, get, create, update, delete           | [refreshtokens.md](./references/entities/refreshtokens.md)                                             |
| RegisteredDevice                   | `registereddevices`                   | list, get, update                           | [registereddevices.md](./references/entities/registereddevices.md)                                     |
| Reminder                           | `reminders`                           | list, get, create, update, delete           | [reminders.md](./references/entities/reminders.md)                                                     |
| Report                             | `reports`                             | list, get, create, update, delete           | [reports.md](./references/entities/reports.md)                                                         |
| Reseller                           | `resellers`                           | list, get, create, update, delete           | [resellers.md](./references/entities/resellers.md)                                                     |
| ResellerAccount                    | `reselleraccounts`                    | list, get, create, update, delete           | [reselleraccounts.md](./references/entities/reselleraccounts.md)                                       |
| ResellerPayout                     | `resellerpayouts`                     | list, get, create, update, delete           | [resellerpayouts.md](./references/entities/resellerpayouts.md)                                         |
| Resource                           | `resources`                           | list, get, create, update, delete           | [resources.md](./references/entities/resources.md)                                                     |
| ResourceAccessRule                 | `resourceaccessrules`                 | list, get, create, update, delete           | [resourceaccessrules.md](./references/entities/resourceaccessrules.md)                                 |
| ResourceAccessRuleEligibleTimeSlot | `resourceaccessruleeligibletimeslots` | list, get, create, update, delete           | [resourceaccessruleeligibletimeslots.md](./references/entities/resourceaccessruleeligibletimeslots.md) |
| ResourceAccessRuleTimeSlot         | `resourceaccessruletimeslots`         | list, get, create, update, delete           | [resourceaccessruletimeslots.md](./references/entities/resourceaccessruletimeslots.md)                 |
| ResourceProduct                    | `resourceproducts`                    | list, get, create, update, delete           | [resourceproducts.md](./references/entities/resourceproducts.md)                                       |
| ResourceTimeSlot                   | `resourcetimeslots`                   | list, get, create, update, delete           | [resourcetimeslots.md](./references/entities/resourcetimeslots.md)                                     |
| ResourceType                       | `resourcetypes`                       | list, get, create, update, delete           | [resourcetypes.md](./references/entities/resourcetypes.md)                                             |
| Role                               | `roles`                               | list, get                                   | [roles.md](./references/entities/roles.md)                                                             |
| Sensor                             | `sensors`                             | list, get, create, update, delete           | [sensors.md](./references/entities/sensors.md)                                                         |
| SensorHistory                      | `sensorhistories`                     | list, get, create, update, delete           | [sensorhistories.md](./references/entities/sensorhistories.md)                                         |
| SimpleTimeZone                     | `simpletimezones`                     | list, get, update                           | [simpletimezones.md](./references/entities/simpletimezones.md)                                         |
| SubscriberActivity                 | `subscriberactivities`                | list, get                                   | [subscriberactivities.md](./references/entities/subscriberactivities.md)                               |
| SubscriberGroup                    | `subscribergroups`                    | list, get, create, update, delete           | [subscribergroups.md](./references/entities/subscribergroups.md)                                       |
| Survey                             | `surveys`                             | list, get, create, update, delete           | [surveys.md](./references/entities/surveys.md)                                                         |
| SurveyAnswer                       | `surveyanswers`                       | list, get, create, update, delete           | [surveyanswers.md](./references/entities/surveyanswers.md)                                             |
| SurveyQuestion                     | `surveyquestions`                     | list, get, create, update, delete           | [surveyquestions.md](./references/entities/surveyquestions.md)                                         |
| SurveyRun                          | `surveyruns`                          | list, get, create, update, delete           | [surveyruns.md](./references/entities/surveyruns.md)                                                   |
| SystemNotification                 | `systemnotifications`                 | list, get, create, update, delete           | [systemnotifications.md](./references/entities/systemnotifications.md)                                 |
| Tariff                             | `tariffs`                             | list, get, create, update, delete           | [tariffs.md](./references/entities/tariffs.md)                                                         |
| TariffBookingCredit                | `tariffbookingcredits`                | list, get, create, update, delete           | [tariffbookingcredits.md](./references/entities/tariffbookingcredits.md)                               |
| TariffDefaultDueDate               | `tariffdefaultduedates`               | list, get, create, update, delete           | [tariffdefaultduedates.md](./references/entities/tariffdefaultduedates.md)                             |
| TariffExtraService                 | `tariffextraservices`                 | list, get, create, update, delete           | [tariffextraservices.md](./references/entities/tariffextraservices.md)                                 |
| TariffProduct                      | `tariffproducts`                      | list, get, create, update, delete           | [tariffproducts.md](./references/entities/tariffproducts.md)                                           |
| TariffSignupProduct                | `tariffsignupproducts`                | list, get, create, update, delete           | [tariffsignupproducts.md](./references/entities/tariffsignupproducts.md)                               |
| TariffTimePass                     | `tarifftimepasses`                    | list, get, create, update, delete           | [tarifftimepasses.md](./references/entities/tarifftimepasses.md)                                       |
| TaskItem                           | `taskitems`                           | list, get, create, update, delete           | [taskitems.md](./references/entities/taskitems.md)                                                     |
| TaskList                           | `tasklists`                           | list, get, create, update, delete           | [tasklists.md](./references/entities/tasklists.md)                                                     |
| TaxRate                            | `taxrates`                            | list, get, create, update, delete           | [taxrates.md](./references/entities/taxrates.md)                                                       |
| Team                               | `teams`                               | list, get, create, update, delete           | [teams.md](./references/entities/teams.md)                                                             |
| TemplateFile                       | `templatefiles`                       | list, get, create, update, delete           | [templatefiles.md](./references/entities/templatefiles.md)                                             |
| TemplateVersion                    | `templateversions`                    | list, get, create, update, delete           | [templateversions.md](./references/entities/templateversions.md)                                       |
| Ticket                             | `tickets`                             | list, get, create, update, delete           | [tickets.md](./references/entities/tickets.md)                                                         |
| TimePass                           | `timepasses`                          | list, get, create, update, delete           | [timepasses.md](./references/entities/timepasses.md)                                                   |
| TimePassPrice                      | `timepassprices`                      | list, get, create, update, delete           | [timepassprices.md](./references/entities/timepassprices.md)                                           |
| TimePassTimeSlot                   | `timepasstimeslots`                   | list, get, create, update, delete           | [timepasstimeslots.md](./references/entities/timepasstimeslots.md)                                     |
| UiModule                           | `uimodules`                           | list, get, create, update, delete           | [uimodules.md](./references/entities/uimodules.md)                                                     |
| User                               | `users`                               | list, get, create, update, delete           | [users.md](./references/entities/users.md)                                                             |
| UserBookmark                       | `userbookmarks`                       | list, get, create, update, delete           | [userbookmarks.md](./references/entities/userbookmarks.md)                                             |
| UserMessage                        | `usermessages`                        | list, get                                   | [usermessages.md](./references/entities/usermessages.md)                                               |
| UserRole                           | `userroles`                           | list, get, create, update, delete           | [userroles.md](./references/entities/userroles.md)                                                     |
| ValidationRule                     | `validationrules`                     | list, get, create, update, delete           | [validationrules.md](./references/entities/validationrules.md)                                         |
| VideoFile                          | `videofiles`                          | list, get, create, update, delete           | [videofiles.md](./references/entities/videofiles.md)                                                   |
| VideoRoom                          | `videorooms`                          | list, get, create, update, delete           | [videorooms.md](./references/entities/videorooms.md)                                                   |
| Visitor                            | `visitors`                            | list, get, create, update, delete           | [visitors.md](./references/entities/visitors.md)                                                       |
| WebHook                            | `webhooks`                            | list, get, create, update, delete           | [webhooks.md](./references/entities/webhooks.md)                                                       |
| Workspace                          | `workspaces`                          | list, get, create, update, delete           | [workspaces.md](./references/entities/workspaces.md)                                                   |

<!-- END:GENERATED-INDEX -->

## Image Uploads

Some entities have image properties (logo, banner, picture, etc.). To set an image, you must provide **two** properties:

1. **`New{PropertyName}Url`** — a **publicly accessible URL** where the Nexudus back-end can download the image. Local file paths or authenticated URLs will not work.
2. **`{PropertyName}FileName`** — the file name (with extension) to store for the image. Use only non-special characters (letters, digits, hyphens, underscores) and include the file extension (e.g., `.png`, `.jpg`).

If the user does not supply a file name, derive one from the URL (use the last path segment, stripping query strings and special characters) or generate a reasonable default like `image.png`. Always ensure the name contains only safe characters and a valid image extension.

| Entity   | Image Property   | CLI URL Option          | API URL Property         | CLI FileName Option           | API FileName Property      |
| -------- | ---------------- | ----------------------- | ------------------------ | ----------------------------- | -------------------------- |
| Business | Logo             | `--logo-url`            | `NewLogoUrl`             | `--logo-file-name`            | `LogoFileName`             |
| Business | BannerImage      | `--banner-url`          | `NewBannerImageUrl`      | `--banner-file-name`          | `BannerImageFileName`      |
| Business | NexIoBannerImage | `--nexio-banner-url`    | `NewNexIoBannerImageUrl` | `--nexio-banner-file-name`    | `NexIoBannerImageFileName` |
| Business | PassportBanner   | `--passport-banner-url` | `NewPassportBannerUrl`   | `--passport-banner-file-name` | `PassportBannerFileName`   |
| Resource | Picture          | `--new-picture-url`     | `NewPictureUrl`          | `--picture-file-name`         | `PictureFileName`          |

Example — set a logo on a business:

```shell
nexudus businesses update <id> --logo-url "https://example.com/logo.png" --logo-file-name "logo.png" --agent
```

Example — set a picture on a resource:

```shell
nexudus resources update <id> --new-picture-url "https://example.com/room.jpg" --picture-file-name "room.jpg" --agent
```

Example — user provides only the URL (agent derives the file name):

```shell
# User says: set the logo to https://cdn.example.com/images/my-logo.png
# Agent extracts "my-logo.png" from the URL path
nexudus businesses update <id> --logo-url "https://cdn.example.com/images/my-logo.png" --logo-file-name "my-logo.png" --agent
```

Example — URL has no usable file name (agent generates one):

```shell
# User says: set the logo to https://cdn.example.com/generate?id=abc
# Agent cannot extract a file name, so it generates a safe default
nexudus businesses update <id> --logo-url "https://cdn.example.com/generate?id=abc" --logo-file-name "logo.png" --agent
```

## Nexudus API Pattern

The Nexudus API follows a consistent REST pattern. Each entity at `/api/{module}/{entities}` supports:

| Operation   | HTTP   | URL                                       |
| ----------- | ------ | ----------------------------------------- |
| Search      | GET    | `/api/{module}/{entities}?page=1&size=25` |
| Get one     | GET    | `/api/{module}/{entities}/{id}`           |
| Create      | POST   | `/api/{module}/{entities}`                |
| Update      | PUT    | `/api/{module}/{entities}`                |
| Delete      | DELETE | `/api/{module}/{entities}/{id}`           |
| Commands    | GET    | `/api/{module}/{entities}/commands`       |
| Run command | POST   | `/api/{module}/{entities}/runCommand`     |

## Passing Multiple Values (List Options)

Some options accept a list of IDs (e.g., `--tariffs`, `--teams`, `--linked-resources`, `--resource-types`). To pass multiple values, **repeat the flag** for each value:

```shell
nexudus resources update <id> --tariffs 101 --tariffs 202 --tariffs 303 --agent
```

Do **not** use comma-separated values or bracket syntax — each value needs its own flag.

### Choosing between `--{list}`, `--added-{list}`, and `--removed-{list}`

Every list property comes in three variants. Use the right one for your intent:

| Variant            | When to use                                                                            | Effect                                             |
| ------------------ | -------------------------------------------------------------------------------------- | -------------------------------------------------- |
| `--{list}`         | **Default choice.** You know the full desired list.                                    | Replaces the entire list with the supplied values. |
| `--added-{list}`   | You want to append one or more items to the existing list without altering the rest.   | Merges the supplied IDs into the existing list.    |
| `--removed-{list}` | You want to remove one or more items from the existing list without altering the rest. | Removes the supplied IDs from the existing list.   |

**Use `--{list}` in almost all cases.** The add/remove variants are only needed when you need surgical, incremental changes — for example, adding a single new tariff to a resource that already has several others you must not disturb.

Example — replace all tariffs on a resource:

```shell
nexudus resources update <id> --tariffs 101 --tariffs 202 --agent
```

Example — add one tariff without changing the existing ones:

```shell
nexudus resources update <id> --added-tariffs 303 --agent
```

Example — remove one tariff without changing the existing ones:

```shell
nexudus resources update <id> --removed-tariffs 101 --agent
```

## Tips

- Use `--page-size 100` to fetch larger pages when you need to scan many records.
- Use `--id <id>` to filter by a single ID, or repeat `--id <id1> --id <id2>` for multiple IDs.
- Use `--unique-id <guid>` to filter by UniqueId (GUID), repeatable for multiple.
- Combine filter options with pagination for efficient searching.
- The `run-command` accepts comma-separated IDs to batch operations: `nexudus products run-command archive 123,456,789 --agent`.
- Business entities cannot be created or deleted via the API — only listed, viewed, and updated.
- Always pass `--yes` with delete commands whegin running non-interactively.
