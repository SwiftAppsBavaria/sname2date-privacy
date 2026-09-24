# Privacy Policy for sName2Date

Last updated: 2026-09-24

## In brief

sName2Date collects, stores and transmits **no** personal data. The app works entirely on
your Mac and never connects to the internet.

## What data the app processes

sName2Date reads the files you explicitly hand to it — by picking them in the open dialog
or by dragging them onto the window. It reads the file name and the file's metadata; it
writes the capture date into exactly those files.

On request, the app also renames these files (off by default). It also sets their creation
and modification date (on by default, can be switched off in Settings). For files that
cannot hold a capture date — such as PDF or text — it always sets only these two dates
instead.

When the **Write date into the file** checkbox is off, the app opens **not a single file**:
it reads only the name and changes only the name and, if set, the creation and modification
date. The content is neither read nor written.

Without your selection the app accesses no file at all. macOS enforces this through the app
sandbox.

If the app searches a folder that contains the "Music" folder, macOS may ask whether it may
access "Media & Apple Music". The app reads neither your library nor your listening history.
There, as everywhere, it works only with files and writes the date into audio and video
files whose name carries one.

## What the app stores on your Mac

- **Settings** in a file `config.json` in the app's protected application folder.
- **A diagnostic log** in the same place, deleted automatically after seven days. It
  contains times and counts of operations. You can save it and pass it on via
  Settings → Diagnostics; otherwise it never leaves your Mac.
- **The paths of the folders you have released**, together with the permission from macOS to
  open them again at the next launch. This is the only reason the app does not have to ask
  every single time. The list contains folder paths, no file contents, and the "Choose
  Folder" button shows it to you.

All of this is removed along with the app when you delete it.

**The app creates something next to your files in one case only:** if a photo, video or
audio file cannot hold the capture date itself (such as HEIF, WebP or AVI), the app writes
it into a sidecar file with the same name and the extension `.xmp`, which many photo
programs read as well. ⌘Z removes it again. Next to other files, such as PDF or text, one is
never created. If a sidecar file is already there — it then comes from another image
program — its capture date is updated as well, so that the file and its sidecar do not say
different things. Whatever the app does not understand inside it stays untouched.

## No sharing, no analytics

There is no advertising, there are no analytics services, no crash reports to third parties
and no accounts.

## Contact

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
