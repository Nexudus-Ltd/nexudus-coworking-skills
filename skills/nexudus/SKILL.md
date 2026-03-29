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

| Flag               | Description                           |
| ------------------ | ------------------------------------- |
| `--agent`          | JSON envelope with summary (use this) |
| `--json`           | Raw JSON envelope                     |
| `--md`             | Markdown output                       |
| `--base-url <url>` | Override API base URL                 |

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

1. `nexudus businesses list --agent` (or `--query "name"` if searching)
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
2. For pagination: add `--page N --size M`

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
| Entity | CLI command | Operations | Reference |
| ------ | ----------- | ---------- | --------- |
| AccessToken | `accesstokens` | list, get, create, update, delete | [accesstokens.md](./references/entities/accesstokens.md) |
| Booking | `bookings` | list, get, create, update, delete | [bookings.md](./references/entities/bookings.md) |
| BookingAvailabilityException | `bookingavailabilityexceptions` | list, get, create, update, delete | [bookingavailabilityexceptions.md](./references/entities/bookingavailabilityexceptions.md) |
| BookingNote | `bookingnotes` | list, get, create, update, delete | [bookingnotes.md](./references/entities/bookingnotes.md) |
| BookingProduct | `bookingproducts` | list, get, create, update, delete | [bookingproducts.md](./references/entities/bookingproducts.md) |
| BookingVisitor | `bookingvisitors` | list, get, create, update, delete | [bookingvisitors.md](./references/entities/bookingvisitors.md) |
| Business | `businesses` | list, get, update | [businesses.md](./references/entities/businesses.md) |
| CancelledBooking | `cancelledbookings` | list, get | [cancelledbookings.md](./references/entities/cancelledbookings.md) |
| Checkin | `checkins` | list, get, create, update, delete | [checkins.md](./references/entities/checkins.md) |
| Country | `countries` | list, get | [countries.md](./references/entities/countries.md) |
| Coworker | `coworkers` | list, get, create, update, commands | [coworkers.md](./references/entities/coworkers.md) |
| CoworkerDataFile | `cowokerdatafiles` | list, get, create, update, delete | [coworkerdatafiles.md](./references/entities/coworkerdatafiles.md) |
| CoworkerDelivery | `coworkerdeliveries` | list, get, create, update, delete | [coworkerdeliveries.md](./references/entities/coworkerdeliveries.md) |
| CoworkerGoogleCalendar | `cowokergooglecalendars` | list, get, create, update, delete | [coworkergooglecalendars.md](./references/entities/coworkergooglecalendars.md) |
| CoworkerIdentityCheck | `coworkeridentitychecks` | list, get, create, update, delete | [coworkeridentitychecks.md](./references/entities/coworkeridentitychecks.md) |
| CoworkerIdentityCheckDocument | `coworkeridentitycheckdocuments` | list, get, create, update, delete | [coworkeridentitycheckdocuments.md](./references/entities/coworkeridentitycheckdocuments.md) |
| CoworkerInventoryAsset | `coworkerinventoryassets` | list, get, create, update, delete | [coworkerinventoryassets.md](./references/entities/coworkerinventoryassets.md) |
| CoworkerMessage | `cowokermessages` | list, get, create, update, delete | [coworkermessages.md](./references/entities/coworkermessages.md) |
| CoworkerMsOfficeCalendar | `coworkermsoffecalendars` | list, get, create, update, delete | [coworkermsofficecalendars.md](./references/entities/coworkermsofficecalendars.md) |
| CoworkerNote | `cowokernotes` | list, get, create, update, delete | [coworkernotes.md](./references/entities/coworkernotes.md) |
| CoworkerNotification | `coworkernotifications` | list, get | [coworkernotifications.md](./references/entities/coworkernotifications.md) |
| CoworkerPricePlanHistory | `coworkerpriceplanhistories` | list, get | [coworkerpriceplanhistories.md](./references/entities/coworkerpriceplanhistories.md) |
| CoworkerSetting | `cowokersettings` | list, get, create, update, delete | [coworkersettings.md](./references/entities/coworkersettings.md) |
| Currency | `currencies` | list, get | [currencies.md](./references/entities/currencies.md) |
| ExtraService | `extraservices` | list, get, create, update, delete | [extraservices.md](./references/entities/extraservices.md) |
| FailedCheckin | `failedcheckins` | list, get | [failedcheckins.md](./references/entities/failedcheckins.md) |
| InventoryAsset | `inventoryassets` | list, get, create, update, delete | [inventoryassets.md](./references/entities/inventoryassets.md) |
| MsOfficeAdminCalendar | `msofficeadmincalendars` | list, get, create, update, delete | [msofficeadmincalendars.md](./references/entities/msofficeadmincalendars.md) |
| Product | `products` | list, get, create, update, delete, commands | [products.md](./references/entities/products.md) |
| ProductExtraService | `productextraservices` | list, get, create, update, delete | [productextraservices.md](./references/entities/productextraservices.md) |
| ProductTimePass | `producttimepasses` | list, get, create, update, delete | [producttimepasses.md](./references/entities/producttimepasses.md) |
| Resource | `resources` | list, get, create, update, delete | [resources.md](./references/entities/resources.md) |
| ResourceAccessRule | `resourceaccessrules` | list, get, create, update, delete | [resourceaccessrules.md](./references/entities/resourceaccessrules.md) |
| ResourceAccessRuleEligibleTimeSlot | `resourceaccessruleeligibletimeslots` | list | [resourceaccessruleeligibletimeslots.md](./references/entities/resourceaccessruleeligibletimeslots.md) |
| ResourceAccessRuleTimeSlot | `resourceaccessruletimeslots` | list | [resourceaccessruletimeslots.md](./references/entities/resourceaccessruletimeslots.md) |
| ResourceTimeSlot | `resourcetimeslots` | list, get, create, update, delete | [resourcetimeslots.md](./references/entities/resourcetimeslots.md) |
| ResourceType | `resourcetypes` | list, get, create, update, delete | [resourcetypes.md](./references/entities/resourcetypes.md) |
| Team | `teams` | list, get, create, update, delete | [teams.md](./references/entities/teams.md) |
| TimePass | `timepasses` | list, get, create, update, delete | [timepasses.md](./references/entities/timepasses.md) |
| Visitor | `visitors` | list, get, create, update, delete | [visitors.md](./references/entities/visitors.md) |
<!-- END:GENERATED-INDEX -->

