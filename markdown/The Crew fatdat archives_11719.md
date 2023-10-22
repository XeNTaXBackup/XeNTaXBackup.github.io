## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-22T17:17:40+00:00
- Post Title: The Crew fat/dat archives

The closed beta started today and it lasts until the 25th.

Once again we have fat & dat pairs, with FAT2 header like in Far Cry 3. Dunia2 tools don't work, but with any luck they'll only need slight modifications.
The game engine is suposedly called Babel. Not sure to what extent it might be a variation of Dunia, or something new built from the ground up by Ivory Tower.
L.E. Geometry files have the same structure as Far Cry 3, but it seems as though it pre-dates it in terms of development. Not only is the file version is lower, but it also features slightly less data.

Fair warning: the game is still beta. Please don't upload or post any files here, not even external links.

Status report:
aluigi released a quickbms script for "raw" unpacking (no file names)
http://aluigi.org/papers/bms/fat2_fat3.bms
Ekey released The Crew DAT Unpacker currently at ver. 0.0.2a_r2
https://www.sendspace.com/file/l0lxx0
and also an updated filelist
download/file.php?id=7633
I'm currently working on a maxscript for importing models: viewtopic.php?p=91256#p91256
## Post #2
- Username: MrYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 11, 2013 5:42 pm
- Post datetime: 2014-07-26T00:42:50+00:00
- Post Title: The Crew fat/dat archives

Strange: The .dat files weren't compressed or encrypted. You can see plaintext. But it looks like the files are mixed together.
Unfortunately, I can't compare it to FC3 because I don't have it. Is there some documentation about the FC3 format?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-26T05:19:00+00:00
- Post Title: The Crew fat/dat archives

Can someone share client? > PM please.
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-26T07:05:34+00:00
- Post Title: The Crew fat/dat archives

