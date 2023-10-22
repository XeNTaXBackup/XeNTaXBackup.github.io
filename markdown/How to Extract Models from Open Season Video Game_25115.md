## Post #1
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-06T01:44:24+00:00
- Post Title: How to Extract Models from Open Season Video Game

This is a Topic of Open Season Models Extracting Site.
It begins when the Topic needs Updating with People.
Next The Owner needs help Extracting LIN Files from Open Season Video Game, Because the UMD File is Encrypted.
Contact Me if there's an Answer.
## Post #2
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-23T20:04:04+00:00
- Post Title: How to Extract Models from Open Season Video Game

The version of the game best suited for ripping models from is the Xbox 360 version and especially more so that the game is now emulatable on the Canary version of Xenia. As for extracting .lin files, we currently don't know how to do that yet as far as I know.
## Post #3
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-23T20:59:47+00:00
- Post Title: How to Extract Models from Open Season Video Game

Can you show me the Xbox 360 Extract files?
## Post #4
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-23T21:59:37+00:00
- Post Title: How to Extract Models from Open Season Video Game

Dunno about Xbox but PC version is based on Unreal Engine 2 v927. *.lin files are compressed with zlib - after decompressing try [UModel](https://www.gildor.org/en/projects/umodel) to extract content (mesh, animation etc.) - in case of problems you can always ask for support on the [forum](https://www.gildor.org/smf/).
## Post #5
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-23T22:12:53+00:00
- Post Title: How to Extract Models from Open Season Video Game

i'll try and see what happens.
## Post #6
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-23T23:41:13+00:00
- Post Title: How to Extract Models from Open Season Video Game

which in UMODEL? Unreal Engine 2? Unreal Engine 2x? or Unreal Engine 3?
## Post #7
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-23T23:43:35+00:00
- Post Title: How to Extract Models from Open Season Video Game

can you show me how to get the PC Files from the Open Season .LIN Files?
## Post #8
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T01:51:11+00:00
- Post Title: How to Extract Models from Open Season Video Game

> Reply from tritterman ↑Sun Apr 24, 2022 4:59 am at Sun Apr 24, 2022 4:59 am
>
> 
Can you show me the Xbox 360 Extract files?
Here's both common and menu in .lin and .liv respectively [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/17pfLO_Tt28zHMsSzudKUOZCx0Xs2LF2C?usp=sharing) (Xbox 360)
## Post #9
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T01:53:53+00:00
- Post Title: How to Extract Models from Open Season Video Game

> Reply from tritterman ↑Sun Apr 24, 2022 7:43 am at Sun Apr 24, 2022 7:43 am
>
> 
can you show me how to get the PC Files from the Open Season .LIN Files?
Here's both common and menu in just .lin since that's what is only available in the last-gen/PC version [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1IPNa7qxKNT43WkPvFLa6SmSB6CPD-Z8H?usp=sharing) (Incase it's not obvious these are from the PC version specifically.
## Post #10
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-24T15:09:27+00:00
- Post Title: How to Extract Models from Open Season Video Game

now, how can i extract them with?
## Post #11
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T16:41:45+00:00
- Post Title: How to Extract Models from Open Season Video Game

Script for *.lin decompresson:

```
# Game: Open Season
# Engine: Unreal Engine 2 v927 *.lin files
# script for QuickBMS http://quickbms.aluigi.org

set CurOffset long 0
get FileSize asize
get FileName basename
string FileName + ".dec"

do
  goto CurOffset
  get DSize long
  get CSize long

  savepos CurOffset

  Append
  clog FileName CurOffset CSize DSize
  Append

  math CurOffset + CSize

while CurOffset < FileSize

```


CMD:

```
quickbms.exe Open_Season_lin.bms "H:\Open Season\System\Linear\pc\menu.lin" Export

or all files:
quickbms.exe -F "{}.lin" Open_Season_lin.bms "H:\Open Season\System\Linear\pc" Export

```


Note:
*.dec it's a dummy extension and holds bunch of files (depends on content it cold be: .ukx .usx etc.).
*.liv (Xbox) holds the names
## Post #12
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T17:29:30+00:00
- Post Title: How to Extract Models from Open Season Video Game

> Reply from VendorX ↑Mon Apr 25, 2022 12:41 am at Mon Apr 25, 2022 12:41 am
>
> 
Script for *.lin decompresson:
Code: Select all# Open_Season_lin.bms
# Game: Open Season
# Engine: Unreal Engine 2 v927 *.lin files
# script for QuickBMS http://quickbms.aluigi.org

set CurOffset long 0
get FileSize asize
get FileName basename
string FileName + ".dec"

do
  goto CurOffset
  get DSize long
  get CSize long

  savepos CurOffset

  Append
  clog FileName CurOffset CSize DSize
  Append

  math CurOffset + CSize

while CurOffset < FileSize


CMD:
Code: Select allone file:
quickbms.exe Open_Season_lin.bms "H:\Open Season\System\Linear\pc\menu.lin" Export

or all files:
quickbms.exe -F "{}.lin" Open_Season_lin.bms "H:\Open Season\System\Linear\pc" Export


Note:
*.dec it's a dummy extension and holds bunch of files (depends on content it cold be: .ukx .usx etc.).
*.liv (Xbox) holds the names
Can you give support for the Xbox 360 files? That'd be great.
## Post #13
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-24T17:29:53+00:00
- Post Title: How to Extract Models from Open Season Video Game

thanks.
## Post #14
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T17:41:00+00:00
- Post Title: How to Extract Models from Open Season Video Game

Script for unpackng pcgame.umd

```
# Game: Open Season
# Unreal Engine 2 v927 pcgame.umd file
# script for QuickBMS http://quickbms.aluigi.org

goto -20
get Tag long
get InfoOffset long
get INFO_LIMIT long
get Version long
get CRC long

goto InfoOffset
get EntryCount VARIABLE2

for i = 0 < EntryCount
    get NAMESZ VARIABLE2
    getdstring NAME NAMESZ
    get Offset long
    get Size longlong
    get Flags long
    get CRC long

    if Offset != 0 && Offset != 1398326
        log NAME Offset Size
    endif
next i

```


CMD:

```

```


Have fun ...
## Post #15
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-24T17:52:21+00:00
- Post Title: How to Extract Models from Open Season Video Game

update me in the Future if there's More that are better.
Cause the UMD and LIN Decompiler was different.
## Post #16
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T18:00:53+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

added the .umd file from the PC and Xbox 360 versions respectively in the google drive links.
## Post #17
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T18:02:19+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

> Reply from tritterman ↑Mon Apr 25, 2022 1:52 am at Mon Apr 25, 2022 1:52 am
>
> 
update me in the Future if there's More that are better.
Cause the UMD and LIN Decompiler was different.

Dunno what you talkng about ...

> Reply from ShadowLuigi ↑Mon Apr 25, 2022 1:29 am at Mon Apr 25, 2022 1:29 am
>
> 
Can you give support for the Xbox 360 files? That'd be great.

Dunno what is the layout (where the files are) ... send some .lin and .liv pairs

> Reply from ShadowLuigi ↑Mon Apr 25, 2022 2:00 am at Mon Apr 25, 2022 2:00 am
>
> 
added the .umd file from the PC and Xbox 360 versions respectively in the google drive links.

No need ... Open_Season_umd.bms script should work on both plateformes
## Post #18
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T18:10:03+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

> Reply from VendorX ↑Mon Apr 25, 2022 1:41 am at Mon Apr 25, 2022 1:41 am
>
> 
Script for unpackng pcgame.umd
Code: Select all# Open_Season_umd.bms
# Game: Open Season
# Unreal Engine 2 v927 pcgame.umd file
# script for QuickBMS http://quickbms.aluigi.org

goto -20
get Tag long
get InfoOffset long
get INFO_LIMIT long
get Version long
get CRC long

goto InfoOffset
get EntryCount VARIABLE2

for i = 0 < EntryCount
    get NAMESZ VARIABLE2
    getdstring NAME NAMESZ
    get Offset long
    get Size longlong
    get Flags long
    get CRC long

    log NAME Offset Size
next i


CMD:
Code: Select allquickbms.exe Open_Season_umd.bms "H:\Open Season\System\pcgame.umd" Export


Have fun ...
Got this error when using the PC UMD script. 


Open Season PC UMD script error.PNG (33.62 KiB) Viewed 70 times
## Post #19
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T18:31:18+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

Also got this when using the script on xenon.umd from the Xbox 360 version. It gets to the static meshes and errors out. 


Open Season PC UMD script error Xbox 360.PNG (33.88 KiB) Viewed 69 times
## Post #20
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T18:53:55+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

I hate console ports ... crapy textures, small maps etc.

Apparently, 'Size = 0' means existing file and 'Size = 1398326' is in different package (.lin maybe).
Open_Season_umd.bms script is updated for PC verison.

Peeps: use PC version - no point of writing different scripts for the same game just because it's a different platform.
## Post #21
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-24T19:27:37+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

To save you some time, most unreal packages from umd files will be incomplete anyway, as they depend on external data (not only on lin, but also engine related stuff from binary) - unless someone is planning to serialize it as raw data. It's more like cache containers. Aside from that, I hardly doubt it will be supported in umodel, as it uses noticiably modified ubisoft version of UE, which is not supported for most similar games.
## Post #22
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T19:45:20+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

I know Unreal Engine ... let's say 'it pays my bills', also did some disassembling - anyway, I'm here to learn this 'exotic' scripting language quickbms is using ... don't care about this particular game.
## Post #23
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T19:46:48+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

> Reply from VendorX ↑Mon Apr 25, 2022 2:53 am at Mon Apr 25, 2022 2:53 am
>
> 
I hate console ports ... crapy textures, small maps etc.

Apparently, 'Size = 0' means existing file and 'Size = 1398326' is in different package (.lin maybe).
Open_Season_umd.bms script is updated for PC verison.

Peeps: use PC version - no point of writing different scripts for the same game just because it's a different platform.
Tried the new version of the script for the PC version and it does work perfectly fine. But I tried using it for the Xbox 360 and I just get this error. It'd be genuinely great if support for the definitive version of the game was made possible.


Open Season PC UMD script Xbox 360 Another Error.PNG (35.84 KiB) Viewed 57 times
## Post #24
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T20:16:26+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

send the file also some .lin and .liv pairs
## Post #25
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T20:20:31+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

> Reply from VendorX ↑Mon Apr 25, 2022 4:16 am at Mon Apr 25, 2022 4:16 am
>
> 
send the file also some .lin and .liv paes
You can always check back, hope this is okay.

> Reply from ShadowLuigi ↑Sun Apr 24, 2022 9:51 am at Sun Apr 24, 2022 9:51 am
>
> 
tritterman wrote: ↑Sun Apr 24, 2022 4:59 am
Can you show me the Xbox 360 Extract files?

Here's both common and menu in .lin and .liv respectively https://drive.google.com/drive/folders/ ... sp=sharing (Xbox 360)
## Post #26
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T20:34:55+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

Replace 1398326 with 1448230
## Post #27
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-24T20:41:59+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

> Reply from VendorX ↑Mon Apr 25, 2022 4:34 am at Mon Apr 25, 2022 4:34 am
>
> 
Replace 1398326 with 1448230
Thanks. works pretty well.
## Post #28
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-24T20:42:40+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

NP
## Post #29
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-25T00:03:47+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

maybe update the script even More?
## Post #30
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-25T00:07:27+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

like for every console?
## Post #31
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-25T08:52:10+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

Script below will split (by brute force) *.dec file in to proper UPackages - later I will write export raw data script from it.

```
# Game: Open Season
# Unreal Engine 2 v927 *.dec files
# script for QuickBMS http://quickbms.aluigi.org

set CurOffset long 0
get FileSize asize
get FileName basename

set FileCount long 0

do
  get B byte
  math CurOffset + 1
  if B == 0xc1
    get C byte
    math CurOffset + 1
    if C == 0x83
      get D byte
      math CurOffset + 1
      if D == 0x2a
        get E byte
        math CurOffset + 1
        if E == 0x9e
          xmath Offset "CurOffset - 4"
          print "%Offset%"
          putArray 0 FileCount Offset
          math FileCount + 1
        endif
      endif
    endif
  endif
  
  xmath NextOffset "CurOffset + 4"

while NextOffset < FileSize

print "%FileCount%"

for index = 0 < FileCount
  getArray Offset 0 index
  set NextOffset long FileSize
  xmath x "index + 1"
  
  if x < FileCount
    getArray NextOffset 0 x
  endif
  
  xmath Size "NextOffset - Offset"
  string TempName p= "%s_%i.%s" FileName index assets

  log TempName Offset Size
  
next index

```


CMD:

```

```

Note: *.assets is a dummy extension.
## Post #32
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-25T20:04:51+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

i don't get it.
## Post #33
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-26T13:31:51+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

Let me enlighten you: end effect of those three scripts is bunch of files which the game engine (UE2) is using. At this point unless you will write a decompiler (time consuming), there is no easy way to export UE content. 
OFC, you can open decompressed (.dec) file in some Hex editor and find all needed offsets, then guess 'what is what' and where belong to - good luck wth that ...- AND maybe in a few years you will finish what you are trying to achive.
Good luck.
## Post #34
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-04-26T13:45:48+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

well update me if there's a Solution then.
## Post #35
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-05-22T07:27:24+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

I'll share the files for the other versions including the PSP version at some point. don't know when tho
## Post #36
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-05-22T12:13:27+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

ok.
## Post #37
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-06-22T00:24:34+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

I'm trying to figure out which part in UModel can open Open Season Character and Extract to SFM.
## Post #38
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-06-22T00:26:30+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

i've tried everything.
## Post #39
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-06-22T00:44:34+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

Wait! i found some .ini files that can contain something.
Which script can i use to export ini files.
## Post #40
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-07-10T19:05:00+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

How's everybody doing?
## Post #41
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-07-10T23:59:29+00:00
- Post Title: Re: How to Extract Models from Open Season Video Game

it's not good. for me.
