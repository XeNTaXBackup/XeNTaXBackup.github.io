## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-11T00:32:59+00:00
- Post Title: Valiant MMO

Another game using the same format 
here is the archive extractor

```
#Valiant
#from chrrox

open FDDE tbl2 1
set arcnum 0


goto 0x100018 1

for i = 0
    get null3 long 1
    get offset long 1
    get size long 1
    get arcnum long 1
    print "%arcnum%"
        set NAME1 string "file0"
    set MYEXT string arcnum
    strlen MYEXTSZ MYEXT
    if MYEXTSZ == 1
        string NAME1 += "00"
    endif
    if MYEXTSZ == 2
        string name1 - 1
        string NAME1 += "0"
    endif
    if MYEXTSZ == 3
        string name1 - 1
        string NAME1 += ""
    endif
    string NAME1 += MYEXT
    string NAME1 += .data2
    open FDSE NAME1 0
    get name string 1
    Padding 4 1
        log name offset size
next i

```

use the scripts here for models and textures
[viewtopic.php?f=16&t=6348](http://forum.xentax.com/viewtopic.php?f=16&t=6348)

Game Download
[http://www.mgame.com/download/download_ ... CD=valiant](http://www.mgame.com/download/download_manager/nowcom_downloader.mgame?GCD=valiant)

[http://file.nowcdn.co.kr/down/mgame/Val ... lMgame.exe](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/InstallMgame.exe)
[http://file.nowcdn.co.kr/down/mgame/Val ... tStart.exe](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/ValiantStart.exe)
[http://file.nowcdn.co.kr/down/mgame/Val ... _Setup.dll](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/_Setup.dll)
[http://file.nowcdn.co.kr/down/mgame/Val ... /data1.cab](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/data1.cab)
[http://file.nowcdn.co.kr/down/mgame/Val ... /data1.hdr](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/data1.hdr)
[http://file.nowcdn.co.kr/down/mgame/Val ... /data2.cab](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/data2.cab)
[http://file.nowcdn.co.kr/down/mgame/Val ... /data3.cab](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/data3.cab)
[http://file.nowcdn.co.kr/down/mgame/Val ... /data4.cab](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/data4.cab)
[http://file.nowcdn.co.kr/down/mgame/Val ... SSetup.dll](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/ISSetup.dll)
[http://file.nowcdn.co.kr/down/mgame/Val ... layout.bin](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/layout.bin)
[http://file.nowcdn.co.kr/down/mgame/Val ... /setup.bmp](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/setup.bmp)
[http://file.nowcdn.co.kr/down/mgame/Val ... /setup.ini](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/setup.ini)
[http://file.nowcdn.co.kr/down/mgame/Val ... /setup.inx](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/setup.inx)
[http://file.nowcdn.co.kr/down/mgame/Val ... /setup.iss](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/setup.iss)
[http://file.nowcdn.co.kr/down/mgame/Val ... svcr90.dll](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/msvcr90.dll)
[http://file.nowcdn.co.kr/down/mgame/Val ... T.manifest](http://file.nowcdn.co.kr/down/mgame/Valiant/Full/20110307/Microsoft.VC90.CRT.manifest)
[valiant.png](https://xentaxbackup.github.io/file/4204_valiant.png)
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-23T19:40:16+00:00
- Post Title: Valiant MMO

Thanks chroxxx this game have very good stuff, anyway this maxscript support valiant models but not all, not support Item files cause have another model file format, maybe you can take a view.

Sample Files
[http://www.megaupload.com/?d=H167HLTN](http://www.megaupload.com/?d=H167HLTN)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-23T20:03:57+00:00
- Post Title: Valiant MMO

Valiant and Argo use the same format for items.

[viewtopic.php?p=55952#p55952](http://forum.xentax.com/viewtopic.php?p=55952#p55952)
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-26T00:27:26+00:00
- Post Title: Valiant MMO

> Reply from finale00
>
> Valiant and Argo use the same format for items.

viewtopic.php?p=55952#p55952

I see its the same format for items Valiant and Argo, but i cant found the script to import the objects in max or blender finished and working,
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T02:02:10+00:00
- Post Title: Valiant MMO

The format is provided. You can write your it yourself
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-26T18:53:52+00:00
- Post Title: Valiant MMO

> Reply from finale00
>
> The format is provided. You can write your it yourself

I am 3D Modeler i dont know abouth code, but if you can help on thist and post a little tutorial abouth how to write bms or max script this can be usefull   cheers.
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-18T07:49:26+00:00
- Post Title: Valiant MMO

.xac and .xtex are solved but wath abouth the .xgeom files? and finale its posible writhe this for .xgeom if its  posible for Noesis? coz the scritp for max only works with .xac files, thanks man.

links for files. 
[http://www.4shared.com/rar/4Qhar_DJ/weapon.html](http://www.4shared.com/rar/4Qhar_DJ/weapon.html)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T16:13:13+00:00
- Post Title: Valiant MMO

Maybe you can practice writing noesis plugin since the format has been figured out already.
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-18T17:25:13+00:00
- Post Title: Valiant MMO

I good with moding for Online games, take models from one and put in other game, i control perfect this area, animations, textures formats with alpha chanels glowing, resizing models with skeletons and cuts, texturize, weights, skining etc, but writing plugins for Noesis? mmm, well maybe i can learn this also, something guide for beginers on this?. step by step please, and if have video its bether also.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T18:25:06+00:00
- Post Title: Valiant MMO

You're basically taking a format specs and translating it into code.
So you need to be able to sit down and stare at a guide that tells you what functions to use, and be able to write the code yourself. Basically think about what the problem is and how you should solve it (that's really all programming is)

You can look at the noesis python import guide chrrox wrote which tells you which functions to use. It's pretty step-by-step, though it assumes you can read the API and know how to read from a file (eg: readUInt(), read('2L'), etc)
## Post #11
- Username: kazhuki01
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Jun 19, 2012 1:46 am
- Post datetime: 2013-08-02T17:27:59+00:00
- Post Title: Valiant MMO

is there available clients link for this game?
I think valiant is dead game already
## Post #12
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2013-08-04T23:48:58+00:00
- Post Title: Valiant MMO

Not sure, but i think you can look here: 
[http://valiant.mgame.com/](http://valiant.mgame.com/)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-04T23:56:54+00:00
- Post Title: Valiant MMO

the link i gave still works to get the client files

[http://content4mapa.nefficient.co.kr/mg ... lMgame.exe](http://content4mapa.nefficient.co.kr/mgame/valiant/20120419/InstallMgame.exe)
[http://content4mapa.nefficient.co.kr/mg ... ta.cab.001](http://content4mapa.nefficient.co.kr/mgame/valiant/20120419/data.cab.001)
[http://content4mapa.nefficient.co.kr/mg ... ta.cab.002](http://content4mapa.nefficient.co.kr/mgame/valiant/20120419/data.cab.002)
## Post #14
- Username: kazhuki01
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Jun 19, 2012 1:46 am
- Post datetime: 2013-08-05T01:41:58+00:00
- Post Title: Valiant MMO

which file contains the models sir?
thanks for the link.
because when i tried downloading.
it wont allow me to download.


Ok working.
Is there any plugin for 3dsmax? to import the objects like armors and etc?
## Post #15
- Username: pakxhit123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 15, 2016 2:22 am
- Post datetime: 2016-02-26T07:41:41+00:00
- Post Title: Valiant MMO

> Reply from chrrox
>
> the link i gave still works to get the client files

http://content4mapa.nefficient.co.kr/mg ... lMgame.exe
http://content4mapa.nefficient.co.kr/mg ... ta.cab.001
http://content4mapa.nefficient.co.kr/mg ... ta.cab.002

 Sir how to unpack this one ? i can't unpack this using quickbms please help me
## Post #16
- Username: megamind
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 17, 2016 10:24 pm
- Post datetime: 2016-06-23T05:11:45+00:00
- Post Title: Re: Valiant MMO

anyone can give working download links for valiant client? or anyone would care to reupload it?
