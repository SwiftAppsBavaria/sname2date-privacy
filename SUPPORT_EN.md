# Help for sName2Date

## What the app does

sName2Date looks for a date in the file name and writes it into the image, video or audio
file as the capture date. If there is no capture date yet, it is created.

At the top of the window there are two checkboxes for this, and they do not exclude each
other:

| | |
|---|---|
| **Write date into the file** | puts the date into the file itself as the capture date — the app's main job |
| **Convert file names** | brings the name into ISO notation, for **every** kind of file |

Both together are the normal case. If only the second one is set, the app opens no file and
only renames.

## First steps

1. Pick a file with "Choose File…" or drag it onto the window. The full version also takes
   whole folders including their subfolders.
2. The list shows the recognized date for each file and, if there is one, the capture date
   already set.
3. "Write Date" carries out the change.

## Frequently asked questions

**A file says "No date found in the name".**
The name contains no recognizable date. Among the notations that are recognized are
`2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`, `2024_01_15`,
`15.01.2024`, `15-01-2024`, `15.01.24` as well as spelled-out month names such as
`15 Jan 2024`, `15 March 2024` or `January 15 2024`. `2016 04` and `04-2016` are read too
— the first of the month then applies, and the row says so.

The app recognizes month names in your system language and in English. Transliterations are
not recognized — in German, for example, `15 Maerz 2024` with `ae`/`oe`/`ue` instead of an
umlaut; enter the date by hand on the right of the row.

**A date is read as the wrong day.**
The third of April is `3.4.` in German and `4/3` in English — the same two numbers with
opposite meanings. With `15-03-2024` this does no harm, since there is no month 15. Only
when both numbers would pass as a month (`03-05-2024`) does someone have to decide: an
orange bar then appears above the list offering both readings, and the affected rows are
marked. The default is the notation of your system region.

**The name contains two dates.**
The first one wins: in `IMG_20240115_bearbeitet_2019-03-02` that is the shot, not the later
note. A date with a time always takes precedence over one without.

**The name contains only a date, no time.**
A time is then assumed — 12 noon by default. You can change it in the settings.

**I want to date a scanned old photo.**
That works: dates entered by hand reach back to 1826, the year of the oldest surviving
photograph.

**Will my photo lose quality?**
No. The image data is taken over unchanged, a JPEG is not recompressed. For videos the
tracks are passed through, nothing is re-encoded.

**Which formats are supported?**
The app writes the capture date into the file itself for images (JPEG, PNG, TIFF, HEIC,
GIF), videos (MP4, MOV, M4V) and audio recordings (M4A, M4B) — the checkmark in the row is
then green.

The list takes **any** file, though. Where the format holds no capture date — a PDF, say, a
text file or a spreadsheet — the app sets the file's creation and modification date instead;
the checkmark is then orange. Applications, aliases and package documents do not appear in
the list.

**My HEIF, WebP or AVI file has a blue checkmark.**
These three formats hold no capture date. The app therefore writes it into a sidecar file
with the same name and the extension `.xmp`, which photo programs such as Lightroom or
digiKam read as well.

With HEIF the extension is often all it takes: as `.heic` the same data counts as a
different format and is then written into the file itself.

**I only want to tidy up the file names without touching the files.**
At the top of the window, switch "Write date into the file" off and "Convert file names" on.
The app then opens not a single file and changes only the name and, if switched on in the
settings, the creation and modification date — `Invoice 15.03.2024.pdf` becomes
`2024-03-15 12-00-00 Invoice.pdf`, and the folder sorts by date in the Finder. This applies
to every kind of file, PDFs, text or spreadsheets included.

If you want the date to stay where it stood in the name, switch "Put date first" off.

Renaming changes the folder entry, and for that macOS needs permission for the folder. If
you choose the folder right away in the full version, that grants it. If you selected
individual files — always the case in sName2Date Lite — the app asks once for the folder; a
parent folder is enough, and the permission still applies after a restart. In the full
version, the "Choose Folder" button lists the most recently used ones in a menu.

**There is a file with the extension `.xmp` next to my file.**
Either it comes from another program — Lightroom and digiKam create such sidecars — or
sName2Date created it because the format does not hold the capture date itself (HEIF, WebP,
AVI; the checkmark is then blue). ⌘Z takes back a sidecar created this way. The app carries
an existing one along when it changes the capture date: otherwise the file would say one
thing and its sidecar another, and most programs read the sidecar first.

**With a large folder, the app asks whether it should keep reading it in.**
Whole folders at once are read by the full version. From 5,000
files on — for example with the home folder including its subfolders — it stops and asks.
While reading in and evaluating, it shows a counter and a progress bar; writing is possible
only once the list is complete. It goes faster with a smaller folder or without "Include
subfolders".

**Can I undo a change?**
Yes. ⌘Z takes back a whole run — capture date, creation and modification date and, if
switched on, the changed file name as well. ⌘⇧Z restores it.

One piece of advice all the same: make a backup before working through a large collection.
Undo restores the values, but it is no substitute for a backup copy.

**Renaming did not work, but the date is in the file.**
If a single file was selected, the app may only work on that file, not in its folder — and
renaming changes the folder entry. Select the folder instead of the individual file, or
grant permission when the app asks for it. Permission granted once still applies after a
restart and covers all subfolders as well.

## Something went wrong?

Settings → Diagnostics → "Save log…" writes the messages of the last seven days into a text
file. Feel free to send it along with your description of the problem.

## Contact

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
