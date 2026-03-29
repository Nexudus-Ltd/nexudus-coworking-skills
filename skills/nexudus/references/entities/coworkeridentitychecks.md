# CoworkerIdentityChecks

<!-- BEGIN:GENERATED entity=CoworkerIdentityChecks -->

CoworkerIdentityChecks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkeridentitychecks list --agent` | List all coworkeridentitychecks |
| `nexudus coworkeridentitychecks list --query "search" --agent` | Search coworkeridentitychecks by name |
| `nexudus coworkeridentitychecks list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkeridentitychecks get <id> --agent` | Get single coworkeridentitycheck |
| `nexudus coworkeridentitychecks create --business <value> --coworker-id <value> --name <value> --agent` | Create coworkeridentitycheck |
| `nexudus coworkeridentitychecks update <id> --name "New Name" --agent` | Update coworkeridentitycheck |
| `nexudus coworkeridentitychecks delete <id> --yes --agent` | Delete coworkeridentitycheck (no prompt) |

#### CoworkerIdentityCheck create options

`--business` (required), `--coworker-id` (required), `--name` (required), `--identity-check-provider`, `--identity-document-type`, `--identity-document-number`, `--identity-document-issued-by`, `--identity-document-expiration-date`, `--address-document-type`, `--verification-type`, `--description`, `--verification-status`

#### CoworkerIdentityCheck update options

`--coworker-id`, `--name`, `--identity-check-provider`, `--identity-document-type`, `--identity-document-number`, `--identity-document-issued-by`, `--identity-document-expiration-date`, `--address-document-type`, `--verification-type`, `--description`, `--verification-status`

### CoworkerIdentityCheck (key fields)

`Id`, `BusinessId`, `BusinessName`, `CoworkerId`, `CoworkerFullName`, `Name`, `VerificationType`, `VerificationStatus`

#### CoworkerIdentityCheck enum values

| Option | Valid values |
| ------ | ------------ |
| `--identity-check-provider` | `1` Manual, `2` StripeIdentity |
| `--identity-document-type` | `1` Passport, `2` DriversLicense, `3` IdCard, `4` UniformedServiceId, `5` CertificateOfNaturalization, `6` AccessCard, `7` MatriculaConsular, `8` ResidentCard, `9` UniversityId, `10` NEXUSCard, `99` Other |
| `--address-document-type` | `1` Passport, `2` DriversLicense, `3` IdCard, `4` LeaseRentalAgreement, `5` InsurancePolicy, `6` Mortgage, `7` VehicleRegistrationCard, `8` VoterCard, `99` Other |
| `--verification-type` | `1` IdDocument, `2` Address |
| `--verification-status` | `1` Pending, `2` Submitted, `3` Successful, `4` Failed, `5` Cancelled |

<!-- END:GENERATED entity=CoworkerIdentityChecks -->
