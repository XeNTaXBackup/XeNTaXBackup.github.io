## Post #1
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-05-30T12:25:52+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

Hey i've been trying to unpack The Void / Tension Bigfiles and it works, atleast for files without folder structures.

I've never worked with mexcom script before but i wanted to give it a try 

File Structure of .VFS Files:

long 0x0 = fileheader = "LP2C"
long 0x4 = total folders in Archive(probably )
long 0x8 = files in current folder
byte 0xC = length of filename
string 0xC + lof = filename
long 0xC + lof = filesize
long 0xC + lof + 4 = offset of file in archive
long 0xC + lof + 4 + 12 = next file

i don't know if  i explained this correctly but check my example files and you'll know wtf i mean 

Examples archives:
[http://s000.tinyupload.com/index.php?fi ... k=transfer](http://s000.tinyupload.com/index.php?file_id=44463602804929757198&gk=transfer)

the script will work perfectly for Effects.vfs however Properties.vfs contains a folderstructure and i have no idea how to handle it...

This is my BMS script so far:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "LP2C"
get TOTAL_SIZE asize
get FOLDERS long 0
set PATHNAME string ""

if FOLDERS < 1;
get FILES long 0
else;
#set FILES 0 
EndIf;

for i = 1 to FILES;
get FILENLENGTH byte 0
getdstring FILENAME FILENLENGTH

get FILESIZE long 0

savepos OFFSET
math OFFSET += 4
goto OFFSET
get FILEOFFSET long 0

string PATHNAME += Extracted
string PATHNAME += \
string PATHNAME += FILENAME

log PATHNAME FILEOFFSET FILESIZE

set PATHNAME string ""

savepos OFFSET
math OFFSET += 12
goto OFFSET

next i;

```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-30T19:09:32+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

the bms language is not good for recursive formats like this one
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-07T21:12:29+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

new version of quickbms just released with (experimental) support for recursive function.
I have tested it with the 2 files you provided and worked perfectly so get the script and the new version and test also the other files:
[http://aluigi.org/papers/bms/thevoid.bms](http://aluigi.org/papers/bms/thevoid.bms)
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-29T16:09:32+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

I tried and is NOt working in a big file called TEXTURES.VFS 3.183.391.171bytes, if you need big attachments (like 25-50mb's) i can upload.

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file Textures.vfs
- open script thevoid.bms
- set output folder output

  offset   filesize   filename
------------------------------
- SCRIPT's MESSAGE:
  the ZERO value is not 0 (721451109), contact me!

```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T16:27:12+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

ok no problem, first try the following test.
open thevoid.bms with a text editor and place a # before the "cleanexit" instruction at line 29, example: "#cleanexit"
then relaunch the script and check if all the files are extracted correctly.
then open the first extracted file (the one for which was showed the ZERO alert) and check if it's content is correct.

if the extraction fails or the content of the file is corrupted then I need to analyze this file, otherwise let me know if it's all correct and I will remove the alert
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-29T17:13:41+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

Okay added # in cleanexit at line 29 i get the next:

```
------------------------------
- SCRIPT's MESSAGE:
  the ZERO value is not 0 (721451109), contact me!

  742e426f 1818582872 \normalize.prc\n☻\_lt.prc♠☺\fresnel_glass.prc\r☻\Û╔☺‼ps_fi
rework_ray.texP♂\Ü╠☼╣Û╔☺‼map_moving_girl.texÇ►\exÇ§\\ãn(╣Û╔☺¶Garden2GrassTile.te
xÇ \◄\◄\y_up.texÇ \HT_LemnaMoonSkyUp.texÇ \\\╔☺▬PS_FX_DrillerSpark.texÇ(\ernButt
erflies.texÇ_\Ole_door2_loops_dnn_300.tex\┘♣\\\Ole_modeling_03_cont_dnn.tex\X♠\\
N7▬╣Û╔☺↓ole_stucco_moulding_2.texÇ_\texÇ_\\_dirDrop.tex

Error: incomplete input file number 0, can't read 584380420 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted

```


No files extracted just created a folder called normalize.prc
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T17:17:45+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

ok, in this case I need to have the file or piece of it
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-29T17:38:44+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

Here is, 44.21MB, unpacked it's 95mb's
[http://www.zshare.net/download/67659142b85bb1a1/](http://www.zshare.net/download/67659142b85bb1a1/)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T18:01:47+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

very well, practically the problem was in the handling of the folders before the files while it was the opposite.
I have updated the [script](http://aluigi.org/papers/bms/thevoid.bms) to version 0.1.1
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-29T22:21:14+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

i get some errors:
This is unpacking the file Textures.vfs

```
  7ef7e0cd 5505152    \garden1_terrain_right_dust.tex
  7f4be14d 5505152    \garden1_tower_down.tex
  7f9fe1cd 5505152    \garden1_tower_down_normal_200.tex
  7ff3e24d 5505152    \garden1_tower_up.tex
  8047e2cd 5505152    \garden1_tower_up_normal_200.tex

Error: the specified offset can't be reached

```


This is unpacking audios in some files, file sizes are different but with same name

```
 0ad698cf 248154     \girl_sister_tree_alive#22.ogg
 0ada6229 248337     \poema#22.ogg
 the file "poema#22.ogg" already exists
 do you want to overwrite it (y/N/all)?

```


And (sorry) the file Scenes.vfs is compressed with zlib, the script unpacks this but not decompress
I upload a 10mb's of scenes.vfs
[http://www.zshare.net/download/676705594a3b061e/](http://www.zshare.net/download/676705594a3b061e/)

Thanks!
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T23:29:11+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

for the first problem it was a bug of quickbms in the handling of files bigger than 2 gigabytes and has been fixed just today in version 0.3.5a, what a luck :)

the second one instead doesn't seem a problem of the script.
sometimes happens that some archives have one or more files with the same name, something like an old and new version of the same file or maybe a resource to which has been assigned the same name (we see their original name but for the game their are only resources to which the latest is the one to be used).

the third one isn't a bug too.
indeed the compressed chunks you see are inside the files so it's part of their format and not part of the archive, that's why don't exist fields in the archive where are located compressed sizes (DUMMY and ZERO are not related to this thing).

I give you an example:
the file test.s is stored at offset 0000f196 and has a size of 11260105 (so till 00acc25f) and we can see a sequence of compressed chunks with offzip in all its content but in its middle and not at the beginning: 0000f25b, 0018ef9f, 001b65ba and so on.

so it's definitely a feature of that specific file or file format and not something related to the archive :)
## Post #12
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-30T14:51:19+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

Works like a charm!! thanks!!
## Post #13
- Username: Arglaar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 16, 2010 9:08 am
- Post datetime: 2010-08-19T01:45:24+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

Sorry for resurrecting this dead topic, but I seem to be having an issue with this for some reason, and I didn't think it would be appropriate to start a new one.

I wanted to take a look at some of the scripts for the game so I downloaded your tool, and the thevoid.bms script.

When I run the bms script on the scripts.vfs file (attached at bottom), I get the following error message:

```
Error: Not enough space
```


The file, itself is only 8.7 meg big and I have over 500gb free on the hard-disk I'm extracting it to.

Running Windows 7 Professional x64 w/ 4gb of DDR3.
Quickbms version 0.4.6a
thevoid.bms ver 0.1.1
*edit* I forgot to add, this is using the Direct2Drive version of TheVoid, which the data files should be the same, shouldn't they?


Link for the file:
[scripts.zip - 1.77MB - 8.7MB Unzipped](http://www.zshare.net/download/79490975b63ac2e1/)


Thanks in advance for any assistance you can give.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-09-17T16:13:13+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

*edit*
ok I have noticed that you wrote you have version 0.4.6a that is the latest at the moment and same for the bms script, so don't know what else to suggest because here I don't have problems with that file
## Post #15
- Username: Arglaar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 16, 2010 9:08 am
- Post datetime: 2010-09-18T08:01:00+00:00
- Post Title: The Void / Tension Bigfiles(.vfs) - Partial .bms Script done

Thanks for taking a look at it.

Maybe I had the syntax wrong or something. *Shrug*

I've since finished this game and moved on, so it's not really that important anymore to get it working.

Thanks again.
## Post #16
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-01-14T19:38:44+00:00
- Post Title: Re: The Void / Tension Bigfiles(.vfs) - Partial .bms Script 

The .bms script works like a charm. I'm able to extract the textures, but does anybody know where and how the model data is stored? I read somewhere that it's the .ase and .bap files that contain the model, but I haven't been able to find anything to convert and/or open these files.

There's also an XML file and a .s file for each girl, and the XML file defines a lot of things, including scripts and triggers, mesh positions, and particles. It looks like this might just define the particle effects, however.

Anyone have any more information or know how to extract the models for this game?
## Post #17
- Username: SergioF
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 16, 2012 2:59 am
- Post datetime: 2012-06-17T21:47:26+00:00
- Post Title: Re: The Void / Tension Bigfiles(.vfs) - Partial .bms Script 

Hello, I'm from Brazil, I am using a translator.

I tried to uncompress a VFS for a friend of mine, but with this script did not work.
We use the wcx_VFS.wcx and we extract, but this plugin does not insert says that issued 0 files.

Looking at the files and format extaido VFS, I was able to gather this information.
I hope they are information that can help you to make a new extractor and inserter for this file.

I noticed that the file structure VFS is similar to that asked in this topic.

He begins with "LP3C" instead of "LP2C" I saw this topic.
Legend:
==============================AREA A
Offset:          -Byte          - Description
0x06              06             - Even number of folders extracted
0x0C              06             - Size of the folder name followed by the file name Example: 06Actors or 04Data
After the folder name, is the bytes: 00 00 00 00 00 00 00 00
==============================
This sequence of "AREA A" is repeated six times (number of folders)
thus:
XXName YY YY YY YY YY YY YY YY
where:
XX = size of the folder name
Name = name of the folder
YY = 00 Bytes
==============================
After the last folder "Strings" the following changes:
00 00 00 00 20 00 00 00
The byte 20 in decimal is = 32 which indicates the number of files (32 files).
==============================
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;AREA B
Then comes a byte that indicates the size of the file name.
Example: 07hud.txt
after the file name, is two bytes.
Example: hud.txt FA 03

FA 03 ao contrario = 03FA = Offset do inicio do arquivo.
Depois vemos bytes.
00 00 00 00 00 00 6C 00 00 00
FA = 03 Unlike = 03FA Offset from the beginning of the file.
After see bytes.
00 00 00 00 00 00 00 00 00 6C

6C is the file size.
After that the AREA B repeats
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

Link File: [http://www.mediafire.com/?qe9039312s2ug2s](http://www.mediafire.com/?qe9039312s2ug2s)
