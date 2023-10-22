## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-12T03:45:14+00:00
- Post Title: RAD Files

I found a game that uses nif files stored in .rad archives.
I have managed to get it to list the file names of the files but I can't get it to extract the files.
I think I am close but I do not know what I am doing wrong.
Here is a sample archive and what I have made out in a bms script so far.

```
#get FILES long
math FILES += 184
goto 0x118
#goto 0x224
for i = 0 < FILES

get NULL1 long
get OFFSET long
goto OFFSET
get OFFSET2 long
getdstring NAME 0x100
get ZSIZE long
get SIZE long

#get ZSIZE long
#get SIZE long
#get NULL long
#get OFFSET long
#goto OFFSET
#get NULL2 long
#getdstring NAME 0x100

clog NAME OFFSET ZSIZE SIZE
goto OFFSET
next i

```

the basic file structure starts with some unkown value normally 0C or 01
then the offset of the file table entry 4 bytes long
then you go to that table entry and you get the zip size long
then the uncompressed size long
then you start the cycle again but you need to log the archive or pick up the file table from that spot so it will keep reading the file table.
what I have commented out was how I got it to list the file table correctly but I could not extract.
Thanks in advance for any help 
then 0x100 for the file name
[Config.rar](https://xentaxbackup.github.io/file/2029_Config.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-12T10:57:59+00:00
- Post Title: RAD Files

```
get FILES long # doesn't seem to be the correct number
set OFFSET long 0x120
get TOTAL_SIZE asize

for
   if OFFSET >= TOTAL_SIZE
      cleanexit
   endif
   goto OFFSET
   get ZIP long   # not verified
   getdstring NAME 0x100
   get ZSIZE long
   get SIZE long
   get DUMMY long
   get DUMMY long
   savepos OFFSET

   if ZIP == 1
      clog NAME OFFSET ZSIZE SIZE
   else
      log NAME OFFSET ZSIZE
   endif

   math OFFSET += ZSIZE
next
```
try it with various files because I don't know if the ZIP value is really referred to the compression
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-12T12:41:07+00:00
- Post Title: RAD Files

The contents of this post was deleted because of possible forum rules violation.
