## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-30T21:54:15+00:00
- Post Title: Runaway A Road Adventure

Hi all!
Sorry, can you help extract resources from that game?
Or that utilit is already exist?
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-01-31T11:53:23+00:00
- Post Title: Runaway A Road Adventure

Hi there,

I don't know of any extractors for this game, so maybe we can make something for you. If you could attach a small archive used in the game, then we may be able to write a script for you. Please zip up an archive and attach it to the message boards here, or email it to one of us if it is small enough (max 4MB).

Thanks, I hope we can help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: NECHAST
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-31T16:21:43+00:00
- Post Title: Runaway A Road Adventure

I have sent you the letter. I hope you can help.
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-01T13:19:38+00:00
- Post Title: Runaway A Road Adventure

Hi again,

Thanks for the email. I took a look at the files and this is my conclusion...

The *.003 file does not look like an archive. There are 2 possibilities - either the archive is encrypted (highly unlikely from the look of it) or there is another file that contains the directory information. Have a look in the directory that has the *.003 file and see if you can find a small file with the same name and different extension. For example, if the file is Resource.003, the could be a file called Resource.dir or Resource.bin or something similar. If there is a file like this, please attach it to the forums here or email it to me - it will probably only be a few Kbs in size.

The *.m02 file probably is an archive, but it worries me that there are so many repeating file offsets. However the structure of the file does seem to indicate that it is an archive, therefore I have the specs here...

```
  4 - File Offset

X - null padding to offset 400

// NOTES:
// The first offset is 0, indicating the offset to the file start
// The last offset is the archive size, indicating the file end
// The offsets in between are file offsets, but some offsets are repeated (just ignore the repeats)
// Stop reading the directory when you read an offset that is the archive size
```


Mr Mouse may be able to whip up a quick script for this so that you can run it in MultiEx Commander (Mr Mouse: not sure if you can remove the repeats using your scripting language) . If not, I will try to make a plugin for my archive editing program so you will be able to use it.

Thanks mate,

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: NECHAST
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-01T17:46:42+00:00
- Post Title: Runaway A Road Adventure

Thank you very much!  
Check up your mail...

Yes. Looks like the *.m02  content differ from *.003. The compression ratio of *.m02 is more lower than *.003. This bad, it may be realy encrypted...
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-02T11:56:30+00:00
- Post Title: Runaway A Road Adventure

Hi again,

Thanks for the list of files - it would probably be safe to assume that each of the different file types in this game are either single resources, or small archive groups. For example, *.aXX files would be animations, *.mXX for music, *.gXX for graphics, *.sXX for sound effects, etc. The *.0XX files may be from the installation of the game?

Anyway, I would assume that each of the small archives have a similar format which follows the structure in the post above, but it is also possible that they are just separate files (ie not archives at all).

I will try and write a plugin for you, and see if it works on some of the files you sent.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-02T12:22:01+00:00
- Post Title: Runaway A Road Adventure

Well, as I did not recieve any archives, I can't check any putative script I write.
## Post #8
- Username: NECHAST
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 02, 2005 9:55 pm
- Post datetime: 2005-02-02T14:50:48+00:00
- Post Title: Runaway A Road Adventure

To: friendsofwatto Yes. It's about 100% that is simply small groups of archives... But *.0XX files not for install. The Install just copy some RESUORCE.XXX (it's depend from install type). This game is about 1997 year release, or something... So she very old for something cool install =))

To: Mr.Mouse I send you attachment, but I'am not sure that is added. Please give me your mail, it would be easy =)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-02T15:14:24+00:00
- Post Title: Runaway A Road Adventure

