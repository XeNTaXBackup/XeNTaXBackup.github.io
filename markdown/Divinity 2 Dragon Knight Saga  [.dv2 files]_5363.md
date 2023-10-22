## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-11-07T20:55:33+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

So, an improved version of Divinity 2 just came out, and the old unpacker and packer won't work with it.
Sadly, I don't know who made them, so I hope he/she'll read this.

New .dv2 file: [http://www32.zippyshare.com/v/48541898/file.html](http://www32.zippyshare.com/v/48541898/file.html)

Old .dv2 unpacker: [http://www32.zippyshare.com/v/81263589/file.html](http://www32.zippyshare.com/v/81263589/file.html)
Old .dv2 packer: [http://www32.zippyshare.com/v/91106099/file.html](http://www32.zippyshare.com/v/91106099/file.html)
Old xml to txt/ txt to xml converter: [http://www32.zippyshare.com/v/32655551/file.html](http://www32.zippyshare.com/v/32655551/file.html)
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-08T13:08:54+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

A quick help for unpacking: Take a look at my comment in the Divinity 2: Flames of Vengeance ( NEW .dv2 files !) topic:
[viewtopic.php?f=10&t=4839&hilit=divinity](http://forum.xentax.com/viewtopic.php?f=10&t=4839&hilit=divinity)
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-11-10T19:36:14+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Sadly the link does not work, so I can't download the BMS script.

And I also need progs for the xml to txt and vice versa converter and the repacking.

Thanks anyway, bacter:)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-11-11T01:40:04+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

for the bms script try with my secondary host (the primary has some problems lately):
[http://aluigi.altervista.org/papers/bms/divinity2.bms](http://aluigi.altervista.org/papers/bms/divinity2.bms)
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-13T19:59:20+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Thanks for the bms aluigi but the bms don't works with Divinity 2 Dragon Knight Saga

> Error: incomplete input file number 0, can't read 15826958 bytes.
>
>        anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted
I attach a file from this version:
[http://www.xup.in/dl,14867188/GFX.dv2/](http://www.xup.in/dl,14867188/GFX.dv2/)
## Post #6
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-14T05:20:19+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Did you modify the script, as I wrote earlier?
Put this two line to the beginning of the "divinity2.bms" script and it will (hopefully) work:

```
GET DUMMY long
```
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-14T07:35:02+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

You right bacter, now the bms works great with the data..
Thanks
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-14T11:03:09+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

I get "strangers" when unpacking the files: Textures.dv2 and Textures2.dv2 

> 02af8000 0          Win32\Textures\CA_bbnn_walls_high_A_DrkM.nif
>
> 488b0000 0          Win32\Textures\skillbutton_MagicBlast_pressed.nif
>
> 478c8000 0          Win32\Textures\TRA_CA2CTA_snsn_A_floor_DrkM.nif
>
> 46858000 0          Win32\Textures\SW_BBBn_ledge_B_arcs_DrkM.nif
>
> 465c8000 0          Win32\Textures\SW_BBBB_low_A_floor_DrkM.nif
>
> 26838000 0          Win32\Textures\M_Legs_NewOrder_T2B_NM.nif
>
> 1e3c8000 0          Win32\Textures\MNA_snsn_up_A_walls_DrkM.nif
>
> 1e0a8000 0          Win32\Textures\MNA_snnn_rocks_C_DrkM.nif
ThE extracted files are zero bytes size.
## Post #9
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-14T15:22:21+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Try this modified script:

```

# These two fields are not exist in the original Divinity2 .DV2 files:
GET DUMMY long  # (5)
GET DUMMY long # (1)

get VER long    # (4)
get ALIGN byte
get ZIP byte
if VER > 0x0000ffff
    endian big
endif
get BASE_OFF long
get NAME_SIZE long
savepos OFFSET
log MEMORY_FILE OFFSET NAME_SIZE
math OFFSET += NAME_SIZE
goto OFFSET
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get origSIZE long
    math OFFSET += BASE_OFF
    get NAME string MEMORY_FILE
    if origSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET SIZE origSIZE
    endif
next i

```
## Post #10
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-11-19T14:10:15+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

> Reply from bacter
>
> Try this modified script:
Code: Select all# QuickBMS script for Divinity 2 .DV2 files

# These two fields are not exist in the original Divinity2 .DV2 files:
GET DUMMY long  # (5)
GET DUMMY long # (1)

get VER long    # (4)
get ALIGN byte
get ZIP byte
if VER > 0x0000ffff
    endian big
endif
get BASE_OFF long
get NAME_SIZE long
savepos OFFSET
log MEMORY_FILE OFFSET NAME_SIZE
math OFFSET += NAME_SIZE
goto OFFSET
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get origSIZE long
    math OFFSET += BASE_OFF
    get NAME string MEMORY_FILE
    if origSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET SIZE origSIZE
    endif
next i

Works perfectly, thanks:) Luckily they did not change the contained .xml files structure, so the xml-txt converter works as well.
We only need a program, to repack the .dv2 files. Anyone, any ideas?
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-19T22:44:21+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Try this tool from Divinity II - Ego Draconis
[Divinity II - Ego Draconis Packer-Unpacker.rar](https://xentaxbackup.github.io/file/3621_Divinity II - Ego Draconis Packer-Unpacker.rar)
## Post #12
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-11-20T12:59:40+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

> Reply from Savage
>
> Try this tool from Divinity II - Ego Draconis

It's the same I linked in my first post.
## Post #13
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-20T13:42:45+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Here's the first, test version of my DV2 packer.
Updated! Now you can use this prog for .DV2 extraction too.
## Post #14
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-11-20T18:38:28+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

> Reply from bacter
>
> Here's the first, test version of my DV2 packer.

Thanks, I'll test it ASAP (tomorrow).
## Post #15
- Username: eddy0851
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 04, 2011 5:04 pm
- Post datetime: 2011-01-04T09:14:27+00:00
- Post Title: Divinity 2: Dragon Knight Saga  [.dv2 files]

Hi,

i'm french and i got a problem in divine divinity II, the text are SO small!!!

I saw that you were really endowed, would have you a solution I, please.

Sorry for my english.

THX!!
## Post #16
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-01-22T12:37:59+00:00
- Post Title: Re: Divinity 2: Dragon Knight Saga  [.dv2 files]

Thank you guy's. But I could not unpack this archive.
## Post #17
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2011-06-06T01:54:38+00:00
- Post Title: Re: Divinity 2: Dragon Knight Saga  [.dv2 files]

> Reply from bacter
>
> Here's the first, test version of my DV2 packer.
Updated! Now you can use this prog for .DV2 extraction too.
Extraction worked, however it does not give an error message when the destination directory does not exist - also, it might be a good idea to auto-create it (but that would require changing the parameter order to directory as the last so it can be optional).
Thank you!

PS. there is some funny business in the appearance of the command line window - a window in a window kind of anomaly - try extracting Patch.dv2 (Dragon Knight Saga 1.02) on Windows 7 Ultimate SP1 x64.

Now I just need to find out the "Gamebryo File Format, Version 20.3.0.9" for .XML and .KF...
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-06T05:43:49+00:00
- Post Title: Re: Divinity 2: Dragon Knight Saga  [.dv2 files]

can anyone reupload this tool pls : Old xml to txt/ txt to xml converter

that file is dead. Thx
## Post #19
- Username: go581
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 03, 2010 10:02 pm
- Post datetime: 2011-06-17T02:10:22+00:00
- Post Title: Re: Divinity 2: Dragon Knight Saga  [.dv2 files]

> Reply from michalss
>
> can anyone reupload this tool pls : Old xml to txt/ txt to xml converter

that file is dead. Thx

me too, thanks.
