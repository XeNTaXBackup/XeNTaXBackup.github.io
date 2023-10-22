## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2016-07-21T20:30:24+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

Hi,

Is there a way to extract and reinsert graphics from Sherlock Holmes: The Secret Earring?

[http://www.mediafire.com/download/oslat ... /documents](http://www.mediafire.com/download/oslatoot30aa08w/documents)

Thank you.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-07-24T20:46:30+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

i have written a script to extract images, but that file table is taking time.....
## Post #3
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2016-07-26T13:00:56+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

> Reply from WRS
>
> i have written a script to extract images, but that file table is taking time.....
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-07-30T22:55:16+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

here is the resource extractor as a bms script:

```
# QuickBMS script by WRS (XeNTaX.com)

get UNKNOWN long
get UNKNOWN long
get UNKNOWN long
get STR_LENGTH long
getdstring LANG_NAME STR_LENGTH
get UNKNOWN_SIZE long
get UNKNOWN_SIZE long
get COUNT long

for i = 0 < COUNT
  get STR_LENGTH long
  getdstring STR STR_LENGTH
  get UNKNOWN_VAL1 long
  get UNKNOWN_VAL2 long
  if UNKNOWN_VAL1 == -1
    get SUB_STR_LENGTH long
    getdstring SUB_STR SUB_STR_LENGTH
    get SUB_UNKNOWN_VAL1 float
    get SUB_UNKNOWN_VAL2 long
    get FLOATS long
    for f = 0 < FLOATS
      get FLOAT_VAL float
    next f
    get VALUES long
    for n = 0 < VALUES
      get INT_VALUE long
    next n
  endif
next i

# resource parsing (INCOMPLETE)

for
  get DUMMY_STR_LENGTH long
  getdstring DUMMY_STR DUMMY_STR_LENGTH
  get RESOURCE_INDEX long
  if RESOURCE_INDEX == -1
    # reached eof
    cleanexit
  endif
  get UNKNOWN_VAL2 long

  get MINUS_ONE long # -1

  get UNKNOWN long
  get UNKNOWN long # hash?
  get UNKNOWN long # hash?
  get IMAGE_SIZE long
  get ZLIB_SIZE long
  get ZLIB_ZSIZE long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get COUNT long
  for c = 0 < COUNT
    get DUMMY float # no idea what this is
  next c
  get UNKNOWN long # 0
  savepos IMAGE_OFFSET
  math ZLIB_OFFSET = IMAGE_OFFSET
  math ZLIB_OFFSET + IMAGE_SIZE
  log "" IMAGE_OFFSET IMAGE_SIZE
  math EOF_ZLIB = ZLIB_OFFSET
  math EOF_ZLIB + ZLIB_ZSIZE
  goto EOF_ZLIB
next

```


as you can see, there are too many unknown values to make a repacker - which sucks   

hopefully this is of use of you anyway !
## Post #5
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2016-07-31T15:21:48+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

Well, it's a start   . Thank you very much.
## Post #6
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2016-08-03T14:37:05+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

With the script (Thanks, WRS!), i've extracted the files i need to translate. But i still need to re-insert the edited files. Does anyone know if it is possible with this type of file?
## Post #7
- Username: AnushkaChakrabart
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 2:56 pm
- Post datetime: 2016-08-08T07:06:50+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

Nice one dude,Well done Well, it's good start.
Thank you very much.
## Post #8
- Username: fignyafsyakaya
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 27, 2019 3:03 pm
- Post datetime: 2023-06-25T01:25:05+00:00
- Post Title: Extract Graphics from Sherlock Holmes: The Silver Earring

Sort of developed the script made by WRS - now it extracts jpgs with their filenames.

```
get UNKNOWN long
get UNKNOWN long
get UNKNOWN long
get STR_LENGTH long
getdstring LANG_NAME STR_LENGTH
get UNKNOWN_SIZE long
get UNKNOWN_SIZE long
get COUNT long

for i = 0 < COUNT
  get STR_LENGTH long
  getdstring STR STR_LENGTH
  get UNKNOWN_VAL1 long
  get UNKNOWN_VAL2 long
 if UNKNOWN_VAL1 == -1
    get SUB_STR_LENGTH long
    getdstring SUB_STR SUB_STR_LENGTH
    get SUB_UNKNOWN_VAL1 float
    get SUB_UNKNOWN_VAL2 long
    get FLOATS long
    for f = 0 < FLOATS
      get FLOAT_VAL float
    next f
    get VALUES long
    for n = 0 < VALUES
      get INT_VALUE long
      string FILENAME p "%s_%s_%04d.jpg" STR SUB_STR n
      putarray 0 INT_VALUE FILENAME
    next n
 else
      string FILENAME p "%s.jpg" STR
      putarray 0 UNKNOWN_VAL1 FILENAME
 endif
  
next i

# resource parsing (might be INCOMPLETE yet)
math j == 0
for
  get DUMMY_STR_LENGTH long
  getdstring DUMMY_STR DUMMY_STR_LENGTH
  get RESOURCE_INDEX long
  if RESOURCE_INDEX == -1
    # reached eof
    cleanexit
  endif
  get UNKNOWN_VAL2 long

  get MINUS_ONE long # -1

  get UNKNOWN long
  get UNKNOWN long # hash?
  get UNKNOWN long # hash?
  get IMAGE_SIZE long
  get ZLIB_SIZE long
  get ZLIB_ZSIZE long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get UNKNOWN long
  get COUNT long
  for c = 0 < COUNT
    get DUMMY float # no idea what this is
  next c
  get UNKNOWN long # not always 0
  getdstring DUMMY UNKNOWN
  savepos IMAGE_OFFSET
  math ZLIB_OFFSET = IMAGE_OFFSET
  math ZLIB_OFFSET + IMAGE_SIZE
  getarray FILENAME 0 j
  string NAME p "%s_folder/%s" ARCHNAME FILENAME
  log NAME IMAGE_OFFSET IMAGE_SIZE
  math EOF_ZLIB = ZLIB_OFFSET
  math EOF_ZLIB + ZLIB_ZSIZE
  goto EOF_ZLIB
  math j += 1
next
```
