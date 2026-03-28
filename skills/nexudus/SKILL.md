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

### Businesses

Businesses support Search, Get, and Update (no Create or Delete via API).

| Command                                                    | Description               |
| ---------------------------------------------------------- | ------------------------- |
| `nexudus businesses list --agent`                          | List all businesses       |
| `nexudus businesses list --query "London" --agent`         | Search businesses by name |
| `nexudus businesses list --page 2 --size 10 --agent`       | Paginated list            |
| `nexudus businesses get <id> --agent`                      | Get single business       |
| `nexudus businesses update <id> --name "New Name" --agent` | Update business fields    |

#### Business update options

`--name`, `--short-intro`, `--about`, `--quote`, `--terms`, `--website`, `--web-contact`, `--privacy-url`, `--cookie-url`, `--address`, `--street-name`, `--street-number`, `--neighborhood`, `--city`, `--state`, `--postcode`, `--country-id`, `--longitude`, `--latitude`, `--phone`, `--fax`, `--email`, `--contact-phone`, `--contact-email`, `--currency-id`, `--timezone-id`, `--default-language`, `--venue-type`, `--tags`, `--floors`, `--floor-space`, `--floor-space-unit`, `--passport-published`, `--passport-name`, `--passport-tagline`, `--passport-description`, `--logo-url`, `--banner-url`, `--nexio-banner-url`, `--passport-banner-url`

### Products

Products support Search, Get, Create, Update, Delete.
Products also support entity commands.

| Command                                                                                                   | Description                    |
| --------------------------------------------------------------------------------------------------------- | ------------------------------ |
| `nexudus products list --agent`                                                                           | List all products              |
| `nexudus products list --query "search" --agent`                                                          | Search products by name        |
| `nexudus products list --page 2 --size 10 --agent`                                                        | Paginated list                 |
| `nexudus products get <id> --agent`                                                                       | Get single product             |
| `nexudus products create --business <value> --name <value> --price <value> --description <value> --agent` | Create product                 |
| `nexudus products update <id> --name "New Name" --agent`                                                  | Update product                 |
| `nexudus products delete <id> --yes --agent`                                                              | Delete product (no prompt)     |
| `nexudus products commands --agent`                                                                       | List available entity commands |
| `nexudus products run-command <key> <ids> --agent`                                                        | Run entity command             |

#### Product create options

`--business` (required), `--name` (required), `--price` (required), `--description` (required), `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--track-stock`, `--archived`, `--financial-account-id`, `--system-product-type`, `--invoice-display`, `--sync-square`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--available-as`, `--starred`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--image-url`, `--image-file`, `--clear-image`

#### Product update options

`--name`, `--price`, `--description`, `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--track-stock`, `--archived`, `--financial-account-id`, `--system-product-type`, `--invoice-display`, `--sync-square`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--available-as`, `--starred`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--image-url`, `--image-file`, `--clear-image`

### Product (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `Price`, `Description`, `Sku`, `Tags`, `Visible`, `CurrencyCode`, `DisplayOrder`, `OnlyForMembers`, `OnlyForContacts`, `TrackStock`, `CurrentStock`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs

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

### "Create a <entity>"

1. First find the business ID: `nexudus businesses list --agent`
2. `nexudus <entity> create --name "Day Pass" --price 25.00 --business <businessId> --agent`
3. Check `ok` is `true`, read `data.Id` for the new entity ID

### "Update a <entity> <property>"

1. `nexudus <entity> get <id> --agent` to verify the entity exists
2. `nexudus <entity> update <id> --<property> <value> --agent`
3. Verify the update by checking the returned `data`

### "Delete a <entity>"

1. `nexudus <entity> get <id> --agent` to confirm the entity exists
2. `nexudus <entity> delete <id> --yes --agent`
3. Check `ok` is `true`

### "List <entity> for a specific business"

1. `nexudus <entity> list --business <businessId> --agent`
2. For pagination: add `--page N --size M`

### "Run an entity command on <entity>"

1. `nexudus <entity> commands --agent` to discover available commands
2. `nexudus <entity> run-command <commandKey> <id1,id2> --agent`
3. Add parameters with `-p Name=Value` if the command requires them

### "Check CLI health"

1. `nexudus doctor --agent`
2. Verify `data.CredentialsStored` is `true`
3. Verify `data.ApiStatus` is `"OK"`

### "Add passes to a product"

