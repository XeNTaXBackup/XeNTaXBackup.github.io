## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-28T19:38:36+00:00
- Post Title: request a tutorial

i assumed that is not bad , we have a topic with this name here !
so , the masters donate a tutorial around a subject , according to frequency of request !
----------------------------------------------------------------------
#1 how can recognize key of xored files by analyzing an EXE !
#2 some strong methods for recognizing of vertex and faces in the mesh files !
-----------------------------------------------------
realy thanks to all author
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-28T21:37:42+00:00
- Post Title: request a tutorial

I can answer (partially) only to the first question.
if the xor key is composed by only one byte (enough common) the only quick way to recognize it is simply the xoring of a portion of the input file with all the bytes from 1 to 0xff and watching when you see a known string (you can create a tool in 10 seconds for doing it otherwise ask).

while for a xor key longer than 1 byte analyzing the executable could give some results in some cases but this is a job for real-time debugging.
with static analysis (so only with the disassembling) you must have enough luck and knowing where to look (maybe a function called after a ReadFile or after the checking of a specific signature of that file) because exist cases where this is not possible or looks just senseless (for example QuakeLive, luckily I noticed the "strange" portion of code which built the key so in 2 minutes was everything ready but as already said it's ever a matter of luck).
## Post #3
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-28T22:43:39+00:00
- Post Title: request a tutorial

also for xor detection if the file is just xored and not compressed you can see a lot of the same characters all in a row that will be your xor key because it is xoring 00 which will reveal the key.
I will create a tutorial for this I was planning on doing it but I have been lazy.
## Post #4
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-29T10:54:34+00:00
- Post Title: request a tutorial

Along the same lines, repeating characters could reveal the XOR key, as they XOR the value 00. It is also important to look for patterns. Always look for patterns. File info entries in a table (such as filename, offset and size) usually have a repeating pattern. Then remember that filenames in many cases follow the convention "name.extension", and mostly the last three characters come after a dot ('.'), the extension. So if you suspect a piece may be a filename, check the position where you'd expect a dot. (0x2e). then XOR the byte there with 0x2e to get to the XOR key.

Read also my tutorial using the Painkiller XOR encryption:
[http://wiki.xentax.com/index.php/DGTEFF ... encryption](http://wiki.xentax.com/index.php/DGTEFF#A_worked_example:_Painkiller_.2A.pak_encryption)
## Post #5
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-27T08:49:59+00:00
- Post Title: request a tutorial

I'm seaching for a tutorial on howto decompress .zlb files..
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-27T19:03:39+00:00
- Post Title: request a tutorial

are you really looking for a zlib tutorial?
did you look 3 posts down?
[viewtopic.php?f=29&t=3528](http://forum.xentax.com/viewtopic.php?f=29&t=3528)
## Post #7
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-28T09:50:14+00:00
- Post Title: request a tutorial

aww stupid me.   
thanks for the response!
## Post #8
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-13T10:01:39+00:00
- Post Title: request a tutorial

I tried ram cheat , it is a simple tool for finding some of memory adress ...
[http://www.winhex.com/ramcheat.html](http://www.winhex.com/ramcheat.html) , it works wonderfull !
but unfortunately it works in very limited criteria }{
it proves that sharing of memory adress is possible too ? [http://www.winhex.com/cheats.html](http://www.winhex.com/cheats.html)
i hope you learn us how can decipher memory adress in wide range ? and share them as a great aid for other members ...
## Post #9
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-13T10:43:04+00:00
- Post Title: request a tutorial

Does this work different from using Ida Pro or ollyDbg to find out the memory dump, or could you just us those type of toosl instead?
## Post #10
- Username: duoblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 15, 2009 2:14 pm
- Post datetime: 2009-12-21T05:47:27+00:00
- Post Title: request a tutorial

Hello! 

I was wondering if someone could make a tutorial explaining how to use Turfster's Maki tool?  I am really only trying to use it for Assassin's Creed as I would like to use Altair's textures for a Final Fantasy XI mod. I have the plugin for the game and I know what file types to use, but I just don't understand how I get textures out of the files.

Thank you.
## Post #11
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-12-22T02:45:04+00:00
- Post Title: request a tutorial

I would like to request a tutorial on figuring out unknown audio codecs.
## Post #12
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-03-14T11:12:00+00:00
- Post Title: request a tutorial

please someone show us a guideline or tutorial about how can work with functions of DLLs , there a lots of application on this subject ...

also Luigi Auriemma mentioned about a feature that is available in QuickBMS , (personally i need a step by step example for understanding it)

> CallDLL DLLNAME FUNC/OFF CONV RET [ARG1] [ARG2] ... [ARGn]
>
>     this is the command which allows to use plugins inside QuickBMS.
>
>     the idea came from the possibility of using the custom
>
>     decompression/decryption functions (both exported and internals)
>
>     located in executables and dlls avoiding the boring reversing of
>
>     all the functions.
>
>     unfortunately this is not much possible with the functions got from
>
>     executables where are used static variables due to some technical
>
>     reasons (memory addresses that don't match), for example if the
>
>     function uses the memory between 006c0000 and 006d0000 it's highly
>
>     possible that such range of memory is not allocated or is already
>
>     in use because the executable has not been loaded (LoadLibrary) in
>
>     its original address because already occupied.
>
>     obviously there are no problems with the dlls.
>
> 
>
>     arguments:
>
>       DLLNAME   name of the dll or executable where is located the
>
>                 function, example "mylib.dll"
>
>                 QuickBMS can even load raw binary files that contain
>
>                 only the dumped function... very useful
>
>       FUNC/OFF  it can be the name of the function to import in which
>
>                   case it must be exported by the dll/exe
>
>                 or the relative offset where is located the function,
>
>                   remember that the relative offset is NOT the absolute
>
>                   one but it's the offset related to the image base of
>
>                   the exe/dll (so if normally the dll loads at offset
>
>                   10000000 and the function is at 10012345 then the
>
>                   offset is 0x12345)
>
>       CONV      calling convention:
>
>                   stdcall: aka winapi, used by Visual C
>
>                   cdecl: used by almost any other C/C++ compiler
>
>       RET       the variable which will contain the value returned by
>
>                 the function, use "" if there is not return value
>
>       [ARGS]    all the arguments of the function
>
>                 from version 0.3.5 QuickBMS implements also the pointer
>
>                 to arguments when they are preceded by a & or a * like
>
>                 &SIZE, ZSIZE. it works only with numeric variables
>
> 
>
>     examples:
>
>       idstring LZ2K
>
>       get SIZE long
>
>       get ZSIZE long
>
>       log MEMORY_FILE 0xc ZSIZE
>
>       putvarchr MEMORY_FILE2 SIZE 0 # like malloc
>
>       #calldll "TransformersDemo.exe" 0x263c50 cdecl "" MEMORY_FILE MEMORY_FILE2 ZSIZE SIZE    # 00663C50
>
>       calldll "unlzk.dll" "unlz2k" cdecl SIZE MEMORY_FILE MEMORY_FILE2 ZSIZE SIZE
>
>       log "dump.dat" 0 SIZE MEMORY_FILE2

as this tool (GR2 to OBJ) converter , works in this style :
[viewtopic.php?f=16&t=3954](http://forum.xentax.com/viewtopic.php?f=16&t=3954)
i used DLL Export Viewer : for listing of all function :
[http://www.nirsoft.net/utils/dll_export_viewer.html](http://www.nirsoft.net/utils/dll_export_viewer.html)

```
_GrannyCompressContentsOfMemory@12	0x5005c0e0	0x0005c0e0	112 (0x70)	Exported Function	
_GrannyCompressContentsOfReader@20	0x5005c0b0	0x0005c0b0	113 (0x71)	Exported Function	
_GrannyCompressCurve@32	0x5005ac50	0x0005ac50	114 (0x72)	Exported Function	
_GrannyComputeBasisConversion@36	0x5005a240	0x0005a240	115 (0x73)	Exported Function	
_GrannyComputePeriodicLoopLog@12	0x5005d480	0x0005d480	116 (0x74)	Exported Function	
_GrannyComputePeriodicLoopVector@12	0x5005d460	0x0005d460	117 (0x75)	Exported Function	
_GrannyConstructBSplineBuffers@52	0x5005a840	0x0005a840	118 (0x76)	Exported Function	
_GrannyControlIsActive@4	0x5005aea0	0x0005aea0	119 (0x77)	Exported Function	
_GrannyControlIsComplete@4	0x5005ad80	0x0005ad80	120 (0x78)	Exported Function	
_GrannyControlModelsBegin@4	0x500596d0	0x000596d0	121 (0x79)	Exported Function	
_GrannyControlModelsEnd@4	0x500596e0	0x000596e0	122 (0x7a)	Exported Function	
_GrannyControlModelsNext@4	0x5005d6f0	0x0005d6f0	123 (0x7b)	Exported Function	
_GrannyConvertFileInfoToRaw@8	0x5005bd80	0x0005bd80	124 (0x7c)	Exported Function	
_GrannyConvertFileToRaw@8	0x5005bda0	0x0005bda0	125 (0x7d)	Exported Function	
_GrannyConvertIndices@20	0x5005e320	0x0005e320	126 (0x7e)	Exported Function	
_GrannyConvertPixelFormat@32	0x50059ea0	0x00059ea0	127 (0x7f)	Exported Function	
_GrannyConvertSingleObject@16	0x5005b980	0x0005b980	128 (0x80)	Exported Function	
_GrannyConvertTree@12	0x5005b9c0	0x0005b9c0	129 (0x81)	Exported Function	
_GrannyConvertTreeInPlace@16	0x5005ba00	0x0005ba00	130 (0x82)	Exported Function	
_GrannyConvertVertexLayouts@20	0x5005e500	0x0005e500	131 (0x83)	Exported Function	
_GrannyCopyLocalPose@8	0x5005c860	0x0005c860	136 (0x88)	Exported Function	
_GrannyCopyLODErrorValuesFromAllAnimations@8	0x5005a190	0x0005a190	132 (0x84)	Exported Function	
_GrannyCopyLODErrorValuesFromAnimation@8	0x5005a170	0x0005a170	133 (0x85)	Exported Function	
_GrannyCopyLODErrorValuesToAllAnimations@12	0x5005a150	0x0005a150	134 (0x86)	Exported Function	
_GrannyCopyLODErrorValuesToAnimation@12	0x5005a130	0x0005a130	135 (0x87)	Exported Function	
_GrannyCopyMeshIndices@12	0x5005ce50	0x0005ce50	137 (0x89)	Exported Function	
_GrannyCopyMeshMorphVertices@16	0x5005cdb0	0x0005cdb0	138 (0x8a)	Exported Function	
_GrannyCopyMeshVertices@12	0x5005cd90	0x0005cd90	139 (0x8b)	Exported Function	
_GrannyCopyTextureImage@32	0x5005d980	0x0005d980	140 (0x8c)	Exported Function	
_GrannyCopyTrackMask@4	0x5005e1c0	0x0005e1c0	141 (0x8d)	Exported Function	
_GrannyCreateBlendDagNodeAnimationBlend@8	0x5005b350	0x0005b350	142 (0x8e)	Exported Function	
_GrannyCreateBlendDagNodeCallback@16	0x5005b390	0x0005b390	143 (0x8f)	Exported Function	
_GrannyCreateBlendDagNodeCrossfade@28	0x5005b3b0	0x0005b3b0	144 (0x90)	Exported Function	
_GrannyCreateBlendDagNodeLocalPose@8	0x5005b370	0x0005b370	145 (0x91)	Exported Function	
_GrannyCreateBlendDagNodeWeightedBlend@16	0x5005b3e0	0x0005b3e0	146 (0x92)	Exported Function	
_GrannyCreateBlendDagNodeWeightedBlendChildren@24	0x5005b890	0x0005b890	147 (0x93)	Exported Function	
_GrannyCreateControl@8	0x5005ac90	0x0005ac90	148 (0x94)	Exported Function	
_GrannyCreateDagPoseCache@8	0x5005b720	0x0005b720	149 (0x95)	Exported Function	
_GrannyCreateMemoryFileReader@20	0x5005cc90	0x0005cc90	150 (0x96)	Exported Function	
_GrannyCreateMemoryFileWriter@12	0x5005ccc0	0x0005ccc0	151 (0x97)	Exported Function	
_GrannyCreatePlatformFileReader@12	0x5005c250	0x0005c250	152 (0x98)	Exported Function	
_GrannyCreatePlatformFileWriter@16	0x5005c2f0	0x0005c2f0	153 (0x99)	Exported Function	
_GrannyCurveConvertToDaK32fC32f@8	0x50059c60	0x00059c60	155 (0x9b)	Exported Function	
_GrannyCurveConvertToDaK32fC32fInPlace@12	0x50059c90	0x00059c90	156 (0x9c)	Exported Function	
_GrannyCurveExtractKnotValue@16	0x50059ce0	0x00059ce0	177 (0xb1)	Exported Function	
_GrannyCurveExtractKnotValues@24	0x50059d00	0x00059d00	178 (0xb2)	Exported Function	
_GrannyCurveFindCloseKnot@12	0x50059db0	0x00059db0	179 (0xb3)	Exported Function	
_GrannyCurveFindKnot@8	0x50059d90	0x00059d90	180 (0xb4)	Exported Function	
_GrannyCurveFormatIsInitializedCorrectly@4	0x50059a90	0x00059a90	181 (0xb5)	Exported Function	
_GrannyCurveGetContentsOfDaK32fC32f@4	0x50059c50	0x00059c50	182 (0xb6)	Exported Function	
_GrannyCurveGetDataTypeDefinition@4	0x5005e770	0x0005e770	183 (0xb7)	Exported Function	
_GrannyCurveGetDegree@4	0x50059b00	0x00059b00	184 (0xb8)	Exported Function	
_GrannyCurveGetDimension@4	0x50059af0	0x00059af0	185 (0xb9)	Exported Function	
_GrannyCurveGetKnotCount@4	0x50059ae0	0x00059ae0	186 (0xba)	Exported Function	
_GrannyCurveGetSize@4	0x50059dd0	0x00059dd0	187 (0xbb)	Exported Function	
_GrannyCurveInitializeFormat@4	0x50059a80	0x00059a80	194 (0xc2)	Exported Function	
_GrannyCurveIsConstantNotIdentity@4	0x50059ad0	0x00059ad0	195 (0xc3)	Exported Function	
_GrannyCurveIsConstantOrIdentity@4	0x50059ac0	0x00059ac0	196 (0xc4)	Exported Function	
_GrannyCurveIsIdentity@4	0x50059ab0	0x00059ab0	197 (0xc5)	Exported Function	
_GrannyCurveIsKeyframed@4	0x50059aa0	0x00059aa0	198 (0xc6)	Exported Function	
_GrannyCurveIsReducible@24	0x5005dd60	0x0005dd60	199 (0xc7)	Exported Function	
_GrannyCurveIsTypeDaK32fC32f@4	0x50059c40	0x00059c40	200 (0xc8)	Exported Function	
_GrannyCurveMakeStaticDaK32fC32f@28	0x50059cb0	0x00059cb0	201 (0xc9)	Exported Function	
_GrannyCurveScaleOffsetSwizzle@20	0x50059d60	0x00059d60	202 (0xca)	Exported Function	
_GrannyCurveSetAllKnotValues@20	0x50059d30	0x00059d30	203 (0xcb)	Exported Function	
_GrannyDataTypeBeginsWith@8	0x500595f0	0x000595f0	204 (0xcc)	Exported Function	
_GrannyDataTypesAreEqual@8	0x50059590	0x00059590	205 (0xcd)	Exported Function	
_GrannyDataTypesAreEqualWithNameCallback@12	0x500595d0	0x000595d0	206 (0xce)	Exported Function	
_GrannyDataTypesAreEqualWithNames@8	0x500595b0	0x000595b0	207 (0xcf)	Exported Function	
_GrannyDeallocateAllFixed@4	0x5005c3c0	0x0005c3c0	208 (0xd0)	Exported Function	
_GrannyDeallocateBSplineSolver@4	0x5005a950	0x0005a950	209 (0xd1)	Exported Function	
_GrannyDeallocateFixed@8	0x5005c3a0	0x0005c3a0	210 (0xd2)	Exported Function	
_GrannyDecodeGRNReference@8	0x5005c1c0	0x0005c1c0	211 (0xd3)	Exported Function	
_GrannyDecompressData@32	0x5005bff0	0x0005bff0	212 (0xd4)	Exported Function	
_GrannyDecompressDataChunk@24	0x5005c030	0x0005c030	213 (0xd5)	Exported Function	

```


but it is really necessary to someone show us how can invoke these functions , perhaps in a standard programming language like turbo c++ under dos , so much thanks if you write a tutorial about it ?
## Post #13
- Username: Abominog
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 14, 2010 6:38 pm
- Post datetime: 2010-06-14T11:54:22+00:00
- Post Title: request a tutorial

Hello everyone

1st - Xentax on the whole is an excellent resource and thanks to everyone involved   

Being a total noob in everything Xentax related I would like to ask if chrrox is ever thinking of making more tutorials on this subject as I've found these very easy to understand and informative especially the format that [viewtopic.php?f=29&t=3545](http://forum.xentax.com/viewtopic.php?f=29&t=3545) was written in (in showing the code placed for a script after each step).
I have lots to learn in all areas but hope one day I might have something to contribute in the form of scripts that may be of use - I've played around with hex editing for some time but mostly blindfolded to what I'm doing until I read those Tutorials.

Just to give you an idea of how good (sorry not sucking up here) they are - I looked at the script by aluigi for Dungeon Keeper 2 as I have this game - so installed the game and tried to follow the script with what I was looking at

```
idstring "DWFB"
get VER long
goto 0x48
get FILES long
get NAMEOFF long
get NAMESZ long
get DUMMY long

```


```
00000027 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 81 00 00 00 B1 A4 .......................................
0000004E 2D 00 CD 06 00 00 00 00 00 00 F5 08 00 00 B1 A4 2D 00 0C 00 00 00 80 14 00 00 37 70 03 00 00 00 00 00 00 00 00 00 00 -...............-.........7p...........
00000075 00 00 00 00 00 00 00 00 00 00 00 67 08 00 00 BD A4 2D 00 0C 00 00 00 B7 84 03 00 31 47 0A 00 00 00 00 00 00 00 00 00 ...........g.....-.........1G..........
0000009C 00 00 00 00 00 00 00 00 00 00 00 00 71 11 00 00 C9 A4 2D 00 14 00 00 00 E8 CB 0D 00 68 2A 00 00 00 00 00 00 00 00 00 ............q.....-.........h*.........
000000C3 00 00 00 00 00 00 00 00 00 00 00 00 00 1C 17 00 00 DD A4 2D 00 0C 00 00 00 50 F6 0D 00 B0 29 00 00 00 00 00 00 00 00 ...................-.....P....)........

```


and found I could follow some of the script of what I was looking at - when before it was just over my head (what the hell am i looking at) to OH! crap I can read this (to a point    ) - like how many files in archive - where the names are - where the file starts and ends in archive etc.

So basically is there any new Tutorials in the works for game archives like chrrox has written.
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-14T13:33:02+00:00
- Post Title: request a tutorial

[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF) You read that one?
## Post #15
- Username: Abominog
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 14, 2010 6:38 pm
- Post datetime: 2010-06-14T13:56:38+00:00
- Post Title: request a tutorial

off and on yes - getting information overload here
## Post #16
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-04T22:58:46+00:00
- Post Title: Re: request a tutorial

Hi, everyone i found this tool called GameAssassin [http://www.gameassassin.com/](http://www.gameassassin.com/), It's Chinese but language can switch to English too. That tool can capture Model, Bone and Animation from 3D games, both OpenGL and 3DX.

The problem is every time i try to work with it, doesn't seem to work   

If anyone knows how to work with it, please help me... i'm desperate...    

Thanks
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-04T22:59:49+00:00
- Post Title: Re: request a tutorial

you need to buy that program for it to work and i have never seen the bone capture work.
## Post #18
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-05T00:50:05+00:00
- Post Title: Re: request a tutorial

I use cracked from [http://forum.cgpersia.com/f13/gameassassin-2708/](http://forum.cgpersia.com/f13/gameassassin-2708/), it also doesn't work.
## Post #19
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-08-23T16:54:44+00:00
- Post Title: Re: request a tutorial

There is an obvious lack of a tutorial about how can figure out Encryption methods in archives ?

so much thanks if you attention to this subject
regards
## Post #20
- Username: NMCM
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Apr 15, 2009 2:02 pm
- Post datetime: 2010-10-05T21:04:10+00:00
- Post Title: Re: request a tutorial

I'm requesting a tutorial on how to extract .bpe files from WWF. Smackdown 2 Know your role PAC files. Here's a pac file from the game[http://www.speedyshare.com/files/24563250/ED1H.rar](http://www.speedyshare.com/files/24563250/ED1H.rar)
## Post #21
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2010-12-26T01:07:57+00:00
- Post Title: Re: request a tutorial

I'm very confused about the whole concept of LZ compression, there are numerous guides including here that go into a fair amount of detail especially with the theory, but I would like to at least have a practical example to look at.
[http://wiki.xentax.com/index.php/LZSS](http://wiki.xentax.com/index.php/LZSS)

There's pseudocode but no example input/output data.
## Post #22
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-02-19T02:39:14+00:00
- Post Title: Re: request a tutorial

my sound sill but I have a game that doesn't store sprites in an archive (its for the sega saturn) how might I convert them to a viewable format
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-19T09:27:01+00:00
- Post Title: Re: request a tutorial

> Reply from viperzerofsx
>
> my sound sill but I have a game that doesn't store sprites in an archive (its for the sega saturn) how might I convert them to a viewable format

That is a very general type of question.Upload examples.
## Post #24
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-02-19T22:40:17+00:00
- Post Title: Re: request a tutorial

> Reply from Mr.Mouse
>
> viperzerofsx wrote:my sound sill but I have a game that doesn't store sprites in an archive (its for the sega saturn) how might I convert them to a viewable format

That is a very general type of question.Upload examples.

this would be one
[AGUM_C.rar](https://xentaxbackup.github.io/file/3946_AGUM_C.rar)
