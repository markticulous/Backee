# Backee

Free, private backup for Windows 10 and 11. Choose what to protect, choose where it goes, and Backee does the rest on a schedule, with every backup kept as a version you can go back to.

**[Download the latest release](https://github.com/markticulous/Backee/releases/latest)** and open the `.msi` file. Backee is a beta (version 0.x), so expect rough edges and keep another copy of anything that matters.

## What it does

- **Backs up files and folders** on a schedule you choose: every few hours, daily, weekly or monthly. A backup missed while the PC was off runs once when it is back on.
- **Four places to back up to:** a drive on this PC (including a USB drive), any S3-compatible service (Backblaze B2, Wasabi, Cloudflare R2, Amazon S3, MinIO and others), Microsoft OneDrive, or Google Drive. OneDrive and Google Drive connect directly, so their desktop apps are not needed.
- **Keeps versions.** Each backup stores only what changed, and data that is the same in many files is stored once. Older versions are tidied up by a retention rule you choose.
- **Encrypts if you ask.** Turn on a password per backup and everything is encrypted before it leaves this PC.
- **Backs up files that are open**, by taking a Windows shadow copy first.
- **Restores any version.** Browse its folders, tick what you want, preview what will happen, and restore to the original place or to another folder. By default nothing is overwritten.
- **Runs as a Windows service with a tray icon**, so backups run on time whether or not the window is open.
- **Updates itself**, safely: see below.

## Why Backee is fast

- **Only changes are read.** Files whose size and modified time match the last backup are not opened.
- **Duplicates are stored once.** Files are split by content, so a chunk already in the backup is never stored or uploaded again, even if it moved or was renamed.
- **No effort is wasted on data that will not shrink.** Photos, video and archives skip compression.
- **All processor cores work in parallel**, at low priority, so the PC stays responsive while it runs.

## Install and updates

Download `Backee-<version>-x64.msi` from the [latest release](https://github.com/markticulous/Backee/releases/latest) and double-click it. Windows asks once for administrator permission. Backee carries its own copy of .NET, so there is nothing else to install.

Backee is not code-signed yet, so Windows SmartScreen may say "Windows protected your PC". Choose **More info**, then **Run anyway**.

**Updates are checked, not trusted.** Once a day Backee looks at this page for a newer release. Each release carries a small description of itself (its version and the exact size and fingerprint of the installer) signed with a key that only the maintainer holds; the matching public key is built into Backee. Backee installs an update only if the signature is genuine and the download matches the fingerprint. It installs only when no backup or restore is running and no Backee window is open, and your backups, schedules and settings are kept. A failed update rolls back to the version you had.

**To remove Backee**, use Settings, Apps, Installed apps. Your backups and Backee's settings and history are kept, so reinstalling picks up where you left off.

## Privacy and terms

Backee runs on your PC and sends your files only to the places you choose. It does not collect data about you and has no ads or tracking.

- [Privacy policy](https://markticulous.github.io/support/backee-privacy.html)
- [Terms of use](https://markticulous.github.io/support/backee-terms.html)

## Third-party software and trademarks

Backee includes open-source software under its own licences; the full notices are in the `licenses` folder where Backee is installed. Microsoft, OneDrive and Windows are trademarks of the Microsoft group of companies. Google Drive and its logo are trademarks of Google LLC. Backee is not affiliated with or endorsed by Microsoft or Google.

## Support

Backee is free. If it gives you peace of mind, you can [buy me a coffee on Ko-fi](https://ko-fi.com/markticulous).
