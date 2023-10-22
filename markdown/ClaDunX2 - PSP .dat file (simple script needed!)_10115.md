## Post #1
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2013-02-07T10:24:28+00:00
- Post Title: ClaDunX2 - PSP .dat file (simple script needed!)

Hello, i guess i need some help after all after hours of staring at BMS syntax and hoping it starts making sense. I knew i was no good at math, because things like "for i < 0 = Files" just look like gibberish to me.

It's a pity, because i know that what i need is a really simple BMS script to extract the files from a DATA.dat file. 

Just take a look at the first few lines and you'll see what i mean.

```
00000010 5359 532E 4441 5432 0000 0000 0000 0000 SYS.DAT2........
00000020 0000 0000 0000 0000 00F2 0400 00AC 5300 .........ò..¬S.
00000030 4D50 3030 3030 322E 444D 4400 0000 0000 MP00002.DMD.....
00000040 0000 0000 0000 0000 1428 0000 0042 B605 ........(...B¶
00000050 4D50 3030 3030 322E 4C44 5400 0000 0000 MP00002.LDT.....
00000060 0000 0000 0000 0000 20C8 0100 00CA A101 ........ È...Ê¡.
...
00004430 4241 525F 5553 4952 4F2E 4D50 4200 0000 BAR_USIRO.MPB...
00004440 0000 0000 0000 0000 D4DF 0100 000E CC05 ........Ôß....Ì
00004450 4E49 535F 4C4F 474F 2E4D 5042 0000 0000 NIS_LOGO.MPB....
00004460 0000 0000 0000 0000 5803 0000 001E E905 ........X....é

```


The first 8 bytes are "PSPFS_V1" and at 0x0008 is the number of files in the archive (547 or 223h).

From 0x0010 onwards there's 32 bytes per file detailing the file name (for 20 bytes as far as i can tell), some bytes padding, then 4 bytes file size and the last 4 bytes are the pointer towards the file.
The pointers are absolute, as you can tell from the address that SYS.DAT2 points to:

```
0053AC00 4453 4152 4320 464C 0A00 0000 0000 0000 DSARC FL........
0053AC10 4152 4D4F 525F 4E4F 4441 5441 2E50 4E47 ARMOR_NODATA.PNG

```


The same data structure works for the PSP and the PC version of the game.
So what i need is a script that reads out the number x of files and then go down the list x times, each time jumping to the pointer, extracting the data to a file and naming it appropriately. Can someone write one for me? Maybe if i look at a script where i know exactly what it does, i'll finally grasp the script's logic.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-07T14:57:59+00:00
- Post Title: ClaDunX2 - PSP .dat file (simple script needed!)

For DAT

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PSPFS_V1"
get FILES long
get NULL long

for i = 0 < FILES
    getdstring NAME 0x18
    get SIZE long
    get OFFSET long
    log NAME OFFSET SIZE
next i
```


For FONT1.ARC FONT2.ARC

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "DSARCIDX"
get FILES long
goto 0x20

for i = 0 < FILES
    getdstring NAME 0x28
    get SIZE long
    get OFFSET long
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2013-02-08T10:52:53+00:00
- Post Title: ClaDunX2 - PSP .dat file (simple script needed!)

Cool, thanks!

I'm still not sure about the loop syntax, but it works.
The music files in the Cladun X2 PSP version are .SPS, which seem to just be AT3 files with a 16 byte header. I modified the script to strip the header and directly export AT3 files for music.

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# Modified by HenryEx
#
# script for QuickBMS http://quickbms.aluigi.org

idstring "PSPFS_V1"
get FILES long
get NULL long

for i = 0 < FILES
    getdstring NAME 0x18
    get SIZE long
    get OFFSET long

    # Comment this if...endif out if you do not want to convert .SPS to .AT3 files
    if NAME & ".SPS"
        string NAME >= ".SPS"
        string NAME += ".AT3"
        math SIZE -= 0x10
        math OFFSET += 0x10
    endif

    log NAME OFFSET SIZE
next i

```
