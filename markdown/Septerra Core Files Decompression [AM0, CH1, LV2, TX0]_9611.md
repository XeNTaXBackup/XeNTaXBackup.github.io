## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-09-07T19:08:06+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

Thanks to aluigi .db archives was unpacked - [viewtopic.php?f=10&t=4809&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=4809&start=15)

However, unpacked files have internal compression, which is not very strong. Part of files can be like a container, which have resource complex - graphics, sounds, etc.

AM0 - sprites and animations.
CH1 - character data.
LV2 - level data resources.
TX0 - texts.

Plus two files - 000001e4.gv0 and 000002e8.il0.

Stuns unpack Deflate and LZO data from files.
Try use .PAS sources of LZSS and LZW compression, but without success.

Think what files have LZ-like or RLE-like compression.

Files can be send throught PM.
## Post #2
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-01-22T15:31:38+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

Unpacked data from demo-version of the game - [http://www.mediafire.com/?98b8op5ueoc5k1m](http://www.mediafire.com/?98b8op5ueoc5k1m)

Without .DAT(.MOV files) and .VSS(.MP3 files) files.
## Post #3
- Username: JustDragonflies
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 24, 2013 9:50 pm
- Post datetime: 2013-03-25T11:52:36+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

I've made a start with decoding the TX0 files and through analysing the executable I found out the following.

The first 16 bytes make up the header of the file. The bytes after that contain the offset table referencing the items in the data section, which is the last section.

Header

```
4..7   -> Number of entries
8..11  -> Size (in bytes) of the data section
12..15 -> Dummy, always seems to be 1

```


Using the number of entries provided in the header you can read the 12 byte structures of the offset table which contain the following data.

Offset Table (x times 12 byte entries)

```
 4..7   -> Length
 8..11  -> Unknown, probably an ID

```


Using these headers you can read the actual data stored. But the data that comes out isn't ASCII, so perhaps there is a form encryption or compression going on, but I haven't been able to identify it yet. @ResearchMan are you certain that the files contain texts, or could it be something else.

I've written a quick/dirty program which decodes the files of which I included an example (the PDF file).

EDIT:
Well it definitely contains text. When you XOR the bytes with 0x60 you get something rather readable. You also need to add the value 2 for bytes in the range of 62..88 (after XOR). The value FF (before XOR) stands for a space. There are still some characters which aren't translating correctly, I will investigate further.

EDIT 2:
I've made a dump of the memory of the game while it was running to see whether the texts get decoded, which isn't the case. So either the texts get decoded on the fly when needed, or the bytes reference a position inside a font graphic, which is more likely I think, because besides the XOR 0x60, there doesn't seem to be a pattern for decoding the other characters (like numbers, quotes, etc...). I will create a translation table and post it here later on. I will also cleanup my source code and put it on Github or something.
[000001e5.pdf](https://xentaxbackup.github.io/file/6288_000001e5.pdf)
## Post #4
- Username: XDarkx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 27, 2011 12:26 am
- Post datetime: 2015-04-01T17:36:46+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

> Reply from JustDragonflies
>
> I've made a start with decoding the TX0 files and through analysing the executable I found out the following.

The first 16 bytes make up the header of the file. The bytes after that contain the offset table referencing the items in the data section, which is the last section.

Header
Code: Select all0..3   -> Header, always 'TX00'.
4..7   -> Number of entries
8..11  -> Size (in bytes) of the data section
12..15 -> Dummy, always seems to be 1


Using the number of entries provided in the header you can read the 12 byte structures of the offset table which contain the following data.

Offset Table (x times 12 byte entries)
Code: Select all 0..3   -> Offset from begin of file
 4..7   -> Length
 8..11  -> Unknown, probably an ID


Using these headers you can read the actual data stored. But the data that comes out isn't ASCII, so perhaps there is a form encryption or compression going on, but I haven't been able to identify it yet. @ResearchMan are you certain that the files contain texts, or could it be something else.

I've written a quick/dirty program which decodes the files of which I included an example (the PDF file).

.
Sorry for revive.
Anyway, Interesting description, as I use this to translate the game texts to another language eg Spanish and convert it again, is possible? I always wanted this.
## Post #5
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-10T15:43:51+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

Hello again, 7 year into the future!

Sorry for the necropost, but are there news over here? Did someone try to look into this matter again? I cannot help technically, but I have time to translate.

Best,

Giovarco
## Post #6
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-10T16:15:16+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

> Reply from Giovarco
>
> Hello again, 7 year into the future!

Sorry for the necropost, but are there news over here? Did someone try to look into this matter again? I cannot help technically, but I have time to translate.

Best,

Giovarco

I found this: [https://github.com/FileFormatTools/jRip ... pterraCore](https://github.com/FileFormatTools/jRipper/tree/master/Tools/SepterraCore)

I think that this contains the solutions of our problems!
## Post #7
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-12T16:02:43+00:00
- Post Title: Septerra Core Files Decompression [AM0, CH1, LV2, TX0]

> Reply from Giovarco
>
> Giovarco wrote:Hello again, 7 year into the future!

Sorry for the necropost, but are there news over here? Did someone try to look into this matter again? I cannot help technically, but I have time to translate.

Best,

Giovarco

I found this: https://github.com/FileFormatTools/jRip ... pterraCore

I think that this contains the solutions of our problems!

Up!

I took a look to JRipper. Inside TX0.vb, you can read "To decrypt TX0 files you must first XOR 96 and then increment uppercase letters +2 (i.e A = C, B = D)". 

Can someone kindly check?
