## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-06-12T23:19:20+00:00
- Post Title: Oneechanbara vorteX (CAT&BIN Info)

in response to a pm.

```
#    xentax.com
#    .cat BMS script (Oneechanbara vorteX)

endian big

for i = 0

  get FPOINTER long

  if FPOINTER == -1
    cleanexit
  endif

  get FSIZE long

  log "" FPOINTER FSIZE

next
```


```
#    xentax.com
#    .bin BMS script (Oneechanbara vorteX)

endian big

get FILES long

for i = 1 to FILES

  get pFile1 long
  get pFile2 long
  get pEOF long

  if pFile2 == -1

    math sFile1 = pEOF
    math sFile1 -= pFile1

    log "" pFile1 sFile1

  else

    if pEOF == -1

      math sFile1 = pFile2
      math sFile1 -= pFile1

      log "" pFile1 sFile1

      savepos Pos
      get nextFile long
      goto Pos

      math sFile2 = nextFile
      math sFile2 -= pFile2

      log "" pFile2 sFile2

    else

      math sFile1 = pFile2
      math sFile1 -= pFile1

      log "" pFile1 sFile1

      math sFile2 = pEOF
      math sFile2 -= pFile2

      log "" pFile2 sFile2

    endif

  endif
  
next i
```
## Post #2
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-13T19:49:53+00:00
- Post Title: Oneechanbara vorteX (CAT&BIN Info)

> Reply from WRS
>
> in response to a pm.
Code: Select all# -- WRS
#    xentax.com
#    .cat BMS script (Oneechanbara vorteX)

endian big

for i = 0

  get FPOINTER long

  if FPOINTER == -1
    cleanexit
  endif

  get FSIZE long

  log "" FPOINTER FSIZE

next
Code: Select all# -- WRS
#    xentax.com
#    .bin BMS script (Oneechanbara vorteX)

endian big

get FILES long

for i = 1 to FILES

  get pFile1 long
  get pFile2 long
  get pEOF long

  if pFile2 == -1

    math sFile1 = pEOF
    math sFile1 -= pFile1

    log "" pFile1 sFile1

  else

    if pEOF == -1

      math sFile1 = pFile2
      math sFile1 -= pFile1

      log "" pFile1 sFile1

      savepos Pos
      get nextFile long
      goto Pos

      math sFile2 = nextFile
      math sFile2 -= pFile2

      log "" pFile2 sFile2

    else

      math sFile1 = pFile2
      math sFile1 -= pFile1

      log "" pFile1 sFile1

      math sFile2 = pEOF
      math sFile2 -= pFile2

      log "" pFile2 sFile2

    endif

  endif
  
next i

anyone upto cracking the TGF format? I want to put models into (DREAM C CLUB).
## Post #3
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2010-06-14T07:56:35+00:00
- Post Title: Oneechanbara vorteX (CAT&BIN Info)

I think you better ask for Surveyor, author of TGF to Collada DAE converter [download/file.php?id=2979](http://forum.xentax.com/download/file.php?id=2979) - he must know all (or almost) about TGF!

P.S: Mega THANKS to WRS for scripts!!!
## Post #4
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-23T02:53:07+00:00
- Post Title: Oneechanbara vorteX (CAT&BIN Info)

The contents of this post was deleted because of possible forum rules violation.
