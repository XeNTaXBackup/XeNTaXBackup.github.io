## Post #1
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-05-24T23:46:43+00:00
- Post Title: Add files size to beginning of another outputted file.

as the title states, I can't work out how to add the compressed size + the uncompressed size to the beginning of the compressed file.

it would look like - (compressed size long)(nul bytes long)(uncompressed size long)(compressed data)

The way I get around this the now, is I use the original files first 12bytes from the original file & output them to a tmp file, then compress the new file. Then I use a batch to combine the tmp files + the new file.

There must be an easier way than the above.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-25T06:43:29+00:00
- Post Title: Add files size to beginning of another outputted file.

I don't know what programming language you are using but with quickbms this is not complex:

```
math SIZE  = 0x5678 # placeholder

log MEMORY_FILE 0 0
put ZSIZE long MEMORY_FILE
put 0     long MEMORY_FILE
put SIZE  long MEMORY_FILE
append
log MEMORY_FILE 0 ZSIZE
append

get SIZE asize MEMORY_FILE
log "output.dat" 0 SIZE MEMORY_FILE

```
## Post #3
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-05-25T11:13:54+00:00
- Post Title: Add files size to beginning of another outputted file.

> Reply from aluigi
>
> I don't know what programming language you are using but with quickbms this is not complex:

I'm using QuickBMS, but this is my first time making a script, well second I done the extractor, this is to compress the output.

Thank you, I was using string & a few other commands with no luck.

I'm still trying to understand everything in the Quickbms.txt

This is the code I have sofar, i tried using MEMORY_FILE for the compressed data but it would always output the uncompressed data, in the final output. (clog MEMORY_FILE2 0x0 DSIZE DSIZE)

```
# MCXB_Save_Encrypt.bms
# (c) 25/05/2013 by Rocky5
#=================================================================================================

endian big
open "tmp" 0.tmp								# Open uncompressed file.
get DSIZE ASIZE								# Get uncompressed size.

	comtype xmemlzx_compress

clog "tmp\1.tmp" 0x0 DSIZE DSIZE			# Compress file.

open "tmp" 1.tmp
get CSIZE ASIZE								# Get compressed size.
math CSIZE += 0x08							# Needed for the Xbox to read the save

log MEMORY_FILE1 0x0 0x0					# Create a memory file.
put CSIZE long MEMORY_FILE1					# Puts file compressed size.
put 0     long MEMORY_FILE1					# Puts Nuls for 4 bytes.
put DSIZE long MEMORY_FILE1					# Puts file uncompressed size.

math CSIZE -= 0x08							# Reset the compressed size

append
log MEMORY_FILE1 0x0 CSIZE					# Puts it all together.
append

get SIZE asize MEMORY_FILE1

log "tmp\savegame.dat" 0 SIZE MEMORY_FILE1

```
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-05-25T14:36:38+00:00
- Post Title: Add files size to beginning of another outputted file.

If you don't mind my asking, why do you need the null long? Both of the values you're storing are always stored as longs themselves, so you shouldn't have any problem separating them.
## Post #5
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-05-25T17:31:48+00:00
- Post Title: Add files size to beginning of another outputted file.

> Reply from Dinoguy1000
>
> If you don't mind my asking, why do you need the null long? Both of the values you're storing are always stored as longs themselves, so you shouldn't have any problem separating them.

The xbox crashes if there not present. 

The compressed size is actually the Null long + uncompressed long + compressed data. So you take 8 off the compressed size & start at 0x0C, for extraction using QuickBMS.

The xbox on the other hand doesn't, well it probably does but if its not present it panics & freezes the console.

I'm new to QuickBMS, I was using Swiss File Kife & cmd commands to do it before, a lot more code required oO
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-05-25T19:03:48+00:00
- Post Title: Add files size to beginning of another outputted file.

Aah, you never said you were making these files for use on an Xbox. Thanks for the explanation.
## Post #7
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-05-28T14:50:21+00:00
- Post Title: Add files size to beginning of another outputted file.

> Reply from Dinoguy1000
>
> Aah, you never said you were making these files for use on an Xbox. Thanks for the explanation.

Sorry & NP.

Could I ask for some help please, How do I pad a file, I have been trying using the MEMORY_FILE code above to try and pad a file to 0x1000 so the compressed data + 000000 to a total size of 0x1000, but no luck, I even tried using a dummy file that is 0x1000 in size & import the compressed data at offset 0x0 then remove the compressed size from the 0x1000.

Update: I got the latter working.
