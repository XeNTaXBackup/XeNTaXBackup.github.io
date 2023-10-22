## Post #1
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2016-12-19T12:33:30+00:00
- Post Title: Resident Evil 7 demo PAK file

The free RE7 demo has been released for PC.

```
http://store.steampowered.com/app/530620/
```


Its data is contained in a single 3 gig PAK file. It runs on a new in-house engine. For the hell of it I tried Street Fighter's UE4 pak file unpacker but as expected it failed.
## Post #2
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2016-12-19T13:09:31+00:00
- Post Title: Resident Evil 7 demo PAK file

What format RE6 used?
## Post #3
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-12-19T13:34:32+00:00
- Post Title: Resident Evil 7 demo PAK file

Furthest I've got so far:

```
{
	uint32_t magic;
	uint32_t version; // ?
	uint32_t num_entries;
	uint32_t unk; // checksum?
};

struct REPak_Entry // 0x30 bytes
{
	uint64_t unk0; // data hash / filename hash / crypto key?
	uint64_t offset; // offset into the pak file
	uint64_t size;
	uint64_t unk18; // flags? 0x1EA0 for most files
	uint64_t unk20; // more flags? 0x1 for most files
	uint64_t unk28; // data hash / filename hash / crypto key?
};

```


Not very far I know, seems they're protecting the demo with Denuvo to make RE even harder  Maybe that could mean there's some goodies in here somewhere though.

Looks like file data is compressed/encrypted too, also can't see any filenames in there, could be using a filename-hash system like Fox Engine does?

EDIT: Saw some strings mentioning the saves using blowfish encryption, perhaps the package does too.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-19T14:46:10+00:00
- Post Title: Resident Evil 7 demo PAK file

```
{
   uint32_t dwID; // KPKA
   uint32_t dwVersion; // 4
   uint32_t dwTotalFiles;
   uint32_t dwUnknown0; //???
};

struct PAKEntry
{
   uint32_t dwLowerHash; // Hash of filename in Lowercase
   uint32_t dwUpperHash; // Hash of filename in Uppercase
   uint64_t dwOffset;
   uint64_t dwZSize; // Compressed size
   uint64_t dwSize; // Uncompressed size
   uint64_t dwFlag; // 1 - if compressed / 0 - uncompressed
   uint32_t dwUnknown2; //???
   uint32_t dwUnknown3; //???
};
```


Compression is Zlib (Deflate)
## Post #5
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2016-12-19T15:17:37+00:00
- Post Title: Resident Evil 7 demo PAK file

> Reply from Kein
>
> What format RE6 used?

It used ARC files for the MT-Framework engine.
## Post #6
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-19T15:35:37+00:00
- Post Title: Resident Evil 7 demo PAK file

> Reply from zzz
>
> Kein wrote:What format RE6 used?

It used ARC files for the MT-Framework engine.

For most of the game assets, yes. Except this archive format for RE7 is an altered version of the PAK format used for shaders (in RE5/6) I believe. Though encrypted and/or compressed for RE7.

Cheers.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-19T21:28:02+00:00
- Post Title: Resident Evil 7 demo PAK file

Simpe script for unpack

Edited: See below
## Post #8
- Username: blizdi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 20, 2016 7:50 am
- Post datetime: 2016-12-20T00:03:35+00:00
- Post Title: Resident Evil 7 demo PAK file

Do we know how long it will take before the unpacked files are going to be usable/viewable? I assume they don't work like RE6's files lol
## Post #9
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2016-12-21T08:06:29+00:00
- Post Title: Resident Evil 7 demo PAK file

Aren't they encrypted?
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-21T13:08:14+00:00
- Post Title: Resident Evil 7 demo PAK file

> Reply from Kein
>
> Aren't they encrypted?
No.
## Post #11
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2016-12-21T13:15:30+00:00
- Post Title: Resident Evil 7 demo PAK file

Okay, so I suppose some people will tweak existing tools for RE6 to be able to process RE7 data.
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-21T13:30:53+00:00
- Post Title: Resident Evil 7 demo PAK file

> Reply from Kein
>
> Okay, so I suppose some people will tweak existing tools for RE6 to be able to process RE7 data.
No, all formats I've seen so far, except the texture format has been altered.
## Post #13
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2016-12-21T14:24:19+00:00
- Post Title: Resident Evil 7 demo PAK file

