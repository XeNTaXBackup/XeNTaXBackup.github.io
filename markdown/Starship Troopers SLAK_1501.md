## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-10T20:53:18+00:00
- Post Title: Starship Troopers SLAK

Help extract SLAK archives for game Starship Troopers
thx  
[slak.zip](https://xentaxbackup.github.io/file/432_slak.zip)
## Post #2
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2005-09-10T22:39:12+00:00
- Post Title: Starship Troopers SLAK

```
uint32 (04)  - Absolute Offset to Directory
uint32 (04)  - Unknown
uint32 (04)  - Unknown (4608)
uint32 (04)  - Unknown (4)
uint32 (04)  - Amount of Files
uint32 (04)  - Unknown
uint32 (04)  - Unknown


 // For each file

uint32 (04)  - Relative Offset to correct Relative Path - from the start of the path entries.
uint32 (04)  - Unknown (3131961357)
uint32 (04)  - Unknown
uint32 (04)  - Unknown (29724392)
uint32 (04)  - Compressed File Length
uint32 (04)  - Uncompressed File Length
uint32 (04)  - Absolute File Offset
uint32 (04)  - Null
uint32 (04)  - Null Terminator Length for the file's relative path?
uint32 (04)  - Unknown


 // For each file

char   (x) - relative path with filename (null terminated)


byte   (x) - file data
```


Something like that I guess.. but it might not be fully correct. 
It seems to use zlib-compression btw.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-11T14:10:04+00:00
- Post Title: Starship Troopers SLAK

Hi mate,

Yep, these are the specs I made - looks kinda the same as the specs above.

```
| Starship Troopers *.slak |
+--------------------------+

// Uses ZLib compression

// ARCHIVE HEADER
  16 - Header ("SlackPackFile  " + null)
  4 - Directory Offset
  4 - File Entry length (40)
  4 - Unknown
  4 - Unknown
  4 - Number Of Files
  4 - Filename Directory Length
  4 - Unknown

// DIRECTORY
  // for each file (40 bytes for each entry)
    4 - Filename Offset (relative to the start of the filename directory)
    4 - Unknown
    8 - Hash?
    4 - Compressed File Length
    4 - Decompressed File Length
    4 - File Offset
    4 - null
    4 - Unknown (1)
    4 - Unknown
    
// FILENAME DIRECTORY
  // for each file
    X - Filename
    1 - null Filename Terminator

// FILE DATA
  // for each file
    X - File Data
```


Will hopefully have a plugin or something for this format within a few days - just need to finish some university work off first.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-20T05:57:18+00:00
- Post Title: Starship Troopers SLAK

OK, I have attached a Game Extractor plugin for this archive - I'm still pretty busy though so I don't have a MexCom script, and I havn't put this plugin into a Game Extractor update yet.

The plugin should work if you unzip it into your "GameExtractor/Plugins" directory, or the "GameExtractor/" directory. If not, you can do the following...

1. Unzip the attachment
2. Open GameExtractor.jar in a zip program like WinZip
3. Put the new plugin into the zip
4. Save it (as GameExtractor.jar , NOT GameExtractor.zip)
5. Run Game Extractor.

Good luck - when I get some more time I will try to get some scripts done and a new Game Extractor update.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_SLAK_SLACKPACK.zip](https://xentaxbackup.github.io/file/441_Plugin_SLAK_SLACKPACK.zip)
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-20T08:05:11+00:00
- Post Title: Starship Troopers SLAK

thx Watooo
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-01T22:19:18+00:00
- Post Title: Starship Troopers SLAK

yeah I know it's a jurassic thread but my post comes from a request I received via mail.
in short an user needed a way to reinject some files so with quickbms 0.4.10b and the following script this is possible and that's the reason I have decided to update this thread:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "SlackPackFile  \0"
get DIRECTORY_OFFSET long
get FILE_ENTRY_LENGTH long
get DUMMY long
get DUMMY long
get FILES long
get FILENAME_DIRECTORY_LENGTH long
get DUMMY long

math FILENAME_DIRECTORY_LENGTH = FILES
math FILENAME_DIRECTORY_LENGTH *= 40
math FILENAME_DIRECTORY_LENGTH += DIRECTORY_OFFSET

goto DIRECTORY_OFFSET
for i = 0 < FILES
    get NAME_OFF long
    get DUMMY long
    get DUMMY longlong
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get DUMMY long
    get DUMMY long  # not the zip!
    get DUMMY long
    savepos TMP
    math NAME_OFF += FILENAME_DIRECTORY_LENGTH
    goto NAME_OFF
    get NAME string
    goto TMP
    if SIZE == ZSIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
*updated*