[http://multiex.xentax.com/](http://multiex.xentax.com/)

There you will find the address. 

OR, look at my profile.
## Post #10
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-04-06T11:50:46+00:00
- Post Title: Runaway A Road Adventure

Hi!

This game has a Hungarian translation... a really-really bad one. I would like to fix major translation problems and maybe mod the game (change some graphics, remaking voiceover), but I couldn't found the files' purposes and the way of extracting them, only for some music/sound effects.

Here's a list of files in the Resource directory:

```
2001.05.14.  14:41       108 761 688 Resource.001
2003.02.04.  17:30         4 662 550 RESOURCE.002
2003.06.16.  17:15         7 340 291 RESOURCE.003
2003.06.27.  10:02           335 436 RESOURCE.004
2003.06.26.  17:05        26 400 433 RESOURCE.A00
2006.12.22.  09:14        10 359 734 RESOURCE.A01
2003.03.04.  11:44        13 327 209 RESOURCE.A02
2003.06.26.  17:38           343 040 RESOURCE.A03
2006.12.22.  10:48        18 292 881 RESOURCE.B01
2001.06.20.  17:00         8 161 628 RESOURCE.B02
2001.06.20.  17:00         4 436 619 RESOURCE.B06
2001.06.20.  17:00         5 832 845 RESOURCE.B08
2001.06.20.  17:00         4 526 257 RESOURCE.D03
2001.06.20.  17:00        18 688 829 RESOURCE.D05
2001.06.20.  17:00        10 608 998 RESOURCE.D06
2001.06.20.  17:00        20 326 098 RESOURCE.D07
2001.06.20.  17:00         1 426 006 RESOURCE.D09
2001.06.20.  17:00        18 716 513 RESOURCE.D10
2001.06.20.  17:00         3 298 476 RESOURCE.D14
2003.06.27.  17:40         2 549 209 RESOURCE.E01
2000.08.30.  12:34         2 140 381 RESOURCE.E02
2001.01.29.  12:13        41 872 288 RESOURCE.E03
2000.08.22.  19:17        12 615 737 RESOURCE.E04
2000.06.28.  17:57         3 756 532 RESOURCE.E05
2001.05.18.  18:34        24 043 532 Resource.e06
2000.06.27.  10:46         5 855 030 RESOURCE.E07
2000.07.03.  11:38        10 998 797 RESOURCE.E08
2001.06.18.  11:32        36 687 596 RESOURCE.E10
2001.05.18.  18:36         8 356 407 RESOURCE.E11
2000.12.12.  13:01         8 825 221 RESOURCE.E13
2000.12.07.  13:58        24 862 465 RESOURCE.E14
2001.05.18.  18:38        23 049 037 RESOURCE.E16
2001.06.11.  20:38         9 572 218 RESOURCE.E17
2000.08.03.  17:02         5 697 710 RESOURCE.F03
2001.05.18.  18:47        13 299 932 RESOURCE.F08
2001.06.15.  14:09        22 286 807 RESOURCE.F09
2001.05.18.  18:48         3 772 662 RESOURCE.F13
2001.06.12.  20:05         8 125 273 RESOURCE.F18
2001.05.25.  14:18         2 180 155 RESOURCE.F19
2001.06.15.  16:45         5 796 701 RESOURCE.F20
2001.06.15.  17:02         2 725 679 RESOURCE.F21
2001.06.11.  14:32         3 088 610 RESOURCE.F22
2001.06.15.  17:03         3 320 406 RESOURCE.F24
2001.05.18.  19:28         8 338 435 RESOURCE.F25
2001.05.18.  19:31        22 106 732 RESOURCE.F26
2001.05.18.  19:34         1 276 622 RESOURCE.F27
2001.05.18.  19:35         1 411 176 RESOURCE.F28
2001.05.29.  14:42        44 596 303 RESOURCE.F29
2001.05.18.  19:51        64 829 865 RESOURCE.F30
2003.06.27.  18:10         1 338 058 RESOURCE.F35
2001.05.25.  14:11         4 217 670 RESOURCE.F37
2000.08.11.  18:48         8 783 550 RESOURCE.F39
2001.06.12.  21:44         7 620 590 RESOURCE.G01
2001.06.20.  08:55        21 760 876 RESOURCE.G02
2001.06.05.  11:35         8 950 522 RESOURCE.G03
2001.05.18.  19:56        12 129 845 RESOURCE.G04
2001.05.18.  19:57         2 535 706 RESOURCE.G05
2001.06.07.  18:27        50 720 460 RESOURCE.H09
2001.05.18.  20:02        13 381 158 RESOURCE.H10
2001.05.18.  20:03         6 025 142 Resource.h13
2001.06.12.  20:06         8 815 999 Resource.h18
2001.05.25.  14:19         2 105 071 RESOURCE.H19
2001.06.15.  17:00        11 114 598 RESOURCE.H20
2001.05.18.  20:04         2 725 679 RESOURCE.H21
2001.06.11.  14:35         9 147 346 RESOURCE.H22
2001.05.21.  18:50        23 351 498 Resource.h23
2001.06.15.  17:04         7 390 072 RESOURCE.H24
2001.05.18.  20:13        22 083 268 RESOURCE.H26
2001.05.29.  14:43         2 145 574 RESOURCE.H29
2001.06.18.  19:27        18 857 241 RESOURCE.H30
2003.06.27.  18:11         1 267 947 RESOURCE.H35
2001.05.25.  14:12         8 002 347 RESOURCE.H37
2001.06.11.  18:56        16 862 171 RESOURCE.H38
2001.05.18.  20:26        11 731 689 RESOURCE.H40
2001.05.18.  20:32         1 372 985 RESOURCE.H41
2001.05.18.  20:30        17 015 799 RESOURCE.H42
2001.03.26.  21:23         5 017 365 RESOURCE.I01
2001.03.26.  20:42        17 786 694 RESOURCE.I03
2002.10.16.  18:49        37 260 196 RESOURCE.M01
2001.06.20.  17:00        27 133 024 RESOURCE.M02
2001.06.18.  15:09        39 773 656 Resource.m03
2002.10.17.  12:29        64 897 560 Resource.m04
2001.06.13.  10:13        19 234 708 Resource.m05
2001.06.19.  20:52        92 776 260 Resource.m06
2001.06.20.  17:00         7 441 880 RESOURCE.S01
2001.06.20.  17:00         4 589 890 RESOURCE.S02
2001.06.15.  18:21         7 117 156 Resource.s03
2001.06.18.  12:25         8 615 994 Resource.s04
2001.06.19.  15:18         3 679 288 Resource.s05
2001.06.17.  13:23        12 032 716 Resource.s06
```


Content of Dataa directory:

```
2003.06.16.  17:09        12 387 032 DATAACA1.000
2003.06.16.  17:09        29 323 290 DATAACA2.000
2003.06.16.  17:09        40 377 586 DATAACA3.000
2003.06.16.  17:09        71 379 111 DATAACA4.000
2003.06.16.  17:09        12 201 792 DATAACA5.000
2003.06.16.  17:09        85 933 920 DATAACA6.000
```


Content of Datav directory:

```
2012.04.06.  12:30        16 961 632 DATAVA02.001
2012.04.06.  12:42           299 948 DATAVB01.000
2012.04.06.  12:43         8 095 676 DATAVB01.001
2012.04.06.  12:57           599 148 DATAVB02.000
2012.04.06.  12:59         5 000 972 DATAVB02.001
2012.04.06.  12:59           463 848 DATAVB02.002
2012.04.06.  12:59        13 002 260 DATAVB02.003
2012.04.06.  12:59         2 500 304 DATAVB02.004
2012.04.06.  12:46         1 901 064 DATAVB03.001
2012.04.06.  12:32         7 035 560 DATAVB04.001
2012.04.06.  12:52        16 814 092 DATAVB05.001
2012.04.06.  12:57        23 778 940 DATAVB06.001
2012.04.06.  12:59           899 428 DATAVB07.000
2012.04.06.  13:00         5 681 832 DATAVB07.001
2012.04.06.  12:32           899 520 DATAVB08.000
2012.04.06.  12:34        72 443 992 DATAVB08.001
2012.04.06.  12:35         3 860 308 DATAVB09.000
2012.04.06.  12:38        42 713 996 DATAVB09.001
2012.04.06.  12:38           626 396 DATAVB09.002
2012.04.06.  12:38         1 376 268 DATAVB09.003
2012.04.06.  12:38           625 272 DATAVB09.004
2004.02.16.  19:34           177 426 DATAVC00.000
2012.04.06.  13:02         1 774 752 DATAVD01.000
2012.04.06.  13:05         4 001 152 DATAVD01.001
2012.04.06.  13:05           891 656 DATAVD01.002
2012.04.06.  13:07         3 401 100 DATAVD02.001
2004.02.16.  19:33         4 401 144 DATAVD03.001
2004.02.16.  19:33         1 901 128 DATAVD04.001
2012.04.06.  13:01           599 552 DATAVD05.000
2012.04.06.  13:01        22 417 824 DATAVD05.001
2004.02.16.  19:33         9 676 868 DATAVD06.001
2004.02.16.  19:33           600 976 DATAVD07.000
2004.02.16.  19:33         5 691 660 DATAVD07.001
2004.02.16.  19:33           150 128 DATAVD08.000
2004.02.16.  19:33         1 462 724 DATAVD08.001
2004.02.16.  19:33           299 548 DATAVD09.000
2004.02.16.  19:33         3 132 332 DATAVD09.001
2004.02.16.  19:33           150 212 DATAVD10.000
2004.02.16.  19:33         3 275 264 DATAVD10.001
2004.02.16.  19:33         6 526 004 DATAVE01.001
2004.02.16.  19:33           987 948 DATAVE02.000
2004.02.16.  19:33        33 263 228 DATAVE02.001
2004.02.16.  19:33         8 976 896 DATAVE03.001
2004.02.16.  19:33         3 501 420 DATAVE04.001
2004.02.16.  19:33         5 526 128 DATAVE05.001
2004.02.16.  19:33           299 480 DATAVE06.000
2004.02.16.  19:33         4 675 604 DATAVE06.001
2004.02.16.  19:33           599 792 DATAVF01.000
2004.02.16.  19:33        47 964 116 DATAVF01.001
2004.02.16.  19:33         3 237 584 DATAVF02.000
2004.02.16.  19:33        63 492 508 DATAVF02.001
2004.02.16.  19:33         6 652 280 DATAVF03.001
2004.02.16.  19:33         7 912 776 DATAVG01.001
2004.02.16.  19:33        21 779 172 DATAVG02.001
2004.02.16.  19:33           752 880 DATAVG03.000
2004.02.16.  19:33        22 580 360 DATAVG03.001
2004.02.16.  19:33           150 092 DATAVG04.000
2004.02.16.  19:33         1 652 052 DATAVG04.001
2004.02.16.  19:33           829 252 DATAVH01.001
2004.02.16.  19:33         1 400 536 DATAVH02.001
2004.02.16.  19:33         1 025 492 DATAVH03.001
2004.02.16.  19:33           753 512 DATAVH04.000
2004.02.16.  19:33        14 007 352 DATAVH04.001
2004.02.16.  19:33           461 772 DATAVH04.002
2004.02.16.  19:33         6 026 496 DATAVH04.003
2004.02.16.  19:33         5 976 484 DATAVH04.004
2004.02.16.  19:33         3 001 096 DATAVH04.005
2004.02.16.  19:33         3 151 944 DATAVH04.006
2004.02.16.  19:33         6 276 400 DATAVH04.007
2004.02.16.  19:33         1 026 604 DATAVH04.008
2004.02.16.  19:33         4 101 444 DATAVH05.001
2004.02.16.  19:33         4 102 068 DATAVH06.001
2004.02.16.  19:33           746 500 DATAVH07.000
2004.02.16.  19:33         2 794 228 DATAVH07.001
2004.02.16.  19:33           901 872 DATAVH08.000
2004.02.16.  19:33        25 876 636 DATAVH08.001
2004.02.16.  19:33           229 920 DATAVH08.002
2004.02.16.  19:33           450 592 DATAVH09.000
2004.02.16.  19:33         2 650 648 DATAVH09.001
2004.02.16.  19:33        59 817 696 DATAVI01.001
2004.02.16.  19:33         2 199 808 DATAVI02.000
2004.02.16.  19:33        18 309 056 DATAVI02.001
2004.02.16.  19:33           750 208 DATAVI03.000
2004.02.16.  19:33        21 006 948 DATAVI03.001
2004.02.16.  19:33           233 536 DATAVI03.002
2004.02.16.  19:34        76 742 920 DATAVI04.001
```


There's also a binkw32.dll in the game's main directory so it uses Bink Video.
## Post #11
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-24T09:47:46+00:00
- Post Title: Runaway A Road Adventure

extract runaway result big mp3 file and i look for cutter or another way for extract them thanks
