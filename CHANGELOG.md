# Release notes

## Hub 0.5.0 — October 24, 2026

- Ported the private-client adapter and Hub setup to Steam build 26083544. Updated native function addresses and changed player/character fields, including Shinku resource handling, housing state and Fair diagnostics.
- Client preparation now reconnects shared content files when Steam replaces its archives. Existing accounts and activation are preserved; run Prepare client once after installing this update.
- Added business furnishing transactions and demand modifiers, bounded housing-layout restoration, Tycoon property refresh, and safer NPC shop purchase validation. Added paid Puka activity transactions; score-based Puka minigames remain unfinished.
- Updated agent HUD rebinding and native resource-widget refresh after switching characters. Story, housing and agent behavior still need gameplay testing; this release does not claim full live-server parity.
- Preserves signed automatic updates and automatic recovery of missing English voice packs.

Validation: 182 server tests, 47 adapter tests, Hub self-test, setup/archive repair, and update rollback checks pass. Native adapter initialization was verified on the new build. World entry and gameplay on this Steam build still need tester verification; they are not claimed as passed.

## Hub 0.1.4 — October 20, 2026

- Existing installations now fetch and verify missing English voice packs automatically during client preparation or game launch, with download progress and interrupted-download recovery. Complete installations reuse their local packs.
- Restored Shinku's held-forward sprint form and corrected native form-effect application. Fixed temporary ability removal so Fadia retains her base abilities after using her ultimate. Both fixes were confirmed in the running client.
- Improved active-agent skill and ultimate rebinding. Some custom resource displays and alternate-state mechanics still need verification; this release does not claim full agent parity.
- Fixed business earnings collection losing partial operating time, repeated settlement after clock rollback, and accrual after capped offline periods. Added Tycoon upgrade request and account-ownership validation.
- Includes the current housing and character restoration work. Housing interactions, Tycoon rewards and the full story remain under testing.
- Preserves accounts, settings and tester activation. The signed update remains compatible with older Hubs; the large voice downloads are separate from the update archive. Matching AGPL server source and build instructions remain included.

## Hub 0.1.3 — October 19, 2026

- Added native F10 player controls for God mode, one-hit kills, infinite stamina and unlimited transformation for Black Bird and Fadia, plus targeted story objective/quest recovery controls. The Hub and in-game controls share the current session.
- Fixed numbered native widget lookup, translated Player/Story controls and removed unused GM buttons. Fixed a form-monitor type mismatch that could stop the local server during login.
- Updated the gameplay runtime with movement-role fixes, character development, Arcs and Consoles, and additional story and City Tycoon restoration work. City Tycoon and story remain incomplete; this is not a claim of full live-server parity.
- Full setup includes recovered English voice content. The automatic update preserves compatibility with existing 0.1.2 Hubs and does not include the large voice packs; existing installations can use the complete setup for recovered audio.
- Preserved local profiles, settings, activation records and the matching AGPL license/corresponding server source in the release.

## Hub 0.1.2 — October 17, 2026

- Fixed the false "Missing service" error after successful startup. Health checks and log exports now normalize Windows path separators before comparing process paths.
- Added automatic first-run client discovery across Steam libraries, registered NTE installs and common game folders on available drives. Discovery verifies the supported client build before selecting it.
- Added numbered setup steps, a persistent progress display, file-preparation counts and explicit verification confirmation. Start server stays disabled until client preparation finishes.
- Added setup checks for free space, NTFS and matching drives, plus clear instructions when the Hub folder needs moving beside the installed game's drive.
- Failed or interrupted preparation is no longer marked ready. Repeating setup resumes existing files and checks the final executable and base DLL hashes.
- Expanded diagnostics with normalized expected service paths and process-inspection errors.

Verified the reported path mismatch against actual running services, automatic discovery, supported-build rejection, isolated client preparation and repeat setup under Windows PowerShell 5.1. Gameplay runtime is unchanged from 0.1.0; story restoration remains in progress.

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
