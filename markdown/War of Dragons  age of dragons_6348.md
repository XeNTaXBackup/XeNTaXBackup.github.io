## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-04T01:06:03+00:00
- Post Title: War of Dragons : age of dragons

I have updated this to support bones and weights.
[War of Dragons.rar](https://xentaxbackup.github.io/file/4168_War of Dragons.rar)
## Post #2
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-04-04T02:13:11+00:00
- Post Title: War of Dragons : age of dragons

Good work Chrrox , i just have a dude this is a 360/PS3 or PC game?
## Post #3
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2011-04-04T02:54:46+00:00
- Post Title: War of Dragons : age of dragons

Ahem...

[http://lmgtfy.com/?q=War+of+Dragons%3A+Age+of+Dragons](http://lmgtfy.com/?q=War+of+Dragons%3A+Age+of+Dragons)

[http://steparu.com/previews/mmo-rpg-pre ... -mgame2009](http://steparu.com/previews/mmo-rpg-previews/373-war-of-dragons-mgame2009)
[http://www.mmoculture.com/2010/11/gstar ... ge-of.html](http://www.mmoculture.com/2010/11/gstar-2010-war-of-dragons-age-of.html)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-06T02:47:59+00:00
- Post Title: War of Dragons : age of dragons

Script has been updated. thanks to reveal8n for some help.

game download links

[http://www.mgame.com/download/download_ ... me?GCD=WOD](http://www.mgame.com/download/download_manager/nowcom_downloader.mgame?GCD=WOD)
[http://www.mgame.com/download/download_ ... me?GCD=WOD](http://www.mgame.com/download/download_manager/cdn_downloader.mgame?GCD=WOD)
[http://file.nowcdn.co.kr/down/mgame/wod ... eSetup.exe](http://file.nowcdn.co.kr/down/mgame/wod/full/20110331/WODOnlineSetup.exe)
[http://file.nowcdn.co.kr/down/mgame/wod ... /data1.zip](http://file.nowcdn.co.kr/down/mgame/wod/full/20110331/data1.zip)
[http://file.nowcdn.co.kr/down/mgame/wod ... /data2.zip](http://file.nowcdn.co.kr/down/mgame/wod/full/20110331/data2.zip)
[http://file.nowcdn.co.kr/down/mgame/wod ... /data3.zip](http://file.nowcdn.co.kr/down/mgame/wod/full/20110331/data3.zip)
[http://file.nowcdn.co.kr/down/mgame/wod ... /data4.zip](http://file.nowcdn.co.kr/down/mgame/wod/full/20110331/data4.zip)
[warofdragonsweight.png](https://xentaxbackup.github.io/file/4169_warofdragonsweight.png)
## Post #5
- Username: Annatar
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 18, 2011 1:17 am
- Post datetime: 2011-04-06T20:20:50+00:00
- Post Title: War of Dragons : age of dragons

Excellent work, thank you! Please say how extract these models from. data2 archives?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-06T21:10:43+00:00
- Post Title: War of Dragons : age of dragons

This will extract the data file.
if the index file changes ill need the newer one to update the initial offset.
The index file must be named file.tbl2

```
#quickbms script
#War of Dragons
#from chrrox

open FDDE tbl2 1
set arcnum 0


goto 0x10001C 1

for i = 0
    get offset long 1
    get zsize long 1
    get null3 long 1
    get size long 1
   get arcnum long 1
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


    get null1 long 1
    get null2 long 1

    get name string 1
    Padding 4 1

    get null long 1

        log name offset zsize
next i


```
## Post #7
- Username: Annatar
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 18, 2011 1:17 am
- Post datetime: 2011-04-07T12:52:34+00:00
- Post Title: War of Dragons : age of dragons

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-07T12:59:22+00:00
- Post Title: War of Dragons : age of dragons

What is the error you got?
it is the same file i have.
please update your quickbms version to the newest also.
## Post #9
- Username: Annatar
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 18, 2011 1:17 am
- Post datetime: 2011-04-07T13:19:10+00:00
- Post Title: War of Dragons : age of dragons

Yes, probably something wrong with my Quickbms, I have version 0.4.10b.
[error.JPG](https://xentaxbackup.github.io/file/4175_error.JPG)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-07T13:38:34+00:00
- Post Title: War of Dragons : age of dragons

try it now i think it was copy paste error on my part.
if it does not work wait till his afternoon ill re upload it
## Post #11
- Username: Annatar
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 18, 2011 1:17 am
- Post datetime: 2011-04-07T13:49:53+00:00
- Post Title: War of Dragons : age of dragons

Thank you very much Chrrox! Everything works perfectly
## Post #12
- Username: babo3615
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 23, 2010 5:52 pm
- Post datetime: 2011-04-08T03:36:33+00:00
- Post Title: War of Dragons : age of dragons

Thank you very much Chrrox!
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-08T04:40:30+00:00
- Post Title: War of Dragons : age of dragons

How to convert .xtex files?
i replaced header with dds, but all textures look like this:
[it_pc_alf_clsuit001-up_n.jpg](https://xentaxbackup.github.io/file/4185_it_pc_alf_clsuit001-up_n.jpg)
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-08T10:37:11+00:00
- Post Title: War of Dragons : age of dragons

Ill code up a converter later today but if you want to try just look for the dxt1 or dxt5 word at the start of the file there should be 4 more bytes after that just delete everthing before that point and paste your header.
## Post #15
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2011-04-08T12:40:52+00:00
- Post Title: War of Dragons : age of dragons

Thx chrrox, works great, a texture converter would be excellent
## Post #16
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-04-08T15:03:06+00:00
- Post Title: Re: War of Dragons : age of dragons

where i can download this game?
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-08T15:14:54+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from logansan25
>
> where i can download this game?
[here](http://forum.xentax.com/viewtopic.php?p=52275#p52275)
## Post #18
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-04-08T15:35:38+00:00
- Post Title: Re: War of Dragons : age of dragons

I get this error, for some reason:
## Post #19
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-04-08T22:53:48+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Tosyk
>
> logansan25 wrote:where i can download this game?
here

Thanks!!!!!

I visited your blog and like me too much, i am interisting and tutorial of animation bones to biped, but i dont understand, because i am a noob.
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-09T03:14:48+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from logansan25
>
> Tosyk wrote:logansan25 wrote:where i can download this game?
here

Thanks!!!!!

I visited your blog and like me too much, i am interisting and tutorial of animation bones to biped, but i dont understand, because i am a noob.
thanks, i agree that biped tutorial is not to easy, it was just a quick tip, but if you have a questions than be my guest
## Post #21
- Username: Andrakann
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-09T18:44:03+00:00
- Post Title: Re: War of Dragons : age of dragons

Texture Converter
quickbms

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get name1 string
getdstring null 0x10
get type long
get height long
get width long
get null long
get dxt long
get mips long
putVarChr MEMORY_FILE 0x1C mips long
putVarChr MEMORY_FILE 0xC width long
putVarChr MEMORY_FILE 0x10 height long
putVarChr MEMORY_FILE 0x54 dxt long
savepos offset
get size asize
math size - offset
get name basename
string name + .dds
append
log MEMORY_FILE offset size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE


```
## Post #22
- Username: Annatar
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 18, 2011 1:17 am
- Post datetime: 2011-04-09T18:49:46+00:00
- Post Title: Re: War of Dragons : age of dragons

Again, thank you Сhrrox! Converter works fine.
## Post #23
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-23T18:42:08+00:00
- Post Title: Re: War of Dragons : age of dragons

The contents of this post was deleted because of possible forum rules violation.


Updated 2015-02-04:
Here is importer for textured and skinned models and for animation.
It requires Blender249 and Python 26.
How use:
1. unpack importer
2. run Blender249.blend
3. in Blender Text Window press alt+p and select:
- xac files from  'part' folder  for meshes
- xac file from model folder for skeleton
- xsm files from 'action' folder for animation
[Blender249[WarOfDragonsOnline][PC][xac][xsm][2015-02-04].zip](https://xentaxbackup.github.io/file/8598_Blender249[WarOfDragonsOnline][PC][xac][xsm][2015-02-04].zip)
## Post #24
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-24T17:24:45+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from chrrox
>
> Texture Converterthanks a lot chrox for texture converter, but can you tell me why can't load the pictures, I don't know the converter get textures bad or not because can't open.





and about mesh of weapons? is not xac format is xmesh so who import it in MAX? the importer is for xac? anyway thanks a lot for all support and pattience for ppl begin in it.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T01:59:57+00:00
- Post Title: Re: War of Dragons : age of dragons

The contents of this post was deleted because of possible forum rules violation.
## Post #26
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-30T18:50:32+00:00
- Post Title: Re: War of Dragons : age of dragons

finalle 00:
 -for import meshes please browse for folder "...\part" for each model using "browse" in section SELECT WAR OF DRAGON XAC DIR
 -for textures use "browse" in section SELECT TEXTURE DIR
 -for animations use "browse" in section SELECT  WAR OF DRAGON XSM  DIR
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T22:11:02+00:00
- Post Title: Re: War of Dragons : age of dragons

Oh, I see it.
I was loading the wrong xac file lol
## Post #28
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2011-09-19T11:29:59+00:00
- Post Title: Re: War of Dragons : age of dragons

done... within the filexxx.data2 is zlib based data... offzip works fine...
## Post #29
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2011-11-02T19:15:26+00:00
- Post Title: Re: War of Dragons : age of dragons

Could anyone confirm if the links are still working for the download, or did they update them?
## Post #30
- Username: archiryo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 15, 2012 11:47 pm
- Post datetime: 2012-02-15T16:04:24+00:00
- Post Title: Re: War of Dragons : age of dragons

i can't download the game!
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T06:38:35+00:00
- Post Title: Re: War of Dragons : age of dragons

What's the pixel format for these textures?

It just says 0x16.

Probably one of those RGBA32 or something, but I don't get anything from it.
[em_007_s_a.7z](https://xentaxbackup.github.io/file/5085_em_007_s_a.7z)
## Post #32
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-01T16:43:25+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from chrrox
>
> Script has been updated. thanks to reveal8n for some help.

game download links

http://www.mgame.com/download/download_ ... me?GCD=WOD
http://www.mgame.com/download/download_ ... me?GCD=WOD
http://file.nowcdn.co.kr/down/mgame/wod ... eSetup.exe
http://file.nowcdn.co.kr/down/mgame/wod ... /data1.zip
http://file.nowcdn.co.kr/down/mgame/wod ... /data2.zip
http://file.nowcdn.co.kr/down/mgame/wod ... /data3.zip
http://file.nowcdn.co.kr/down/mgame/wod ... /data4.zipHello God, I've been looking for this game for a long time, many connections are disabled, can give a new connection, for which I would like to thank you, my friend
## Post #33
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-07-01T19:18:12+00:00
- Post Title: Re: War of Dragons : age of dragons

No warez
## Post #34
- Username: skylab
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-01T22:26:31+00:00
- Post Title: Re: War of Dragons : age of dragons

No need to worry mr. mouse.
This is a free to play and download mmo.
The link for the client files still works
if you view the source of page.
[http://www.mgame.com/download/download_ ... me?GCD=WOD](http://www.mgame.com/download/download_manager/cdn_downloader.mgame?GCD=WOD)
it gives you the client download links.

```
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data1.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data2.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data3.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data4.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data5.zip

```
## Post #35
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-14T14:37:09+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from chrrox
>
> No need to worry mr. mouse.
This is a free to play and download mmo.
The link for the client files still works
if you view the source of page.
http://www.mgame.com/download/download_ ... me?GCD=WOD
it gives you the client download links.
Code: Select allhttp://content4mapa.nefficient.co.kr/mgame/wod/20120524/WODOnlineSetup.exe
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data1.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data2.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data3.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data4.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data5.zip

Chrrox, i downaloded and treid to open some files, .xac with script you did, but some appear this error in 3dmax:


Others files, like this BOW open normal. What can be?


I notice that sometimes the same file that open once, in the second time to try to open, gave that error.
## Post #36
- Username: Dezert
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 31, 2016 9:58 pm
- Post datetime: 2016-05-15T20:56:22+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from chrrox
>
> No need to worry mr. mouse.
This is a free to play and download mmo.
The link for the client files still works
if you view the source of page.
http://www.mgame.com/download/download_ ... me?GCD=WOD
it gives you the client download links.
Code: Select allhttp://content4mapa.nefficient.co.kr/mgame/wod/20120524/WODOnlineSetup.exe
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data1.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data2.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data3.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data4.zip
http://content4mapa.nefficient.co.kr/mgame/wod/20120524/data5.zip

Do you still have this game, if Yes, throw please the link
## Post #37
- Username: Egaoladakir
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 03, 2020 5:37 pm
- Post datetime: 2020-06-13T16:47:21+00:00
- Post Title: Re: War of Dragons : age of dragons

I salvaged the Russian version client (WOD 130722).

[https://mega.nz/file/TMt1yASQ#Bz_MeV7iB ... Zlm0gPuoho](https://mega.nz/file/TMt1yASQ#Bz_MeV7iBzfpU82EH8yBtddnwH2Q5zJeqZlm0gPuoho)
## Post #38
- Username: Egaoladakir
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 03, 2020 5:37 pm
- Post datetime: 2020-06-13T16:50:30+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Dezert ↑Mon May 16, 2016 4:56 am at Mon May 16, 2016 4:56 am
>
> 


Do you still have this game, if Yes, throw please the link

I got some russian version (WOD_130722)

[https://mega.nz/file/TMt1yASQ#Bz_MeV7iB ... Zlm0gPuoho](https://mega.nz/file/TMt1yASQ#Bz_MeV7iBzfpU82EH8yBtddnwH2Q5zJeqZlm0gPuoho)


I tried mentioned guides to unpack models, textures and sounds - nothing worked for me.
I don't know how to unpack tlb2/data2 archives. And I probably used wrong guide to use Offzip.
## Post #39
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-14T15:10:07+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Egaoladakir ↑Sun Jun 14, 2020 12:50 am at Sun Jun 14, 2020 12:50 am
>
> 

I got some russian version (WOD_130722)

https://mega.nz/file/TMt1yASQ#Bz_MeV7iB ... Zlm0gPuoho


I tried mentioned guides to unpack models, textures and sounds - nothing worked for me.
I don't know how to unpack tlb2/data2 archives. And I probably used wrong guide to use Offzip.


Man! god bless you! I've been looking for this client a lot and never found it.

Someone knows if all war of dragon version were closed or if there is anyone still online ( kr, ch, ru, etc..) ?
## Post #40
- Username: Egaoladakir
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 03, 2020 5:37 pm
- Post datetime: 2020-06-14T23:18:54+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Drawing ↑Sun Jun 14, 2020 11:10 pm at Sun Jun 14, 2020 11:10 pm
>
> 

Man! god bless you! I've been looking for this client a lot and never found it.

Someone knows if all war of dragon version were closed or if there is anyone still online ( kr, ch, ru, etc..) ?

Yes, game is officially shut down long ago.

Right now, I have the question. How to rip models? I cannot unpack Data2/tbl2 files.
Next, I don't know how to access XAC model and other file containing textures.

Please let me know, if this client is in any of use?
## Post #41
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-14T23:49:23+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Egaoladakir ↑Mon Jun 15, 2020 7:18 am at Mon Jun 15, 2020 7:18 am
>
> 

Yes, game is officially shut down long ago.

Right now, I have the question. How to rip models? I cannot unpack Data2/tbl2 files.
Next, I don't know how to access XAC model and other file containing textures.

Please let me know, if this client is in any of use?
[https://aluigi.altervista.org/bms/war_o ... ragons.bms](https://aluigi.altervista.org/bms/war_of_the_dragons.bms)

I extracted content using this script for quickbms 

just select file.tlb  In char folder and it will unpack everything. 

To import models we got different way: most canonic would be use chrrox max plugin (mesh, bones) , or you could try fatimporter ( it should load animation too; i don't remember if it was integrated war of dragon but it has dk online and other game using .xac, xsm format). You could try noesis script made by finale too.
## Post #42
- Username: Egaoladakir
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 03, 2020 5:37 pm
- Post datetime: 2020-06-15T00:21:02+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Drawing ↑Mon Jun 15, 2020 7:49 am at Mon Jun 15, 2020 7:49 am
>
> 

https://aluigi.altervista.org/bms/war_o ... ragons.bms

I extracted content using this script for quickbms 

just select file.tlb  In char folder and it will unpack everything. 

To import models we got different way: most canonic would be use chrrox max plugin (mesh, bones) , or you could try fatimporter ( it should load animation too; i don't remember if it was integrated war of dragon but it has dk online and other game using .xac, xsm format). You could try noesis script made by finale too.

Is there ways to import into blender?
How to be with texture access?
## Post #43
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-16T11:13:52+00:00
- Post Title: Re: War of Dragons : age of dragons

> Reply from Szkaradek123 ↑Sun Apr 24, 2011 2:42 am at Sun Apr 24, 2011 2:42 am
>
> 
Updated 2015-02-04:
Here is importer for textured and skinned models and for animation.
It requires Blender249 and Python 26.
How use:
1. unpack importer
2. run Blender249.blend
3. in Blender Text Window press alt+p and select:
- xac files from  'part' folder  for meshes
- xac file from model folder for skeleton
- xsm files from 'action' folder for animation
[download/file.php?id=8598](https://forum.xentax.com/download/file.php?id=8598)

for texture, you need to find yourself where they are located, they are in .xtex format. then use this script for quickbms made by chrrox to convert them

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get name1 string
getdstring null 0x10
get type long
get height long
get width long
get null long
get dxt long
get mips long
putVarChr MEMORY_FILE 0x1C mips long
putVarChr MEMORY_FILE 0xC width long
putVarChr MEMORY_FILE 0x10 height long
putVarChr MEMORY_FILE 0x54 dxt long
savepos offset
get size asize
math size - offset
get name basename
string name + .dds
append
log MEMORY_FILE offset size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE

```
