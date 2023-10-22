## Post #1
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T17:55:26+00:00
- Post Title: Just Cause 2 Big-Endian Files

Tools (Downloads)
Gibbed Tools (supports x360 files now)
[Gibbed Tools Rev 104](http://www.sendspace.com/file/b795kd)
Convert pc bin to x360 bin + Create - Extract x360 bin - xml exe
[Download](http://www.sendspace.com/file/vbvzux)

------------------------------------------------------------------------------------------------------------------------

Ok I'm making this thread to see if any one could help in converting PC (little-endian) assets to x360 (big-endian) assets as not all the xbox 360 files are mapped out and also the modding community is more interested in modding the PC version.

files compatible off the bat no editing needed.

1. DDS (PC Textures these work on x360)

files that can already be converted to and from Big-Endian

1. Bin Files (xml)
2. eex360z files (All other models)
3. blx360 (some sort of archive?)
4. x360 DDS (Textures, look further down the thread to see how to convert.)

files that currently cannot be converted (that i know of)

1. RBM (Character Models)


Big thanks going out to Rick for his tools to extract and edit these files much appreciated man.

------------------------------------------------------------------------------------------------------------------------

here are two drag and drop batch files for converting, extracting and making x360 bin files. (Gibbed tools needed place both batches inside the folder)

Create - Extract x360 bin - xml

```
MODE CON: COLS=91 LINES=4
title Create - Extract x360 bin - xml

if exist "Gibbed.Avalanche.FileFormats.dll" goto start
Echo Error: Please place this Batch/Exe in the folder containing the Gibbed Tools.
Pause>nul
Exit

:start
if "%~x1" == ".bin" goto bin
if "%~x1" == ".xml" goto xml

:bin
if not "%~x1" == ".bin" goto error
"%~p1\Gibbed.Avalanche.bin2xml" -b "%~1"
exit

:xml
if not "%~x1" == ".xml" goto error
"%~p1\Gibbed.Avalanche.xml2bin" -b "%~1" "%~pn1.bin"
exit

:error
echo:
echo drop an x360 .bin or .xml file on this bat file to extract/create an x360 .bin or .xml file
pause>nul
exit
```

Convert pc bin to x360 bin

```
MODE CON: COLS=56 LINES=4
title Convert pc bin to x360 bin

if exist "Gibbed.Avalanche.FileFormats.dll" goto start
Echo Error: Please place this Batch/Exe in the folder
Echo containing the Gibbed Tools.
Pause>nul
Exit

:start
if not "%~x1" == ".bin" goto error 
"%~p1\Gibbed.Avalanche.bin2xml" "%~1"
ren "%~1" "%~n1_PC%~x1"
"%~p1\Gibbed.Avalanche.xml2bin" -b "%~pn1.xml" "%~pn1.bin"
exit
:error
echo:
echo drop .bin file on this bat file to create x360 .bin file
pause>nul
exit
```


Rick i used the icon in the Other folder hope this is ok if not i can change it.

Updated the batches/exe files to know there in the correct folder.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-12T18:11:21+00:00
- Post Title: Just Cause 2 Big-Endian Files

RBM is going to be a pain to convert right now since only a few block types are partially understood.

If you're aiming to do model replacers like the ones I've already replaced you can do that by using the 360 version of the files.
## Post #3
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T18:12:47+00:00
- Post Title: Just Cause 2 Big-Endian Files

> Reply from Rick
>
> RBM is going to be a pain to convert right now since only a few block types are partially understood.

If you're aiming to do model replacers like the ones I've already replaced you can do that by using the 360 version of the files.

yeah that is what i want to do i want Scorpion  but i cant find any rbm files using the head revision for your tools.
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-12T18:16:07+00:00
- Post Title: Just Cause 2 Big-Endian Files

> Reply from Rocky5
>
> Rick wrote:RBM is going to be a pain to convert right now since only a few block types are partially understood.

If you're aiming to do model replacers like the ones I've already replaced you can do that by using the 360 version of the files.

i thought that but cant find the files lol even in the head revision for your tools rbm files cant be found.Character models should be found inside exported\cdoll\*.eex360z. I don't have the 360 files so I can't look at them.

What files are inside mc01_rico.eex360z?
## Post #5
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T18:18:31+00:00
- Post Title: Just Cause 2 Big-Endian Files

> Reply from Rick
>
> Rocky5 wrote:Rick wrote:RBM is going to be a pain to convert right now since only a few block types are partially understood.

If you're aiming to do model replacers like the ones I've already replaced you can do that by using the 360 version of the files.

i thought that but cant find the files lol even in the head revision for your tools rbm files cant be found.Character models should be found inside exported\cdoll\*.eex360z. I don't have the 360 files so I can't look at them.

What files are inside mc01_rico.ee360z?

here we go attached the original file and the uncompressed version.

i had a look in there but the lod file just points to Characters\MainCharacters\Rico\mc01_lod1-rico.rbm

unless mc01_rico.cdoll is the model don't know this points to the textures and c01_parachute_dif.dds one to so just need to find that one.


you need any files to help your development let me know i love the game and mods make it better.
[mc01_rico.eex360z.rar](https://xentaxbackup.github.io/file/2925_mc01_rico.eex360z.rar)
## Post #6
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-12T18:23:50+00:00
- Post Title: Just Cause 2 Big-Endian Files

Okay, it's possible they didn't do a full eez for Rico since that's not actually used fully by the game unlike other ee's.

What's in mc02_jadetan.eex360z?
## Post #7
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T18:30:54+00:00
- Post Title: Just Cause 2 Big-Endian Files

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-12T18:39:35+00:00
- Post Title: Just Cause 2 Big-Endian Files

Yes but if you pay attention, the model's extension is "rbx360" instead of "rbm".

Which is what the rico model is named - mc01_lod1-rico.rbx360.

(I've committed an update to my SVN to add the new extension to the file list for the Rico model)
## Post #9
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T18:45:06+00:00
- Post Title: Just Cause 2 Big-Endian Files

> Reply from Rick
>
> Yes but if you pay attention, the model's extension is "rbx360" instead of "rbm".

Which is what the rico model is named - mc01_lod1-rico.rbx360.

(I've committed an update to my SVN to add the new extension to the file list for the Rico model)

yeah i noticed that but still doesn't work (invisible model lol) if i use the pc one just testing an x360 model see if it works.
## Post #10
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T20:57:03+00:00
- Post Title: Just Cause 2 Big-Endian Files

OK can now convert x360 dds files to little-endian using hexworkshop.

first thing is open the x360 dds file

copy from offset 0 to 127 cut this an put it in a new file now in this new file flip the bytes 32 bit unsigned long now replace offset - to 4 bytes with 44445320 now go back to the other file and you want to flip the bytes by 16 bit unsigned short now we need to put back in the header open the new file and copy that code and paste it into the original file at the top save and you now have a little-endian dds file.

will upload a video soon showing how to do it.

[video](http://www.youtube.com/watch?v=OPGwswKTE08) may want to wait a bit till its processed correctly.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-12T21:37:30+00:00
- Post Title: Just Cause 2 Big-Endian Files

the following script for QuickBMS is probably a better solution (moreover because it can be launched recursively on a folder):

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "DDS "
get HEADSZ long
if HEADSZ & 0xff000000
    reverselong HEADSZ
endif
math HEADSZ += 4

get SIZE asize
log MEMORY_FILE 0 SIZE
for i = 4 < HEADSZ
    getvarchr NUM MEMORY_FILE i long
    reverselong NUM
    putvarchr MEMORY_FILE i NUM long
    math i += 4
next
for i = i < SIZE
    getvarchr NUM MEMORY_FILE i short
    reverseshort NUM
    putvarchr MEMORY_FILE i NUM short
    math i += 2
next

get NAME basename
string NAME += "_pc.dds"
log NAME 0 SIZE MEMORY_FILE
```
## Post #12
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-12T21:39:18+00:00
- Post Title: Just Cause 2 Big-Endian Files

> Reply from aluigi
>
> the following script for QuickBMS is probably a better solution (moreover because it can be launched recursively on a folder):

ah cheers m8 lol just uploaded my video haha much appreciated.

batch file to convert dds files just place your dds files in the same folder the batch will do the rest.

```
md "dds original"
move "*.dds" "dds original"
quickbms.exe "convert.bms" "dds original" .

```
## Post #13
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2010-04-16T02:02:59+00:00
- Post Title: Just Cause 2 Big-Endian Files

Got model replacing working on the 360 i never realised that there were more than 3 dds entries in each model lol, but all sorted now so time to start replacing model parts.
[](http://img217.imageshack.us/my.php?image=img0488b.jpg)
## Post #14
- Username: xerius
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 16, 2010 11:21 am
- Post datetime: 2010-08-17T04:22:50+00:00
- Post Title: Just Cause 2 Big-Endian Files

> Reply from aluigi
>
> the following script for QuickBMS is probably a better solution (moreover because it can be launched recursively on a folder):
Code: Select all# DDS endian reverser 0.1
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "DDS "
get HEADSZ long
if HEADSZ & 0xff000000
    reverselong HEADSZ
endif
math HEADSZ += 4

get SIZE asize
log MEMORY_FILE 0 SIZE
for i = 4 < HEADSZ
    getvarchr NUM MEMORY_FILE i long
    reverselong NUM
    putvarchr MEMORY_FILE i NUM long
    math i += 4
next
for i = i < SIZE
    getvarchr NUM MEMORY_FILE i short
    reverseshort NUM
    putvarchr MEMORY_FILE i NUM short
    math i += 2
next

get NAME basename
string NAME += "_pc.dds"
log NAME 0 SIZE MEMORY_FILE

Hi! Help pls! How to make the reverse conversion from Little-Endian to Big-Endian?
