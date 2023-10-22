## Post #1
- Username: Szkaradek123
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-08T18:41:32+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Tools

Noesis Mesh Importer for Lara Croft and the Temple of Osiris by Gh0stBlade:



[Download fmt_LC2_mesh.py v1.4](http://www.tombraiderforums.com/showthread.php?p=7234672)

Regards.
## Post #2
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T18:48:08+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Lara Croft and the Temple of Osiris has been released.

As expected there are some slight format changes to that of the last game and the tools don't seem to be supported.

Anyone able to push out updated tools?

And there are files check?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-08T19:02:26+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

I have uploaded a file sample here:

[Bigfile_English.000.tiger.rar](https://mega.co.nz/#!J9BxHbyA!BFR1M1ccNMY6RNVhmiR22mAbUq6aU3XawbEg-SP9jN0)
## Post #4
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-12-09T15:22:35+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

I have tested this file with this unpacker:
[viewtopic.php?f=10&t=10174](http://forum.xentax.com/viewtopic.php?f=10&t=10174)
but don't work correctly

any ideas?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-09T20:25:17+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

I'm working on unpacker but the situation as in with Tomb Raider 2013. This DRM's used only as index (pointer) for data. Format TIGER a little bit modified, also modified CDRM's structure (data for DRM's)
## Post #6
- Username: roman4112
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-09T21:27:50+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Ekey
>
> I'm working on unpacker but the situation as in with Tomb Raider 2013. This DRM's used only as index (pointer) for data. Format TIGER a little bit modified, also modified CDRM's structure (data for DRM's)

Great work as always EKey!

Yes that is correct.... I wrote a quick unpacker but it's missing the filenames and I don't have any tools to dump them. What you're best off doing is maybe... Directly taking the DRM name, cutting off ".drm" and extracting all DRM sections to their own folder within it. I guess that's how it's intended to be.

Do you think you can dump decompressed files? I didn't write an DRM extractor at all. Format looks very similar to TR2013's DRM format.

I'm interested in the meshes  

Regards.
## Post #7
- Username: jmgg
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-11T02:31:49+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Well I managed to extract a mesh file correctly....

Subsequently I just branched off my existing Tomb Raider: Underworld Noesis mesh importer and this happened:



I haven't yet tested it on other meshes but it *should* work on them all... I hope....

I need Lara's mesh!   

Regards.
## Post #8
- Username: jmgg
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-12T18:09:12+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Mesh plugin is live, still awaiting for a propper extractor.

Edit: Location of the skeleton is unknown. If someone manages to locate where they're stored please let me know!
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-14T23:09:44+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Script version 1.3 is available. Added some new texture types, code for future updates and some other stuff....
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-15T14:23:44+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Some progress



Not sure what types are valid, but content data is suitable
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-15T18:18:50+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Well, tools for test out 

TIGER Unpacker (0.0.1 [r1]) / Ekey (h4x0r)
[LCTOTIGGERUnpacker_0.0.1.[r1].rar](https://xentaxbackup.github.io/file/8280_LCTOTIGGERUnpacker_0.0.1.[r1].rar)
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-15T18:23:31+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)
[Download_Link.rar](https://xentaxbackup.github.io/file/8281_Download_Link.rar)
## Post #13
- Username: ssringo
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-15T22:48:26+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Updated Noesis script to support the meshes without stripped headers. Should be compatible with EKey's unpacker.

[fmt_LC2_mesh_1_4.py](https://mega.co.nz/#!p84nAITC!LZf-E90XeuHjGbwtA0a_pWNO3QiaJDpTOSIuNaCRSNo)
## Post #14
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-16T01:21:21+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Been keeping an eye on this thread. Thanks to Ekey and Gh0stblade for their work. Can't wait to get home and try these out. 

Haven't seen any talk about skeletons since Gh0stblade mentioned he was looking for them. Any luck with those? I'm wondering if they bothered giving them much of a skeleton. Can't remember seeing anyone's face having any movement in the game.
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-16T01:34:05+00:00
- Post Title: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from ssringo
>
> Been keeping an eye on this thread. Thanks to Ekey and Gh0stblade for their work. Can't wait to get home and try these out. 

Haven't seen any talk about skeletons since Gh0stblade mentioned he was looking for them. Any luck with those? I'm wondering if they bothered giving them much of a skeleton. Can't remember seeing anyone's face having any movement in the game.

Lots of information has been stripped out of the mesh files. They no longer contain the skeleton. The material info is also missing too. The reason for this could be:

1. I'm looking at the wrong DRM file (Unlikely).
2. The Skeleton is in another DRM file.
3. The Skeleton is now a 1 frame animation.

Don't have a clue but they need finding because it's such a shame.

Regards.
## Post #16
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-04-24T09:11:07+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Thanks All
How to decoding .psd9 file?
## Post #17
- Username: A20Group
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-04-24T17:27:48+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from A20Group
>
> Thanks All
How to decoding .psd9 file?
The Noesis script I wrote should import the PCD files fine.
## Post #18
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-04-26T09:35:09+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Gh0stBlade
>
> A20Group wrote:Thanks All
How to decoding .psd9 file?
The Noesis script I wrote should import the PCD files fine.
Where is the link?
and After editing the file .pcd9?
thnaks man
## Post #19
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-05-05T19:16:33+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Plz Give Me Noesis Mesh Importer for Lara Croft and the Temple of Osiris by Gh0stBlade Link.
## Post #20
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-08T11:28:54+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

[http://www.tombraiderforums.com/showthr ... ?p=7234672](http://www.tombraiderforums.com/showthread.php?p=7234672)
## Post #21
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-05-08T13:53:29+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Gh0stBlade
>
> http://www.tombraiderforums.com/showthr ... ?p=7234672
Thank you so much for care
But Link Script fmt_LC2_mesh_1_5.py open
fmt_TR8_mesh_2_4.py script link .
Strike it just now
thanks
## Post #22
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-11-15T06:52:06+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

[https://www.sendspace.com/file/vr5fel](https://www.sendspace.com/file/vr5fel)
линк в архиве устарел, если не линиво перезалейте DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r) для Temple of Osiris
==============

the link in the archive is outdated, if not difficult, to re-download DRM for Temple of Osiris...
hanks in advance..))
## Post #23
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-11-19T13:12:03+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

упс...все дружно игнор включили...
Кста по именам файлов вопрос, я их получил патчем сетапа игры, но с первого уровня не больше 600 имён.
Есть другой способ?

```
E9 BE3A9B07     JMP 07EF2A1C


PUSHAD
PUSH 3
PUSH 07EF29B8
PUSH 07EF2A08                                     ; ASCII "FileNames.list"
ALL DWORD PTR DS:[<&KERNEL32.OpenFile>]
MOV DWORD PTR DS:[7EF29B4],EAX
PUSH 0
PUSH 07EF29AC
PUSH 10000
PUSH 07EF2B00
PUSH EAX
CALL DWORD PTR DS:[<&KERNEL32.ReadFile>]
MOV EAX,DWORD PTR SS:[ESP+28]
MOV ECX,DWORD PTR DS:[EAX]
MOV DWORD PTR DS:[7EF2900],ECX
ADD EAX,4
MOV AL,BYTE PTR DS:[EAX]
MOV BYTE PTR DS:[7EF2904],AL
MOV EDX,DWORD PTR SS:[ESP+2C]
XOR ECX,ECX
CMP BYTE PTR DS:[EDX],0
JMP SHORT 07EF2A68:
JE SHORT 07EF2A71
INC EDX
INC ECX
JMP SHORT 07EF2A68
JE SHORT 07EF2A71:
MOV EDI,07EF2905
MOV ESI,DWORD PTR SS:[ESP+2C]
REP MOVS BYTE PTR ES:[EDI],BYTE PTR DS:[ESI]
MOV EAX,DWORD PTR SS:[ESP+24]
ADD EAX,4
MOV EAX,DWORD PTR DS:[EAX]
MOV DWORD PTR DS:[EDI],EAX
PUSH 0
PUSH 0
MOV EAX,07EF2900
JMP SHORT 07EF2A90:
CMP BYTE PTR DS:[EAX],0
JE SHORT 07EF2A99
INC EAX
INC ECX
JMP SHORT 07EF2A90
JE SHORT 07EF2A99:
MOV DWORD PTR DS:[EAX],0A0D
SUB EAX,ECX
ADD ECX,2
PUSH ECX
PUSH EAX
MOV EAX,DWORD PTR DS:[7EF29B4]
PUSH EAX
CALL DWORD PTR DS:[<&KERNEL32.WriteFile>]
MOV EAX,DWORD PTR DS:[7EF29B4]
PUSH EAX
CALL DWORD PTR DS:[<&KERNEL32.CloseHandle>]
MOV EDI,07EF2900
MOV ESI,07EF2950
MOV ECX,60
REP MOVS BYTE PTR ES:[EDI],BYTE PTR DS:[ESI]
POPAD
ADD ESP,10
POP EBP
RETN 8

```
## Post #24
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-11-28T16:22:42+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Ekey
>
> DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)
Hi
Please Re Upload File
Thanks
## Post #25
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-12-10T14:52:52+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from A20Group
>
> Ekey wrote:DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)
Hi
Please Re Upload File
Thanks
That was really one of the file was uploaded again?
## Post #26
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-10T21:03:48+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from A20Group
>
> A20Group wrote:Ekey wrote:DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)
Hi
Please Re Upload File
Thanks
That was really one of the file was uploaded again?
in RTBDRMDumper identical algorithm, types of files Dumper loads by default, go check bigfile.000.tiger, and fix in two places a pointer to the actual offset. In the memory of the process.
## Post #27
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-12T00:06:00+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