A ProductTimePass links a `TimePass` to a `Product` so customers purchasing the product receive check-in time. The amount and type of time depends on the linked `TimePass`:

- Linking a **Day Pass** (no `MinutesIncluded`) gives the customer a number of calendar days — each day allows unlimited check-ins. Set `--passes-included` to the number of calendar days.
- Linking a **Time Pass** (has `MinutesIncluded`) gives the customer a number of hours to use across any dates. Set `--passes-included` to the number of pass instances; total minutes = `PassesIncluded × MinutesIncluded`.

**Example: 5 calendar days**

1. Find the product: `nexudus products list --query "Day Pass Bundle" --agent` → note the `Id`
2. Find the day pass: `nexudus timepasses list --query "Day Pass" --agent` → confirm `MinutesIncluded` is null → note the `Id`
3. Create the link:
   ```shell
   nexudus producttimepasses create \
     --product-id <productId> \
     --time-pass-id <timePassId> \
     --passes-included 5 \
     --agent
   ```

**Example: 100 hours across different dates**

1. Find the product and note its `Id`
2. Find a time pass with `MinutesIncluded = 60` (1 hour per pass): `nexudus timepasses list --query "1 Hour Pass" --agent` → note the `Id`
3. Create the link with `--passes-included 100` (100 × 60 min = 6000 min = 100 hours):
   ```shell
   nexudus producttimepasses create \
     --product-id <productId> \
     --time-pass-id <timePassId> \
     --passes-included 100 \
     --agent
   ```
4. Check `ok` is `true`, read `data.Id` for the new link ID

### "List passes included in a product"

1. `nexudus producttimepasses list --agent`
2. Filter results where `ProductId` matches the target product

### "Update passes included in a product"

1. `nexudus producttimepasses list --agent` → find the link by `ProductId` and `TimePassId`
2. `nexudus producttimepasses update <id> --passes-included 20 --agent`
3. Verify the update by checking the returned `data`

### "Remove a pass from a product"

1. `nexudus producttimepasses list --agent` → find the link by `ProductId` and `TimePassId`
2. `nexudus producttimepasses delete <id> --yes --agent`
3. Check `ok` is `true`

### "Add booking time for a resource type to a product"

ProductExtraServices link an ExtraService (resource pricing rule) to a Product so that customers purchasing the product automatically receive an allowance of booking time for that resource type.

1. Find the product: `nexudus products list --query "Bundle" --agent` → note the `Id`
2. Find the extra service: `nexudus extraservices list --query "Meeting Room" --agent` → note the `Id` and `ChargePeriod`
3. Create the link — set `--uses-included` in the unit matching the extra service's charge period (e.g. 120 minutes if ChargePeriod=1):
   ```shell
   nexudus productextraservices create \
     --product-id <productId> \
     --extra-service-id <extraServiceId> \
     --uses-included 120 \
     --agent
   ```
4. Check `ok` is `true`, read `data.Id` for the new link ID

### "List booking time included in a product"

1. `nexudus productextraservices list --agent`
2. Filter results where `ProductId` matches the target product
3. The `ExtraServiceChargePeriod` field indicates the unit of `UsesIncluded` for each row

### "Update booking time included in a product"

1. `nexudus productextraservices list --agent` → find the link by `ProductId` and `ExtraServiceId`
2. `nexudus productextraservices update <id> --uses-included 5 --agent`
3. Verify the update by checking the returned `data`

### "Remove booking time from a product"

1. `nexudus productextraservices list --agent` → find the link by `ProductId` and `ExtraServiceId`
2. `nexudus productextraservices delete <id> --yes --agent`
3. Check `ok` is `true`

### "Add printing credit to a product"

A printing credit extra service has `IsPrintingCredit = true`, `ChargePeriod = 5` (Uses), and `Price = 1`. Linking it to a product via a `ProductExtraService` grants customers a number of print jobs when they purchase the product.

1. Check whether a printing credit extra service already exists: `nexudus extraservices list --agent` → look for an entry where `IsPrintingCredit` is `true`
2. If none exists, create one:
   ```shell
   nexudus extraservices create \
     --business <businessId> \
     --name "Printing Credit" \
     --printing-credit true \
     --charge-period 5 \
     --price 1 \
     --agent
   ```
   Note the `Id` from `data.Id`.
