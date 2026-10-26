## WireGuard Manager v1.0.10 candidate

For Synology RT2600ac on SRM 1.3.2-9366 Update 3. This release includes the full ARMv7 WireGuard installer and SRM desktop App. It is an in-place Package Center upgrade from reviewed versions 1.0.1–1.0.9; fresh installation is also supported when no prior Manager state exists. Disable Manager and wait for Apply to finish before upgrading. Back up configuration and private keys externally.

Changes since 1.0.0 include Package Center in-place upgrades, DNS-reply learning with bounded periodic refresh, guarded multi-profile health recovery, WAN fallback for rules and dependent profiles when a parent profile is turned Off or deleted, improved Save/Apply handling, a revised desktop/mobile status layout, and per-profile MTU input. In 1.0.10, a profile without an imported or explicit MTU uses **Auto: 1420**; an MTU imported from `.conf` is displayed and used.

The owner checked an earlier 1.0.10 archive on one RT2600ac: successful upgrade with settings and private keys preserved; Manager/profile enable-disable; rule/profile add-delete; action changes; changed and unchanged Save; intended VPN connectivity; imported 1360 and Auto 1420 MTU; and unauthenticated/non-administrator access denied. This published candidate corrects only the embedded README. Archive comparison confirmed all runtime and installer files are byte-for-byte the same; the repacked archive itself has not been installed on the Router. A failed-upgrade rollback, independent security review, and fresh installation on a second Router remain unverified. Accordingly, this is a **candidate**, not a security-certified stable release.

The `README.md` embedded in this candidate correctly identifies v1.0.10 and the 1.0.1–1.0.9 upgrade range. Router owners already on the older 1.0.10 archive do not need to reinstall for documentation alone; Package Center does not support same-version replacement.

Installer: `WireGuardManager-1.0.10-1010-RT2600ac-UNTESTED-c88266f54ee5.spk`
SHA-256: `c88266f54ee5cd652ee95f871e9ab5bd844a6557863472cb69638da4d370a98f`

Download the `.spk` release asset, not GitHub's automatic source-code ZIP/TAR. See the repository README for installation, upgrade, recovery, limitations, and licensing. The `UNTESTED` filename is retained for provenance; it denotes unfinished release gates despite the single-Router checks above.
