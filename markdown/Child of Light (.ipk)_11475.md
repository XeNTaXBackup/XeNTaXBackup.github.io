## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-05-01T10:22:57+00:00
- Post Title: Child of Light (.ipk)

Child of Light uses UbiArt Framework engine (like Rayman Origins and Rayman Legends). Here is modified BMS for unpacking IPK archives. 

```
# Based on BMS script for Rayman Legends (PC / Xbox 360)
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x34	# 0x2c for Rayman Legends
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
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-02T18:22:17+00:00
- Post Title: Child of Light (.ipk)

> Reply from merlinsvk
>
> Child of Light uses UbiArt Framework engine (like Rayman Origins and Rayman Legends). Here is modified BMS for unpacking IPK archives. 
Code: Select all# Child of Light (PC / maybe Xbox 360 too)
# Based on BMS script for Rayman Legends (PC / Xbox 360)
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x34	# 0x2c for Rayman Legends
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

Thanks a lot. But it doesn't work for templateinstance_pc32.ipk file.
[K-40.png](https://xentaxbackup.github.io/file/7286_K-40.png)
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-05-02T19:51:08+00:00
- Post Title: Child of Light (.ipk)

I know. That file is probably dummy. It should have 3000+ files, but there are only few of them.
## Post #4
- Username: tomsolo
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Sep 17, 2011 3:33 am
- Post datetime: 2014-05-05T10:40:57+00:00
- Post Title: Child of Light (.ipk)

templateinstance_pc32.ipk its a dummy, descriptive/template file, no need to decompress.

If you want to run ChoL as extracted game, just decompress all other .ipk file*** - except templateinstance_pc32.ipk - in the game root. Rename / move these ipk files and voila game start.

If you want to make a translate, just open the localization_english.isg.ckd an hexeditor, and overwrite strings to what you want, but allways give the exact char numbers - a non ascii chars need two bytes.

The fonts it's a simple mapped DXT3 textures - see *tga* tag in filenames, just replace with photoshop to a non used char with your language specific character. 





*** Need good order, because some archives contain another dummy files too.
## Post #5
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-06T04:31:54+00:00
- Post Title: Child of Light (.ipk)

> Reply from tomsolo
>
> templateinstance_pc32.ipk its a dummy, descriptive/template file, no need to decompress.

If you want to run ChoL as extracted game, just decompress all other .ipk file*** - except templateinstance_pc32.ipk - in the game root. Rename / move these ipk files and voila game start.

If you want to make a translate, just open the localization_english.isg.ckd an hexeditor, and overwrite strings to what you want, but allways give the exact char numbers - a non ascii chars need two bytes.

The fonts it's a simple mapped DXT3 textures - see *tga* tag in filenames, just replace with photoshop to a non used char with your language specific character. 

*** Need good order, because some archives contain another dummy files too.

 No.. It is not easy to make a translation patch. Because no one can edit tfn.ckd files and work it on the game.
tfn.ckd file contains information(size and position..) about tga.ckd font file. I've tried to edit tfn.ckd file to exchange glyph's position but it won't work at all.
So it is impossible to make a one's own language font. Unicode number's are different from country. So I've tried to make a table file and edit font file..
But I was dropping with fatigue..
## Post #6
- Username: tomsolo
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Sep 17, 2011 3:33 am
- Post datetime: 2014-05-06T08:24:57+00:00
- Post Title: Child of Light (.ipk)

> Reply from albert1905
>
>  Because no one can edit tfn.ckd files and work it on the game. tfn.ckd file contains information(size and position..)

No, this is not true. I investigated templateinstance_pc32.ipk file and unfortunately yes it's contain some small files - like *tfn.ckd-s - but easily bypass: just replace all font's file path to something wrong in templateinstance_pc32.ipk file, like:

cache/itf_cooked/pc32/enginedata/misc/fonts/ 
to
cache/itf_cooked/pc32/enginedata/misc/font1/

Now engine use all *tfn.ckd files in the cache/itf_cooked/pc32/enginedata/misc/fonts/ folder.

The character encoding in localization file is UTF-8, but tfn.ckd use the UNICODE charmap.

I tried replace - avant_garde_md_32.tfn.ckd at 0x1FF0 -  in the the Latin small letter o with tilde - õ - to the Latin small letter o with double acute - ő - and success. (00F5 to 0151)

In example the "Downloadable" word in hungarian "Letölthető", and before this modification i wrote "Letölthetõ" in localization file and replace Latin small letter o with tilde's  bitmap to Latin small letter o with double acute texture.

I hope it's help for you but i know that hangul is more complicated.
## Post #7
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-06T15:10:39+00:00
- Post Title: Child of Light (.ipk)

> Reply from tomsolo
>
> albert1905 wrote: Because no one can edit tfn.ckd files and work it on the game. tfn.ckd file contains information(size and position..)

No, this is not true. I investigated templateinstance_pc32.ipk file and unfortunately yes it's contain some small files - like *tfn.ckd-s - but easily bypass: just replace all font's file path to something wrong in templateinstance_pc32.ipk file, like:

cache/itf_cooked/pc32/enginedata/misc/fonts/ 
to
cache/itf_cooked/pc32/enginedata/misc/font1/

Now engine use all *tfn.ckd files in the cache/itf_cooked/pc32/enginedata/misc/fonts/ folder.

The character encoding in localization file is UTF-8, but tfn.ckd use the UNICODE charmap.

I tried replace - avant_garde_md_32.tfn.ckd at 0x1FF0 -  in the the Latin small letter o with tilde - õ - to the Latin small letter o with double acute - ő - and success. (00F5 to 0151)

In example the "Downloadable" word in hungarian "Letölthető", and before this modification i wrote "Letölthetõ" in localization file and replace Latin small letter o with tilde's  bitmap to Latin small letter o with double acute texture.

I hope it's help for you but i know that hangul is more complicated.

Thanks a lot! It worked for me.
## Post #8
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-26T13:21:36+00:00
- Post Title: Child of Light (.ipk)

Is there a way to change Japanese voice to English voice?
## Post #9
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-21T01:33:35+00:00
- Post Title: Child of Light (.ipk)

> Reply from merlinsvk
>
> Child of Light uses UbiArt Framework engine (like Rayman Origins and Rayman Legends). Here is modified BMS for unpacking IPK archives. 
Code: Select all# Child of Light (PC / maybe Xbox 360 too)
# Based on BMS script for Rayman Legends (PC / Xbox 360)
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x34	# 0x2c for Rayman Legends
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

Can you modify BMS script for Valiant Hearts The Great War (*.ipk), too? Thanks in advance !
And here is my screenshot:
## Post #10
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-21T05:54:24+00:00
- Post Title: Child of Light (.ipk)

Here it is. [viewtopic.php?f=35&t=11715](http://forum.xentax.com/viewtopic.php?f=35&t=11715)
## Post #11
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-21T08:00:50+00:00
- Post Title: Child of Light (.ipk)

> Reply from albert1905
>
> Here it is. viewtopic.php?f=35&t=11715
Thanks! ^^
## Post #12
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-29T14:05:44+00:00
- Post Title: Child of Light (.ipk)

> Reply from albert1905
>
> Here it is. viewtopic.php?f=35&t=11715
Hi! In command dos, how to choose yes to skip bigger file ? Thanks !
## Post #13
- Username: Arts
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 18, 2014 10:35 pm
- Post datetime: 2014-10-18T14:47:42+00:00
- Post Title: Child of Light (.ipk)

Hi, 
i have problem with getting a file in format .dds

After extraction bootresourcemap_pc32.ipk in QuickBMS Editor with script

```
# Based on BMS script for Rayman Legends (PC / Xbox 360)
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x34   # 0x2c for Rayman Legends
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

