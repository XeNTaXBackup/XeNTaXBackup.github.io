## Post #1
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-09-14T16:53:09+00:00
- Post Title: Zlib compressed, or something more?

Attached is an example file, they appear to be DDS files yet will not load in any viewer.  If I run the files through Jaeder Naub with zlib detection it generates a raw file.  When the raw file is renamed to XXX.dds and viewed, *some* of them are working perfectly.  Unfortunately others are coming out corrupted.  Does anyone recognize this, "ZMHx" ID string?

Thanks!
[test.zip](https://xentaxbackup.github.io/file/2354_test.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-14T20:01:00+00:00
- Post Title: Zlib compressed, or something more?

try with the following script for QuickBMS:

```
get EXT extension
string NAME += "_unpacked."
string NAME += EXT

idstring ZMH1
get DUMMY long
get FILESIZE long
set OFFSET long 0x24
set MYFILESIZE long 0
append
for
    if MYFILESIZE >= FILESIZE
        cleanexit
    endif
    goto OFFSET
    get DUMMY long
    get SIZE long
    get ZSIZE long
    savepos OFFSET
    clog NAME OFFSET ZSIZE SIZE
    math OFFSET += ZSIZE
    math MYFILESIZE += SIZE
next
```
## Post #3
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-09-16T01:43:42+00:00
- Post Title: Zlib compressed, or something more?

Bugtest, thank you!  Your script works great on the DDS textures, and also TGA files from the archive.  I was actually able to expand them using offzip too.  The strange part is, it only seems to be working on DDS and TGA files.  The other text files, JPG, etc. will not expand properly.  I'm guessing it is something very simple, but haven't worked with compressed files enough to spot the problem.  I've attached a copy of an .inf file that I am running into this problem with, can you tell what is different about these?
[maps.zip](https://xentaxbackup.github.io/file/2355_maps.zip)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-16T08:34:39+00:00
- Post Title: Zlib compressed, or something more?

the problem is that this file is not compressed with zlib but uses another unknown algorithm (not lzss, lzw, lzo or blast).
tested also with xor and rot13 to see if it resulted in a obfuscated zlib but nothing
## Post #5
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-09-16T18:42:05+00:00
- Post Title: Zlib compressed, or something more?

Hmm darn, thanks again for looking into it.  This is pretty much the last roadblock I've run into, at least I can get at the graphics assets.  Was really hoping to dig around to find skill/item information, but may have to give up on that idea.
## Post #6
- Username: verkho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 24, 2009 9:40 pm
- Post datetime: 2009-10-20T08:29:54+00:00
- Post Title: Zlib compressed, or something more?

Loculi, can you tell me how you managed to extract the dds file from the data.ifs ?

I see that the file has been built on using blocks of 1024 bytes but I'm having problems figuring out where the x (size or size*1024) is defined.
As far as I can tell there is a header block of 4096 bytes, followed by a block of 1024 bytes specifying 8 files and some values connected to these.

Haven't been able to figure out much of those values yet though.

-Verkho
