## Post #1
- Username: RVR72GV
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 08, 2011 5:16 pm
- Post datetime: 2011-11-09T01:57:39+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

Doesn't seem to be similar case as [Ashes Cricket 2009](http://forum.xentax.com/viewtopic.php?f=10&t=4268&hilit=.w32).

I've tried using Ashes 2009 .bms but no luck (it says 0 files found)

Anybody can help me?
## Post #2
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-11-11T11:25:22+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

Every file in archive may have 1 or 2 streams - 2nd stream is texture or texturepack.
An empty .stream2 file will be created, even if there is no 2nd stream, sorry for that.
Use this script on chunks.toc.w32

```
Open FDSE "chunks.big.w32" 1
Open FDSE "chunks.toc.names.w32" 2
ComType unzip_dynamic
Get FILES long
Get DUMMY longlong
Get DUMMY long 2
Math NAMES_BASE_OFFSET = FILES
Math NAMES_BASE_OFFSET *= 12
Math NAMES_BASE_OFFSET += 4
Math FN_OFFSET1 = NAMES_BASE_OFFSET
For I = 0 < FILES
 Get FILEID long
 Get OFFSET longlong
 Get SIZE1 long
 Get ZSIZE1 long
 Get SIZE2 long
 Get ZSIZE2 long
 Math OFFSET *= 0x10
 
 Get FN_OFFSET2 long 2
 Math FN_OFFSET2 += NAMES_BASE_OFFSET
 Math FN_OFFSET2 -= FN_OFFSET1
 Get HDR_SIZE1 long 2
 Get HDR_SIZE2 long 2
 SavePos FN_POS 2
 GoTo FN_OFFSET1 2
 GetDString CHUNK_NAME FN_OFFSET2 2
 Math FN_OFFSET1 += FN_OFFSET2
 GoTo FN_POS 2

 String NAME p= "%s.stream1" CHUNK_NAME
 If ZSIZE1 == 0
  Log NAME OFFSET SIZE1 1
  Math OFFSET += SIZE1
 Else
  GoTo OFFSET 1
  Get CHUNKS long 1
  If CHUNKS != 1
  For J = 2 <= CHUNKS
   Get CHUNK_SIZE long 1
   Math ZSIZE1 += CHUNK_SIZE
  Next J
  EndIf
  Math HDR_SIZE1 -= ZSIZE1
  Math HDR_SIZE1 n HDR_SIZE1
  Math BLOCK_OFFSET = HDR_SIZE1
  Math END = OFFSET
  Math END += ZSIZE1
  CallFunction UnpackChunk
  #Log NAME OFFSET ZSIZE1 1
  Log NAME 0 SIZE1 MEMORY_FILE
  Math OFFSET += ZSIZE1
 EndIf

 String NAME p= "%s.stream2" CHUNK_NAME
 If ZSIZE2 == 0
  Log NAME OFFSET SIZE2 1
 Else
  GoTo OFFSET 1
  Get CHUNKS long 1
  If CHUNKS != 1
  For J = 2 <= CHUNKS
   Get CHUNK_SIZE long 1
   Math ZSIZE2 += CHUNK_SIZE
  Next J
  EndIf
  Math HDR_SIZE2 -= ZSIZE2
  Math HDR_SIZE2 n HDR_SIZE2
  Math BLOCK_OFFSET = HDR_SIZE2
  Math END = OFFSET
  Math END += ZSIZE2
  CallFunction UnpackChunk
  #Log NAME OFFSET ZSIZE2 1
  Log NAME 0 SIZE2 MEMORY_FILE
 EndIf
Next I

################################
StartFunction UnpackChunk
 Log MEMORY_FILE 0 0
 Append
 GoTo OFFSET 1
 Math BLOCK_OFFSET += OFFSET
 Math CHUNKS *= 4
 GoTo CHUNKS 1 SEEK_CUR
 Do
  Get BLOCK_SIZE short 1
  CLog MEMORY_FILE BLOCK_OFFSET BLOCK_SIZE BLOCK_SIZE 1
  Math BLOCK_OFFSET += BLOCK_SIZE
  Math BLOCK_OFFSET x= 0x10
 While BLOCK_OFFSET < END
 Append
EndFunction UnpackChunk
################################
```
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-15T04:13:24+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

Don't worked.

```
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted


Note that if both the scripts and your files are correct then it's possible
that the script needs a newer version of QuickBMS, in which case download it:

  http://aluigi.org/quickbms
```

Any idea?[/b]
## Post #4
- Username: RVR72GV
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 08, 2011 5:16 pm
- Post datetime: 2011-11-17T12:32:29+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

It works for chunks.toc.w32 and NOT chunks.toc.names.w32 though
## Post #5
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-11-18T01:58:19+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

> Reply from Axsis
>
> Every file in archive may have 1 or 2 streams - 2nd stream is texture or texturepack.
An empty .stream2 file will be created, even if there is no 2nd stream, sorry for that.
Use this script on chunks.toc.w32
People just don't want to read, they want to EXTRACT! NOW!
## Post #6
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-11-18T03:47:13+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

Thanks for the effort Axsis!
I can confirm the script works 100% with chunks.toc.w32 using QuickBMS v0.5.3a. It reports 19754 files found. My problem is I don't know what to do with the resulting .w32.chunk.stream1 and .w32.chunk.stream2 files. Is there a program to handle those or are we waiting for one to be made?
## Post #7
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-11-18T04:34:48+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

stream1 files are maps, models, sounds, music, scripts, etc
stream2 files are textures and texturepacks.
maps and models are in unknown (for me) format, music and sounds in fsb;
textures and packs in dds; for texturepack files stream1 file contains info about textures, and stream2 contains textures itself.
## Post #8
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-18T16:41:52+00:00
- Post Title: Janes Advanced Strike Fighters .big.w32 and .toc.w32 Files

> Reply from Axsis
>
> Axsis wrote:Every file in archive may have 1 or 2 streams - 2nd stream is texture or texturepack.
An empty .stream2 file will be created, even if there is no 2nd stream, sorry for that.
Use this script on chunks.toc.w32

People just don't want to read, they want to EXTRACT! NOW!
I can read very well
I used the script in the file chunks.toc.w32
My error was to direct the extraction to a different folder. Now I could extract the package. Thanks