3. Find the product: `nexudus products list --query "Bundle" --agent` → note the `Id`
4. Create the link — set `--uses-included` to the number of printing credits to include:
   ```shell
   nexudus productextraservices create \
     --product-id <productId> \
     --extra-service-id <extraServiceId> \
     --uses-included 50 \
     --agent
   ```
5. Check `ok` is `true`, read `data.Id` for the new link ID

### "Update printing credit included in a product"

1. `nexudus productextraservices list --agent` → find the link where `ExtraServiceChargePeriod` is `5` and the extra service has `IsPrintingCredit = true`
2. `nexudus productextraservices update <id> --uses-included <newAmount> --agent`
3. Verify the update by checking the returned `data`

### "Remove printing credit from a product"

1. `nexudus productextraservices list --agent` → find the link by `ProductId` and the printing credit `ExtraServiceId`
2. `nexudus productextraservices delete <id> --yes --agent`
3. Check `ok` is `true`

## Error Handling

| Error                                            | Meaning                  | Action                                        |
| ------------------------------------------------ | ------------------------ | --------------------------------------------- |
| `ok: false`, summary contains "Not logged in"    | No stored credentials    | Tell user to run `nexudus login`              |
| `ok: false`, summary contains "Unauthorized"     | Invalid credentials      | Tell user to run `nexudus login` again        |
| `ok: false`, summary contains "Forbidden"        | Insufficient permissions | Inform user they lack API permissions         |
| `ok: false`, summary contains "not found"        | Entity doesn't exist     | Check the ID and try again                    |
| `ok: false`, summary contains "Failed to create" | Create validation error  | Check required fields (name, business, price) |
| Non-zero exit code                               | Command failed           | Read stderr or the JSON envelope for details  |

## Entity Models

### Business (key fields)

`Id`, `Name`, `Address`, `TownCity`, `State`, `PostalCode`, `CountryName`, `Phone`, `EmailContact`, `WebAddress`, `CurrencyCode`, `Tags`, `PassportPublished`, `VenueType`

### Products

<!-- BEGIN:GENERATED entity=Products -->

Products support Search, Get, Create, Update, Delete.
Products also support entity commands.

| Command                                                                                                   | Description                    |
| --------------------------------------------------------------------------------------------------------- | ------------------------------ |
| `nexudus products list --agent`                                                                           | List all products              |
| `nexudus products list --query "search" --agent`                                                          | Search products by name        |
| `nexudus products list --page 2 --size 10 --agent`                                                        | Paginated list                 |
| `nexudus products get <id> --agent`                                                                       | Get single product             |
| `nexudus products create --business <value> --name <value> --price <value> --description <value> --agent` | Create product                 |
| `nexudus products update <id> --name "New Name" --agent`                                                  | Update product                 |
| `nexudus products delete <id> --yes --agent`                                                              | Delete product (no prompt)     |
| `nexudus products commands --agent`                                                                       | List available entity commands |
| `nexudus products run-command <key> <ids> --agent`                                                        | Run entity command             |

#### Product create options

`--business` (required), `--name` (required), `--price` (required), `--description` (required), `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--track-stock`, `--archived`, `--financial-account-id`, `--system-product-type`, `--invoice-display`, `--sync-square`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--available-as`, `--starred`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--image-url`, `--image-file`, `--clear-image`

#### Product update options

`--name`, `--price`, `--description`, `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--track-stock`, `--archived`, `--financial-account-id`, `--system-product-type`, `--invoice-display`, `--sync-square`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--available-as`, `--starred`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--image-url`, `--image-file`, `--clear-image`

### Product (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `Price`, `Description`, `Sku`, `Tags`, `Visible`, `CurrencyCode`, `DisplayOrder`, `OnlyForMembers`, `OnlyForContacts`, `TrackStock`, `CurrentStock`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Product enum values

| Option                  | Valid values                                                                                                 |
| ----------------------- | ------------------------------------------------------------------------------------------------------------ |
| `--system-product-type` | `0` None, `1` DayPass, `2` CreditBundle, `3` Stationery, `4` BookingFeature, `5` BookingProducts, `99` Other |
| `--available-as`        | `1` RecurrentOrOneOff, `2` OnlyRecurrent, `3` OnlyOneOff                                                     |

<!-- END:GENERATED entity=Products -->

### TimePasses

Passes allow customers to check in to a coworking space. There are two kinds:

