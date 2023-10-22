## Post #1
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-12-09T10:36:47+00:00
- Post Title: aqua digger 3d dat file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-10T17:50:06+00:00
- Post Title: aqua digger 3d dat file

```
get UNKNOWN long   # not sure
get DPOINT long    # pointer to start of structures
get FCOUNT long    # file count

goto DPOINT

for i = 1 to FCOUNT
  get FNPOINT long  # filename pointer
  get UNKNOWN long  # ??
  get NFPOINT long  # pointer to end of data / next struct
  get FSIZE long    # decompressed size
  get FZSIZE long   # compressed size
  goto FNPOINT      # just skips 2 null bytes
  get FNAME string  # filename! 
  savepos FOFFSET

  if FZSIZE == FSIZE
    log FNAME FOFFSET FSIZE
  else
    clog FNAME FOFFSET FZSIZE FSIZE
  endif

  goto NFPOINT
next i

```
## Post #3
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-12-10T21:23:57+00:00
- Post Title: aqua digger 3d dat file

thanks the script works i have such question
what it are for commands: get UNKNOWN long, get DPOINT long, get FCOUNT long etc?
these commands was not in instruction to quickbms I did not know that files location there is after names files
I hope you write back to mi
one more thing:
what from theme kao the kangaroo adp music file?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-11T21:37:03+00:00
- Post Title: aqua digger 3d dat file

> Reply from Bogus
>
> thanks the script works i have such question
what it are for commands: get UNKNOWN long, get DPOINT long, get FCOUNT long etc?
these commands was not in instruction to quickbms I did not know that files location there is after names files
I hope you write back to mi
one more thing:
what from theme kao the kangaroo adp music file?

quickbms.txt explains the functions, but to break it down even further:

```
get [b]FCOUNT [/b]long
```

FCOUNT is the variable name i assign to the result of the 'get' command

```
get FCOUNT [b]long[/b]
```

long is the type of data (long = integer = 32 bits)
## Post #5
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-12-12T10:00:51+00:00
- Post Title: aqua digger 3d dat file

what from adp files?
I would like to convert on wav
the point is that I want to listen to music not only in the game but also outside the game
long this I know what it is that 4 bytes
interesting whether mi write back
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-12T21:02:00+00:00
- Post Title: aqua digger 3d dat file

> Reply from Bogus
>
> what from adp files?
I would like to convert on wav
the point is that I want to listen to music not only in the game but also outside the game
long this I know what it is that 4 bytes
interesting whether mi write back

i was just trying to explain what i thought you were asking. translated english isn't an ideal way to communicate.
your adp files i don't care about. if i did, i would be posting in one of the threads you created for it. please understand that. no more pms please!
## Post #7
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-12-12T22:01:50+00:00
- Post Title: aqua digger 3d dat file

probably nothing you can do
injury
what do you suggest?
I would like to have this music
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-01-17T01:25:04+00:00
- Post Title: aqua digger 3d dat file

The music files are MO3 files.

Basically they are a newer version of the old tracker modules similar to those used in DOS games combined with the MP3 codec.

I've ripped and converted the music for you into FLAC and I'll post a link later on in the week for you.

For future reference, MO3 files can be played with XMPlayer.
