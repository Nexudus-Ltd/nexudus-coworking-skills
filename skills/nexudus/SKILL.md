---
description: Manage Nexudus coworking spaces via the `nexudus` CLI — businesses, products, authentication, and configuration.
triggers:
  - nexudus
  - coworking
  - business management
  - product management
  - spaces
invocable: true
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

| Command           | Description                        |
| ----------------- | ---------------------------------- |
| `nexudus login`   | Authenticate (interactive prompt)  |
| `nexudus logout`  | Clear stored credentials           |
| `nexudus whoami`  | Show current authenticated user    |

### Configuration

| Command                              | Description              |
| ------------------------------------ | ------------------------ |
| `nexudus config get <key>`           | Read a config value      |
| `nexudus config set <key> <value>`   | Set a config value       |

Config keys: `base-url`

### Businesses

Businesses support Search, Get, and Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus businesses list --agent` | List all businesses |
| `nexudus businesses list --query "London" --agent` | Search businesses by name |
| `nexudus businesses list --page 2 --size 10 --agent` | Paginated list |
| `nexudus businesses get <id> --agent` | Get single business |
| `nexudus businesses update <id> --name "New Name" --agent` | Update business fields |

#### Business update options

`--name`, `--short-intro`, `--about`, `--quote`, `--terms`, `--website`, `--web-contact`, `--privacy-url`, `--cookie-url`, `--address`, `--street-name`, `--street-number`, `--neighborhood`, `--city`, `--state`, `--postcode`, `--country-id`, `--longitude`, `--latitude`, `--phone`, `--fax`, `--email`, `--contact-phone`, `--contact-email`, `--currency-id`, `--timezone-id`, `--default-language`, `--venue-type`, `--tags`, `--floors`, `--floor-space`, `--floor-space-unit`, `--passport-published`, `--passport-name`, `--passport-tagline`, `--passport-description`

### Products

Products support full CRUD plus entity commands.

| Command | Description |
| --- | --- |
| `nexudus products list --agent` | List all products |
| `nexudus products list --query "Pass" --agent` | Search products by name |
| `nexudus products list --business <id> --agent` | Filter by business |
| `nexudus products list --page 2 --size 10 --agent` | Paginated list |
| `nexudus products get <id> --agent` | Get single product |
| `nexudus products create --name "Day Pass" --price 25.00 --business <id> --agent` | Create product |
| `nexudus products update <id> --name "New Name" --price 30.00 --agent` | Update product |
| `nexudus products delete <id> --yes --agent` | Delete product (no prompt) |
| `nexudus products commands --agent` | List available entity commands |
| `nexudus products run-command <key> <ids> --agent` | Run entity command |

#### Product create options

`--name` (required), `--business` (required), `--price` (required), `--description`, `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--track-stock`, `--financial-account-id`

#### Product update options

`--name`, `--price`, `--description`, `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--track-stock`, `--archived`, `--financial-account-id`

### Diagnostics

```shell
nexudus doctor --agent
```

### Global Flags

| Flag | Description |
| --- | --- |
| `--agent` | JSON envelope with summary (use this) |
| `--json` | Raw JSON envelope |
| `--md` | Markdown output |
| `--base-url <url>` | Override API base URL |

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

### "Create a product"

1. First find the business ID: `nexudus businesses list --agent`
2. `nexudus products create --name "Day Pass" --price 25.00 --business <businessId> --agent`
3. Check `ok` is `true`, read `data.Id` for the new product ID

### "Update a product price"

1. `nexudus products get <id> --agent` to verify the product exists
2. `nexudus products update <id> --price 30.00 --agent`
3. Verify the update by checking the returned `data`

### "Delete a product"

1. `nexudus products get <id> --agent` to confirm the product exists
2. `nexudus products delete <id> --yes --agent`
3. Check `ok` is `true`

### "List products for a specific business"

1. `nexudus products list --business <businessId> --agent`
2. For pagination: add `--page N --size M`

### "Run an entity command on products"

1. `nexudus products commands --agent` to discover available commands
2. `nexudus products run-command <commandKey> <id1,id2> --agent`
3. Add parameters with `-p Name=Value` if the command requires them

### "Check CLI health"

1. `nexudus doctor --agent`
2. Verify `data.CredentialsStored` is `true`
3. Verify `data.ApiStatus` is `"OK"`

## Error Handling

| Error | Meaning | Action |
| --- | --- | --- |
| `ok: false`, summary contains "Not logged in" | No stored credentials | Tell user to run `nexudus login` |
| `ok: false`, summary contains "Unauthorized" | Invalid credentials | Tell user to run `nexudus login` again |
| `ok: false`, summary contains "Forbidden" | Insufficient permissions | Inform user they lack API permissions |
| `ok: false`, summary contains "not found" | Entity doesn't exist | Check the ID and try again |
| `ok: false`, summary contains "Failed to create" | Create validation error | Check required fields (name, business, price) |
| Non-zero exit code | Command failed | Read stderr or the JSON envelope for details |

## Entity Models

### Business (key fields)

`Id`, `Name`, `Address`, `TownCity`, `State`, `PostalCode`, `CountryName`, `Phone`, `EmailContact`, `WebAddress`, `CurrencyCode`, `Tags`, `PassportPublished`, `VenueType`

### Product (key fields)

`Id`, `Name`, `BusinessId`, `BusinessName`, `Price`, `Description`, `Sku`, `Tags`, `Visible`, `Archived`, `CurrencyCode`, `DisplayOrder`, `OnlyForMembers`, `OnlyForContacts`, `TrackStock`, `CurrentStock`

## Nexudus API Pattern

The Nexudus API follows a consistent REST pattern. Each entity at `/api/{module}/{entities}` supports:

| Operation | HTTP | URL |
| --- | --- | --- |
| Search | GET | `/api/{module}/{entities}?page=1&size=25` |
| Get one | GET | `/api/{module}/{entities}/{id}` |
| Create | POST | `/api/{module}/{entities}` |
| Update | PUT | `/api/{module}/{entities}` |
| Delete | DELETE | `/api/{module}/{entities}/{id}` |
| Commands | GET | `/api/{module}/{entities}/commands` |
| Run command | POST | `/api/{module}/{entities}/runCommand` |

Current entity mappings:

| Entity | Module | Path |
| --- | --- | --- |
| Business | sys | businesses |
| Product | billing | products |

## Tips

- Use `--size 100` to fetch larger pages when you need to scan many records.
- Combine `--query` with pagination for efficient searching.
- The `run-command` accepts comma-separated IDs to batch operations: `nexudus products run-command archive 123,456,789 --agent`.
- Business entities cannot be created or deleted via the API — only listed, viewed, and updated.
- Always pass `--yes` with delete commands when running non-interactively.
