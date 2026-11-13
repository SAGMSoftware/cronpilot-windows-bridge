# CronPilot Sim Bridge – Privacy Information

**Last updated:** November 13, 2026  
**Application:** CronPilot Sim Bridge for Windows, version 0.3.4  
**Developer and privacy contact:** SAGM Software – [support@sagm.net](mailto:support@sagm.net)  
**Project:** [CronPilot Sim Bridge on GitHub](https://github.com/SAGMSoftware/cronpilot-windows-bridge)

## 1. Scope

This notice describes the Windows **CronPilot Sim Bridge** application. The separate **CronPilot Android** app has its own privacy policy. The Bridge is designed for local communication between Microsoft Flight Simulator 2020/2024 and the Android app over a user-selected private network.

The inspected Bridge source does not include user accounts, advertising, dedicated analytics, in-app purchases or an application-operated cloud telemetry service. SAGM Software does not automatically receive simulated aircraft telemetry or Android pairing records through the Bridge.

## 2. Information processed locally

When the Bridge is running, it may process the following information:

- **Simulated aircraft data:** simulated latitude and longitude, groundspeed, true track, altitude when available, and a timestamp. These values are obtained from Microsoft Flight Simulator via SimConnect and are transmitted to connected, authorized Android clients over the local network. They are simulator values, not measurements of the phone's physical GPS position.
- **Device pairing records:** an Android device identifier, a device display name, an authentication verifier derived from the device key, and the dates/times of initial pairing and last successful authentication. The Windows Bridge does not store the original device key in plaintext.
- **Local connection details:** IP addresses and connection events used to establish, manage and display local sessions. These details can appear in the Bridge's on-screen event log while it is running. The inspected version does not save that event log to a separate permanent file.
- **Temporary authentication information:** a six-digit session PIN and other protocol values used during pairing or connections.

An Android device name may contain information identifying a person. Local IP addresses and connection metadata may also be personal data in some circumstances.

## 3. Network communication and security

The Bridge uses **TCP port 45913** for Android connections and **UDP port 45914** for optional local discovery. Simulated aircraft telemetry, pairing information and authentication traffic are exchanged on the local network.

**These connections are not TLS-encrypted.** Anyone with sufficient access to an untrusted network may be able to observe or interfere with traffic, especially during initial pairing. Use the Bridge only on a trusted private LAN. Do not use public Wi-Fi or forward its ports to the Internet.

The inspected application does not automatically upload its pairing database or simulator telemetry to SAGM Software or GitHub. Selecting the GitHub project link in the application opens a website in your browser; that external service and your browser may process technical connection information under their respective privacy practices. See [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

Microsoft Flight Simulator, Windows and other software or network services used on your PC may process information independently under their own terms.

## 4. Local storage, retention and deletion

By default, trusted-device records are stored in this per-user Windows location:

`%LOCALAPPDATA%\SAGM Software\CronPilot Sim Bridge\trusted_devices.json`

The records remain until you remove a device, clear the trusted-device list, or delete the file. They may **remain after the Bridge is uninstalled**. To remove them, use the **TRUSTED DEVICES** controls, or close the Bridge and delete its local application-data folder if you no longer require its contents. Any copies made through Windows backups or by other software must be managed separately.

The Bridge holds recent simulator telemetry in memory for live display and transmission. The inspected version does not save simulated flight tracks to a persistent flight-history database. Information shown in the window's event log is not configured as a permanent log file.

For complete pairing revocation, also remove or forget the corresponding trusted connection on the Android device as appropriate.

## 5. Support correspondence

If you email SAGM Software, the email address and information you choose to provide are processed to respond to the inquiry and address any associated legal obligations. Please avoid sending pairing keys, passwords, identifiable flight information or other sensitive content unless strictly necessary. Email providers process correspondence under their own terms.

Support correspondence should be retained only as long as needed to handle the request and any applicable legal obligations; actual retention practices must comply with the relevant law. You may contact **support@sagm.net** with a privacy request.

## 6. Privacy rights and legal basis

Where the EU General Data Protection Regulation (GDPR) applies and SAGM Software acts as a controller, support correspondence may be processed on the basis of legitimate interests in responding to inquiries (Article 6(1)(f) GDPR), and where required to comply with legal obligations (Article 6(1)(c) GDPR). The Bridge's local data handling is primarily controlled by the person operating the Windows PC; it is not automatically collected by SAGM Software.

Depending on the circumstances and applicable law, you may request access, correction, deletion or restriction of processing of personal data held by SAGM Software, or object to processing based on legitimate interests. You may also have a right to data portability where applicable. Contact **[support@sagm.net](mailto:support@sagm.net)** to make a request.

You can submit a complaint to a competent data-protection supervisory authority. The [European Data Protection Board](https://www.edpb.europa.eu/about-edpb/about-edpb/members_en) provides a list of European supervisory authorities.

SAGM Software cannot remotely inspect or delete your locally stored trusted-device records through the Bridge. The application does not perform advertising profiling or automated decisions with legal or similarly significant effects.

## 7. Safety and policy changes

CronPilot Sim Bridge is a flight simulator utility, not a certified aviation or emergency navigation instrument. Do not use simulated telemetry for safety-critical real-world flight decisions.

This notice may be revised if the software or its data handling changes. The date at the top identifies the latest published revision. Questions may be directed to **[support@sagm.net](mailto:support@sagm.net)**.
