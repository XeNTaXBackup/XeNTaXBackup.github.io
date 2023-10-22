## Post #1
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-10-01T22:23:51+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

Somebody can make a bms script for unpacking?
Here is a sample - [bigfile.7z (122.47 MB)](http://www.multiupload.com/I0I6MNIGNV)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-02T18:18:04+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

+1
## Post #3
- Username: JBieber
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2010 1:01 am
- Post datetime: 2010-10-03T02:38:25+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

+1 and plus packer or tool to edit text please   
Edit: UnpackTRU tool (by Dusan) not works for tomb raider GOL bigfile.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-04T15:12:57+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

are there any smaller files with the client? the data is aligned to 2048 blocks (dvd) but missing filenames, pointers and sizes. you can sort of parse it, but its missing that other file!

uh, example:

```

get SIZE asize

for
  set NEXTBLOCK long 0x800
  math NEXTBLOCK *= i

  if NEXTBLOCK >= SIZE
    cleanexit
  endif

  goto NEXTBLOCK

  get SIGN long

  if SIGN == 0x4D524443 # CDRM, for example
    getdstring UNKNOWN 4 # 0
    get HEADCOUNT long
    math HEADCOUNT *= 8 # int, int ? second maybe flags
    getdstring UNKNOWN HEADCOUNT

    get UNKNOWN long # total size?

   # then padded to 16
  # standard compressed data is packed in here. w/o padding for number of HEADCOUNT

  endif

  math i += 1

next

```


if not, we can compare the other tr games made by the same studio.
## Post #5
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-10-30T13:36:28+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

> Reply from JBieber
>
> +1 and plus packer or tool to edit text please   
Edit: UnpackTRU tool (by Dusan) not works for tomb raider GOL bigfile.

UnpackTRU tool Version 3.96 works good for me for PC version.
When you extract all, Be care, too many files may crash your explorer.

UnpackTRU tool for guardian light does not work for me. Just normal UnpackTRU works for me.
But it is really hard to find which file is for Lara!
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-30T13:51:34+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

This post if for all the times I spend time on one of this silly threads to be ignored in favor of some closed source tool. It defeats the point of using XeNTaX to share knowledge and utterly wastes my time.
## Post #7
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-10-30T14:11:09+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

> Reply from WRS
>
> This post if for all the times I spend time on one of this silly threads to be ignored in favor of some closed source tool. It defeats the point of using XeNTaX to share knowledge and utterly wastes my time.

UnpackTRU released source too!
It's not closed source tool.

I am just newbie here. I am just telling what i know. that's all.
## Post #8
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-11-01T06:45:19+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

Try this...
[UnpackTRU1.0GoL.zip](https://xentaxbackup.github.io/file/3571_UnpackTRU1.0GoL.zip)
## Post #9
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2019-01-10T13:47:25+00:00
- Post Title: [PC] Lara Croft and the Guardian of Light - bigfile.00*

This program does not work with me, but it should be a newer version, only the links no longer work.
