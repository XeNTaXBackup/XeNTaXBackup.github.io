## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-02-29T14:14:26+00:00
- Post Title: Death Stranding (PS4)

Death Stranding (PS4) tool.

Usage is same as horizon zero dawn ([viewtopic.php?f=16&t=17726](https://forum.xentax.com/viewtopic.php?f=16&t=17726)), but it needs oo2core_7_win64.dll





animations are also extracted:


[ds.rar](https://xentaxbackup.github.io/file/18884_ds.rar)
## Post #2
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2020-03-03T03:22:56+00:00
- Post Title: Death Stranding (PS4)

Nice ! I can't wait ! : )
## Post #3
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2020-03-03T12:32:48+00:00
- Post Title: Death Stranding (PS4)

> Reply from zaykho ↑Tue Mar 03, 2020 11:22 am at Tue Mar 03, 2020 11:22 am
>
> 
Nice ! I can't wait ! : )

Yes
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-03T15:09:36+00:00
- Post Title: Death Stranding (PS4)

Tool posted. You can ask your friends about game files. As usual, I hope the game fans community will handle the task of files distributing.
## Post #5
- Username: G1fan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 23, 2018 3:03 pm
- Post datetime: 2020-03-03T22:01:16+00:00
- Post Title: Death Stranding (PS4)

Thanks for all the work daemon. If anyone wouldn't mind sharing the files with someone who's just looking to export some game assets, I'd really appreciate it. Cheers
## Post #6
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-04T00:19:58+00:00
- Post Title: Death Stranding (PS4)

A script for batch file extraction.
You will need the original daemon1's tool.
Edit the "INTERFACE" section:
Select the paths to the tool and files, select the steps (True - execute, False - skip).
Step 0 and 1 need to be performed once, then you can just turn them off
(step_0_create_res_file = False
step_1_unpack_bin = False)
resources are extracted to the tool_path
Models and textures will be converted ONLY from the work_dir folder (now configured for characters  )
In the process of step 3, the script creates skel_work folders - for skeletons and join_geo - for finished geometry combined with skeletons.
These models are referred to as __join __ (the name of the used skeleton ) and include all fragments from the parts folder.
You can also enable separate saving of each part of model (the create_join_parts parameter in the script) this will create __jp_ (part name) _ (skeleton name) files.

During the script operation,  may appear windows with error (crash Horizon) - this is normal. The script itself will close them.
During all the work of the programs, you will need the source *.bin files - never remove them.
Make sure that no extraneous .bin files get into the folder with source *.bin files - this can lead to errors.
Tested on python 3.7, but should work on older 3.x

Good luck.

UPDATE: 
add optional step_2_5_patch_ascii_names - chang name submesh in ascii to name_ascii_file__name_texture_set
[unpacker_ds_v6.7z](https://xentaxbackup.github.io/file/17898_unpacker_ds_v6.7z)
## Post #7
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-03-04T01:36:00+00:00
- Post Title: Death Stranding (PS4)

I'm gonna do a search myself as well, but if any kind soul wants to distribute the game model files so I can port some to another game engine I'd appreciate it!
## Post #8
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-03-04T01:48:54+00:00
- Post Title: Death Stranding (PS4)

I would like to look into the game files as well, If anyone can supply me with the game files I'd appreciate it!
## Post #9
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-03-04T05:33:13+00:00
- Post Title: Death Stranding (PS4)

Hi can anyone help me how to get game data i have a pkg game but i cant unpacked pkg
## Post #10
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-06T17:01:32+00:00
- Post Title: Death Stranding (PS4)

Well this is bloody fantastic news, but where do I get the game lol? It sure as heck isn't out yet on the web from what I've seen...
## Post #11
- Username: darkluap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2010 8:04 am
- Post datetime: 2020-03-07T01:47:15+00:00
- Post Title: Death Stranding (PS4)

As much as I search and search I didn't find the game anywhere. I will have to wait until it appears to play with the tool. It looks incredible
## Post #12
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-07T01:58:07+00:00
- Post Title: Death Stranding (PS4)

> Reply from darkluap ↑Sat Mar 07, 2020 9:47 am at Sat Mar 07, 2020 9:47 am
>
> 
As much as I search and search I didn't find the game anywhere. I will have to wait until it appears to play with the tool. It looks incredible

Yeah same, not sure how daemon pulled the models. I assume he/she used an actual ps4 to dump it or something I guess.
## Post #13
- Username: darkluap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2010 8:04 am
- Post datetime: 2020-03-07T17:49:42+00:00
- Post Title: Death Stranding (PS4)

OK I found the game but of course the passcode is necessary to be able to unpack it, I can't find a way to achieve it. I do not know what to do
## Post #14
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-07T19:29:48+00:00
- Post Title: Death Stranding (PS4)

Think you could PM me where you found the game? I still can't find it.
## Post #15
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-03-07T20:08:22+00:00
- Post Title: Death Stranding (PS4)

Could you share the files with me please I can't find it
## Post #16
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-07T22:47:54+00:00
- Post Title: Re: Death Stranding (PS4)

Seems pointless to even have the files as they need to be decrypted right now it seems and the usual passcode isn't working for it, so all bets are off for now.
## Post #17
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-03-07T22:53:51+00:00
- Post Title: Re: Death Stranding (PS4)

did you have the files for me I will do it
## Post #18
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-08T15:06:07+00:00
- Post Title: Re: Death Stranding (PS4)

The other guy darkluap does, ask him. Perhaps we can sort this out.
## Post #19
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-03-09T08:42:49+00:00
- Post Title: Re: Death Stranding (PS4)

it's the official game you need the fake pkg game otherwise it doesn't work we don't have the key I tried the keys don't work
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T11:48:28+00:00
- Post Title: Re: Death Stranding (PS4)

Tool updated:
- uv layers 3 & 4 support
- texture type 13 support
- bone rotations added to ascii
## Post #21
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-03-09T18:14:32+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ProGamer ↑Mon Mar 09, 2020 4:42 pm at Mon Mar 09, 2020 4:42 pm
>
> 
it's the official game you need the fake pkg game otherwise it doesn't work we don't have the key I tried the keys don't work

Well I'm pretty sure nobody has the fake pkg anywhere right now.
## Post #22
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-03-09T18:30:25+00:00
- Post Title: Re: Death Stranding (PS4)

No
## Post #23
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2020-03-19T12:35:18+00:00
- Post Title: Re: Death Stranding (PS4)

Model (fbx,obj) download please.Thx
## Post #24
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-05-06T08:09:10+00:00
- Post Title: Re: Death Stranding (PS4)

Any tips on merging these models' heads and bodies together?
Their heads are not quite fit their bodies. There's always a seam between them no matter how I place them
## Post #25
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-06T13:43:42+00:00
- Post Title: Re: Death Stranding (PS4)

Check user Crazy119 or something on deviantart, he's already posted most models from DS and fixed issues.
## Post #26
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-05-07T02:24:03+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Assasinge ↑Wed May 06, 2020 9:43 pm at Wed May 06, 2020 9:43 pm
>
> 
Check user Crazy119 or something on deviantart, he's already posted most models from DS and fixed issues.

He doesn't know how these models work either  .
I've asked him and downloaded his models. His models have the same problem as I said.
It's quite weird
## Post #27
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-07T17:10:27+00:00
- Post Title: Re: Death Stranding (PS4)

Then id-daemon probably didn't correct the script for ripping the models, I don't know.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-07T17:54:35+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Assasinge ↑Fri May 08, 2020 1:10 am at Fri May 08, 2020 1:10 am
>
> 
Then id-daemon probably didn't correct the script for ripping the models, I don't know.
the tool is correct, its not a script.
## Post #29
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-08T18:10:37+00:00
- Post Title: Re: Death Stranding (PS4)

My bad. Well, you could tell us what we're doing wrong if multiple people are reporting the same issue at least?...
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-08T19:31:21+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Assasinge ↑Sat May 09, 2020 2:10 am at Sat May 09, 2020 2:10 am
>
> 
My bad. Well, you could tell us what we're doing wrong if multiple people are reporting the same issue at least?...
i think this is how the models look. Probably engine problem.
I've never seen death stranding, but in Horizon it seems everybody is wearing necklaces to hide that. On a rare characters who dont, i remember you can see the seam in game.
## Post #31
- Username: vladgohn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 13, 2015 6:02 am
- Post datetime: 2020-05-21T22:26:44+00:00
- Post Title: Re: Death Stranding (PS4)

Hi, daemon!
I’ve been trying for days to solve the problem of exporting models from Death Stranding. but i'm a newbie.  

• Tell me please, for a successful implementation, I need a fake PKG?  
• Is there somewhere in the clouds (possibly yours) a given package suitable for decryption?  
• I found CUSA of the original version of DS, will this help me solve the problem?  
• Also I have both, PS4 + acquired digital copy of the game  

I ask for help, as soon as I can successfully complete this, I will make a video on YouTube to help others 
[https://imgur.com/16R0lJb](https://imgur.com/16R0lJb)
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-22T15:20:46+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from vladgohn ↑Fri May 22, 2020 6:26 am at Fri May 22, 2020 6:26 am
>
> 
• Tell me please, for a successful implementation, I need a fake PKG?no

> Reply from vladgohn ↑Fri May 22, 2020 6:26 am at Fri May 22, 2020 6:26 am
>
> 
• Is there somewhere in the clouds (possibly yours) a given package suitable for decryption?no

> Reply from vladgohn ↑Fri May 22, 2020 6:26 am at Fri May 22, 2020 6:26 am
>
> 
• I found CUSA of the original version of DS, will this help me solve the problem?no

> Reply from vladgohn ↑Fri May 22, 2020 6:26 am at Fri May 22, 2020 6:26 am
>
> 
• Also I have both, PS4 + acquired digital copy of the gamegood, but this will not help you
## Post #33
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-07-14T21:28:27+00:00
- Post Title: Re: Death Stranding (PS4)

Death Stranding is now released on steam. Will there be PC support in the future?
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-07-15T03:59:31+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from qs12 ↑Wed Jul 15, 2020 5:28 am at Wed Jul 15, 2020 5:28 am
>
> 
Death Stranding is now released on steam. Will there be PC support in the future?
PS4 tool can just work with PC. Files must be almost the same.
## Post #35
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-16T02:00:04+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1
>
> PS4 tool can just work with PC. Files must be almost the same.
Nah, it does not works (for me). There are 3 problems.

1)

```
File not found in cache! prefetch/fullgame.prefetch.core
```

Resolved by copying tool in game directory.

2)

```
   в System.IO.MemoryStream.InternalReadInt32()
   в ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
```


3)

```
Необработанное исключение: OutOfMemoryException.
```


Problem 2 and 3 - due to the fact tool protected by some obfuscator (Win10 Pro Lic detect it as Trojan:Win32/Occamy.C > Confuser ??), it is impossible to understand what the error is and why it occurs, because obfuscator protecting all classes, consts, strings and methods names cause it's a .Net project. I just was planning to add decryption code for Naomi's project for supporting encrypted files and wanted to compare some data files, but, apparently, not destiny 

I suppose that the master key (init hash) is different from the PC version, not sure because I do not know it from PS4 (if PS4 also encrypted as PC of cource).  

Can you tell me what is the identifier for bin files in PS4 version? 0x20304050 or 0x21304050?
## Post #36
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-16T04:00:47+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Wed Jul 15, 2020 11:59 am at Wed Jul 15, 2020 11:59 am
>
> 
qs12 wrote: ↑Wed Jul 15, 2020 5:28 am
Death Stranding is now released on steam. Will there be PC support in the future?

PS4 tool can just work with PC. Files must be almost the same.

It's a different format, the previously mapped out structures will not work.
PC Magic is 0x21304050, PS4 is likely 0x20304050, but it could also be that Death Stranding is using a newer iteration of the engine in general as opposed to the file format being a console-difference.
## Post #37
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2020-07-16T04:17:49+00:00
- Post Title: Re: Death Stranding (PS4)

Maybe start work with a movies container? It must have BINK files inside and the structure at the beginning and the end of the file seems just xored.
## Post #38
- Username: pkl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 27, 2020 5:31 am
- Post datetime: 2020-07-16T06:53:44+00:00
- Post Title: Re: Death Stranding (PS4)

This seems very nice but do you plan to make it work for the PC version?  It appears to crash on startup.
## Post #39
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-16T10:37:57+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from DEElekgolo
>
> It's a different format, the previously mapped out structures will not work.
PC Magic is 0x21304050, PS4 is likely 0x20304050, but it could also be that Death Stranding is using a newer iteration of the engine in general as opposed to the file format being a console-difference.

There is only one difference - an identifier that specifies that the archives are encrypted.

1) Header encrypted
2) Record table encrypted
3) Block table encrypted
4) Files data aslo encrypted
5) Structures have not changed

I have solved the problem with the decrypting of the header and tables. now i ve trying to decrypt content because algorithm is little bit different.

> Reply from pkl ↑Thu Jul 16, 2020 2:53 pm at Thu Jul 16, 2020 2:53 pm
>
> 
This seems very nice but do you plan to make it work for the PC version?  It appears to crash on startup.
Movies archive also encrypted
## Post #40
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-07-16T11:04:34+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Ekey ↑Thu Jul 16, 2020 10:00 am at Thu Jul 16, 2020 10:00 am
>
> I just was planning to add decryption code for Naomi's project for supporting encrypted files and wanted to compare some data files, but, apparently, not destiny

Someone found my HZD project it looks like   

> Reply from Ekey ↑Thu Jul 16, 2020 10:00 am at Thu Jul 16, 2020 10:00 am
>
> 
I suppose that the master key (init hash) is different from the PC version, not sure because I do not know it from PS4 (if PS4 also encrypted as PC of cource).  

