## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-21T05:52:27+00:00
- Post Title: Valiant Hearts The Great War BMS script

Here it is. Valiant Hearts The Great War BMS script.

```
# Based on BMS script for Child of Light
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x38   # 0x2c for Rayman Legends
get FILES long
for i = 0 < FILES
    get DUMMY1 long
    get SIZE long
    get ZSIZE long
    get TSTAMP longlong
    get OFFSET longlong
    if DUMMY1 == 2
        get DUMMY4 long
        get DUMMY5 long
    endif
    get FOLDERSZ long
   getdstring FOLDER FOLDERSZ
   get NAMESZ long
   getdstring NAME NAMESZ
   string FOLDER + NAME
   string NAME = FOLDER
    math OFFSET += BASE_OFF
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
   get DUMMY6 long
   get DUMMY7 long
next i
```
## Post #2
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-21T08:24:11+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from albert1905
>
> Here it is. Valiant Hearts The Great War BMS script.
Code: Select all# Valiant Hearts The Great War PC
# Based on BMS script for Child of Light
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x38   # 0x2c for Rayman Legends
get FILES long
for i = 0 < FILES
    get DUMMY1 long
    get SIZE long
    get ZSIZE long
    get TSTAMP longlong
    get OFFSET longlong
    if DUMMY1 == 2
        get DUMMY4 long
        get DUMMY5 long
    endif
    get FOLDERSZ long
   getdstring FOLDER FOLDERSZ
   get NAMESZ long
   getdstring NAME NAMESZ
   string FOLDER + NAME
   string NAME = FOLDER
    math OFFSET += BASE_OFF
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
   get DUMMY6 long
   get DUMMY7 long
next i

Do you know where is text located ? Thanks !
## Post #3
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-21T09:25:49+00:00
- Post Title: Valiant Hearts The Great War BMS script

localisation.loc8 contains all of the language scripts of Valiant Hearts.

Work with rayman tool(made by swuforce).

How to usage

1) export localisation.loc8 to text files.
2) choose the one tex(one language) and edit it
3) import that one text file to *.loc8 files.

For example, use rayman tool(made by swuforce) to export text from localisation.loc8. And edit 'RaymanLegendsText_0'(English). After that, use import and select 'RaymanLegendsText_0' and then select 'localisation.loc8'. Then you can get NEW_localisation.loc8. Rename it to localisation.loc8 and check it on the game.

 You can find font data at C:\Program Files (x86)\Valiant Hearts The Great War\Bundle_unpack\cache\itf_cooked\pc\enginedata\misc\fonts and child of light template(made by tomsolo) also work with Valiant Hearts. So you can edit the font mapping data by 010 editor with that template.

For the '*.tga.ckd', just delete header(0x38h) and rename it to dds. Then you can edit it on the photoshop.
## Post #4
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-07-21T10:17:20+00:00
- Post Title: Valiant Hearts The Great War BMS script

Did you just rename my tool, upload again(original still available), and post it here?
## Post #5
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-21T10:26:30+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from swuforce
>
> Did you just rename my tool, upload again(original still available), and post it here? If you upset it, I'm sorry for that. But I post it here because namquang93 asking how to adjust merlinsvk's bms script to valiant hearts. [viewtopic.php?f=10&t=11475](http://forum.xentax.com/viewtopic.php?f=10&t=11475).
So, I just give he or she the information about it. I mentioned the author of template but don't know the writer of rayman tools so I just post it without your nickname. I just grab the tool, template and show namquang93 how to localizing it, instead of link, for the simplest information.
## Post #6
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-21T11:13:07+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from swuforce
>
> Did you just rename my tool, upload again(original still available), and post it here?

> Reply from albert1905
>
> swuforce wrote:Did you just rename my tool, upload again(original still available), and post it here? If you upset it, I'm sorry for that. But I post it here because namquang93 asking how to adjust merlinsvk's bms script to valiant hearts. viewtopic.php?f=10&t=11475.
So, I just give he or she the information about it. I mentioned the author of template but don't know the writer of rayman tools so I just post it without your nickname. I just grab the tool, template and show namquang93 how to localizing it, instead of link, for the simplest information.

Sorry for that! Beacause of my asking! And thanks swuforce with albert1905.
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-07-21T17:36:08+00:00
- Post Title: Valiant Hearts The Great War BMS script

loc8 tool here: [viewtopic.php?f=10&t=11295](http://forum.xentax.com/viewtopic.php?f=10&t=11295)
localization and font templates by tomsolo here: [viewtopic.php?f=35&t=11494&p=94481](http://forum.xentax.com/viewtopic.php?f=35&t=11494&p=94481)
This is the simplest way...

Then you can write your detailed information about usage, if you want.
## Post #8
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-22T03:12:21+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from swuforce
>
> loc8 tool here: viewtopic.php?f=10&t=11295
localization and font templates by tomsolo here: viewtopic.php?f=35&t=11494&p=94481
This is the simplest way...

Then you can write your detailed information about usage, if you want.

Thanks!
## Post #9
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2014-07-27T07:26:15+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from swuforce
>
> loc8 tool here: viewtopic.php?f=10&t=11295
localization and font templates by tomsolo here: viewtopic.php?f=35&t=11494&p=94481
This is the simplest way...

Then you can write your detailed information about usage, if you want.

Unlike CoL, Valiant Hearts got no templateinstance_pc32.ipk file for the bypass trick by tomsolo. Does it meant either we have to Patch the .exe for using the modified font in the root or worse - extracted the whole Bundle_PC.ipk? Anybody have a solution here? Also is it possible to repack the ipk in the first place?

EDIT: Try repack using quickbms, but not working...
## Post #10
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-09-25T15:42:09+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from albert1905
>
> For the '*.tga.ckd', just delete header(0x38h) and rename it to dds. Then you can edit it on the photoshop.

Hi, i want some help with these files.

there are a lot of ".tga.ckd". I want convert all of them to dds. is there any program or bms script to do this?

sorry for my bad english.
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-25T18:01:57+00:00
- Post Title: Valiant Hearts The Great War BMS script

```
# Valiant Hearts

get NAME basename
get SIZE asize
math SIZE -= 0x38
string NAME += ".dds"
log NAME 0x38 SIZE
```
## Post #12
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-09-27T11:34:18+00:00
- Post Title: Valiant Hearts The Great War BMS script

> Reply from merlinsvk
>
> Code: Select all# .tga.ckd to .dds
# Valiant Hearts

get NAME basename
get SIZE asize
math SIZE -= 0x38
string NAME += ".dds"
log NAME 0x38 SIZE
 Thanks, man
