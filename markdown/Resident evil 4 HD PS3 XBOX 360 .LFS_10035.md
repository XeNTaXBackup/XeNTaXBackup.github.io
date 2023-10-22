## Post #1
- Username: IngPereira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2011 8:55 am
- Post datetime: 2013-01-12T15:56:07+00:00
- Post Title: Resident evil 4 HD PS3 XBOX 360 .LFS

First i'm gonna say hello to all this great modding community i search here long time ago but now i come because there is something that we can made with a RE game series.

Well people i and many other people have a problem when we want to edit some files of RE4 HD (PS3 or X360) (like .esl for scripts of stages, omake.esl for example)

This because in the HD versions they use the new file archive .lfs and they added a .crc check so they make the file omake.esl now omake.esl.lfs.crc, i have reversed the EBOOT (Executable ps3) so i now that .crc is not a File system or file extension because if you open omake01.esl.lfs.crc you can see the file with (LFS 'ZLDR' HEADER) so the .crc is just an extension to force a flag check of the file with .crc algorithms.

I uploaded three files of the game for example:

Omake01.esl.lfs.crc [http://www.mediafire.com/?2zanpyewyz7myai](http://www.mediafire.com/?2zanpyewyz7myai)

config.txt.crc (Totally a .txt file without any compresion or anything, just debug text) [http://www.mediafire.com/?tpuaa8cg58286sh](http://www.mediafire.com/?tpuaa8cg58286sh)

f55a.tpl.crc (Texture files for the game) [http://www.mediafire.com/?n5nkb56j5evofo1](http://www.mediafire.com/?n5nkb56j5evofo1)

Other sample .lfs emleon00.esl.lfs.crc [http://www.mediafire.com/download.php?436tr7zor7ia7ul](http://www.mediafire.com/download.php?436tr7zor7ia7ul).

sample .lfs save_s.dat.lfs.crc  [http://www.mediafire.com/?mfq5emn5pamtuhm](http://www.mediafire.com/?mfq5emn5pamtuhm)

You can see that .crc is not an File System or compression file, is just an extension (In the eboot ps3 executable is most like a FLAG to check .CRC) like you see (because if you open config.txt.crc you can open it with Notepad even because its just text).

I have my patch to disable CRC32 CHECKS on this game ready but first we gonna need to do something with these .LFS files.

So i want to deal with the REAL extension there on many files and is .LFS.

LFS have something with LZMA compression system and in the exec file you can see strings like:

edgeLzmaTaskSet
[lfs] Decompression offset error.
[lfs] Critical error.
edgeLzmaInflateRawData error

So it must be some sort of LZMA file the header like you see in the samples is 'ZLDR', i'm doing research in the game but i need help of more people with more knowledge.

In my Debugger i see the Game when load a .LFS file always check first header of file loaded and compare it to 'ZLDR' header and if is invalid (NOT EQUAL TO 'ZLDR') return this message "File Access Error: 1"

The game runs his own taskset to uncompress every .LFS file edgeLzmaTaskSet

For now: .LFS File Structure. I am reversing a lot xD
.LFS RE4 header:
0x0 size 4 bytes > magic 'ZLDR'
0x4 size 4 bytes > unknown
0x8 size 4 bytes > string 'segs'
0xC size 1 byte  > kDecompressionType (Always '1' in these .LFS format RE4 HD)
'1' = kDecompressionType_EdgeLzma
0xD size 1 byte  > File Version num (Commonly '5' in these .LFS format RE4 HD game)
0xE size 2 bytes > Number of compressed blocks.
0x10 size 4 bytes > Size of uncompressed archive
0x1C size 4 bytes > 'ZLDR' Header size
('ZLDR' Header size - 1) + 0x8 size 5 bytes > LZMA PROPERTIES (Example '5d''00''00''01''00')
The game use a dictionary size of 0x10000

UPDATE: I have dumped now a file from RAM Memory on PS3 and is save_s.dat unpacked from save_s.dat.lfs and i upload there: 

[http://www.mediafire.com/?4xdzrb2a1l4a2ie](http://www.mediafire.com/?4xdzrb2a1l4a2ie)

Like you can see the size is OK if we know the header of the .lfs and the compressed save_s.dat.lfs file was 186kb now uncompressed is 564kb.

Now searching.

Thanks for any help and sorry because my language is not perfect.
## Post #2
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-03-08T22:14:21+00:00
- Post Title: Resident evil 4 HD PS3 XBOX 360 .LFS

Resident Evil 4 HD got released on PC recently and it's based on the xbox 360 port. Almost everything is compressed with LFS format and the format seems very similar.

I looked at one file from both PC and 360 (HomeBtn_Se.bin.lfs), and here's my notes:
The PC and XBox 360 files are very similar. The only difference I see is that most of the header has different endian.

The first few values of the header is straightforward:
0x0 size 4 bytes > magic
0x4 size 4 bytes > unknown (always the same)
0x8 size 4 bytes > uncompressedSize
0xC size 4 bytes > compressedSize

After the above header there's an array of 13 DWORDs. I don't know what they are for, maybe sizes of various chunks in compressed data? The array is differently sized in other files, based on the size of the compressed data. After that there's 20 bytes of data (WORDs?), which are big endian on both xbox 360 and PC. After that is the actual compressed data. The size of it is slightly larger than the compressedSize value in the header, I suspect there might be some dummy bytes at the very end of the file as there's just a bunch of zeroes there.
## Post #3
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-03-09T02:35:19+00:00
- Post Title: Resident evil 4 HD PS3 XBOX 360 .LFS

for pc 

```
get name basename
log MEMORY_FILE 0 0 
goto 0x10
get chunks long
append
for i = 0 < chunks
get zsize short
get size short
if size = 0 
    math size = 0x10000
endif
get offset long
math offset + 0x13
clog MEMORY_FILE offset zsize size
next i
append
get size asize MEMORY_FILE
log name 0x00 size MEMORY_FILE
```


game work with uncompressed files too
