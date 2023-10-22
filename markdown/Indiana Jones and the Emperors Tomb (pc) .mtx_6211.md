## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-13T03:47:53+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

I can not understand how to unpack this mulitex container, can anyone help me? [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/indiana-jones-atet/indy-and-emperors-tomb-pc-textures.7z)

Also here i started [thread for models](http://forum.xentax.com/viewtopic.php?f=16&t=6212).
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-13T13:57:58+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

rough start. i can't identify the data, but there are minimaps, so possibily dds? i'll get back to you if i get any further   

edit: see below post

also, its amazing how old this game is - 2003 and no community behind it?!
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-13T15:08:40+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

eah, game is very good  it have a community, but all community's steps ends in 2006. Nobody can't proceed the modding of this game because of complicate formats.

p.s.: don't know how to work with script, it can't find anything in *.mtx
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-13T16:49:59+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

i'm failing to identify the dds format, so here's an updated script with dumps with DTX3. its a lot of trial and error on my side (i'm not good with graphics   )

the nvidia thumbnail viewer is showing recognizable previews though, so ITS CLOSE

edit: see updated script below (again!)
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-13T16:59:18+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

> Reply from WRS
>
> i'm failing to identify the dds format, so here's an updated script with dumps with DTX3. its a lot of trial and error on my side (i'm not good with graphics   )

the nvidia thumbnail viewer is showing recognizable previews though, so ITS CLOSE
thanks for help WRS, it works  

p.s.: but it will looks better without mipmaps
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-13T18:59:13+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

now DXT1    
got there eventually! headers may not be correct though


```
# quickbms script by WRS, xentax.com

idstring "MULTITEX"
get SIX short
get TWO short
get ONE long
get ZERO long

get TEXCOUNT long
get TEXHEADSIZE long
get TWFOUR long      # head size
get TEXHEADSIZE long # 128

get FNAME basename

for t = 0 < TEXCOUNT
  get INDEX long
   getdstring UNKNOWN 16
   get UNKNOWN short     # 256/ flags?
   get UNKNOWN short
  getdstring TEXNAME1 32
  getdstring TEXNAME2 32 # not 64 because of repeated data
  get TWIDTH long
  get THEIGHT long
   get UNKNOWN long
  get BPP long
   get UNKNOWN long
  get MINIMAPS long
   get UNKNOWN long
   get UNKNOWN long
  get TEXPOS long
  get TEXTSIZE long

  # POS is a pointer to minimap info

  savepos POS
  goto TEXPOS

  # write 128-byte dds header
  log MEMORY_FILE 0 0
  putvarchr MEMORY_FILE 127 0

  # setup dds header

  putvarchr MEMORY_FILE 0 0x20534444 long  #dwMagic (DDS )
  putvarchr MEMORY_FILE 4 0x7C long        #dwSize (128)
  putvarchr MEMORY_FILE 8 0x21007 long     #dwFlags (prob. wrong)

  putvarchr MEMORY_FILE 12 THEIGHT long    #dwHeight
  putvarchr MEMORY_FILE 16 TWIDTH long     #dwWidth
  putvarchr MEMORY_FILE 28 MINIMAPS long   #dwMiniMapCount

  putvarchr MEMORY_FILE 76 32 long         #dwSize
  putvarchr MEMORY_FILE 80 4 long          #dwFlags
  putvarchr MEMORY_FILE 84 0x31545844 long #dwFourCC (DXT1)

  putvarchr MEMORY_FILE 108 4198408 long   #dwCaps1

  append
  for i = 0 < MINIMAPS
    get DATASIZE long  # minimap size
    savepos POS2
    log MEMORY_FILE POS2 DATASIZE  # save minimap
    math POS2 += DATASIZE
    goto POS2
  next i
  append

  get DSIZE asize MEMORY_FILE
  string FILENAME p= "%s/%s.dds" FNAME TEXNAME1
  log FILENAME 0 DSIZE MEMORY_FILE

  goto POS
next t

```

[c_ij_txr_head.jpg](https://xentaxbackup.github.io/file/4064_c_ij_txr_head.jpg)
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-14T01:18:21+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

> Reply from WRS
>
> now DXT1    
got there eventually! headers may not be correct though
ohhh, thank youuu))), works great
## Post #8
- Username: CaptainJack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2011 12:56 pm
- Post datetime: 2011-04-30T12:39:16+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

Hello! I am very new to multiex commander 4.5 and scripting in general, so please forgive my ignorance.

I tried to run the script (so kindly supplied above) on the same Indy.mtx file and I receive a message saying: "Error: QBMS Failed to Produce List". I am just straight copy and pasting the script into the scriptor window  from this thread, changing to Quickbms, and selecting "Use On" and then selecting the mtx file in question. Should I be adding or taking away anything from the script to get it to run for me? Or is there possibly something else that is super obvious that I am overlooking?

Again, apologies for ignorance,

Thanks kind people! 

CJ

EDIT: Okay, I figured out that you guys are using the latest version of quickbms that I didn't have, so that's where I was going wrong. So extraction is now working perfectly for me. Still not having any luck reimporting adjusted textures though (despite the program telling me my reimporting process was successful).
## Post #9
- Username: CaptainJack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2011 12:56 pm
- Post datetime: 2011-05-04T00:51:10+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

WRS, I think I am in need of your assistance 

I am having no luck with reimporting edited textures into the original archive (I understand the program cannot work for every single filetype under the sun). I am assuming that the mtx file is just too complex for quickbms to have success on its own, and possibly a script for reinjection is required. I do not know the first thing about scripting so my journey of trying to edit the Emperors Tomb appears to be at an end. If anyone had a chance to give it a go I would be incredibly grateful!!!

Here is a screenshot of my allegedly successful results:




And yet, when I open the archive again, the original file is restored and no changes have been made. Frustration sets in due to my excitement being dashed and I go have another coffee... Cheers to anyone who can offer insightful suggestion or practical help, it would be really appreciated
## Post #10
- Username: CaptainJack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2011 12:56 pm
- Post datetime: 2012-04-12T05:01:50+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

I figured it wouldn't hurt to express my plea for help one last time before I give up on this. I'm super keen to mod the graphics of this old 2003 game that still delivers the most enjoyable action centric Indiana Jones experience on PC.

To reiterate, thanks to the script already posted it is now possibly to open the .MTX file type but not to repack that .MTX file, and I imagine a new script for re-injection is required (of which I have absolutely zero idea how to accomplish). Help would be totally appreciated.

Cheers,
CJ
## Post #11
- Username: CaptainJack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2011 12:56 pm
- Post datetime: 2014-11-05T03:44:01+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

Hi all, just bumping this one last time (couple years later), to see if anyone could help with a script to repack an mtx file
## Post #12
- Username: fisherathletic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 09, 2017 6:12 am
- Post datetime: 2017-10-09T23:02:25+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

Bumping sorry

Did this get anywhere im trying to learn how to do it myself , when trying to reimport all i get is this. Even after almost 15 years im trying to find a way to mod this game. thanks
[reimport problem.jpg](https://xentaxbackup.github.io/file/13424_reimport problem.jpg)
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-10T16:20:24+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

i'd like to see some of these mtx samples
## Post #14
- Username: fisherathletic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 09, 2017 6:12 am
- Post datetime: 2017-10-11T15:41:00+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

> Reply from AceWell
>
> i'd like to see some of these mtx samples

big thanks for replying and just having a look

here are some   

[https://sabercathost.com/52fz/NaziSoldier.mtx](https://sabercathost.com/52fz/NaziSoldier.mtx)

[https://sabercathost.com/52fx/nazi_jacket.dds](https://sabercathost.com/52fx/nazi_jacket.dds)

[https://sabercathost.com/52fy/nazi_jacket_(2).dds](https://sabercathost.com/52fy/nazi_jacket_%282%29.dds)

the .mtx holds these files .dds these can be edited with paint.net i haven't tried photoshop yet 
 or just to view them WTV dds file viewer can be used

ive attached a picture of what the folder should look like once unpacked using the script above for quickbms by WRS , the problem is finding a way to pack them back into mtx  , i understand the files need to be of equal size or smaller , but im not script writer so its abit out of my league.
[nazi soldier contents.jpg](https://xentaxbackup.github.io/file/13428_nazi soldier contents.jpg)
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-12T18:16:55+00:00
- Post Title: Indiana Jones and the Emperors Tomb (pc) *.mtx

well i don't know much about game modding, thats not my area, but i'd say if you want to reimport the data as it was stored
originally you will need to strip the 128 byte header from the modified dds file and maybe remove the extension before trying it.   
also if you can provide more mtx samples that would be great, i can't compare data with just one.  

edit
just tried reimporting with Quickbms and the script hangs on memory_file stuff, and i believe aluigi said reimporting 
doesn't work with those commands anyway, so the script may need to be reworked to get around that stuff.
## Post #16
- Username: fisherathletic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 09, 2017 6:12 am
- Post datetime: 2017-10-13T00:35:39+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

[https://sabercathost.com/9euU/Indy_MTX_files.rar](https://sabercathost.com/9euU/Indy_MTX_files.rar)

here are some more ,  Don't know if its worth adding but here are some edited textures if anyone is interested at just looking we didn't go into too much detail to keep the memory low . um i would have no idea how to write script i only just came across this forum about 4 or 5 days ago. thanks. 
[example files.jpg](https://xentaxbackup.github.io/file/13432_example files.jpg)
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-13T17:14:36+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

okay here i modified the original QuickBMS script for reimport and it seems to work  


 IndianaJonesandtheEmperorsTomb_PC_mtx_reimport.zip
(640 Bytes) Downloaded 55 times



use the original script by WRS to extract textures with headers etc,
modify the texture in your favorite image editing software and resave with mipmaps,
open the saved dds file and delete first 128 bytes and remove the dds extension too,
start the reimport process as instructed by aluigi and use this modified script.
## Post #18
- Username: fisherathletic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 09, 2017 6:12 am
- Post datetime: 2017-10-14T10:56:06+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

> Reply from AceWell
>
> okay here i modified the original QuickBMS script for reimport and it seems to work  
IndianaJonesandtheEmperorsTomb_PC_mtx_reimport.zip

use the original script by WRS to extract textures with headers etc,
modify the texture in your favorite image editing software and resave with mipmaps,
open the saved dds file and delete first 128 bytes and remove the dds extension too,
start the reimport process as instructed by aluigi and use this modified script.

thanks sorry for taking so long to reply was out last night , how do i remove the first 128 bites and remove the dds im abit confused about this your working with a monkey sorry im pretty useless but i really cant thank you enough for this
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-14T18:51:08+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

just run this bms script on your modified dds file  

```

get NAME basename
get SIZE asize
math SIZE - 0x80
log NAME 0x80 SIZE
```
## Post #20
- Username: fisherathletic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 09, 2017 6:12 am
- Post datetime: 2017-10-14T22:01:47+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

WOW !!! youve done it you achieved what me and small community would never have thought been possible years ago , thank you sir , thank you    
[success.jpg](https://xentaxbackup.github.io/file/13445_success.jpg)
## Post #21
- Username: CaptainJack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 08, 2011 12:56 pm
- Post datetime: 2018-01-30T05:28:50+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

> Reply from fisherathletic
>
> WOW !!! youve done it you achieved what me and small community would never have thought been possible years ago , thank you sir , thank you

Hi Acewell and Fisherathletic! This is absolutely incredible that you have cracked the code and made this possible! Holy Smokes!

After attempting and failing years ago, you legends combined with WRS original work, have done the impossible! I have no idea why I stumbled back into this old thread but am ecstatic that I did  I'd well and truly given up any and all hope of modding IJET years ago, but you have done it!!

Finally the greatest Indiana Jones action game yet released has a chance to be updated, enhanced and graphically tweaked. A million thanks guys! When I get a chance to sink some time into this, I'll update with creations.

Again, many many thanks you champions!

CJ
## Post #22
- Username: medievil
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 26, 2018 11:03 am
- Post datetime: 2018-04-28T18:45:00+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

I must be missing something...I have a whole bunch of dds files ripped from an MTX, the script will not recreate the MTX though.. tried all the various instructions... just get the signature does match (Expected MULTITEX)...
I am working on converting the xbox version of Buffy the vampire slayer to PC (using the indy slayer engine) and thought the reimporter would recreate the Multitex file (since it wouldn't know if any file was altered)
***EDIT***
ok I understand, it only adds them back over itself in the existing multitex file, not good for creating new MTX files then :\
## Post #23
- Username: medievil
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 26, 2018 11:03 am
- Post datetime: 2018-04-30T16:16:14+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

modified WRS original mtx code, it didn't take into account texture format (dxt1 or 5)

```
# quickbms script by WRS, xentax.com
#Modified by Medievil to add DXT compression method

idstring "MULTITEX"
get SIX short
get TWO short
get ONE long
get ZERO long

get TEXCOUNT long
get TEXHEADSIZE long
get TWFOUR long      # head size
get TEXHEADSIZE long # 128

get FNAME basename

for t = 0 < TEXCOUNT
  get INDEX long
   getdstring UNKNOWN 16
   get UNKNOWN short     # 256/ flags?
   get UNKNOWN short
  getdstring TEXNAME1 32
  getdstring TEXNAME2 32 # not 64 because of repeated data
  get TWIDTH long
  get THEIGHT long
   get UNKNOWN long
  get BPP long
   get UNKNOWN long
  get MINIMAPS long
   get UNKNOWN long
   get DXT BYTE
 get UNKNOWN THREEByte
  get TEXPOS long
  get TEXTSIZE long
next t
  # POS is a pointer to minimap info

  savepos POS
  goto TEXPOS

  # write 128-byte dds header
  log MEMORY_FILE 0 0
  putvarchr MEMORY_FILE 127 0

  # setup dds header
 math DXT += 0x30
  putvarchr MEMORY_FILE 0 0x20534444 long  #dwMagic (DDS )
  putvarchr MEMORY_FILE 4 0x7C long        #dwSize (128)
  putvarchr MEMORY_FILE 8 0x21007 long     #dwFlags (prob. wrong)

  putvarchr MEMORY_FILE 12 THEIGHT long    #dwHeight
  putvarchr MEMORY_FILE 16 TWIDTH long     #dwWidth
  putvarchr MEMORY_FILE 28 MINIMAPS long   #dwMiniMapCount

  putvarchr MEMORY_FILE 76 32 long         #dwSize
  putvarchr MEMORY_FILE 80 4 long          #dwFlags
  putvarchr MEMORY_FILE 84 0x00545844 long #dwFourCC 
  putvarchr MEMORY_FILE 87 Dxt byte (DXT1 or 5 depending on byte read)
  putvarchr MEMORY_FILE 108 4198408 long   #dwCaps1

  append
  for i = 0 < MINIMAPS
    get DATASIZE long  # minimap size
    savepos POS2
    log MEMORY_FILE POS2 DATASIZE  # save minimap
    math POS2 += DATASIZE
    goto POS2
  next i
  append

  get DSIZE asize MEMORY_FILE
  string FILENAME p= "%s/%s.dds" FNAME TEXNAME1
  log FILENAME 0 DSIZE MEMORY_FILE

  goto POS
next t
```
## Post #24
- Username: icup321
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 26, 2020 10:54 am
- Post datetime: 2022-03-12T09:22:33+00:00
- Post Title: Re: Indiana Jones and the Emperors Tomb (pc) *.mtx

> Reply from medievil ↑Tue May 01, 2018 12:16 am at Tue May 01, 2018 12:16 am
>
> 
modified WRS original mtx code, it didn't take into account texture format (dxt1 or 5)
Code: Select all# IJET *.mtx (multi texture format)
# quickbms script by WRS, xentax.com
#Modified by Medievil to add DXT compression method

idstring "MULTITEX"
get SIX short
get TWO short
get ONE long
get ZERO long

get TEXCOUNT long
get TEXHEADSIZE long
get TWFOUR long      # head size
get TEXHEADSIZE long # 128

get FNAME basename

for t = 0 < TEXCOUNT
  get INDEX long
   getdstring UNKNOWN 16
   get UNKNOWN short     # 256/ flags?
   get UNKNOWN short
  getdstring TEXNAME1 32
  getdstring TEXNAME2 32 # not 64 because of repeated data
  get TWIDTH long
  get THEIGHT long
   get UNKNOWN long
  get BPP long
   get UNKNOWN long
  get MINIMAPS long
   get UNKNOWN long
   get DXT BYTE
 get UNKNOWN THREEByte
  get TEXPOS long
  get TEXTSIZE long
next t
  # POS is a pointer to minimap info

  savepos POS
  goto TEXPOS

  # write 128-byte dds header
  log MEMORY_FILE 0 0
  putvarchr MEMORY_FILE 127 0

  # setup dds header
 math DXT += 0x30
  putvarchr MEMORY_FILE 0 0x20534444 long  #dwMagic (DDS )
  putvarchr MEMORY_FILE 4 0x7C long        #dwSize (128)
  putvarchr MEMORY_FILE 8 0x21007 long     #dwFlags (prob. wrong)

  putvarchr MEMORY_FILE 12 THEIGHT long    #dwHeight
  putvarchr MEMORY_FILE 16 TWIDTH long     #dwWidth
  putvarchr MEMORY_FILE 28 MINIMAPS long   #dwMiniMapCount

  putvarchr MEMORY_FILE 76 32 long         #dwSize
  putvarchr MEMORY_FILE 80 4 long          #dwFlags
  putvarchr MEMORY_FILE 84 0x00545844 long #dwFourCC 
  putvarchr MEMORY_FILE 87 Dxt byte (DXT1 or 5 depending on byte read)
  putvarchr MEMORY_FILE 108 4198408 long   #dwCaps1

  append
  for i = 0 < MINIMAPS
    get DATASIZE long  # minimap size
    savepos POS2
    log MEMORY_FILE POS2 DATASIZE  # save minimap
    math POS2 += DATASIZE
    goto POS2
  next i
  append

  get DSIZE asize MEMORY_FILE
  string FILENAME p= "%s/%s.dds" FNAME TEXNAME1
  log FILENAME 0 DSIZE MEMORY_FILE

  goto POS
next t

Sorry for necroposting, but I feel that I should point out that this updated script was broken by default, but I managed to fix it myself:

```
# quickbms script by WRS, xentax.com

idstring "MULTITEX"
get SIX short
get TWO short
get ONE long
get ZERO long

get TEXCOUNT long
get TEXHEADSIZE long
get TWFOUR long      # head size
get TEXHEADSIZE long # 128

get FNAME basename

for t = 0 < TEXCOUNT
  get INDEX long
   getdstring UNKNOWN 16
   get UNKNOWN short     # 256/ flags?
   get UNKNOWN short
  getdstring TEXNAME1 32
  getdstring TEXNAME2 32 # not 64 because of repeated data
  get TWIDTH long
  get THEIGHT long
   get UNKNOWN long
  get BPP long
   get UNKNOWN long
  get MINIMAPS long
   get UNKNOWN long
   get DXT BYTE
   get UNKNOWN THREEByte
  get TEXPOS long
  get TEXTSIZE long

  # POS is a pointer to minimap info

  savepos POS
  goto TEXPOS

  # write 128-byte dds header
  log MEMORY_FILE 0 0
  putvarchr MEMORY_FILE 127 0

  # setup dds header
  math DXT += 0x30
  putvarchr MEMORY_FILE 0 0x20534444 long  #dwMagic (DDS )
  putvarchr MEMORY_FILE 4 0x7C long        #dwSize (128)
  putvarchr MEMORY_FILE 8 0x21007 long     #dwFlags (prob. wrong)

  putvarchr MEMORY_FILE 12 THEIGHT long    #dwHeight
  putvarchr MEMORY_FILE 16 TWIDTH long     #dwWidth
  putvarchr MEMORY_FILE 28 MINIMAPS long   #dwMiniMapCount

  putvarchr MEMORY_FILE 76 32 long         #dwSize
  putvarchr MEMORY_FILE 80 4 long          #dwFlags
  putvarchr MEMORY_FILE 84 0x00545844 long #dwFourCC 
  putvarchr MEMORY_FILE 87 DXT byte (DXT1 or 5 depending on byte read)
  putvarchr MEMORY_FILE 108 4198408 long   #dwCaps1

  append
  for i = 0 < MINIMAPS
    get DATASIZE long  # minimap size
    savepos POS2
    log MEMORY_FILE POS2 DATASIZE  # save minimap
    math POS2 += DATASIZE
    goto POS2
  next i
  append

  get DSIZE asize MEMORY_FILE
  string FILENAME p= "%s/%s.dds" FNAME TEXNAME1
  log FILENAME 0 DSIZE MEMORY_FILE

  goto POS
next t
```
