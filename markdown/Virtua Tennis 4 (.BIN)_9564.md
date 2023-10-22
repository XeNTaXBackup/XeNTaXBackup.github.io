## Post #1
- Username: saad755
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 08, 2010 10:04 am
- Post datetime: 2012-08-29T08:33:01+00:00
- Post Title: Virtua Tennis 4 (*.BIN)

Hi there,

Can anyone please guide me to opening Virtua Tennis 4's BIN archive,
The game has only two files that seems to contain all the resources  namely resource.bin (1.98 GB) and resource.1.bin (0.98 GB)

Somebody please make an extractor/explorer/injector for these archives.

Thanks in advance.

P.S. XeNTaX community please come forward my trust in you is shaking because i have asked for help many times but never got a single response. Hope to hear from someone soon...
## Post #2
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2013-05-22T18:43:00+00:00
- Post Title: Virtua Tennis 4 (*.BIN)

Up!!
Please anyone, i need this too!
## Post #3
- Username: SergioF
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 16, 2012 2:59 am
- Post datetime: 2015-06-12T15:41:21+00:00
- Post Title: Virtua Tennis 4 (*.BIN)

I realized that is a container, but the compression is unknown to me.
I made a bms script.
Discovering the compression will be useful for translation into my language (Portuguese of Brazil).

```
#   Virtual Tennis 4
# script for QuickBMS http://quickbms.aluigi.org

#comtype ???? replace ??? for compression algo

endian big
set SIZETOTAL asize
set VALUENUMBER 0
SavePos OFFSETPOS 0

For i = OFFSETPOS < SIZETOTAL
GoTo OFFSETPOS 0
get SIZE long # Size decompressed
get ZSIZE long # Size compressed

math OFFSETPOS + 8

set NAME "DUMP_"
string NAME += VALUENUMBER
string NAME += ".dat"

log NAME OFFSETPOS ZSIZE

math OFFSETPOS + ZSIZE
math VALUENUMBER += 1
next
```