With file names a simple task. A little handmade in OllyDbg. Put a breakpoint at the beginning of the hash function of files for fast searching in a hash table. For Trl,Tra,Tru, LCGL :

```
85C9                                                TEST ECX,ECX              
0F84 8E000000                                       JE 0047DA09               
56                                                  PUSH ESI                  
8D6424 00                                           LEA ESP,DWORD PTR SS:[ESP]
0FB632                                              MOVZX ESI,BYTE PTR DS:[EDX
C1E6 18                                             SHL ESI,18                
33C6                                                XOR EAX,ESI               
42                                                  INC EDX                   
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D996        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D998        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9A5        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D9A7        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9B4        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D9B6        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9C3        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D9C5        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9D2        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D9D4        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9E1        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D9E3        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9F0        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047D9F2        
D1E0                                                SHL EAX,1                 
85C0                                                TEST EAX,EAX              
79 09                                               JNS SHORT 0047D9FF        
03C0                                                ADD EAX,EAX               
35 B71DC104                                         XOR EAX,4C11DB7           
EB 02                                               JMP SHORT 0047DA01        
D1E0                                                SHL EAX,1                 
49                                                  DEC ECX                   
0F85 78FFFFFF                                       JNZ 0047D980              
5E                                                  POP ESI                   
F7D0                                                NOT EAX                   
C3                                                  RETN                      

```

