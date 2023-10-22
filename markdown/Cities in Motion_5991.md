## Post #1
- Username: Microsnakey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 09, 2010 5:29 am
- Post datetime: 2011-02-04T21:53:33+00:00
- Post Title: Cities in Motion

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-05T22:01:35+00:00
- Post Title: Cities in Motion

more chunks..    but with this format, i was able to define everything!

if any file breaks this script, please upload it. i couldn't be bothered to use a loop to read the chunks, so it just reads the chunks in the same order as the only example provided   

```
# packed zlib files, chunks, amusing footnote

idstring "GS10"
get FSIZE long

## verify
savepos pos
get SIZE asize
math FSIZE += POS
if FSIZE != SIZE
  print "Unexpected filesize"
  cleanexit
endif

## it's all chunked by id

get CHUNKTYPE1 long
get CHUNKSIZE1 long

if CHUNKTYPE1 != 0x01000000 # file info chunk expected first
  print "FileInfo chunk expected"
  cleanexit
endif

get CHUNKTYPE2 long
get CHUNKSIZE2 long

if CHUNKTYPE2 != 0x01100000
  print "ResourceInfo chunk expected"
  cleanexit
endif

# continue resourceinfo
get FILES long

get CHUNKTYPE3 long # folder: 0x01130000
get STRSIZE long
getdstring FOLDERNAME STRSIZE

# now the files
for f = 1 to FILES
  savepos CSTART
  get CHUNKTYPE long # file: 0x01120000
  get CHUNKSIZE long # 144
  getdstring CHUNKID 4

  ## noted the "fu" id for the .script type ..

  get ZLIBPNTR long
  savepos POS
  math POS -= CSTART
  math ZLIBPNTR += POS # it's 16 btw
  get RSIZE long
  get ZSIZE long
  getdstring FILENAME STRSIZE
  string FNAME = FOLDERNAME
  string FNAME += FILENAME

  clog FNAME ZLIBPNTR ZSIZE RSIZE
next f

# next chunk is the compressed data
get CHUNKTYPE4 long
get CHUNKSIZE4 long

if CHUNKTYPE4 != 0x01200000
  print "ZLibData chunk expected" # well.. it's already parsed..
  cleanexit
endif

savepos POS
math POS += CHUNKSIZE4
goto POS

## funny footnote

get CHUNKTYPE5 long
get CHUNKSIZE5 long

if CHUNKTYPE5 != 0x00000001
  print "Missing the footnote :("
  cleanexit
endif

getdstring FOOTNOTEMSG CHUNKSIZE5
print "Footnote: '%FOOTNOTEMSG%'"
# eof

```
## Post #3
- Username: Microsnakey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 09, 2010 5:29 am
- Post datetime: 2011-02-06T13:36:26+00:00
- Post Title: Cities in Motion

Thanks a lot, it works great. Is they a way to repack the files
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-06T15:28:18+00:00
- Post Title: Cities in Motion

> Reply from Microsnakey
>
> Thanks a lot, it works great. Is they a way to repack the files

i only write the scripts as proof-of-concept, and quickbms doesn't handle repacking
plus this site is primarily about researching formats, which i've covered here.
