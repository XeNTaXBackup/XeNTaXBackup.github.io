## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2011-08-17T18:39:18+00:00
- Post Title: Help to decrompress .pak archive mystery mountains

Hi friends, i need help with the decompress the file xml.pak 
the game is Mystery stories mountains of madness
the file 

[http://www.mediafire.com/?asxus8j56cws66i](http://www.mediafire.com/?asxus8j56cws66i)
## Post #2
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2011-10-04T12:44:12+00:00
- Post Title: Help to decrompress .pak archive mystery mountains

Please help

[http://www.mediafire.com/?db2u0jn0jida95q](http://www.mediafire.com/?db2u0jn0jida95q)
[http://www.mediafire.com/?8zn32d853dwi8wa](http://www.mediafire.com/?8zn32d853dwi8wa)
## Post #3
- Username: Marry
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2011 7:30 pm
- Post datetime: 2011-12-17T23:34:19+00:00
- Post Title: Help to decrompress .pak archive mystery mountains

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-18T11:47:06+00:00
- Post Title: Help to decrompress .pak archive mystery mountains

job done, it was a simple encryption scheme:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "gfcpk"
get VER byte
getdstring KEY 4
get DUMMY long

get SIZE asize
log MEMORY_FILE 0 SIZE

print "wait some seconds/minutes for the decryption..."
savepos OFFSET
for i = OFFSET < SIZE
    getvarchr T MEMORY_FILE i
    math C = i
    math X = i
    math X &= 3
    getvarchr X KEY X
    math C ^= X
    math T ^= C
    putvarchr MEMORY_FILE i T
next i

print "extraction..."
goto OFFSET MEMORY_FILE
get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZIP long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    if ZIP == 0
        log NAME OFFSET SIZE MEMORY_FILE
    else
        clog NAME OFFSET ZSIZE SIZE MEMORY_FILE
    endif
next i
```
## Post #5
- Username: Marry
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2011 7:30 pm
- Post datetime: 2011-12-18T17:26:19+00:00
- Post Title: Help to decrompress .pak archive mystery mountains

Thank you very much, Luigi