Can you tell me what is the identifier for bin files in PS4 version? 0x20304050 or 0x21304050?

0x20304050 according to the files I have, PS4 version is also not encrypted.
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-16T12:43:17+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Yretenai
>
> Someone found my HZD project it looks like

Ah, you here  This is an interesting project 

I'll give information on encryption later.
## Post #42
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-16T16:32:53+00:00
- Post Title: Re: Death Stranding (PS4)

Here is my test tool for decrypting and dump the header and tables (source's included). 
Not a professional code, but I think it's okay 

PS: There is no code to decrypt files yet.
[Decima.Decryptor.Test-src-bin.rar](https://xentaxbackup.github.io/file/18481_Decima.Decryptor.Test-src-bin.rar)
## Post #43
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-16T16:35:36+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Ekey ↑Fri Jul 17, 2020 12:32 am at Fri Jul 17, 2020 12:32 am
>
> 
Here is my test tool for decrypting and dump the header and tables (source's included). 
Not a professional code, but I think it's okay 

PS: There is no code to decrypt files yet.

Lookin good 

I got some C++ code up here too
[https://github.com/Wunkolo/DecimaTools](https://github.com/Wunkolo/DecimaTools)

```
Version:                 6DD02CEF
FileSize:                 2004617
DataSize:                 2131705
FileTableCount:                 4
ChunkTableCount:                9
MaxChunkSize:              262144
        ---------------------------------------
        EntryID:                      797099076
        Unknown04:                   1833628696
        Unknown08:             3F821535414ED8FD
        Offset:                               0
        Size:                           1354751
        Unknown1C:                     7496F6C2
        ---------------------------------------
        EntryID:                     4172398392
        Unknown04:                   2136868349
        Unknown08:             D3D19A0EB596F903
        Offset:                         1354751
        Size:                            145618
        Unknown1C:                     3D7F6668
        ---------------------------------------
        EntryID:                     3114963283
        Unknown04:                   4088237356
        Unknown08:             3E20BD7DB9BE7960
        Offset:                         1532501
        Size:                            599204
        Unknown1C:                     58D97D4F
        ---------------------------------------
        EntryID:                     1447133094
        Unknown04:                   3705277707
        Unknown08:             130EA489D652BD55
        Offset:                         1500369
        Size:                             32132
        Unknown1C:                     00176D49
        ---------------------------------------------
        OffsetUncompressed:                          
        SizeUncompresed:                       262144
        Unknown0C:                           030DFD13
        OffsetCompressed:                         456
        SizeCompressed:                        213931
        Unknown1C:                           5859112B
        ---------------------------------------------
        OffsetUncompressed:                    262144
        SizeUncompresed:                       262144
        Unknown0C:                           AE3F6A60
        OffsetCompressed:                      214387
        SizeCompressed:                        258608
        Unknown1C:                           DF45ABE1
        ---------------------------------------------
        OffsetUncompressed:                    524288
        SizeUncompresed:                       262144
        Unknown0C:                           D9A5F8E8
        OffsetCompressed:                      472995
        SizeCompressed:                        259270
        Unknown1C:                           9D9AC56C
        ---------------------------------------------
        OffsetUncompressed:                    786432
        SizeUncompresed:                       262144
        Unknown0C:                           CCE42AAC
        OffsetCompressed:                      732265
        SizeCompressed:                        258467
        Unknown1C:                           9015E633
        ---------------------------------------------
        OffsetUncompressed:                   1048576
        SizeUncompresed:                       262144
        Unknown0C:                           E52D54EF
        OffsetCompressed:                      990732
        SizeCompressed:                        254252
        Unknown1C:                           8A3465A0
        ---------------------------------------------
        OffsetUncompressed:                   1310720
        SizeUncompresed:                       262144
        Unknown0C:                           FE5724A2
        OffsetCompressed:                     1244984
        SizeCompressed:                        213497
        Unknown1C:                           EFFCE6F5
        ---------------------------------------------
        OffsetUncompressed:                   1572864
        SizeUncompresed:                       262144
        Unknown0C:                           DBCB4E32
        OffsetCompressed:                     1458481
        SizeCompressed:                        257844
        Unknown1C:                           D961FE10
        ---------------------------------------------
        OffsetUncompressed:                   1835008
        SizeUncompresed:                       262144
        Unknown0C:                           A7CD7DB2
        OffsetCompressed:                     1716325
        SizeCompressed:                        254539
        Unknown1C:                           DF590A89
        ---------------------------------------------
        OffsetUncompressed:                   2097152
        SizeUncompresed:                        34553
        Unknown0C:                           A5DAA534
        OffsetCompressed:                     1970864
        SizeCompressed:                         33753
        Unknown1C:                           5D58BE0F

```
## Post #44
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-16T16:42:45+00:00
- Post Title: Re: Death Stranding (PS4)

Great job! Do you looked code for decrypt files data? Seems MD5 is involved in decryption and there other key (salt) are used 

```
       0x6C084A37, 0x7E159D95, 0x3D5AF7E8, 0x18AA7D3F};
```


or

```
       0x37, 0x4A, 0x08, 0x6C, 0x95, 0x9D, 0x15, 0x7E,
       0xE8, 0xF7, 0x5A, 0x3D, 0x3F, 0x7D, 0xAA, 0x18};
```


As you wish
## Post #45
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-07-16T21:11:56+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from DEElekgolo ↑Fri Jul 17, 2020 12:35 am at Fri Jul 17, 2020 12:35 am
>
> 
Ekey wrote: ↑Fri Jul 17, 2020 12:32 am
Here is my test tool for decrypting and dump the header and tables (source's included). 
Not a professional code, but I think it's okay 

PS: There is no code to decrypt files yet.


Lookin good 

I got some C++ code up here too
https://github.com/Wunkolo/DecimaTools

Mind slapping a license on that project? I'm planning on rewriting ProjectZeroDawn to C++ when the PC port releases and I'd love to have a C++ point of reference.
## Post #46
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-17T00:02:40+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Yretenai ↑Fri Jul 17, 2020 5:11 am at Fri Jul 17, 2020 5:11 am
>
> 
DEElekgolo wrote: ↑Fri Jul 17, 2020 12:35 am

Lookin good 

I got some C++ code up here too
https://github.com/Wunkolo/DecimaTools


Mind slapping a license on that project? I'm planning on rewriting ProjectZeroDawn to C++ when the PC port releases and I'd love to have a C++ point of reference.

Sure! It's just MIT

> Reply from Ekey ↑Fri Jul 17, 2020 12:42 am at Fri Jul 17, 2020 12:42 am
>
> 
Great job! Do you looked code for decrypt files data? Seems MD5 is involved in decryption and there other key (salt) are used 
Code: Select allstatic unsigned long lpSalt2[4] = {
       0x6C084A37, 0x7E159D95, 0x3D5AF7E8, 0x18AA7D3F};

or
Code: Select allstatic unsigned char lpSalt2[16] = {
       0x37, 0x4A, 0x08, 0x6C, 0x95, 0x9D, 0x15, 0x7E,
       0xE8, 0xF7, 0x5A, 0x3D, 0x3F, 0x7D, 0xAA, 0x18};

As you wish

Still digging in slowly! Haven't been able to take this on full-time but I'm still digging in with the intent of possibly re-encrypting and re-packaging these files at some point.
## Post #47
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-17T11:52:10+00:00
- Post Title: Re: Death Stranding (PS4)

The files are approximately decrypting as follows:

1) For each chunk you need to get first 16 bytes of block table



```
byte[] lpBlockTableData = Copy here blablabla
```


PS: Screen from block table of file 7017f9bb9d52fc1c4433599203cc51b1.bin

2) Now we need to get murmur3 hash from this

```
var lpMur3Hash = MurMur3_GetHash(lpBlockTableData, 16);
```


3) Necessary to mix hash with second key (salt): 

```
{
    lpMixedKey[i] = lpMur3Hash[i] ^= lpSalt2[i];
}
```


4) Now we need to get MD5 hash of MurMur3 hash

```
var lpMD5Hash = MD5_GetHash(lpMur3Hash);
```


5) Decrypting data by provided by MD5 hash (probably lpMixedKey using at the end, until I figured it out -> if dwSomeDataSize....)

```
Int32 dwSomeDataSize = dwChunkSize & 0xF;

if (dwEncryptedSize)
{
    for (Int32 i = 0; i < dwEncryptedSize; i++)
    {
        lpBuffer[i] ^= lpMD5Hash[i % 16];
    }
}

if ( dwSomeDataSize )
{
    __asm { vpxor   xmm0, xmm0, xmm0 }
    Var38 = 7;
    Var39 = (unsigned int)dwSomeDataSize;
    do
    {
	_RDX = 1i64 << (Var38 & 0x3F);
	if ( Var38 & 0x40 )
        _RDX = 0i64;
	Var38 += 8;
	__asm
	{
		vmovq   xmm1, rdx
		vpinsrq xmm1, xmm1, rcx, 1
		vpor    xmm0, xmm1, xmm0
	}
	--Var39;
    }
    while ( Var39 );
    _R10 = 2 * dwChunkSize;
    __asm
    {
	//lpMixedKey???
	vmovdqu xmm2, xmmword ptr [rsi+r10*8]
	vpxor   xmm1, xmm3, xmm2
	vpblendvb xmm1, xmm2, xmm1, xmm0
	vmovdqu xmmword ptr [rsi+r10*8], xmm1
    }
}
```


```
goto 1);
```


The information is not yet complete but it is the basis of encryption, maybe I missed something else, anyway, I’ll supplement it later
## Post #48
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-17T18:14:26+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Ekey ↑Fri Jul 17, 2020 7:52 pm at Fri Jul 17, 2020 7:52 pm
>
> 
5) Decrypting data by provided by MD5 hash (probably lpMixedKey using at the end, until I figured it out -> if dwSomeDataSize....)
Code: Select allInt32 dwEncryptedSize = dwChunkSize >> 4;
Int32 dwSomeDataSize = dwChunkSize & 0xF;

if (dwEncryptedSize)
{
    for (Int32 j = 0; j < dwEncryptedSize; i++)
    {
        lpBuffer[i] ^= lpMD5Hash[i % 16];
    }
}

if ( dwSomeDataSize )
{
    __asm { vpxor   xmm0, xmm0, xmm0 }
    Var38 = 7;
    Var39 = (unsigned int)dwSomeDataSize;
    do
    {
	_RDX = 1i64 << (Var38 & 0x3F);
	if ( Var38 & 0x40 )
        _RDX = 0i64;
	Var38 += 8;
	__asm
	{
		vmovq   xmm1, rdx
		vpinsrq xmm1, xmm1, rcx, 1
		vpor    xmm0, xmm1, xmm0
	}
	--Var39;
    }
    while ( Var39 );
    _R10 = 2 * dwChunkSize;
    __asm
    {
	//lpMixedKey???
	vmovdqu xmm2, xmmword ptr [rsi+r10*8]
	vpxor   xmm1, xmm3, xmm2
	vpblendvb xmm1, xmm2, xmm1, xmm0
	vmovdqu xmmword ptr [rsi+r10*8], xmm1
    }
}

`dwSomeDataSize` looks like it's just handling unaligned data while `dwEncryptedSize` is handling aligned data(groups of 16).
That `vpblendvb`looks like it's doing some byte-level blending between the xor-ed unaligned data and the salted hash before writing it out to the chunk(Picks bytes between registers depending using another byte, the equivalent of a byte-level conditional write, c = x&0x80 ? a:b). That `vpinsrq` loop looks like it's just pushing a bit value(x = 0b111ul <<  i%64) on the lower 64 bits of the 128 bit register and a rcx into the upper 64 bits before doing a `^=` and then blending it later. Not sure what rcx is in this case.

Got an exe offset or signature or something for this function so I can take a look?
## Post #49
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-17T20:27:44+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from DEElekgolo
>
> `dwSomeDataSize` looks like it's just handling unaligned data while `dwEncryptedSize` is handling aligned data(groups of 16).
That `vpblendvb`looks like it's doing some byte-level blending between the xor-ed unaligned data and the salted hash before writing it out to the chunk(Picks bytes between registers depending using another byte, the equivalent of a byte-level conditional write, c = x&0x80 ? a:b). That `vpinsrq` loop looks like it's just pushing a single-bit value(x = 0b111ul <<  i%64) on the lower 64 bits of the 128 bit register and a rcx into the upper 64 bits before doing a `^=` and then blending it later. Not sure what rcx is in this case.
rcx is always zero

> Reply from DEElekgolo
>
> Got an exe offset or signature or something for this function so I can take a look?

Yeah sure, for current patch 1.01 address is 00000001416D1C90.
## Post #50
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-18T20:48:37+00:00
- Post Title: Re: Death Stranding (PS4)

Still digging in. That routine is a bit of a tangle and the IDA decompiler is missing out on entire registers since it cant make sense of some of the higher-level intents of the SSE and AVX simd. RCX isnt always zero but rather RDX and RCX are ultimately going to become the upper and lower halfs of xmm1 and are generated differently based on some conditional moves.

It looks like that routine just generates the mask register(setting the upper 7th bit in each byte), Loads in the 16 bytes of cipher-text(likely padded with 00s), xors it with the hash like before, and then uses the mask register for byte-blending between the previously xor-ed value, and the mask register again before writing it back to plain-text. My SIMD/HPC programming experience is paying off   



Rather than recreate this mask-generation code though, xmm0 can be made entirely ahead of time. This code is only run on unaligned data and so all 15 possible mask registers can be made like this.