## Image Uploads

Some entities have image properties (logo, banner, picture, etc.). To set an image, use the corresponding `New{PropertyName}Url` property, which accepts a **publicly accessible URL**. The Nexudus back-end downloads the image from that URL and stores it, so the URL must be reachable from the internet — local file paths or authenticated URLs will not work.

The naming convention is: for an image property called `{PropertyName}`, the upload property is `New{PropertyName}Url`.

| Entity   | Image Property   | CLI Option              | API Property             |
| -------- | ---------------- | ----------------------- | ------------------------ |
| Business | Logo             | `--logo-url`            | `NewLogoUrl`             |
| Business | BannerImage      | `--banner-url`          | `NewBannerImageUrl`      |
| Business | NexIoBannerImage | `--nexio-banner-url`    | `NewNexIoBannerImageUrl` |
| Business | PassportBanner   | `--passport-banner-url` | `NewPassportBannerUrl`   |
| Resource | Picture          | `--new-picture-url`     | `NewPictureUrl`          |

Example — set a logo on a business:

```shell
nexudus businesses update <id> --logo-url "https://example.com/logo.png" --agent
```

Example — set a picture on a resource:

```shell
nexudus resources update <id> --new-picture-url "https://example.com/room.jpg" --agent
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

- Use `--size 100` to fetch larger pages when you need to scan many records.
- Combine `--query` with pagination for efficient searching.
- The `run-command` accepts comma-separated IDs to batch operations: `nexudus products run-command archive 123,456,789 --agent`.
- Business entities cannot be created or deleted via the API — only listed, viewed, and updated.
- Always pass `--yes` with delete commands whegin running non-interactively.
