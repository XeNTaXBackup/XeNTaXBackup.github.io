## Post #1
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-03-19T17:20:14+00:00
- Post Title: Ascend: Hand of Kul res.sacb file and others

Hello, first time posting here, so please don't get angry at me.

I am trying to unpack the res.sacb file from the game Ascend: Hand of Kul, which was available on Xbox 360. (Now on Steam, so you can download it)
But this format is undocumented and there are absolutely zero valid search results for that here.
The only thing I understood was that the first 4 bytes repeat one time after "!SigB!" part and that part stays the same for all *.*b files.
This game has been around for quite a lot of time, but nobody (or anyone I could find, for that matter...) had time to actually make an unpacker for those files.
I went as far as trying to use D3D Ripper while the game was running without any success. Any ideas?
If you want file, I can send it for you.

p.s. Those .wem files have WaveFMT header but has invalid structure.

1.2.xmlb entire file (in ASCII)

```
æqe€!SigB!..æqe€................................................................................l..€,...<?xml version="1.0" encoding="ISO-8859-1" ?>....
```

res.sacb header (in ASCII)

```
^oŽò!SigB!..^oŽò................................................................................
```


EDIT 2: .BNK files and .WEM files are Wwise Audio Bank files. Use BNKExtr tool.
EDIT 3: Ripped WAV files are still unreadable. What's going on?

EDIT:
A little bit more information here.
So .xmlb is a XML file, which wasn't compressed. It had exactly 96 bytes of header, which is:

```
(4 byte header)!SigB!(02 00)(4 byte header)(80 bytes of null)
```

The trailing bytes might be indicating what kind of encryption/compression is being used (6C 00 00 80 2C 00 00 00 on aforementioned .xmlb file).
The rule is:
a) It starts with 4 byte string.
b) It always has "!SigB!.." after the first 4 bytes.
c) First 4 bytes of data repeats after that.
d) There are 80 bytes of null characters after that.
e) File always ends with four bytes of null characters.
f) Some lines repeat with few bytes changed. Possibly bzip?
## Post #2
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-03-20T03:18:03+00:00
- Post Title: Ascend: Hand of Kul res.sacb file and others

Plus, there is a file table on offset 114ED0~25744F.
Check the enclosed file table dump for more information.
(I am still unsure about those *.*b files.)
[res.sacb.filetable.7z](https://xentaxbackup.github.io/file/10611_res.sacb.filetable.7z)
## Post #3
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-06-26T15:05:02+00:00
- Post Title: Ascend: Hand of Kul res.sacb file and others

Found out how to do that.

Use this script instead, and use COMMAND LINE mode on QuickBMS. (NOT GUI MODE)

```
get FILES long
math OFF = 0x78
for i = 0 < FILES
goto OFF
get NAMEOFF THREEBYTE
math NAMEOFF -= 4
get DUMMY byte
get NAMESIZE long
get UNK1 long
get UNK2 long
get OFFSET long
get ZSIZE long
get SIZE long
getdstring DUMMY 0x1c
savepos OFF
goto NAMEOFF
getdstring NAME NAMESIZE
if SIZE == ZSIZE
log NAME OFFSET SIZE
else
clog NAME OFFSET ZSIZE SIZE
endif
next i
```


Usage: quickbms.exe (script file name) res.sacb (destination folder, recommended)

I still have to figure out how to remove extra "SigB" header from the files...
## Post #4
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-06-27T09:31:09+00:00
- Post Title: Ascend: Hand of Kul res.sacb file and others

.*b files have 68(16) bytes of useless data in front of them. EXCEPT for some files. They seem to be in a substandard format.

Currently verified:
.swfb
.xmlb

Info:
.tgab files have static 70(16) bytes of data.
.nutb files have F0(16) bytes of junk data.
