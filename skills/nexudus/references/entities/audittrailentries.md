# AuditTrailEntries

<!-- BEGIN:GENERATED entity=AuditTrailEntries -->

AuditTrailEntry is the read-only audit trail for a location: one record per audited creation, deletion, or changed field, holding the before and after values of an update and the account that made the change. The time of the action is the record's created-on timestamp, and older records are removed periodically by a scheduled maintenance job.

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
| `--business-id` | long | ID of the location that owns the audited record, taken from the record itself rather than from the account that made the change. |
| `--entity-short-name` | string | Internal class name of the audited record type, such as Coworker, Booking, Charge or BusinessSetting; never localized, so filter on the internal name. |
| `--description` | string | System-generated summary of the action in the location's language; the English form reads UPDATED, CREATED or DELETED followed by a label identifying the audited record, and it is truncated to 390 characters. The account that made the change is in ActionBy, not here. |
| `--property-name` | string | For an update, the localized form label of the changed field, falling back to the internal property name when no label exists; for a creation or deletion, the localized name of the audited record type. Localized per location, so prefer EntityShortName for reliable filtering. |
| `--audit-type` | enum | Audited action: Create (1) when the record was inserted, Update (2) when one field changed, or Delete (3) when the record was removed. An update that changes several fields produces one record per changed field. |
| `--old-value` | string | Value of the changed field before the update; empty for creations and deletions. Related records are recorded as their numeric ID, files as a hexadecimal identifier, and custom-field or localization data as JSON. |
| `--new-value` | string | Value of the changed field after the update, formatted as OldValue is; empty for creations and deletions, and recorded as **** when the field name contains "password". |
| `--action-by` | string | Account that performed the action, normally the signed-in username with the originating IP address in parentheses, or the identity supplied by the audited record for background and integration work. |
| `--entity-id` | int | ID of the audited record itself, stored as a 32-bit integer; combine it with EntityShortName to identify exactly which record changed. |
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
