## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-04-26T06:31:27+00:00
- Post Title: Lemony Snicket's Series of Unfortunate Events .res files

Got this off my GameCube recently, and I was wondering if unpacking these files are possible. I assume that these are archives, based on the fact that most of the asset directories only consist of .res files. The game data itself isn't organised in a way like Grand Theft Auto (i.e. a few large archive files with INIs pointing to that chunk of data whenever the game starts), and it's more or less like the ones in Need For Speed or something.

The header reads out something like this (header contents are similar to each other and are of the same size but contents may vary between files):

```

72 65 73 0A 07 00 03 00 00 00 10 00 00 04 12 A0 00 04 30 00 00 02 56 88 00 03 F5 58 00 06 90 00 00 00 16 8C 00 00 00 0A 73 64 74 61 00 01 00 20 67 73 68 64 00 0C 00 20 6E 6F 64 65 00 BC 00 20 77 61 76 65 00 07 00 20 73 75 72 66 00 23 00 80 6E 64 62 67 00 04 00 20 73 74 72 67 00 01 00 04 62 6D 73 68 00 22 00 20 69 6E 64 78 00 04 00 08 62 6F 64 79 00 40 00 20

klaus_book.res:

72 65 73 0A 07 00 03 00 00 00 10 00 00 03 4D 64 00 03 60 00 00 04 1A B0 00 03 27 58 00 07 80 00 00 00 1B 34 00 00 00 0A 73 64 74 61 00 01 00 20 67 73 68 64 00 0C 00 20 6E 6F 64 65 00 BC 00 20 77 61 76 65 00 07 00 20 73 75 72 66 00 23 00 80 6E 64 62 67 00 04 00 20 73 74 72 67 00 01 00 04 62 6D 73 68 00 22 00 20 69 6E 64 78 00 04 00 08 62 6F 64 79 00 40 00 20

```

A mother lode of zeroes then follows before the content really starts. IDK if it's compressed, packed or otherwise, and I don't think they're encrypted in some whay (unless the developers decided to).

I uploaded a few res files for us to tinker with: [snicketmdls.rar - 1.57MB](http://www.zshare.net/download/753913996cbed5cf/)

I hope someone would take a look at it; I'm curious as to how the game was built together, so any help will be appreciated.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-26T19:18:20+00:00
- Post Title: Lemony Snicket's Series of Unfortunate Events .res files

okay, so i was a little optimistic with that last edit - i can't finish this.

the pointers are all over the place, and there are nice filename tables. here's the bulk of it:

(the 4 segments are aligned in 4096-byte blocks - hence your "motherload of zeroes" :

HEADER (see below)
SEGMENT 1 (filenames at end)
SEGMENT 2 (filenames at end too..)
SEGMENT 3 (smallest - expected pointers))

segments are logged in the bms script

```

## header
idstring "res\x0a"

get DUMMY short
get DUMMY short

for i = 1 to 3

  if i == 1

    get pSECTOR1 long
    get sSECTOR1 long

    log "SECTOR_1.dat" pSECTOR1 sSECTOR1

  else

    get pSECTOR long
    get sSECTOR long

    if i == 2

      get pTABLE long

    endif

    set NAME string "SECTOR_"
    string NAME += i
    string NAME += ".dat"

    log NAME pSECTOR sSECTOR

  endif

next i

get SECTORS long

for i = 1 to SECTORS

  getdstring NAME 4

#  print "%NAME%"

  get DUMMY short # >1, some odd, not unique
  get DUMMY short # flags? 4,8,32,128

next i

## end of header

```


other stuff:


the filenames should be pointed to, though can be read with 4-byte padding after string (get NAME string \n padding 4)

```


set SEEK pSECTOR1  ### this is why i kept the first pointer seperately ^^
math SEEK += pTABLE

goto SEEK

get FILES long
get DUMMY long # 4

savepos SEEK
math FILES *= 12 # short, short, char[4], short, short
math SEEK += FILES
goto SEEK

for 

  get FILENAME string

  strlen FNLEN FILENAME

  if FNLEN == 0
    cleanexit
  endif

  padding 4
  print "%FILENAME%"

next

```


the structure before them is 12 bytes -- short, short, char[4], short, short

the third segment is : get Count long, get DUMMY long (4), with a 20-byte structure of getdstring NAME 4 and 8 shorts. i was expecting this data to point to the file, but it isn't consistent..

if the segment/sector size is 0, the following sector will start at the same position.
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-04-26T23:30:02+00:00
- Post Title: Lemony Snicket's Series of Unfortunate Events .res files

Thanks, dude. So, was it really an archive or something, or just some Fort Knox of a file?

EDIT: Dug up a few more files; turns out that the header seems to vary in size, but I guess it isn't much of a difference.

I uploaded animlist.res and fmajor.res (I think these stand for a list of animations and a song played ingame, respectively): [snicketmdls2.rar - 0.78MB](http://www.zshare.net/download/75426213de3a9e60/)