- **Day Pass** — valid for a single calendar day. Created with `--minutes-included` omitted (null). The customer can check in any number of times during that day.
- **Time Pass** — valid across multiple days up to a fixed amount of time. Created with `--minutes-included <minutes>` set. The customer can check in until the included minutes are exhausted.

<!-- BEGIN:GENERATED entity=TimePasses -->

TimePasses support Search, Get, Create, Update, Delete.

| Command                                                               | Description                 |
| --------------------------------------------------------------------- | --------------------------- |
| `nexudus timepasses list --agent`                                     | List all timepasses         |
| `nexudus timepasses list --query "search" --agent`                    | Search timepasses by name   |
| `nexudus timepasses list --page 2 --size 10 --agent`                  | Paginated list              |
| `nexudus timepasses get <id> --agent`                                 | Get single timepass         |
| `nexudus timepasses create --business <value> --name <value> --agent` | Create timepass             |
| `nexudus timepasses update <id> --name "New Name" --agent`            | Update timepass             |
| `nexudus timepasses delete <id> --yes --agent`                        | Delete timepass (no prompt) |

#### TimePass create options

`--business` (required), `--name` (required), `--invoice-display`, `--price`, `--minutes-included`, `--counts-towards-plan`, `--payg-members`, `--payg-contacts`, `--use-priority`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--kisi-group-id`, `--door-guard-group-id`, `--allow-network-checkin`, `--only-for-contacts`, `--only-for-members`, `--archived`

#### TimePass update options

`--name`, `--invoice-display`, `--price`, `--minutes-included`, `--counts-towards-plan`, `--payg-members`, `--payg-contacts`, `--use-priority`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--kisi-group-id`, `--door-guard-group-id`, `--allow-network-checkin`, `--only-for-contacts`, `--only-for-members`, `--archived`

### TimePass (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `Price`, `MinutesIncluded`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`

<!-- END:GENERATED entity=TimePasses -->

### ProductTimePasses

A **ProductTimePass** links a `TimePass` to a `Product` so that customers purchasing the product automatically receive an amount of check-in time. The nature of that time depends on the type of the linked `TimePass`:

- **Day Pass** (TimePass with `MinutesIncluded` = null) — `PassesIncluded` is the number of calendar days. The customer can check in any number of times during each calendar day they hold.
- **Time Pass** (TimePass with `MinutesIncluded` set) — `PassesIncluded` is the number of pass instances (each worth `MinutesIncluded` minutes). Multiply `PassesIncluded` by `MinutesIncluded` to get total hours. For example, `PassesIncluded = 10` with a 60-minute time pass gives the customer 10 hours of check-in time to use across different dates.

<!-- BEGIN:GENERATED entity=ProductTimePasses -->

ProductTimePasses support Search, Get, Create, Update, Delete.

| Command                                                                                | Description                        |
| -------------------------------------------------------------------------------------- | ---------------------------------- |
| `nexudus producttimepasses list --agent`                                               | List all producttimepasses         |
| `nexudus producttimepasses list --query "search" --agent`                              | Search producttimepasses by name   |
| `nexudus producttimepasses list --page 2 --size 10 --agent`                            | Paginated list                     |
| `nexudus producttimepasses get <id> --agent`                                           | Get single producttimepass         |
| `nexudus producttimepasses create --product-id <value> --time-pass-id <value> --agent` | Create producttimepass             |
| `nexudus producttimepasses update <id> --name "New Name" --agent`                      | Update producttimepass             |
| `nexudus producttimepasses delete <id> --yes --agent`                                  | Delete producttimepass (no prompt) |

#### ProductTimePass create options

`--product-id` (required), `--time-pass-id` (required), `--passes-included`, `--expiration-type`, `--expires-in`

#### ProductTimePass update options

`--passes-included`, `--expiration-type`, `--expires-in`

### ProductTimePass (key fields)

`Id`, `ProductId`, `ProductName`, `TimePassId`, `TimePassName`, `PassesIncluded`

#### ProductTimePass enum values

| Option              | Valid values                                                              |
| ------------------- | ------------------------------------------------------------------------- |
| `--expiration-type` | `1` PricePlan, `2` Day, `3` Week, `4` Month, `5` Year, `6` LastDayOfMonth |

<!-- END:GENERATED entity=ProductTimePasses -->

### Resources

<!-- BEGIN:GENERATED entity=Resources -->

Resources support Search, Get, Create, Update, Delete.