```

CurShift = 7
Mask128 = 0
for x in range(16):
    Mask = c_uint64(1 << (CurShift % 64)).value
    MaskLo = Mask
    MaskHi = 0
    if CurShift & 0b01000000: MaskLo, MaskHi = MaskHi, MaskLo
    CurShift += 8
    Mask128 |= (MaskHi << 64 | MaskLo)
    print(format(x,'3') + ": " + format(Mask128, '0128b'))

```

And these values can be 

```
  1: 00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001000000010000000
  2: 00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000100000001000000010000000
  3: 00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010000000100000001000000010000000
  4: 00000000000000000000000000000000000000000000000000000000000000000000000000000000000000001000000010000000100000001000000010000000
  5: 00000000000000000000000000000000000000000000000000000000000000000000000000000000100000001000000010000000100000001000000010000000
  6: 00000000000000000000000000000000000000000000000000000000000000000000000010000000100000001000000010000000100000001000000010000000
  7: 00000000000000000000000000000000000000000000000000000000000000001000000010000000100000001000000010000000100000001000000010000000
  8: 00000000000000000000000000000000000000000000000000000000100000001000000010000000100000001000000010000000100000001000000010000000
  9: 00000000000000000000000000000000000000000000000010000000100000001000000010000000100000001000000010000000100000001000000010000000
 10: 00000000000000000000000000000000000000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000
 11: 00000000000000000000000000000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000
 12: 00000000000000000000000010000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000
 13: 00000000000000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000
 14: 00000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000
 15: 10000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000100000001000000010000000

```


When you collapse this logic though, it seems like the un-aligned xors are quite literally just doing partial xors(n-bytes of unaligned data is just the first n-bytes of the mixed-hash being xored against it) and then using the byte-blending to preserve whatever un-aligned data is within that 16-byte window. You can pretty safely assume that it is just a full xor for aligned and unaligned data.

I don't have my code base up to the point to where it even has to decrypt these chunks to verify a working implementation. And I won't be able to look at this full-time but I can give it an afternoon every now and then and share notes while I update my code base
## Post #51
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-07-19T23:05:54+00:00
- Post Title: Re: Death Stranding (PS4)

Thanks for the work you two have been doing on decryption, and for keeping things open as well. I've updated an old repo I had based on your findings. I didn't implement that new information about unaligned data, but some things seem to be decrypting correctly. file 0 of 7017f9bb9d52fc1c4433599203cc51b1 looks to be the prefetch file.

