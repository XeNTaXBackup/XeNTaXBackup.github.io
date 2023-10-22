## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-19T20:19:35+00:00
- Post Title: D. Gray-man PS2

I'm not sure if there are some standards for packing PS2 data.
There's an ELF file, but don't know if that contains anything I need. There are a bunch of strings in the ELF file though, so it might be needed.

File table at the top followed by data, but I don't see anything that looks like sizes or offsets, or number of files even.

```
   int32 ?
   int32 ?
   char[56] string
}

```


The data is not compressed or encrypted, I'm just not sure how it is structured.

You can see that the data is stored in 4 separate archives (don't think they are related, and is grouped based on types of files (sounds, pictures, etc)

Here's what the top of one of the archives look like



PM for samples.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-19T22:23:31+00:00
- Post Title: D. Gray-man PS2

there are offsets I think, but must be scaled by 0x800. if you look at the full file you will see most data starts at an 0x800 boundary.

look at offset 0xF7C0 and read 0x754D.
for that file, multiply 0x754D by 0x800 and you get 0x3AA6800.
go to 0x3AA6800 and you will see the start of the data for that file.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-19T23:24:47+00:00
- Post Title: D. Gray-man PS2

Oh, that's an interesting way to look at it. It was kind of odd that the first integer for each entry was pretty much increasing linearly, while there was a whole bunch of null bytes everywhere in the data portion. I guess the data is rather spread out, seeing how I compressed the archive to 15% original size.

I wonder if a lot of PS2 games are bloated this way lol

I guess the number of files is determined by (first offset * 0x800) / 64, which should be fine since the entries appear to be listed sequentially anyways. Even if there are less files than that, at least I'm not MISSING files.

```

# get number of files
# assumes the first entry is the first file stored in the archive
get FILES long
math FILES *= 0x800
math FILES /= 64

# parse entries
goto 0
for i = 0 < FILES
  get OFFSET long
  get SIZE long
  getdstring NAME 56
  
  math OFFSET *= 0x800
  log NAME OFFSET SIZE
next i

```


This version assumes there are ALWAYS null bytes after the last entry. That means the offset I read will be 0, which is impossible for a valid data file.

```

# just keep parsing
for i = i
  get OFFSET long
  if OFFSET == 0
    cleanexit
  endif
  get SIZE long
  getdstring NAME 56
  
  math OFFSET *= 0x800
  log NAME OFFSET SIZE
next i

```


Now to figure out the TIPS image format(s), which don't look TOO bad except the fact that a single TIPS file may contain dozens of images (I guess it's like storing a series of images to form an animation)