| Command                                                                                         | Description                 |
| ----------------------------------------------------------------------------------------------- | --------------------------- |
| `nexudus resources list --agent`                                                                | List all resources          |
| `nexudus resources list --query "search" --agent`                                               | Search resources by name    |
| `nexudus resources list --page 2 --size 10 --agent`                                             | Paginated list              |
| `nexudus resources get <id> --agent`                                                            | Get single resource         |
| `nexudus resources create --business <value> --name <value> --resource-type-id <value> --agent` | Create resource             |
| `nexudus resources update <id> --name "New Name" --agent`                                       | Update resource             |
| `nexudus resources delete <id> --yes --agent`                                                   | Delete resource (no prompt) |

#### Resource create options

`--business` (required), `--name` (required), `--system-resource-type`, `--resource-type-id` (required), `--description`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order`, `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-user-id`, `--last-cleaned-at`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--new-picture-url`, `--picture-file-name`, `--clear-picture-file`

#### Resource update options

`--name`, `--system-resource-type`, `--resource-type-id`, `--description`, `--email-confirmation-content`, `--visible`, `--requires-confirmation`, `--display-order`, `--group-name`, `--projector`, `--internet`, `--conference-phone`, `--standard-phone`, `--white-board`, `--large-display`, `--catering`, `--tea-and-coffee`, `--drinks`, `--security-lock`, `--cctv`, `--voice-recorder`, `--air-conditioning`, `--heating`, `--natural-light`, `--standing-desk`, `--quiet-zone`, `--wireless-charger`, `--privacy-screen`, `--soundproof`, `--video-conferencing`, `--dual-display-screen`, `--display-screen`, `--wireless-presentation`, `--pa-system`, `--desktop-monitor`, `--flip-chart`, `--secure-storage`, `--allow-multiple-bookings`, `--allocation`, `--limit-visitors-to-allocation`, `--book-in-advance-limit`, `--late-booking-limit`, `--late-cancellation-limit`, `--interval-limit`, `--no-return-policy`, `--no-return-policy-all-resources`, `--no-return-policy-all-users`, `--max-booking-length`, `--min-booking-length`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--teams` (list, repeat flag), `--added-teams` (list, repeat flag), `--removed-teams` (list, repeat flag), `--shifts`, `--linked-resources` (list, repeat flag), `--added-linked-resources` (list, repeat flag), `--removed-linked-resources` (list, repeat flag), `--longitude`, `--latitude`, `--hide-in-calendar`, `--archived`, `--use-shared-zoom-account`, `--zoom-user-id`, `--last-cleaned-at`, `--linked-resource-ids`, `--only-for-contacts`, `--only-for-members`, `--only-for-invoicing-business`, `--booking-availability-exceptions` (list, repeat flag), `--added-booking-availability-exceptions` (list, repeat flag), `--removed-booking-availability-exceptions` (list, repeat flag), `--cancellation-fee-product-id`, `--charge-cancellation-fee`, `--cancellation-fee-type`, `--cancellation-fee-amount`, `--cancellation-fee-percentage`, `--repeat-booking-quantity-limit`, `--repeat-booking-period-limit-in-months`, `--new-picture-url`, `--picture-file-name`, `--clear-picture-file`

### Resource (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `ResourceTypeId`, `ResourceTypeName`, `Visible`, `GroupName`, `Allocation`, `Archived`, `OnlyForContacts`, `OnlyForMembers`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Teams`, `AddedTeams`, `RemovedTeams`, `LinkedResources`, `AddedLinkedResources`, `RemovedLinkedResources`, `BookingAvailabilityExceptions`, `AddedBookingAvailabilityExceptions`, `RemovedBookingAvailabilityExceptions`

#### Resource enum values

| Option                    | Valid values                                                                                                                                                                                 |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `--system-resource-type`  | `0` None, `1` MeetingRoom, `2` HotDesk, `3` PrivateOffice, `4` EventSpace, `5` Lab, `6` Kitchen, `7` TreatmentRoom, `9` StorageUnit, `10` Machine, `11` DayPass, `12` PhoneBooth, `99` Other |
| `--cancellation-fee-type` | `0` None, `1` Absolute, `2` Percentage                                                                                                                                                       |

<!-- END:GENERATED entity=Resources -->