For Tr2013, LCTO,RTR :

```
8BC1                                                  MOV EAX,ECX                           
C1E0 18                                               SHL EAX,18                            
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E1D4                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E1D6                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E1E3                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E1E5                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E1F2                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E1F4                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E201                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E203                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E210                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E212                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E21F                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E221                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E22E                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E230                    
03C0                                                  ADD EAX,EAX                           
85C0                                                  TEST EAX,EAX                          
79 09                                                 JNS SHORT 0102E23D                    
03C0                                                  ADD EAX,EAX                           
35 B71DC104                                           XOR EAX,4C11DB7                       
EB 02                                                 JMP SHORT 0102E23F                    
03C0                                                  ADD EAX,EAX                           
89048D 68B9B002                                       MOV DWORD PTR DS:[ECX*4+2B0B968],EAX  
41                                                    INC ECX                               
81F9 00010000                                         CMP ECX,100                           
0F8C 6FFFFFFF                                         JL 0102E1C2                           
C3                                                    RETN                                  

```

The first pick objectlist.txt.
The names of the containers, without the *.drm. Path type "pc-w\" and others are at the beginning of each function. Names Raw, Mul, and others, in the open form are in bigfile.000
## Post #28
- Username: goldroger
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 03, 2017 3:59 pm
- Post datetime: 2017-06-23T15:48:50+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Hey guys,

