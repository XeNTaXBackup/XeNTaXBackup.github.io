## Post #1
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-05-14T11:52:10+00:00
- Post Title: Spider-Man: Web of Shadows PC

Greetings everyone,I need help with extracting models from SM:WoS
Everything what we have currently for this game is QuickBms decompressor script
[http://aluigi.altervista.org/bms/spider ... ck_nch.bms](http://aluigi.altervista.org/bms/spiderman_pcpack_nch.bms)
If anyone wanna help here are samples :
[https://mega.nz/#!bgQHXAoR!nDHkeK3of8Eb ... n4cm7jKA84](https://mega.nz/#!bgQHXAoR!nDHkeK3of8EbpdLkpDPi7EAphEm-98yFgn4cm7jKA84)

Thanks in advance!

P.S
Texture finder can see some textures inside decompressed pcpack
[http://i.imgur.com/SX9CkN9.png](http://i.imgur.com/SX9CkN9.png)
so i hope mesh extraction is possible too,i would like to try but i'm total n00b in Hex2obj.
Decompressed pcpack sample - [https://mega.nz/#!K5ABSYRC!r_FPEOTKZ08T ... tVV5ytzXRo](https://mega.nz/#!K5ABSYRC!r_FPEOTKZ08TPJVjmpnsSGtk_BQm3uV-atVV5ytzXRo)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-18T17:37:53+00:00
- Post Title: Spider-Man: Web of Shadows PC

> Reply from Rutabaga
>
> so i hope mesh extraction is possible too,i would like to try but i'm total n00b in Hex2obj.I know 



ACT2_Mech_intro.JPG (92.51 KiB) Viewed 514 times
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-19T18:44:38+00:00
- Post Title: Spider-Man: Web of Shadows PC

the bms script here can extract the textures from the decompressed pcpack samples   
[viewtopic.php?p=129363#p129363](http://forum.xentax.com/viewtopic.php?p=129363#p129363)
## Post #4
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-05-20T09:09:48+00:00
- Post Title: Spider-Man: Web of Shadows PC

> Reply from shakotay2
>
> Rutabaga wrote:so i hope mesh extraction is possible too,i would like to try but i'm total n00b in Hex2obj.I know 
ACT2_Mech_intro.JPG
Ok,glad this is possible  

> Reply from AceWell
>
> the bms script here can extract the textures from the decompressed pcpack samples   
viewtopic.php?p=129363#p129363
I have problems with the your script..
[http://i.imgur.com/AN2AaY9.png](http://i.imgur.com/AN2AaY9.png)
Sample :
[https://www.sendspace.com/file/k9pcap](https://www.sendspace.com/file/k9pcap)

Thanks in advance,i hope you can fix this problem.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-20T10:13:47+00:00
- Post Title: Spider-Man: Web of Shadows PC

> Reply from Rutabaga
>
> I have problems with the your script..
http://i.imgur.com/AN2AaY9.png
Sample :
https://www.sendspace.com/file/k9pcap
Thanks in advance,i hope you can fix this problem.
that sample has 61 APKF blocks and only 1 has a TEX section.   
use this bms script to split the decompressed pcpack into separate APKF blocks 

```
math i = 1
do
    goto OFFSET
    get SKIP long
    findloc NEXT_OFFSET binary "\x41\x50\x4B\x46" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE - OFFSET
    get NAME basename
    string NAME + "_"
    string NAME + i 
    string NAME + ".36"
    log NAME OFFSET SIZE
    math i + 1
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```

then use the previous texture extraction script on the resulting *.36 files.  

you might even be able to use daemon1's tool on them too   
[viewtopic.php?p=130172#p130172](http://forum.xentax.com/viewtopic.php?p=130172#p130172)
## Post #6
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-05-20T14:04:51+00:00
- Post Title: Spider-Man: Web of Shadows PC

> Reply from AceWell
>
> 
that sample has 61 APKF blocks and only 1 has a TEX section.   
use this bms script to split the decompressed pcpack into separate APKF blocks 
Code: Select allfindloc OFFSET binary "\x41\x50\x4B\x46"
math i = 1
do
    goto OFFSET
    get SKIP long
    findloc NEXT_OFFSET binary "\x41\x50\x4B\x46" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE - OFFSET
    get NAME basename
    string NAME + "_"
    string NAME + i 
    string NAME + ".36"
    log NAME OFFSET SIZE
    math i + 1
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

then use the previous texture extraction script on the resulting *.36 files.  

you might even be able to use daemon1's tool on them too   
viewtopic.php?p=130172#p130172
Thanks a lot!
Now everything works nice,only proper mesh extraction is left.
I tried deamon1 tool,it works,but requires a optimization for Sm Wos meshes
[http://i.imgur.com/PSFa12v.png](http://i.imgur.com/PSFa12v.png)
## Post #7
- Username: Big4Rig
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 12, 2015 5:51 am
- Post datetime: 2017-08-26T02:00:00+00:00
- Post Title: Spider-Man: Web of Shadows PC

daemon's Spider-Man 3 APKF script works on the .36 files partially. It extracts all the textures as .dds and converts the meshes to .smd's with skeletons, but the issue is that the meshes are converted in UV format (meaning they're flattened and all distorted).
## Post #8
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2021-01-18T03:35:15+00:00
- Post Title: Spider-Man: Web of Shadows PC

Does anyone know how to get the meshes from this game? With daemon's Spider-Man 3 APKF script only works to get the textures but the .smd's files look messed up in noesis or any other rendering tool.
## Post #9
- Username: ggctuk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 07, 2016 5:08 am
- Post datetime: 2021-10-18T19:41:57+00:00
- Post Title: Spider-Man: Web of Shadows PC

Any chance that there has ever been progress with this? I would love to properly extract models from the game.