> **Resource → ResourceType → ExtraService (pricing):** Every resource belongs to exactly one `ResourceType` (via `ResourceTypeId`). A resource type is a category of bookable space (e.g., "Meeting Room", "Hot Desk"). Pricing rules for a resource type are defined as `ExtraService` records — each extra service can apply to one or more resource types and represents a specific price for a given charge period and set of restrictions. You cannot create a resource without first knowing the ID of an existing resource type.

### ResourceTypes

A **ResourceType** is a category of bookable space (e.g., "Meeting Room", "Phone Booth", "Hot Desk"). Every `Resource` must be assigned to exactly one resource type. Pricing for a resource type is not stored on the type itself — it is defined by `ExtraService` records that reference the type. Multiple extra services can apply to the same resource type, covering different charge periods or customer restrictions.

<!-- BEGIN:GENERATED entity=ResourceTypes -->

ResourceTypes support Search, Get, Create, Update, Delete.

| Command                                                       | Description                     |
| ------------------------------------------------------------- | ------------------------------- |
| `nexudus resourcetypes list --agent`                          | List all resourcetypes          |
| `nexudus resourcetypes list --query "search" --agent`         | Search resourcetypes by name    |
| `nexudus resourcetypes list --page 2 --size 10 --agent`       | Paginated list                  |
| `nexudus resourcetypes get <id> --agent`                      | Get single resourcetype         |
| `nexudus resourcetypes create --business <value> --agent`     | Create resourcetype             |
| `nexudus resourcetypes update <id> --name "New Name" --agent` | Update resourcetype             |
| `nexudus resourcetypes delete <id> --yes --agent`             | Delete resourcetype (no prompt) |

#### ResourceType create options

`--business` (required), `--name`

#### ResourceType update options

`--name`

### ResourceType (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`

<!-- END:GENERATED entity=ResourceTypes -->

### ExtraServices

An **ExtraService** serves two distinct purposes:

1. **Resource-type pricing rule** — defines how one or more resource types are billed. A single resource type can have multiple extra services — for example, one per charge period (hourly, half-day, full-day) or one per customer segment.
2. **Printing credit** — when `IsPrintingCredit` is `true`, the extra service represents a printing allowance rather than booking time. In this case `ChargePeriod` must always be `5` (Uses) and `Price` should be set to `1`.

Restrictions available on each extra service include:

- **Charge period** — hourly, daily, etc. (`--charge-period`). For printing credit, always use `5` (Uses).
- **Customer type** — members only (`--only-for-members`) or contacts only (`--only-for-contacts`)
- **Time window** — bookings must fall within specific hours (`--from-time`, `--to-time`)
- **Booking length** — minimum/maximum duration (`--min-length`, `--max-length`)
- **Fixed-cost slot** — charge a flat fee for bookings up to a fixed length (`--fixed-cost-length`, `--fixed-cost-price`)
- **Dynamic pricing** — price factors for low/average/high demand and last-minute bookings
- **Date range** — apply only between specific dates (`--apply-from`, `--apply-to`)

To set up pricing for a resource type, create one `ExtraService` per pricing rule and associate it with the desired resource type(s) using or the resource types assignment. The `ResourceTypeNames` field on an extra service shows which resource types it currently applies to.

To create a **printing credit** extra service, set `--printing-credit true`, `--charge-period 5`, and `--price 1`. Resource type assignment is not required for printing credit extra services.

### Setting up hourly pricing

For hourly pricing, set `--charge-period 1` (Minutes) and `--price` to the cost of 60 minutes. The system interprets a charge period of 1 minute as hourly billing when the price represents a full hour.

Example — create a $50/hour meeting room pricing rule:

<!-- BEGIN:GENERATED entity=ExtraServices -->

ExtraServices support Search, Get, Create, Update, Delete.

| Command                                                                  | Description                     |
| ------------------------------------------------------------------------ | ------------------------------- |
| `nexudus extraservices list --agent`                                     | List all extraservices          |
| `nexudus extraservices list --query "search" --agent`                    | Search extraservices by name    |
| `nexudus extraservices list --page 2 --size 10 --agent`                  | Paginated list                  |
| `nexudus extraservices get <id> --agent`                                 | Get single extraservice         |
| `nexudus extraservices create --business <value> --name <value> --agent` | Create extraservice             |
| `nexudus extraservices update <id> --name "New Name" --agent`            | Update extraservice             |
| `nexudus extraservices delete <id> --yes --agent`                        | Delete extraservice (no prompt) |

