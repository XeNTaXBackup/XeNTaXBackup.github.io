## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-10-23T12:44:42+00:00
- Post Title: Smash Cars .tbl file

Hello everyone!
Is there anyone who can suggest a program for the attached .tbl file or can someone please make a decoder & encoder for it please?

 common.rar
(11.84 KiB) Downloaded 20 times
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-28T16:51:10+00:00
- Post Title: Smash Cars .tbl file

for some reason my quickbms script wont treat the block names as strings (     ) but before i bother writing this up

1 - this is a language file - xentax has a translation section now
2 - try editing one of the strings in a hex editor and testing it. the table index has either a string id or hash

```

math HASSTRS = 0

for i = 1
  get BLOCKNAME long #getdstring BLOCKNAME 4
  get BLOCKSIZE long

#  print "Block: %BLOCKNAME%\nSize:  %BLOCKSIZE%"

  if BLOCKNAME == 1129468740 # "DSRC"
    # unicode string table

    # no point looping, offsets are static
    math HASSTRS = 1

  elif BLOCKNAME == 1129468749 # "MSRC"
    # string info table

    get STRS long
    get STRUCTSIZE long

    if STRUCTSIZE != 12
      print "unsupported string info table format"

      # language file, so no point skipping data (??)
      cleanexit
    endif

    for s = 0 < STRS
      get STRUNKNOWN long # string id?
      get STRDUMMY long
      get STROFF long
    next s

    print "processed %STRS% strings"

  else
    math BLOCKSIZE -= 8 # size of name (4) + size flag (4)
    math BLOCKSIZE x 4 # alignment
    getdstring DUMMY BLOCKSIZE
  endif

  savepos POS
  if POS == SIZE
    print "Done. Found %i% sections."
    cleanexit
  endif
next i

```
## Post #3
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-11-20T15:11:47+00:00
- Post Title: Smash Cars .tbl file

Now i tested the hex editing and it works fine.  So please try to finish this script, thank you so much!
## Post #4
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2011-11-24T14:27:36+00:00
- Post Title: Smash Cars .tbl file

> Reply from hunpatrik
>
> Now i tested the hex editing and it works fine.  So please try to finish this script, thank you so much!

can u tell me how to do that ? do u hex that by one word or .. ?
## Post #5
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-11-24T15:34:20+00:00
- Post Title: Smash Cars .tbl file

I didn't get what you mean, but i used xvi32 for editing. In the file the chars of a text in every second hex code for example: Options-> O p t i o n s (the spaces are 00 in hex) so i just modified it to A b c d e f g. And it worked, but if you would like to translate it, i didn't recommend this way. Just wait for a tool. Maybe someone help us.
## Post #6
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2011-11-25T18:49:42+00:00
- Post Title: Smash Cars .tbl file

> Reply from hunpatrik
>
> I didn't get what you mean, but i used xvi32 for editing. In the file the chars of a text in every second hex code for example: Options-> O p t i o n s (the spaces are 00 in hex) so i just modified it to A b c d e f g. And it worked, but if you would like to translate it, i didn't recommend this way. Just wait for a tool. Maybe someone help us.

ahh damn i want to translate in to mongolian but by one word its just impossible
