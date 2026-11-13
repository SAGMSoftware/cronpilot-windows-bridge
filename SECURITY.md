# CronPilot Sim Bridge – Security Information

**Applies to:** CronPilot Sim Bridge for Windows, version 0.3.4  
**Last updated:** November 13, 2026  
**Publisher:** SAGM Software  
**Security contact:** [support@sagm.net](mailto:support@sagm.net)

## Purpose and supported environment

CronPilot Sim Bridge transfers simulated aircraft telemetry from Microsoft Flight Simulator 2020/2024 on a Windows PC to CronPilot Android. It is intended **only for a trusted private local network (LAN)**. It is not an Internet-facing service, a certified aviation instrument, or an emergency navigation system.

**Do not expose CronPilot Sim Bridge to the public Internet.**

## Network connections

| Port | Protocol | Purpose |
| --- | --- | --- |
| 45913 | TCP | Android client connection, authentication and simulated aircraft telemetry |
| 45914 | UDP | Optional automatic discovery of the Bridge on the local network |

The TCP telemetry listener binds to a selected private IPv4 address on the Windows computer. UDP discovery listens on the computer's available IPv4 interfaces but answers only recognized discovery requests from private/local IPv4 clients. The Windows Firewall remains an important additional protection.

The installer offers **optional** inbound Windows Firewall rules restricted to the **Private** network profile and the **local subnet** for these ports. The installer does not turn a Public network into a Private one. Do not open these ports on the Public profile or forward them through a router.

## Authentication is not encryption

CronPilot Sim Bridge supports:

- A legacy client mode that uses a six-digit session PIN on connection.
- A trusted-device mode in which a new Android device pairs using a six-digit PIN, receives a device identifier and key, and subsequently authenticates with a challenge-response mechanism.
- Removal of individual trusted devices or all trusted devices from the Windows application's **TRUSTED DEVICES** section.

**Neither pairing nor telemetry is protected by TLS encryption.** Initial pairing information, the legacy PIN and simulated flight data can be observed or interfered with by an attacker who has access to an untrusted local network. Trusted-device authentication limits access but does not make an untrusted network safe.

## Recommended safe use

1. Connect the Windows PC and Android device to a **private LAN or Wi-Fi network you control**.
2. Do not use hotel, airport, guest, public or otherwise untrusted networks.
3. Never configure Internet port forwarding, publicly reachable VPN routing or public inbound firewall rules for TCP 45913 or UDP 45914.
4. Keep Windows, Microsoft Flight Simulator, CronPilot Android and the Bridge up to date. Start the Bridge only when needed.
5. Do not disclose the pairing PIN or trusted-device credentials. Pair new devices only when you recognize and authorize them.
6. Remove devices you no longer use from **TRUSTED DEVICES**. Also forget the pairing on the Android device when appropriate.
7. Protect the Windows user account and its local application data with appropriate access controls. Do not share trusted-device files.

## Local security-related information

The Bridge stores trusted-device records by default in:

`%LOCALAPPDATA%\SAGM Software\CronPilot Sim Bridge\trusted_devices.json`

This file contains device identifiers, device names, a cryptographic verification value and pairing timestamps. It does **not** contain the original device key in plaintext, but the verification value is authentication-sensitive. Protect the file and the Windows account that owns it.

The application's event log is displayed in the running window and can include connection IP addresses. The reviewed version does not implement a permanent event-log file. Stored pairing records may remain after uninstalling the Bridge; remove them through **TRUSTED DEVICES** or delete the application data manually after closing the application if you no longer need them.

See [PRIVACY.md](PRIVACY.md) for further details about local data processing.

## Reporting security issues

Please report suspected vulnerabilities privately to **[support@sagm.net](mailto:support@sagm.net)**. Include the Bridge version, affected feature and steps to reproduce the issue, if available. Do not publish working exploits, pairing secrets, passwords, personal flight data or sensitive logs in a public GitHub issue.

No guaranteed response or remediation timeframe is offered. This document describes the inspected 0.3.4 implementation; it does not constitute a security audit or a guarantee against vulnerabilities.
