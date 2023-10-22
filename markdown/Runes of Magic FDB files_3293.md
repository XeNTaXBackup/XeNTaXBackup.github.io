## Post #1
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2009-01-12T18:30:35+00:00
- Post Title: Runes of Magic FDB files

The file structure description is located here: [http://wiki.xentax.com/index.php?title= ... _Magic_FDB](http://wiki.xentax.com/index.php?title=Runes_of_Magic_FDB)

FDB Samples: [http://uploaded.to/?id=pic33i](http://uploaded.to/?id=pic33i)
data.fdb - thats the full file
interface.001 - this is the first part of the interface.fdb file (it was split to 10MB peaces)
interface.014 - this is the 14-th part of the interface.fdb file (it was split to 10MB peaces)
interface.015 - this is the last part of the interface.fdb file (it contains the wast 417Kb of the file)

PNG Sample: [http://uploaded.to/file/afjoiv](http://uploaded.to/file/afjoiv)

Runes of Magic is a new Free2Play MMORPG game I'd like to try to mod.
Games HomePage - [http://www.runesofmagic.com/](http://www.runesofmagic.com/)

P.S. I'd like to give my thanks to Seipheroth for his help figuring the file structure. As well as everyone else who attempts to help me in the future.
P.S.S. Also I'll appreciate any help with the header rebuilding/removal for the models and textures contained inside the game archives.
P.S.S.S. Any recommendations about useful software/tools/guides or advices are welcomed since this is my second attempt at reversing GA and I consider myself a noob.
## Post #2
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2009-01-18T14:14:49+00:00
- Post Title: Runes of Magic FDB files

I'm stuck with the script, it can extract the Zlib compressed content but for some reason it can't uncompress it.
Also I need help figuring out what is the 8byte variable type for the scripts if any, and what is the file time format used in the GA?
As well as any way of rebuilding the texture files headers.

```
# ComType ZLib1 ;
Get ID Long 0 ;
# FNum - Files number
Get FNum Long 0 ;
# Processing index loop
For T = 1 To FNum ;
# FType1 - File Type
Get FType1 Long 0 ;
# FDateX - File Date
Get FDate1 Long 0 ;
Get FDate2 Long 0 ;
# FBPos - File Block Position
Get FBPos Long 0 ;
# EO - Remember Position
SavePos EO 0 ;
# Jump to File Block Position
GoTo FBPos 0 ;
# FBSize - File Block Size
Get FBSize Long 0 ;
# FType2 - File Type
Get FType2 Long 0 ;
# UN1 - Unknown Value N1
Get UN1 Long 0 ;
# UFS - Uncompressed File Size
SavePos UFSO 0 ;
Get UFS Long 0 ;
# CFS - Compressed File Size
SavePos CFSO 0 ;
Get CFS Long 0 ;
# FDateX - File Date
Get FDate3 Long 0 ;
Get FDate4 Long 0 ;
# FNS - File Name Size
Get FNS Long 0 ;
# Get File Path/Name String
GetDString FName FNS 0 ;
# ZLB - Save Start Position of ZLib Data
SavePos ZLB 0 ;
# FType2 ver check (skip header block, replace ZLB with CFS for extraction with header)
If FType2 = 2 ;
Math ZLB += 16 ;
EndIf ;
# Extract
Log FName ZLB CFS 0 0 ;
# CLog FName ZLB CFS 0 CFSO UFS UFSO ;
# Go Back to index entry for next file
GoTo EO 0 ;
Next T ;

```
## Post #3
- Username: Seipheroth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 15, 2009 8:16 pm
- Post datetime: 2009-01-20T10:38:35+00:00
- Post Title: Runes of Magic FDB files

The filetime's are windows FILETIME structures, which according to MSDN are 64-bit values representing the number of 100-nanosecond intervals since January 1, 1601 (UTC)
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-21T13:07:35+00:00
- Post Title: Runes of Magic FDB files

> Reply from PCto
>
> I'm stuck with the script, it can extract the Zlib compressed content but for some reason it can't uncompress it.
Also I need help figuring out what is the 8byte variable type for the scripts if any, and what is the file time format used in the GA?
As well as any way of rebuilding the texture files headers.

The current script version does not support 8byte variables unfortunately. Rahly is working on a new version and script, that will be a vast improvement. 

Does the script extract zlibbed files correctly? Does MexCom report an error when uncompressing ?
Can you show me the debug.log (ctrl+L) when it does? 

I will check the script, which GRA did you try it on?
## Post #5
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2009-01-21T16:56:53+00:00
- Post Title: Runes of Magic FDB files

No, the script can extract the ZLib compressed content but it can't extract and uncompress it regardless of the GRA I try it on so I'm using the data.fdb because it is the smallest and have text files.
GameExtractor v2 is able to preview the files correctly but not to extract them (even with the version that is able to extract the compressed content), and MexCom gives "Error while decompressing" as soon as you click on a file. I'm using 32bit Vista if it matters.

```
MEX Open list file D:\Programs\MultiEx Commander\data\multiex.lst
MEX Number of list entries 18
MEX Preview file failed

```


P.S. I don't think it's a good idea to search for the GameExtractor files only in the default location could you put a field in witch we can specify the path or a config file for it? Sorry if there is already such an option. Also is there an script checker/writer I can use or should I continue using notepad?
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-21T18:15:39+00:00
- Post Title: Runes of Magic FDB files

Yeah, there is such a Scriptor, but I have to fix it. Also, I agree with you about GE, this is on my to do list (which is long    )
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-22T08:15:06+00:00
- Post Title: Runes of Magic FDB files

You can also check out the mex3.log (see Options), please do attach that here as well. It shows debugging info about the script processing.
## Post #8
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2009-01-22T17:06:34+00:00
- Post Title: Runes of Magic FDB files

It doesn't help. I've already checked it, the index is build correctly.
[mex3.zip](https://xentaxbackup.github.io/file/1836_mex3.zip)
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-22T19:16:23+00:00
- Post Title: Runes of Magic FDB files

Okay, I noticed that other zlibbed files are correctly decompressed by MexCom. I used another tool and that could also not decompress the extracted files. Did you use a tool to decompress them before? If so, which?
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-22T21:08:31+00:00
- Post Title: Runes of Magic FDB files

UPDATE: It turns out zlib gives a continuable Buffer Error. It decompresses, but gives an error while inflating (at the end of the file). I have fixed MexCom to ignore this error, but have to do some more work on MexCom before I can release it. 

I have fixed MexBinderPlus that contains the Scriptor. 

(attached).
[MexBinderPlus.zip](https://xentaxbackup.github.io/file/1837_MexBinderPlus.zip)
## Post #11
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2009-01-23T16:43:32+00:00
- Post Title: Runes of Magic FDB files

Yes, I'm attaching it here.
I think i found it on a thread somewhere in here.
[zlibc.rar](https://xentaxbackup.github.io/file/1838_zlibc.rar)
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-23T18:55:47+00:00
- Post Title: Runes of Magic FDB files

Yes, that also reports the Buffer Error (-5).
