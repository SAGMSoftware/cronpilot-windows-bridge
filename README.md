# CronPilot Sim Bridge

**Windows companion application for CronPilot Android**

CronPilot Sim Bridge connects Microsoft Flight Simulator 2020/2024 to the CronPilot Android app over a trusted private local network.

## Features

- Microsoft Flight Simulator 2020 and 2024 support via SimConnect
- Real-time simulator aircraft position and flight data
- Automatic device discovery on the local network
- PIN-based pairing and trusted-device management
- DEMO mode for testing without a running flight simulator
- English user manual

## Current Version

CronPilot Sim Bridge 0.3.4 for Windows x64.

## Requirements

- Windows 64-bit
- Microsoft Flight Simulator 2020 or 2024 for live simulator connectivity
- CronPilot Android on a device connected to the same trusted private network

## Network and Security

The application uses TCP port 45913 for communication and UDP port 45914 for device discovery.

The local network connection does not use TLS encryption.

Use CronPilot Sim Bridge only on a trusted private network. Do not expose its network ports to the Internet or use router port forwarding.

## Android Application

https://github.com/SAGMSoftware/cronpilot-android

## Important Notice

CronPilot and CronPilot Sim Bridge are not certified aviation instruments and must not be used for safety-critical flight operations.

## License, Warranty and Third-Party Modifications

Copyright (C) 2026 SAGM Software.

CronPilot Sim Bridge is distributed under the GNU Affero General Public License, version 3 or later (AGPL-3.0-or-later), subject to applicable third-party license terms.

The software is provided "AS IS", without warranty of any kind, to the extent permitted by applicable law.

Third parties may modify and redistribute the software in accordance with the applicable license terms. Modified versions must clearly identify the changes made and must not be misrepresented as official SAGM Software releases.

SAGM Software does not review, approve, maintain or support independently modified versions unless expressly stated otherwise.

The disclaimer of warranty and limitation of liability in Sections 15 and 16 of the GNU AGPL apply, subject to mandatory applicable law.

Official releases are published at:
https://github.com/SAGMSoftware/cronpilot-windows-bridge

## Support

support@sagm.net

Developed by SAGM Software.
