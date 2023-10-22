## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-28T13:02:30+00:00
- Post Title: Inversion .s3darc

the localization has been mentioned already: [viewtopic.php?f=35&t=9187&hilit=inversion](http://forum.xentax.com/viewtopic.php?f=35&t=9187&hilit=inversion) and there are other games which use this format or one similar which i've not tested.

```
# QuickBMS script by WRS (xentax.com)

# NOTE: extracted files are given guessed extensions
# this is to help guess the ftype attribute

math IS_DEBUG = 0

comtype zlib

if IS_DEBUG = 1
  get size_1 long
  get zsize_1 long
  savepos offset
  clog MEMORY_FILE offset zsize_1 size_1
  math offset += zsize_1
  goto offset
  get val_1 long MEMORY_FILE

  get size_2 long
  get zsize_2 long
  savepos offset
  clog MEMORY_FILE offset zsize_2 size_2
  math offset += zsize_2
  goto offset
  get val_2 long MEMORY_FILE

  print "Debug: %val_1% %val_2%"
else
  goto 40
endif

get offset long
goto offset
get declen long
get cmplen long
savepos offset
clog MEMORY_FILE offset cmplen declen

get files long MEMORY_FILE

for f = 1 to files
  get fnlen long MEMORY_FILE
  getdstring fn fnlen MEMORY_FILE
  get ftype long MEMORY_FILE
  get foffset long MEMORY_FILE
  get fhash long MEMORY_FILE
  get fdeclen long MEMORY_FILE
  get fcmplen long MEMORY_FILE

  clog MEMORY_FILE2 foffset fcmplen fdeclen

  # scripts
  if ftype == 0
    ## NOTE FOR REPACKERS:
    # script files have the filesize prepended to the file2

    get datasize long MEMORY_FILE2

    # datasize now equals (fdeclen-4)

    string fn p= "%s.txt" fn
    log fn 4 datasize MEMORY_FILE2

  # unknown
  #elif ftype == 2

  # texture data - unknown type
  #elif ftype == 6

  # localization
  elif ftype == 14
    string fn p= "%s.loc" fn
    log fn 0 fdeclen MEMORY_FILE2

  # .gfx
  elif ftype == 18
    get size_3 long MEMORY_FILE2
    get zsize_3 long MEMORY_FILE2

    string fn p= "%s.gfx" fn
    clog fn 10 zsize_3 size_3 MEMORY_FILE2


  else
    string fn p= "%s_%02X" fn ftype
    log fn 0 fdeclen MEMORY_FILE2
  endif
next f


```
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-28T23:53:53+00:00
- Post Title: Inversion .s3darc

bumping to say ive just release a locale patching tool over in the localization section which may be more useful to anyone looking to translate inversion: [viewtopic.php?f=35&t=9187&p=76346#p76346](http://forum.xentax.com/viewtopic.php?f=35&t=9187&p=76346#p76346)
