# EverShade

**Cloud's local-server project for Neverness to Everness.**

EverShade runs a private world on your PC. The Windows Hub handles client setup, local accounts, server controls and game launch. This repository distributes builds and release notes; it does not contain the Hub's source code.

This is a testing build. Story restoration is in progress. A successful login or a passing server test does not mean every quest, activity or agent behaves exactly like the live game.

## Download

Get **Evershade-Setup.zip** from [Releases](https://github.com/CloudyCodez/EverShade/releases). Extract the whole folder before running `Evershade Hub.exe`.

You need Windows x64 and your own installed NTE client matching supported Steam build **26083544**. The setup does not include the official game. Extract EverShade onto the same NTFS drive as your installed client so setup can share content files without downloading them again. Python and .NET do not need to be installed separately.

## Open testing

Testing is open. No invitation key, activation request or manual approval is required. Download the setup and follow the steps below. Existing accounts and saves stay in place when updating.

## First run

1. On first launch, Hub opens **Setup & settings** and searches for NTE automatically. The selected path and supported-build confirmation appear on screen. Use **Find NTE automatically** to search again, or **Browse** for an unusual installation folder.
2. Click **Prepare client**. Watch the progress display for file counts and final verification. If NTE is on a different drive, move the extracted Evershade folder to that drive first; this allows large content files to be shared instead of duplicated.
3. Click **Start server** after setup reports success. First startup can take up to two minutes; progress appears in Activity. Wait for **Server ready**.
4. Click **Launch game**. The button only enables when client setup is complete and all three local services pass their health checks.

The default account is **Player**. Creating more accounts is optional; use **Accounts** when needed and close the game before switching.

The supported client is prepared in a separate folder. Accounts have separate saves under `runtime\profiles`. Use **Back up selected** before testing a major update. Removing an account keeps a recovery copy under `runtime\deleted-accounts`.

## Player and story testing controls

Press **F10** in the game for the native testing menu. Player controls include God mode, one-hit kills, infinite stamina and unlimited transformation for Black Bird and Fadia (press R again to exit). Other agents’ alternate states are still being restored. Story recovery can advance the current objective or skip the tracked quest when a restoration issue blocks testing; it changes that account's progress, so back up first. These controls share the current client session with the Hub.

## Recovered audio

Hub 0.1.4 checks for recovered English speech during client preparation and game launch. Missing content downloads automatically with visible progress; interrupted downloads can resume. Existing complete content is reused. Allow approximately 1.7 GB for the voice download if your installation is missing it. Setup and automatic updates reuse the same published, hash-verified speech packs. They download only when missing; an existing working voice installation is kept.

## Updating from 0.1.4

Close the game and server, then install the signed Hub 0.5 update. Open **Setup & settings → Prepare client** once to connect the updated Steam content to your private client. Accounts and activation stay in place. This release requires Steam build 26083544; it does not bypass the client compatibility check.

## Updates

The Hub checks this repository's latest release and downloads newer signed updates. An available, verified newer release is required before setup or game launch. Apply it with **Install update & restart** after closing the game.

Update manifests are signed by Cloud's owner key. Packages and individual files are checked before installation. An update cannot replace profiles or account configuration. Failed installation attempts roll back replaced files and write a result in `runtime\hub-updates`; the Hub does not automatically restart itself into an installation loop. When GitHub cannot be reached, a previously discovered required update remains required. Otherwise the Hub can continue offline with its installed version.

Do not delete your existing folder to update. If repairing manually, preserve `runtime\profiles`, `runtime\accounts.json`, your `.toml` files, `evershade.json`, and the activation directory above.

## Reporting a problem

Include the Hub version, agent or activity involved, the last action before the failure, and whether it survives a full restart. Click **Export logs** beside the server controls and send the resulting ZIP to Cloud. This works even if the server cannot start. The export includes recent log tails, Hub activity and service status; it excludes account saves and activation files. Review logs before sharing them publicly. **Activity → Open logs folder** also opens the original files. Never upload a profile backup, tester key or activation request publicly.

## Credits and notices

**Cloud** leads EverShade: project direction, live-client restoration, modified server behavior, integration and testing. The Hub and tester distribution are part of Cloud's EverShade project.

The server foundation is [Fadia / fadia-rs](https://git.xeondev.com/fadia-rs/fadia-rs). Its original authors retain credit for that foundation. The modified server remains under **AGPL-3.0**. The matching license and corresponding server source, including build instructions, are supplied in `licenses\FADIA-AGPL-3.0.txt` and `licenses\fadia-corresponding-source.zip` inside each complete setup. That license does not grant rights to Cloud's separately distributed Hub.

**REA** provided reverse-engineering resources and tooling that substantially accelerated analysis and verification.

Neverness to Everness and its original assets belong to their respective owners. EverShade is an independent project and is not an official game service.
