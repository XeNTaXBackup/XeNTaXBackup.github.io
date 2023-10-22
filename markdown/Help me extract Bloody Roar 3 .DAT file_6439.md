## Post #1
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-04-16T07:46:02+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: He1ix&Spira1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 19, 2011 5:34 pm
- Post datetime: 2011-04-19T09:36:18+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

Anyone help us?
## Post #3
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-04-20T16:11:11+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-06-03T16:42:23+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

Help me plz anyone
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-06-28T19:14:59+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

> Reply from S0UZ
>
> Help me plz anyone

Here is information about Bloody Roar 3:
The main data file is IMAGE00.dat
However the file names are in the 
IMAGE00.TBL file.
Here is the format of the IMAGE00.TBL file:
01 00
2Byte#NumberofRealFiles
4Byte#NumberofTotalFiles(in mine it includes the null last file of size zero)
4ByteIntegerOffsetToFileTable (on mine the pointer says 0x18)
4ByteIntegerSizeofASCIITable
4ByteIntegerOffsetToASCIITable
4ByteIntegerOffsetToEndofTBLfile

FileTableArrayFormat:
{4ByteUnknown, 4ByteStartofFile, 4ByteSizeofFile}
(In my file table the last listing is of size zero so a script should account for this to avoid an error because the last dummy file does not have a file name, only the first "NumberofRealFiles" are valid files)

ASCIITableArrayFormat:
File Paths are 0x00 terminated
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-07T19:18:25+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

