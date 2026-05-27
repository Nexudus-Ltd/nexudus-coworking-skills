# RadiusServers

<!-- BEGIN:GENERATED entity=RadiusServers -->

A **RadiusServer** configures a RADIUS authentication server used for Wi-Fi access control. Each server defines the vendor type, connection settings, and shared secret for authenticating customer devices on the network.

RadiusServers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus radiusservers list --agent` | List all radiusservers |
| `nexudus radiusservers list --id <id> --agent` | Filter by single ID |
| `nexudus radiusservers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus radiusservers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus radiusservers list --business-id <value> --name <value> --agent` | Filter radiusservers by properties |
| `nexudus radiusservers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus radiusservers get <id> --agent` | Get single radiusserver |
| `nexudus radiusservers create --business-id <value> --name <value> --vendor <value> --agent` | Create radiusserver |
| `nexudus radiusservers update <id> --name "New Name" --agent` | Update radiusserver |
| `nexudus radiusservers delete <id> --yes --agent` | Delete radiusserver (no prompt) |

#### RadiusServer list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this radius server |
| `--vendor` | enum | The vendor value for this radius server |
| `--active` | bool | Whether this radius server is currently active |
| `--description` | string | Free-text description of this radius server |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RadiusServer create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this radius server |
| `--vendor` | enum, required | The vendor value for this radius server |
| `--active` | bool | Whether this radius server is currently active |
| `--description` | string | Free-text description of this radius server |

#### RadiusServer update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this radius server |
| `--vendor` | enum | The vendor value for this radius server |
| `--active` | bool | Whether this radius server is currently active |
| `--description` | string | Free-text description of this radius server |

#### RadiusServer enum values

| Option | Valid values |
| ------ | ------------ |
| `--vendor` | `0` Aerohive_Networks, `1` Alcatel_Lucent, `2` Aruba_Instant, `3` Aruba_Mobility_Controller, `4` Avaya, `5` Bluesocket, `6` Casa_Systems, `7` ChilliSpot, `8` CoovaChilli, `9` Cisco_Systems, `10` Dell, `11` EnGenius, `12` ExtremeWireless, `13` FortiGate, `14` ICC, `15` LigoWave, `16` Meraki_Sign_On, `17` Meraki_ClickThrough, `18` Meru_Networks, `19` MikroTik, `20` Motorola, `21` Mojo_Networks, `22` Open_Mesh_Cloudtrax, `23` pfSense, `24` Peplink, `25` Ruckus_Wireless, `26` Ruckus_Virtual_SZ, `27` SonicWall, `28` Ubiquiti_Networks, `29` TP_Link_EAP, `30` Trapeze_Wireless, `31` Trendnet, `32` Xirrus, `33` Virtual_Controller, `34` Other |

<!-- END:GENERATED entity=RadiusServers -->
