## Post #1
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T22:18:55+00:00
- Post Title: Unknown Compression Method

Hi guys,

Someone sent me an archive to look at from the game Black Magic. The archive format it easy enough, but the files are compressed using an unknown algorithm. However, I was hoping someone would know the method, as the compressed files (not the archive itself) all seem to have a 2-byte header with values (09,0B) in hex, or (9,11) in decimal.

I thought that it may simply have been a PKZip file that had been encrypted somehow, but it doesn't seem to be anything nice if this is the case.

If anyone could shed some light on this, it'd be great. I have attached a zip with some sample compressed files in it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)

PS - I have tried to run it through some generic algorithms like gzip, zlib, LZSS, LZW, etc but didn't have any success
[comp.zip](https://xentaxbackup.github.io/file/552_comp.zip)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-04T00:02:24+00:00
- Post Title: Unknown Compression Method

Is there a possibility that you could post the exe file for this game?
maybe the answer lies in there.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T01:45:47+00:00
- Post Title: Unknown Compression Method

Sorry no, I don't have access to it - someone send me the archive - otherwise I would have given it a go.

Oh, and the name of the game was wrong - it is BLOOD MAGIC.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-04T03:04:35+00:00
- Post Title: Unknown Compression Method

hehe, i thought that was wrong, unless its an Activision game, they would be sued for that game name
## Post #5
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2006-01-04T11:04:01+00:00
- Post Title: Unknown Compression Method

I upload exe file from BLOOD MAGIC  on [http://s37.yousendit.com/d.aspx?id=30YG ... H9IA7ES59K](http://s37.yousendit.com/d.aspx?id=30YGGLIZ7I93N2I6H9IA7ES59K)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T11:38:10+00:00
- Post Title: Unknown Compression Method

Some listed functions and dependancies below: (the first one seems interesting and also the LuaStateMachine. Lua is a scripting language. 

Check out this: [http://lua-users.org/wiki/LuaModuleLzo](http://lua-users.org/wiki/LuaModuleLzo)

LZO compression could be the one we're after, but I'm sure there are more methods for Lua. I think LZO is mostly used for text. 

Check this: [http://luaforge.net/softwaremap/trove_l ... orm_cat=42](http://luaforge.net/softwaremap/trove_list.php?form_cat=42)

```
6 (0x0006)
7 (0x0007)
?CreateGlobalVariable@LuaStateMachine_c@@QAEXPBDH@Z
?CreateGlobalVariable@LuaStateMachine_c@@QAEXPBDM@Z
10 (0x000A)
11 (0x000B)
?DeterminePlayerSpawnplace@ServerWorld_c@@QAE_NPAVrpgCharacter_c@@@Z
13 (0x000D)
14 (0x000E)
15 (0x000F)
?LandRegionInit@@YAXXZ
17 (0x0011)
18 (0x0012)
?MoveToMap@Game_c@@IAE_NABVFileName_c@@ABV?$String_T@$0BAA@@@@Z
20 (0x0014)
21 (0x0015)
?RenderInit@@YA_NXZ
23 (0x0017)
24 (0x0018)
25 (0x0019)
26 (0x001A)
?SendCharacterInfo@ServerWorld_c@@IBEXHPAVrpgCharacter_c@@@Z
?SendItemInfo@ServerWorld_c@@QBEXHPAVrpgItem_c@@_NHHW4ItemDropType_e@@@Z
?Serialize@rpgCharacter_c@@QAEXAAVSerializeable_c@@@Z
30 (0x001E)
?SinCosTableInit@@YAXXZ
32 (0x0020)
?WerksWaterInit@@YAXXZ

```


The dependancies:

```
AVIFIL32.DLL
BINKW32.DLL
BLOODMAGIC.EXE
COMCTL32.DLL
D3D8THK.DLL
D3D9.DLL
D3DX9_26.DLL
DINPUT8.DLL
GDI32.DLL
KERNEL32.DLL
MSACM32.DLL
MSVCRT.DLL
MSVFW32.DLL
NTDLL.DLL
OLE32.DLL
OLEAUT32.DLL
PROTECT.DLL
RPCRT4.DLL
SHELL32.DLL
SHLWAPI.DLL
USER32.DLL
VERSION.DLL
WINMM.DLL
WS2HELP.DLL
WS2_32.DLL
WSOCK32.DLL

```
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T12:00:27+00:00
- Post Title: Unknown Compression Method

Ah yes, I've heard of LUA and know kinda what its all about - never seen any compressed LUA files though.

Thanks, I will see if I can find some LZO decompressors.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T12:26:57+00:00
- Post Title: Unknown Compression Method

Can we also see the archive in total?
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T12:42:03+00:00
- Post Title: Unknown Compression Method

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-04T14:51:54+00:00
- Post Title: Unknown Compression Method

The exefile is protected with starforce. is it possible
that the datafiles is protected with this too?
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T21:34:21+00:00
- Post Title: Unknown Compression Method

I guess it would be possible, but not probable. In all the starforce games I've encountered, either the archive is totally protected, or it has no protection at all. I don't think that they would protect the individual files in the archive (is that even possible using starforce) ?

Nice possibility though, good thinking - I'd be interested to see if you were correct or not.

Oh, not that I think of it, i don't think this would be the issue - the files are compressed, not encrypted. I don't think starforce does compression??

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #12
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-01-04T22:11:27+00:00
- Post Title: Unknown Compression Method

Hello in regards to LZO compression, I've seen it compress many things in game before. Look at Fable tons of LZO compressed chunks. With that the compression was noticeable by the tail of the compressed data. I imagine there are probably differences from different type. The only thing I noticed was 09 0B  at start of each file. The .wavs were initially the same but the dds the next two bytes changed.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-05T20:40:32+00:00
- Post Title: Unknown Compression Method

For help on LZO, try to use minilzo (available on the same website):

        len = lzo1x_decompress_safe(in, len, out, outsz, LZO1X_MEM_DECOMPRESS);

where in is the buffer containing  the compressed data, len is the lenght of this data, out is the output buffer which will contain the decompressed data and outsz is its max size.
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-05T22:25:50+00:00
- Post Title: Unknown Compression Method

Thanks for that. Yeah I tried the LZO decompression but it didn't decompress - complained that the headers of the archive were not correct 

Shame - cause now we are back to square one. Never mind.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
