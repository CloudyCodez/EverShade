# EverShade

**Cloud's local-server project for Neverness to Everness.**

EverShade runs a private world on your PC. The Windows Hub handles client setup, local accounts, server controls and game launch. This repository distributes builds and release notes; it does not contain the Hub's source code.

This is a testing build. Story restoration is in progress. A successful login or a passing server test does not mean every quest, activity or agent behaves exactly like the live game.

## Download

Get **Evershade-Setup.zip** from [Releases](https://github.com/CloudyCodez/EverShade/releases). Extract the whole folder before running `Evershade Hub.exe`.

You need Windows x64 and your own installed NTE client matching supported build **25643250**. The setup does not include the official game. Extract EverShade onto the same NTFS drive as your installed client so setup can share content files without downloading them again. Python and .NET do not need to be installed separately.

## Tester access

Downloads are public. Setup currently requires a tester key issued by Cloud.

1. Put your assigned `.key` file beside `Evershade Hub.exe`. Keep only your own invitation in that folder.
2. Open the Hub and choose **Export request**.
3. Send the generated activation-request JSON to Cloud privately.
4. Import the approved `.key` file Cloud returns. You can also place it beside the Hub and reopen it.

Each invitation can approve one PC installation. Re-exporting the same request does not use another key. Do not post invitations or activation requests in public issues. A reinstall of Windows or loss of your local activation folder may need Cloud's help.

Once approved, activation is stored under `%LOCALAPPDATA%\Evershade\activation`. Updating the Hub does not ask for your key again. The game server runs locally; approval is a manual exchange, not a permanent connection to a licensing service.

## First run

1. Open **Setup & settings**, select your installed NTE folder, and choose **Set up client**.
2. Choose or create an account in **Accounts**. Close the game before switching accounts.
3. Choose **Start server**. The Hub checks all three local services before enabling **Launch game**.

The supported client is prepared in a separate folder. Accounts have separate saves under `runtime\profiles`. Use **Back up selected** before testing a major update. Removing an account keeps a recovery copy under `runtime\deleted-accounts`.

## Updates

The Hub checks this repository's latest release and downloads newer signed updates. An available, verified newer release is required before setup or game launch. Apply it with **Install update & restart** after closing the game.

Update manifests are signed by Cloud's owner key. Packages and individual files are checked before installation. An update cannot replace profiles, account configuration or the activation store. Failed installation attempts roll back replaced files and write a result in `runtime\hub-updates`; the Hub does not automatically restart itself into an installation loop. When GitHub cannot be reached, a previously discovered required update remains required. Otherwise the Hub can continue offline with its installed version.

Do not delete your existing folder to update. If repairing manually, preserve `runtime\profiles`, `runtime\accounts.json`, your `.toml` files, `evershade.json`, and the activation directory above.

## Reporting a problem

Include the Hub version, agent or activity involved, the last action before the failure, and whether it survives a full restart. **Activity → Open logs folder** opens the local logs. Remove personal information before sharing logs. Never upload a profile backup, tester key or activation request publicly.

## Credits and notices

**Cloud** leads EverShade: project direction, live-client restoration, modified server behavior, integration and testing. The Hub and tester distribution are part of Cloud's EverShade project.

The server foundation is [Fadia / fadia-rs](https://git.xeondev.com/fadia-rs/fadia-rs). Its original authors retain credit for that foundation. The modified server remains under **AGPL-3.0**. The matching license and corresponding server source, including build instructions, are supplied in `licenses\FADIA-AGPL-3.0.txt` and `licenses\fadia-corresponding-source.zip` inside each complete setup. That license does not grant rights to Cloud's separately distributed Hub.

**REA** provided reverse-engineering resources and tooling that substantially accelerated analysis and verification.

Neverness to Everness and its original assets belong to their respective owners. EverShade is an independent project and is not an official game service.
