# Release notes

## Hub 0.1.1 — October 17, 2026

- Fixed low-contrast tabs and profile dropdowns. Account and setup panels now scroll on smaller displays.
- Added **Export logs** beside the server controls. It saves recent server logs, Hub activity and service status in one ZIP, without saves or activation files.
- Fixed setup with an empty client path so it can search installed Steam libraries and save the detected location.
- Replaced CIM-based startup port checks with native Windows checks. Startup allows up to two minutes, reports progress and includes log details if it times out.
- Fixed Stop server on Windows PowerShell 5.1, where service records were being read as a nested array and processes could remain running.
- Fixed account selection after removing a selected account, and included the fresh-account creation sidecar when archiving a deleted account.

This update keeps the previously published gameplay runtime and leaves unchanged server binaries out of the update download. The relocated startup test passed; use Export logs if startup still fails on another PC.

## Hub 0.1.0 — October 17, 2026

- Added a Windows Hub with local account selection, creation, backups and removal.
- Added guided setup for the supported installed client and health-gated game launch.
- Added signed, manually approved tester activation. Invitations approve one PC installation.
- Added signed GitHub update downloads, required-version gating and installation rollback.
- Packaged the launcher and .NET runtime so testers do not need separate developer tools.
- Included the modified Fadia server's license, corresponding source and build instructions.

Server development checks pass, including growth, Arcs, Consoles, inventory transactions and story-state progression. The full fresh-account intro, cinematic flow and end-to-end story are still being restored. This release is not a claim of complete live-server parity.