#### ExtraService create options

`--business` (required), `--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--name` (required), `--description`, `--invoice-display`, `--visible`, `--display-order`, `--price`, `--credit-price`, `--charge-period`, `--maximum-price`, `--default-price`, `--per-night-pricing`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--from-time`, `--to-time`, `--min-length`, `--max-length`, `--only-within-available-times`, `--fixed-cost-length`, `--fixed-cost-price`, `--only-for-contacts`, `--only-for-members`, `--booking-credit`, `--printing-credit`, `--apply-to-visitors`, `--price-factor-low-demand`, `--price-factor-average-demand`, `--price-factor-high-demand`, `--price-factor-last-minute`, `--last-minute-period`, `--last-minute-adjustment-type`, `--apply-from`, `--apply-to`

#### ExtraService update options

`--resource-types` (list, repeat flag), `--added-resource-types` (list, repeat flag), `--removed-resource-types` (list, repeat flag), `--name`, `--description`, `--invoice-display`, `--visible`, `--display-order`, `--price`, `--credit-price`, `--charge-period`, `--maximum-price`, `--default-price`, `--per-night-pricing`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--from-time`, `--to-time`, `--min-length`, `--max-length`, `--only-within-available-times`, `--fixed-cost-length`, `--fixed-cost-price`, `--only-for-contacts`, `--only-for-members`, `--booking-credit`, `--printing-credit`, `--apply-to-visitors`, `--price-factor-low-demand`, `--price-factor-average-demand`, `--price-factor-high-demand`, `--price-factor-last-minute`, `--last-minute-period`, `--last-minute-adjustment-type`, `--apply-from`, `--apply-to`

### ExtraService (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `Visible`, `Price`, `ChargePeriod`, `IsDefaultPrice`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `ResourceTypeNames`

**List properties (only returned by `get`, not by `list`):** `ResourceTypes`, `AddedResourceTypes`, `RemovedResourceTypes`

#### ExtraService enum values

| Option                          | Valid values                                                               |
| ------------------------------- | -------------------------------------------------------------------------- |
| `--charge-period`               | `1` Minutes, `2` Days, `3` Weeks, `4` Months, `5` Uses, `6` FourWeekMonths |
| `--last-minute-adjustment-type` | `1` Disabled, `2` Fixed, `3` Gradual                                       |

<!-- END:GENERATED entity=ExtraServices -->

### ProductExtraServices

A **ProductExtraService** links an `ExtraService` to a `Product`. The meaning of `UsesIncluded` depends on the type of the linked extra service:

- **Booking time** (ExtraService with `IsPrintingCredit = false`) — customers receive an allowance of booking time for the resource type(s) associated with that extra service. For example, a product called "Hot Desk Bundle" might include 2 hours of meeting room usage — achieved by linking a "Meeting Room Hourly" extra service with `--uses-included 120`.
- **Printing credit** (ExtraService with `IsPrintingCredit = true`) — customers receive a number of print jobs/pages. `UsesIncluded` is the number of printing credits included. The linked extra service must have `ChargePeriod = 5` (Uses) and `Price = 1`.

Always check `IsPrintingCredit` on the linked extra service before interpreting `UsesIncluded`.

For booking-time extra services, the unit of `UsesIncluded` is determined by the **ChargePeriod** of the linked `ExtraService`:

| ExtraService ChargePeriod | UsesIncluded unit |
| ------------------------- | ----------------- |
| 1 (Minutes)               | Minutes           |
| 2 (Days)                  | Days              |
| 3 (Weeks)                 | Weeks             |
| 4 (Months)                | Months            |
| 5 (Uses)                  | Individual uses   |
| 6 (FourWeekMonths)        | 4-week periods    |

So `--uses-included 60` on a minutes extra service means 60 minutes of booking time included. On a daily extra service it means 60 full days.

<!-- BEGIN:GENERATED entity=ProductExtraServices -->

ProductExtraServices support Search, Get, Create, Update, Delete.

