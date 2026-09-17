# RadiusServers

<!-- BEGIN:GENERATED entity=RadiusServers -->

A RADIUS server is a hosted Wi-Fi authentication network that a location rents through the built-in provider integration, so customers sign in to the Wi-Fi with their Nexudus account and their network sessions become check-ins. Creating a record is not a settings change: the backend calls the provider to build a real network, a captive portal for the selected Vendor, and an authentication endpoint, then stores the returned network, portal, splash-page, IP, port and shared-secret values as read-only fields the operator copies into their wireless controller. It fails unless the location has a RADIUS licence key configured. Deleting a record deletes the network and captive portal at the provider and cannot be undone. Only the first active server of a location is used, an active server is billed monthly, and a server that is not active is skipped by the 15-minute synchronisation. The record alone does not grant anyone Wi-Fi access; that depends on each customer allowing network check-in and holding a pass that allows it.

RadiusServers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus radiusservers list --agent` | List all radiusservers |
| `nexudus radiusservers list --id <id> --agent` | Filter by single ID |
| `nexudus radiusservers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus radiusservers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus radiusservers list --business-id <value> --name <value> --agent` | Filter radiusservers by properties |
| `nexudus radiusservers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus radiusservers list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus radiusservers get <id> --agent` | Get single radiusserver |
| `nexudus radiusservers create --business-id <value> --name <value> --vendor <value> --agent` | Create radiusserver |
| `nexudus radiusservers update <id> --name "New Name" --agent` | Update radiusserver |
| `nexudus radiusservers delete <id> --yes --agent` | Delete radiusserver (no prompt) |

#### RadiusServer list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this RADIUS server. The location's RADIUS licence key setting decides whether the server can be provisioned at all, and its country selects the hosting region: US, AU, or Europe for everywhere else. |
| `--name` | string | Operator-facing label for this server in the location's list. The provider-side network and captive portal are named automatically from the location name and the creation date, so this value is not sent to the provider. |
| `--vendor` | enum | Wireless hardware or controller the captive portal is built for, such as Meraki_Sign_On, Ubiquiti_Networks, MikroTik or Ruckus_Wireless; use Other when the vendor is not listed. It is applied only while the captive portal is provisioned during creation, so changing it afterwards does not rebuild the portal and the admin form disables it once the record exists. |
| `--active` | bool | Whether this server is included in the RADIUS synchronisation that runs every 15 minutes to import provider accounting data as customer check-ins. Only the first active server of a location is used, and an active server also adds a RADIUS line to the location's monthly invoice. Set false to stop syncing and billing without tearing down the provisioned network. |
| `--description` | string | Optional free-text note about this server. It is not shown on the admin form and is not sent to the provider. |
| `--network-id` | string | Read-only identifier of the hosted RADIUS network created by the provider when this record was saved. Deleting the record deletes that network at the provider; it cannot be set or changed. |
| `--captive-portal-id` | string | Read-only identifier of the captive portal created alongside the network at creation time, using the selected Vendor. Deleting the record deletes the portal at the provider; it cannot be set or changed. |
| `--splash-page-id` | string | Read-only public identifier the provider generates for the captive portal's splash page. It appears in the customer-facing Wi-Fi login URL and cannot be set or changed. |
| `--radius-ip1` | string | Read-only primary RADIUS server IP address supplied by the provider at creation. The operator enters it in the wireless controller's RADIUS settings; it cannot be set or changed here. |
| `--radius-ip2` | string | Read-only backup RADIUS server IP address supplied by the provider at creation, used when the primary address is unreachable. It cannot be set or changed here. |
| `--account-port` | string | Read-only RADIUS accounting port supplied by the provider at creation. The wireless controller sends accounting packets here, which become customer check-ins on the next synchronisation. |
| `--auth-port` | string | Read-only RADIUS authentication port supplied by the provider at creation. The wireless controller sends authentication requests here. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RadiusServer sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### RadiusServer create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this RADIUS server. The location's RADIUS licence key setting decides whether the server can be provisioned at all, and its country selects the hosting region: US, AU, or Europe for everywhere else. |
| `--name` | string, required | Operator-facing label for this server in the location's list. The provider-side network and captive portal are named automatically from the location name and the creation date, so this value is not sent to the provider. |
| `--vendor` | enum, required | Wireless hardware or controller the captive portal is built for, such as Meraki_Sign_On, Ubiquiti_Networks, MikroTik or Ruckus_Wireless; use Other when the vendor is not listed. It is applied only while the captive portal is provisioned during creation, so changing it afterwards does not rebuild the portal and the admin form disables it once the record exists. |
| `--active` | bool | Whether this server is included in the RADIUS synchronisation that runs every 15 minutes to import provider accounting data as customer check-ins. Only the first active server of a location is used, and an active server also adds a RADIUS line to the location's monthly invoice. Set false to stop syncing and billing without tearing down the provisioned network. |
| `--description` | string | Optional free-text note about this server. It is not shown on the admin form and is not sent to the provider. |

#### RadiusServer update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this RADIUS server. The location's RADIUS licence key setting decides whether the server can be provisioned at all, and its country selects the hosting region: US, AU, or Europe for everywhere else. |
| `--name` | string | Operator-facing label for this server in the location's list. The provider-side network and captive portal are named automatically from the location name and the creation date, so this value is not sent to the provider. |
| `--vendor` | enum | Wireless hardware or controller the captive portal is built for, such as Meraki_Sign_On, Ubiquiti_Networks, MikroTik or Ruckus_Wireless; use Other when the vendor is not listed. It is applied only while the captive portal is provisioned during creation, so changing it afterwards does not rebuild the portal and the admin form disables it once the record exists. |
| `--active` | bool | Whether this server is included in the RADIUS synchronisation that runs every 15 minutes to import provider accounting data as customer check-ins. Only the first active server of a location is used, and an active server also adds a RADIUS line to the location's monthly invoice. Set false to stop syncing and billing without tearing down the provisioned network. |
| `--description` | string | Optional free-text note about this server. It is not shown on the admin form and is not sent to the provider. |

#### RadiusServer enum values

| Option | Valid values |
| ------ | ------------ |
| `--vendor` | `0` Aerohive_Networks, `1` Alcatel_Lucent, `2` Aruba_Instant, `3` Aruba_Mobility_Controller, `4` Avaya, `5` Bluesocket, `6` Casa_Systems, `7` ChilliSpot, `8` CoovaChilli, `9` Cisco_Systems, `10` Dell, `11` EnGenius, `12` ExtremeWireless, `13` FortiGate, `14` ICC, `15` LigoWave, `16` Meraki_Sign_On, `17` Meraki_ClickThrough, `18` Meru_Networks, `19` MikroTik, `20` Motorola, `21` Mojo_Networks, `22` Open_Mesh_Cloudtrax, `23` pfSense, `24` Peplink, `25` Ruckus_Wireless, `26` Ruckus_Virtual_SZ, `27` SonicWall, `28` Ubiquiti_Networks, `29` TP_Link_EAP, `30` Trapeze_Wireless, `31` Trendnet, `32` Xirrus, `33` Virtual_Controller, `34` Other |

<!-- END:GENERATED entity=RadiusServers -->
