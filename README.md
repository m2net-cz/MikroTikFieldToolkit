# MikroTik Field Toolkit

Bulk RouterOS upgrades, safe wireless-driver migrations and config deployment for
MikroTik fleets — built by a working ISP operator, for working ISP operators.

> **Status:** free public **beta (v1.0.0)**. Windows desktop app. No telemetry.

## Why

I run a small WISP on MikroTik gear and never found an upgrade/migration tool that fit.
The late nights doing bulk upgrades and config migrations got old, so I built my own.
This is that tool.

## What it does

- **Bulk RouterOS upgrades** with the mandatory v6 → v7 hops (6.49 → 7.12.1 → newer),
  architecture-aware package selection, and an automatic backup before every action.
- **Safe upgrade ordering** — detects PoE power (never reboots an injector and the device
  it powers at the same time) and wireless role (APs serving clients go last, stations/CPEs
  first), following backhaul chains.
- **wireless → wifi-qcom driver migration** (7.13+) with config conversion, a two-step
  safe switch for wireless-only-reachable devices, and rollback.
- **CAPsMAN (v6 → v7 wifi)** and **OSPF (v6 → v7)** migration with preview and warnings —
  nothing is applied until you confirm.
- **Safe config & firewall deploy with auto-rollback** — if a router goes silent after a
  deploy, it restores itself from backup within a set window.
- **WireGuard config generator**, bulk password change, backups (binary + .rsc), old-backup cleanup.
- Inventory with groups, CSV import, manual `.npk` upgrade for advanced cases.
- **Bulk Password change**


## Requirements

- Windows 10/11 (64-bit).
- SSH access to your routers (the toolkit uses SSH for upgrades and scripts; API/API-SSL
  is used for quick identification).
- RouterOS v6.x or v7.x targets.

## Safety

This tool acts on production hardware. Every risky operation takes a backup first, and the
critical steps have auto-rollback. **Even so: test on a lab or non-critical device first.**
Driver switches on wireless-only-reachable devices are inherently risky — read the in-app
warnings before confirming.

## Privacy

**No telemetry.** The app sends no usage data anywhere. The license is checked on activation
and then the app runs offline (with a 14-day offline grace window).

## Download & license

1. Download the latest build from **[Releases](../../releases)**.
   SHA-256: `sha256:f8eab53f0d1eb209aee0049f9705a68f1a5a9e453e54a2059f01effc3488a006`
2. It's free to test. Email **info@m2net.cz** and I'll issue a license valid for
   **3 months, up to 100 devices**.
3. Activate in the app (About → license → enter `LIC-…` → Activate).

In return I'd appreciate honest feedback — what's missing, what's awkward, what you'd use.
Beta testers get founder pricing once it becomes a paid product.

## Server / Docker edition

There is also a server (Docker) edition for web-based fleet management. It is
**experimental and not production-tested yet** — treat it as a preview.

## License

Proprietary software. © M2NET.CZ s.r.o. All rights reserved.
Redistribution, decompilation, or reverse engineering is not permitted.
This repository contains documentation and release binaries only; no source code.

## Contact

M2NET.CZ s.r.o. — info@m2net.cz — https://www.m2net.cz
