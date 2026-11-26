# WireGuard Manager v1.0.21-1133

**Smarter routing, enhanced Streaming controls and more flexible VPN management.**

WireGuard Manager brings native WireGuard VPN management to the Synology RT2600ac. This release expands selective routing, adds flexible background DNS controls and improves day-to-day profile management, monitoring and Package Center upgrades.

**Platform:** Synology RT2600ac · SRM 1.3.2-9366 Update 3 · Primary IPv4 LAN (`lbr0`)

## What's new since v1.0.10

- **Intelligent DNS and domain routing:** Five Resolve modes — Learning Only, Lite, Normal, High and Extra High — plus a configurable daily Power Saving window. Numeric hostname ranges, persistent bounded hostname learning, reduced repeat queries for negative DNS answers and priority handling of exact names make DNS management more flexible.
- **Streaming groups:** Configure selected LAN devices to open a 15-minute VPN route window when a matching plaintext DNS reply is observed. Ordinary learned-domain policies remain available to other LAN devices.
- **Enhanced routing rules:** Enter up to 16 comma-separated LAN IPv4 addresses or CIDRs in a Source IP field. Improved duplicate detection covers saved and unsaved rules, with clear unsaved-change indicators.
- **Flexible VPN profile management:** Import and activate a new profile in a single Save & Apply, delete individual profiles and view connectivity checks while Profile Settings is open. Results are cached for ten minutes, with on-demand refresh for active profiles. Checks run only while Manager is enabled.
- **Live monitoring and diagnostics:** View CPU/RAM while Manager is active, separate Background Resolve and General Resolve IP counts, clearer Apply status and a Save receipt linked to its background job.
- **Managed routing protection:** Disabling or deleting a profile returns directly affected rule Actions to WAN. Underlay changes also return affected rules to WAN. Affected Streaming groups turn Off. Apply withdraws managed references to the old routing table before switching the tunnel, and stops the transition if references remain.
- **Enhanced upgrade handling:** Package Center upgrade preflight waits a bounded interval for accepted Apply operations and preserves configuration and private keys on successful upgrades.

## Download

Install the SPK release asset below, rather than GitHub's automatically generated source archives.

**Installer:** `WireGuardManager-1.0.21-1133-RT2600ac-aedc6ad518a7.spk`

**SHA-256:** `aedc6ad518a71660e92b6f9883c2e7ab19499782669638b177a2f912ff5e127b`

The SPK includes the ARMv7 WireGuard components, Manager service and SRM desktop app. No separate WireGuard compilation is required.

## Upgrading

Upgrade directly from v1.0.10 (`1.0.10-1010`) to v1.0.21-1133 using SRM Package Center. No intermediate update is required.

1. Verify the SPK checksum, keep the previous SPK and back up your configuration and private keys externally. Retain a separate way to access your router.
2. Disable Manager and confirm it shows **Disabled**.
3. Select the new SPK in **SRM Package Center → Manual Install**. Keep the existing package and configuration directory in place.
4. Reopen the app and confirm saved profiles, routing rules, SRM access and network connectivity before resuming normal operation.

**Routing note:** Profile changes can return affected traffic to WAN. During a Streaming route window, other public traffic from the selected device can also use the VPN.

See the [README](https://github.com/ICHTBAA/WireGuard-Client-for-Synology-RT2600ac-Router/blob/main/README.md) for installation, screenshots, routing behaviour and configuration details.

If WireGuard Manager is useful, consider starring the [repository](https://github.com/ICHTBAA/WireGuard-Client-for-Synology-RT2600ac-Router).
