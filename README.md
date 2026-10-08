# Roam

A local travel itinerary planner for Windows and macOS. Arrange places and transport by day, use order mode or a timeline, and export mobile-friendly images or shareable itinerary files.

## Documentation

- [Downloads](https://github.com/Niki-Linn/Roam-Downloads/releases/tag/v0.1.19)

## Before downloading

- Download the app from this repository's [Releases page](https://github.com/Niki-Linn/Roam-Downloads/releases/tag/v0.1.19). **Code → Download ZIP** on the repository homepage downloads repository documentation, not a ready-to-run app.
- This is the public download repository. You do not need a GitHub account or repository invitation to download the app. Source code and development history are maintained separately in a private repository.
- The downloads include the required runtime. You do not need to install Node.js, Python or Electron separately. Live searches, weather, maps and model calls require an internet connection.

## Windows installation

1. Under **Assets** on the release page, download `Roam-0.1.19-Windows-x64.zip`. This is the Windows 64-bit version; it cannot run on macOS.
2. Right-click the downloaded ZIP and choose **Extract All**. Extract it to a folder you can write to. Do not run the app from inside the ZIP.
3. Open the extracted `Roam` folder and double-click `Roam.exe`. Keep the other files and subfolders beside it; they are required to run the app.
4. To launch from your desktop, create a desktop shortcut to `Roam.exe`. Do not move the EXE out of its folder by itself.
5. On first launch, open **Settings → Account settings**, connect ChatGPT or enter your own API key, and select a model.

The Windows version is portable and needs no installation wizard. It is not developer code-signed, so Windows may show an unknown-publisher warning. Confirm that the download came from this repository.

## macOS installation

**For Mac, download the `.dmg` for your chip. The `.zip` is an alternative package, not an additional requirement. Both contain the same app; choose one, not both.**

1. Open **Apple menu  → About This Mac** and check the chip or processor. Choose arm64 for Apple Silicon / M-series chips, or x64 for an Intel processor.
2. Under **Assets** on the release page, download the matching file:
   - **Apple Silicon (M-series)**: `Roam-0.1.19-macOS-arm64.dmg`
   - **Intel**: `Roam-0.1.19-macOS-x64.dmg`
3. Double-click the DMG and drag **Roam.app** to the **Applications** folder shown in the window.
4. Once copying finishes, open Roam from **Applications**. You can eject the mounted Roam disk and delete the downloaded DMG.
5. On first launch, open **Settings → Account settings**, connect ChatGPT or enter your own API key, and select a model. macOS may ask you to allow Keychain access.

**Alternative option (optional)**: choose the matching `.zip` only if you prefer a ZIP archive. If you downloaded the DMG, you do not need the ZIP. Extract it, move the complete **Roam.app** to **Applications**, and open it. Do not separate the app bundle or move its internal executable by itself.

The Mac version is currently ad-hoc signed, without an Apple Developer ID signature or notarization. If macOS blocks it, first confirm that it came from this repository, then follow [Apple's instructions](https://support.apple.com/102445): after trying to open the app, go to **System Settings → Privacy & Security → Open Anyway**. Do not disable system-wide security protection.

## Local data, updates and sharing

- **Windows**: Projects, caches and desktop sign-in data are stored in the `RoamData` folder beside `Roam.exe`. Back it up before updating. Extract the new version, then copy your existing `RoamData` folder beside the new `Roam.exe`; do not delete or overwrite your personal data.
- **macOS**: Data is stored in `~/Library/Application Support/Roam/RoamData`. In Finder, use **Go → Go to Folder** to open this path. To update, quit Roam and replace Roam.app in Applications, keeping the data folder.
- Desktop ChatGPT credentials are encrypted using the operating system's local protection. API keys and standalone web-prototype sign-ins currently remain in memory for the running session only. Account and model availability depends on service authorization and usage limits.
- Export dialogs let you choose where to save files or folders. Send a shareable itinerary file to a friend, who can open it using **Import itinerary** on their Roam homepage. Do not share your entire RoamData folder or sign-in credentials.
- Release packages start with an empty project list and exclude the developer's personal projects, credentials and search caches. Place and transport information comes only from actual Google Maps queries; missing results are not filled with sample data.

## Version and verification

The current version is **0.1.19**, with downloads for Windows x64, macOS arm64 and macOS x64. The Windows version retains its existing functionality. Both Mac versions were packaged, backend-tested and launch-tested on GitHub Mac runners of the matching architecture. Live account sign-in, online queries and save dialogs on macOS still need verification on users' own computers.

The release includes `SHA256SUMS.txt` for Windows and `SHA256SUMS-macOS-*.txt` for Mac. To verify a download, compare its SHA-256 hash with the corresponding list using `Get-FileHash -Algorithm SHA256` in Windows PowerShell or `shasum -a 256` in macOS Terminal.

## Third-party components

Electron and Chromium notices are included in the distributions. The bundled Yozai font retains its SIL Open Font License in `app/assets/fonts/OFL.txt`. The app uses functional system fonts by default.