| Command                                                                                                               | Description                            |
| --------------------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| `nexudus productextraservices list --agent`                                                                           | List all productextraservices          |
| `nexudus productextraservices list --query "search" --agent`                                                          | Search productextraservices by name    |
| `nexudus productextraservices list --page 2 --size 10 --agent`                                                        | Paginated list                         |
| `nexudus productextraservices get <id> --agent`                                                                       | Get single productextraservice         |
| `nexudus productextraservices create --product-id <value> --extra-service-id <value> --uses-included <value> --agent` | Create productextraservice             |
| `nexudus productextraservices update <id> --name "New Name" --agent`                                                  | Update productextraservice             |
| `nexudus productextraservices delete <id> --yes --agent`                                                              | Delete productextraservice (no prompt) |

#### ProductExtraService create options

`--product-id` (required), `--extra-service-id` (required), `--uses-included` (required), `--expiration-type`, `--expires-in`

#### ProductExtraService update options

`--uses-included`, `--expiration-type`, `--expires-in`

### ProductExtraService (key fields)

`Id`, `ProductId`, `ProductName`, `ExtraServiceId`, `ExtraServiceName`, `ExtraServiceChargePeriod`, `UsesIncluded`

<!-- END:GENERATED entity=ProductExtraServices -->

### Currencies

<!-- BEGIN:GENERATED entity=Currencies -->

Currencies support Search, Get (no Create or Delete via API).

| Command                                              | Description               |
| ---------------------------------------------------- | ------------------------- |
| `nexudus currencies list --agent`                    | List all currencies       |
| `nexudus currencies list --query "search" --agent`   | Search currencies by name |
| `nexudus currencies list --page 2 --size 10 --agent` | Paginated list            |
| `nexudus currencies get <id> --agent`                | Get single currency       |

### Currency (key fields)

`Id`, `Name`, `Code`, `Format`

<!-- END:GENERATED entity=Currencies -->

### Countries

<!-- BEGIN:GENERATED entity=Countries -->

Countries support Search, Get (no Create or Delete via API).

| Command                                             | Description              |
| --------------------------------------------------- | ------------------------ |
| `nexudus countries list --agent`                    | List all countries       |
| `nexudus countries list --query "search" --agent`   | Search countries by name |
| `nexudus countries list --page 2 --size 10 --agent` | Paginated list           |
| `nexudus countries get <id> --agent`                | Get single country       |

### Country (key fields)

`Id`, `Name`, `TwoDigitsCode`, `Culture`

<!-- END:GENERATED entity=Countries -->

### Businesses

<!-- BEGIN:GENERATED entity=Businesses -->

Businesses support Search, Get, Update (no Create or Delete via API).

| Command                                                    | Description               |
| ---------------------------------------------------------- | ------------------------- |
| `nexudus businesses list --agent`                          | List all businesses       |
| `nexudus businesses list --query "search" --agent`         | Search businesses by name |
| `nexudus businesses list --page 2 --size 10 --agent`       | Paginated list            |
| `nexudus businesses get <id> --agent`                      | Get single business       |
| `nexudus businesses update <id> --name "New Name" --agent` | Update business           |

#### Business update options

`--name`, `--address`, `--city`, `--state`, `--postcode`, `--country-id`, `--phone`, `--email`, `--website`, `--currency-id`, `--tags`, `--passport-published`, `--venue-type`, `--short-intro`, `--about`, `--quote`, `--terms`, `--web-contact`, `--privacy-url`, `--cookie-url`, `--street-name`, `--street-number`, `--neighborhood`, `--longitude`, `--latitude`, `--fax`, `--contact-phone`, `--contact-email`, `--timezone-id`, `--default-language`, `--floors`, `--floor-space`, `--floor-space-unit`, `--passport-name`, `--passport-tagline`, `--passport-description`

### Business (key fields)

`Id`, `Name`, `Address`, `TownCity`, `State`, `PostalCode`, `CountryName`, `Phone`, `EmailContact`, `WebAddress`, `CurrencyCode`, `Tags`, `PassportPublished`, `VenueType`

<!-- END:GENERATED entity=Businesses -->

<!-- END:GENERATED-SECTIONS -->

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

Current entity mappings:

| Entity              | Module  | Path                 |
| ------------------- | ------- | -------------------- |
| Business            | sys     | businesses           |
| Product             | billing | products             |
| TimePass            | billing | timepasses           |
| ProductTimePass     | billing | producttimepasses    |
| ProductExtraService | billing | productextraservices |
| Resource            | spaces  | resources            |
| ResourceType        | spaces  | resourcetypes        |
| ExtraService        | spaces  | extraservices        |
| Currency            | sys     | currencies           |
| Country             | sys     | countries            |

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
