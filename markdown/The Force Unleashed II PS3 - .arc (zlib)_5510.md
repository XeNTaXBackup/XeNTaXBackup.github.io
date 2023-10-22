## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-08T17:04:51+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-08T18:07:41+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

just use a large size of reasonable quantity: eg 0xFFFFF, which is used in the guide.
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-12-08T18:24:59+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

Can use offzip.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-08T20:30:00+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

took a look at the format.
as there don't appear to be any zsize properties, you can just use the next pointer reference, or the filesize.

i wrote a little script, getting distracted with the index skip stuff, but the barebones are here:

```
endian big
idstring "PSAR"
get VER short

get CTYPELEN short
getdstring CTYPE CTYPELEN
get DATASTART long
get HEADSIZE long
get HEADCOUNT long
get UNKNOWN long
get UNKNOWN long
getdstring UNKNOWN 16

math gnpIndex = 0
math gnpRes = 0

for i = 1 to HEADCOUNT

  get INDEX long
  get PADDING char
  get NINDEXSKIP short # next header index = INDEX + 1 + NINDEXSKIP
                       # edit: it should be, but GP_PS2.LP.ARC
                       #       breaks this rule (!)
  get UNKNOWN short
  get PADDING char
  get POINTER long
  getdstring UNKNOWN 16

  math gnpIndex = i
  callfunction GetNextPointer
  # math gnpRes -= POINTER
  # clog INDEX POINTER gnpRes 0xFFFFF
  print "%INDEX% %POINTER% %gnpRes%" # broken scope, function doesn't set the global gnpRes variable 

next i

startfunction GetNextPointer
  savepos POS

  if gnpIndex == HEADCOUNT
    get NPOINTER asize
  else
    math TMP = gnpIndex
    math TMP *= HEADSIZE # 30
    math TMP += 48
    math TMP += 10 # skip to POINTER attribute
    goto TMP
    get NPOINTER long
  endif

  set gnpRes = NPOINTER
  goto POS
endfunction

```


the only issue is i can't remember how to force a function in quickbms to use the global scope!! other than that, it could work like that.

- wrs
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-13T18:14:25+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

Hm, how can I extract files with this script? I'm not that fond of compression algorithms, sorry.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-30T06:55:44+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

> Reply from AlphaTwentyThree
>
> Hm, how can I extract files with this script? I'm not that fond of compression algorithms, sorry.

i was waiting to hear from aluigi how to make functions use the global scope with quickbms   

so apparently you just chance this line:

```
callfunction GetNextPointer
```


to

```
callfunction GetNextPointer 1
```


and uncommented out the clog line and the line before. should be good
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-30T12:40:37+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

Thanks for your efforts! However, it doesn't work properly with the files I've uploaded. Could you check again please? Thanks!
## Post #8
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-12-30T12:59:37+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2012-09-30T04:05:04+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

Sorry for the necropost but I'm looking into unpacking the PS3 version files, but the script provided above doesn't seem to work on the .arc files

Is there any working one floating around?
## Post #10
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-07T03:39:34+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

> Reply from Panzah
>
> Sorry for the necropost but I'm looking into unpacking the PS3 version files, but the script provided above doesn't seem to work on the .arc files

Is there any working one floating around?

Is there a reason you'd want to unpack the ps3 files when xbox and PC files are so much easier to attain?
## Post #11
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2012-10-07T12:14:09+00:00
- Post Title: The Force Unleashed II PS3 - *.arc (zlib)

Yes actually, I do not have access to the XBOX versions files from the DLC, but I do have the PS3 version ones.
Namely the costume packs and Endor DLC, I'm fairly sure the files are the same across all platforms and only the archive in which they are contained are different.
My goal is to try and see if I can make the Endor DLC work with the PC version, assuming I can unpack the PS3 ver files first.
