## Post #1
- Username: falconcool
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-10T18:40:33+00:00
- Post Title: MMO ARGO

here is a file extractor script


```
#ARGO
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


    get null1 long 1
    get null2 long 1

    get name string 1
    Padding 4 1

    get null long 1
if zsize == size
        log name offset zsize
else
clog name offset zsize size
endif
next i

```


and you can use the same import and texture converter here
[viewtopic.php?f=16&t=6348](http://forum.xentax.com/viewtopic.php?f=16&t=6348)

file download for game
[http://www.mgame.com/download/download_ ... e?GCD=ARGO](http://www.mgame.com/download/download_manager/nowcom_downloader.mgame?GCD=ARGO)

[http://file.nowcdn.co.kr/down/mgame/ARG ... nstall.exe](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/MGameInstall.exe)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /setup.exe](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/setup.exe)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /data1.cab](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/data1.cab)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /data1.hdr](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/data1.hdr)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /data2.cab](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/data2.cab)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /data3.cab](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/data3.cab)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /data4.cab](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/data4.cab)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /data5.cab](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/data5.cab)
[http://file.nowcdn.co.kr/down/mgame/ARG ... gine32.cab](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/engine32.cab)
[http://file.nowcdn.co.kr/down/mgame/ARG ... layout.bin](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/layout.bin)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /setup.bmp](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/setup.bmp)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /setup.ibt](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/setup.ibt)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /setup.ini](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/setup.ini)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /setup.inx](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/setup.inx)
[http://file.nowcdn.co.kr/down/mgame/ARG ... /setup.iss](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/setup.iss)
[http://file.nowcdn.co.kr/down/mgame/ARG ... svcr90.dll](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/msvcr90.dll)
[http://file.nowcdn.co.kr/down/mgame/ARG ... T.manifest](http://file.nowcdn.co.kr/down/mgame/ARGO/Full/20110107/Microsoft.VC90.CRT.manifest)

Enjoy
## Post #2
- Username: bmobius
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 18, 2010 6:44 am
- Post datetime: 2011-04-16T22:55:43+00:00
- Post Title: MMO ARGO

Running the risk of sounding.. well.. retarded... I have the game, but I'm not sure how to use QuickBMS with this game. What files are you unpacking with it and where are the character archives located?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-17T00:33:45+00:00
- Post Title: MMO ARGO

Argo\Resources\file.tbl

its the huge set of archives in the game.
## Post #4
- Username: Sniperello
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 08, 2011 7:26 am
- Post datetime: 2011-04-17T15:17:15+00:00
- Post Title: MMO ARGO

thnx man!
## Post #5
- Username: bmobius
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 18, 2010 6:44 am
- Post datetime: 2011-04-18T04:54:38+00:00
- Post Title: MMO ARGO

> Reply from chrrox
>
> Argo\Resources\file.tbl

its the huge set of archives in the game.

Ah! So that's what I was missing!

Once I pointed QuickBMS to the correct file, everything else fell right into place. It generated a proper folder and unpacked to that location. Then on top, the 3DS Max import script worked like a charm as well as the QuickBMS texture script.

Thanks for the work!
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-26T17:31:20+00:00
- Post Title: MMO ARGO

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-23T21:27:29+00:00
- Post Title: MMO ARGO

thanks a lot guys, all work fine, but 1 question, about bms script when convert xtex to dds don't work, take a look





and about mesh of weapons? is not xac format is xmesh so who import it in MAX? the importer is for xac? anyway thanks a lot for all support and pattience for ppl begin in it.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T03:15:37+00:00
- Post Title: MMO ARGO

^I have tried the bms script on some item textures but I converted it to tga afterwards.

If anyone is interested in figuring out the xgeom files (items), here's a couple small ones I picked out.
There are a couple 1 KB ones 



My guess is that it uses shorts for stuff like number of characters in a string (based on the last line), but it doesn't seem obvious what some of the other numbers mean before the big section of floats.

The xmesh files tell which xgeom and which xmtl files to load. Some of them are in binary some are them are in XML format, so maybe that makes it easier to tell what the xmesh file is.
one type of xgeom is like

> dword xbin
>
> 10 bytes [seems always 0D 0A 00 0B 00 00 00 00 00 01]
>
> short charCount
>
> charCount meshName
>
> 10 bytes ???
>
> short charCount
>
> charCount unique ID (just some name. Some xgeom have, some don't)
>
> 2 bytes ???
>
> short vertType 
>
> 
>
> ===== Following applies to vertType 1 only =====
>
> 5 bytes ???
>
> short numVerts
>
> short numVerts * 3 (so numFaces = this / 3)
>
> 
>
> struct vertex {
>
>    float_3 x,y,z 
>
>    float_3 (normals probably)
>
>    float_2 u,v
>
> }
>
> struct face {
>
>    short_3 v1, v2, v3
>
> }
>
> short ???
>
> short charCount
>
> charCount material library name (.xMtl files)

Seems to be working for the items. There are larger xgeom files that are more complicated.

If someone can help me with the notation to make it clearer that would be great.




[xgeom.7z](https://xentaxbackup.github.io/file/4401_xgeom.7z)
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T03:16:17+00:00
- Post Title: MMO ARGO

Valiant online uses the same format, and it works as well.

The smaller items seems to work using the format up there, but it won't work for a lot of the larger files.

In particular, some differences are

> dword xbin
>
> 10 bytes [seems always 0D 0A 00 0B 00 00 00 00 00 01]
>
> short charCount
>
> charCount meshName
>
> 10 bytes ???
>
> short charCount
>
> charCount unique ID (just some name. Some xgeom have, some don't)
>
> 9 bytes [00 12 03 00 00 04 00 00 00]

Instead of 12 01 it is now 12 03. So maybe can conclude there are two different types of xgeom files.
There is also 12 04. Maybe it represents the vertex type since any xgeom file with type 12 01 follows the previous post's structure.

Maybe something special about that second byte.

xmtl files seem pretty straightforward, but I don't understand materials that much so I don't know what the values could be.
Some groups of 4 floats and 3 floats here and there, maybe for RGBA, ambient, and emissive?

Here's some bigger files in case small ones lack detail.
And some bigger files definitely have different format than the small ones.
[h_medic.7z](https://xentaxbackup.github.io/file/4402_h_medic.7z)
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T15:57:24+00:00
- Post Title: MMO ARGO

Type 1 vertex has vertsize 32
Type 3 vertex has vertsize 48
Type 4 vertex has vertsize 56

```
10 bytes [seems always 0D 0A 00 0B 00 00 00 00 00 01]
short charCount
charCount meshName
10 bytes ???
short charCount
charCount unique ID (just some name. Some xgeom have, some don't)
2 bytes ???
short vertType 
5 bytes ???
short numVerts
short numVerts * 3 (so numFaces = this / 3)

struct vertex type 1 {
   float_3 x,y,z 
   float_3 (normals probably)
   float_2 u,v
}

struct vertex type 3 {
  float_3 x,y,z
  float_3 maybe
  float_2 maybe
  16 bytes ???
}
struct vertex type 4 {
   float_3 x,y,z
   float_3 maybe
   float_2 maybe
   24 bytes ???
}
struct face {
   short_3 v1, v2, v3
}
short ???
short charCount
charCount material library name (.xMtl files)

```



Since coords, uv, and normals have been dealt with in type 1, I'm guessing the rest are bones and stuff? Haven't actually looked into bones yet so I don't know how they are usually stored, or what kind of information they might need.

Any references that I can look at for this info? Most of the tutorials I've read are very practical and just talk about how to make stuff...
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-01T02:13:23+00:00
- Post Title: MMO ARGO

Some results:



Works for all non-XML xgeom files.

Also...here are XML versions of the xgeom, xlocus, xmesh, and xmtl files.
I was wondering what was causing certain files to crash my script and noticed this 

Those should be straightforward to parse.
[000_006_02529.7z](https://xentaxbackup.github.io/file/4407_000_006_02529.7z)
## Post #12
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-06T02:43:13+00:00
- Post Title: MMO ARGO

xgeom files, but where its the script or the converter, somebody can release this from the code Finale wrhote?
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-22T17:20:15+00:00
- Post Title: MMO ARGO

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-10T17:41:14+00:00
- Post Title: MMO ARGO

Any idea or news with .xgeom files?
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T07:00:01+00:00
- Post Title: MMO ARGO

xgeom noesis plugin added.

May not work for all models yet (I think there were some issues with a couple of them when I looked at it, but not sure which)

Test different types of xgeom and see which ones fail. I'm sure it was related to characters though.
## Post #16
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-19T07:11:18+00:00
- Post Title: Re: MMO ARGO

Tested with Argo and Valiant Items, works fully perfect...   .
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T07:17:09+00:00
- Post Title: Re: MMO ARGO

Test it on more than just items.
There are some characters in argo that are stored in xgeom.
## Post #18
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-19T16:29:15+00:00
- Post Title: Re: MMO ARGO

> Reply from finale00
>
> Test it on more than just items.
There are some characters in argo that are stored in xgeom.

.xgeom (ITEM) can open in ARGO  
.xgeom (OBJECT) not works  

Here Item and Object
[http://www.4shared.com/rar/qAMJ_n0o/AJIJIOS.html](http://www.4shared.com/rar/qAMJ_n0o/AJIJIOS.html)
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T19:29:18+00:00
- Post Title: Re: MMO ARGO

Updated script.

See if it breaks for anything.

Verify that the normals and UV's look right (you didn't include the material library .xmtl so I hardcoded texnames)
## Post #20
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-19T21:12:21+00:00
- Post Title: Re: MMO ARGO

Works perfect  , but not with all the .xgeom its rare, take a view of this.
This its another folders group, its the last folder groups with .xgeom items.

[http://www.4shared.com/rar/AYwmshUJ/SUBIENDO.html](http://www.4shared.com/rar/AYwmshUJ/SUBIENDO.html)

BTw, all textures for all objects, items, etc. are stored in subfolder with the name of Texture.

Maybe can writhe the plugin to load the texture from this folder?.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T21:21:48+00:00
- Post Title: Re: MMO ARGO

Updated.
If you look at the script, you'll see that I have a vertType.

The ones you uploaded have vertType of 3, and the vert structs are 48 bytes each.
VertType 2 has struct size of 56, while vertType 1 has struct size 32.

I've added in an else condition that just prints out the vertType, so if another model doesn't load, that might be the issue.

It also loads all models in a single folder.

The UV's seem kind of off though....
## Post #22
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-19T21:55:24+00:00
- Post Title: Re: MMO ARGO

Just perfect, now all .xgeom are loaded right, mmmm btw i download all your plugins, but lot half of this plugins send this error.



wath u think can be the error?. 27 plugins send this error.

Windows 7 64bytes maybe?
## Post #23
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-19T22:09:54+00:00
- Post Title: Re: MMO ARGO

> Reply from Rimbros
>
> Just perfect, now all .xgeom are loaded right, mmmm btw i download all your plugins, but lot half of this plugins send this error.



wath u think can be the error?. 27 plugins send this error.

Windows 7 64bytes maybe?he said that this plugin is not made ​​of 100%, then it is not usable at the moment.
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T23:03:54+00:00
- Post Title: Re: MMO ARGO

> Reply from Rimbros
>
> Just perfect, now all .xgeom are loaded right, mmmm btw i download all your plugins, but lot half of this plugins send this error.



wath u think can be the error?. 27 plugins send this error.

Windows 7 64bytes maybe?

Some of the plugins I didn't do type checking. For example in dragon nest, I don't know how to check whether it is a dragon nest format. That means every .msh file will use Dragon Nest if the plugin manager decided to import Dragon Nest first.

Also, I sometimes forget to remove the Sanae3D test package after I have figured out enough of the format to not need it.

If an erroneous plugin pops up, just delete it from your plugin folder.
It's not like you need all of them at the same time anyways.
## Post #25
- Username: draion
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 22, 2012 3:26 pm
- Post datetime: 2013-08-31T20:56:26+00:00
- Post Title: Re: MMO ARGO

Hello everyone , a lurker here    , well sometime ago i downloaded the Furinkazan MMO Client [viewtopic.php?f=16&t=6479](http://forum.xentax.com/viewtopic.php?f=16&t=6479) and boy that was one of the hardest file i have ever had to found on the interwebz since 99% of the links or servers were dead or removed well and i tried to unpack the files but i couldnt 
and i dont know why because i was able to successfully unpack Valiant MMO Files [viewtopic.php?f=16&t=6398](http://forum.xentax.com/viewtopic.php?f=16&t=6398) and Argo MMO too though the latter gave me this message at the end.

So it will be great if anyone could help me here thank you so much and excuse my english  
[ARGO.png](https://xentaxbackup.github.io/file/6581_ARGO.png)
## Post #26
- Username: draion
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 22, 2012 3:26 pm
- Post datetime: 2013-09-02T02:32:40+00:00
- Post Title: Re: MMO ARGO

Here are some Furinkazan files in case anyone needs them , i upload them to mediafire since i know is against the ToS of this website so i think is ok this way , i will really appreciate if anyone can help me with the scripts or similar since i am not an expert in code or hacker , thank you also sorry for the double post

[http://www.mediafire.com/?dxd7idy3dzmm0ms](http://www.mediafire.com/?dxd7idy3dzmm0ms)
