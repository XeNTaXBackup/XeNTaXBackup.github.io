## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-01-29T21:42:47+00:00
- Post Title: [Request] Travia 2

Web: [http://www.travia2.co.kr/index.asp](http://www.travia2.co.kr/index.asp)
Download Client: [http://down3.travia2.co.kr/Travia2_KOR_ ... 110801.exe](http://down3.travia2.co.kr/Travia2_KOR_Live_20110801.exe)

Ok I found a interesting game and maybe someone can help me for do it, ok the files extention are veru rare so I upload some samples for check it.

[Sample Files](http://www.mediafire.com/?75alck2cmzzcyss)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-13T21:57:20+00:00
- Post Title: [Request] Travia 2

You forgot about main filelist table (Lump.dat). Contained names archives and files inside archives.. Main executable protected with ASProtect v1.23 + API Emulation 

Unpacked executable can be found [here](http://www.progamercity.net/other-mmo/3078-release-travia-2-unpacked.html)
Lump.dat [here](http://www.mediafire.com/?0uibsk8fhpfbh1c)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T23:24:17+00:00
- Post Title: [Request] Travia 2

Lol critical why do you keep posting things in the graphics forum.

```
idstring "DGPAK"
get unk long
get unk long
get LUMPS long

for i = 0 < LUMPS do
	get lump_number long
	get nameLen long
	getdstring lump_name nameLen
next i

get FILES long
for i = 0 < FILES do
	get lump_number long
	get unk long
	get nameLen long
	getdstring NAME nameLen
	get unk2 long
	getdstring null 24
next i

```


Anyways some unknowns.
It first defines all the lumps (.0 through .530) and then for each file, it specifies which lump_number it is located in.
Then there are the two unknowns. The first one is just some seemingly arbitrary number. The second one is more reasonable. Multiple files may be stored in a single lump.

Bmx is likely the mesh extension.
I looked at the mesh lump but don't see anything obvious. It just looks like garbage really... Compression?
The textures lump you can see the tga TRUEVISION TARGA thingk, but I'm not sure whether it is a valid tga file since there's nulls everywhere.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-14T14:05:43+00:00
- Post Title: [Request] Travia 2

> Reply from finale00
>
> The textures lump you can see the tga TRUEVISION TARGA thingk, but I'm not sure whether it is a valid tga file since there's nulls everywhere.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T18:28:47+00:00
- Post Title: [Request] Travia 2

What tool is this? Looks useful for checking offsets and sizes.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T04:39:00+00:00
- Post Title: [Request] Travia 2

I don't know how the lump.dat file works but this seems to work for the archives.

```
#Written by Tsukihime
#Feb 14, 2012

get lump_num long
get nameLen long
getdstring lump_name nameLen
get FILES short
for i = 0 < FILES 
	get unk short
	get unk long
	get len long
	getdstring NAME len
	get unk1 long
	get unk2 long
	get unk3 long
	get unk4 long
	get unk5 long
	get unk6 long
	get SIZE long
	savepos OFFSET
	log NAME OFFSET SIZE
	math OFFSET += SIZE
	goto OFFSET
next i

```
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-15T14:37:36+00:00
- Post Title: [Request] Travia 2

> Reply from finale00
>
> What tool is this? Looks useful for checking offsets and sizes.
Nova Extractor 2.5
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-05T07:07:49+00:00
- Post Title: [Request] Travia 2

> Reply from CriticalError
>
> 

Web: http://www.travia2.co.kr/index.asp
Download Client: http://down3.travia2.co.kr/Travia2_KOR_ ... 110801.exe

Ok I found a interesting game and maybe someone can help me for do it, ok the files extention are veru rare so I upload some samples for check it.

Sample FilesHello my friend, this client connection has failed, can I re-upload a new connection, in advance thank you
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-07-05T13:25:42+00:00
- Post Title: [Request] Travia 2

> Reply from raykingnihong
>
> CriticalError wrote:

Web: http://www.travia2.co.kr/index.asp
Download Client: http://down3.travia2.co.kr/Travia2_KOR_ ... 110801.exe

Ok I found a interesting game and maybe someone can help me for do it, ok the files extention are veru rare so I upload some samples for check it.

Sample FilesHello my friend, this client connection has failed, can I re-upload a new connection, in advance thank youHello and sorry, but long time ago when leave all of this I delete all my korean accounts, so can't access anymore, don't remember id and pw for login and put new link sorry.
