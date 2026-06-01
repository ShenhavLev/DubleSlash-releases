# DubleSlash — Releases

Public download artifacts for the [DubleSlash](https://github.com/ShenhavLev/DubleSlash-method) desktop app.

The app's source code lives in a private repo. This repo only holds the `.dmg` installers and the Tauri updater manifest (`latest.json`) so first users and the auto-updater can fetch them without GitHub auth.

## Install (macOS, Apple Silicon — M1 or newer, macOS 13+)

1. Download the latest `.dmg` from the [Releases page](https://github.com/ShenhavLev/DubleSlash-releases/releases/latest).
2. Open the `.dmg` and drag **DubleSlash** to your Applications folder.
3. Open **Terminal** and run:

   ```bash
   xattr -dr com.apple.quarantine /Applications/DubleSlash.app
   ```

4. Open DubleSlash from Applications. Grant Accessibility permission when prompted (System Settings → Privacy & Security → Accessibility).

### Why the `xattr` step?

The MVP build is not yet signed with an Apple Developer ID. macOS attaches a quarantine flag to anything downloaded from the web; for unsigned apps this surfaces as a confusing **"DubleSlash is damaged and can't be opened"** dialog. The `xattr` command removes that flag — there's no actual corruption, no security tradeoff beyond the one you already accepted by choosing to install. Apple Developer signing + notarization is planned for a later release; once that's in place this step goes away.

If you get any other error, ping Shenhav.
