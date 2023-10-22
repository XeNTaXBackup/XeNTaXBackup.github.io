## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-03-07T09:16:00+00:00
- Post Title: [IKS] Dexter’s Laboratory – Mandark’s Lab - research & tools

Hello. I have written a set of functions in Python, which allows you to extract/replace text and graphics from game Dexter’s Laboratory – Mandark’s Lab.
This article will have 3 sections: Research info, translation tips and tool description.

* Research info *

Main archive is a DATA.BIN file, which contains everything except STR movies.

```
4 bytes - number of files

//file entry
16 bytes - filename + padding
4 bytes - file size
4 bytes - file offset / 0x800


//file
x bytes - data
108 bytes - padding
```


For BIN file the best option is to use quickBMS script from aluigi:

```
# script for QuickBMS http://quickbms.aluigi.org

get FILES long
for i = 0 < FILES
    getdstring NAME 0x10
    get SIZE long
    get OFFSET long
    math OFFSET *= 0x800
    log NAME OFFSET SIZE
next i

```



TEX files are graphics which appears before each mission in the game.

```
4 bytes - magic
2 bytes - width
2 bytes - height
x bytes - image data
```


TIM files are graphics which appears when game starts (ex. warner bros logo)

```
8 bytes - magic
4 bytes - data size
4 bytes - ?
2 bytes - width
2 bytes - height
x bytes - image data
```


GEC files are graphics that appears on the screen when we are playing any mission in game.
I haven't finished research of this format so it is incomplete.

```
//header
12 bytes - file name
4 bytes -  offset of number of images
4 bytes - offset of table of image offsets
4 bytes - offset garbage data
4 bytes - offset image data array
4 bytes - image data offset
2 bytes - number of images
2 bytes - ? (5dec)
2 bytes - ? (52dec)
2 bytes - ? (32dec)

//image offsets?
number of images*4 bytes - offset of image

//palette data???
x bytes - palette data

//graphic info array
8 bytes - image name
24 bytes - ???

//image data
number of images*x bytes - data


```


* Translation tips *

You can check polish translation here [http://ikskoks.pl/dexters-laboratory-ma ... lszczenie/](http://ikskoks.pl/dexters-laboratory-mandarks-lab-spolszczenie/)

DATA.BIN file: Just use aluigi's quick bms script for extracting and inserting files to main archive
TEX files: Extraxt tex file by tex_to_dds function, edit it in gimp, save image as A1RGB5 format and insert it by dds_to_tex function.
TIM files: as above, but use tim_to_dds and dds_to_tim functions.
STR files: I had troubles with replacing audio in these files. I tried to use STR Converter 1.1 but with no luck. But it is possible to replace movies (with no sounds). If someone has a way to replace audio here, please contact me.
BIN files: There is some text in bin level files. You can replace text in them easily by hex editor.
Dialogues: voice audio is mostly in separate BIN audio track. You can extraxt PCM audio using CDMage and Extractr.NET
GEC files: I think that it is possible to replace GEC images, but it aquire time to write good tool for that.
CUT files: in here you can find all cutscenes between missions.
SND/XND files: sound files, maybe they can be extracted by VAG/VAB/STR tools, but I haven't tried. PSound can play them.

There are also other files like BDT, GEL, LVL, REL, TCP, VRM and TOC but I haven't payed too much attention to them :p

* Tool description *
My tool has several functions that can be used in easy way.
Just go to the end of the script, uncomment function which you want to use and specify a valid path.

List of functions:
unpack_dexter - unpack DATA.BIN file
pack_dexter - unused
unpack_cut_files - extract almost all texts from game
pack_cut_files - packs text to game
tex_to_dds - extracts TEX images
dds_to_tex - imports TEX images
tim_to_dds - extracts TIM images
dds_to_tim - imports TIM images
gec_to_dds - partially extracts GEC images (this function isn't finished)
[Dexter Bin Tool_20.zip](https://xentaxbackup.github.io/file/12563_Dexter Bin Tool_20.zip)
## Post #2
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2017-03-15T00:29:10+00:00
- Post Title: [IKS] Dexter’s Laboratory – Mandark’s Lab - research & tools

do you happen to know which files the models are stored in?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-03-15T07:31:44+00:00
- Post Title: [IKS] Dexter’s Laboratory – Mandark’s Lab - research & tools

Sorry, I have no idea. :p
