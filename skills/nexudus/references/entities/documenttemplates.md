# DocumentTemplates

<!-- BEGIN:GENERATED entity=DocumentTemplates -->

A DocumentTemplate is a location-scoped reusable layout for generating customer, booking, contract, and proposal documents. Designer templates (Editor = Designer) are authored as a design (DesignJson) with fields, conditions, repeats and signature blocks for a DataContext and compiled to Liquid HTML; Classic templates use Liquid source or an uploaded mail-merge document.

DocumentTemplates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus documenttemplates list --agent` | List all documenttemplates |
| `nexudus documenttemplates list --id <id> --agent` | Filter by single ID |
| `nexudus documenttemplates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus documenttemplates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus documenttemplates list --business-id <value> --business-name <value> --agent` | Filter documenttemplates by properties |
| `nexudus documenttemplates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus documenttemplates list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus documenttemplates get <id> --agent` | Get single documenttemplate |
| `nexudus documenttemplates create --business-id <value> --name <value> --template-output-format <value> --editor <value> --data-context <value> --agent` | Create documenttemplate |
| `nexudus documenttemplates update <id> --name "New Name" --agent` | Update documenttemplate |
| `nexudus documenttemplates delete <id> --yes --agent` | Delete documenttemplate (no prompt) |

#### DocumentTemplate list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the required location that owns this document template; only operators linked to that location can see or use it. |
| `--business-name` | string | Display value for Business.Name. |
| `--name` | string | Required name used to identify this document template to operators; also used as the file name of documents generated from it. |
| `--document` | string | Liquid HTML source rendered for Classic templates when TemplateOutputFormat is Html or Word. The variables available come from the data context built for the record the document is generated for (Location, Customer, Contract, Proposal and Booking roots), falling back to a small legacy set when no context can be built. For Designer templates this is generated from DesignJson on every save, so any value sent here is overwritten; change DesignJson instead. |
| `--binary-document-file-name` | string | Current file name of the binary document (read-only; upload via the corresponding URL field) |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum | Selects the generated format: Html, Word (Liquid source converted to a Word document) or Binary (the uploaded BinaryDocument used for mail merge, so it only makes sense together with an uploaded file). Saving a Designer template forces this back to Html. |
| `--editor` | enum | Which editor owns the template: Classic (uploaded Word document merged with TX Text Control, or raw Liquid HTML) or Designer (a design authored in the Document Designer and compiled to Liquid HTML). Designer templates require DataContext and DesignJson, are validated and compiled on every save, and have TemplateOutputFormat forced to Html and any uploaded BinaryDocument cleared. |
| `--data-context` | enum | What the template is about: Customer, Contract, Proposal or Booking. Decides which data roots (Location, Customer, Contract, Proposal, Booking) the design can use. Designer templates must set one of the four; saving a Designer template while this is Unspecified is rejected. Classic templates leave it Unspecified. |
| `--design-json` | string | Document Designer design (JSON, schema version 1) for Designer templates, holding the blocks, fields, conditions, repeats and signature blocks. Validate it with the document_template_designer tool before saving; the platform validates it again and compiles it into Document (Liquid HTML) on save, and a failed validation aborts the save. Ignored for Classic templates. |
| `--design-version` | int | Read-only schema version of the last compiled design, set by the platform when a Designer template is saved (currently 1); 0 when the template has never been compiled from a design. Change DesignJson to recompile. |
| `--from-design-version` | range | |
| `--to-design-version` | range | |
| `--compiled-on` | DateTime | Read-only UTC timestamp of the last time Document was compiled from DesignJson, set by the platform when a Designer template is saved; empty for Classic templates. |
| `--from-compiled-on` | range | |
| `--to-compiled-on` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### DocumentTemplate sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### DocumentTemplate create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the required location that owns this document template; only operators linked to that location can see or use it. |
| `--name` | string, required | Required name used to identify this document template to operators; also used as the file name of documents generated from it. |
| `--document` | string | Liquid HTML source rendered for Classic templates when TemplateOutputFormat is Html or Word. The variables available come from the data context built for the record the document is generated for (Location, Customer, Contract, Proposal and Booking roots), falling back to a small legacy set when no context can be built. For Designer templates this is generated from DesignJson on every save, so any value sent here is overwritten; change DesignJson instead. |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum, required | Selects the generated format: Html, Word (Liquid source converted to a Word document) or Binary (the uploaded BinaryDocument used for mail merge, so it only makes sense together with an uploaded file). Saving a Designer template forces this back to Html. |
| `--editor` | enum, required | Which editor owns the template: Classic (uploaded Word document merged with TX Text Control, or raw Liquid HTML) or Designer (a design authored in the Document Designer and compiled to Liquid HTML). Designer templates require DataContext and DesignJson, are validated and compiled on every save, and have TemplateOutputFormat forced to Html and any uploaded BinaryDocument cleared. |
| `--data-context` | enum, required | What the template is about: Customer, Contract, Proposal or Booking. Decides which data roots (Location, Customer, Contract, Proposal, Booking) the design can use. Designer templates must set one of the four; saving a Designer template while this is Unspecified is rejected. Classic templates leave it Unspecified. |
| `--design-json` | string | Document Designer design (JSON, schema version 1) for Designer templates, holding the blocks, fields, conditions, repeats and signature blocks. Validate it with the document_template_designer tool before saving; the platform validates it again and compiles it into Document (Liquid HTML) on save, and a failed validation aborts the save. Ignored for Classic templates. |

#### DocumentTemplate update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the required location that owns this document template; only operators linked to that location can see or use it. |
| `--name` | string | Required name used to identify this document template to operators; also used as the file name of documents generated from it. |
| `--document` | string | Liquid HTML source rendered for Classic templates when TemplateOutputFormat is Html or Word. The variables available come from the data context built for the record the document is generated for (Location, Customer, Contract, Proposal and Booking roots), falling back to a small legacy set when no context can be built. For Designer templates this is generated from DesignJson on every save, so any value sent here is overwritten; change DesignJson instead. |
| `--new-binary-document-url` | string | URL of a new file to upload as the binary document |
| `--clear-binary-document-file` | bool | Set to true to remove the current binary document file |
| `--template-output-format` | enum | Selects the generated format: Html, Word (Liquid source converted to a Word document) or Binary (the uploaded BinaryDocument used for mail merge, so it only makes sense together with an uploaded file). Saving a Designer template forces this back to Html. |
| `--editor` | enum | Which editor owns the template: Classic (uploaded Word document merged with TX Text Control, or raw Liquid HTML) or Designer (a design authored in the Document Designer and compiled to Liquid HTML). Designer templates require DataContext and DesignJson, are validated and compiled on every save, and have TemplateOutputFormat forced to Html and any uploaded BinaryDocument cleared. |
| `--data-context` | enum | What the template is about: Customer, Contract, Proposal or Booking. Decides which data roots (Location, Customer, Contract, Proposal, Booking) the design can use. Designer templates must set one of the four; saving a Designer template while this is Unspecified is rejected. Classic templates leave it Unspecified. |
| `--design-json` | string | Document Designer design (JSON, schema version 1) for Designer templates, holding the blocks, fields, conditions, repeats and signature blocks. Validate it with the document_template_designer tool before saving; the platform validates it again and compiles it into Document (Liquid HTML) on save, and a failed validation aborts the save. Ignored for Classic templates. |

#### DocumentTemplate enum values

| Option | Valid values |
| ------ | ------------ |
| `--template-output-format` | `1` Html, `2` Word, `3` Binary |
| `--editor` | `1` Classic, `2` Designer |
| `--data-context` | `1` Unspecified, `2` Customer, `3` Contract, `4` Proposal, `5` Booking |

<!-- END:GENERATED entity=DocumentTemplates -->
