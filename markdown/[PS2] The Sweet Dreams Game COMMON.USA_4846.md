## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-05T13:13:16+00:00
- Post Title: [PS2] The Sweet Dreams Game COMMON.USA

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-08-09T05:52:52+00:00
- Post Title: [PS2] The Sweet Dreams Game COMMON.USA

Anyone, please?
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-09T18:24:26+00:00
- Post Title: [PS2] The Sweet Dreams Game COMMON.USA

mat/tex extractor from the mat file provided.
not sure the extracted files are complete though (may need the signatures added back)

```
#    xentax.com
#    .mat BMS script

get FSIZE asize

for

  getdstring rTYPE 4
  get rSIZE long

  savepos POS

  set STMP string POS

  if rTYPE == "MATF" then

    # this just stores the number of files for each file type
    # as it may not always just store 2 and we don't need them, i left it out

    # from the sample:
    #  number of MAT files, number of TEX files

  elif rTYPE == "MAT " then

    string STMP += ".MAT"
    log STMP POS rSIZE

  elif rTYPE == "TEX " then

    string STMP += ".TEX"
    log STMP POS rSIZE

  endif

  math POS += rSIZE
  goto POS

  if POS == FSIZE then

    cleanexit

  endif

next

```
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-09T20:28:05+00:00
- Post Title: [PS2] The Sweet Dreams Game COMMON.USA

part 2 

i got the feeling this file wasn't meant to be split (as in, parsed as one).

if you find anything that can view these files, post a link to it for us.



```
#    xentax.com
#    .usa BMS script


# -- header (56 bytes)

idstring "RKET"

goto 0x10
get pEKO_FILES long

goto 0x20
get cVAG long
get cEKO long
get cOther1 long
get cOther2 long

goto 56 # end of header

# -- end header

set tmp long cOther1
math tmp += cOther2
print "Expecting %cVAG% VAG\nExpecting %cEKO% EKO\nIgnoring %tmp% (%cOther1%+%cOther2%) others"

# -- VAG files

for v = 1 to cVAG

  ## header 1 (8 bytes)

  get totVSize long # total size (including header 2)
  get unknown long

  ## header 2 (16 bytes)

  get VSize long # actual size
  getdstring unknown 12

  savepos POS
  set STMP string POS
  string STMP += ".vag"
  
  log STMP POS VSize

  math POS += VSize
  goto POS

next v

# -- EKO files

for e = 1 to cEKO

  get ESize long
  idstring "EKO\x00" # parsing purposes only

  savepos POS
  set STMP string POS
  string STMP += ".eko"
  
  log STMP POS ESize

  math POS += ESize
  goto POS

next e

# -- Other1

for other = 1 to cOther1

  get OSize long
  get unknown long

  # not dumping this
  # the data is so bitty

  savepos POS

  math POS += OSize
  goto POS

next other

# -- Other2

for other = 1 to cOther2

  get OSize long
  get blank long

  # not dumping this either

  savepos POS

  math POS += OSize
  goto POS

next other

get FSize asize




if FSize == POS then

  print "Success!"

endif

```
