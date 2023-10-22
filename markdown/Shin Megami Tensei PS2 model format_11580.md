## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-06-08T13:06:05+00:00
- Post Title: Shin Megami Tensei PS2 model format

Hello, could anyone please look at the following [files](http://puu.sh/9kebZ/58c847c552.7z) I uploaded?
The .pb files seem to be a container of sorts, seeing how it sections like TXP0, TMX0, MD00 and so forth
The model format is used by all PS2 Shin Megami Tensei games (SMT III, Digital Devil Saga 1/2, Devil Summoner 1/2)
The TMX files can be converted using a [program](http://puu.sh/9ke7K/ad12c167bb.7z) left on the disc.
I don't know how to crack it myself so I appreciate any help.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-10T00:02:06+00:00
- Post Title: Shin Megami Tensei PS2 model format

using hex2obj (view link in my sig):



luci_PB.JPG (37.93 KiB) Viewed 243 times


other submesh:
0x72FA0 471
Vb0
0x0
0x73350 179
020000
0x0 255
(copy previous 6 lines into an empty txt file and save it as luci_mask.h2o for example
 then load model and h2o into hex2obj)

hex2obj is intended for a quickcheck only, to get the full model a script would make sense.
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-06-10T21:49:43+00:00
- Post Title: Shin Megami Tensei PS2 model format

> Reply from shakotay2
>
> using hex2obj (view link in my sig):
luci_PB.JPG
Oh wow, thanks. I tried messing around with it myself but I'm not a coder, I can't do much with this myself sadly.
All I can do is hope someone is willing to write a script lol.
## Post #4
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-06-18T20:14:57+00:00
- Post Title: Shin Megami Tensei PS2 model format

I just took a cursory look at it, it seems to follow this basic pattern:

```
uint16 fileId;
uint32 flags;
char segmentType[4];

```


EDIT:
It also contains texture data in the TMX0 section
TXP0 seems to be a palette.

And I forgot to mention, but it's probably known: The files are little endian.

EDIT2:
Do you mind seeing if there is a PDB on the disc?

> [antidote@the-key-bearer BE0605]$ file BE0605.exe 
>
> BE0605.exe: PE32 executable (GUI) Intel 80386 (stripped to external PDB), for MS Windows

EDIT3:
I was wrong about a few things, I've removed them.
## Post #5
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-06-23T07:14:39+00:00
- Post Title: Shin Megami Tensei PS2 model format

> Reply from antidote
>
> I just took a cursory look at it, it seems to follow this basic pattern:
Code: Select alluint16 unk;
uint16 fileId;
uint32 flags;
char segmentType[4];


EDIT:
It also contains texture data in the TMX0 section
TXP0 seems to be a palette.

And I forgot to mention, but it's probably known: The files are little endian.

EDIT2:
Do you mind seeing if there is a PDB on the disc?

[antidote@the-key-bearer BE0605]$ file BE0605.exe 
BE0605.exe: PE32 executable (GUI) Intel 80386 (stripped to external PDB), for MS Windows


EDIT3:
I was wrong about a few things, I've removed them.
Uhh, I can't exactly extract all the files, since it uses some archive with the filetable in a seperate file.
Unless I knew what to look for with a hex editor, I can't find the PDB.