source code and files at [https://github.com/Jayveer/Decima-Explo ... es/tag/1.5](https://github.com/Jayveer/Decima-Explorer/releases/tag/1.5) if anyone wants to try it.
## Post #52
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-07-20T10:57:42+00:00
- Post Title: Re: Death Stranding (PS4)

@JayK - Good job! Here is a list of archives with a description, if anyone is interested 

```
6fb69851f3279ea051f48ee6c98c73fe.bin - Area00_English
225bb34815aa3e89f155ba2515570cb2.bin - Area00_French
e72aac57de9918c67eaf3d5102c8acb8.bin - Area00_Spanish
84e35fcf5de2ba16cc1ee893ba4dc56c.bin - Area00_German
6fcdd0390579931aa1c93da879e28d82.bin - Area00_Italian
553cfe4d8b9fe4769e534e703bfb9732.bin - Area00_Portuguese
2709afee4cac7fc87a04bd2b6c1c5882.bin - Area00_Russian
f573fbfdff7eb1fa271f382e24503f82.bin - Area00_Polish
f3a2ab17a7c17470623d3e842224841f.bin - Area00_Japanese
4411fbe7b81d872e8517abf67e932280.bin - Area00_LATAMSP
6cafab4876800a73ab36290c76730f68.bin - Area00_LATAMPOR
8761c9be94b95d7197c850a230bb05aa.bin - Area00_Greek
1a472f28ea1537dd3cb911fd1e18f2af.bin - Area01_English
f77b66dc12e3085afdf2ccee9e3bddb8.bin - Area01_French
55a0f2ad6fd854eb46eda325ebd3fdfe.bin - Area01_Spanish
88c5cf29d347a6f0007199554279573e.bin - Area01_German
a53083d2a39c921b2fbfc520216f17d7.bin - Area01_Italian
4c7518f562e8cfc65349f261cb4a4935.bin - Area01_Portuguese
4e5bed8e41d7417c889b2284f33c35f0.bin - Area01_Russian
110d9add046eec4d23810f2fa9565924.bin - Area01_Polish
eb8cd08d682978a9b9112d7c8f54de21.bin - Area01_Japanese
f7b4c4ff1b831d3adf6fa1952a978767.bin - Area01_LATAMSP
c172307816383537bd4703897044f6c5.bin - Area01_LATAMPOR
f26fd3ec3d943dd6aaff93a45a8025c2.bin - Area01_Greek
c0306eef15c4b5122ab61a834f80d743.bin - Area02
9abda4bd99f4fa01951fd153775e7e8d.bin - Area02_English
69e57bab4b0e47d007bab3b3fcca6dc5.bin - Area02_French
e8b2c1ef002e12ddfb73977afa1955a7.bin - Area02_Spanish
b11ab76d7450f70cd80f46037963e22f.bin - Area02_German
47a882f8b80bfb6954d92201251744bf.bin - Area02_Italian
7eb2acb7d14889097248e156637e95a1.bin - Area02_Portuguese
0404fe2210c6609046c1c08bf2ea7c8a.bin - Area02_Russian
cb4196d63aaed195c987dfb47bbfadf5.bin - Area02_Polish
2c8aaa03cef19c1d7d4d14f8b29c7197.bin - Area02_Japanese
dae3bdff0b5583a91ff40d98d3bf73a3.bin - Area02_LATAMSP
13cf568657bcfb893b6b97b5e81f4ae3.bin - Area02_LATAMPOR
e084898e7d0371f8cd9688cd303841f5.bin - Area02_Greek
dc847b243b638c5ce539d4be7ff48007.bin - Area04
8d60c6e8d6ce70496107e588205a3054.bin - Area04_English
f0f467ec1b144337ef804ab0dc1a633e.bin - Area04_French
20dec5c29481cc1d3e21dec2b289e8e9.bin - Area04_Spanish
a64d5675363bcfae85f36b39faafba5d.bin - Area04_German
0a5d8e4999a0dc48da7b66c8b8251c42.bin - Area04_Italian
adc5401f627e7d6b1e23afe75e06fe4c.bin - Area04_Portuguese
0a58238b82416a35c9e3dc3b3a6e825c.bin - Area04_Russian
3430babbf55916a937a8757da75199c7.bin - Area04_Polish
237d41a6888266372a7c9100526dfeb9.bin - Area04_Japanese
7ff527fda0571c79839bb8aa9c3db648.bin - Area04_LATAMSP
ea97cfbec2be98a216a6450faf9710b0.bin - Area04_LATAMPOR
a610c95e0690047924d1afbb824d0250.bin - Area04_Greek
477e458b2c825633499874678a2b9ea5.bin - Beach01
f70387b309fdda4e66a9d1808815252d.bin - Beach01_English
c4c4d7253d00afff7e7859822e967f05.bin - Beach01_French
0a7a707a3e247348d81931fa45ad28b3.bin - Beach01_Spanish
f829e168029598d8ceea4f4d01e54378.bin - Beach01_German
8a290e232dd8d4c727cf2da3fadd5c5b.bin - Beach01_Italian
1c3b38583613deb87f5b4e9ff1dd94c4.bin - Beach01_Portuguese
f7f21580058bd1b925180851f3969070.bin - Beach01_Russian
4d8d31832be4055295b9e619cf315740.bin - Beach01_Polish
c28838ba40cb2165ee8dd703a8cdb0e3.bin - Beach01_Japanese
c2dc1b0259864bcf814b4cd81cd917d4.bin - Beach01_LATAMSP
dc915927c83cb738ae87857742e4c774.bin - Beach01_LATAMPOR
10b8dcebcce8280dac2f30f0a57cba2a.bin - Beach01_Greek
7017f9bb9d52fc1c4433599203cc51b1.bin - Initial
a694c2e00b87cd761ee2a25b09a49ea7.bin - Initial_English
a5dcec9b54e1586b097e5c49a07429c5.bin - Initial_French
a1cc3eee3d405a5613916e1297641289.bin - Initial_Spanish
3cd22bf810430d77b7fff991a4b81551.bin - Initial_German
dbef71d6d372f7c6bdaf3717c119b519.bin - Initial_Italian
c920bcebb78902bf6ac6c447eab9fb41.bin - Initial_Portuguese
d8f0b887a3642eca5ada40e8cdff07db.bin - Initial_Russian
54d23a724866aa2d6025ebb2a688c968.bin - Initial_Polish
4bb8707b549628feb844fbf8d0c85327.bin - Initial_Japanese
cf44457b965b72abb6ee66bdddd60b3a.bin - Initial_LATAMSP
94d6a62c9fb7a869754f0d6bc19f81e7.bin - Initial_LATAMPOR
8ebc24104a70f5f1b13eb04d175614b2.bin - Initial_Greek
59b95a781c9170b0d13773766e27ad90.bin - Patch
3460515fd6d930b689143a8b9a51a060.bin - Remainder
17881513a7e2a728ccd2ae7301dc9054.bin - Remainder_English
d9ae8d6654a7ceca64c8dc18952d3209.bin - Remainder_French
e33dd8b96035b2f7e547aed5fbfdf8e5.bin - Remainder_Spanish
a6b263ffdda8aca7fb8decba961b8097.bin - Remainder_German
e8276e34701d2a6664c9a29d20062f9c.bin - Remainder_Italian
9eb0941601e90d4b6c81d62b48959786.bin - Remainder_Portuguese
fa24bd744dbf75e81308c45581f49817.bin - Remainder_Russian
be25f0823739852892e4b6179818e715.bin - Remainder_Polish
17fa480245a3a67a1e5ecc246cee719d.bin - Remainder_Japanese
b52dacb981213ed55cb3be42bea80258.bin - Remainder_LATAMSP
dbcebbf108d0da62acee516ab446ccd0.bin - Remainder_LATAMPOR
fee239d94dfcb9a257cd4d15fe0a7d21.bin - Remainder_Greek
968bf82f34e2b499687c901a888e633a.bin - Warrior01
4707c0dea95bdf7b38ed0d838965e0e6.bin - Warrior01_English
b70fa685f46ec3f4b8a19b53f666b69f.bin - Warrior01_French
fb4e818aa0dc2f8f791fe518a8910337.bin - Warrior01_Spanish
3523588f0825ad5f54013b6031361d3b.bin - Warrior01_German
26d92e4a0d5e060ba1879de2d02f5fc2.bin - Warrior01_Italian
b20229b7199ba8c81854d513f764e2c9.bin - Warrior01_Portuguese
fb5160bf0cda8b0bca124d04d51de62c.bin - Warrior01_Russian
68d7fcb76bb55037ebbffbd01bcb2b08.bin - Warrior01_Polish
c9d841287e962d3d54123652828ebd00.bin - Warrior01_Japanese
44108381064a698eb7376aee4bc1478d.bin - Warrior01_LATAMSP
d0218c32efbff643a19603a31efcc3c2.bin - Warrior01_LATAMPOR
8d73fa4af178fe81ae95d0cb8c7fc606.bin - Warrior01_Greek
fcd4b5918cea9a220c0da171bb60c214.bin - Warrior02
7ccfce87d9887adf1689fbd07df4200a.bin - Warrior02_English
46485581ea66e58e27b5040b40257bce.bin - Warrior02_French
80022ad18cf34441da2e8e8557d524df.bin - Warrior02_Spanish
aa828c35c790d250cdc765ab9b8e6050.bin - Warrior02_German
6a562dc4e089db4b922573066a7ec884.bin - Warrior02_Italian
2b4203d8d2cf539bada40ff7fbe734fc.bin - Warrior02_Portuguese
cd336bf6b36bab5527c3b3609093abe7.bin - Warrior02_Russian
e9ea778cf34ee584e523e958bfcf8f81.bin - Warrior02_Polish
50023cc2d26d8242720e71676ceac967.bin - Warrior02_Japanese
9392f016b4dba2cfec41607e0a9e2250.bin - Warrior02_LATAMSP
da0346efdd0d2b8eb3c067c93ffdbf33.bin - Warrior02_LATAMPOR
343d88e2515bfd702fd34962f63c1d45.bin - Warrior02_Greek
a53f66da5938a089f06b8a0c07c97f18.bin - Warrior03
93a37de4096fad67e0c99100775cce42.bin - Warrior03_English
064bff9f859fb5a0bd74f0a486e133ab.bin - Warrior03_French
32c38c240a31c6452f47836177ee46b9.bin - Warrior03_Spanish
3c040baec191e5117685af0bf4e2c312.bin - Warrior03_German
9652986d6bacd063df6cbb252ef828ee.bin - Warrior03_Italian
9ac69cf07935e12ebc4a10a5a846d5cf.bin - Warrior03_Portuguese
1bb90bd3941536ce94002ae82a953f6b.bin - Warrior03_Russian
54106a2ec29dfb15584b5c104c05b219.bin - Warrior03_Polish
b0720c4389202911af7e64531d973a00.bin - Warrior03_Japanese
49a78b888f6a86fbb68a50b115ee77c4.bin - Warrior03_LATAMSP
138969409f16e44df28d7fbcb87a5909.bin - Warrior03_LATAMPOR
819f5249d44b19c7e4bff600b89a1a32.bin - Warrior03_Greek
```


Yup, 7017f9bb9d52fc1c4433599203cc51b1.bin is a initial archive which, contains of all entry list (with id 0) and apparently for this it is always loaded first. I did not find a list in other files
## Post #53
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-07-22T18:33:55+00:00
- Post Title: Re: Death Stranding (PS4)

Looking into it more, it looks as if that other decryption path is hit once it starts reading above 0x80000000 (for example once the compressed offset is above that)
EDIT: Nevermind, false alarm. Was just an fseek problem.
## Post #54
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-07-24T11:18:23+00:00
- Post Title: Re: Death Stranding (PS4)

Something interesting is to see PC and PS4 versions of 3D models or textures files are not the same.
Here is a sample:
[https://cdn.discordapp.com/attachments/ ... weapon.zip](https://cdn.discordapp.com/attachments/614355643830239242/736180014407483422/weapon.zip)
## Post #55
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2020-07-26T00:14:43+00:00
- Post Title: Re: Death Stranding (PS4)

Any progress on exctracting videos from movies.mpk file?
## Post #56
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-07-26T02:24:02+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Espio ↑Sun Jul 26, 2020 8:14 am at Sun Jul 26, 2020 8:14 am
>
> 
Any progress on exctracting videos from movies.mpk file?

The decryption used on the mpk files is the same for the header and info, the salt is different this time { 0x833237C3, 0xBA5CD4B6, 0x3371A06B, 0xAEA7EDB2 }; 0x04 of header is the 4 bytes which replace the first 4 bytes of the salt this time round with 1 pass for decryption. 0x08, 0x0C are both used to replace the first 4 bytes of the salt for each pass respectively. Haven't found the subroutine for where the decryption of the rest of the data is done yet.

Edit: Ok, quite close to figuring out the movie decryption, it's mostly similar to the main file decryption, the differences being that there is an xmm blend this time before the xor salt, which blends against a value from EBP. It was 0 in the example I was debugging the first time it hit the function, 2 the second, 1 the third.So I'l have to see what it actually resolves to to say this is figured out completely (at a guess it could be the current iteration). The xor salt this time is { 0xCE857276, 0x9ACC40E8, 0x8242DBD6, 0xCF703987 } after the md5 hash it xor's a fixed number of times (0x10000 as it's 0x10 bytes a time thats 0x100000 bytes). Not sure how it handles alignment considering this loop is rigid, may just pad bytes up to that in the last few passes. I'd probably have to step out of this function a bit to resolve the last few unknowns, I'll add it to my source once it's done.

Edit2: EBP did turn out to be the current iteration of the function so that it is what gets blended with the result of the murmurhash func, the rest is pretty much the same and thats all their is to the movie decryption. I've added an implementation of it to the tool I posted above.
## Post #57
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-07-27T15:06:04+00:00
- Post Title: Re: Death Stranding (PS4)

Edit2: EBP did turn out to be the current iteration of the function so that is what gets blended with the result of the murmurhash func, the rest is pretty much the same and that's all there is to the movie decryption. I've added an implementation of it to the tool I posted above.
## Post #58
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2020-07-27T23:35:39+00:00
- Post Title: Re: Death Stranding (PS4)

Thanks for info and research. Could you please upload binary with movie extraction support? If not on GH, then here. Thanks in advance!
## Post #59
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-07-28T08:46:17+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Espio ↑Tue Jul 28, 2020 7:35 am at Tue Jul 28, 2020 7:35 am
>
> 
Thanks for info and research. Could you please upload binary with movie extraction support? If not on GH, then here. Thanks in advance!

I already linked it a few posts above,  but here it is again
[https://github.com/Jayveer/Decima-Explo ... es/tag/1.5](https://github.com/Jayveer/Decima-Explorer/releases/tag/1.5)
## Post #60
- Username: Azetlor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 04, 2020 2:25 am
- Post datetime: 2020-08-03T18:42:57+00:00
- Post Title: Re: Death Stranding (PS4)

Is it possible to extract the game's music using this tool? Does anyone know where the music is located?
## Post #61
- Username: healyv
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 15, 2016 10:57 am
- Post datetime: 2020-08-07T17:48:56+00:00
- Post Title: Re: Death Stranding (PS4)

When using daemon1's ds.exe, it fails with an 
```
Unhandled Exception: OutOfMemoryException.
```
 I've got plenty of RAM to spare, so I'm not sure what's up with that. This occurs when running the executable bare with no arguments, with args, and when dropping an extracted .core file onto it to convert (with either PS4 or PC version assets). Has anyone else run into this issue?
## Post #62
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-08-08T07:08:25+00:00
- Post Title: Re: Death Stranding (PS4)

If you compare PS4 and PC files you'll see they are not the same so if the structure is different, the tool will not work.
## Post #63
- Username: Azetlor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 04, 2020 2:25 am
- Post datetime: 2020-08-12T15:14:14+00:00
- Post Title: Re: Death Stranding (PS4)

I look forward to a PC unpacker. Will it be in a seperate thread?
## Post #64
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-12T20:36:26+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Azetlor ↑Wed Aug 12, 2020 11:14 pm at Wed Aug 12, 2020 11:14 pm
>
> 
I look forward to a PC unpacker. Will it be in a seperate thread?

That would be a good idea but I suggest to merge this forum with PC, Here's the Unpacker [https://github.com/Jayveer/Decima-Explorer](https://github.com/Jayveer/Decima-Explorer) it also works for Horizon Zero Dawn.
## Post #65
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-08-15T02:53:51+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from qs12 ↑Thu Aug 13, 2020 4:36 am at Thu Aug 13, 2020 4:36 am
>
> 
Azetlor wrote: ↑Wed Aug 12, 2020 11:14 pm
I look forward to a PC unpacker. Will it be in a seperate thread?


That would be a good idea but I suggest to merge this forum with PC, Here's the Unpacker https://github.com/Jayveer/Decima-Explorer it also works for Horizon Zero Dawn.

Does it mean that this tool is able to extract the models and textures form Death Stranding?
## Post #66
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-15T03:44:40+00:00
- Post Title: Re: Death Stranding (PS4)

No, It only extracts .core files at the moment and the PS4 Tools doesn't work with the PC .core files yet.
## Post #67
- Username: Azetlor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 04, 2020 2:25 am
- Post datetime: 2020-08-15T16:51:37+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from qs12 ↑Thu Aug 13, 2020 4:36 am at Thu Aug 13, 2020 4:36 am
>
> 
That would be a good idea but I suggest to merge this forum with PC, Here's the Unpacker https://github.com/Jayveer/Decima-Explorer it also works for Horizon Zero Dawn.

Oh brilliant! Thank you for the link!
## Post #68
- Username: antex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 14, 2020 8:10 pm
- Post datetime: 2020-08-16T03:13:17+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from healyv ↑Sat Aug 08, 2020 1:48 am at Sat Aug 08, 2020 1:48 am
>
> 
When using daemon1's ds.exe, it fails with an Code: Select allUnhandled Exception: OutOfMemoryException. I've got plenty of RAM to spare, so I'm not sure what's up with that. This occurs when running the executable bare with no arguments, with args, and when dropping an extracted .core file onto it to convert (with either PS4 or PC version assets). Has anyone else run into this issue?

if i run ds.exe from game folder, then i got same problem:

```
Unhandled Exception: OutOfMemoryException.
```


Does anyone know how to convert ".core" models to some popular format for further converting to .stl?
I don't know much about modding at all and have not tried it. I just want to extract some models for 3D printing.

Maybe there are descriptions of the structure and format of these files? Or some examples of source code to work with them?

Thanks.
## Post #69
- Username: HiddenX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 14, 2019 4:56 pm
- Post datetime: 2020-08-16T07:59:42+00:00
- Post Title: Re: Death Stranding (PS4)

Big thanks to daemon1 for making this tool. Most of the steps required can be found in this and the horizon zero dawn threads. Just listing a process to help with extracting.

1: Extract files / bin
Get fake ps4 pkg (easy to find now, search for "fpkg" or "fake pkg").
Don't extract from the pc version.
Get Fake_PKG_Tools_v1.5.1
Run orbis-pub-chk.exe from Fake_PKG_Tools_v1.5.1 to extract.
Password should just be all zeros e.g '00000000000000000000000000000000'

2: Get res.txt (OutOfMemoryException issue)
Create a temp folder, add ds.exe, Image0/packed_pink/initial.bin and oo2core_7_win64.dll (found in pc version of death stranding)
Run ds.exe 
Generates res.txt ~20mb (shouldn't get offset / size errors)
Move initial.bin back

3: Exporting core files
Move ds.exe and oo2core_7_win64.dll to \Image0\packed_pink

Find a characters assets in res.txt (normally body, head).
Create a new text file with only the files you want to export in it.
From command line: cd to \Image0\packed_pink and run:
ds /x fileName.txt
This should generate a collection of core files in the same folder
Important: don't move the files to another location, needs to be in this folder for next export step

4: Exporting skinned meshes
Only process one skeleton at a time

Example: head
Export mesh (drag core file onto ds.exe)
This generates a matrices file (used by skeleton)
Export the skeleton (drag core file onto ds.exe)
If the skeleton core file is empty / 0 bytes then you exported the wrong mesh.
Important: delete the matrices file before exporting another mesh e.g the body

Combine the mesh and skeleton:
Open the skeleton.smd file
Double check that the skeleton has the correct values e.g not all zero position
Copy all
Open the mesh.smd file
Paste it at the top of the mesh.smd (replaces first two lines)

5: Textures
Convert using microsofts texconv e.g
texconv -r src/*.dds -ft tga -f RGBA

Import normal maps into gimp with dds plugin (yellow normal maps)

6: Animation
Didn't test. only works with morpheme animations e.g walk, run.

7: converting to stl
Import smd into blender (value Blender Source Tools)
Export stl from blender
## Post #70
- Username: antex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 14, 2020 8:10 pm
- Post datetime: 2020-08-16T10:26:45+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from HiddenX ↑Sun Aug 16, 2020 3:59 pm at Sun Aug 16, 2020 3:59 pm
>
> 
Big thanks to daemon1 for making this tool. Most of the steps required can be found in this and the horizon zero dawn threads. Just listing a process to help with extracting.

thanks for the guide. I did it!
## Post #71
- Username: LordMelkor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 17, 2020 11:29 pm
- Post datetime: 2020-08-17T22:09:32+00:00
- Post Title: Re: Death Stranding (PS4)

Am I understanding correctly that in order to export the models, we would need both the PS4 version and the PC version...?
## Post #72
- Username: HiddenX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 14, 2019 4:56 pm
- Post datetime: 2020-08-18T00:15:13+00:00
- Post Title: Re: Death Stranding (PS4)

You only need the PS4 fake package. oo2core_7_win64.dll is required and can be found in a few games including the PC version of Death Stranding. You might already have it, just try searching you steam apps folder.
## Post #73
- Username: zeaofsuos
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Apr 19, 2019 10:07 pm
- Post datetime: 2020-08-23T18:17:30+00:00
- Post Title: Re: Death Stranding (PS4)

ADMIN, PLEASE DELETE.
## Post #74
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-23T19:07:36+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from zeaofsuos ↑Mon Aug 24, 2020 2:17 am at Mon Aug 24, 2020 2:17 am
>
> 
Does DecimaExplorer support sound extraction?

I used the tool on the PS4 & PC version's core files of Death Stranding and it doesn't seem to show any of the games sound files

No idea, It does work on the movie file however
## Post #75
- Username: STANNco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 26, 2020 8:16 pm
- Post datetime: 2020-08-26T12:27:46+00:00
- Post Title: Re: Death Stranding (PS4)

I assume these Don't work with the PC version? (as i tried and couldn't get any results)
Any way to make it work maybe??

I'd like the models as part of an animation parody i'm working on for the game
## Post #76
- Username: STANNco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 26, 2020 8:16 pm
- Post datetime: 2020-08-27T16:34:13+00:00
- Post Title: Re: Death Stranding (PS4)

I managed to download a ps4 version, and have the pkg. Though i can't unpack it without the passcode? Someone mentioned earlier you should get the fake pkg, but i got no idea what or where that is.

Any help appreciated. I just want some of the models to use in a small animation parody.



Also the thing with merging head and body, i assume the head are separate because there's different clothing in the game. You could manually merge them in a 3D program like Blender or Maya probably
## Post #77
- Username: HiddenX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 14, 2019 4:56 pm
- Post datetime: 2020-08-28T00:13:00+00:00
- Post Title: Re: Death Stranding (PS4)

Just updated the guide. Password should be all zeros e.g '00000000000000000000000000000000'. If it doesn't work then it's probably not a fpkg.
## Post #78
- Username: ExactExtract
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 05, 2020 2:39 am
- Post datetime: 2020-09-08T09:23:22+00:00
- Post Title: Re: Death Stranding (PS4)

So how does one go about getting the animations into SMD? Is this possible?

I've got morpheme files but that's as far as I've got.
## Post #79
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-08T15:04:16+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ExactExtract ↑Tue Sep 08, 2020 5:23 pm at Tue Sep 08, 2020 5:23 pm
>
> 
So how does one go about getting the animations into SMD? Is this possible?

I've got morpheme files but that's as far as I've got.
its described in horizon tool thread, link on 1st post
## Post #80
- Username: ExactExtract
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 05, 2020 2:39 am
- Post datetime: 2020-09-08T17:25:52+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Tue Sep 08, 2020 11:04 pm at Tue Sep 08, 2020 11:04 pm
>
> 
ExactExtract wrote: ↑Tue Sep 08, 2020 5:23 pm
So how does one go about getting the animations into SMD? Is this possible?

I've got morpheme files but that's as far as I've got.

its described in horizon tool thread, link on 1st post

Thank you, I have looked and managed to just about get the morpheme anims working in blender kind of?



They play at least, so that's a major step forward for me but I really need to know what the best method is because this is definitely not normal   , there are 3 different tools in the Horizon thread and some things don't match between games. 

Do you have advice on the best method to use for DS specifically?

P.s are morphemes the only animations that work? I think the game has some more that could be extremely cool. Things like "ds/animations/game/sam/samppm/an_samppm_s_farewall_walk_privateroom" seem unique but may not be possible, similar to Horizons?

Thank you for your hard work and tools for allowing me to get this far.
## Post #81
- Username: bedman88
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 11, 2020 7:12 pm
- Post datetime: 2020-09-11T11:26:09+00:00
- Post Title: Re: Death Stranding (PS4)

Hi, i don't really know anything about 3d model and all that, but i'm interested in the 3d models of Death Stranding, i plan on buying a 3d printer in the near future and i think it can be cool to print the green figures that are in the game. Can someone send me those files or do i have to extract them myself, i'm new to this so i don't really understand how this work
## Post #82
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-11T15:48:32+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ExactExtract ↑Wed Sep 09, 2020 1:25 am at Wed Sep 09, 2020 1:25 am
>
> 
Do you have advice on the best method to use for DS specifically?
you have to use DS tool.

> Reply from ExactExtract ↑Wed Sep 09, 2020 1:25 am at Wed Sep 09, 2020 1:25 am
>
> 
P.s are morphemes the only animations that work?
yes
## Post #83
- Username: af0928
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 12, 2017 10:54 pm
- Post datetime: 2020-09-15T14:09:36+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from bedman88 ↑Fri Sep 11, 2020 7:26 pm at Fri Sep 11, 2020 7:26 pm
>
> 
Hi, i don't really know anything about 3d model and all that, but i'm interested in the 3d models of Death Stranding, i plan on buying a 3d printer in the near future and i think it can be cool to print the green figures that are in the game. Can someone send me those files or do i have to extract them myself, i'm new to this so i don't really understand how this work

Game models are actually unprintable without any proper cleanup. If you know nothing about 3d, I don't think it's going to work.
## Post #84
- Username: Senden
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 30, 2018 1:12 am
- Post datetime: 2020-09-20T22:00:37+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from af0928 ↑Tue Sep 15, 2020 10:09 pm at Tue Sep 15, 2020 10:09 pm
>
> 
bedman88 wrote: ↑Fri Sep 11, 2020 7:26 pm
Hi, i don't really know anything about 3d model and all that, but i'm interested in the 3d models of Death Stranding, i plan on buying a 3d printer in the near future and i think it can be cool to print the green figures that are in the game. Can someone send me those files or do i have to extract them myself, i'm new to this so i don't really understand how this work 


Game models are actually unprintable without any proper cleanup. If you know nothing about 3d, I don't think it's going to work.

Not all of then, I'm having some success on extracted parts with some fairly limited cleanup without having to rebuild everything (just splitting up elements, removing some excess geometry)

As for the toy soldiers? I wish you luck finding them.
[LudensMask.png](https://xentaxbackup.github.io/file/18772_LudensMask.png)
## Post #85
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-09-21T18:21:24+00:00
- Post Title: Re: Death Stranding (PS4)

About the DS animations, here is a tutorial:
[https://www.youtube.com/watch?v=HyBjNQXlguw](https://www.youtube.com/watch?v=HyBjNQXlguw)
## Post #86
- Username: ExactExtract
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 05, 2020 2:39 am
- Post datetime: 2020-09-22T19:06:27+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from devilsnake88 ↑Tue Sep 22, 2020 2:21 am at Tue Sep 22, 2020 2:21 am
>
> 
About the DS animations, here is a tutorial:
https://www.youtube.com/watch?v=HyBjNQXlguw

Thank you for this, greatly appreciated.
## Post #87
- Username: MottledYeen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 06, 2017 1:20 pm
- Post datetime: 2020-09-27T22:47:55+00:00
- Post Title: Re: Death Stranding (PS4)

When trying to export the backpack battery the UV somehow gets really messed up? I'm getting it from ds/models/item/bak0_backpack0/core/bak0_batt_def
[https://i.gyazo.com/5dc5347c0adc7244ad5 ... 9e06c7.png](https://i.gyazo.com/5dc5347c0adc7244ad5d4fc88e9e06c7.png) this is what I end up with when looking at it, anyone have any idea what's going on? I tried putting the texture in anyways to see if it was just scaled down and could be easily fixed without trying to figure out what parts go where, but it seems to be a bit of a jumbled mess..
## Post #88
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-28T06:25:46+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from MottledYeen ↑Mon Sep 28, 2020 6:47 am at Mon Sep 28, 2020 6:47 am
>
> 
When trying to export the backpack battery the UV..
probably wrong UV channel
## Post #89
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-09-28T15:06:19+00:00
- Post Title: Re: Death Stranding (PS4)

You'll also probably need to flip the UV.
## Post #90
- Username: MottledYeen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 06, 2017 1:20 pm
- Post datetime: 2020-09-29T06:19:26+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Mon Sep 28, 2020 2:25 pm at Mon Sep 28, 2020 2:25 pm
>
> 
MottledYeen wrote: ↑Mon Sep 28, 2020 6:47 am
When trying to export the backpack battery the UV..

probably wrong UV channel
How would I go about fixing that in Blender? I've used Blender for quite some time but I've never messed with different UV channels before
## Post #91
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-10-01T22:23:08+00:00
- Post Title: Re: Death Stranding (PS4)

Hi

same problem, some files have wrong UV information, i don´t now why, i hope somebody can help, the second pic shows correct UV, and also some dds file are broken, some of them can be open with Noesis and then it´s possible to export it again in dds, 

regards
## Post #92
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-10-01T22:24:50+00:00
- Post Title: Re: Death Stranding (PS4)

[https://imgur.com/a/ZCelA0X](https://imgur.com/a/ZCelA0X)
## Post #93
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-02T10:30:54+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ap127 ↑Fri Oct 02, 2020 6:23 am at Fri Oct 02, 2020 6:23 am
>
> 
same problem, some files have wrong UV information, i don´t now why, i hope somebody can help, the second pic shows correct UV, and also some dds file are broken
Nothing is broken.

All UVs are ok, including the files mentioned here. Just choose correct UV channel and keep in mind that SMD can only hold 1 channel, so these are not recommended.

Also none of the DDS are wrong. Google how to use DirectX10 standard DDS files. This was mentioned on xentax a million times already.
## Post #94
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-10-03T12:27:06+00:00
- Post Title: Re: Death Stranding (PS4)

I really want to get Chiral Artist's model form ds, but it seems to have some problems with her meshes and textures' extraction:
It said  "File not found in cache" , but I just found out these files list from the res.txt, how could it be "not found"  
Both she and her boyfriend's meshes got this weird problem but the other models are pretty fine.
The problematic files list is:

```
ds/models/characters/ppf_preppersfemale/core/ppf_body_def_v03/model/parts/mesh_body_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_def_v03/model/skeletons/mesh_skeleton_jnt_c_b_000_root
ds/models/characters/ppf_preppersfemale/core/ppf_body_def_v03/model/skeletons/mesh_skeleton_jnt_c_b_000_root_posedeformer
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/animations/neutral
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_arm00_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_arm01_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_foot_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_head00_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_head01_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_head02_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_head03_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_lower00_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_lower01_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_upper00_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_upper01_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/parts/mesh_upper02_lx
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/skeletons/mesh_skeleton_jnt_c_b_000_root
ds/models/characters/ppf_preppersfemale/core/ppf_body_mob/model/skeletons/mesh_skeleton_jnt_c_b_000_root_posedeformer
ds/models/characters/ppf_preppersfemale/core/ppf_textures/textures/ppf_body_arm_shrd_v03_set
ds/models/characters/ppf_preppersfemale/core/ppf_textures/textures/ppf_body_arm_v01_set
ds/models/characters/ppf_preppersfemale/core/ppf_textures/textures/ppf_body_arm_v03_set
ds/models/characters/ppf_preppersfemale/core/pp
```

[](https://ibb.co/0JrCpqk)

[](https://ibb.co/Db5BbZb)
## Post #95
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-10-04T00:11:20+00:00
- Post Title: Re: Death Stranding (PS4)

I tested it, the folders are empty, it seems that there are a few small problems, but only daemon can solve them
## Post #96
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-04T03:33:54+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ap127 ↑Sun Oct 04, 2020 8:11 am at Sun Oct 04, 2020 8:11 am
>
> 
I tested it, the folders are empty, it seems that there are a few small problems, but only daemon can solve them is there a tut for extracting stuff?
## Post #97
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-04T06:38:19+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Kanbara ↑Sat Oct 03, 2020 8:27 pm at Sat Oct 03, 2020 8:27 pm
>
> 
I just found out these files list from the res.txt, how could it be "not found"

It means these files are NOT used in the game. So they are NOT present in files.
Use some of her other models.
## Post #98
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-04T09:22:54+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Sun Oct 04, 2020 2:38 pm at Sun Oct 04, 2020 2:38 pm
>
> 
Kanbara wrote: ↑Sat Oct 03, 2020 8:27 pm
I just found out these files list from the res.txt, how could it be "not found" 

It means these files are NOT used in the game. So they are NOT present in files.
Use some of her other models. can i have permission to get ds tool?
## Post #99
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-04T11:19:38+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Sun Oct 04, 2020 2:38 pm at Sun Oct 04, 2020 2:38 pm
>
> 
Kanbara wrote: ↑Sat Oct 03, 2020 8:27 pm
I just found out these files list from the res.txt, how could it be "not found" 

It means these files are NOT used in the game. So they are NOT present in files.
Use some of her other models. sorry i know im posting a lot/ asking but im stuck on this part "Find a characters assets in res.txt (normally body, head).
Create a new text file with only the files you want to export in it.
From command line: cd to \Image0\packed_pink and run:
ds /x fileName.txt" im confused on what cd is and am i naming the txt x filename? i dont understand
## Post #100
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-10-04T13:37:48+00:00
- Post Title: Re: Death Stranding (PS4)

use " ds /p res.txt "  to extract all files, it is easier to work with, but it uses about 30gb more space, with / p this will extract all existing data with the file structure. I also took the res.txt file and inserted it into Excel, it is also easier to sort or create new tables here
[alle.jpg](https://xentaxbackup.github.io/file/18794_alle.jpg)
## Post #101
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-10-04T13:38:18+00:00
- Post Title: Re: Death Stranding (PS4)

excel 
[alle2.jpg](https://xentaxbackup.github.io/file/18795_alle2.jpg)
## Post #102
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-10-04T13:47:33+00:00
- Post Title: Re: Death Stranding (PS4)

it seems that a part of the Chiral Artist's is in the v00 folder, but can't find her head
[alle4.jpg](https://xentaxbackup.github.io/file/18796_alle4.jpg)
## Post #103
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-04T23:53:03+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ap127 ↑Sun Oct 04, 2020 9:37 pm at Sun Oct 04, 2020 9:37 pm
>
> 
use " ds /p res.txt "  to extract all files, it is easier to work with, but it uses about 30gb more space, with / p this will extract all existing data with the file structure. I also took the res.txt file and inserted it into Excel, it is also easier to sort or create new tables here

Alright so i followed the guide and when i make the temp folder and goto cmd what do i put? it says c:\users\owner> am i suppose to change that? and do i need the pc tool to? or better yet is there a video guide for this?
## Post #104
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-10-05T00:31:38+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from ap127 ↑Sun Oct 04, 2020 9:47 pm at Sun Oct 04, 2020 9:47 pm
>
> 
it seems that a part of the Chiral Artist's is in the v00 folder, but can't find her head

Yeah, I can only found her body so far but her head is gone.
## Post #105
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-10-05T00:32:31+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Sun Oct 04, 2020 2:38 pm at Sun Oct 04, 2020 2:38 pm
>
> 
Kanbara wrote: ↑Sat Oct 03, 2020 8:27 pm
I just found out these files list from the res.txt, how could it be "not found" 

It means these files are NOT used in the game. So they are NOT present in files.
Use some of her other models.

Okay, thanks for you replys!
## Post #106
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-10-05T01:04:32+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from breaper528 ↑Mon Oct 05, 2020 7:53 am at Mon Oct 05, 2020 7:53 am
>
> 
ap127 wrote: ↑Sun Oct 04, 2020 9:37 pm
use " ds /p res.txt "  to extract all files, it is easier to work with, but it uses about 30gb more space, with / p this will extract all existing data with the file structure. I also took the res.txt file and inserted it into Excel, it is also easier to sort or create new tables here


Alright so i followed the guide and when i make the temp folder and goto cmd what do i put? it says c:\users\owner> am i suppose to change that? and do i need the pc tool to? or better yet is there a video guide for this?

①First, you need to press the "Win+R" on your keyboard and type cmd so as to open the command panel we want;

②(The following process is done in cmd)
    1.type d: ("d" means your hard disk's name and the disk where you put your game files in; in other words, if your game files are in disk f, just type down f:,etc., and the full code will be closely like:
C:Users\Satoshi>f:
     2.press Enter, to go to the next command;
C:Users\Satoshi>f:
             F:\>
     3.type down cd and press space, then copy paste the path where your game files are and a folder named "packed pink" is exactly what we want. So the full code will closely be like:
C:Users\Satoshi>f:
             F:\>cd F:\Death Stranding\packed pink
     4.(please make sure ds.exe (the extraction tool) and oo2core_7_win64.dll are both in the packed pink folder)
      If you run ds.exe directly, you will see a res.txt be created in the same folder, which is all the assets list for extraction. Just create a new text and copy paste the assets you want to extract from the res.txt, otherwise it will have all the assets extracted. Save it and name the new text you compile an another name.

      Okay, back to the the cmd, type down ds /x prepper.txt(prepper.txt is the text you create, so the name can be varied), and press Enter. And now it will extract the assets you want in the same folder.
      BTW, if you want to make extracted assets in hierarchical level, just replace the /x with /p(ds /p prepper.txt).
## Post #107
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-05T09:30:16+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Kanbara ↑Mon Oct 05, 2020 9:04 am at Mon Oct 05, 2020 9:04 am
>
> 
breaper528 wrote: ↑Mon Oct 05, 2020 7:53 am
ap127 wrote: ↑Sun Oct 04, 2020 9:37 pm
use " ds /p res.txt "  to extract all files, it is easier to work with, but it uses about 30gb more space, with / p this will extract all existing data with the file structure. I also took the res.txt file and inserted it into Excel, it is also easier to sort or create new tables here


Alright so i followed the guide and when i make the temp folder and goto cmd what do i put? it says c:\users\owner> am i suppose to change that? and do i need the pc tool to? or better yet is there a video guide for this?


①First, you need to press the "Win+R" on your keyboard and type cmd so as to open the command panel we want;

②(The following process is done in cmd)
    1.type d: ("d" means your hard disk's name and the disk where you put your game files in; in other words, if your game files are in disk f, just type down f:,etc., and the full code will be closely like:
C:Users\Satoshi>f:
     2.press Enter, to go to the next command;
C:Users\Satoshi>f:
             F:\>
     3.type down cd and press space, then copy paste the path where your game files are and a folder named "paced pink" is exactly what we want. So the full code will closely be like:
C:Users\Satoshi>f:
             F:\>cd F:\Death Stranding\packed pink
     4.(please make sure ds.exe (the extraction tool) and oo2core_7_win64.dll are both in the packed pink folder)
      If you run ds.exe directly, you will see a res.txt be created in the same folder, which is all the assets list for extraction. Just create a new text and copy paste the assets you want to extract from the res.txt, otherwise it will have all the assets extracted. Save it and name the new text you compile an another name.

      Okay, back the the cmd, type down ds /x prepper.txt(prepper.txt is the text you create, so the name can be varied), and press Enter. And now it will extract the assets you want in the same folder.
      BTW, if you want to make extracted assets in hierarchical level, just replace the /x with /p(ds /p prepper.txt).
I got it, thank you so much
## Post #108
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-05T23:25:21+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Sun Oct 04, 2020 2:38 pm at Sun Oct 04, 2020 2:38 pm
>
> 
Kanbara wrote: ↑Sat Oct 03, 2020 8:27 pm
I just found out these files list from the res.txt, how could it be "not found" 

It means these files are NOT used in the game. So they are NOT present in files.
Use some of her other models.
I know you said its because theyre not in the game and use other models but i cant find anymore of higgs, got any tips?
## Post #109
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-06T18:30:35+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from breaper528 ↑Tue Oct 06, 2020 7:25 am at Tue Oct 06, 2020 7:25 am
>
> 
I know you said its because theyre not in the game and use other models but i cant find anymore of higgs, got any tips?
You're probably missing some of base game files.
You need to have ALL .bin files from the game.
## Post #110
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-10-06T19:24:10+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from Kanbara ↑Sat Oct 03, 2020 8:27 pm at Sat Oct 03, 2020 8:27 pm
>
> ...

Try mbf_mobfemale>mbf_head_a00
## Post #111
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-10-07T13:46:20+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from devilsnake88 ↑Wed Oct 07, 2020 3:24 am at Wed Oct 07, 2020 3:24 am
>
> 
Kanbara wrote: ↑Sat Oct 03, 2020 8:27 pm...

Try mbf_mobfemale>mbf_head_a00

Jesus!!
Thanks!!
## Post #112
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-10-08T01:59:44+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Wed Oct 07, 2020 2:30 am at Wed Oct 07, 2020 2:30 am
>
> 
breaper528 wrote: ↑Tue Oct 06, 2020 7:25 am
I know you said its because theyre not in the game and use other models but i cant find anymore of higgs, got any tips?

You're probably missing some of base game files.
You need to have ALL .bin files from the game.

I did all and its still doing it, is there different model types for the characters? like what should I look for?
## Post #113
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-08T04:02:38+00:00
- Post Title: Re: Death Stranding (PS4)

i did this one from your list, and it extracts fine:

ds/models/characters/hgs_higgs/core/hgs_body_holo/model/parts/mesh_body_lx

it was in one af "area" BINs
## Post #114
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-10-19T18:47:21+00:00
- Post Title: Re: Death Stranding (PS4)

Oh no, tool doesnt work with PC .core files
## Post #115
- Username: sladaar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 20, 2020 5:17 pm
- Post datetime: 2020-10-20T12:30:45+00:00
- Post Title: Re: Death Stranding (PS4)

very sorry to bother guys but the download link seem to be broken (download fails!)!
Am i wrong somehow?

(been using horizon tool but got strange behaviour)
## Post #116
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-20T13:18:17+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from sladaar ↑Tue Oct 20, 2020 8:30 pm at Tue Oct 20, 2020 8:30 pm
>
> 
very sorry to bother guys but the download link seem to be broken (download fails!)!
no, it works. Its not a link btw, the file is embedded on the server, so it CANT be broken
## Post #117
- Username: sladaar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 20, 2020 5:17 pm
- Post datetime: 2020-10-20T17:20:39+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Tue Oct 20, 2020 9:18 pm at Tue Oct 20, 2020 9:18 pm
>
> 
no, it works. Its not a link btw, the file is embedded on the server, so it CANT be broken

Thank you for the reply, it was due to windows antivirus (and firefox and tor weren't explaining, chrome did)!
## Post #118
- Username: kakalot
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 28, 2016 10:13 am
- Post datetime: 2020-10-26T14:00:19+00:00
- Post Title: Re: Death Stranding (PS4)

texture and uv do not match, I think the model may contain multiple uv sets.
but how to open ascii files? blender xnalara addon can't open it
## Post #119
- Username: IXProductions
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 26, 2020 10:36 pm
- Post datetime: 2020-10-26T18:33:38+00:00
- Post Title: Re: Death Stranding (PS4)

Does this tool work with the PC Version?
## Post #120
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-27T07:15:28+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from kakalot ↑Mon Oct 26, 2020 10:00 pm at Mon Oct 26, 2020 10:00 pm
>
> 
but how to open ascii files? blender xnalara addon can't open it
blender xnalara addon opens it
## Post #121
- Username: kakalot
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 28, 2016 10:13 am
- Post datetime: 2020-10-27T07:44:23+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Tue Oct 27, 2020 3:15 pm at Tue Oct 27, 2020 3:15 pm
>
> 
kakalot wrote: ↑Mon Oct 26, 2020 10:00 pm
but how to open ascii files? blender xnalara addon can't open it 

blender xnalara addon opens it
which version? both blender2.8 (XNALaraMesh2.x) and blender2.79b (XNALaraMesh1.8.7) report errors when importing
## Post #122
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-27T09:30:31+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from kakalot ↑Tue Oct 27, 2020 3:44 pm at Tue Oct 27, 2020 3:44 pm
>
> 
all versions work
you probably did something wrong when converting models
## Post #123
- Username: kakalot
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 28, 2016 10:13 am
- Post datetime: 2020-10-27T12:50:00+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Tue Oct 27, 2020 5:30 pm at Tue Oct 27, 2020 5:30 pm
>
> 
kakalot wrote: ↑Tue Oct 27, 2020 3:44 pm

all versions work
you probably did something wrong when converting models

smd file generated at the same time is fine, how to solve it?  
is it possible to generate multiple smd files containing different uvsets (such as xx_uv1.smd, xx_uv2.smd...) when model contains multiple uvsets.

```
rootDir: F:\PS4\Death Stranding\Image0\packed_pink\output
Reading Bones
Traceback (most recent call last):
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\xps_tools.py", line 164, in execute
    status = import_xnalara_model.getInputFilename(xpsSettings)
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\import_xnalara_model.py", line 78, in getInputFilename
    status = xpsImport()
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\import_xnalara_model.py", line 140, in xpsImport
    xpsData = loadXpsFile(xpsSettings.filename)
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\import_xnalara_model.py", line 106, in loadXpsFile
    xpsData = read_ascii_xps.readXpsModel(filename)
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\read_ascii_xps.py", line 223, in readXpsModel
    bones = readBones(ioStream)
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\read_ascii_xps.py", line 95, in readBones
    coords = readXYZ(file)
  File "C:\Users\xxx\AppData\Roaming\Blender Foundation\Blender\2.83\scripts\addons\XNALaraMesh\read_ascii_xps.py", line 26, in readXYZ
    y = (ascii_ops.getFloat(values[1]))  # Y pos
IndexError: list index out of range
location: <unknown location>:-1
location: <unknown location>:-1

```
## Post #124
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-10-27T13:28:07+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from kakalot ↑Tue Oct 27, 2020 8:50 pm at Tue Oct 27, 2020 8:50 pm
>
> 
smd file generated at the same time is fine, how to solve it?  
is it possible to generate multiple smd files containing different uvsets (such as xx_uv1.smd, xx_uv2.smd...) when model contains multiple uvsets.
i dont see reasons for this. SMD is not good format anyway.
Blender trace means nothing for me, because its not my plugin.
Still, most probably you did not add skeleton to the model like its said in the tool description.
## Post #125
- Username: kakalot
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 28, 2016 10:13 am
- Post datetime: 2020-10-27T14:21:39+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Tue Oct 27, 2020 9:28 pm at Tue Oct 27, 2020 9:28 pm
>
> 
kakalot wrote: ↑Tue Oct 27, 2020 8:50 pm
smd file generated at the same time is fine, how to solve it?  
is it possible to generate multiple smd files containing different uvsets (such as xx_uv1.smd, xx_uv2.smd...) when model contains multiple uvsets.

i dont see reasons for this. SMD is not good format anyway.
Blender trace means nothing for me, because its not my plugin.
Still, most probably you did not add skeleton to the model like its said in the tool description.

it can be imported successfully after merging the skeleton,  thanks!!!
## Post #126
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2020-11-08T09:41:07+00:00
- Post Title: Re: Death Stranding (PS4)

Hello!
Just to tell you that it's possible to dump sound files, and here is how to do that. At least on the PC version. As far as I know, in a single .bin data file can be present (at the same time) packed sound files (containing multiple files) and loose sound files. 

The former can be extracted easily using DecimaExplorer-GUI: just look for 
```
sd_wwise_bnk_collection_*
```
 using CTRL+F and extract them. Then, use [Wwise unpacker](https://github.com/Vextil/Wwise-Unpacker/) to extract the single files (remember to rename .core to .pck so that the batch script finds them).



The latter are tougher. Basically, with my dirty solution, I extracted all the files from a single .bin data file and converted them using the tools in Wwise_ unpacker (linked above). To do so, I created these scripts
extract.bat:

```
setlocal EnableDelayedExpansion

for /f "tokens=2 delims= " %%a in ('Archive.exe %1 ^| find "FileTableCount"') do set /a n = %%a

set /a i = 0

:loop
DecimaExplorer -e %1 !i! %~n1\!i!.bin
set /A i+=1
if !i! lss !n! goto loop
```

(note: this requires the tool Archive.exe compiled from [DecimaTools](https://github.com/Wunkolo/DecimaTools) and it's used just to know the number of files contained in a .bin)

toogg.bat:

```
FOR %%c IN (%~n1\*.bin) DO ("ww2ogg.exe" "%%c" --pcb packed_codebooks_aoTuV_603.bin)
DEL "%~n1\*.bin"
FOR %%d IN (%~n1\*.OGG) DO ("revorb.exe" "%%d")
```

(note: requires the tools provided with Wwise unpacker)

For instance, let's consider 7017f9bb9d52fc1c4433599203cc51b1.bin. To use this scripts, just run

```
extract.bat 7017f9bb9d52fc1c4433599203cc51b1.bin
```

This will extract all files in a numbering sequence inside the folder "7017f9bb9d52fc1c4433599203cc51b1".
Then run

```
toogg.bat 7017f9bb9d52fc1c4433599203cc51b1.bin
```

This will convert all the loose (wav) files contained in the folder "7017f9bb9d52fc1c4433599203cc51b1". Note: all .bin files will be deleted, and at the end the folder will contain just .ogg audio files.

With these tools you should be able to extract localized audio files and common sound files present in the game (for instance 7017f9bb9d52fc1c4433599203cc51b1.bin contains BB voice lines, odradek sounds, vehicle sounds, quest completion sounds, BGM and more).


I leave here this useful table with the data file names

```
    6fb69851f3279ea051f48ee6c98c73fe.bin - Area00_English
    225bb34815aa3e89f155ba2515570cb2.bin - Area00_French
    e72aac57de9918c67eaf3d5102c8acb8.bin - Area00_Spanish
    84e35fcf5de2ba16cc1ee893ba4dc56c.bin - Area00_German
    6fcdd0390579931aa1c93da879e28d82.bin - Area00_Italian
    553cfe4d8b9fe4769e534e703bfb9732.bin - Area00_Portuguese
    2709afee4cac7fc87a04bd2b6c1c5882.bin - Area00_Russian
    f573fbfdff7eb1fa271f382e24503f82.bin - Area00_Polish
    f3a2ab17a7c17470623d3e842224841f.bin - Area00_Japanese
    4411fbe7b81d872e8517abf67e932280.bin - Area00_LATAMSP
    6cafab4876800a73ab36290c76730f68.bin - Area00_LATAMPOR
    8761c9be94b95d7197c850a230bb05aa.bin - Area00_Greek
    1a472f28ea1537dd3cb911fd1e18f2af.bin - Area01_English
    f77b66dc12e3085afdf2ccee9e3bddb8.bin - Area01_French
    55a0f2ad6fd854eb46eda325ebd3fdfe.bin - Area01_Spanish
    88c5cf29d347a6f0007199554279573e.bin - Area01_German
    a53083d2a39c921b2fbfc520216f17d7.bin - Area01_Italian
    4c7518f562e8cfc65349f261cb4a4935.bin - Area01_Portuguese
    4e5bed8e41d7417c889b2284f33c35f0.bin - Area01_Russian
    110d9add046eec4d23810f2fa9565924.bin - Area01_Polish
    eb8cd08d682978a9b9112d7c8f54de21.bin - Area01_Japanese
    f7b4c4ff1b831d3adf6fa1952a978767.bin - Area01_LATAMSP
    c172307816383537bd4703897044f6c5.bin - Area01_LATAMPOR
    f26fd3ec3d943dd6aaff93a45a8025c2.bin - Area01_Greek
    c0306eef15c4b5122ab61a834f80d743.bin - Area02
    9abda4bd99f4fa01951fd153775e7e8d.bin - Area02_English
    69e57bab4b0e47d007bab3b3fcca6dc5.bin - Area02_French
    e8b2c1ef002e12ddfb73977afa1955a7.bin - Area02_Spanish
    b11ab76d7450f70cd80f46037963e22f.bin - Area02_German
    47a882f8b80bfb6954d92201251744bf.bin - Area02_Italian
    7eb2acb7d14889097248e156637e95a1.bin - Area02_Portuguese
    0404fe2210c6609046c1c08bf2ea7c8a.bin - Area02_Russian
    cb4196d63aaed195c987dfb47bbfadf5.bin - Area02_Polish
    2c8aaa03cef19c1d7d4d14f8b29c7197.bin - Area02_Japanese
    dae3bdff0b5583a91ff40d98d3bf73a3.bin - Area02_LATAMSP
    13cf568657bcfb893b6b97b5e81f4ae3.bin - Area02_LATAMPOR
    e084898e7d0371f8cd9688cd303841f5.bin - Area02_Greek
    dc847b243b638c5ce539d4be7ff48007.bin - Area04
    8d60c6e8d6ce70496107e588205a3054.bin - Area04_English
    f0f467ec1b144337ef804ab0dc1a633e.bin - Area04_French
    20dec5c29481cc1d3e21dec2b289e8e9.bin - Area04_Spanish
    a64d5675363bcfae85f36b39faafba5d.bin - Area04_German
    0a5d8e4999a0dc48da7b66c8b8251c42.bin - Area04_Italian
    adc5401f627e7d6b1e23afe75e06fe4c.bin - Area04_Portuguese
    0a58238b82416a35c9e3dc3b3a6e825c.bin - Area04_Russian
    3430babbf55916a937a8757da75199c7.bin - Area04_Polish
    237d41a6888266372a7c9100526dfeb9.bin - Area04_Japanese
    7ff527fda0571c79839bb8aa9c3db648.bin - Area04_LATAMSP
    ea97cfbec2be98a216a6450faf9710b0.bin - Area04_LATAMPOR
    a610c95e0690047924d1afbb824d0250.bin - Area04_Greek
    477e458b2c825633499874678a2b9ea5.bin - Beach01
    f70387b309fdda4e66a9d1808815252d.bin - Beach01_English
    c4c4d7253d00afff7e7859822e967f05.bin - Beach01_French
    0a7a707a3e247348d81931fa45ad28b3.bin - Beach01_Spanish
    f829e168029598d8ceea4f4d01e54378.bin - Beach01_German
    8a290e232dd8d4c727cf2da3fadd5c5b.bin - Beach01_Italian
    1c3b38583613deb87f5b4e9ff1dd94c4.bin - Beach01_Portuguese
    f7f21580058bd1b925180851f3969070.bin - Beach01_Russian
    4d8d31832be4055295b9e619cf315740.bin - Beach01_Polish
    c28838ba40cb2165ee8dd703a8cdb0e3.bin - Beach01_Japanese
    c2dc1b0259864bcf814b4cd81cd917d4.bin - Beach01_LATAMSP
    dc915927c83cb738ae87857742e4c774.bin - Beach01_LATAMPOR
    10b8dcebcce8280dac2f30f0a57cba2a.bin - Beach01_Greek
    7017f9bb9d52fc1c4433599203cc51b1.bin - Initial
    a694c2e00b87cd761ee2a25b09a49ea7.bin - Initial_English
    a5dcec9b54e1586b097e5c49a07429c5.bin - Initial_French
    a1cc3eee3d405a5613916e1297641289.bin - Initial_Spanish
    3cd22bf810430d77b7fff991a4b81551.bin - Initial_German
    dbef71d6d372f7c6bdaf3717c119b519.bin - Initial_Italian
    c920bcebb78902bf6ac6c447eab9fb41.bin - Initial_Portuguese
    d8f0b887a3642eca5ada40e8cdff07db.bin - Initial_Russian
    54d23a724866aa2d6025ebb2a688c968.bin - Initial_Polish
    4bb8707b549628feb844fbf8d0c85327.bin - Initial_Japanese
    cf44457b965b72abb6ee66bdddd60b3a.bin - Initial_LATAMSP
    94d6a62c9fb7a869754f0d6bc19f81e7.bin - Initial_LATAMPOR
    8ebc24104a70f5f1b13eb04d175614b2.bin - Initial_Greek
    59b95a781c9170b0d13773766e27ad90.bin - Patch
    3460515fd6d930b689143a8b9a51a060.bin - Remainder
    17881513a7e2a728ccd2ae7301dc9054.bin - Remainder_English
    d9ae8d6654a7ceca64c8dc18952d3209.bin - Remainder_French
    e33dd8b96035b2f7e547aed5fbfdf8e5.bin - Remainder_Spanish
    a6b263ffdda8aca7fb8decba961b8097.bin - Remainder_German
    e8276e34701d2a6664c9a29d20062f9c.bin - Remainder_Italian
    9eb0941601e90d4b6c81d62b48959786.bin - Remainder_Portuguese
    fa24bd744dbf75e81308c45581f49817.bin - Remainder_Russian
    be25f0823739852892e4b6179818e715.bin - Remainder_Polish
    17fa480245a3a67a1e5ecc246cee719d.bin - Remainder_Japanese
    b52dacb981213ed55cb3be42bea80258.bin - Remainder_LATAMSP
    dbcebbf108d0da62acee516ab446ccd0.bin - Remainder_LATAMPOR
    fee239d94dfcb9a257cd4d15fe0a7d21.bin - Remainder_Greek
    968bf82f34e2b499687c901a888e633a.bin - Warrior01
    4707c0dea95bdf7b38ed0d838965e0e6.bin - Warrior01_English
    b70fa685f46ec3f4b8a19b53f666b69f.bin - Warrior01_French
    fb4e818aa0dc2f8f791fe518a8910337.bin - Warrior01_Spanish
    3523588f0825ad5f54013b6031361d3b.bin - Warrior01_German
    26d92e4a0d5e060ba1879de2d02f5fc2.bin - Warrior01_Italian
    b20229b7199ba8c81854d513f764e2c9.bin - Warrior01_Portuguese
    fb5160bf0cda8b0bca124d04d51de62c.bin - Warrior01_Russian
    68d7fcb76bb55037ebbffbd01bcb2b08.bin - Warrior01_Polish
    c9d841287e962d3d54123652828ebd00.bin - Warrior01_Japanese
    44108381064a698eb7376aee4bc1478d.bin - Warrior01_LATAMSP
    d0218c32efbff643a19603a31efcc3c2.bin - Warrior01_LATAMPOR
    8d73fa4af178fe81ae95d0cb8c7fc606.bin - Warrior01_Greek
    fcd4b5918cea9a220c0da171bb60c214.bin - Warrior02
    7ccfce87d9887adf1689fbd07df4200a.bin - Warrior02_English
    46485581ea66e58e27b5040b40257bce.bin - Warrior02_French
    80022ad18cf34441da2e8e8557d524df.bin - Warrior02_Spanish
    aa828c35c790d250cdc765ab9b8e6050.bin - Warrior02_German
    6a562dc4e089db4b922573066a7ec884.bin - Warrior02_Italian
    2b4203d8d2cf539bada40ff7fbe734fc.bin - Warrior02_Portuguese
    cd336bf6b36bab5527c3b3609093abe7.bin - Warrior02_Russian
    e9ea778cf34ee584e523e958bfcf8f81.bin - Warrior02_Polish
    50023cc2d26d8242720e71676ceac967.bin - Warrior02_Japanese
    9392f016b4dba2cfec41607e0a9e2250.bin - Warrior02_LATAMSP
    da0346efdd0d2b8eb3c067c93ffdbf33.bin - Warrior02_LATAMPOR
    343d88e2515bfd702fd34962f63c1d45.bin - Warrior02_Greek
    a53f66da5938a089f06b8a0c07c97f18.bin - Warrior03
    93a37de4096fad67e0c99100775cce42.bin - Warrior03_English
    064bff9f859fb5a0bd74f0a486e133ab.bin - Warrior03_French
    32c38c240a31c6452f47836177ee46b9.bin - Warrior03_Spanish
    3c040baec191e5117685af0bf4e2c312.bin - Warrior03_German
    9652986d6bacd063df6cbb252ef828ee.bin - Warrior03_Italian
    9ac69cf07935e12ebc4a10a5a846d5cf.bin - Warrior03_Portuguese
    1bb90bd3941536ce94002ae82a953f6b.bin - Warrior03_Russian
    54106a2ec29dfb15584b5c104c05b219.bin - Warrior03_Polish
    b0720c4389202911af7e64531d973a00.bin - Warrior03_Japanese
    49a78b888f6a86fbb68a50b115ee77c4.bin - Warrior03_LATAMSP
    138969409f16e44df28d7fbcb87a5909.bin - Warrior03_LATAMPOR
    819f5249d44b19c7e4bff600b89a1a32.bin - Warrior03_Greek
```


P.s.: a huge thanks to the developers of these tools!
## Post #127
- Username: Fenixs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 25, 2020 3:08 am
- Post datetime: 2020-11-08T20:33:02+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from giofrida ↑Sun Nov 08, 2020 5:41 pm at Sun Nov 08, 2020 5:41 pm
>
> 
requires the tool Archive.exeCan you upload this file?
## Post #128
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2020-11-09T09:00:04+00:00
- Post Title: Re: Death Stranding (PS4)

Sure, [here's the download](http://www.mediafire.com/file/al1wc34lsxu5hqp/DecimaTools-master.zip/file).
I compiled DecimaTools using gcc under cygwin, but I placed the required libraries along with executables. Let me know if it works
## Post #129
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2020-11-09T12:47:31+00:00
- Post Title: Re: Death Stranding (PS4)

I also give you a summary of the audio content of data files and packed files that I extracted. The number of audio files is written between brackets.

Loose files:

```
c0306eef15c4b5122ab61a834f80d743.bin - Area02:    BGM and few sounds (72)
dc847b243b638c5ce539d4be7ff48007.bin - Area04:    bossfight (I think) BGM and sounds (24)
7017f9bb9d52fc1c4433599203cc51b1.bin - Initial:   BB, odradek, completion, vehicles, BGM, more (1942)
3460515fd6d930b689143a8b9a51a060.bin - Remainder: room, m-link, terminal?, BB (194)
acc0d12f571a5b85f368497756cbcd3c.bin - ???:       cutscenes BGM and sounds, q-pid activation, robot delivery, 'knots' sounds (140)
```


Packed files:

```
ds\sounds\wwise_bnk_collections\sd_wwise_bnk_collection_area_general:                  mostly enemies (839)
ds\sounds\wwise_system_bnk_collections\sd_wwise_system_bnk_collection_system_resident: mostly hud sounds (the "like!" sound too), ringtones, gunfires (3132) 
```
## Post #130
- Username: Fenixs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 25, 2020 3:08 am
- Post datetime: 2020-11-09T19:19:35+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from giofrida ↑Mon Nov 09, 2020 5:00 pm at Mon Nov 09, 2020 5:00 pm
>
> 
Sure, here's the download.
I compiled DecimaTools using gcc under cygwin, but I placed the required libraries along with executables. Let me know if it worksThanks, It works.
## Post #131
- Username: Realmoonlight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 05, 2020 3:55 pm
- Post datetime: 2020-11-10T07:27:31+00:00
- Post Title: Re: Death Stranding (PS4)

Пожалуйста, помогите кто-нибудь достать Клиффа из игры
Hi, please help someone get Cliff out of the game (smd, blender. max). I really need it for use in Xnalara
## Post #132
- Username: phoondos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 14, 2020 12:55 pm
- Post datetime: 2020-11-14T05:03:23+00:00
- Post Title: Re: Death Stranding (PS4)

how would I rip files out of the PC version? I don't have a packed_pink folder.
## Post #133
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2020-12-02T10:17:37+00:00
- Post Title: Re: Death Stranding (PS4)

could someone rip cliff or higgs? i cant get get the models lol
## Post #134
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-12-02T10:29:04+00:00
- Post Title: Re: Death Stranding (PS4)

Death Stranding - How to rip models and textures from PS4 version:

[https://www.youtube.com/watch?v=myKl1HmOBsc](https://www.youtube.com/watch?v=myKl1HmOBsc)
## Post #135
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2020-12-19T20:27:02+00:00
- Post Title: Re: Death Stranding (PS4)

Is there any solution how to rip models & textures from PC Version, and if yes, can anybody make tut on youtube maybe, and also how to extract the audio files, that would be nice
## Post #136
- Username: LIANGJJ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 30, 2021 2:31 pm
- Post datetime: 2021-02-25T10:09:32+00:00
- Post Title: Re: Death Stranding (PS4)

PKG extraction password invalid, how to help, hope to get help!!!
## Post #137
- Username: swzjb123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 09, 2021 11:02 pm
- Post datetime: 2021-03-09T15:03:03+00:00
- Post Title: Re: Death Stranding (PS4)

Thanks!!
## Post #138
- Username: tyresebro1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 05, 2020 6:54 pm
- Post datetime: 2021-03-10T10:29:50+00:00
- Post Title: Re: Death Stranding (PS4)

Do all of the roads I make go out online? If someone gets my roads do they get ALL of my roads or just a part? Ive had to remake 99% of them solo, so does that mean I'm some kind of road fairy now, where people get connected to me and suddenly have roads? Because I've had to re build them solo that makes me think they don't work that way (surely someone else I've connected to has built a road past the first couple), but rather when I rebuild a road it only adds materials to other peoples worlds, but they still have to cap them off themselves..... but when I first got to the second map there where already a couple pieces of road already built, so maybe they dont work in a strait forward manner. I'm beginning to think that I'm not being nearly as helpful as I thought I was when I started, which is pretty disheartening.[wholesale folding chairs](https://blossomfurnishings.com/metal-foldable-chairs-manufacturer/)
## Post #139
- Username: Synrvrer3
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 13, 2020 2:17 pm
- Post datetime: 2021-03-18T08:33:42+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from daemon1 ↑Tue Oct 27, 2020 9:28 pm at Tue Oct 27, 2020 9:28 pm
>
> 
kakalot wrote: ↑Tue Oct 27, 2020 8:50 pm
smd file generated at the same time is fine, how to solve it?  
is it possible to generate multiple smd files containing different uvsets (such as xx_uv1.smd, xx_uv2.smd...) when model contains multiple uvsets.

i dont see reasons for this. SMD is not good format anyway.
Blender trace means nothing for me, because its not my plugin.
Still, most probably you did not add skeleton to the model like its said in the tool description.
Do you happen to where where cliffs head is? The one I got when you apply the textures look weird and he has no hair or do i have to apply it?
## Post #140
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2021-03-19T02:58:22+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from devilsnake88 ↑Wed Dec 02, 2020 6:29 pm at Wed Dec 02, 2020 6:29 pm
>
> 
Death Stranding - How to rip models and textures from PS4 version:

https://www.youtube.com/watch?v=myKl1HmOBsc

what is the difference of _tear _def and _holo?
## Post #141
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2021-03-19T20:44:51+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from breaper528 ↑Fri Mar 19, 2021 10:58 am at Fri Mar 19, 2021 10:58 am
>
> 
what is the difference of _tear _def and _holo?

Did you play the game or even took a look at the corresponding textures to see before asking...?
## Post #142
- Username: breaper528
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 03, 2020 6:22 am
- Post datetime: 2021-03-21T01:21:15+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from devilsnake88 ↑Sat Mar 20, 2021 4:44 am at Sat Mar 20, 2021 4:44 am
>
> 
breaper528 wrote: ↑Fri Mar 19, 2021 10:58 am
what is the difference of _tear _def and _holo?


Did you play the game or even took a look at the corresponding textures to see before asking...?

yes and yes i know what holo is someone said tear is a model that can make tears? i have no idea what tear and def is sorry for the lack of knowledge i couldnt see a difference in the textures any help would be appreciated : )
## Post #143
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2021-03-21T16:36:44+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from breaper528 ↑Sun Mar 21, 2021 9:21 am at Sun Mar 21, 2021 9:21 am
>
> ...
def -> default apearances?
tear -> when characters have appearing tears?
holo -> when characters appears as holograms?

If you take a look at the models with (or without) the textures you see the differences...
## Post #144
- Username: GPChannel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2021 3:42 pm
- Post datetime: 2021-04-11T20:54:21+00:00
- Post Title: Re: Death Stranding (PS4)

Maybe can someone port Sam Lake (the veteran) from the game?
## Post #145
- Username: BaynanaSlug
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 15, 2021 7:10 am
- Post datetime: 2021-07-17T04:20:34+00:00
- Post Title: Re: Death Stranding (PS4)

Can someone please help me understand how to extract the fonts from the game? I have no idea what I'm doing and was hoping there was a way to derive .ttf or .otf files from the .core files I extracted w/ Decima Explorer.
## Post #146
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2021-07-22T07:33:12+00:00
- Post Title: Re: Death Stranding (PS4)

> Reply from BaynanaSlug ↑Sat Jul 17, 2021 12:20 pm at Sat Jul 17, 2021 12:20 pm
>
> 
Can someone please help me understand how to extract the fonts from the game? I have no idea what I'm doing and was hoping there was a way to derive .ttf or .otf files from the .core files I extracted w/ Decima Explorer.

Hi! I had a look at those files and actually managed to understand how they work. There are lots of similarities with TrueType fonts and shouldn't be really hard to convert them to a common file format. At the moment I was able to read the font data and print letters using MATLAB:

[](https://ibb.co/PQFn56F)
[](https://ibb.co/KrJpmcr)

I will post a proof of concept code and information on how data is encoded in the following days.
## Post #147
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2021-07-23T15:36:04+00:00
- Post Title: Re: Death Stranding (PS4)

Ok so here's how data is stored in these font files. Let's consider the font "bocdmonolightultcond.core".
Note that all the hex numbers are stored in little endian format, that is, they must be read right to left. 

Let's start from the header:


F3 08 7B 7B 6C 8D E6 E0 is the file header, and is present in all of these font .core files.
31 10 00 00 = 4145 bytes is the file length in bytes.
A4 64 01 DC F5 D4 45 43 8E E7 6D CE 1F A7 EC DD is most probably a hash value used by the game to reference to this font. Indeed, it is present inside the file "ui_font_family.core" that it seems to contain information on which font 
to use in the UI of the game.
18 00 00 00 = 24 bytes is the length of the font name, in bytes.
67 C5 E1 31 unknown, may be a date or a checksum.
42 4F 20 43 44 20 4D 6F 6E 6F 20 4C 69 67 68 74 20 55 6C 74 43 6F 6E 64 = "BO CD Mono Light UltCond" is of course the font name, composed of 24 bytes.



00 00 7A 44 = 1000. It is the "EM units" of the font.
00 00 48 44 = 800. It is the "ascent" of the font, that is, the positive height of characters with respect to the baseline.
00 00 48 43 = 200. It is the "descent" of the font, that is, the negative height of characters with respect to the baseline.
00 00 2F 44 = 700. It is the height of capital letters in the font.

Here is a picture to better clarify the meaning of those parameters:

Note that ascent + descent = EM.

0B 00 00 00 = 11. It is the number of characters stored in the font file (in this case 10 numbers + 1 for space).

Then, the next 4 bytes, right after 00 80 A5 43, are 20 00 00 00 = ' ' (it is the symbol of a space). Let's skip this one for a moment and consider the next glyph, which is easier to understand:



00 80 A5 43 = 331. It is the so called "advance" of the glyph.
30 00 00 00 = '0'. It is the symbol of the glyph: a zero.
00 00 34 42 00 00 00 00 = (45,0). They are the (x,y) coordinates of the lower left point of the glyph.
00 80 8E 43 00 00 2F 44 = (285,700). They are the (x,y) coordinates of the upper right point of the glyph.

To better understand the meaning of these values, refer to the following figure, where you can clearly see the "advance" and "min" and "max" coordinates:


In most fonts, glyph's data is stored as a sequence of coordinates of points that define its outlines. There may be more than one outline (this happens if the outlines need to be disjoint like in the symbols 'O', '=', etc.).
02 00 00 00 = 2. It is the number of outlines that define the borders of the glyph.
Now we enter in the #1 outline details:
0F 00 00 00 = 15 is the length of what I call "line data" of the outline, and define how the outline must be traced.
42 01 42 01 42 01 42 01 42 01 42 01 42 01 42 is the "line data" of this outline. In each byte, 
   if the bit #6 = 0, the number represent the number of points connected by straight lines (e.g. 01 = 1 straight line);
   if the bit #6 = 1, the number subtracted by 64 represent the number of points connected by bezier curves (e.g. 42 -> 2 bezier curves).

18 00 00 00 = 24 is the number of coordinates (x,y) of points that define the outline.
So 24 x 2 coord. x 4 bytes = 192 bytes is the length of the following outline data:
00 00 65 43 00 80 2D 44 
00 C0 5E 43 00 00 2F 44 
00 00 57 43 00 00 2F 44 
00 00 E6 42 00 00 2F 44
00 80 D6 42 00 00 2F 44 
00 00 CA 42 00 80 2D 44
00 00 4C 42 00 00 21 44
00 00 34 42 00 70 1F 44 
00 00 34 42 00 80 1D 44 
00 00 34 42 00 00 8C 42 
00 00 34 42 00 00 79 42 
00 00 4C 42 00 00 60 42 
00 00 CA 42 00 00 C0 40 
00 80 D6 42 00 00 00 00 
00 00 E6 42 00 00 00 00 
00 00 57 43 00 00 00 00 
00 C0 5E 43 00 00 00 00 
00 00 65 43 00 00 C0 40 
00 80 8B 43 00 00 60 42 
00 80 8E 43 00 00 79 42 
00 80 8E 43 00 00 8C 42 
00 80 8E 43 00 80 1D 44 
00 80 8E 43 00 70 1F 44 
00 80 8B 43 00 00 21 44
is the sequence of points expressed as coordinates (x,y) that define the outline. 
In this example there are indeed 24 points.

After this block of data you can see the "line data" of outline #2 followed by its sequence of points.
You should now be able to understand how the space ' ' glyph is stored. Note that no outlines have been defined for it, and (x,y) min and max are meaningless for it.

Using this information, I was able to write a small script using MATLAB. Here it is an example of the number '0' that was discussed above:
[](https://ibb.co/pxZjkPx)
Note how the glyph is actually centred with an advance of 331 units. The lower left point is indeed (45,0) and the upper right is (285,700).
The numbers in red, from 1 to 24, represent the numbered sequence of points in the outline #1. 

A note about those bezier curves used to join points: according to [this webpage](http://chanae.walon.org/pub/ttf/ttf_glyphs.htm) (and also [this post](https://stackoverflow.com/questions/20733790/truetype-fonts-glyph-are-made-of-quadratic-bezier-why-do-more-than-one-consecu)), a quadratic bezier curve is used to join two adjacent points. In order to reduce the number of data stored in the font file, the virtual control point is not present among the sequence of points of the outline, and must be computed as the mean of the previous and the next points in the sequence.

Sorry for the long post, but I wanted to be as clear as possible. Let me know if you have any question or want to add more information about this topic. 


Update: 
I finally understood the meaning of the font values next to its name. They are indeed metrics used to define the font and are called "EM units", "ascent", "descent" and "cap height". 
Then, I proceeded to generate a SVG font (which is a deprecated file format, but really easy to understand) using [this webpage](https://www.w3.org/TR/SVG11/fonts.html) as reference. This is done with the new script "generatesvgfont.m".
The last step to obtain a TrueType font is to convert it with a software. To do so, open FontForge, import the SVG font:
[](https://ibb.co/zGC4phy)
Then go to Element->Font Info.. and add a value in the "Version" field (you can digit whatever number you want). Finally, go to File->Generate Fonts.. and save the font as .TTF or whatever format you need. Ignore the errors that may pop up.

The MATLAB scripts are here attached and updated. 

"demo.m" is indeed a demo script that prints the font table and then a sentence.
"generatesvgfont.m" is used to create a SVG font from the imported .core data.
[ds_font.zip](https://xentaxbackup.github.io/file/20522_ds_font.zip)
## Post #148
- Username: kakuka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 03, 2021 12:50 am
- Post datetime: 2021-08-04T15:26:19+00:00
- Post Title: Re: Death Stranding (PS4)

pic fbffef4d176b845fe659bfc361fe022.png (12.34 KiB) Viewed 243 times


It's very cool!
But,why  I failed  in  the step of  drag core file into the ds.exe??? There is nothing Output ... 
I'm almost crazy~~~
## Post #149
- Username: Synrvrer3
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 13, 2020 2:17 pm
- Post datetime: 2021-08-30T20:32:33+00:00
- Post Title: Re: Death Stranding (PS4)

Does anyone know if cliffs trenchcoat model is available to be ripped?
## Post #150
- Username: Heraizen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 04, 2021 2:38 pm
- Post datetime: 2021-09-04T13:30:11+00:00
- Post Title: Re: Death Stranding (PS4)

Anyone figured out how to extract images from packed_pink\interface\textures\ds\

Looking to get some of the menu and map icons for a project?
## Post #151
- Username: UltraBlake
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 25, 2021 11:07 am
- Post datetime: 2021-10-29T05:49:09+00:00
- Post Title: Re: Death Stranding (PS4)

Just wanted to share some progress I've made, and give a heartfelt thank you to everyone who has taken the time to write code and figure this all out.

This is in blender with the skeleton working great, and texture applied. Not done yet, as I want to import the other necessary textures. I'm excited to do some custom animation too.

[](https://ibb.co/WWv8jNM)

You guys rock!

Edit: Oh yeah, I did have a question. Does anyone know if you can import animations from the an_ files for the particular models? I tried running one through ds.exe but it didn't spit anything out that I'm aware of.
## Post #152
- Username: Rainsky
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 13, 2022 11:38 pm
- Post datetime: 2022-02-13T15:39:23+00:00
- Post Title: Re: Death Stranding (PS4)

Nice !
## Post #153
- Username: xitjunk
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 03, 2022 8:18 am
- Post datetime: 2022-11-07T02:24:45+00:00
- Post Title: Re: Death Stranding (PS4)

hey guys anyone knows how to extract the sound files?
## Post #154
- Username: NotStuButPid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 02, 2023 5:06 pm
- Post datetime: 2023-04-02T16:11:27+00:00
- Post Title: Re: Death Stranding (PS4)

guys how do I extract the green figures with its posture in private room? I have a 3d printer and I want to print it
