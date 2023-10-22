## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-02T06:02:48+00:00
- Post Title: FFXI PlayOnline Tetra Master

Found this today while cleaning my hard drive. Kind of surprised, but I liked the game and thought getting the resources easily wasn't a bad deal.

It is recursively defined but there's only one level of recursion so I didn't really bother.
Though, I'm kind of interested why I couldn't make a path name by combining the FOLDER with "/" and NAME. FOLDER kept giving me some weird character.

```
#written by Tsukihime
#script for QuickBMS http://aluigi.org/papers.htm#quickbms

for i
  get TYPE long
  if TYPE != 32768
    cleanexit
  endif
  
  getdstring FOLDER 4
  getdstring unk 8
  get STARTOFS long
  get SIZE long
  get unk long
  get unk long
  
  savepos curr
  
  goto STARTOFS
  for j
    get TYPE long
    if TYPE != 16384
      break
    endif
    getdstring NAME 12
    get OFFSET long
    get SIZE long
    get unk long
    get unk long
    
    string NAME += ".png"
    math OFFSET += STARTOFS
    log NAME OFFSET SIZE
  next j

  goto curr
next i

```
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-06-23T01:42:04+00:00
- Post Title: FFXI PlayOnline Tetra Master

(slightly) better script to extract with correct filenames. also this game rocks.

```
  savepos last
  get type long

  if type == 0x8000
    getdstring lastFolder 12
    get a long
    get b long
    get c long
    get d long
    savepos pos
    goto a

    for
      savepos last2
      get type2 long

      if type2 == 0x4000
        getdstring lastFile 12
        get a2 long
        get b2 long
        get c2 long
        get d2 long

        string NAME = "extracted_"
        string NAME += lastFolder
        string NAME += "/"
        string NAME += lastFile
        string NAME += ".png"

        math OFFSET = a
        math OFFSET += a2

        log NAME OFFSET b2
      else
        break # no more files here
      endif
    next

    goto pos
  else
    print "Done"
    cleanexit
  endif
next

```
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-06-23T21:22:32+00:00
- Post Title: FFXI PlayOnline Tetra Master

is there a way to grab models + animations and export yet?
