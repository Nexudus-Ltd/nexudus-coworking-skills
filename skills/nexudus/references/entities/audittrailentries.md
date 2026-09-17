# AuditTrailEntries

<!-- BEGIN:GENERATED entity=AuditTrailEntries -->

AuditTrailEntry is a read-only location activity log for audited record creations, updates, and deletions, including the field values recorded for updates.

AuditTrailEntries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus audittrailentries list --agent` | List all audittrailentries |
| `nexudus audittrailentries list --id <id> --agent` | Filter by single ID |
| `nexudus audittrailentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus audittrailentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus audittrailentries list --business-id <value> --entity-short-name <value> --agent` | Filter audittrailentries by properties |
| `nexudus audittrailentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus audittrailentries list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus audittrailentries get <id> --agent` | Get single audittrailentry |

#### AuditTrailEntry list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location where the audited record belongs. |
| `--entity-short-name` | string | Internal type name of the audited record, such as Coworker, Booking, or Charge. |
| `--description` | string | System-generated, human-readable summary of the audited action and the account that performed it. |
| `--property-name` | string | Display name of the entity field changed by an update, or the audited entity name for a creation or deletion. |
| `--audit-type` | enum | Audited action: Create (1), Update (2), or Delete (3). |
| `--old-value` | string | Display-formatted value of the changed field before an update; blank for creation records. |
| `--new-value` | string | Display-formatted value of the changed field after an update; blank for creation records. |
| `--action-by` | string | Username recorded for the action, with the IP address in parentheses when available. |
| `--entity-id` | int | Integer ID of the audited record; combine it with EntityShortName to identify the record type. |
| `--from-entity-id` | range | |
| `--to-entity-id` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AuditTrailEntry sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AuditTrailEntry enum values

| Option | Valid values |
| ------ | ------------ |
| `--audit-type` | `1` Create, `2` Update, `3` Delete |

<!-- END:GENERATED entity=AuditTrailEntries -->
