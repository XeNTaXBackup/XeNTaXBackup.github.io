## Post #1
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-03-22T18:16:15+00:00
- Post Title: Trying to learn some QuickBMS, please help.

Hi there, I'm currently trying to de-interleave and extract the mp3s from the audio files from Sly4. I've done this in the past with Journey using the script here: [viewtopic.php?f=13&p=39344#p39344](http://forum.xentax.com/viewtopic.php?f=13&p=39344#p39344) but it was a slow and arduous task as I needed to make a separate script for each different header length, interleave and number of layers.

With Sly4 I'm trying to use the same script but trying to modify it so it retrieves those lengths automatically from the file itself. I've found the bytes in the file that determine the header length as well as the multiple of 300 bytes that winds up being the interleave. My problem is that I can't figure out how to take those values and use them in my script.

The length of the header is stored as a two-byte hex value at position 0x6 in the file. The interleave multiple is stored at 0x3B.

Currently my script is just trying to read in this Header length but I can't get it to keep it as a hex value, the command I'm using reads in the ASCII value and then I'm trying to convert that back to hex, but then it's stored as a string and not a hex offset.

If someone could please be gentle and guide me in the direction I need to go, I'd be much appreciative as I'm trying to learn, but the BMS language is still Greek to me.

Thanks!

```
GetDString HEADERBYTE 2
String HEADER B HEADERBYTE
GoTo 0x0
#set HEADER 0x134
print "%HEADER%"
string 
set INTERL 0x2D00
set SKIP 0x0
set LAYERS 2
set JUMP INTERL
math JUMP *= LAYERS # JUMP = size of one block
math INTERL -= SKIP
   get TEST asize
   math TEST %= LAYERS
   if TEST != 0
      print "Illegal deinterleave parameters! Aborting..."
      cleanexit
   endif
get CYCLES asize
math CYCLES /= JUMP # number of interleave blocks
get RES asize
math RES %= JUMP # size of last interleave block
#print "residuum: %RES%"
math RES /= LAYERS # size of single last interleave

if RES != 0
   print "Warning: last block is incomplete! Check your parameters!"
endif


for i = 1 <= LAYERS
   log MEMORY_FILE 0 0
   set OFFSET i
   math OFFSET -= 1
   math OFFSET *= INTERL
   math OFFSET += HEADER
   print "%OFFSET%"
   append
   for k = 1 <= CYCLES
      log MEMORY_FILE OFFSET INTERL
      math OFFSET += JUMP
      math OFFET += SKIP
   NEXT k
   if RES != 0 # incomplete but valid last block
      set OFF i
      math OFF -= 1
      math OFF *= RES
      math OFFSET -= JUMP
      math OFFSET -= SKIP
      math OFFSET += OFF
      log MEMORY_FILE OFFSET RES
   endif
   append
   get SIZE asize MEMORY_FILE
   get NAME basename
   if LAYERS != 1
      string NAME += "_"
      string NAME += i
   endif
   log NAME 0 SIZE MEMORY_FILE
next i
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-22T18:22:31+00:00
- Post Title: Trying to learn some QuickBMS, please help.

I don't understand the HEADER/HEADERBYTE sequence, anyway I guess you want to use:
get HEADER short
## Post #3
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-03-22T18:27:24+00:00
- Post Title: Trying to learn some QuickBMS, please help.

> Reply from aluigi
>
> I don't understand the HEADER/HEADERBYTE sequence, anyway I guess you want to use:
get HEADER short

Does that get a 2-byte value then? When I do this:

```
get HEADER short
GoTo 0x0
print "%HEADER%"
```


it prints "13313"

Which when converted to hex is exactly backwards from the byte order I need... must be some way to convert the byte order, right?
## Post #4
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-03-22T18:42:19+00:00
- Post Title: Trying to learn some QuickBMS, please help.

Ah Hah! Declaring "endian big" at the beginning of the script seems to have solved that problem. Now we're getting somewhere!
