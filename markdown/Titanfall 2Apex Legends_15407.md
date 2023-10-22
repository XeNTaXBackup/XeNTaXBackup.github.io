## Post #1
- Username: analblaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 17, 2015 5:05 pm
- Post datetime: 2016-10-24T17:54:05+00:00
- Post Title: Titanfall 2/Apex Legends

Preload just went up. Still using VPKs, but also "RPAKs" and "STARPAKs". N̶a̶t̶u̶r̶a̶l̶l̶y̶,̶ ̶e̶x̶i̶s̶t̶i̶n̶g̶ ̶t̶o̶o̶l̶s̶ ̶a̶r̶e̶n̶'̶t̶ ̶w̶o̶r̶k̶i̶n̶g̶ ̶w̶i̶t̶h̶ ̶t̶h̶e̶m̶ ̶y̶e̶t̶.̶ I must have not been opening _dirs or something, because now cra0kalo's VPK tool is opening them just fine. Nice.
That said, Crowbar is saying that models are of a newer unknown version and sounds are stored in their own unknown archives. Materials seem to be opening just fine with Nem's tools, though.

If anyone's interested in taking a look and doesn't feel like buying the game, let me know and I can throw things up on Mega or something.

(paging cra0kalo, wherever he may be)
## Post #2
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-10-25T14:36:20+00:00
- Post Title: Titanfall 2/Apex Legends

> Reply from analblaze
>
> Preload just went up. Still using VPKs, but also "RPAKs" and "STARPAKs". N̶a̶t̶u̶r̶a̶l̶l̶y̶,̶ ̶e̶x̶i̶s̶t̶i̶n̶g̶ ̶t̶o̶o̶l̶s̶ ̶a̶r̶e̶n̶'̶t̶ ̶w̶o̶r̶k̶i̶n̶g̶ ̶w̶i̶t̶h̶ ̶t̶h̶e̶m̶ ̶y̶e̶t̶.̶ I must have not been opening _dirs or something, because now cra0kalo's VPK tool is opening them just fine. Nice.
That said, Crowbar is saying that models are of a newer unknown version and sounds are stored in their own unknown archives. Materials seem to be opening just fine with Nem's tools, though.

If anyone's interested in taking a look and doesn't feel like buying the game, let me know and I can throw things up on Mega or something.

(paging cra0kalo, wherever he may be)

Hi, it would be appreciate if you leave link on Mega; VPKs and etc.
## Post #3
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-10-28T16:42:12+00:00
- Post Title: Titanfall 2/Apex Legends

Maybe the audio formats was the wrong place to post, can someone have a look at the audio archive they are using in TF2? 