> Reply from Gh0stBlade
>
> Kein wrote:Okay, so I suppose some people will tweak existing tools for RE6 to be able to process RE7 data.
No, all formats I've seen so far, except the texture format has been altered.
Texture format was altered too at least ARCtool does not work anymore with it
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-29T22:37:59+00:00
- Post Title: Resident Evil 7 demo PAK file

Well, i'm found algorithm. First and second fileds in entry this is hash'es of file name in lowercase and uppercase. To be continue
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-30T02:26:51+00:00
- Post Title: Resident Evil 7 demo PAK file

Here we go. Script updated, names included (~2000 unknown names at this moment). Have fun 
[re7_pak_unpack_r2.rar](https://xentaxbackup.github.io/file/12140_re7_pak_unpack_r2.rar)
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-12-30T10:17:46+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Here we go. Script updated, names included (~2000 unknown names at this moment). Have fun

Nice.. Thx ekey
## Post #17
- Username: teranio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 30, 2016 6:57 pm
- Post datetime: 2016-12-31T11:54:27+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

[s]Ekey, can you post hash function, please?[/s]

OK, I found it. MurmurHash
## Post #18
- Username: Justreg2seeFile
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 12, 2017 6:09 am
- Post datetime: 2017-01-11T22:14:48+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Here we go. Script updated, names included (~2000 unknown names at this moment). Have fun
Any update yet?
I have more files with a hack extracted but 1. there over 2k left, and second i have no idea why you list them like 
3399843968 natives/x64/aaa/ambassadortrial/environment/mesh/chapter1/c01_corridor01.mdf2.6
Because i created a md5 check like
bad663e310897f0d1cbf2cc870066384	0000000000001f84.bkh
which is
bad663e310897f0d1cbf2cc870066384	natives/X64/Sound/Wwise/sm1352.bnk.2.X64
how i put it into the list?
did it work if i just use
0000000000001f84.bkh natives/X64/Sound/Wwise/sm1352.bnk.2.X64
?
Other example, the second video file
6b55f18a8358ac56896019194d49a28a	natives/X64/streaming/AAA/AmbassadorTrial/Movie/AmbassadorTrialEndMovie.mov.1
is
6b55f18a8358ac56896019194d49a28a	00000000000003f3.dat
Don't belive me? open the 3f3.dat with VLC player 
[FileList.zip](https://xentaxbackup.github.io/file/12206_FileList.zip)
## Post #19
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2017-01-12T16:02:29+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Anyone figure out how to open the sdf files?
## Post #20
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-01-24T22:35:00+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

i used the pak tool on retail but its unusable files. can the resource hack dll be updated for retail version?
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2017-01-24T22:46:01+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

crude exporter on xnalara site. models and textures... just need ekey to do his thing lol.
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-25T00:58:00+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from howfie
>
> just need ekey to do his thing lol.
what you mean? script for unpack is ready > [viewtopic.php?p=125600#p125600](http://forum.xentax.com/viewtopic.php?p=125600#p125600) . I can't update list with names because i don't have the game lal
## Post #23
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-25T12:41:38+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> howfie wrote:just need ekey to do his thing lol.
what you mean? script for unpack is ready > viewtopic.php?p=125600#p125600 . I can't update list with names because i don't have the game lal
I have it, can you tell me how to create a file list of that?
I unpacked all files from the pak, 41.207 files   
How i do a list like you did? I really want to mod the game
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-25T13:48:27+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from 35234917DOTmp4
>
> 
I have it, can you tell me how to create a file list of that?
I unpacked all files from the pak, 41.207 files   
How i do a list like you did? I really want to mod the game
For DEMO i written special hook to get names.
## Post #25
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-25T13:56:07+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> 35234917DOTmp4 wrote:
I have it, can you tell me how to create a file list of that?
I unpacked all files from the pak, 41.207 files   
How i do a list like you did? I really want to mod the game 
For DEMO i written special hook to get names.
Are you reminer from reddit?
## Post #26
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-01-25T21:21:57+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> howfie wrote:just need ekey to do his thing lol.
what you mean? script for unpack is ready > viewtopic.php?p=125600#p125600 . I can't update list with names because i don't have the game lal

ill family share the game with you on steam. well worth it.
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-25T23:07:57+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Here is my Hook. Extract two DLL's in game folder and run the game. After play you can see RE7Hook.log file, just send it to me.

PS: Thanks to Haoose for provided executable. 
[RE7Hook_0.01_r2.rar](https://xentaxbackup.github.io/file/12289_RE7Hook_0.01_r2.rar)
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2017-01-26T00:31:14+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Awesome lol. Told you just gotta wait for Ekey, king of hooks, to do his thing hahahaha. Ekey, how do you find the function to hook? Do you just step through a debugger checking eax or something?
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-26T01:04:36+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Yep, debugging mechanism of reading PAK files.
## Post #30
- Username: 35234917DOTmp4
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-01-26T01:28:27+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Ekey
Thanks. And here 34182/43258 filenames for you =)


 RE7Hook34182.rar
(152.6 KiB) Downloaded 507 times
## Post #31
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-01-26T01:31:54+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Here is my Hook. Extract two DLL's in game folder and run the game. After play you can see RE7Hook.log file, just send it to me.

PS: Thanks to Haoose for provided executable.

Here ya go 

[https://drive.google.com/open?id=0Byccq ... ENlU2RWc1U](https://drive.google.com/open?id=0ByccqhR9ERGHanBLTENlU2RWc1U)

edit, the file kept getting larger in size.

[https://drive.google.com/open?id=0Byccq ... kRXZW1WWVU](https://drive.google.com/open?id=0ByccqhR9ERGHSGdLMkRXZW1WWVU)
## Post #32
- Username: 35234917DOTmp4
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-01-26T08:34:23+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Hi Ekey,

Can you please post the hash function for filenames ? Im writing repacker and i would like to know it..

Thx
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-26T13:05:24+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> Hi Ekey,

Can you please post the hash function for filenames ? Im writing repacker and i would like to know it..

Thx
Hash is Murmur 3.

All submitted logs is combined > [Update 1](http://dropmefiles.com/eDfDg) , [Update 2](http://dropmefiles.com/0UxNC)
## Post #34
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2017-01-26T15:12:19+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

wow great progress, keep it up guys!

Can anyone have ago at opening any of these?
I'm wanting to take alook at any of the shading stuff if possible.

4198720342 natives/x64/systems/shader/advancedsystem.sdf
335903976 natives/x64/systems/shader/advancedsystem.sdf.69
289272597 natives/x64/systems/shader/atmosphericscattering.sdf
1277990896 natives/x64/systems/shader/atmosphericscattering.sdf.69
4056491122 natives/x64/systems/shader/cgexpressions/cgexpressions.sdf
2132654139 natives/x64/systems/shader/cgexpressions/cgexpressions.sdf.69
1522912452 natives/x64/systems/shader/computeshadervfx.sdf
2711776306 natives/x64/systems/shader/computeshadervfx.sdf.69
3888094553 natives/x64/systems/shader/fog.sdf
1221640865 natives/x64/systems/shader/fog.sdf.69
617075997 natives/x64/systems/shader/fur.sdf
741030720 natives/x64/systems/shader/gridfluid2d.sdf
103378681 natives/x64/systems/shader/gridfluid2d.sdf.69
2694818063 natives/x64/systems/shader/lighting.sdf
751994732 natives/x64/systems/shader/lighting.sdf.69
1178293010 natives/x64/systems/shader/lightingfornextproject.sdf
2185547900 natives/x64/systems/shader/lightingnvidia.sdf.69.x64
1370271712 natives/x64/systems/shader/lightingnvidia.sdf.69.x64.en
928259135 natives/x64/systems/shader/lightshaft.sdf
1382955473 natives/x64/systems/shader/lightshaft.sdf.69
266863774 natives/x64/systems/shader/polynomiallens.sdf
1349277477 natives/x64/systems/shader/polynomiallens.sdf.69
2635296795 natives/x64/systems/shader/primitive.sdf
1992174239 natives/x64/systems/shader/primitive.sdf.69
1966723160 natives/x64/systems/shader/shallowwater.sdf.69.x64
3195472901 natives/x64/systems/shader/shallowwater.sdf.69.x64.en
1589854536 natives/x64/systems/shader/smaa.sdf
1228641740 natives/x64/systems/shader/system.sdf
4090296213 natives/x64/systems/shader/system.sdf.69
3821612456 natives/x64/systems/shader/systemdevelop.sdf
3697887126 natives/x64/systems/shader/systemdevelop.sdf.69
## Post #35
- Username: mazz3d
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-01-26T15:58:23+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

redspike474


 shader.rar
From Game (377.19 KiB) Downloaded 77 times




 shader.rar
From Patch (406.05 KiB) Downloaded 64 times
## Post #36
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2017-01-26T16:23:58+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Thanks ! any idea what the file format is? would be nice to recover some of the shader info.
Wanting to write a shader for max/maya to emulate the re7 shading.
## Post #37
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-26T17:07:33+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Updated my Hook. In log is written only file names that begin with the natives. 

PS: Thanks to Haoose for tests  

Edited: See on next page
## Post #38
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-26T17:49:56+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Haoose
>
> redspike474
shader.rar
shader.rar
Can you share your quickbms list with us?

Oh i miss that thank you.
## Post #39
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-01-26T17:55:15+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

35234917DOTmp4
[viewtopic.php?p=126754#p126754](http://forum.xentax.com/viewtopic.php?p=126754#p126754)
## Post #40
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-26T19:34:45+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Updated my Hook. In log is written only file names that begin with the natives.
[V3 Log](http://www.mediafire.com/file/65n8nq99oskbleg/RE7Hook.zip)


Ekey can you help me to make this [hook](http://www.mediafire.com/file/g5ysdh30kd2fji2/RE7PATCH_sc.zip) work for re7?
It worked with the demo, but sadly not with the retail even if i change the filename to re7trial.exe
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-26T19:44:24+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from 35234917DOTmp4
>
> 
V3 Log
Thanks. Added ~400 names > [Update 3](http://dropmefiles.com/iEchA)

> Reply from 35234917DOTmp4
>
> 
Ekey can you help me to make this hook work for re7?
It worked with the demo, but sadly not with the retail even if i change the filename to re7trial.exe
In this source you hook CreateFile. My variant is detouring hash algorithm (Murmur 3). RVA address is 0x93E8C20 in current version.
## Post #42
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-26T19:49:31+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> 35234917DOTmp4 wrote:
V3 Log
Thanks. Added ~400 names > Update 3
35234917DOTmp4 wrote:
Ekey can you help me to make this hook work for re7?
It worked with the demo, but sadly not with the retail even if i change the filename to re7trial.exe
In this source you hook CreateFile. My variant is detouring hash algorithm (Murmur 3). RVA address is 0x93E8C20 in current version.
Yeah i know, it creates the files while you play.
So replace 0x123A5678 with 0x93E8C20? I have no idea about it, someone else programm the dll hook.
Somehow my saves broke, otherwise i could load later sav stats for the log.
## Post #43
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-26T21:12:21+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from 35234917DOTmp4
>
> 
So replace 0x123A5678 with 0x93E8C20?
Then why are you trying to do something that is already there? I mean about my hook. What is not satisfied? It works without any problems.
I do not want honestly edit another's source code. Where you got it and who author? If you don't know what you need to fix for it I think it is better you contact the author of this source.
In current code is hooking two RVA addresses:

```
const LPVOID addr_files_construct_ver2 = (LPVOID)0x000000000827648A;
```
## Post #44
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-27T00:36:44+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Okay, your unpacking list works just perfect, i only have to leave the patch.pak in the folder, to make natives folder work 
Somehow it will not load, i unpack the patch pak now to test if it works if i put it in the original natives folder.
But really...thank you very much for your list! Very great work!

Oh and the Author from the demo hook is a user from reddit called "reminer" but he deleted his [thread](https://www.reddit.com/r/residentevil/comments/5kwaaj/release_a_tool_to_hack_re7_demo_resources/).
## Post #45
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-27T12:17:39+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Small list update > [Update 4](http://dropmefiles.com/xnHT4)

PS: Thanks to Haoose & Seyter.
## Post #46
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-01-27T18:36:32+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Small list update > Update 4

PS: Thanks to Haoose & Seyter.

so with the new hook we can load edited files similar to the demo hook? by putting the natives folder in the root?
## Post #47
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-27T22:15:46+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from iambosh
>
> 
so with the new hook we can load edited files similar to the demo hook? by putting the natives folder in the root?
I don't know, because i don't have game, but you can try.
## Post #48
- Username: 35234917DOTmp4
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-01-28T17:53:15+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Anyone found the font files pls ? I have try to extract all dds and i did but i was not able to identify the font file except this oft files in IU folder, but data from that files does not mean anything for me. Can anyone pls have a look, at least tell me what format is that? We figured out the new message format, it also mess and a complete a new structure..  Im working on the tool to mod the game but without possibility to do localization i will leave it, coz we need only loc the game at this moment. Only obstacle is damn stupid fonts.. I dont think that font is in tex file...

```
http://dropmefiles.com/l8VDN
```


Thx
## Post #49
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-01-28T22:00:01+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

I have played a bit and got over 330 MB Log packed into 14 MB Zip:
[http://www.mediafire.com/file/6d6ab658b ... E7Hook.zip](http://www.mediafire.com/file/6d6ab658bcie0bi/RE7Hook.zip)
I hope it helps, took a bit to upload, i have slow internet upload.

> Reply from michalss
>
> Anyone found the font files pls ? I have try to extract all dds 


Thx
Please tell me how you convert the tex to dds!

> Reply from iambosh
>
> Ekey wrote:Small list update > Update 4

PS: Thanks to Haoose & Seyter.

so with the new hook we can load edited files similar to the demo hook? by putting the natives folder in the root?

Sure: 
- Extract re_chunk_000.pak with ekeys great list (thanks ekey!) and rename it or move it
- Leave re_chunk_000.pak.patch_001.pak in the Resi folder
- Put the native folder into the re7 folder and then you can edit the files of the natives folder
Somehow some files are missing, thats why you need the patch_001 file i think, i extracted it + original pak and put it together, patch file last ofc but the game start with error messages and end in loop loading.
## Post #50
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-29T20:48:44+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

List update > [Update 5](http://dropmefiles.com/idDci)

PS: Thanks to Haoose
## Post #51
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-01-29T21:06:31+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> List update > Update 5
Thx! Current stats:
DLC 530590 - 22/36 filenames found
DLC 530592 - 8/36 filenames found
Patch - 2044/2549 filenames found
Main - 32342/40709 filenames found
Total - 79.4% filenames found
## Post #52
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-30T12:45:17+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Updated Hook for latest patch
[RE7Hook_0.02_r4.rar](https://xentaxbackup.github.io/file/12351_RE7Hook_0.02_r4.rar)
## Post #53
- Username: desperados
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 22, 2009 10:33 pm
- Post datetime: 2017-01-30T19:13:28+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Hi, thank you for all good tools.
I want to translate the game. Could someone please create a text editor?
Here I am sending files to text

[http://dropmefiles.com/ltbkt](http://dropmefiles.com/ltbkt)
## Post #54
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-01-30T19:24:21+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from desperados
>
> Hi, thank you for all good tools.
I want to translate the game. Could someone please create a text editor?
Here I am sending files to text

http://dropmefiles.com/mqGZO

I was working on tools, but i drop it coz i could not get fonts...
## Post #55
- Username: Griaule
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 31, 2017 3:29 am
- Post datetime: 2017-01-30T19:34:19+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Hello
Great work guys, keep up the good work!
Thanks to you all I have already managed to translate every subtitle and menu text in the game. The lore files will take a longer time thought. 
However, it seems that some of the extracted cutscenes doesn't have sound and some subtitle files are malfunctioning (showing japanese subtitles instead of english even before I touched the extracted files).
Can someone help me with this problem?
## Post #56
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-01-30T20:22:49+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> desperados wrote:Hi, thank you for all good tools.
I want to translate the game. Could someone please create a text editor?
Here I am sending files to text

http://dropmefiles.com/mqGZO

I was working on tools, but i drop it coz i could not get fonts...

I am waiting for tool
## Post #57
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-01-30T21:03:05+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Griaule
>
> Hello
Great work guys, keep up the good work!
Thanks to you all I have already managed to translate every subtitle and menu text in the game. The lore files will take a longer time thought. 
However, it seems that some of the extracted cutscenes doesn't have sound and some subtitle files are malfunctioning (showing japanese subtitles instead of english even before I touched the extracted files).
Can someone help me with this problem?

Manage to sort out the fonts ?
## Post #58
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-31T00:24:02+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

List updated. Added ~2000 names > [Update 7](http://dropmefiles.com/e7CTF)

PS: Thanks to balagoor, billyadelphia, dante3732, Haoose & Seyter.
## Post #59
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-01-31T00:39:47+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> List updated. Added ~2000 names > Update 7
Thx! Current stats:
DLC 530590 - 29/36 filenames found
DLC 530591 - 11/36 filenames found
DLC 530592 - 27/36 filenames found
Patch - 2117/2549 filenames found
Main - 33915/40709 filenames found
Total - 83.24% filenames found
## Post #60
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-31T12:17:24+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Small list update. Added ~400 names > [Update 8](http://dropmefiles.com/IKXDC)

PS: Thanks to Haoose & DimJones.
## Post #61
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-31T16:28:22+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

List is updated. Removed unused names and duplicates (only unique names). Added ~800 names > [Update 8](http://dropmefiles.com/DoXbh).
## Post #62
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-02-01T23:52:40+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> Anyone found the font files pls ? I have try to extract all dds and i did but i was not able to identify the font file except this oft files in IU folder, but data from that files does not mean anything for me. Can anyone pls have a look, at least tell me what format is that? We figured out the new message format, it also mess and a complete a new structure..  Im working on the tool to mod the game but without possibility to do localization i will leave it, coz we need only loc the game at this moment. Only obstacle is damn stupid fonts.. I dont think that font is in tex file...
Code: Select allhttp://dropmefiles.com/l8VDN

Thx
Fonts are encrypted (In Open Type Format). I wrote small tool for decrypt and encrypt it. Simpe usage:

```
RE7.Fonts.CryptTool <mScrFile> <mDstFile>
```


Note: If you want to view font > after decrypt you need open in hex editor output file and remove first 4 bytes (FBFO) + you need also change extension to .OTF. Example on fot-newcinemaastd-d.oft.1


[RE7.Fonts.CryptTool_0.1b.rar](https://xentaxbackup.github.io/file/12368_RE7.Fonts.CryptTool_0.1b.rar)
## Post #63
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-02-02T12:17:43+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> Anyone found the font files pls ? I have try to extract all dds and i did but i 


Thx

Why you ignoring my question?!
How did you extract the dds from a tex file?!
## Post #64
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-02-02T19:09:42+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> michalss wrote:Anyone found the font files pls ? I have try to extract all dds and i did but i was not able to identify the font file except this oft files in IU folder, but data from that files does not mean anything for me. Can anyone pls have a look, at least tell me what format is that? We figured out the new message format, it also mess and a complete a new structure..  Im working on the tool to mod the game but without possibility to do localization i will leave it, coz we need only loc the game at this moment. Only obstacle is damn stupid fonts.. I dont think that font is in tex file...
Code: Select allhttp://dropmefiles.com/l8VDN

Thx
Fonts are encrypted (In Open Type Format). I wrote small tool for decrypt and encrypt it. Simpe usage:
Code: Select allRE7.Fonts.CryptTool <mScrFile> <mDstFile>

Note: If you want to view font > after decrypt you need open in hex editor output file and remove first 4 bytes (FBFO) + you need also change extension to .OTF. Example on fot-newcinemaastd-d.oft.1

Thx a lot ekey, i had no idea  thx again You are rly good mate... Ekey can you please tell me how this files been encrypted ?
## Post #65
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-02-02T19:11:55+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from 35234917DOTmp4
>
> michalss wrote:Anyone found the font files pls ? I have try to extract all dds and i did but i 


Thx

Why you ignoring my question?!
How did you extract the dds from a tex file?!

simple answer coz i have not sort out the all headers and i dont rly need it anymore since good man ekey sort out the fonts . So will write archive repacker and text repacker i guess.. Not sure when but i guess i will
## Post #66
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-02-02T20:14:42+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> 
Thx a lot ekey, i had no idea  thx again You are rly good mate... Ekey can you please tell me how this files been encrypted ?
In fact is the simple xor, key must be generated from simple seed and file size.

PS: Has anyone figured out with unknown value(s) after dwFlag in Entries? I tried different variants hashing (32/64), like: Compressed Data, Uncompressed Data, Directory Path, File Extension, also check File Date & Time and etc, but no luck.
## Post #67
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-02-02T20:58:18+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> michalss wrote:
Thx a lot ekey, i had no idea  thx again You are rly good mate... Ekey can you please tell me how this files been encrypted ?
In fact is the simple xor, key must be generated from simple seed and file size.

PS: Has anyone figured out with unknown value(s) after dwFlag in Entries? I tried different variants hashing (32/64), like: Compressed Data, Uncompressed Data, Directory Path, File Extension, also check File Date & Time and etc, but no luck.

Looks like crc kind of, but im not sure about it. I just hope it does not affect the repacking.
## Post #68
- Username: tice17
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 04, 2015 1:20 am
- Post datetime: 2017-02-03T19:07:41+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

I have a localization project for this game, can somebody make interface based editing program for text files?  would realy appreciate it.

and for fonts and bms script, really thx ekey, you are da man
## Post #69
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-02-03T20:47:06+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> michalss wrote:Anyone found the font files pls ? I have try to extract all dds and i did but i was not able to identify the font file except this oft files in IU folder, but data from that files does not mean anything for me. Can anyone pls have a look, at least tell me what format is that? We figured out the new message format, it also mess and a complete a new structure..  Im working on the tool to mod the game but without possibility to do localization i will leave it, coz we need only loc the game at this moment. Only obstacle is damn stupid fonts.. I dont think that font is in tex file...
Code: Select allhttp://dropmefiles.com/l8VDN

Thx
Fonts are encrypted (In Open Type Format). I wrote small tool for decrypt and encrypt it. Simpe usage:
Code: Select allRE7.Fonts.CryptTool <mScrFile> <mDstFile>

Note: If you want to view font > after decrypt you need open in hex editor output file and remove first 4 bytes (FBFO) + you need also change extension to .OTF. Example on fot-newcinemaastd-d.oft.1

Is not a font file
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-02-04T01:54:45+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from MuratG
>
> Is not a font file
What? Output file in your screenshot is fot-newcinemaastd-d.oft.1.dec, you need change extension .oft.1.dec to .otf => fot-newcinemaastd-d.otf
## Post #71
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2017-02-04T04:04:42+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> MuratG wrote:Is not a font file

What? Output file in your screenshot is fot-newcinemaastd-d.oft.1.dec, you need change extension .oft.1.dec to .otf => fot-newcinemaastd-d.otf

Thanks
## Post #72
- Username: urao
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 29, 2016 9:14 pm
- Post datetime: 2017-02-05T15:09:39+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Thanks
## Post #73
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-02-07T19:30:21+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Small list update. Added ~400 names > Update 8

PS: Thanks to Haoose & DimJones.

Can you please reupload it ekey ? Thx
## Post #74
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-02-07T21:14:06+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

[Reuploaded](http://www104.zippyshare.com/v/F5bqr9TP/file.html)
## Post #75
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-02-12T10:29:42+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

No updates? 
Any idea how i can help finding all files?
## Post #76
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2017-02-12T13:44:12+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Which format used for in-game music?

I can see bnk and pack-archives... everything else?
## Post #77
- Username: 35234917DOTmp4
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 25, 2017 8:39 pm
- Post datetime: 2017-02-14T01:26:49+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Reuploaded
Thanks but can you tell me how extract all the other files? Can i help in any way?!
If i extract the files, i still need patch1..bla bla.pak so i can not edit all files, the files which are inside the pak.
Can you help me make the extractor while playing working?

> Reply from Ekey
>
> 35234917DOTmp4 wrote:
In current code is hooking two RVA addresses:
Code: Select allconst LPVOID addr_files_construct_ver1 = (LPVOID)0x000000000849784A;
const LPVOID addr_files_construct_ver2 = (LPVOID)0x000000000827648A;

How i can find these RVA addresses in the final game exe? these RVA addresses are from the demo.
The point is, to extract 1. all the other files while playing
2. extract the files which are needed to start the first time, so mods can be created.
## Post #78
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-02-21T21:53:32+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Here is updated base list. Added some filenames for Banned Footage Vol. 1 and Vol. 2  DLC's > [Update 10](http://www116.zippyshare.com/v/yD9mxE50/file.html)

> Reply from 35234917DOTmp4
>
> 
Thanks but can you tell me how extract all the other files? Can i help in any way?!
I said several times > you need make hook for hash algorithm.
## Post #79
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-21T17:01:18+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

I have unpacked the files of re7 and I want to find my font file and language editing file,

So what files should I look for??? And you have found out file yet?
## Post #80
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2017-05-17T16:46:00+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

anyone have text editor for this game?

@michalss 
are you still working on text editor?
any hope?
## Post #81
- Username: delroku
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 12, 2017 7:20 am
- Post datetime: 2017-11-12T21:53:01+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Hey, thank all of you guys for all these cool tools you make, really helps me find good models, and the thing is that i need 2 guns from the game, it's the Automag and the Samurai's Edge, i think i managed to extract the "re_chunk_000" and get the files with something like numeric extensions, i downloaded XLAra blender import/export blender addon trying to open the .mesh files (i renamed the ".mesh.32" to just ".mesh" (seemed pretty intuitive)) and tried to import them to blender however when i try to do so, an error pops up and that's pretty much it, i still can't figure out how to convert the ".tex.8" files either, am i doing this right? did i skipped anything?
thanks in advance.
## Post #82
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-12-13T10:07:28+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> Here is updated base list. Added some filenames for Banned Footage Vol. 1 and Vol. 2  DLC's > Update 10

may i ask if you're interested in updating the filename list to the latest dlc(s)? 
that'd be really nice of you.
## Post #83
- Username: desperados
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 22, 2009 10:33 pm
- Post datetime: 2017-12-24T11:38:56+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

please, update:  re7_pak_names.list  --- DLC - Not a Hero, End of Zoe
thanks
## Post #84
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2018-03-29T12:42:59+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from Ekey
>
> michalss wrote:Hi Ekey,

Can you please post the hash function for filenames ? Im writing repacker and i would like to know it..

Thx
Hash is Murmur 3.

All submitted logs is combined > Update 1 , Update 2

Hi Ekey, can you please post exact function in here ? I have try many Murmur3 implementation on interenet for C#, never found the correct uint hash with it .. Pls Help
## Post #85
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T13:52:34+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> Hi Ekey, can you please post exact function in here ? I have try many Murmur3 implementation on interenet for C#, never found the correct uint hash with it .. Pls Help
Are you sure that you use strings in Unicode?

[https://github.com/spotify/sparkey/blob ... murHash3.c](https://github.com/spotify/sparkey/blob/master/src/MurmurHash3.c)

C++

```
{
	unsigned int dwLength;
	unsigned int dwHash;

	dwLength = -1i64;
	do
		++dwLength;
	while (*(WORD *)(m_String + dwLength));
	return MurmurHash3_x86_32(m_String, dwLength * 2, -1);
}
```

[https://gist.github.com/automatonic/3725443](https://gist.github.com/automatonic/3725443)

C#

```
        {
            uint dwHash = 0;
            byte[] pBuffer = Encoding.Unicode.GetBytes(m_String);

            using (MemoryStream TMemoryStream = new MemoryStream(pBuffer))
            {
                dwHash = MurMurHash3.Hash(TMemoryStream);
            }
            return dwHash;
        }
```
## Post #86
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2018-03-30T20:07:51+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Anyone would be interested about Extractor and Patch Maker ? Even for PS4.. 

BTW: Thx ekey again, problem was a correct seen number i was not able to find, now all ok..
## Post #87
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2018-03-31T15:19:22+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> Anyone would be interested about Extractor and Patch Maker ? Even for PS4..

an updated filename-list would be really great.
## Post #88
- Username: ferex
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 04, 2015 6:06 am
- Post datetime: 2018-04-02T10:27:39+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> Anyone would be interested about Extractor and Patch Maker ? Even for PS4.. 

BTW: Thx ekey again, problem was a correct seen number i was not able to find, now all ok..
Hi michalls, could you give me unpack seen number for ps4?
## Post #89
- Username: yolartut
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2018-04-07T06:10:57+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

RELEASED TOOLS FOR RE7 (PC, PS4)

[viewtopic.php?f=32&t=17935](http://forum.xentax.com/viewtopic.php?f=32&t=17935)
## Post #90
- Username: ferex
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 04, 2015 6:06 am
- Post datetime: 2018-04-08T23:18:35+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

> Reply from michalss
>
> RELEASED TOOLS FOR RE7 (PC, PS4)

viewtopic.php?f=32&t=17935
Thank you so much michalls.İts very good.Its working.
## Post #91
- Username: DragonRuines4
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 24, 2019 3:28 pm
- Post datetime: 2020-07-28T12:53:11+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

{}
## Post #92
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2020-09-30T23:51:58+00:00
- Post Title: Re: Resident Evil 7 demo PAK file

Anyone figure out the .scn format? looks like its some kind of XML type script?


 itemresources.rar
(2.45 KiB) Downloaded 24 times
