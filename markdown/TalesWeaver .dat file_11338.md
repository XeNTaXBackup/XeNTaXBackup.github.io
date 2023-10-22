## Post #1
- Username: taarna23
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 03, 2010 5:13 am
- Post datetime: 2014-03-21T03:00:30+00:00
- Post Title: TalesWeaver .dat file

Hi there, I'm looking for some help with a file from an asian MMORPG. Specifically, I want to extract from the Japanese version. I've got some information on the file format that is, while dated and from a different version, seems to still have at least some validity. The file itself is a bit large for me to upload at present, but curious people could download the client from [http://www.talesweaver.jp](http://www.talesweaver.jp).

I do know the file is zlib compressed. I also have the following information, translated from a chinese site:

```
0000000A(4b)		value 1, unknown purpose
0000000E(1b)		decode character, used for zlib, 0xB5 for jTW
0000000F(4b)		Pack directory length
00000013            Pack directory, decoded D:\315TWNPACK\TalesWeaverPack
00000030(4b)        value 7, number of subdirectories
00000034(4b)        value 0, unknown

subdirectory 1
00000038(4b)        subdirectory length
0000003C            subdirectory, decoded D:\315TWNPACK\TalesWeaverPack\3DObject
00000062(4b)        total size of files in this subdirectory
00000063			Beginning of block followed by a file...

subdirectories 2 through 7, each with the same format as above

file block format of subdirectory 1
4byte               directory length
                    table of contents, D:\315TWNPACK\TalesWeaverPack\3DObject
4byte               value 0, unknown
4byte               number of files
-	file 1
-	4byte               filename length
-						filename, 0000.KFD
-	4byte               decompressed size (zlib compression)
-	4byte               compressed size
-	4byte               unknown
-	Followed by next file...

```


There used to be tools for extracting the files I am interested in, specifically things to be translated, but these tools are no longer maintained, and the creator refused to release the source. Also, the directories listed will be different for this version. I'm not sure if that affects anything at all.

My own programming skills are too weak for this task (currently I'm learning how to manipulate a bitmap image - not quite up to par), so I am hoping some kind soul will lend a hand. Note that if the game has not changed in the way it runs, extraction is the only thing necessary, not packing. The configuration files can be altered to read from an external directory.
