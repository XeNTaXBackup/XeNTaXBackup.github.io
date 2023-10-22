## Post #1
- Username: skstylez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 20, 2011 8:15 pm
- Post datetime: 2013-05-23T18:36:33+00:00
- Post Title: Showdown Legends of Wrestling Script WIP

Hey there,

I've been working on a script to extract the DDS images from the thousands of .dat and .neo files that are extracted from the WRESTLER.DR and COSTUMES.DR files respectively from Showdown Legends of Wrestling for Xbox.

I have come up with this so far

```

goto 0x38
get OFFSET short
if OFFSET == 0

goto 0xBC
get FILES long
get OFFSET long

else
goto 0xA0
get FILES long
endif

goto OFFSET
for i = 0 < FILES
get WIDTH long
get HEIGHT long
get UNK1 long
get NSIZE long
getdstring UNK2 16
getdstring NAME 0x10
string NAME <= "."
string NAME += "dds"
get OFFSET1 long
savepos OFFSET2

goto OFFSET1
get UNK3 byte
get TYPE byte
goto OFFSET2

get UNK4 long
get SIZE long
get NULL1 long

callfunction addDDSheader
math SIZE += 0x80
log NAME 0 SIZE MEMORY_FILE

next i

startfunction addDDSheader
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0xC HEIGHT long

if TYPE == 0x0F
putVarChr MEMORY_FILE 0x57 0x35
else
putVarChr MEMORY_FILE 0x57 0x31
endif

endian little
   append
   log MEMORY_FILE OFFSET1 SIZE
   append

endfunction
```


I have a couple of problems which I can't seem to solve. The first problem I have is that I want to have the dds header replace the parts that are highlighted, instead of it being added before it.


The second problem is that when using the script on the .neo file, I get this.


I've attached some sample files

Any help would be much appreciated.

Thanks in advance
[LOW3.zip](https://xentaxbackup.github.io/file/6423_LOW3.zip)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-23T20:26:24+00:00
- Post Title: Showdown Legends of Wrestling Script WIP

looks like an image with a pallet.
## Post #3
- Username: skstylez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 20, 2011 8:15 pm
- Post datetime: 2013-05-24T15:03:15+00:00
- Post Title: Showdown Legends of Wrestling Script WIP

Is there a way to view the image correctly? 

I've managed to solve the first problem that I was having in regards to the dds header.

```

goto 0x38
get OFFSET short
if OFFSET == 0

goto 0xBC
get FILES long
get OFFSET long

else
goto 0xA0
get FILES long
endif

goto OFFSET
for i = 0 < FILES
get WIDTH long
get HEIGHT long
get UNK1 long
get NSIZE long
get UNK2 long
get UNK3 long
get UNK4 long
get UNK5 long
getdstring NAME 0x10
string NAME <= "."
string NAME += "dds"
get OFFSET1 long
savepos OFFSET2

goto OFFSET1
get UNK6 byte
get TYPE byte

goto OFFSET2
get UNK7 long
get SIZE long
get NULL1 long

math OFFSET1 += 0x80
math SIZE -= 0x80

callfunction addDDSheader
math SIZE += 0x80
log NAME 0 SIZE MEMORY_FILE

next i

startfunction addDDSheader
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00"
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0xC HEIGHT long

if TYPE == 0x0F
putVarChr MEMORY_FILE 0x57 0x35
else
putVarChr MEMORY_FILE 0x57 0x31
endif

endian little
   append
   log MEMORY_FILE OFFSET1 SIZE
   append

endfunction
```


Thanks
## Post #4
- Username: skstylez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 20, 2011 8:15 pm
- Post datetime: 2013-05-28T14:40:09+00:00
- Post Title: Showdown Legends of Wrestling Script WIP

Having added a tga header instead of a dds header on the .neo file, I've managed to make a bit of progress. Am I right in saying that the image is swizzled?
## Post #5
- Username: skstylez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 20, 2011 8:15 pm
- Post datetime: 2013-06-16T16:40:26+00:00
- Post Title: Showdown Legends of Wrestling Script WIP

Is there any noesis script to unswizzle xbox tga/bmp files? I've searched around for a tool, but all I could find was a dead link for a BMP unswizzle tool for MVP Baseball 2005.

Sorry for the triple post.