I get the files in CKD format
using a script 

```
get NAME basename
get SIZE asize
math SIZE -= 0x38
string NAME += ".dds"
log NAME 0x38 SIZE

```

i get a file in DDS format - but this file i can not open with Photoshop+DDS plugin
when i try to open DDS file - getting an error 
"could not complete your request because file-format module cannot parse the file"

What am I doing wrong??
Please help...and sory for my bad english..
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-10-18T20:21:04+00:00
- Post Title: Child of Light (.ipk)

Are you trying to convert .tga.ckd file? Because there are many other files with .ckd extension.
## Post #15
- Username: Arts
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 18, 2014 10:35 pm
- Post datetime: 2014-10-18T21:45:03+00:00
- Post Title: Child of Light (.ipk)

From here i got a script for converting .ckd to DDS
[viewtopic.php?f=35&t=11715](http://forum.xentax.com/viewtopic.php?f=35&t=11715)
last post say about script working correctly with Valiant Hearts The Great War

if this script work with files from game Valiant Hearts - why it don't work with files from game Child of Light??? 

Is there any other way to converting CKD files to DDS correctly from Child of Light??
## Post #16
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-10-19T10:53:58+00:00
- Post Title: Re: Child of Light (.ipk)

Textures in Valiant Hearts have a bit different structure.

Use this script:

```
get SIZE asize
math SIZE -= 0x34
string NAME += ".dds"
log NAME 0x34 SIZE

```
## Post #17
- Username: Arts
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 18, 2014 10:35 pm
- Post datetime: 2014-10-19T11:34:12+00:00
- Post Title: Re: Child of Light (.ipk)

You are genius man...thanks thanks thanks...
## Post #18
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-11-14T07:54:32+00:00
- Post Title: Re: Child of Light (.ipk)

Hi! I founded font file image in another *.ipk and avant_garde_md_32_outline.tfn.ckd in templateinstance_pc32.ipk by childoflight quickbms script! But with templateinstance_pc32.ipk, maybe have diffirent structer? I can not upack this file. Please help me unpack avant_garde_md_32_outline.tfn.ckd. I needing that file to make font. Thanks for any help! Here is sample and script: [https://mega.co.nz/#!4RwTVQ4b!K0rmVsS5W ... lD4r3wJ9Og](https://mega.co.nz/#!4RwTVQ4b!K0rmVsS5WIisUv-0gWhzCkOaxZYtt43IKlD4r3wJ9Og)


templateinstance_pc32.ipk in hex

Only need unpack avant_garde_md_32_outline.tfn.ckd for edit! Thanks! Sorry for my bad English!
## Post #19
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-14T08:07:37+00:00
- Post Title: Re: Child of Light (.ipk)

Find that font in different .ipk, and edit templateinstance_pc32.ipk like tomsolo wrote on previous page.
## Post #20
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-11-14T13:12:30+00:00
- Post Title: Re: Child of Light (.ipk)

> Reply from merlinsvk
>
> Find that font in different .ipk, and edit templateinstance_pc32.ipk like tomsolo wrote on previous page.

Thanks. But i search for all, there is not that file. This for online font.
