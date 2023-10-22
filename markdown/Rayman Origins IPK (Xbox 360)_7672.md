## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-11T12:03:47+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

Hey there,

Can I ask for your help in extracting the IPK bigfile from the newly-released Rayman Origins demo? The final gam uses IPK files as well so it would be great if we could extract them as soon as possible.
I uploaded it here: [http://www.multiupload.com/LKPDY6P2D6](http://www.multiupload.com/LKPDY6P2D6)
It seems easy to do, as the files are uncompressed and there's clearly a filetable in the header of the file.
Sadly, I'm really bad at extracting information from a filetable myself. :/
It would be awesome if anyone managed to do this - as we would be able to extract the artwork (png I think), music&sounds (xma), etc with their proper filenames.

Thanks in advance!
Droolie.

EDIT -> Added two much smaller IPK files for you to look at - 5 and 4 MB.
[http://www.box.net/s/9v8xobi0hcu7b5czaojr](http://www.box.net/s/9v8xobi0hcu7b5czaojr)
[http://www.box.net/s/28lrki2rcq0fubi4slgr](http://www.box.net/s/28lrki2rcq0fubi4slgr)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-13T01:57:15+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

I am interested too, I had no luck myself extracting the files. Maybe someone with more experience can?
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-13T13:08:38+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

The game is out in less-legal ways now. I have it and they use a lot of the same IPK archives. Hurry! 
I already got the music out of the demo but it was a pain. Rayman Origins' music is split into multiple segments, and joining those segments after extracting them without any filenames (I didn't manage to extract the archive correctly) is a real pain.
I would also definitely like to see all the sprites - they're just saved as PNG files from the looks of it...

EDIT -> It's even worse than I first thought. The files aren't sorted correctly in the IPK archives, which means the segments are in the wrong order. And there are almost over 9000 of them. I can never rip this mess if I can't extract the IPK files correctly...

EDIT 2 -> Added two much smaller IPK files for you to look at - 5 and 4 MB.
[http://www.box.net/s/9v8xobi0hcu7b5czaojr](http://www.box.net/s/9v8xobi0hcu7b5czaojr)
[http://www.box.net/s/28lrki2rcq0fubi4slgr](http://www.box.net/s/28lrki2rcq0fubi4slgr)

EDIT 3 -> Found out more about the files. The four bytes starting at 0000000C specify the length of the first part of the header.
That header starts with 50EC12BA.
Then, after 19 bytes, the second part begins, showing how and where all the files should be put when extracted.
The first byte shows the length of the following string (I'll call that the "length byte"). The next few bytes contain the string, with the length specified in the previous byte. If this string contained a folder name, then 3 "00" bytes follow, then the length byte of a file to be put in that folder, then the filename. After the filename, there are 4 bytes specifying something I don't know. After that, 3 bytes of "00" and repeat. Please, can anyone help me with this?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-14T16:29:23+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

job done:
[http://aluigi.org/papers/bms/rayman_origins.bms](http://aluigi.org/papers/bms/rayman_origins.bms)
## Post #5
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-14T18:25:46+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

> Reply from aluigi
>
> job done:
http://aluigi.org/papers/bms/rayman_origins.bms
Wow! Thanks a lot for this! You're a hero! 
At first it didn't work for me but I was using an old version of QuickBMS. I updated it and now it works. Thanks again!
## Post #6
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2011-11-15T21:44:26+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

Without trying to sound like a complete moron, how would I go about converting or decompressing the .ckd files? They all appear the be "something.actualextention.ckd" - like "bossbird.png.ckd"

I'm sure I'm being an idiot...
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-17T23:34:44+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

the ckd files that were posted in another thread were just raw dds files:
[viewtopic.php?f=21&t=7690](http://forum.xentax.com/viewtopic.php?f=21&t=7690)
## Post #8
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-02T21:49:40+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

Aluigi, thanks again for the script. There's something weird though: in all the versions (Wii/Xbox/PS3) there is one IPK file that isn't extracted correctly: bootsequence_[platform].ipk. Any idea how it can be fixed?
Here's the one from the PS3 version: [http://www.box.com/s/8e7h3l733lup49sex3lk](http://www.box.com/s/8e7h3l733lup49sex3lk)

EDIT -> For anyone still interested in this, I managed to update the script myself to support the bootsequence_ps3.ipk file as well.

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x2c
get FILES long
goto 0x30
for i = 0 < FILES
    get DUMMY1 long
    get SIZE long
    get ZSIZE long
    get TSTAMP longlong
    get DUMMY3 long
    get OFFSET long
    if DUMMY1 == 2
        get DUMMY4 long
        get DUMMY5 long
    endif
    get NAMESZ long
    math NAMESZ *= 2
    getdstring NAME NAMESZ
    set NAME unicode NAME
    math OFFSET += BASE_OFF
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #9
- Username: guilt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 29, 2012 12:30 am
- Post datetime: 2012-02-28T16:35:40+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

CKD files aren't DDS files. There are WAV files packed as .CKD, There are misc. files like bubblemenu_squeleton.skl.ckd packed that way too.

It's got to be an encryption. Any help?
## Post #10
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-02-28T23:40:17+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

> Reply from guilt
>
> CKD files aren't DDS files. There are WAV files packed as .CKD, There are misc. files like bubblemenu_squeleton.skl.ckd packed that way too.

It's got to be an encryption. Any help?
CKD files aren't encrypted. They just contain different types of files.
png.ckd and dds.ckd files contain DDS files (header modified, you can convert most of them back using the script I posted above). wav.ckd files contain WAV files.
Files ending in skl.ckd, etc are data files (that specific one is an animation "skeleton"/structure for the main menu) to be read with the UbiArt engine which hasn't been released to public yet.
## Post #11
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2012-06-30T07:44:10+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

aluigi,can you make a Rayman Origins IPK bms for Pc ?
## Post #12
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-12-09T01:29:19+00:00
- Post Title: Rayman Origins IPK (Xbox 360)

> Reply from Droolie
>
> guilt wrote:CKD files aren't DDS files. There are WAV files packed as .CKD, There are misc. files like bubblemenu_squeleton.skl.ckd packed that way too.

It's got to be an encryption. Any help?
CKD files aren't encrypted. They just contain different types of files.
png.ckd and dds.ckd files contain DDS files (header modified, you can convert most of them back using the script I posted above). wav.ckd files contain WAV files.
Files ending in skl.ckd, etc are data files (that specific one is an animation "skeleton"/structure for the main menu) to be read with the UbiArt engine which hasn't been released to public yet.

Hi there. Anyone see this texture in xbox 360 game, I think it is type of xbox 360 texture (like *.xpr file), please take my example file: [https://drive.google.com/file/d/0B44CD2 ... sp=sharing](https://drive.google.com/file/d/0B44CD2ifnn4NTkxrLVM4T0w3R0k/view?usp=sharing)

Thanks for any help!
