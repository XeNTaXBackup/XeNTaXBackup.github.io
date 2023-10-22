## Post #1
- Username: jcarl904
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-09T15:37:29+00:00
- Post Title: Pain PS3

Here is a max importer for pain and a texture converter.
Note*
if you are using the blueray disc version the files are in CacheData.dat and CacheData.pak
run this script to extract it.

```
open FDDE dat 1
endian big
get files long 1
get null long 1
set offset 0
for i = 0 < files
get size long 1
getdstring name 0xFC 1
log name offset size
math offset + size
next i

```


The models are in the .rsx files
first decompress the rsx files.
offzip.exe -1 -a -z -15 c:\file.rsx c:\output 0x0
rename the .dat file it creates to .rsx
2nd
extract the textures with this bms script.

```
goto 0x10
get textable long
goto textable
get files long
get start long
for i = 1 to files
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
endian big
goto start
get offset long
get mips short
print "%mips%"
get type byte
print "%type%"
#86 = dxt1
#87 = dxt3
#88 = dxt5
get unk byte
getdstring null 0x10
get height short
get width short
getdstring null 0x10
savepos start
get size long
if i == files
get size asize
endif
math size - offset
endian little
putVarChr MEMORY_FILE 0x1C mips short
putVarChr MEMORY_FILE 0xC width short
putVarChr MEMORY_FILE 0x10 height short
if type == 134
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x16 0x08 byte
endif
if type == 135
putVarChr MEMORY_FILE 0x57 0x33 byte
endif
if type == 136
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x16 0x10 byte
endif
if type == 133
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short
endif
get name basename
string name + _
string name + i
string name + .dds
print "%offset%"
append
log MEMORY_FILE offset size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE
next i

```

3rd run my max script attached here and then assign textures to your model.
The script currently supports 
Meshes
Bones
does not support
auto texture
weighting

4th
Enjoy

[rsx2.rar](https://xentaxbackup.github.io/file/4191_rsx2.rar)
## Post #2
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-04-10T09:46:29+00:00
- Post Title: Pain PS3

Thanks Chrrox ...anther great work!! I have this funny game...it has an unusual character design.
thanks again.
## Post #3
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-04-10T23:15:11+00:00
- Post Title: Pain PS3

I don't understand this:
"first decompress the rsx files.
offzip.exe -1 -a -z -15 c:\file.rsx c:\output 0x0"

Offzip.exe, where I find?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-10T23:17:02+00:00
- Post Title: Pain PS3

[http://aluigi.org/mytoolz/offzip.zip](http://aluigi.org/mytoolz/offzip.zip)
## Post #5
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-04-10T23:21:26+00:00
- Post Title: Pain PS3

Thanks, I try now extract!
## Post #6
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2011-10-25T15:45:40+00:00
- Post Title: Pain PS3

chrrox, I need your assistance.  
I'm using the .bms script posted above to extract the CacheData.pak, but I get this error.
[](http://imageshack.us/photo/my-images/696/quickbmserror.png/)

Any help would be really appreciated.

Solution, rename CacheDesc.dat to CacheData.dat.
## Post #7
- Username: 711pagan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 07, 2012 5:18 am
- Post datetime: 2012-11-12T20:42:42+00:00
- Post Title: Pain PS3

First I'd like to say thank you for all you do here. Pretty impressive and really inspiring.

When I run offzip, I am getting some errors, specifically; "zlib Z_DATA_ERROR, the data in the file is not in zip format or uses a different windowBits value (-z). Try to use a-z 15"
I have tried with a couple different character files with the same results, so don't think its the file??  Wondered if these offsets are the textures?

Here is a redirect of the console window. The error msg's didn't output to the text file but are obviously at the offsets with no zip blocks;
- open input file:    c:\somefile.rsx
- enter in directory: c:\output
- zip data to check:  32 bytes
- zip windowBits:     -15
- seek offset:        0x00000000  (0)

+------------+-------------+-------------------------+
| hex_offset | blocks_dots | zip_size --> unzip_size |
+------------+-------------+-------------------------+
  0x00000039 
  0x00000048 
  0x00000060  36921 --> 65536
  0x000090a0  47525 --> 65536
  0x00014a50  47998 --> 65536
  0x000205d0  46418 --> 65536
  0x0002bb30  24931 --> 35456
  0x00031cb8 
  0x00031cb9 
  0x00031cf8 
  0x00031d01 
  0x00031d10 
  0x00031d19 
  0x00031d28 
  0x00031d29 
  0x00031d81 
  0x00031d90 
  0x00031db0  28142 --> 65536
  0x00038ba0  21893 --> 65536
  0x0003e130  22122 --> 65536
  0x000437a0  22007 --> 65536
  0x00048da0  23694 --> 65536
  0x0004ea30  30371 --> 65536
  0x000560e0  40881 --> 65536
  0x000600a0  42230 --> 65536
  0x0006a5a0  37371 --> 65536
  0x000737a0  39939 --> 65536
  0x0007d3b0  35797 --> 65536
  0x00085f90  34458 --> 65536
  0x0008e630  29979 --> 65536
  0x00095b50  42917 --> 65536
  0x000a0300  44447 --> 65536
  0x000ab0a0  40277 --> 65536
  0x000b4e00  37152 --> 65536
  0x000bdf20  43048 --> 65536
  0x000c8750  33483 --> 65536
  0x000d0a20  41547 --> 65536
  0x000dac70  44224 --> 65536
  0x000e5930  39818 --> 65536
  0x000ef4c0  38687 --> 65536
  0x000f8be0  48962 --> 65536
  0x00104b30  42730 --> 65536
  0x0010f220  38888 --> 65536
  0x00118a10  44596 --> 65536
  0x00123850  45854 --> 65536
  0x0012eb70  35910 --> 65536
  0x001377c0  36092 --> 65536
  0x001404c0  37491 --> 65536
  0x00149740  32659 --> 51896


- 37 valid zip blocks found

Thanks for any help/patience you can provide a n00b.
