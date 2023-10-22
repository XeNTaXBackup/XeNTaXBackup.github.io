## Post #1
- Username: buang007
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 04, 2010 1:10 am
- Post datetime: 2010-09-03T14:32:43+00:00
- Post Title: XBrave Online user Gamebryo Version 20.3.0.9

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-09-03T23:49:35+00:00
- Post Title: XBrave Online user Gamebryo Version 20.3.0.9

I get this with signsearch:

> 00f24350 309  padding used in hashing algorithms <0x80 0 ... 0> [..64]
>
> 0086a559 2269 DMC compression [32.le.16&]
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-04T15:49:22+00:00
- Post Title: XBrave Online user Gamebryo Version 20.3.0.9

odd that sigsearch didnt pickup the deflate algo. either way - 

```
#    xentax.com
#    .dho BMS script

get FSIZE asize

for

  get BLOCKSIG long

  if BLOCKSIG == 0x01797268 # hry\x1

    get FLAGS long
    get CTYPE short
    get UNKNOWN long
    get CRC32 long
    get ZSIZE long
    get SIZE long
    get FNAMESIZE long

    getdstring FNAME FNAMESIZE

    if FILESIZE > 0

      savepos POS

      if CTYPE == 0

        log FNAME POS ZSIZE       

      elif CTYPE == 8

        comtype deflate
        clog FNAME POS ZSIZE SIZE

      else

        print "Unknown compression type for '%FNAME%'"
        cleanexit

      endif

      math POS += ZSIZE
      goto POS

    endif


  elif BLOCKSIG == 0x04797268 # hry\x4

    getdstring UNKNOWN 36

    get FNAMESIZE long
    get UNKNOWN short # should test this is always 0

    getdstring FNAME FNAMESIZE


  elif BLOCKSIG == 0x07797268 # hry\x7

    getdstring UNKNOWN 24

  else

    print "unrecognised block header (%BLOCKSIG%)"
    cleanexit

  endif

  savepos POS

  if POS == FSIZE

    cleanexit

  endif

next

```
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-09-04T23:48:54+00:00
- Post Title: XBrave Online user Gamebryo Version 20.3.0.9

good stuff