I made a QuickBMS script, that will extract the .dat file from Bloody Roar 3. What you do is run this script:
[http://ps23dformat.wikispaces.com/file/view/br3.bms](http://ps23dformat.wikispaces.com/file/view/br3.bms)

Put both the
IMAGE00.DAT file
and the
IMAGE00.TBL file in the same folder.
Then open the br3.bms file using QuickBMS
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
First select the .TBL file
Then select where you want the files saved. 

```
open FDDE TBL 0
open FDDE DAT 1
ImpType Standard ;
Set D Long 2 ;
GoTo D 0 ;
Get C Int 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
SavePos D 0 ;
Set JF Long 16 ;
GoTo JF 0 ;
Get JF Long 0 ;
GoTo D 0 ;
For T = 1 To C ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos D 0 ;
SavePos CSO 0 ;
Get CS Long 0 ;
Get D Long 0 ;
SavePos D 0 ;
GoTo JF 0 ;
Get FN String 0 ;
SavePos JF 0 ;
GoTo D 0 ;
Log FN FO CS 1 ;
Next T ;
</bms>
```
## Post #7
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-08-15T13:35:06+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

Can anyone make some script for import model into 3ds max or blender plz
## Post #8
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-27T23:37:34+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

> Reply from S0UZ
>
> Can anyone make some script for import model into 3ds max or blender plz
Yes, I want to work on this game, the format is complex, I do not know what to make of the models which are contained in the TTM files, but currently I do know most of the format of the Texture files, which have the extension TI, let me make a script, to convert the textures, and I will post the script here.
## Post #9
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-29T00:22:50+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

Here is a script that will convert most of the TI files from this game. The only TI files it does not convert, are ones in which the texture count is different then the palate count.
This is a QuickBMS script:
[http://ps23dformat.wikispaces.com/file/ ... xtures.bms](http://ps23dformat.wikispaces.com/file/view/br3TItotxdtextures.bms)
Run with the commandprompt the -w must be lowercase:

```
D:\black\quickbms\quickbms.exe -w D:\black\quickbms\br3TItotxdtextures.bms D:\black\quickbms\0210.TI D:\black\quickbms
```

then when it asks you what other file you want to open just put in a name of a non existing file, say dat.dat.
Then the script will out put several .TXD files.
Use the free program called "PS2TXDViewer" from 
[http://www.steve-m.com/downloads/tools/txdviewer/](http://www.steve-m.com/downloads/tools/txdviewer/)

to open the txd files, ignore any error, by just clicking ok, and do not highlight anything but the first texture in each txd, as there is only one texture per txd, highlighting anything else but the first texture will crash the program.
Press control-F to see the texture properly. To extract you must go over to the menu, and press extract several textures, select the first, but uncheck the options.
An example of a converted texture:


Here is the script:

```
Get startfile Long 0 ;
Get texcount short 0 ;
Get palcount short 0 ;
Get base Long 0 ;
If texcount != palcount ;
CleanExit ;
EndIf
GoTo startfile 0 ;
SavePos palbase 0 ;
Math Fox = texcount ;
Math Fox *= 16 ;
Math Fox += palbase ;
Math texbase = Fox ;
GoTo texbase 0 ;
SavePos texbase 0 ;
For T = 1 To palcount ;
GoTo 0 1 ;
set M Byte 0x16 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos TotalSize 1 ;
Put 0 Long 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
Put palcount Long 1 ;
SavePos Zebra 1 ;
GoTo texbase 0 ;
Get D short 0 ;
Get X short 0 ;
Get Y short 0 ;
Get D short 0 ;
Get totex long 0 ;
GoTo 4 0 SEEK_CUR ;
SavePos texbase 0 ;
GoTo palbase 0 ;
GoTo 8 0 SEEK_CUR ;
Get topal long 0 ;
GoTo 4 0 SEEK_CUR ;
SavePos palbase 0 ;
Math HALFX = X ;
Math HALFX /= 2 ;
Math HALFY = Y ;
Math HALFY /= 2 ;
Math TLONG = X ;
Math TLONG *= Y ;
Math TLONG += 1372 ;
Math XY = X ;
Math XY *= Y ;
Math atex = totex ;
Math atex += base ;
Math apal = topal ;
Math apal += base ;
GoTo Zebra 1 ;
set M Byte 0x15 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
Put TLONG Long 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x50 ;
Put M Byte 1 ;
set M Byte 0x53 ;
Put M Byte 1 ;
set M Byte 0x32 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x06 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0C ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x45 ;
Put M Byte 1 ;
set M Byte 0x5F ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0x5F ;
Put M Byte 1 ;
set M Byte 0x36 ;
Put M Byte 1 ;
set M Byte 0x32 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x5A ;
Put M Byte 1 ;
set M Byte 0xE8 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
Put X Long 1 ;
Put Y Long 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0xB5 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x80 ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0xDD ;
Put M Byte 1 ;
set M Byte 0x05 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x5C ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0C ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x80 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x05 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x54 ;
Put M Byte 1 ;
set M Byte 0x80 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x56 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x50 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x18 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xC0 ;
Put M Byte 1 ;
set M Byte 0x0F ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x90 ;
Put M Byte 1 ;
set M Byte 0x5A ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x0E ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x51 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
Put HALFX Long 1 ;
Put HALFY Long 1 ;
set M Byte 0x52 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x53 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos qqq 1 ;
For Pixel = 1 To XY ;
GoTo atex 0 ;
Get pix Byte 0 ;
SavePos atex 0 ;
GoTo qqq 1 ;
Put pix Byte 1 ;
SavePos qqq 1 ;
Next Pixel ;
GoTo qqq 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x0E ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x51 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x52 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x53 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos qqq 1 ;
For deer = 1 To 1024 ;
GoTo apal 0 ;
Get pix Byte 0 ;
SavePos apal 0 ;
GoTo qqq 1 ;
Put pix Byte 1 ;
SavePos qqq 1 ;
Next deer ;
GoTo qqq 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0xC0 ;
Put M Byte 1 ;
set M Byte 0x0F ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos Zebra 1 ;
GoTo TotalSize 1 ;
Put Zebra Long 1 ;
Set NUM long T ;
string QQ = texture. ;
string QQ += NUM ;
string QQ += .TXD ;
Log QQ 0 Zebra 1 ;
For wolfwolf = 0 To Zebra ;
Put 0 Byte 1 ;
Next wolfwolf ;
Next T ;
```
## Post #10
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-08-29T14:39:54+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

> Reply from FurryFan
>
> S0UZ wrote:Can anyone make some script for import model into 3ds max or blender plz
Yes, I want to work on this game, the format is complex, I do not know what to make of the models which are contained in the TTM files, but currently I do know most of the format of the Texture files, which have the extension TI, let me make a script, to convert the textures, and I will post the script here.
I had onetime saw you edit pcsx2 to edit texture,does this effect point or vertex of those model?I mean when you edit vertex of 1 model,will you figure out what this file is and what to do with it?Sorry i'm just noob in this,and my request may be too hard,you are the only one who continue in this,so i'm hoping you don't abandon it
## Post #11
- Username: pepodmc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 28, 2017 1:29 pm
- Post datetime: 2020-06-01T18:17:03+00:00
- Post Title: Help me extract Bloody Roar 3 .DAT file

> Reply from FurryFan ↑Wed Aug 29, 2012 8:22 am at Wed Aug 29, 2012 8:22 am
>
> 
Here is a script that will convert most of the TI files from this game. The only TI files it does not convert, are ones in which the texture count is different then the palate count.
This is a QuickBMS script:
http://ps23dformat.wikispaces.com/file/ ... xtures.bms
Run with the commandprompt the -w must be lowercase:
Code: Select allD:\black\quickbms\quickbms.exe -w D:\black\quickbms\br3TItotxdtextures.bms D:\black\quickbms\0210.TI D:\black\quickbms
then when it asks you what other file you want to open just put in a name of a non existing file, say dat.dat.
Then the script will out put several .TXD files.
Use the free program called "PS2TXDViewer" from 
http://www.steve-m.com/downloads/tools/txdviewer/

to open the txd files, ignore any error, by just clicking ok, and do not highlight anything but the first texture in each txd, as there is only one texture per txd, highlighting anything else but the first texture will crash the program.
Press control-F to see the texture properly. To extract you must go over to the menu, and press extract several textures, select the first, but uncheck the options.
An example of a converted texture:


Here is the script:
Code: Select allopen FDSE ? 1 ;
Get startfile Long 0 ;
Get texcount short 0 ;
Get palcount short 0 ;
Get base Long 0 ;
If texcount != palcount ;
CleanExit ;
EndIf
GoTo startfile 0 ;
SavePos palbase 0 ;
Math Fox = texcount ;
Math Fox *= 16 ;
Math Fox += palbase ;
Math texbase = Fox ;
GoTo texbase 0 ;
SavePos texbase 0 ;
For T = 1 To palcount ;
GoTo 0 1 ;
set M Byte 0x16 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos TotalSize 1 ;
Put 0 Long 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
Put palcount Long 1 ;
SavePos Zebra 1 ;
GoTo texbase 0 ;
Get D short 0 ;
Get X short 0 ;
Get Y short 0 ;
Get D short 0 ;
Get totex long 0 ;
GoTo 4 0 SEEK_CUR ;
SavePos texbase 0 ;
GoTo palbase 0 ;
GoTo 8 0 SEEK_CUR ;
Get topal long 0 ;
GoTo 4 0 SEEK_CUR ;
SavePos palbase 0 ;
Math HALFX = X ;
Math HALFX /= 2 ;
Math HALFY = Y ;
Math HALFY /= 2 ;
Math TLONG = X ;
Math TLONG *= Y ;
Math TLONG += 1372 ;
Math XY = X ;
Math XY *= Y ;
Math atex = totex ;
Math atex += base ;
Math apal = topal ;
Math apal += base ;
GoTo Zebra 1 ;
set M Byte 0x15 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
Put TLONG Long 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x50 ;
Put M Byte 1 ;
set M Byte 0x53 ;
Put M Byte 1 ;
set M Byte 0x32 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x06 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0C ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x45 ;
Put M Byte 1 ;
set M Byte 0x5F ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0x5F ;
Put M Byte 1 ;
set M Byte 0x36 ;
Put M Byte 1 ;
set M Byte 0x32 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x5A ;
Put M Byte 1 ;
set M Byte 0xE8 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
Put X Long 1 ;
Put Y Long 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0xB5 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x80 ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0xDD ;
Put M Byte 1 ;
set M Byte 0x05 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x5C ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0C ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x80 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x05 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x54 ;
Put M Byte 1 ;
set M Byte 0x80 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x56 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x50 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x18 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xC0 ;
Put M Byte 1 ;
set M Byte 0x0F ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x90 ;
Put M Byte 1 ;
set M Byte 0x5A ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x0E ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x51 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
Put HALFX Long 1 ;
Put HALFY Long 1 ;
set M Byte 0x52 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x53 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos qqq 1 ;
For Pixel = 1 To XY ;
GoTo atex 0 ;
Get pix Byte 0 ;
SavePos atex 0 ;
GoTo qqq 1 ;
Put pix Byte 1 ;
SavePos qqq 1 ;
Next Pixel ;
GoTo qqq 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x0E ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x51 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x52 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x53 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos qqq 1 ;
For deer = 1 To 1024 ;
GoTo apal 0 ;
Get pix Byte 0 ;
SavePos apal 0 ;
GoTo qqq 1 ;
Put pix Byte 1 ;
SavePos qqq 1 ;
Next deer ;
GoTo qqq 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x04 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0xFF ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
set M Byte 0xC0 ;
Put M Byte 1 ;
set M Byte 0x0F ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
SavePos Zebra 1 ;
GoTo TotalSize 1 ;
Put Zebra Long 1 ;
Set NUM long T ;
string QQ = texture. ;
string QQ += NUM ;
string QQ += .TXD ;
Log QQ 0 Zebra 1 ;
For wolfwolf = 0 To Zebra ;
Put 0 Byte 1 ;
Next wolfwolf ;
Next T ;


Hello.

Thanks for the script and the tips, i was able to extract some txd files with this.

But i want to know if there is a way to reinsert a modified image into the txd or build a new working TXD. I want to make changes to the UI of the game (characters select portraits, main menu screen,etc.)
Because if i build a new TXD with "TXD builder" when i want to open it again with "TXD viewer" it gives me a "range check error".

I made a spanish translation of the game some years ago, and i didnt knew how to extract TI files ,so, some things are still in english.

[https://www.youtube.com/watch?v=7uU9qiAFrTc](https://www.youtube.com/watch?v=7uU9qiAFrTc)

Thanks for the help.