The archive begins with RTSC, I've searched around and couldn't find anything pertaining to it. I'd really like to get the sound and music files.
[General_stream.zip](https://xentaxbackup.github.io/file/11848_General_stream.zip)
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2016-10-29T04:00:57+00:00
- Post Title: Titanfall 2/Apex Legends

When I get time (and I'm not free like I was a few years ago) I will take a look at supporting that format and updating the VPK tool.
I need to buy the game too.
## Post #5
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-10-30T13:53:11+00:00
- Post Title: Titanfall 2/Apex Legends

awesome keep us up to date when you get time.
## Post #6
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-10-30T17:56:34+00:00
- Post Title: Titanfall 2/Apex Legends

> Reply from cra0
>
> When I get time (and I'm not free like I was a few years ago) I will take a look at supporting that format and updating the VPK tool.
I need to buy the game too.

i can give you my origin account to play it on so you can figure out the encryption. Be well worth it
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2016-10-31T02:39:34+00:00
- Post Title: Titanfall 2/Apex Legends

> Reply from iambosh
>
> cra0 wrote:When I get time (and I'm not free like I was a few years ago) I will take a look at supporting that format and updating the VPK tool.
I need to buy the game too.

i can give you my origin account to play it on so you can figure out the encryption. Be well worth it
pm me.
## Post #8
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-11-01T21:47:52+00:00
- Post Title: Titanfall 2/Apex Legends

I hope this helps 

Watching the game credits I've found out that the audio archive used is Miles Sound System by rad game tools [http://www.radgametools.com/miles.htm](http://www.radgametools.com/miles.htm) There was no information other than the software is coded in C and C++

nothing else about the archive was found....
## Post #9
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2016-11-02T03:25:09+00:00
- Post Title: Titanfall 2/Apex Legends

> Reply from durandal217
>
> I hope this helps 

Watching the game credits I've found out that the audio archive used is Miles Sound System by rad game tools http://www.radgametools.com/miles.htm There was no information other than the software is coded in C and C++

nothing else about the archive was found....
we know it uses miles when you look at the modules loaded in the client library 


Anyway I found that rtech_game.dll contains a export called Pak_SetLoadFuncs which is called when loading the PAK files which are compressed/encrypted/whatever
sub_180008C80 inside rtech_game

When I have a working copy Ill see if i can just call this function and pass it a pak file to get the output.
## Post #10
- Username: EnclaveTrooper
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 02, 2016 8:00 pm
- Post datetime: 2016-11-02T12:04:05+00:00
- Post Title: Titanfall 2/Apex Legends

How hard will it be too extract the IMC and Militia models from the game im very keen to port these models in Fallout 4
## Post #11
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-11-02T19:31:21+00:00
- Post Title: Titanfall 2/Apex Legends

> Reply from cra0
>
> durandal217 wrote:I hope this helps 

Watching the game credits I've found out that the audio archive used is Miles Sound System by rad game tools http://www.radgametools.com/miles.htm There was no information other than the software is coded in C and C++

nothing else about the archive was found....
we know it uses miles when you look at the modules loaded in the client library 


Anyway I found that rtech_game.dll contains a export called Pak_SetLoadFuncs which is called when loading the PAK files which are compressed/encrypted/whatever
sub_180008C80 inside rtech_game

When I have a working copy Ill see if i can just call this function and pass it a pak file to get the output.

yeah i really wanna get in and disable film grain and dof and force higher fov
## Post #12
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2016-11-07T03:00:32+00:00
- Post Title: Titanfall 2/Apex Legends

x64 assembly isn't really my strong suit so I might need a little help if anyone here wants to help.   

Titanfall 2 has

*VPK
*RPAK
*STARPAK

VPK fileformat hasn't changed since TitanFall 1 it still uses the modifed Valve format with lzham
compression.

RPAK contains a header which has a string to the starpak that contains the contents of its data
0x67 bytes in.

image base: 0x7FEE2880000

            sub_7FEE28831C0((__int64)&v43, 257i64, (__int64)"r2\\paks\\Win64\\%s", (__int64)v5);

is used to combine the paths to form a full path to the data

so for example.
paks\Win64\mp_homestead_loadscreen.rpak

contains starpak
paks\Win64\pc_all.starpak

sub_180008C80 inside rtech_game.dll loads the paks

dl: [http://cra0.net/rel/rtech_game.dll](http://cra0.net/rel/rtech_game.dll)

if anyone wants to take a look

```
{
    uint64  fileSize;
    uint32  flagA;
    uint32  flagB;
} pinfo_group1;

typedef struct
{
    uint64  valueA;
    uint32  flagA;
    uint32  flagB;
} generic_struct_group1;

typedef struct
{
    char	magic_sig[4];		//RPak
    int16	ver1;
    byte	opA;
    byte    opB_enabled;
    uint32  const_unkA;
    uint32  const_unkB;
    uint32  unkC;
    uint32  unkD;
    //uint32  fileSize;
    pinfo_group1 unk_gA;
    generic_struct_group1 unk_gB;
    uint16  unkE;
    uint16  unkF;
    uint16  unkG;
    uint16  unkH;
    uint32  unkI;
    uint32  unkJ;
    uint32  unkK;
    uint32  unkL;
    uint32  unkM;
    uint32  unkN;
    //generic_struct_group1 unk_gC;
    //generic_struct_group1 unk_gD;
    byte    idkA[15];
    string  starPackagePath;

} RPAKHeader; //header of file

struct
{
    char	magic_sig[4];		//SRPk
    int32	ver1;
    byte	alignPad[4088];
} STAR_PAKHeader; //header of file



```
## Post #13
- Username: alexio614
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 03, 2016 10:13 pm
- Post datetime: 2016-11-24T13:28:04+00:00
- Post Title: Titanfall 2/Apex Legends

any progress?
## Post #14
- Username: NIOS
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 13, 2016 6:18 pm
- Post datetime: 2016-12-13T10:23:01+00:00
- Post Title: Titanfall 2/Apex Legends

There seems to be a good amount of content in Titanfall2\r2\paks\Win64 (The rpak folder) that cannot be accessed by the dir_vpk's; including two ten gigabyte files. I bet there are sounds inside those... Also a lot of camo files, which is what I am trying to get into.
## Post #15
- Username: Tanagashi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 09, 2017 4:22 am
- Post datetime: 2017-01-08T20:27:58+00:00
- Post Title: Titanfall 2/Apex Legends

I would love to get access to the model files - I make armor and weapon prop replicas, and it would be nice to get proper measurements, proportions etc.
So hopefully cra0 will find the time to update the tool eventually.
## Post #16
- Username: DJMutagen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 19, 2014 2:23 am
- Post datetime: 2017-01-11T17:37:44+00:00
- Post Title: Re: Titanfall 2

hey, guys! any updates? I'm trying to access the bt and cooper dialogue audio. Gotten pretty good recordings through audio card and EQing some of the bg music out (i use samples for my own music), but they are still not the best quality or as isolated as I'm looking for. Also, anyone found a way to simply disable the campaign music? It's AMAZING and I understand why they don't have an in-game option; The music is freaking AMAZING and flows with the story. ANYWAY. Thanks for al your hard work, everyone!
## Post #17
- Username: alexio614
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 03, 2016 10:13 pm
- Post datetime: 2017-03-08T07:51:20+00:00
- Post Title: Re: Titanfall 2

Yea... seems like this game didn't get enough attention from the modding community (can't blame them either).
## Post #18
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2017-06-03T10:56:50+00:00
- Post Title: Re: Titanfall 2

Not sure if anyone saw it but there's some information about the purpose of .rpak and .starpak files in [http://twvideo01.ubm-us.net/o1/vault/gd ... eaming.pdf](http://twvideo01.ubm-us.net/o1/vault/gdc2017/Presentations/Barb_Chad_EfficientTextureStreaming.pdf)
Looks like they store some sort of texture data for performance.
## Post #19
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2017-06-21T03:50:35+00:00
- Post Title: Re: Titanfall 2

> Reply from tschumann
>
> Not sure if anyone saw it but there's some information about the purpose of .rpak and .starpak files in http://twvideo01.ubm-us.net/o1/vault/gd ... eaming.pdf
Looks like they store some sort of texture data for performance.
I do plan on having another look at them when I have free time.
## Post #20
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2017-12-18T12:58:58+00:00
- Post Title: Re: Titanfall 2

Hi. I've been fiddling with rtech_game.dll for quite a while. Now I'm relatively new to reversing so the work doesn't really go that fast. But I managed to find functions that manage data chunks and the actual rpak decoder. So if anyone is interested (cra0?), I can provide functions' file offsets and basic explanations of what part does what. I reverse in x64dbg so I can even provide database with comments and functions (but it's a mess with my own notations). I yet have to polish the decoder ported code (written in python) and figure out where and how does unpacked data go.
## Post #21
- Username: Wanty
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 04, 2018 9:43 pm
- Post datetime: 2018-03-04T16:29:14+00:00
- Post Title: Re: Titanfall 2

I'm curious to see what you done around that.
## Post #22
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-03-17T05:32:57+00:00
- Post Title: Re: Titanfall 2

> Reply from Tushkan
>
> Hi. I've been fiddling with rtech_game.dll for quite a while. Now I'm relatively new to reversing so the work doesn't really go that fast. But I managed to find functions that manage data chunks and the actual rpak decoder. So if anyone is interested (cra0?), I can provide functions' file offsets and basic explanations of what part does what. I reverse in x64dbg so I can even provide database with comments and functions (but it's a mess with my own notations). I yet have to polish the decoder ported code (written in python) and figure out where and how does unpacked data go.

Yeah any more details would be good.
## Post #23
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-02-07T10:46:10+00:00
- Post Title: Re: Titanfall 2

Looks like Apex Legends might use the same formats as Titanfall 2. Anyone made any progress with .rpak, .starpak or .stbsp files?
## Post #24
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-02-10T06:58:08+00:00
- Post Title: Re: Titanfall 2

I've had a very brief look at some .stbsp files - the start of header seems to be as follows:

```
__int16 iMajorVersion;
__int16 iMinorVersion;

```


Titanfall 2 has v8.0 and Apex Legends has v8.1 by the looks of it.
## Post #25
- Username: loongers111
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 09, 2019 2:37 pm
- Post datetime: 2019-02-13T01:17:44+00:00
- Post Title: Re: Titanfall 2

> Reply from tschumann
>
> I've had a very brief look at some .stbsp files - the start of header seems to be as follows:
Code: Select all__int32 iMagicNumber;
__int16 iMajorVersion;
__int16 iMinorVersion;


Titanfall 2 has v8.0 and Apex Legends has v8.1 by the looks of it.

the Apex .rpak files also look like v8.1, but not sure the compression method of this kind of files
## Post #26
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2019-02-14T03:12:17+00:00
- Post Title: Re: Titanfall 2

I'm trying to form some sort of discipline and get back into this stuff.

Last I recall titanfall2 .rpak was encrypted or packed with a unique compression method.
I'll purchase the game this weekend and have a look.
## Post #27
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2019-02-14T05:49:33+00:00
- Post Title: Re: Titanfall 2

> Reply from cra0
>
> I'm trying to form some sort of discipline and get back into this stuff.

Last I recall titanfall2 .rpak was encrypted or packed with a unique compression method.
I'll purchase the game this weekend and have a look.

Or you can download apex legends, it's free and it's using 8.1 of the titanfall 2 engine.
## Post #28
- Username: loongers111
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 09, 2019 2:37 pm
- Post datetime: 2019-02-14T09:29:28+00:00
- Post Title: Re: Titanfall 2

> Reply from cra0
>
> I'm trying to form some sort of discipline and get back into this stuff.

Last I recall titanfall2 .rpak was encrypted or packed with a unique compression method.
I'll purchase the game this weekend and have a look.

I have this game and can send the link to you if you wish.
The rpak file might contains the index , and the decompress routine is in the 180004B80 and 180004EA0
4b80 is the function to determin the decompress size, and 4ea0 seems like the real decompress routine,
but I could not get its real content after decompress, it seems still encrypted or something.
## Post #29
- Username: mads059k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 20, 2019 5:07 pm
- Post datetime: 2019-02-20T14:28:03+00:00
- Post Title: Re: Titanfall 2

Any news on this topic?
Has anyone found a way to datamine Apex legends yet?
## Post #30
- Username: eg0npro1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 24, 2019 10:47 pm
- Post datetime: 2019-02-24T14:52:19+00:00
- Post Title: Re: Titanfall 2

> Reply from cra0 ↑Thu Feb 14, 2019 11:12 am at Thu Feb 14, 2019 11:12 am
>
> 
I'm trying to form some sort of discipline and get back into this stuff.

Last I recall titanfall2 .rpak was encrypted or packed with a unique compression method.
I'll purchase the game this weekend and have a look.

I think it would be better to download Apex Legends at this point, as the most assets are now stored in .rpak and .starpak files, i tried opening some .vpks but nothing useful is there.
## Post #31
- Username: analblaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 17, 2015 5:05 pm
- Post datetime: 2019-02-27T17:38:17+00:00
- Post Title: Re: Titanfall 2/Apex Legends

If anyone hasn't already noticed, the current version of Cra0's VPK tool can't extract a lot of changed files from Apex Legends, and repacked VPKs don't seem to want to work at all right now. There seem to still be some people on twitter opening the stuff that it can't extract though, is there another tool floating around out there or are they just working it out themselves?

> Reply from cra0 ↑Thu Feb 14, 2019 11:12 am at Thu Feb 14, 2019 11:12 am
>
> 
I'm trying to form some sort of discipline and get back into this stuff.

Last I recall titanfall2 .rpak was encrypted or packed with a unique compression method.
I'll purchase the game this weekend and have a look.
Perfect news to see.
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-05T15:52:58+00:00
- Post Title: Re: Titanfall 2/Apex Legends

You can use the following BMS commands to unpack the starpak archives:

```
goto -8 0 SEEK_END
savepos entryOffset
get entryCount longlong
set entrySize longlong entryCount
math entrySize * 0x10
math entryOffset - entrySize
log MEMORY_FILE entryOffset entrySize
get Path basename
for i = 0 < entryCount
	get Offset longlong MEMORY_FILE
	get Size longlong MEMORY_FILE
	goto Offset
	get Magic longlong
	set Flag longlong Size
	math Flag & 0x0FFF
	if Magic == 0x1800000007
		set Ext string ".msh"
	elif Flag == 0
		set Ext string ".tex"
	else
		set Ext string ".dat"
	endif
	set Name string ""
	string Name p "%s/%08d%s" Path i Ext
	log Name Offset Size
next i

```

The only problem is files are output without names so there's a simple detection for the extesions.
The mesh format this game use has some optimizations on the vertex data so there're extra work to do to convert them to common format. Some simple mesh is easy to extract though.



msh.jpg (152.17 KiB) Viewed 471 times
## Post #33
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2019-03-05T20:13:07+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from Bigchillghost ↑Tue Mar 05, 2019 11:52 pm at Tue Mar 05, 2019 11:52 pm
>
> 
You can use the following BMS commands to unpack the starpak archives:
Code: Select allidstring "SRPk" # starpak
goto -8 0 SEEK_END
savepos entryOffset
get entryCount longlong
set entrySize longlong entryCount
math entrySize * 0x10
math entryOffset - entrySize
log MEMORY_FILE entryOffset entrySize
get Path basename
for i = 0 < entryCount
	get Offset longlong MEMORY_FILE
	get Size longlong MEMORY_FILE
	goto Offset
	get Magic longlong
	set Flag longlong Size
	math Flag & 0x0FFF
	if Magic == 0x1800000007
		set Ext string ".msh"
	elif Flag == 0
		set Ext string ".tex"
	else
		set Ext string ".dat"
	endif
	set Name string ""
	string Name p "%s/%08d%s" Path i Ext
	log Name Offset Size
next i

The only problem is files are output without names so there's a simple detection for the extesions.
The mesh format this game use has some optimizations on the vertex data so there're extra work to do to convert them to common format. Some simple mesh is easy to extract though.

NICE! Any progress/chance we can get a BMS script to unpack the .MSTR archives?
## Post #34
- Username: mads059k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 20, 2019 5:07 pm
- Post datetime: 2019-03-12T11:07:14+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from Bigchillghost ↑Tue Mar 05, 2019 11:52 pm at Tue Mar 05, 2019 11:52 pm
>
> 
You can use the following BMS commands to unpack the starpak archives:
Code: Select allidstring "SRPk" # starpak
goto -8 0 SEEK_END
savepos entryOffset
get entryCount longlong
set entrySize longlong entryCount
math entrySize * 0x10
math entryOffset - entrySize
log MEMORY_FILE entryOffset entrySize
get Path basename
for i = 0 < entryCount
	get Offset longlong MEMORY_FILE
	get Size longlong MEMORY_FILE
	goto Offset
	get Magic longlong
	set Flag longlong Size
	math Flag & 0x0FFF
	if Magic == 0x1800000007
		set Ext string ".msh"
	elif Flag == 0
		set Ext string ".tex"
	else
		set Ext string ".dat"
	endif
	set Name string ""
	string Name p "%s/%08d%s" Path i Ext
	log Name Offset Size
next i

The only problem is files are output without names so there's a simple detection for the extesions.
The mesh format this game use has some optimizations on the vertex data so there're extra work to do to convert them to common format. Some simple mesh is easy to extract though.
msh.jpg

What program do you use for opening .msh files?
## Post #35
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-12T15:38:06+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from mads059k ↑Tue Mar 12, 2019 7:07 pm at Tue Mar 12, 2019 7:07 pm
>
> 
What program do you use for opening .msh files?
It's hex2obj that I used to load one of the meshes. But thing is getting more complicated than I expected. Might take a little while to figure out the relation between the vertex IDs and the data.
## Post #36
- Username: FunGames
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 01, 2018 12:46 am
- Post datetime: 2019-03-12T16:59:33+00:00
- Post Title: Re: Titanfall 2/Apex Legends

How would you read the tex files? Is it a dxt format or sth else?
## Post #37
- Username: silverm9
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 12, 2018 8:39 pm
- Post datetime: 2019-03-12T21:44:05+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from FunGames ↑Wed Mar 13, 2019 12:59 am at Wed Mar 13, 2019 12:59 am
>
> 
How would you read the tex files? Is it a dxt format or sth else?

The textures seem to be DXT for the most part
## Post #38
- Username: mads059k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 20, 2019 5:07 pm
- Post datetime: 2019-03-13T08:13:02+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from silverm9 ↑Wed Mar 13, 2019 5:44 am at Wed Mar 13, 2019 5:44 am
>
> 
FunGames wrote: ↑Wed Mar 13, 2019 12:59 am
How would you read the tex files? Is it a dxt format or sth else?


The textures seem to be DXT for the most part

But how did you open them?
## Post #39
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-14T12:53:16+00:00
- Post Title: Re: Titanfall 2/Apex Legends

The latest progress:


All LODs:
## Post #40
- Username: exhaleme
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 10, 2017 10:59 am
- Post datetime: 2019-03-14T20:07:11+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Legion has been released for Apex by DTZxPorter & id-daemon: [https://wiki.modme.co/wiki/apps/Legion.html](https://wiki.modme.co/wiki/apps/Legion.html)

Models + textures and eventually animations.

Fully rigged + materials in SEModel, OBJ, SMD, XNALara Text, XNALara Binary.
SETools: [https://github.com/dtzxporter/SETools](https://github.com/dtzxporter/SETools)
## Post #41
- Username: BigBangYourMother
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:33 am
- Post datetime: 2019-03-15T02:36:42+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from exhaleme ↑Fri Mar 15, 2019 4:07 am at Fri Mar 15, 2019 4:07 am
>
> 
Legion has been released for Apex by DTZxPorter & id-daemon: https://wiki.modme.co/wiki/apps/Legion.html

Models + textures and eventually animations.

Fully rigged + materials in SEModel, OBJ, SMD, XNALara Text, XNALara Binary.
SETools: https://github.com/dtzxporter/SETools

So ive unpacked the starpack files and as asked above all the files are .tex or .msh. How does the Autodesk + the plugins open these files? Usually pretty good with this stuff but im stumped
## Post #42
- Username: exhaleme
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 10, 2017 10:59 am
- Post datetime: 2019-03-15T02:57:08+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from BigBangYourMother ↑Fri Mar 15, 2019 10:36 am at Fri Mar 15, 2019 10:36 am
>
> 
So ive unpacked the starpack files and as asked above all the files are .tex or .msh. How does the Autodesk + the plugins open these files? Usually pretty good with this stuff but im stumped

This is completely useless, follow the instructions on usage of Legion from the link, it uses the rpaks to extract all the assets. The starpaks are merely a bank of data which is used by the rpaks.
## Post #43
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-15T12:09:06+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from BigBangYourMother ↑Fri Mar 15, 2019 10:36 am at Fri Mar 15, 2019 10:36 am
>
> So ive unpacked the starpack files and as asked above all the files are .tex or .msh.
Here is a msh to FBX convertor if it's needed. All meshes of all LODs are preserved and grouped like this in a scene:



Tested on msh files from pc_all(01).starpak only.
[mshConv.zip](https://xentaxbackup.github.io/file/15898_mshConv.zip)
## Post #44
- Username: BigBangYourMother
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:33 am
- Post datetime: 2019-03-15T12:27:49+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from Bigchillghost ↑Fri Mar 15, 2019 8:09 pm at Fri Mar 15, 2019 8:09 pm
>
> 
BigBangYourMother wrote: ↑Fri Mar 15, 2019 10:36 amSo ive unpacked the starpack files and as asked above all the files are .tex or .msh.

Here is a msh to FBX convertor if it's needed. All meshes of all LODs are preserved and grouped like this in a scene:



Tested on msh files from pc_all(01).starpak only.

this is what i was after! thanks.
## Post #45
- Username: mads059k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 20, 2019 5:07 pm
- Post datetime: 2019-03-15T16:49:11+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from Bigchillghost ↑Fri Mar 15, 2019 8:09 pm at Fri Mar 15, 2019 8:09 pm
>
> 
BigBangYourMother wrote: ↑Fri Mar 15, 2019 10:36 amSo ive unpacked the starpack files and as asked above all the files are .tex or .msh.

Here is a msh to FBX convertor if it's needed. All meshes of all LODs are preserved and grouped like this in a scene:



Tested on msh files from pc_all(01).starpak only.

But is it possible to apply the textures to the models yet? And if so  how?
## Post #46
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-15T23:48:03+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from mads059k ↑Sat Mar 16, 2019 12:49 am at Sat Mar 16, 2019 12:49 am
>
> 
But is it possible to apply the textures to the models yet?
It's not. The tex files contain merely raw pixel data without any header and it's unlikely to determine the height and width and the pixel format based on the file size. You may use the tool that deals with the rpak arcs mentioned above to get the textures, and models if you'd like to.
## Post #47
- Username: BigBangYourMother
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:33 am
- Post datetime: 2019-03-16T02:14:05+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from Bigchillghost ↑Sat Mar 16, 2019 7:48 am at Sat Mar 16, 2019 7:48 am
>
> 
mads059k wrote: ↑Sat Mar 16, 2019 12:49 am
But is it possible to apply the textures to the models yet? 

It's not. The tex files contain merely raw pixel data without any header and it's unlikely to determine the height and width and the pixel format based on the file size. You may use the tool that deals with the rpak arcs mentioned above to get the textures, and models if you'd like to.

So its not possible to add textures to models? How have i seen others do it?
## Post #48
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-16T07:25:11+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from BigBangYourMother ↑Sat Mar 16, 2019 10:14 am at Sat Mar 16, 2019 10:14 am
>
> So its not possible to add textures to models? How have i seen others do it?
Cause they're not dealing with the files taken directly from the starpak arcs. While the msh files generated with my script contain enough info to convert the assets within, however, the tex files have no info about the image formats. Of course if you treat all of them as the same format you can guess the resolutions based on the size, and deal with the false results later. But that would be an ugly workflow and it's not worth the effort. My tool is only designed to be a quick approach to get the models, though I might add some other features in the future. So as stated earlier,

> Reply from Bigchillghost ↑Sat Mar 16, 2019 7:48 am at Sat Mar 16, 2019 7:48 am
>
> You may use the tool that deals with the rpak arcs mentioned above to get the textures, and models if you'd like to.
## Post #49
- Username: analblaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 17, 2015 5:05 pm
- Post datetime: 2019-03-19T17:14:38+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Hate to be a broken record, but while all the progress in the last week or so on the RPAKs is really good, I gotta ask again if anyone's made any headway regarding the VPK's? :V
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-08T05:05:12+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Animation export added. Now everything is supported in this game.

[https://wiki.modme.co/wiki/apps/Legion.html](https://wiki.modme.co/wiki/apps/Legion.html)
## Post #51
- Username: frezixx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 30, 2017 6:35 pm
- Post datetime: 2019-04-10T07:35:27+00:00
- Post Title: Re: Titanfall 2/Apex Legends

any news about the other texture maps? i.e. normal maps and such
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-10T07:47:31+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from frezixx ↑Wed Apr 10, 2019 3:35 pm at Wed Apr 10, 2019 3:35 pm
>
> 
any news about the other texture maps? i.e. normal maps and such

what are you talking about? all textures, including normal maps and all other types are extracted by the tool a month ago!
## Post #53
- Username: frezixx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 30, 2017 6:35 pm
- Post datetime: 2019-04-10T11:12:54+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from daemon1 ↑Wed Apr 10, 2019 3:47 pm at Wed Apr 10, 2019 3:47 pm
>
> 
frezixx wrote: ↑Wed Apr 10, 2019 3:35 pm
any news about the other texture maps? i.e. normal maps and such


what are you talking about? all textures, including normal maps and all other types are extracted by the tool a month ago!

some maps are just blank white solid images when i export them
[Screenshot_1.png](https://xentaxbackup.github.io/file/16014_Screenshot_1.png)
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-10T12:14:05+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from frezixx ↑Wed Apr 10, 2019 7:12 pm at Wed Apr 10, 2019 7:12 pm
>
> 
daemon1 wrote: ↑Wed Apr 10, 2019 3:47 pm
frezixx wrote: ↑Wed Apr 10, 2019 3:35 pm
any news about the other texture maps? i.e. normal maps and such


what are you talking about? all textures, including normal maps and all other types are extracted by the tool a month ago!


some maps are just blank white solid images when i export them

supposed to be very small amount of these. Do you have many? Can you send example?
## Post #55
- Username: frezixx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 30, 2017 6:35 pm
- Post datetime: 2019-04-10T16:31:27+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from daemon1 ↑Wed Apr 10, 2019 8:14 pm at Wed Apr 10, 2019 8:14 pm
>
> 
frezixx wrote: ↑Wed Apr 10, 2019 7:12 pm
daemon1 wrote: ↑Wed Apr 10, 2019 3:47 pm


what are you talking about? all textures, including normal maps and all other types are extracted by the tool a month ago!


some maps are just blank white solid images when i export them


supposed to be very small amount of these. Do you have many? Can you send example?

yee some are just these blank .dds files not just a few, i've been looking for the normal maps of some weapons and they're not there. Maybe im doing something wrong?
[Screenshot_2.jpg](https://xentaxbackup.github.io/file/16016_Screenshot_2.jpg)
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-10T16:44:07+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from frezixx ↑Thu Apr 11, 2019 12:31 am at Thu Apr 11, 2019 12:31 am
>
> Maybe im doing something wrong?

yes, google how to open DX10 DDS
## Post #57
- Username: droads
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 02, 2016 12:57 am
- Post datetime: 2019-04-12T20:46:00+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Any chances for animation from TF2? 
Some weapons, equipment, titans..
Models from apex and tf2 don't have identical structures?
## Post #58
- Username: prayeriz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 16, 2015 10:16 pm
- Post datetime: 2019-04-16T09:45:09+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from daemon1 ↑Mon Apr 08, 2019 1:05 pm at Mon Apr 08, 2019 1:05 pm
>
> 
Animation export added. Now everything is supported in this game.

https://wiki.modme.co/wiki/apps/Legion.html

Do you plan to document the rpak format?
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-16T15:40:59+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from prayeriz ↑Tue Apr 16, 2019 5:45 pm at Tue Apr 16, 2019 5:45 pm
>
> 
Do you plan to document the rpak format?

no
## Post #60
- Username: Azhora
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 19, 2019 1:22 am
- Post datetime: 2019-04-18T17:33:25+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Very excited to see the development in this topic and the Legion software!

Is there any support for .stbsp unpacking planned?
## Post #61
- Username: Juso87
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 29, 2017 6:05 pm
- Post datetime: 2019-04-19T13:46:09+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from frezixx ↑Wed Apr 10, 2019 3:35 pm at Wed Apr 10, 2019 3:35 pm
>
> 
any news about the other texture maps? i.e. normal maps and such

I had to use --imgfmt=png to get normal maps and the like to work.
## Post #62
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-05-06T04:21:31+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from analblaze ↑Thu Feb 28, 2019 1:38 am at Thu Feb 28, 2019 1:38 am
>
> 
If anyone hasn't already noticed, the current version of Cra0's VPK tool can't extract a lot of changed files from Apex Legends, and repacked VPKs don't seem to want to work at all right now. There seem to still be some people on twitter opening the stuff that it can't extract though, is there another tool floating around out there or are they just working it out themselves?

Which files can't be extracted?
## Post #63
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2019-05-07T00:33:00+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from tschumann ↑Mon May 06, 2019 12:21 pm at Mon May 06, 2019 12:21 pm
>
> 
analblaze wrote: ↑Thu Feb 28, 2019 1:38 am
If anyone hasn't already noticed, the current version of Cra0's VPK tool can't extract a lot of changed files from Apex Legends, and repacked VPKs don't seem to want to work at all right now. There seem to still be some people on twitter opening the stuff that it can't extract though, is there another tool floating around out there or are they just working it out themselves?


Which files can't be extracted?

The tool parsers what the TOC has, some of the data streams I believe are different than Titanfall 1, I haven't updated the tool in many years.
## Post #64
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-05-11T11:38:16+00:00
- Post Title: Re: Titanfall 2/Apex Legends

If they're still v2.3 .vpk files then maybe the compression or something has changed.
This was what I figured out for the entry structure:

```
	{
		unsigned __int32 iCRC32;
		unsigned __int16 iUnknown1; // always 0?
		unsigned __int16 iArchiveIndex;
		unsigned __int16 iUnknown2; // usually 257, sometimes 1
		unsigned __int32 iUnknown3; // usuaully 0, sometimes 16, sometimes >524000
		unsigned __int32 iEntryOffset;
		unsigned __int32 iUnknown4; // always 0?
		unsigned __int32 iEntryLength; // compressed data size
		unsigned __int32 iUnknown5; // always 0?
		unsigned __int32 iFileSize; // uncompressed file size
		unsigned __int32 iUnknown6; // always 0?
	};

```

I guess one of the unknown fields will be different.
## Post #65
- Username: damndoe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 13, 2019 9:14 am
- Post datetime: 2019-12-30T05:31:09+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from Bigchillghost ↑Tue Mar 05, 2019 11:52 pm at Tue Mar 05, 2019 11:52 pm
>
> 
You can use the following BMS commands to unpack the starpak archives:
Code: Select allidstring "SRPk" # starpak
goto -8 0 SEEK_END
savepos entryOffset
get entryCount longlong
set entrySize longlong entryCount
math entrySize * 0x10
math entryOffset - entrySize
log MEMORY_FILE entryOffset entrySize
get Path basename
for i = 0 < entryCount
	get Offset longlong MEMORY_FILE
	get Size longlong MEMORY_FILE
	goto Offset
	get Magic longlong
	set Flag longlong Size
	math Flag & 0x0FFF
	if Magic == 0x1800000007
		set Ext string ".msh"
	elif Flag == 0
		set Ext string ".tex"
	else
		set Ext string ".dat"
	endif
	set Name string ""
	string Name p "%s/%08d%s" Path i Ext
	log Name Offset Size
next i

The only problem is files are output without names so there's a simple detection for the extesions.
The mesh format this game use has some optimizations on the vertex data so there're extra work to do to convert them to common format. Some simple mesh is easy to extract though.
msh.jpg
Hey Ghost, any chance you could update your script? I do nit believe it works correctly anymore.
## Post #66
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-02-21T23:13:38+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Did anyone ever make tools for Titanfall 2 RPAK and STARPAKS?
## Post #67
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-02-23T14:19:20+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Okay tried the BMS script above. Seems to work, but no file names means i'd probably be better just using ninjaripper...
## Post #68
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-21T15:40:25+00:00
- Post Title: Re: Titanfall 2/Apex Legends

To those of you that are interested in both these games that are being talked about in here.
Titanfall 2 finally got some love from Porter, and it looks like it has support now.
I personally haven't tested it yet, but I thought you guys might want to know.
[https://wiki.modme.co/wiki/apps/Legion.html](https://wiki.modme.co/wiki/apps/Legion.html)

```
•2.10 - Support for Titanfall 2 (Models, Animations, RPaks, Sounds).
```
## Post #69
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-03-22T19:43:22+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Thanks mono24 for the information

Textures extracted using Legion [PNG selected], models extracted with the VPK Tool [MDL converted to SMD with Crowbar].

All working well within 3D software.

Much appreciated
## Post #70
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-03-24T09:10:07+00:00
- Post Title: Re: Titanfall 2/Apex Legends

I have found an issue with the Legion rpak extraction:

Setting to extract using DDS, PNG or TIFF the alpha maps or channel does not appear.

After checking the folder named Images containing 4,558 items, I managed to find an alpha I needed for the 'pilot_heavy_drex_ghullie_skin_01'
## Post #71
- Username: theRAIN
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 14, 2020 2:25 am
- Post datetime: 2020-04-13T18:48:00+00:00
- Post Title: Re: Titanfall 2/Apex Legends

hey guys does anyone knows where the game code is stored, i want to look at the movement system, never done any reverse engineering so here is my first step
## Post #72
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2020-05-24T10:01:37+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Any examples of the Apex Legends .vpk files that won't extract? I did a spot check of what was in englishclient_frontend.bsp.pak000_dir.vpk and they seemed to extract okay.

> Reply from theRAIN ↑Tue Apr 14, 2020 2:48 am at Tue Apr 14, 2020 2:48 am
>
> 
hey guys does anyone knows where the game code is stored, i want to look at the movement system, never done any reverse engineering so here is my first step

I think it's in r5apex.exe but I'm not sure.
## Post #73
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2023-03-26T06:53:43+00:00
- Post Title: Re: Titanfall 2/Apex Legends

Looks like [https://wiki.modme.co/wiki/apps/Legion.html](https://wiki.modme.co/wiki/apps/Legion.html) can open some of the new file types. I haven't tried it.
## Post #74
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2023-05-20T10:26:33+00:00
- Post Title: Re: Titanfall 2/Apex Legends

There's a .rpak extractor now: [https://wiki.modme.co/wiki/apps/Legion.html](https://wiki.modme.co/wiki/apps/Legion.html)

I think it's open source too.
## Post #75
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-20T13:38:30+00:00
- Post Title: Re: Titanfall 2/Apex Legends

> Reply from tschumann ↑Sat May 20, 2023 6:26 pm at Sat May 20, 2023 6:26 pm
>
> 
There's a .rpak extractor now: https://wiki.modme.co/wiki/apps/Legion.html

I think it's open source too.
I believe that is abandoned now for quite a while, and not once have i seen source code released either.
