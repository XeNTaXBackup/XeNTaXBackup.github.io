## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-01T16:58:48+00:00
- Post Title: LZS compression

Hello, All!
Please help extract pac file.
I can't able to extract and uncompress from this game with quickbms.
4 Byte Header "add."
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-01T17:52:05+00:00
- Post Title: LZS compression

What game is this
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-01T18:08:26+00:00
- Post Title: LZS compression

xentax is so distracting   

anyway, heres a script which can recursively get every filename from every "add" block. theres only 2 levels in your sample, BUT IT CAN SUPPORT MORE   

to actually dump stuff, a check for the "lzs" blockid needs to be added to the if statement. not familiar with lzs so the data i did dump i had no idea was correct.

```
# quickbms script (wip)

math POINTER = 0
callfunction ProcessBlock

startfunction ProcessBlock
  goto POINTER
  savepos BASEPOS
  getdstring BLOCKID 4

  if BLOCKID == "add"

    get UNKNOWN long
    get HEADSIZE long
    get HEADERS long
    get UNKNOWN long
    get FILESIZE long
    get NULL long
    get NULL long

    for h = 1 to HEADERS
      get POINTER long
      get SIZE long
      get NULL long
      get NULL long
      get NAME string
      padding 4
      savepos CHEAD
      math POINTER += BASEPOS
      print "Processing: %NAME% @ %POINTER%"

      callfunction ProcessBlock
      goto CHEAD
    next h

  #elif BLOCKID == "lzs"
#    print "Awesome! But not ready to dump yet!"

  else
    print "Not sure how to handle %BLOCKID%"
  endif

endfunction

```


signing off for a few hours.
## Post #4
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-01T18:10:52+00:00
- Post Title: LZS compression

> Reply from chrrox
>
> What game is this
Pac file from Shinkon Gattai Godannar PS2
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-01T18:13:50+00:00
- Post Title: LZS compression

> Reply from WRS
>
> xentax is so distracting   

anyway, heres a script which can recursively get every filename from every "add" block. theres only 2 levels in your sample, BUT IT CAN SUPPORT MORE   

to actually dump stuff, a check for the "lzs" blockid needs to be added to the if statement. not familiar with lzs so the data i did dump i had no idea was correct.
Code: Select all# WRS, xentax.com
# quickbms script (wip)

math POINTER = 0
callfunction ProcessBlock

startfunction ProcessBlock
  goto POINTER
  savepos BASEPOS
  getdstring BLOCKID 4

  if BLOCKID == "add"

    get UNKNOWN long
    get HEADSIZE long
    get HEADERS long
    get UNKNOWN long
    get FILESIZE long
    get NULL long
    get NULL long

    for h = 1 to HEADERS
      get POINTER long
      get SIZE long
      get NULL long
      get NULL long
      get NAME string
      padding 4
      savepos CHEAD
      math POINTER += BASEPOS
      print "Processing: %NAME% @ %POINTER%"

      callfunction ProcessBlock
      goto CHEAD
    next h

  #elif BLOCKID == "lzs"
#    print "Awesome! But not ready to dump yet!"

  else
    print "Not sure how to handle %BLOCKID%"
  endif

endfunction


signing off for a few hours.

I appreciate your effort very much.

I'm very sorry, there is an error message on the monitor.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-01T18:16:41+00:00
- Post Title: LZS compression

What do you want to get out of this game? the character the sounds?
## Post #7
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-01T18:20:45+00:00
- Post Title: LZS compression

> Reply from chrrox
>
> What do you want to get out of this game? the character the sounds?
I want to character file.
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-01T22:23:17+00:00
- Post Title: LZS compression

> Reply from alon
>
> I'm very sorry, there is an error message on the monitor.

please read:

> Reply from WRS
>
> to actually dump stuff, a check for the "lzs" blockid needs to be added to the if statement. not familiar with lzs so the data i did dump i had no idea was correct.

i dont know how to decompress from the pointers. the missing blockids are deliberate.. as i said

anyone who can recognize lzs, go right ahead and see what you make of it
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-01T23:18:40+00:00
- Post Title: LZS compression

its most likely some custom ps2 lzss a lot of games did this its a real pain and thats why a lot of games were never looked into.
I tried quickbms but it does not seem to be anything implemented in it.
The structure seems to be
0x20 LZS header -- says its compressed
then the file name as a null terminated string
flag01 short
flag02 short
uncompressed size long
flag03 short
flag04 short
compressed size including header long
then i assume the data starts here.
I tried everything in quickbms using the bat file method and nothing gave readable data.
So the only way you will get those ps2 models is with a 3d ripper
or dump the model files from ram then reverse the model format.
## Post #10
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-02T02:34:23+00:00
- Post Title: LZS compression

Oops! Sorry!
It's a hard nut to crack.
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-02T03:30:05+00:00
- Post Title: LZS compression

its impossible to crack unless you reverse a ps2 emulator or you can rip the models the way i said.
## Post #12
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-11-30T05:15:32+00:00
- Post Title: LZS compression

PCSX2 sstates *.p2s file extracted the eeMemory.bin
I got some lcv & tim2 files.
I don't know where is model section.
Here's are some lcv & tim2 files.
## Post #13
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-18T21:09:37+00:00
- Post Title: LZS compression

!!!!!!!!!!!!!!

This is awesome!!!
I am trying to rip the models of the mechs from this game, I will attempt to locate my copy of the game and look at the file format. Lets keep this thread alive, this game has some awesome models, especially mecha models.
## Post #14
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-19T06:28:32+00:00
- Post Title: LZS compression

> Reply from kingfisher13
>
> !!!!!!!!!!!!!!

This is awesome!!!
I am trying to rip the models of the mechs from this game, I will attempt to locate my copy of the game and look at the file format. Lets keep this thread alive, this game has some awesome models, especially mecha models.
Thanks kingfisher13 interest in my problem.
[viewtopic.php?f=21&t=8341](http://forum.xentax.com/viewtopic.php?f=21&t=8341)
[viewtopic.php?f=16&t=7786](http://forum.xentax.com/viewtopic.php?f=16&t=7786)
I am turning to you for help
## Post #15
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-19T18:35:49+00:00
- Post Title: LZS compression

It would be better to use 3d Ripper DX to rip the models from the game, maybe someone could help us out with that?
I know it can be done, it has been done before. The problem usually with that is the models come out skewed.

EDIT:
I would also try to contact the owner of this site: 
```
http://ps23dformat.wikispaces.com/How+To+Extract+Models
```

He is working on ripping models from PS2 games, using hex editor. I have contacted him already about this game, maybe he can help.