@MrYeah they don't seem "plain" to me. At least in vehicles.dat I can't see any 3d geometry data. They are at least compressed.
The fat header size is the same as Watch Dogs, posted by Ekey [here](http://forum.xentax.com/viewtopic.php?p=94816#p94816), except it's FAT2 and version is 5

```
{
   DWORD   dwID; // 2TAF
   DWORD   dwVersion; // Always = 5
   DWORD   dwUnknown; // Always = 1
   DWORD   dwTotalFiles;
};
```


but each file entry is 24 bytes in size

@Ekey check PM
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-26T12:05:08+00:00
- Post Title: The Crew fat/dat archives

hash is _int64 > CRC64
## Post #6
- Username: MrYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 11, 2013 5:42 pm
- Post datetime: 2014-07-26T21:24:19+00:00
- Post Title: The Crew fat/dat archives

@Ekey: Nice find.

@Chipicao:
You can see some XML in startup.dat, some parts of English sentences in localization.dat and DDS textures compressed with DXT5 like in greatcanyon.dat.
If the geometry data of the cars is compressed, it's not part of the fat/dat format.
## Post #7
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-07-27T02:18:42+00:00
- Post Title: The Crew fat/dat archives

We should try to get the game to play after beta time.
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-27T08:57:26+00:00
- Post Title: The Crew fat/dat archives

@MrYeah Nope. That's how this compression type works. You can see glimpses of file headers and plain-text file markers, but everything else is compressed.
It was the same with Far Cry 3. Here, have a look at an unpacked xbg and how you see it in fc3_main.dat:
[](http://www.imagebam.com/image/c61aa3341373861) 

It's the same thing with those files you mentioned. You're not seeing uncompressed data, just small pieces. Try to snip out that DDS texture and you'll see it doesn't work.
The good news is that Crew xgb file structure seems almost identical to Far Cry 3, which means my import script might work with little to no modifications.  But I'll only know for sure when we have an unpacker.

@d875j Maybe you should move warez talk someplace else...
## Post #9
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-07-27T12:02:00+00:00
- Post Title: The Crew fat/dat archives

> Reply from Chipicao
>
> @d875j Maybe you should move warez talk someplace else...
Warez? How if the beta is free? All i'm saying i want to play it after the beta period i will buy game but still.
## Post #10
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-27T12:24:41+00:00
- Post Title: The Crew fat/dat archives

Getting the beta to work after it has expired is like making a crack. Period.

Also, you don't need to quote my entire post just to reply to a single phrase. You're just making a mess...
## Post #11
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-07-27T12:39:47+00:00
- Post Title: The Crew fat/dat archives

> Reply from Chipicao
>
> Getting the beta to work after it has expired is like making a crack. Period.

Also, you don't need to quote my entire post just to reply to a single phrase. You're just making a mess...
Sorry but i don't think so at all.It's not like a crack period.People ripping models and ect is kinda wrong but people do it.Any ways as i said i enjoyed game and want to play it while i wait for the game to be released.
## Post #12
- Username: Speeder
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 05, 2011 4:17 am
- Post datetime: 2014-07-27T12:47:08+00:00
- Post Title: The Crew fat/dat archives

I don't think it's even possible or it would be really too much work for that (afaik savegames are server sided and some features of the game as well, plus memory dumping seems buggy from what I've tried).

Also I dumped every launch options available, can I post those there? (for the ini file, didnt test but seems there is interesting stuff if it's still enabled)
## Post #13
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-27T13:14:32+00:00
- Post Title: The Crew fat/dat archives

@d875j Think again. To make the beta work you would have to modify the exe and bypass all the checks and connections it does with uplay and the game servers. That's a crack, so let's stop talking about this.

@Speeder Please do, I'm curious to see what you found.
## Post #14
- Username: Speeder
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 05, 2011 4:17 am
- Post datetime: 2014-07-27T13:25:53+00:00
- Post Title: The Crew fat/dat archives

```
INPUT_ON_BACKGROUND
SOUND_ON_BACKGROUND
FORCE_TRACKING
VERBOSE_TRACKING
SYSTEM_PROFILING_TRACKING
CHECK_LOCA
CUV
USE_WHEEL
NO_PAD_VIB
PATCHARCHIVE
USEEDITIONDATA
PC_VERSION
PCGame
UPLAYPC
STEAMPC
RENDERQUALITY (low-medium-high-ultrahigh-durango-orbis-console(=x360 leftover settings?))
DISABLE_CAMERA_CONTROL_MOUSE
VSYNC
AUTO_LOGIN
NO_SOLO
SERVER
FREERIDE
LOGIN
PASSWORD
RB_IP
RB_PORT
PROXY_IP
PROXY_PORT
PVP
TV
SAVE
AFFINITY
NO_ASYNCH_MODE
PC_BETA
```


I'm not sure how those are supposed to work (I tried to enable the verbose tracking but I didn't find any log... it might be setup for a remote debugger?) and if those aren't supposed to be in the Config.xml file... Time to try and try I guess.  

EDIT: list of every server config available (didnt test all of those, but I doubt there is any offline or serverless config):

```
//note: exp might be experimental; ext external; vm virtual machine; uat the QA service of Ubisoft; mtl is for Montreal (internal ubi test I assume); 
work
release
release_ext
milestone
loadtest
mtl
dev
ludo
vm01 to vm18
beta01 to beta09
vm01exp to vm18exp
beta01exp to beta09exp
closedbeta //closed beta official server
closeduat
buat01 to buat09
scalabilityLT
scalabilityLTexp
closedbetapp1
closeduatpp1
```
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-31T18:07:25+00:00
- Post Title: The Crew fat/dat archives

```
{
   DWORD   dwZSize; // i guess ???
   DWORD   dwUnknown; // Just zero - dwZSize maybe int64 ???
   __int64 dwHash;
   DWORD   dwSize;
   DWORD   dwOffset;
};
```


```
FATEntry.dwOffset := (FATEntry.dwOffset << 2) |= (FATEntry.dwOffset & $C0000000) >> 30;
```
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-01T10:34:18+00:00
- Post Title: Re: The Crew fat/dat archives

File types

```
- <ResourceConfig>
  <Resource Class="CGeometryResource" SourceExt=".glm" TargetExt=".xbg" Compiler="GeomCompiler" DependsOf=".wb.entities.bin;.entities.bin;.bar;.bse" /> 
  <Resource Class="CMaterialResource" SourceExt=".material.xml" TargetExt=".material.bin" Compiler="MaterialCompiler" DependsOf=".xbg" /> 
  <Resource Class="CTextureResource" SourceExt=".png;.dds" TargetExt=".xbt" Compiler="TexCompiler" DependsOf=".material.bin;.bar;.bse;.wb.entities.bin;.entities.bin" /> 
  <Resource Class="CSkeletonResource" SourceExt=".skel.xml" TargetExt=".skeleton" Compiler="Scene2Skeleton" DependsOf=".wb.entities.bin;.entities.bin" /> 
  <Resource Class="CAnimationResource" SourceExt=".mac" TargetExt=".mab" CompileDependency=".mkai;.mks;.mkfx" Compiler="Packman" DependsOf=".wb.entities.bin;.entities.bin;.bac" /> 
  <Resource Class="AreaResource" SourceExt=".xar" TargetExt=".bar" Compiler="WorldCompiler" /> 
  <Resource Class="SectorResource" SourceExt=".xse" TargetExt=".bse" Compiler="WorldCompiler" DependsOf=".bar" /> 
  <Resource Class="CHeightMapResource" SourceExt=".hmg" TargetExt=".hms" Compiler="HeightFieldCompiler" DependsOf=".bar;.bse" /> 
  <Resource Class="CAudioEventResource" SourceExt=".fdp" TargetExt=".fev" Compiler="AudioCompiler" DependsOf=".wb.entities.bin;.entities.bin;.bac" /> 
  <Resource Class="CSoundBankResource" SourceExt=".wav;.fsproj" TargetExt=".fsb" Compiler="AudioCompiler" DependsOf=".wb.entities.bin;.entities.bin;.bac" /> 
  <Resource Class="FlashResource" SourceExt=".swf" TargetExt=".bwf" Compiler="FlashCompiler" DependsOf=".wb.entities.bin;.entities.bin" /> 
  <Resource Class="CPhysResource" SourceExt=".hkr;.rcg" TargetExt=".hkx" Compiler="PhysCompiler" DependsOf=".wb.entities.bin;.entities.bin;.xbg;.bar;.bse" /> 
  <Resource Class="NavResource" SourceExt=".nav" TargetExt=".van" Compiler="AICompiler" DependsOf=".bar;.bse" /> 
  <Resource Class="DrawableRoadMap" SourceExt=".drp" TargetExt=".drp" DependsOf=".bar;.bse" /> 
  <Resource Class="MovieResource" SourceExt=".bac" TargetExt=".bac" DependsOf=".wb.entities.bin;.entities.bin" /> 
  <Resource Class="CCarReplayResource" SourceExt=".rpl" TargetExt=".rpl" DependsOf=".bac" /> 
  <Resource Class="AudioResource" SourceExt=".mp3" TargetExt=".mp3" DependsOf=".wb.entities.bin;.entities.bin" /> 
  <Resource Class="CClothResource" SourceExt=".glm" TargetExt=".xbg" Compiler="GeomCompiler" DependsOf=".wb.entities.bin;.entities.bin;.bar;.bse" /> 
  <Resource Class="VideoResource" SourceExt=".bk2" TargetExt=".bk2" DependsOf=".wb.entities.bin;.entities.bin" /> 
  <Resource Class="SkillGhostMedalResource" SourceExt=".sgm" TargetExt=".sgm" DependsOf=".wb.entities.bin;.entities.bin" /> 
  </ResourceConfig>
```
## Post #17
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-01T11:12:46+00:00
- Post Title: Re: The Crew fat/dat archives

Nice work man! Hope we'll get a public release soon
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-01T11:55:04+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Chipicao
>
> Nice work man! Hope we'll get a public release soon
I hope too if enough of my patience
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-08-01T14:20:04+00:00
- Post Title: Re: The Crew fat/dat archives

In my opinion your values (offset/zsize/size) are not correct.

The following is the script I have made just now and works with both Watch Dogs (PC/PS) and The Crew:
[http://aluigi.org/papers/bms/fat2_fat3.bms](http://aluigi.org/papers/bms/fat2_fat3.bms)

There are no errors during the extraction of the samples I collected.
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-01T14:35:32+00:00
- Post Title: Re: The Crew fat/dat archives

Yep i know. It's already fixed. I will share unpacker in the next hour after update filenames base
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-01T15:30:59+00:00
- Post Title: Re: The Crew fat/dat archives

Test build - Download > See below
## Post #22
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-01T15:56:04+00:00
- Post Title: Re: The Crew fat/dat archives

Thanks a lot for your work guys!

As I expected, model files are almost identical to Far Cry 3. I just need to change some submess stuff to get rid of those rogue faces.
[](http://www.imagebam.com/image/0ab956342405904)
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-01T19:45:18+00:00
- Post Title: Re: The Crew fat/dat archives

Test Build 2 - [Download](https://www.sendspace.com/file/l0lxx0)

* Filelist updated
* Added: detecting file types for unknown files
## Post #24
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-08-02T07:03:04+00:00
- Post Title: Re: The Crew fat/dat archives

Great how about a repacker? It's great to see the game files can be unpacked.
## Post #25
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-08-02T08:20:24+00:00
- Post Title: Re: The Crew fat/dat archives

Anyone can share with clients?PM pls
## Post #26
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-02T09:05:28+00:00
- Post Title: Re: The Crew fat/dat archives

Who has beta access or beta key?
## Post #27
- Username: Speeder
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 05, 2011 4:17 am
- Post datetime: 2014-08-02T15:16:16+00:00
- Post Title: Re: The Crew fat/dat archives

I do have access to the beta if needed. 

Can't wait for a repacker anyway, so many stuff to test (even the debug functions could be interesting to test).

Small but not efficient python script to read the textures (sometimes the TBX have a different data length; but most of the time it'll work):

```
TBX= 1
TBXEND= 40
for root, dirs, files in os.walk("."):
    for file in files:
        if file.endswith(".xbt"):
		with open( file, 'rb' ) as inputfile, open( file+'.dds', 'wb' ) as outfile:
			outfile.write(inputfile.read( TBX - 1 ))
			inputfile.seek(TBXEND)
			outfile.write(inputfile.read())
```
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-08-02T16:13:23+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from d875j
>
> Great how about a repacker? It's great to see the game files can be unpacked.
If you want to make a simple test you can use my script with quickbms in reimport mode.
Luckily The Crew and the other FAT2 games don't use chunks (like instead does Watch Dogs) and the algorithm is just lzo, so it's fully supported.
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-02T16:34:19+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Speeder
>
> I do have access to the beta if needed.
Yeah needed for update filename base, pm me if you can share 

btw: I looked through all the archives and did not find any scripts
## Post #30
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-08-02T18:23:19+00:00
- Post Title: Re: The Crew fat/dat archives

I have beta access pm me.
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-02T19:35:15+00:00
- Post Title: Re: The Crew fat/dat archives

Servers like Release, E3, Dev, Work > unable to authenticate for reson, all other - unable to connect proxy
## Post #32
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-03T08:21:27+00:00
- Post Title: Re: The Crew fat/dat archives

One step closer 
[](http://www.imagebam.com/image/4883ed342753891) [](http://www.imagebam.com/image/557f86342755032) 

@Ekey What exactly do you need? Files or direct access? The beta ran from 21st to 25th July, it's not available (for now).
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-03T08:26:33+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Chipicao
>
> @Ekey What exactly do you need? Files or direct access? The beta ran from 21st to 25th July, it's not available (for now).
Yeah i know, i try connect to other servers
## Post #34
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-03T10:20:31+00:00
- Post Title: Re: The Crew fat/dat archives

Updated base

PS: See below
## Post #35
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-08-03T14:50:11+00:00
- Post Title: Re: The Crew fat/dat archives

What can i do i do to help? I want to play beta still my account has the beta and has to be a way i only was able to play few hours when i got my key. If the only way to play is to have on uplay i already cleared for that must be a way to make it work.
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-03T14:55:35+00:00
- Post Title: Re: The Crew fat/dat archives

Nothing. Waiting next CBT
## Post #37
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2014-08-03T17:21:51+00:00
- Post Title: Re: The Crew fat/dat archives

know that CBT is over, can i get 3d models without entering the game?
## Post #38
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-03T18:06:01+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from dimon4ik6565
>
> know that CBT is over, can i get 3d models without entering the game?
Use unpacker for get models with extensions mesh and xbg
## Post #39
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2014-08-03T18:29:32+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Ekey
>
> dimon4ik6565 wrote:know that CBT is over, can i get 3d models without entering the game?
Use unpacker for get models with extensions mesh and xbg

already, unpacked and converted texture in DDS, but .mesh not understand a program like ogre, how to open it?
## Post #40
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-03T19:28:50+00:00
- Post Title: Re: The Crew fat/dat archives

I guess Chipicao have max script for open models
## Post #41
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2014-08-03T19:34:09+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Ekey
>
> I guess Chipicao have max script for open models

I see in the screenshots bricks under suspension, seems it's ripper.

---------------------------

read the first post with the screenshot, apparently not ripper
## Post #42
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-04T01:06:22+00:00
- Post Title: Re: The Crew fat/dat archives

Importer, not ripper 

The script is able to decode the vertex format (FVF code) and read all LODs and submeshes with vertex color, normals, UV1-UV3, material names.
TODO list:
- attach moving parts (doors, steering wheel) to corresponding bones DONE
- read material files, properties and textures
- fix UV and vertex scaling DONE

UV mapping is scaled differently depending on the shader used, just like in Far Cry 3 and Watch Dogs.
But even worse, vertex positions are also scaled differently based on the shader:
[](http://www.imagebam.com/image/940887342917674) [](http://www.imagebam.com/image/802b6f342917682) [](http://www.imagebam.com/image/4a483d342917677) [](http://www.imagebam.com/image/2bffc8342917694) 
int16/16383.5 --- int16/16383.5 --- int16/10922.5

Traffic vehicles have a different scale as well.
I will release the script after I fix these isues or find a workaround
## Post #43
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2014-08-04T02:14:09+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Chipicao
>
> Importer, not ripper 

The script is able to decode the vertex format (FVF code) and read all LODs and submeshes with vertex color, normals, UV1-UV3, material names.
TODO list:
- attach moving parts (doors, steering wheel) to corresponding bones
- read material files, properties and textures
- fix UV and vertex scaling

UV mapping is scaled differently depending on the shader used, just like in Far Cry 3 and Watch Dogs.
But even worse, vertex positions are also scaled differently based on the shader:
    
int16/16383.5 --- int16/16383.5 --- int16/10922.5

Traffic vehicles have a different scale as well.
I will release the script after I fix these isues or find a workaround

guys you are the best
## Post #44
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-08-04T14:38:37+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Chipicao
>
> Importer, not ripper 

The script is able to decode the vertex format (FVF code) and read all LODs and submeshes with vertex color, normals, UV1-UV3, material names.
TODO list:
- attach moving parts (doors, steering wheel) to corresponding bones
- read material files, properties and textures
- fix UV and vertex scaling

UV mapping is scaled differently depending on the shader used, just like in Far Cry 3 and Watch Dogs.
But even worse, vertex positions are also scaled differently based on the shader:
    
int16/16383.5 --- int16/16383.5 --- int16/10922.5

Traffic vehicles have a different scale as well.
I will release the script after I fix these isues or find a workaround

What the hell vertex position also scaled ? wow I though watch_dogs was bad hahah dam
## Post #45
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-05T23:12:38+00:00
- Post Title: Re: The Crew fat/dat archives

I found out where position and UV multipliers are stored, and also managed to link all meshes to nodes.
Now all that's left is reading materials and putting all these pieces together.
[](http://www.imagebam.com/image/abf810343318648) 
Each car is split into a dozen files...

By the way, I started to realize that Watch_Dogs isn't as different to Far Cry 3 as I thought. Some data blocks are the same, others were "upgraded" being a newer version, but the way they are structured in the file is completely different, which threw me off.
No, this doesn't mean I'm getting back to researching WD, sorry.
## Post #46
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-08-08T11:32:41+00:00
- Post Title: Re: The Crew fat/dat archives

Next beta on August 25
## Post #47
- Username: Speeder
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 05, 2011 4:17 am
- Post datetime: 2014-08-09T15:37:46+00:00
- Post Title: Re: The Crew fat/dat archives

A simple Texture viewer    . Will update when we'll be able to repack the files (and make an integrated dds viewer maybe).


Download: [https://www.mediafire.com/?jztepr2ai7ddr61](https://www.mediafire.com/?jztepr2ai7ddr61)
More info: [http://backwardgaming.wordpress.com/201 ... oject-3-0/](http://backwardgaming.wordpress.com/2014/08/09/project-3-0/)
## Post #48
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2014-08-09T18:00:22+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Speeder
>
> A simple Texture viewer    . Will update when we'll be able to repack the files (and make an integrated dds viewer maybe).


Download: https://www.mediafire.com/?jztepr2ai7ddr61
More info: http://backwardgaming.wordpress.com/201 ... oject-3-0/

but after all have already made program for converting multiple textures in dds, even more so with multiple folders.
## Post #49
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-10T11:48:42+00:00
- Post Title: Re: The Crew fat/dat archives

btw: fcb files can be converted by ConvertBinaryObject from [dunnia2](http://svn.gib.me/builds/dunia2/)
## Post #50
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-08-10T13:34:18+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Speeder
>
> A simple Texture viewer    . Will update when we'll be able to repack the files (and make an integrated dds viewer maybe).


Download: https://www.mediafire.com/?jztepr2ai7ddr61
More info: http://backwardgaming.wordpress.com/201 ... oject-3-0/

Didn't I already make a xbt extractor
## Post #51
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-10T14:35:17+00:00
- Post Title: Re: The Crew fat/dat archives

Updated base
[TC_Projects_u3.rar](https://xentaxbackup.github.io/file/7653_TC_Projects_u3.rar)
## Post #52
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-16T15:33:25+00:00
- Post Title: Re: The Crew fat/dat archives

Well..... who can give account for next beta? Because i can't connect anymore by account from Speeder! 

PM please.
## Post #53
- Username: djkroko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 28, 2014 4:23 pm
- Post datetime: 2014-08-28T08:26:38+00:00
- Post Title: Re: The Crew fat/dat archives

Hi,

do you have also a way to pack the xml files back to a .dat file?
## Post #54
- Username: thedoc
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 10, 2014 11:13 pm
- Post datetime: 2014-09-24T13:56:29+00:00
- Post Title: Re: The Crew fat/dat archives

Any updates?
I downloaded the first beta, i have all the files, if it helps i can share anything you need.
Thank you for your efforts
## Post #55
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-11-28T15:26:32+00:00
- Post Title: Re: The Crew fat/dat archives

Tool working perfect on the final build
## Post #56
- Username: thor96ita
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 31, 2014 8:41 pm
- Post datetime: 2014-12-01T21:04:48+00:00
- Post Title: Re: The Crew fat/dat archives

The Crew is out any news for the repacker? Bye
## Post #57
- Username: Faalagorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 20, 2009 9:57 pm
- Post datetime: 2014-12-03T21:35:09+00:00
- Post Title: Re: The Crew fat/dat archives

First of all, kudos to Ekey, as the unpacker works like a charm. However, since the game is now a full release and the newest FileNames.list is outdated now, I have a question: 
where do the filenames come from and is there a possibility to update them by yourself easily? The file itself is plain text, but I honestly have no idea where the file names come from.
Also, one thing got me curious - since the FileNames.list file contains simply a full path but no CRC, offset or whatsoever, yet the program correctly named some of the files after extraction, how does it know which file is what o.o? That really puzzles me up.

If not, I guess I'll need to settle with most of the files having no names (I mostly need the UI textures from gui.dat) or wait for an official update 

EDIT: Oh, and since I'm messing with textures, one more thing to notice:

> Reply from cra0
>
> Didn't I already make a xbt extractor
I'm not sure which extractor is it, but for referecne: Gibbed Dunia 2 Tools (with GUI) works just fine with the game's XBT textires as a DDS converter
## Post #58
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-07T10:33:36+00:00
- Post Title: Re: The Crew fat/dat archives

I've released the script I was working on for importing meshes: [viewtopic.php?p=91256#p91256](http://forum.xentax.com/viewtopic.php?p=91256#p91256)

It's still incomplete as it doesn't import materials or textures, but everything else works fine, including LODs, submeshes, normals, mesh and UV scaling, hierarchy.
## Post #59
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-07T16:26:51+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Faalagorn
>
> First of all, kudos to Ekey, as the unpacker works like a charm. However, since the game is now a full release and the newest FileNames.list is outdated now, I have a question: 
where do the filenames come from and is there a possibility to update them by yourself easily? The file itself is plain text, but I honestly have no idea where the file names come from.
You can get new names from game memory and add in FileNames.list

> Reply from Faalagorn
>
> Also, one thing got me curious - since the FileNames.list file contains simply a full path but no CRC, offset or whatsoever, yet the program correctly named some of the files after extraction, how does it know which file is what o.o? That really puzzles me up.
Here no magic 

> Reply from Ekey
>
> Test Build 2 - Download

* Filelist updated
* Added: detecting file types for unknown files
Reuploaded.
## Post #60
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-07T22:24:35+00:00
- Post Title: Re: The Crew fat/dat archives

I've added 2580 files by parsing all model files and listing materials, and by "brute forcing" material files in search for textures.
I cant's say if they're all good, but at least some of them are working because I see new files renamed.

[http://www.mediafire.com/download/f63l0 ... cts_u4.zip](http://www.mediafire.com/download/f63l08q622we42j/TC_Projects_u4.zip)
## Post #61
- Username: thedoc
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 10, 2014 11:13 pm
- Post datetime: 2014-12-07T23:54:12+00:00
- Post Title: Re: The Crew fat/dat archives

First of all congrats Chipi for the script!
Could you add, if possible (maybe is even in the plans) multiple files import and LOD select.

Thank you, always the best
## Post #62
- Username: thor96ita
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 31, 2014 8:41 pm
- Post datetime: 2014-12-15T22:32:47+00:00
- Post Title: Re: The Crew fat/dat archives

Hi, I found rain file but in the game I didn't see it. Some one see it?
And I have a problem with script i drag and drop in 3d max 2015 but nothing happen. Any solution?

thx
## Post #63
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-16T16:25:20+00:00
- Post Title: Re: The Crew fat/dat archives

@thedoc yess I'll add more features.

@thor96ita I replied to your issue in the other thread.

As for rain, I've seen some references too, but they could be just standard leftovers from the Dunia engine.
One of the developers has clearly stated in an interview that there's no dynamic weather, only region-specific weather like snow.
## Post #64
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-16T23:08:38+00:00
- Post Title: Re: The Crew fat/dat archives

For anyone interested, here's a tool I just made to stitch together low-res tiles of the game's map: [http://www.mediafire.com/download/4i571 ... tchLow.zip](http://www.mediafire.com/download/4i571s8xvciryvs/CrewMapStitchLow.zip)

- extract global.fat/dat using Ekey's tool
- place CrewMapStitchLow.exe in \data_win32\Unpacked\project\road66\base\area and run
- after a few seconds you'll get a lowresc.dds file in the same area folder
- no recompression is done, the DDS data is just re-arranged in one larger texture

It actually faster for me to code this to tool instead of manually stitching 209 images.  Not to mention the amount of memory Photoshop would have eaten...

P.S I'm aware these textures are meant to be rendered on 3D map areas, but this is just a means to an end.
## Post #65
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T17:14:21+00:00
- Post Title: Re: The Crew fat/dat archives

Here is another little tool I made a few weeks ago that might come in handy: [XBGmover](http://www.mediafire.com/download/n0svasvjxhdrfvc/XBGmover.zip)
It only works for vehicles and it's just a way to group mesh files belonging to the same car. Actual file paths may be different (if we ever find them).
Usage:
- extract only vehicles.dat/fat with [Ekey's tool](https://www.sendspace.com/file/l0lxx0) and make sure you use my [updated filelist](http://www.mediafire.com/download/f63l08q622we42j/TC_Projects_u4.zip).
- place XBGmover.exe in the extracted folder, on the same level with __Unknown and graphics
- run it and wait

What it does is it parses unknown .mesh files, then materials, it gets a list of textures and based on the texture path it moves each mesh file in a specific vehicle folder.
For example a model that uses graphics\vehicles\mclaren\mp4_12c\maps\mclaren_logo_c.xbt will be moved in graphics\vehicles\mclaren\mp4_12c\

The problem is that some car parts only use common textures from graphics\vehicles\common_maps, so there's no way to tell which car they belong to.
Even so, you still get between 20 to 60 mesh files moved.

If anyone attempts to identify other files manually, I would appreciate if you'd post your findings here.
## Post #66
- Username: JoshuaX
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 06, 2015 7:59 pm
- Post datetime: 2015-01-06T19:13:56+00:00
- Post Title: Re: The Crew fat/dat archives

unfortunately XBGmover does nothing - DOS window just opened and closed, nothing happened. If runed from directory /graphic for instance, it crashes saying, that couldn't find a path...
## Post #67
- Username: MrBolleck
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 04, 2011 6:46 am
- Post datetime: 2015-01-06T19:57:17+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from JoshuaX
>
> unfortunately XBGmover does nothing - DOS window just opened and closed, nothing happened. If runed from directory /graphic for instance, it crashes saying, that couldn't find a path...

same here
## Post #68
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T20:51:57+00:00
- Post Title: Re: The Crew fat/dat archives

Try it now.

You got it right the first time, run from outside graphics folder.
Are you sure you extracted vehicles.dat using my filelist?
## Post #69
- Username: MrBolleck
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 04, 2011 6:46 am
- Post datetime: 2015-01-06T20:57:40+00:00
- Post Title: Re: The Crew fat/dat archives

[](http://abload.de/image.php?img=unbenanntmpse6.png)


so it should look
says zero files found

I just downloaded only all from your last post

Maybe interesting

I win8 x64
and started as admin

is a specific NetFrame may be required?
## Post #70
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T21:05:19+00:00
- Post Title: Re: The Crew fat/dat archives

Ok.. 

Let's try something else. I included in the archive a cmd file that should move all the car files I found. Just run it, no need for the exe.
## Post #71
- Username: MrBolleck
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 04, 2011 6:46 am
- Post datetime: 2015-01-06T21:11:38+00:00
- Post Title: Re: The Crew fat/dat archives

it has done something

but is in cmd

E: \ blablabla \ Unpacked> move __Unkown \ XXXXXXX.mesh graphics \ vehicles \ blablabla \ XXXXXXX.xbg
The system can not find the file specified.

[](http://abload.de/image.php?img=image2m3s97.png)
## Post #72
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T21:22:46+00:00
- Post Title: Re: The Crew fat/dat archives

WTF? Do you have any .mesh files inside __Unknown?

See if you can find any of these:
19CD0EB44C03139B.mesh
1CE0A14DDF140EB4.mesh
2CC9EB3FD7A5CE85.mesh
46C02028E0E874B9.mesh
## Post #73
- Username: MrBolleck
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 04, 2011 6:46 am
- Post datetime: 2015-01-06T21:29:32+00:00
- Post Title: Re: The Crew fat/dat archives

[](http://abload.de/image.php?img=unbenanntovumy.png)

no I did not .mesh files in the folder

[](http://abload.de/image.php?img=image22guwz.png) [](http://abload.de/image.php?img=unbenanntr8ur7.png)
## Post #74
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T22:03:21+00:00
- Post Title: Re: The Crew fat/dat archives

Oh, I see the problem now. Ekey updated his tool and files are now xbg instead of .mesh.

Re-download XBGmover and try again please.

You should also re-download my updated filelist; I've re-synced it with Ekey's latest release.
## Post #75
- Username: MrBolleck
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 04, 2011 6:46 am
- Post datetime: 2015-01-06T22:12:54+00:00
- Post Title: Re: The Crew fat/dat archives

You are a god.

it runs, I think as it should
## Post #76
- Username: JoshuaX
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 06, 2015 7:59 pm
- Post datetime: 2015-01-06T22:24:13+00:00
- Post Title: Re: The Crew fat/dat archives

+1
## Post #77
- Username: thedoc
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 10, 2014 11:13 pm
- Post datetime: 2015-01-07T21:48:46+00:00
- Post Title: Re: The Crew fat/dat archives

At me it worked flawless, ty Chipi!

May it be a 64 bit only exe?
## Post #78
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-08T17:59:28+00:00
- Post Title: Re: The Crew fat/dat archives

No, nothing like that. It was a silly issue that I fixed afterwards.

Thanks for the feedback though.
## Post #79
- Username: MrBolleck
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 04, 2011 6:46 am
- Post datetime: 2015-02-08T19:21:30+00:00
- Post Title: Re: The Crew fat/dat archives

hello Chipicao
Do you have your file list already renewed
## Post #80
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-02-15T11:21:31+00:00
- Post Title: Re: The Crew fat/dat archives

No. Has something changed after the last update?
## Post #81
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2015-03-12T16:59:12+00:00
- Post Title: Re: The Crew fat/dat archives

uhm, got the vehicle.dat and the vehicle.fat now, anyone has the carpass files? (458 speciale + MP4-12C)
## Post #82
- Username: thedoc
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 10, 2014 11:13 pm
- Post datetime: 2015-05-12T17:16:51+00:00
- Post Title: Re: The Crew fat/dat archives

Is there any way to import more files per time?
## Post #83
- Username: SandroX
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Apr 20, 2010 3:43 am
- Post datetime: 2015-05-21T09:29:42+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Chipicao
>
> 
How I can import more then one file?
## Post #84
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2015-05-23T10:41:50+00:00
- Post Title: Re: The Crew fat/dat archives

hello Chipicao
Could you tell me how to hook the game so i can build a filelist? I m actually building a filelist for Watch Dogs, which uses fat/dat as well.
## Post #85
- Username: Izack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 26, 2012 1:32 pm
- Post datetime: 2015-06-18T20:55:17+00:00
- Post Title: Re: The Crew fat/dat archives

Great work. Is any way to import the pieces of the map in the right way ? like in game. I am really interested in the whole map.
## Post #86
- Username: thedoc
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 10, 2014 11:13 pm
- Post datetime: 2016-01-20T11:22:11+00:00
- Post Title: Re: The Crew fat/dat archives

The Wild Run update has been released in november. Are there any apdates about the import script?
At least a script that allows to import more files at once...

Thank you in advance

(I have Wild Run, if you want/need i can provide files for research)
## Post #87
- Username: Justdragos
- Rank: advanced
- Number of posts: 69
- Joined date: Tue Feb 21, 2012 3:19 pm
- Post datetime: 2016-01-29T15:15:18+00:00
- Post Title: Re: The Crew fat/dat archives

this method is just for the pc version or does it work also for the xbox360?:D
## Post #88
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2016-03-06T00:30:56+00:00
- Post Title: Re: The Crew fat/dat archives

@Chipi did this die off ? the game has so much potential. i think a revision of tools would be a great benefit.. your XBG mover is perfect - although - i still had to place some files myself manually after checking crashing errors on newer files (i used your list on wild run) it moved some things, but gave errors for others, explaining where they should actually go... 

it seems we are almost there , maybe a rename function like the Dunia importer has ?
## Post #89
- Username: DevilDriver
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 11, 2014 6:35 pm
- Post datetime: 2016-03-06T20:05:49+00:00
- Post Title: Re: The Crew fat/dat archives

From Chipicao's profile:

> Last visited: Thu Jan 14, 2016 1:57 am
## Post #90
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2016-03-18T22:45:48+00:00
- Post Title: Re: The Crew fat/dat archives

It hasn't died, but without proper filenames it's not really worth it.
My XBG mover is kind of a "brute force" method, and it doesn't even find all required files to build a complete car.

I tested Wild run when it was in beta, and I know there have been some changes to the XBG file structure, probably nothing major.
But before I continue developing my converter, I need complete file names and paths, so that I can link models to materials and then to textures.
## Post #91
- Username: viruscn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 21, 2016 1:16 pm
- Post datetime: 2016-03-25T09:04:01+00:00
- Post Title: Re: The Crew fat/dat archives

the topic is not died./
## Post #92
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2016-05-28T00:17:22+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Faalagorn
>
> ... the newest FileNames.list is outdated now, I have a question: 
where do the filenames come from and is there a possibility to update them by yourself easily? The file itself is plain text, but I honestly have no idea where the file names come from.

> Reply from Ekey
>
> You can get new names from game memory and add in FileNames.list

Can somebody please expand on this? I wish to update the file list because there are still a lot of things missing and the game has been updated significantly since.
## Post #93
- Username: ilufir
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 07, 2016 7:04 pm
- Post datetime: 2016-09-26T14:16:04+00:00
- Post Title: Re: The Crew fat/dat archives

Okaaaaay... It's been too silent here
The Crew is temporarily free on Uplay, so... I got it and you know... Why is this topic so silent? No one has imported the map, which is strange, because the map is AMAZING!
## Post #94
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2016-09-27T21:45:01+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Ekey
>
> You can get new names from game memory and add in FileNames.list
Indeed, if wed know how to perform that "game memory" to extract full list and updated would be great, anyone knows how?
So many of us can help, just give us clue as to how to perform it, tools/utilities, etc etc etc

cheers
## Post #95
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2016-11-07T19:27:56+00:00
- Post Title: Re: The Crew fat/dat archives

would be good to see some more progress on this, as I have the game files sitting here after installing the game this morning.

would look beautiful in GTA
## Post #96
- Username: Justdragos
- Rank: advanced
- Number of posts: 69
- Joined date: Tue Feb 21, 2012 3:19 pm
- Post datetime: 2017-01-20T11:40:22+00:00
- Post Title: Re: The Crew fat/dat archives

Just found something that mihgt help you guys
[http://gamemodels.ru/tutorials/article/ ... ew-models/](http://gamemodels.ru/tutorials/article/21-the-crew-models/)
## Post #97
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-03-09T15:23:08+00:00
- Post Title: Re: The Crew fat/dat archives

Hi all i work out how edit audio sound files took bit time i edit wav but not ogg so far, I just tryed same setting with ogg files and works so u all start edit engine sounds now thank to you all for hard work and doing dat unpacker biggest thx's to Chipicao for making program.
General
Complete name                            : C:\Users\andrew\Documents\The Crew\mods\vehicles_sounds\IL6_BMW_Z4_OFF_01_RACING\IL6_BMW_Z4_Idle_RACING.wav
Format                                   : Wave
File size                                : 57.2 KiB
Duration                                 : 2 s 168 ms
Overall bit rate mode                    : Constant
Overall bit rate                         : 216 kb/s

Audio
Format                                   : ADPCM
Codec ID                                 : 11
Codec ID/Hint                            : Intel
Duration                                 : 2 s 168 ms
Bit rate mode                            : Constant
Bit rate                                 : 216 kb/s
Channel(s)                               : 1 channel
Sampling rate                            : 48.0 kHz
Bit depth                                : 4 bits
Stream size                              : 57.2 KiB (100%)
ok just playing around file in Audacity got it work have do import raw data 
encoding. unsingned 8 bit pcm
byte order. no endianness
channels. 1 channel [mono]
start offset. 0
amount to import. 100%
sample rate 48000
now edit them but were or what do after that get them work in game.
u need export audio go options set to quality 0 save it to ogg. u play them in vlc player.
## Post #98
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-03-09T15:26:23+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from headrushmayor
>
> Hi all i work out how edit audio sound files took bit time i edit wav but not ogg so far, I just tryed same setting with ogg files and works so u all start edit engine sounds now thank to you all for hard work and doing dat unpacker biggest thx's to Chipicao for making program.
General
Complete name                            : C:\Users\andrew\Documents\The Crew\mods\vehicles_sounds\IL6_BMW_Z4_OFF_01_RACING\IL6_BMW_Z4_Idle_RACING.wav
Format                                   : Wave
File size                                : 57.2 KiB
Duration                                 : 2 s 168 ms
Overall bit rate mode                    : Constant
Overall bit rate                         : 216 kb/s

Audio
Format                                   : ADPCM
Codec ID                                 : 11
Codec ID/Hint                            : Intel
Duration                                 : 2 s 168 ms
Bit rate mode                            : Constant
Bit rate                                 : 216 kb/s
Channel(s)                               : 1 channel
Sampling rate                            : 48.0 kHz
Bit depth                                : 4 bits
Stream size                              : 57.2 KiB (100%)
ok just playing around file in Audacity got it work have do import raw data 
encoding. unsingned 8 bit pcm
byte order. no endianness
channels. 1 channel [mono]
start offset. 0
amount to import. 100%
sample rate 48000
now edit them but were or what do after that get them work in game.
u need export audio go options set to quality 0 save it to ogg. u play them in vlc player.
for audio info get this program. [https://mediaarea.net/en/MediaInfo](https://mediaarea.net/en/MediaInfo)
## Post #99
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-03-09T17:03:41+00:00
- Post Title: Re: The Crew fat/dat archives

ok so trying work out ogg files i try lot programs edit them but not much luck here screen shot of format so anyone help me edit them.
[ogg format vehicle_common_starter.JPG](https://xentaxbackup.github.io/file/12587_ogg format vehicle_common_starter.JPG)
## Post #100
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-03-10T06:55:46+00:00
- Post Title: Re: The Crew fat/dat archives

Hi all so played with ogg file could not read or play them so look on google for fsb to ogg so found program it unpack them  fmod_extractors.rar,
[http://zenhax.com/viewtopic.php?f=17&t=1901](http://zenhax.com/viewtopic.php?f=17&t=1901)
Required DLL's download them put same folder then just drag over the ogg to fmod_extr.exe it unpack to same folder the files are in start to edit.
i want edit turbo and other trans sound as well and found great audio edit do wav and ogg not Audacity as hate ogg found this one it 10x better 
Audiodope it free as well easy use, there just 1000's file to edit,
Can edit program dat unpacker do txt files as trying find engine and game files so edit sounds in file not audio.
Sorry for my spelling i have XXY my words or txt hard read i try my best hope understand.
## Post #101
- Username: AA97
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2017 8:08 pm
- Post datetime: 2017-03-12T11:08:13+00:00
- Post Title: Re: The Crew fat/dat archives

Has anyone completely sorted all the files?
## Post #102
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-03-13T19:14:21+00:00
- Post Title: Re: The Crew fat/dat archives

I am so ready and so willing to help, in making the new list, fully if possible.
I just would like those with knowledge, to point me in the right direction as to how one can perform proper memory dump of the game and how do you view the list names and analyze the dump.

For instance, if I dump the game memory data using task manager while the game is running, it dumps over 3GB, and then I try to analyze it with WinDbg, but no matter what commands I throw at it, it can not load symbols in order to open the dump data.
Is there another step I am missing?
Is anyone willing to help and point in to the right direction?
Tools utilities software anything, sooooooo many of us can help and contribute, I get that the forum has a bad reputation with begging and annoying users with very bad requests, and get ignored for good reason.
But id really like to genuinely help, I am not a coder programmer etc etc, but if pointed in the right direction, miracles can happen.

If by some reason no one wants to share the info publicly, PM can always be used, please and thank you, lets communicate and make things work.

cheers
## Post #103
- Username: havatan10
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 11, 2016 2:00 am
- Post datetime: 2017-03-14T00:24:45+00:00
- Post Title: Re: The Crew fat/dat archives

are we able to export also map/terrain meshes and buildings or does it only work for vehicles? anyone tried with terrain/buildings so far ?
## Post #104
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-03-16T16:25:40+00:00
- Post Title: Re: The Crew fat/dat archives

hi there is list all files in game it in data_win32/Projects/FileNames.list i don't if got this file list in your game, there only 19 car sounds files i have not found bikes or all other car sounds or 4x4 monster truck sounds as so many cars in this game must using same sounds, i edit the engine sound Audiodope they sound better or take sounds out other car games add them u hear on my side but don't if hear on your side.
For life of me i don't if dat unpacker will find txt files as can't find car engine sound txt or other game setting if they in game must be xbt they texture files, when open sound file in Audiodope they sound so sweet but soon back in game they sound crap like game putting dull mute on files or there blocker on how good game sound can be, they so clear but not best record of sounds lot pops and crackles in files i don't if Audiodope doing to sounds but they not best like other games engines sounds. sum of files same as codemasters grid dev.xml is same different company but same file.
I find if use FsbExtractor.exe not as good as using fmod_extr.exe seem do sounds better for fsb files.just wish way repack the fsb files and repack the dat files so work in game better.
I made mod folder in my document/the crew seem make files work in game.
[FileNames.rar](https://xentaxbackup.github.io/file/12633_FileNames.rar)
## Post #105
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-03-16T16:34:20+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from havatan10
>
> are we able to export also map/terrain meshes and buildings or does it only work for vehicles? anyone tried with terrain/buildings so far ?
texture file are xbt i don't how open them my try 3DSMax export value. here list one files.
<Profile>
	<!-- CrashHandlerConfig -->
	<CrashHandlerConfig 
		IsActive="0"
		IsDebug="0"
		PCInGameEditorExecNamePrefix="fc2editor"
		PCEditorExecNamePrefix="editor"
		PCEngineExecNamePrefix="farcry2"

so they using farcry2 editor for game it seems.
programs i use are 
fmod_extr.exe/FsbExtractor.exe = fsb
DATUnpacker.exe = dat/fat files
Ravioli explorer get texture out the dat files if big file my take bit time get them. u use on any game as it will unpack other files as well.
Gibbed tool for other games as well.
iripper.exe to edit texture files hard to find this program.
Audiodope.exe do all my sound editing.
hope this help you out. if know other programs u use pop them up help others as well.
## Post #106
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-10-15T04:29:14+00:00
- Post Title: Re: The Crew fat/dat archives

hi all i unpacked all dat files came too 175gb's so watch out as know sound in game way to low i use FMOD FSB Extractor get all wav files out there about 167gb's files so redid them in mp3 took down too 2.6gb's still sound so good in game they sound better then wav files save alot of space. i upload them to mega.nz u download them play around with them if like i have edit sum files use Audio Speed Changer Pro to chance pitch to -6 give cars and other sound in game bit low end kick to them as well used dbpoweramp boost sound up still a lot to do to sound files as play around u see going street to fullstock cars sound same so if use Audio Speed Changer Pro chance pitch i did street stock, racing -2.5, perf -5, fullstock to -8 u hear different in game now it like it unlock sound as cars sound better. here link for files if post here.

[https://mega.nz/#!cvY1TaIY!pTrAPtydFV-J ... SowcRojdsw](https://mega.nz/#!cvY1TaIY!pTrAPtydFV-JYbS0ImPw6dZ7hAd67Z-rHSowcRojdsw)
## Post #107
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-12-27T04:58:02+00:00
- Post Title: Re: The Crew fat/dat archives

So, anyone can help in ponting me in the righ tdirection as to how one performs a game dump, analyze the dump to extract the file names fully to update the list, anyone?
come on guys, a link, something, as to what needs to be done, anything, yes? no? maybe? possibly?
## Post #108
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-19T20:46:08+00:00
- Post Title: Re: The Crew fat/dat archives

Well... still trying to figure out how to freaking dump this game properly then to update that list for the game assets, yet still no one wants to help in how to do it right.
Still tried to Google for lots of info/research, nothing is to be found for this kind of process.
I have IDA to analyze the dump file created with task manager with in windows still nothing, come one, someone? anyone?

Ekey only mentioned that needs to be extracted from the memory dump, but that was it, no other freaking clue, once again, anyone? I want to update that list for extraction, how can I do it?
## Post #109
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-27T14:45:23+00:00
- Post Title: Re: The Crew fat/dat archives

After lots of trial and error, I understood a bit how to gain access in various ways to memory dump, in order to manually build the damn list, yet still wont work fully, something else I am missing, but I cant figure out yet.

CheatEngine is a neat tool, but it requires lots and lost of unnecessary clicking here in there to even see the strings, saving them is a pain in the ass.

Using windows task manager to dump the memory is a walk in the park and then to extract the strings from it, but no matter at how many stages I dump the game loaded in the memory, the results are almost the same with only few strings additions here and there, that means its buggy to dump the strings properly and another step I must perform but cant figure out what, yet, unless that is how it works?

Using WinHex is another great tool too, but like CheatEngine to save the strings is difficult.

basically all three offer almost identical results, so Ekey, any suggestions please or anyone else?
## Post #110
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-28T17:26:10+00:00
- Post Title: Re: The Crew fat/dat archives

First of all, there's no easy and/or "proper" way to 100% find the names. This is why nobody answers to you.

There are some possible ways, but all of them have problems, and it seemd in case of THIS particular game they are especially big.

1. make a code hack (hook) for the running game and dump the names it will request in real-time.
Problems:
- considering its an online game, you may loose your game/account
- its hard or impossible to do if the game has heavy protection
- hook will only dump files names requested by game in real time, so its no guarantee you will EVER get all files, maybe only 80% or 30% of them.

2. unpack all game files, parse and scan them for names.
Problem: it will take a lot of time to reverse game formats, maybe months or years. I checked the thread and Chipicao already tried that, and seems there are some difficulties in this.

3. Scan the memory dump.
Problem: you will hardly ever get much names with that, its the worst method.

Big problem for all ways: if the devs completely removed name usage at some point, you will never get ANY names at all since that moment. The idea is that the game DOESNT need names to run, names only slow it down, so many other engines are only using hashes, or decided to remove names and access files by hashes. For both reasons of speed and blocking people from getting files from the game.

To conclude: to try finding the names or building the map, one will at least need ALL the game files, and probably the possibility to hook/debug the running game, which is dangerous.
## Post #111
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-02-28T19:11:19+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from daemon1
>
> 
- its hard or impossible to do if the game has heavy protection
- hook will only dump files names requested by game in real time, so its no guarantee you will EVER get all files, maybe only 80% or 30% of them.
Yeah, you are absolutely right. Game protected by Denuvo and when I try to change the code to inject hook, a game just closing with message like
## Post #112
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-03-01T01:18:30+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from daemon1
>
> ok now i understand, if you can spend years on it, loading a few thousand files is not a problem for you. I will continue answering in "the crew" thread
Thank you.
The reason I am doing this insane task, is because of the stage of the giving research/tools/options that are available thx to Ekey and Chipicao and other people who posted information.

> Reply from daemon1
>
> First of all, there's no easy and/or "proper" way to 100% find the names. This is why nobody answers to you.
At least now I know.

> Reply from daemon1
>
> make a code hack (hook) for the running game and dump the names it will request in real-time.
-Yes I gave up on that idea since being online and protected would be bad, as simple as that.

> Reply from daemon1
>
> unpack all game files, parse and scan them for names.
-already did this 5 times, in various stages, and the results where 100% there.
I parsed every single file that had geometry and material, and after a full day, on top of what was already in Ekey's records list, I was able to add few more thousands, which I was very happy with.
Total file record now are 49290 entries.
The problem is, a good number of geometry lead to non existent materials to look for required strings, which makes no sense since geometry is there but no materials, and Ekey's tool unpacks everything, I think, even if some are unknown format.

> Reply from daemon1
>
> Problem: it will take a lot of time to reverse game formats, maybe months or years. I checked the thread and Chipicao already tried that, and seems there are some difficulties in this.
-I don't think extra reverse is necessary besides finding the right internal transforms where every piece of geometry goes in the 3D space:
Basically geometry is importable in 3dsMax with no issues what so ever, textures are fully extractable and usable.

> Reply from daemon1
>
> Scan the memory dump.
-I did multiple times various stages and files are same every time and already strings are in the record list of the unpack tool, so I gave up on it.

> Reply from daemon1
>
> if the devs completely removed name usage at some point, you will never get ANY names at all since that moment.
-names might not be the big issue in comparison to no material names to know what goes where from textures, yet they all work on hashes while hashed geometry leads to material then to textures.

In conclusion, there are only two viable options left, that make sense to me at least, please correct me if am wrong or better options are doable.

Option 1: Chipicao made that XBGMover utility to move hash named geometry in its required folders/subfolders based on the material file that leads to textures who already have folder structure.

Problem: is that its only available for moving vehicle geometry, nothing else.

Solution: another batch/tool utility that would parse every geometry and look for the material inside, then all will be placed in its required folder/subfolder, thus making the process speed up by 30% at least, and Chipicao's script to be updated with internal transforms and multiple file selection not one by one, he said he'd update the Max script but never got the chance.
Textures already have folder structure and geometry can be placed there, and it should solve the dilemma as to where textures go with out much guessing.
But I know that you do not like to do third party stuff for other applications so I respect that, it is what it is.

Option 2: would be for you to apply your generous knowledge same way you do for other game maps by making your own tools that would export the geometry where it belongs in game, which is impressive, honestly, you did more things in a short period of time where others struggled years, kudos.

> Reply from Ekey
>
> daemon1 wrote:
- its hard or impossible to do if the game has heavy protection
- hook will only dump files names requested by game in real time, so its no guarantee you will EVER get all files, maybe only 80% or 30% of them.
Yeah, you are absolutely right. Game protected by Denuvo and when I try to change the code to inject hook
Thank you for your presence and looking in to it, much appreciated.

PS another thought
Maybe Ekey can update his unpack tool and it can extract the geometry in correct folders while parsing materials? just saying, theoretically anything is possible.
## Post #113
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-05T17:53:51+00:00
- Post Title: Re: The Crew fat/dat archives

After a few days of research i have some first results. This highest LOD road of 1/6 of whole map takes 180 MB ascii file. 







last image in HQ:
[https://imgur.com/a/DD4ZI](https://imgur.com/a/DD4ZI)
## Post #114
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-03-11T22:22:42+00:00
- Post Title: Re: The Crew fat/dat archives

Daemon1 made more progress on the game map, and these images show how it looks based on his export/import tests,
no tools are made yet, more information and other progress will be available in due time.
## Post #115
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-03-26T21:12:50+00:00
- Post Title: Re: The Crew fat/dat archives

Would anyone here be able to take a look at TC2's archives (maybe Ekey or Chipicao)? I'd provide the fat/dat archives of the Closed Alpha 2 privately for this purpose.

EDIT: I've found out that the original DAT Unpacker can still be used for a few of TC2's archives (although only a few files get extracted), such as the video and sound archives, so it surely isn't much of an effort to get it fully working, I think.
## Post #116
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T08:58:05+00:00
- Post Title: Re: The Crew fat/dat archives

Nah, I do not have.
## Post #117
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-29T16:48:14+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from CobraGamer
>
> so it surely isn't much of an effort to get it fully working, I think.
i wouldn't be so sure
## Post #118
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-03-30T20:55:23+00:00
- Post Title: Re: The Crew fat/dat archives

I don't know, you're the expert

@Ekey: What do you mean?
## Post #119
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-31T11:22:16+00:00
- Post Title: Re: The Crew fat/dat archives

Unpacker for TC2 [here](https://www.sendspace.com/file/0ukx26)
## Post #120
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T12:07:02+00:00
- Post Title: Re: The Crew fat/dat archives

oh, thats why "only a few files get extracted". Because they use oodle too

Considering filenames, it seems maps can be extracted the same way as in the crew 1
## Post #121
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-03-31T12:54:11+00:00
- Post Title: Re: The Crew fat/dat archives

Thank you so much! That was quick!
## Post #122
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2018-04-04T18:16:58+00:00
- Post Title: Re: The Crew fat/dat archives

Noticed on the unknown files extracted from the sector files got quite a few havok physics files but those don't get a default extension added by the tool and there doesn't seem a obvious way for hacking a mapping in
## Post #123
- Username: verde57
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 03, 2017 4:53 pm
- Post datetime: 2018-05-21T09:47:36+00:00
- Post Title: Re: The Crew fat/dat archives

Where can I find the complete game?
 The Crew Wild Run
## Post #124
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-05-21T13:11:38+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from verde57
>
> Where can I find the complete game?
 The Crew Wild Run
There is no such game called like that, that's only an expansion of the game a DLC.
The game The Crew has two major expansions/DLCs.
>Wild Run
>Calling All Units

And you can get the game files for free by downloading the Trial Version "The Crew Ultimate Edition" with/from Uplay.
## Post #125
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-05-29T22:21:43+00:00
- Post Title: Re: The Crew fat/dat archives

@Ekey

It seems the file structure of the archives has changed from The Crew 2 Alpha, although I could be wrong.
Because I have access to the Closed Beta now, and the files seem to be included in less archives than the usual.
Where can I get the hook you usually use to extract more filenames while running the game?
Right now I am extracting every file name string the usual manual way by scanning every single file and see if I can update the list with more strings.
## Post #126
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-05-30T18:35:49+00:00
- Post Title: Re: The Crew fat/dat archives

@ Ekey

Trying to collect more strings from the files yet the tool crashes at one point.



01.JPG (89.41 KiB) Viewed 212 times
## Post #127
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-05-31T20:15:40+00:00
- Post Title: Re: The Crew fat/dat archives

Why are you putting so much effort into this if we probably won't ever get a repacker for the game?
## Post #128
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-06-10T14:15:57+00:00
- Post Title: Re: The Crew fat/dat archives

looking forward to updated texture viewer... i already began unpack of vehicles, and arranging via folder name etc, so thank you guys, keep it up
## Post #129
- Username: Edison007
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 10, 2012 7:33 pm
- Post datetime: 2018-06-22T17:57:07+00:00
- Post Title: Re: The Crew fat/dat archives

del
## Post #130
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-06-23T13:12:36+00:00
- Post Title: Re: The Crew fat/dat archives

Could one of you guys maybe take a look at road66database/item.babdb in scenaric.dat? That seems to be a pretty big database with every item in the game.
## Post #131
- Username: dhcnmtcs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 10, 2017 10:57 am
- Post datetime: 2018-06-24T18:41:30+00:00
- Post Title: Re: The Crew fat/dat archives

This should rename some of the files in "vehicles_resources\__Unknown". (unfinished)
[__UNKNOWN_XBG_Renamer.rar](https://xentaxbackup.github.io/file/14516___UNKNOWN_XBG_Renamer.rar)
## Post #132
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-07-04T10:22:52+00:00
- Post Title: Re: The Crew fat/dat archives

Is there any chance one of you will make a repacker for the game?
I've looked at some of the files and see potential there.
## Post #133
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-04T23:35:59+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from CobraGamer
>
> a repacker for the game?
Something like that will never be possible for an online game like The Crew 2 for example with out getting caught/banned, no matter what, there are many checks in place to see if anything gets modified, tampered with, hacked, so on and so forth, I couldn't be more happier that they added more security I was tired of a lot of cheaters and people who fucked up he game play on the first one with those trainers and hacks, no one wants that crap.

PS: this is the "memo", in case you missed it. 

> In order to serve its purpose of preventing and detecting the use of cheat software with the goal of ensuring a fair game environment, BattlEye may process the following information from you:
>
> 
>
> - IP address
>
> - Game identifiers (e.g. in-game name, account ID, etc.)
>
> - Hardware device information and identifiers (e.g. serial numbers)
>
> - Information about the running operating system
>
> - Information about game-related and operating-system-related files and memory
>
> - Information about running processes, drivers and other executable code
>
> - File names included in other information listed here, which might also contain your operating system user name
>
> 
>
> BattlEye follows a data minimization policy that ensures that data is only being stored when necessary, i.e. when BattlEye finds information that may potentially indicate the use of cheat software. As a result, BattlEye generally will not store any information on most users.
>
> 
>
> BattlEye may store the information for the entire duration of the provision of its services for the game.
>
> 
>
> You may contact Ubisoft at any time to exercise your rights in relation to this data processing. See BattlEye's Privacy Policy, https://www.battleye.com/privacy-policy/, and Ubisoft's Privacy Policy, https://legal.ubi.com/privacypolicy, for more information.
## Post #134
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-07-05T11:41:38+00:00
- Post Title: Re: The Crew fat/dat archives

What is able to be extracted from The Crew 2

Can someone provide pictures of what can be extracted

I have the game on PS4 but if models can be extracted then i probably will buy it for PC
## Post #135
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-07-05T13:59:26+00:00
- Post Title: Re: The Crew fat/dat archives

Everything can be unpacked, it's just a matter of finding the files you want as we don't have a complete filelist. As for the models, I don't know if the XBG format has changed from The Crew 1, but at the moment there's no way to open them, they are different from Watch Dogs and Far Cry XBG for sure.

@mono24: Anti-cheat software almost certainly only punishes modders, not cheaters. Cheaters will always find a way. Our changes would be much more harmless, as we don't aim to get an advantage over others by that.
## Post #136
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-07-05T20:54:47+00:00
- Post Title: Re: The Crew fat/dat archives

I only want the car models   

But i really hope someone will make an importer for the XBG files

That could be awesome
## Post #137
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-06T06:48:54+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from CobraGamer
>
> Everything can be unpacked
Well, not everything.

> Reply from CobraGamer
>
> ...at the moment there's no way to open them...
Wrong.


> Reply from Faithfullfaun
>
> 
But I really hope someone will make an importer for the XBG files
And as you can see above everything still works as should, I don't understand what else you want as an importer if models work.
## Post #138
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-07-06T07:46:12+00:00
- Post Title: Re: The Crew fat/dat archives

...and do you wanna tell us what program to open the XBGs with?
## Post #139
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-06T18:07:08+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from CobraGamer
>
> ...and do you wanna tell us what program to open the XBGs with?
Ummmm, your joking right?   
That's 3dsMax in the screenshot, everything has been posted already since 2013, but I guess that's what happens when no one cares to do a bit of search in the forum anymore, damn.
## Post #140
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-07-08T21:23:30+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from mono24
>
> That's 3dsMax in the screenshot, everything has been posted already since 2013, but I guess that's what happens when no one cares to do a bit of search in the forum anymore, damn.
Inappropriate answer for a serious question.
I was expecting a proper method instead of a plugin for a professional modelling software that is 1.5k USD per year.

> Reply from mono24
>
> CobraGamer wrote:Everything can be unpacked
Well, not everything.
Everything can be unpacked.
## Post #141
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-09T00:11:33+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from CobraGamer
>
> 
Inappropriate answer for a serious question.
Not only that a plain text does not carry proper tone, a question like that can not be taken too serious giving the fact everything is already posted, and people, yourself included, are still ignorant to the "search" function, which makes no sense, have you ever taken in to consideration as to why so many "serious questions" are left hanging? Just think about it, anyway.

> Reply from CobraGamer
>
> I was expecting a proper method instead of a plugin for a professional modelling software that is 1.5k USD per year.
There is a proper way, its a 3dsMax script that does the job just fine, we all use what we get here for free, I am sure you can make it work same way we all do even with its host expensive software .

> Reply from CobraGamer
>
> Everything can be unpacked.
Once again wrong, if you would have taken the time to look back in my post you'd see that NOT everything can be extracted giving the existing unpacker, period.
## Post #142
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-07-13T16:00:22+00:00
- Post Title: Re: The Crew fat/dat archives

I simply didn't expect a 3dsMax script from 2013 to still work, and not everybody can recognize software from a screenshot that's not even full screen sized.
Also, could you tell me what files can't be extracted? I'm not gonna test each of the 45 archives as it seems like you already did? Do some of the archives have a different format or something else that causes the unpacker to not work?
## Post #143
- Username: nicpad78
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 18, 2012 11:49 pm
- Post datetime: 2018-08-26T21:23:51+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from mono24
>
> CobraGamer wrote:Everything can be unpacked
Well, not everything.
CobraGamer wrote:...at the moment there's no way to open them...
Wrong.

Faithfullfaun wrote:
But I really hope someone will make an importer for the XBG files
And as you can see above everything still works as should, I don't understand what else you want as an importer if models work.

great job, you can understand what tools you used and have a list of the programs used to achieve this result
thank you!
## Post #144
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-15T20:23:45+00:00
- Post Title: Re: The Crew fat/dat archives

Did a few tests with The Crew 2 maps, they can be exported, format is the same as the Crew 1.
## Post #145
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-20T09:46:36+00:00
- Post Title: Re: The Crew fat/dat archives

The whole The Crew 2 road map loaded - 13 million vertices
Blender file is 1GB in size
## Post #146
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-10-20T14:58:07+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from daemon1
>
> The whole The Crew 2 road map loaded - 13 million vertices
Blender file is 1GB in size

How long did that take to load?
## Post #147
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-20T15:25:00+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Faithfullfaun
>
> daemon1 wrote:The whole The Crew 2 road map loaded - 13 million vertices
Blender file is 1GB in size

How long did that take to load?
After importing ascii into blender, this blender file loads in about 5 seconds.

Import is what takes long, it was about 10 or 15 minutes.
## Post #148
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-10-20T17:41:30+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from daemon1
>
> Faithfullfaun wrote:daemon1 wrote:The whole The Crew 2 road map loaded - 13 million vertices
Blender file is 1GB in size

How long did that take to load?  
After importing ascii into blender, this blender file loads in about 5 seconds.

Import is what takes long, it was about 10 or 15 minutes.

Okay then it's like Uncharted maps
Then i usally save them as blend. files to make it faster aswell
## Post #149
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-10-27T03:36:44+00:00
- Post Title: Re: The Crew fat/dat archives

More progress has been made by Daemon, this time terrain data, it all falls nicely with the rest of the game assets, for now they are only vertices in the 3D space, later on will be connected with faces, as usual more info will be posted in due time.
## Post #150
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-13T17:00:02+00:00
- Post Title: Re: The Crew fat/dat archives

For those of you who missed it, the released tool is located here: [viewtopic.php?f=16&t=19065](http://forum.xentax.com/viewtopic.php?f=16&t=19065)
## Post #151
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-12-18T20:11:51+00:00
- Post Title: Re: The Crew fat/dat archives

Is Ekey around>? im hoping somebody could look into or has already looked into the .xbt files again? TC2 beta had updated texture formatting using DX10, i was able to dump textures from xbt via a quick hex edit, but now, it seems impossible. Idk if maybe im missing something, or theres a new tool as its been a while since messed with files, but would like to get back at the game asap. Even a work-around would be handy for now, as its only for 3 vehicles but essentially more
## Post #152
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-20T05:19:16+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Dennissaurus
>
> TC2 beta had updated texture formatting using DX10, i was able to dump textures from xbt via a quick hex edit, but now, it seems impossible.
Everything still works same, even in beta even in last release, all you got to do is delete everything until DDS and save it and IrfanView displays them properly.
Or use a batch mode as shown in screenshot as well, drag and drop as many as you want, you get the idea.



001.JPG (128.52 KiB) Viewed 675 times


have fun
## Post #153
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-12-20T20:28:16+00:00
- Post Title: Re: The Crew fat/dat archives

Welp, i didnt know about BATCH method.. thank you  i was using HxD and visual studio for same thing previously... i must be getting old or smoking too much  Thanks again
## Post #154
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2019-04-27T04:55:56+00:00
- Post Title: Re: The Crew fat/dat archives

I succesfull imported some parts from models but i was wondering if there is a more finished  __UNKNOWN_XBG_Renamer.rar 
or is there a other way to find the  complete models sorted?
## Post #155
- Username: dhcnmtcs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 10, 2017 10:57 am
- Post datetime: 2019-04-27T09:21:20+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from justspeeding ↑Sat Apr 27, 2019 12:55 pm at Sat Apr 27, 2019 12:55 pm
>
> 
I succesfull imported some parts from models but i was wondering if there is a more finished  __UNKNOWN_XBG_Renamer.rar 
or is there a other way to find the  complete models sorted?
im still working on it (this renames files in vehicle_resources_patch)
[XBG_Renamer_Update3.rar](https://xentaxbackup.github.io/file/16127_XBG_Renamer_Update3.rar)
## Post #156
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2019-05-14T15:54:05+00:00
- Post Title: Re: The Crew fat/dat archives

Thx
## Post #157
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-06-24T19:36:38+00:00
- Post Title: Re: The Crew fat/dat archives

Hi, i have a problem about xbg file format. i unpacked vehicles.dat with  unpacker 0.0.2a r2, then i get folders with vehicle names, but in these folders  only rim files have .xbg extension, files in "map" folder  have xbt extension, so i couldnt import them with 3dsmax. i also run XBGmover (from Unpacked folder) but i think it didnt make anything. idk am i missing something or did something wrong.
## Post #158
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-06-24T19:45:09+00:00
- Post Title: Re: The Crew fat/dat archives

That is beacuse XBT is a texture where XBG are models
## Post #159
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-06-24T19:51:09+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Faithfullfaun ↑Tue Jun 25, 2019 3:45 am at Tue Jun 25, 2019 3:45 am
>
> 
That is beacuse XBT is a texture where XBG are models

yes that is right. i need vehicle model files with xbg extension to import them 3dsmax, but how could get these files or where to find?
## Post #160
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-25T02:40:12+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from nicotine41 ↑Tue Jun 25, 2019 3:51 am at Tue Jun 25, 2019 3:51 am
>
> but how could get these files or where to find?
But if you said you already dumped/extracted the game files with the unpacker , what else are you looking for?
The models are all there after extraction.
## Post #161
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-06-25T14:54:08+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from mono24 ↑Tue Jun 25, 2019 10:40 am at Tue Jun 25, 2019 10:40 am
>
> 
nicotine41 wrote: ↑Tue Jun 25, 2019 3:51 ambut how could get these files or where to find?

But if you said you already dumped/extracted the game files with the unpacker , what else are you looking for?
The models are all there after extraction.

there are folders with vehicle brand/model names, but there is no 3d file in it (interior,exterior,wheels etc.), only rims have 3d model. Also there are 3d files in another folder with name "_unknown" but these are only interior.
## Post #162
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-25T15:01:04+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from nicotine41 ↑Tue Jun 25, 2019 10:54 pm at Tue Jun 25, 2019 10:54 pm
>
> Also there are 3d files in another folder with name "_unknown" but these are only interior.
Yes all geometry is there, its highly tedious and almost impossible to know what its what until you import each and one of them at a time and see where it fits what matches with what vehicle, so on and so forth.
The reason you do NOT see them in the created folder structure is because the rest of the stuff has no names, Only hashes, that's it.

good luck
## Post #163
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-06-26T01:52:41+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from mono24 ↑Tue Jun 25, 2019 11:01 pm at Tue Jun 25, 2019 11:01 pm
>
> 
nicotine41 wrote: ↑Tue Jun 25, 2019 10:54 pmAlso there are 3d files in another folder with name "_unknown" but these are only interior.

Yes all geometry is there, its highly tedious and almost impossible to know what its what until you import each and one of them at a time and see where it fits what matches with what vehicle, so on and so forth.
The reason you do NOT see them in the created folder structure is because the rest of the stuff has no names, Only hashes, that's it.

good luck

Thanks for the answer, 

so i have to arrange model files myself, this will take lots of time i guess.
## Post #164
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2019-11-16T00:35:15+00:00
- Post Title: Re: The Crew fat/dat archives

Has anyone made a texture tool for Crew 2 yet?  Kinda tiring removing the first 36 from each file via hex then converting DX10 down to DX9 for viewing.

(2000+ textures alone found within the nov 2019 DLC alone...)
## Post #165
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-11-16T00:43:06+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Dennissaurus ↑Sat Nov 16, 2019 8:35 am at Sat Nov 16, 2019 8:35 am
>
> Kinda tiring removing the first 36 from each file via hex...
The above still works: [viewtopic.php?p=146821#p146821](https://forum.xentax.com/viewtopic.php?p=146821#p146821)
## Post #166
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2020-01-06T03:44:12+00:00
- Post Title: Re: The Crew fat/dat archives

i know just so busy with work i didnt get a chance to "update" my normal process/software thank you though. Seems plenty of people are jumping on board, so will hold out a while, see if i can compile a texture pack for those in need.
## Post #167
- Username: Den4ik
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 15, 2018 6:13 am
- Post datetime: 2020-01-17T12:46:57+00:00
- Post Title: Re: The Crew fat/dat archives

Hi everyone! Tell me, what could be the problem? How to correct it? If you import any file from the updated vehicles_resources_patch.dat archive into 3D max, bitwise reflections on the model, if you take any file from the old archive vehicles_resources.dat the models are fine.
[](http://www.imagebam.com/image/1cca9e1331203352)[](http://www.imagebam.com/image/464dae1331203348)
## Post #168
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-01-17T17:17:02+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from Den4ik ↑Fri Jan 17, 2020 8:46 pm at Fri Jan 17, 2020 8:46 pm
>
> ...what could be the problem?
Not an expert but, looks like they might have changed the way normals are processed?
And I doubt there will ever be any updates for The Crew games tools and such from original creators, unless someone else takes over.
## Post #169
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-01-17T21:39:26+00:00
- Post Title: Re: The Crew fat/dat archives

Hi, anyone still has Ekey's The Crew DAT Unpacker? A DL link in OP is dead as well as [this](https://forum.xentax.com/viewtopic.php?f=10&t=11719&start=105#p139165).
Thanks in advance!

EDIT: It seems I found unpacker (FC5.Unpacker.exe) but now I've got to obtain a filelist because the one in the very 1st post isn't available anymore... Anyone able to give me a hand?
Bye!
## Post #170
- Username: Den4ik
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 15, 2018 6:13 am
- Post datetime: 2020-01-18T08:48:13+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from GenericRipper ↑Sat Jan 18, 2020 5:39 am at Sat Jan 18, 2020 5:39 am
>
> 
Hi, anyone still has Ekey's The Crew DAT Unpacker? A DL link in OP is dead as well as this.
Thanks in advance!

EDIT: It seems I found unpacker (FC5.Unpacker.exe) but now I've got to obtain a filelist because the one in the very 1st post isn't available anymore... Anyone able to give me a hand?
Bye!

Here
[https://mega.nz/#!oU0nSSJI!guXm6zBCUJ9U ... kI7Wm77R_o](https://mega.nz/#!oU0nSSJI!guXm6zBCUJ9U9pAEWg68iLkzvtut_4ByikI7Wm77R_o)
[https://mega.nz/#!MQ8BiIxQ!ZvgEHVeCzbWV ... SX2zEvFGjQ](https://mega.nz/#!MQ8BiIxQ!ZvgEHVeCzbWVuwBhwsl5ZdEVeqqBO9RqDSX2zEvFGjQ)
## Post #171
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-06-01T13:20:21+00:00
- Post Title: Re: The Crew fat/dat archives

hey everyone

i've spent the last few weeks to check and convert the xbg files of the crew 2 (and still not done yet)

[https://i.imgur.com/GiyCnpF.png](https://i.imgur.com/GiyCnpF.png)

is there anyone who can check the material.bin files to locate the correct textures?

looking at "maximerea-m-0612201360591549.material.bin" it is called "SG_Police_LosAngeles" looking for the XBT
graphics\vehicles\traffic_cars\traffic_brand\common_maps\decals_losangeles_new.xbt

in the yet unknown folder, i found a police texture with an los angeles badge on it - called "AAC8D87D6F37D6CA.xbt"

is there a way to identify the cryptic names of the textures somehow through hex editing?

could not find any reference to xbg names of any car parts so far
## Post #172
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-06-28T21:07:22+00:00
- Post Title: Re: The Crew fat/dat archives

The XBT you've found is the one you're looking for.

You can add any filenames you found to Projects/FileNames.list. In most cases though, the game only references texture files (and other resources) by hash, meaning it's practically impossible for us to get the original filenames for them.
## Post #173
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-08-06T08:51:04+00:00
- Post Title: Re: The Crew fat/dat archives

it's me again ... did some more research and found a few informations about restoring the 4 vehicles_resources_x files

a lot of the xbt files had its path in the header before the correct dds file starts

```
TBX (...) graphics\vehicles\cars\ford\ford_gt_2016\maps\tex_ford_gt_2016_detail_01_a_mip0.xbt.DDS
```


most informations can be found in the material.bin files

```
TAM (...) SG_Glass_Racing_Int (...) ITCarGlass (...) graphics\vehicles\cars\dodge\dodge_charger_1969\maps\racing_glass_c.xbt (...)
```


and inside of the vehicles_resources_hr the xbt are calling for _miphr.xbt
so its a possible combination of *.xbt _mip0.xbt and _miphr.xbt
i added those possible combinations to the filelist and found all vehicle textures (except for a bunch of livery/vinyl textures and ui stuff)

to restore the material.bin filenames it would need a tool to scan the xbg files from the start HSEM to the EDON and print out the paths

```
HSEM (...) GRAPHICS\_MATERIALS\HU (...) .material.bin.EDON
```


on top of that, in the starter.dat i found a xml file which referred to one vehicle .xbg
extended that path to all cars and found 7300 xbg names so far


i may upload a updated filenames.list here if anyone is still interested in this game
## Post #174
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-07T00:09:36+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from guki ↑Thu Aug 06, 2020 4:51 pm at Thu Aug 06, 2020 4:51 pm
>
> i may upload a updated filenames.list here if anyone is still interested in this game
Sure, that'd be great, maybe I can join in and help move faster, I might help with the process if you want here or via PM or even discord, I happen to love these game series.
## Post #175
- Username: dhcnmtcs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 10, 2017 10:57 am
- Post datetime: 2020-08-08T09:38:53+00:00
- Post Title: Re: The Crew fat/dat archives

Here's an XBT Viewer. Can post the source code if anyone wants it 
[XBT viewer 0.2.1.rar](https://xentaxbackup.github.io/file/18574_XBT viewer 0.2.1.rar)
## Post #176
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-09T01:44:37+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from dhcnmtcs ↑Sat Aug 08, 2020 5:38 pm at Sat Aug 08, 2020 5:38 pm
>
> 
Here's an XBT Viewer.
Thanks, a nice tool that comes handy while searching for specific textures.
Right know it works very slow on my end, takes a while to load the textures, and you think its possible when you maximize the UI window, the textures stretch to the windows resolution, is it possible for them to keep their actual size in the preview window?
Also it sais on the UI v0.2 not 0.2.1 as in your name above.
## Post #177
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2020-12-20T00:27:59+00:00
- Post Title: Re: The Crew fat/dat archives

thats a lot of progress mate  did you manage to get a new filelist made?
## Post #178
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2021-02-26T20:15:10+00:00
- Post Title: Re: The Crew fat/dat archives

does anyone still working on this?
Sadly I don't have any luck finding new mesh names.
## Post #179
- Username: TheCrewMapLover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2021 3:44 pm
- Post datetime: 2021-06-11T22:22:59+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from headrushmayor ↑Sun Oct 15, 2017 12:29 pm at Sun Oct 15, 2017 12:29 pm
>
> 
hi all i unpacked all dat files came too 175gb's so watch out as know sound in game way to low i use FMOD FSB Extractor get all wav files out there about 167gb's files so redid them in mp3 took down too 2.6gb's still sound so good in game they sound better then wav files save alot of space. i upload them to mega.nz u download them play around with them if like i have edit sum files use Audio Speed Changer Pro to chance pitch to -6 give cars and other sound in game bit low end kick to them as well used dbpoweramp boost sound up still a lot to do to sound files as play around u see going street to fullstock cars sound same so if use Audio Speed Changer Pro chance pitch i did street stock, racing -2.5, perf -5, fullstock to -8 u hear different in game now it like it unlock sound as cars sound better. here link for files if post here.

https://mega.nz/#!cvY1TaIY!pTrAPtydFV-J ... SowcRojdsw
Hi can you please upload it again im a sound designer this would be very useful to me. Hope for a answer
## Post #180
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-11T23:15:37+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from TheCrewMapLover ↑Sat Jun 12, 2021 6:22 am at Sat Jun 12, 2021 6:22 am
>
> Hi can you please upload it again im a sound designer this would be very useful to me. Hope for a answer
I would recommend to get them yourself, even if you do not own the game, there's the trial you can get from Steam, it holds all the assets, and unpack the audio assets only using Ekey's unpacker for the game, in their original form are less GB in size, then you'd use foobar2000/vgmstream combo to play/convert to your format of choosing for what ever project you wish, asking for those assets its against the rules anyway.
## Post #181
- Username: TheCrewMapLover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2021 3:44 pm
- Post datetime: 2021-06-12T12:44:48+00:00
- Post Title: Re: The Crew fat/dat archives

Thanks i already have the beta of the game for converting also the map. I will try the steps that you told me. I have some questions for you. How can i export multiple areas from the map. I can only export all sectors but not all areas is there a method or do i have to live with it. The next is, ive sucessfully managed to convert the files but in blender i can only export one ascii file at the time. But because ive exported 500 ascii files it would be really big pain to convert all them manually. Do you have maybe a software where you convert multiple ascii files at once to fbx. The last is do i have to put the textures on the models manually or can it be done automatic. Wouldnt matter ive i would have to do them manually. Just wanna know: Hope again for a nicely helpful answer from you
## Post #182
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-12T13:01:48+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from TheCrewMapLover ↑Sat Jun 12, 2021 8:44 pm at Sat Jun 12, 2021 8:44 pm
>
> ...How can i export multiple areas from the map...
Same way, except you add them to a batch one line after another, and it will be exported one area after another, make sure you have at least a free 10TB HDD though, as the game is insanely large since it exports in the ASCII which is basically a text format, that means NO compression what so ever, hence large ASCIIs.

> Reply from TheCrewMapLover ↑Sat Jun 12, 2021 8:44 pm at Sat Jun 12, 2021 8:44 pm
>
> ...but in blender i can only export one ascii file at the time. But because ive exported 500 ascii files it would be really big pain to convert all them manually...
Assuming you meant importing one at a time, then yes, there's no other way to bring them inside a 3D editor, such as blender in a batch that i am aware of.

> Reply from TheCrewMapLover ↑Sat Jun 12, 2021 8:44 pm at Sat Jun 12, 2021 8:44 pm
>
> ...Do you have maybe a software where you convert multiple ascii files at once to fbx...
Unfortunately myself, same as you, we are all stuck using this workflow, there is simply no other way, again, that i am currently aware of.
You could try Noesis, it has a batch mode, see how that works for you, although it will be problematic, as everything must go through Blender no matter what, other wise you will screw up the proper scale of the assets and terrain, otherwise nothing will match, and trust me you don't want that on this scale of the map.

> Reply from TheCrewMapLover ↑Sat Jun 12, 2021 8:44 pm at Sat Jun 12, 2021 8:44 pm
>
> ...The last is do i have to put the textures on the models manually or can it be done automatic...
Sadly yes, which it will take you probably two years to do textures alone, or maybe a whole year if you work on it constantly, so good luck on that one.
## Post #183
- Username: TheCrewMapLover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2021 3:44 pm
- Post datetime: 2021-06-12T14:16:29+00:00
- Post Title: Re: The Crew fat/dat archives

Hey thank you very much for answering all questions, they were very helpful. Yeah i already have a 50tb ssd so that wouldnt be a problem. WIth the multiple areas i meant, all at the time so that i dont have to type like 0 0 8 8, 0 1 8 8 , 0 2 8 8, 1 0 8 8 etc. So that i can tell the exe will try export all of them together without typing every command of every area to convert. So with the ascii thats bad news so i need to be very patient. With the textures, i have people that i pay for doing that work, so they could apply all textures manually, so it would take about 1 month for the whole map. Because the project is for a sim game i have about 1000 supporters for this project,it will be like a pack with sounds of the crew as mods for the game, and of course the map included as a mod. Theres another problem, with importing ascii files into blender. I was able to export them as fbx, but i cannot see them in blender, even tho i have increased the render distance, i cannot see the models, do you have a solution for that problem, my supporters and workers also have the same problem. And another question: after exporting them as fbx, is it possible to place the textures also in 3ds max, because im struggling with Blender since i started modelling. And the last: when importing the ascii files, are they already placed where they sould be so that after importing all ascii files, so that they are all placed where they are like in the game, so it looks like a city where the trees, houses etc. are placed where they are. Is the terrain also automatically positioned so that the ascii files fit perfectly onto the terrain. So other than the textures the map itself would be game ready?

Sorry for my english im in a hurry, so i cant really pay attention on how to write it correctly

 You are very important to me and im really thankful, because i have to give the instructions you tell me to the people that i pay, so that everything works fine, and work can be perfectly done. And some end result would be in the end. Im really sorry for disturbing you, but i have no other person where i can get support of this specif topic.
## Post #184
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-12T15:16:05+00:00
- Post Title: Re: The Crew fat/dat archives

Your last message changes everything, due to your project, long story short...

Been trying to stitch this map together, due to being tiled by sectors, its like a puzzle, but for main parts, not small assets where instancing is required, all alone for a very long time, few years back, after a while i had given up on it of course, it was insane, then i had found out terrain was not just plain geometry, it was a height map data that needed to be reversed to actual geometry, among other things.
Later on i asked the reverser/dev ID-Daemon (daemon1) if he would support the first game, as initially second game wasn't known about, then second game was released, tool he posted is for second game only, not first, currently the tool is in an unfinished state, its more like a test tool at this point, all blend maps for the terrain aren't even exported, terrain has issues here and there, needs a bit further reversing for accuracy, etc. and if i am not mistaken, as i do not remember anymore, not everything is supported from the games assets/types, but i could be wrong, its been too long.

At same time instancing is NOT supported, as every single assets once converted to ASCII is turned in to each individual assets, that's why there's such a huge amount of hundreds of GB up on export, if you decide to ignore it, you WILL have to think of a way to turn everything back to instancing in your preferred 3D editor, with current state of the tool, and that is NO easy task, it gets complicated, more and more.
You would then have to export everything as each sector then, NOT area, think about it, any game engine out there, based on games progression it loads map assets/terrain incrementally based on player progression, otherwise its impossible to load such large map, instancing is the key here, among other optimizations and such. And The Crew series use sectors to load things as you drive around, in different levels of LODs based on how far/close you are.

As for Blender, i never encountered your issue, increasing the draw distance solves the viewing of the assets, as everything is exported as in-game with global coordinates not local, everything gets placed accordingly where they belong and where intended by the game devs, if increasing draw distance didn't solve your issues, you guys did something wrong and need to start all over.
You can import your assets in ANY 3D editor of your choosing, is irrelevant where you want to apply textures, you can use even a game engine, its same procedure.
For this massive thing your doing, I'd suggest to put it on hold, otherwise you'll waste your money, and since your involving money here for content you do NOT own copyrights, I'm not sure is a good idea.

I have never done modding, and its a very gray area for me, legally not sure what is OK or NOT OK to do, again, once money are involved with content you do NOT own copyrights/permission.

I per say am not a technical guy or know how to explain everything accordingly and/or accurately, so i did my best to explain what i have been dealing with thus far.

Too bad i didn't know about this large scale project way back, the progression would have been that much quicker, as i too was interested in the map to be exported, now i doubt the initial dev of the tool will ever continue the research to support fully both games, i have been wishing this for far too long, and it is what it is at this stage.
## Post #185
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-12-04T22:02:15+00:00
- Post Title: Re: The Crew fat/dat archives

@Ekey, can you tell me the algorithm for converting string to CRC64 hash for TC1/TC2?
I'm making a tool to collect materials/textures
## Post #186
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-05T00:26:51+00:00
- Post Title: Re: The Crew fat/dat archives

[https://github.com/PeterScott/rdbparser ... er/crc64.c](https://github.com/PeterScott/rdbparser/blob/master/crc64.c)
## Post #187
- Username: CryptoCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 20, 2021 6:26 am
- Post datetime: 2022-05-09T18:43:53+00:00
- Post Title: Re: The Crew fat/dat archives

Is there a more recent filelist than TC_Projects_u4?
## Post #188
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-10T13:45:48+00:00
- Post Title: Re: The Crew fat/dat archives

I think nope. You must manually check for every file. Thanks to Ubisoft logic...
## Post #189
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-10T15:20:06+00:00
- Post Title: Re: The Crew fat/dat archives

> Reply from SanJose ↑Fri Jun 10, 2022 9:45 pm at Fri Jun 10, 2022 9:45 pm
>
> 
I think nope. You must manually check for every file. Thanks to Ubisoft logic...
no you dont have to manually check anything
i recently made a tool that sorts everything out
