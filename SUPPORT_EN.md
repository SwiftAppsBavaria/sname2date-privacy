# Help for sName2Date

## What the app does

sName2Date looks for a date in the file name and writes it into the image or video file as
the capture date. If there is no capture date yet, it is created.

The full version has **two modes** for this, switched at the top of the window:

| | |
|---|---|
| **Capture Date** | writes the date into the file — the app's main job |
| **File Names** | only brings the name into ISO notation, for **any** kind of file |

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
In *Capture Date* mode: the images JPEG, PNG, TIFF, HEIC and GIF, the videos MP4, MOV and
M4V. The app writes the date into the file itself for all of these.

In *File Names* mode **no extension matters** — only the name is changed there, and every
file has one.

**My HEIF, WebP or AVI file does not appear in the list at all.**
These three formats hold no capture date — the app could only park the date beside them
instead of writing it in, and that is precisely not what it is for. They are therefore
passed over while loading in *Capture Date* mode; a line above the list says how many there
were.

They can still be renamed: switch to *File Names* for that.

With HEIF the extension is often all it takes: as `.heic` the same data counts as a
different format and is then written.

**I only want to tidy up the file names without touching the files.**
Switch to *File Names* at the top of the window. The app then opens not a single file and
changes only the name — `Invoice 15.03.2024.pdf` becomes `2024-03-15 12-00-00 Invoice.pdf`,
and the folder sorts by date in the Finder. This applies to every kind of file, PDFs, text
or spreadsheets included.

If you want the date to stay where it stood in the name, switch "Put date first" off.

⚠️ In this mode the app accepts **folders** only, not individual files. The reason is the
renaming itself: it changes the folder entry, and for that macOS needs permission for the
folder — which comes about when you select it. Once chosen, the app remembers the folder;
the "Choose Folder" button lists the most recently used ones in a menu.

**There is a file with the extension `.xmp` next to my file.**
That one comes from another program — Lightroom and digiKam create such sidecars.
sName2Date creates none, but it carries an existing one along when it changes the capture
date. Otherwise the file would say one thing and its sidecar another, and most programs
read the sidecar first.

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

Andreas Heiligtag · andreas.heiligtag@gmx.de
