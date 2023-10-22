## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-13T03:03:52+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

hey guys im looking for someone that can make a .bms script for this game  the files extensions are .sea and .img 


sea
[http://www.mediafire.com/?y2wxx0c75ruq756](http://www.mediafire.com/?y2wxx0c75ruq756)

img
[https://mega.co.nz/#!jQFmmIoR!VTkDzX71N ... Y5aBRcgUjg](https://mega.co.nz/#!jQFmmIoR!VTkDzX71NrsvHoXvbHJ-2TWYZrcDycixfY5aBRcgUjg)

world.dir
[http://www.mediafire.com/?wext8l1ihxrb1l3](http://www.mediafire.com/?wext8l1ihxrb1l3)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-13T09:55:47+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

IMG without DIR useless file, but you can try use my script for PC + dont forget enable Endian BIG

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

open FDDE DIR 0
open FDDE IMG 1

get DSIZE asize 0

for
    get OFFSET long 0
    get SIZE long 0
    math OFFSET *= 2048
    math SIZE *= 2048
    getdstring NAME 0x18 0
    log NAME OFFSET SIZE 1
    savepos TMP
    if TMP == DSIZE
  cleanexit
 endif
next
```


SEA - seems audio
## Post #3
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-04-13T12:42:53+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

Dose anyone know how to edit the font and text?
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-13T14:09:20+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

kk i  will give it a go  and see if it works


seems like that script didnt work
[](http://s675.photobucket.com/user/ps2iso/media/bully_zps1ac381d6.png.html)

*Update*
i got 1 file out so far
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-13T18:18:58+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

sorry about that ekey i just found the dir yif you can take a look at it when u can that would be thankful i didnt know u needed the dir XD

but it has been uploaded
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-13T20:42:44+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

Seems QuickBMS bugged bucause he tries find second file in output folder. You need select Output folder where input archive. Example:

```
Input Archive : C:\Test\World.img
Output Folder : C:\Test
```
## Post #7
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-13T21:55:22+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

hmm i just tried that but it seems not to work it unpacks 1 file can u edit the script to have big en
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-13T22:02:18+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big

open FDDE DIR 0
open FDDE IMG 1

get DSIZE asize 0

for
    get OFFSET long 0
    get SIZE long 0
    math OFFSET *= 2048
    math SIZE *= 2048
    getdstring NAME 0x18 0
    log NAME OFFSET SIZE 1
    savepos TMP
    if TMP == DSIZE
  cleanexit
endif
next
```


PS: Upload small archives (IMG/DIR)
## Post #9
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-13T22:46:03+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

sorry lol i can still upload some if u still want them

same thing happens 1 file extracts 

but here are the small files with the dirs

[http://www.mediafire.com/download.php?a8xxc91vzts521w](http://www.mediafire.com/download.php?a8xxc91vzts521w)
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-13T23:37:05+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

For me works fine.
## Post #11
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-14T00:37:00+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

i dont know how u did that because i get this on the small ones and big files i used the new script that u gave me tryed to leave it in the org  folder of bully 

[](http://s675.photobucket.com/user/ps2iso/media/xentax_zps345a34bc.png.html)
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-14T07:46:24+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

Dont use stupid GUI + you use not latest version QuickBMS
## Post #13
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-14T21:01:06+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

hmm the only thing i use the gui version is to make the .bms file
not sure if i can use the quickbms (cmd) with a .txt?
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-14T21:06:59+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

> Reply from lllccc
>
> hmm the only thing i use the gui version is to make the .bms file
not sure if i can use the quickbms (cmd) with a .txt?
Just run quickbms.exe, select script (any extension), select archive, select output dir = profit.
## Post #15
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-14T23:10:02+00:00
- Post Title: Bully Scholarship Edition (XBOX 360)

lol yea that's what i do  but seems not to work for me lol 

as shown in this video 

[http://www.youtube.com/watch?v=jgRsR3Q2 ... e=youtu.be](http://www.youtube.com/watch?v=jgRsR3Q2-Ts&feature=youtu.be)
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-15T06:17:21+00:00
- Post Title: Re: Bully Scholarship Edition (XBOX 360)

omfg update to latest version QuickBMS
## Post #17
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-15T12:20:28+00:00
- Post Title: Re: Bully Scholarship Edition (XBOX 360)

... now i feel like a dumb XD downloaded the lastest version worked perfect thank you for your help ^_^
## Post #18
- Username: sakalak
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 18, 2014 4:53 pm
- Post datetime: 2014-08-22T12:59:30+00:00
- Post Title: Re: Bully Scholarship Edition (XBOX 360)

i'm trying American.img file open with img tool 2.0
this program img files just open

how to xbox360 American.img file unpack and pack
for translate
please help

sorry my bad english
