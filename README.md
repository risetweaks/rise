# RISE

[![Windows build](https://github.com/risetweaks/rise/actions/workflows/windows.yml/badge.svg)](https://github.com/risetweaks/rise/actions/workflows/windows.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-orange.svg)](LICENSE)

RISE is a proprietary Windows 10/11 desktop utility built with .NET 8 and WPF. It brings system information, reversible user-level settings, game discovery and launching, process-priority profiles, and Windows-native network and maintenance tools together in one app.

**Website:** [risetweaks.netlify.app](https://risetweaks.netlify.app/) · **Community:** [Discord](https://discord.gg/ynW9VufKY)

## Features

- Dark RISE-branded interface with a launch animation and animated page transitions.
- Live Windows version/build, CPU, display-driver GPU name when available, memory, system-drive space, architecture, battery status, active power scheme, and network availability.
- Ten individually implemented, documented, reversible per-user registry tweaks. This build provides 10 tweaks; it does not claim the requested 130 Free or 300 Pro tweaks. Original values are saved before changes; individual and bulk restore are available. RISE does not disable Windows services or security protections.
- Search and category filters for the actual tweak inventory; the displayed total comes from the implemented definitions.
- Updated the app logo to match the supplied angular peak mark in orange and black.
- Detection of 24 game profiles in common installation folders, with manual executable selection and launch. Steam library folders are read from the local Steam configuration.
- Light, Balanced, and Extreme launch profiles request Normal, AboveNormal, and High process priority, respectively. RISE never requests real-time priority or terminates other processes.
- Live CPU-time and working-set readings for the process RISE launched. System-wide CPU usage is reported separately.
- Existing Windows power-plan activation with confirmation and a session-only restore option.
- Active adapter/IP/DNS display, ICMP connectivity/loss/round-trip measurements to `1.1.1.1`, and a Windows DNS-cache flush command.
- Current-user startup manager: review, disable, and restore registry `Run` entries without deleting their saved commands.
- Registered desktop-app inventory, Windows Settings links for app removal and startup management, conservative cleanup of old top-level files in the current user's temp folder, and text system-report export.
- Persistent accent, launch-at-sign-in, animation, boost-profile, and manually located game settings.
- Official RISE website and Discord links. No passwords or fabricated Pro entitlements are stored.

## Build and run

Install the .NET 8 SDK on Windows:

```powershell
dotnet build RISE.csproj -c Release
dotnet run --project RISE.csproj
```

Publish a self-contained x64 Windows build:

```powershell
dotnet publish RISE.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true
```

The GitHub Actions Windows workflow builds the app and publishes a downloadable build artifact for pushes and pull requests.

## Safety and limitations

RISE is an early preview, not the complete optimizer described in the original product specification. The desktop app currently provides the Free edition only. Secure sign-in, Pro subscription validation, Developer access, and a backend are not implemented; editing local files cannot grant a verified account entitlement because there is no client-side entitlement system. Read each change before applying it. User settings and registry backups are stored under `%LOCALAPPDATA%\RISE`.

Games are launched from their detected or manually selected executable; some titles require their official launcher or anti-cheat flow and may not start directly. The process opened by a launcher may not be the game itself. Automatic game updates, GPU/FPS/frame-time/game-ping telemetry, DNS benchmarking/provider changes, per-game settings, custom RISE power plans, AppX removal, service/process managers, restore-point creation, backups of arbitrary settings, tray support, licensing, and developer diagnostics are not implemented. Startup management is limited to the current user's registry `Run` entries; it does not change all-user entries, startup folders, or scheduled tasks.

Windows does not expose a generally reliable game-independent FPS or GPU-reading API, so unavailable values are not estimated or fabricated. DNS changes are not claimed to reduce game ping, and RISE does not promise performance gains.

## Contributing

Bug reports and feature requests are welcome. Code contributions require prior written permission from the rights holder; read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting code. Please do not include passwords, license keys, personal paths, or other sensitive information in issues or logs.

## License

This repository is distributed under the All Rights Reserved terms in [LICENSE](LICENSE). Copyright (c) 2026 risetweaks. Changing the license for this repository does not revoke rights that may have been granted under earlier distributions; those copies remain subject to their original terms.