I know this thread is a bit old, but I current have a project that is very similar to the looks and feel of LC Tomb of Osiris.

Would it be possible to extract the level meshes and textures from the tiger file? Has anyone tried it?

Any assistance will be greatly appreciated.
## Post #29
- Username: goldroger
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 03, 2017 3:59 pm
- Post datetime: 2017-06-23T18:13:42+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Ekey
>
> DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)

Sorry if this thread is very old, but I really need the DRM Dumper file for LC Tomb of Osiris. Can't find it anywhere..

Thank you
## Post #30
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-06-24T12:20:16+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from goldroger
>
> Ekey wrote:DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)

Sorry if this thread is very old, but I really need the DRM Dumper file for LC Tomb of Osiris. Can't find it anywhere..

Thank you
[http://dropmefiles.com/j7Of2](http://dropmefiles.com/j7Of2)
## Post #31
- Username: goldroger
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 03, 2017 3:59 pm
- Post datetime: 2017-06-24T23:33:27+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Ekey
>
> goldroger wrote:Ekey wrote:DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)

Sorry if this thread is very old, but I really need the DRM Dumper file for LC Tomb of Osiris. Can't find it anywhere..

Thank you
http://dropmefiles.com/j7Of2

Awesome man!
Appreciate the response. Cheers
## Post #32
- Username: PanStasio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 18, 2017 9:22 pm
- Post datetime: 2017-08-18T15:28:51+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from Ekey
>
> goldroger wrote:Ekey wrote:DRM Dumper (0.0.1 [r1]) / Ekey (h4x0r)

Sorry if this thread is very old, but I really need the DRM Dumper file for LC Tomb of Osiris. Can't find it anywhere..

Thank you
http://dropmefiles.com/j7Of2
Can anyone reupload DRM Dumper for Lara Croft and the Temple of Osiris?
## Post #33
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-08-26T07:48:16+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

Does anyone still have the DRM dumper? ><
## Post #34
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-26T22:23:25+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

there is a working link in this thread   
[viewtopic.php?f=10&p=83304#p83304](http://forum.xentax.com/viewtopic.php?f=10&p=83304#p83304)
## Post #35
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-08-27T15:32:31+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from AceWell
>
> there is a working link in this thread   
viewtopic.php?f=10&p=83304#p83304

Unfortunately that one is for a different game and doesn't work with this one. Thank You though!
## Post #36
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2017-09-05T09:13:10+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

DRM Dumper  

```
https://mega.nz/#!X4Q2iRhA!53fLSqJzEPM6Umlv5veh_twnqyAfvBDN4BXTXlvF9mw
```


credits to Ekey (h4x0r)
## Post #37
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-09-05T17:20:09+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

> Reply from T0M099
>
> DRM Dumper  
Code: Select allhttps://mega.nz/#!X4Q2iRhA!53fLSqJzEPM6Umlv5veh_twnqyAfvBDN4BXTXlvF9mw

credits to Ekey (h4x0r)

Thanks so much!!
## Post #38
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2017-11-07T10:33:58+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

I extracted the file bigfileenglish.tiger. In one of the resulting folders there were files with no extension in which the subtitles are, but I do not know how to edit them, is there a way to do this? Help

Unpacked\FFFFFFC1\_Uknown\

Each such file contains one dialog in several languages, the rest is probably unnecessary. Is there anyone who would help me to compress all these files into a tiger file?
## Post #39
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2023-08-16T20:04:44+00:00
- Post Title: Re: Lara Croft and the Temple of Osiris Bigfile.000.tiger

hey gyus possible extract monster models and animations?
