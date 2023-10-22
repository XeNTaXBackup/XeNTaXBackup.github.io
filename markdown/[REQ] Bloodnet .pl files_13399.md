## Post #1
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-10-07T09:21:28+00:00
- Post Title: [REQ] Bloodnet .pl files

An old DOS game called BloodNet. Tried to search for .pl extension, and the clue I got was a program called BRL-CAD, but still couldn't view any of the files. Examples [here](https://cloud.mail.ru/public/Mxbs/mKATyydVQ).
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-10-10T02:59:20+00:00
- Post Title: [REQ] Bloodnet .pl files

I only found out a few things about file format.

file header:
uint16	- number of sprites
uint32	- address of spriteOffsetTable

spriteOffsetTable:
// for each sprite:
uint32	- address of sprite
char[8]	- sprite name

Between the header and the spriteOffsetTable are all the sprites.
The problem is that they are somehow compressed. I don't know which compression was used but maybe someone can tell from the histogram:



histogram.png (5.11 KiB) Viewed 72 times

All of the .pl files have a similar histogram like this one.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-10T07:22:47+00:00
- Post Title: [REQ] Bloodnet .pl files

(interesting thought with the histogram but I think we'd need an atlas of histograms for different compression algos
to decide which one might be used here)

In the pic of intrface.pl you see the bytes for menu1 (highlighted) and menu2 (from 0x6CBE to 6D46).



menu1,menu2.JPG (96.82 KiB) Viewed 68 times


It would help if we knew the plain text of menu1 and menu2.
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-10-10T15:01:39+00:00
- Post Title: [REQ] Bloodnet .pl files

menu4 is also interesting:

```
02 00 FF FF 02 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 10 00 10 00 03 00 00 DE 0F F9
```

format of a single sprite:

header (0x1C bytes):
0x01 byte: type (type = 2 in interface.pl, 3 in backgrn.pl)
0x01 byte: size of unknown extra data
0x14 bytes: unknown
0x02 bytes: width
0x02 bytes: height
0x02 bytes: size of compressed pixel data

the order of the 3 next lines is unknown:
var. bytes: compressed pixel data
var. bytes: unknown extra data
0x01 byte: unknown

if type == 3:
0x300 bytes: color table (256 colors, probably RGB888)
## Post #5
- Username: dragonzh
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jul 29, 2015 1:23 pm
- Post datetime: 2016-01-20T13:01:48+00:00
- Post Title: [REQ] Bloodnet .pl files

Maybe, image compression format .FLC helps.
## Post #6
- Username: dragonzh
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jul 29, 2015 1:23 pm
- Post datetime: 2016-01-20T13:16:39+00:00
- Post Title: [REQ] Bloodnet .pl files

footer unpack file contains a colors map.
[hellactu.rar](https://xentaxbackup.github.io/file/10340_hellactu.rar)
## Post #7
- Username: Pyhesty
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 16, 2017 7:21 pm
- Post datetime: 2017-08-16T13:39:26+00:00
- Post Title: [REQ] Bloodnet .pl files

> Reply from dragonzh
>
> footer unpack file contains a colors map.

 Hello!
 we are group from old-games.ru found function for unpack image from resourse pl file of game bloodnet
 hellactu.rar  - un/pack pl file to resourses
 but need unpack resourses to bmp image...
  for example, need unpack death1 resourse to bmp image
  may be are you have this utils? 
 thanks!
[INTRO.PL_TEXTS1.zip](https://xentaxbackup.github.io/file/13209_INTRO.PL_TEXTS1.zip)
## Post #8
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2017-08-23T18:59:27+00:00
- Post Title: [REQ] Bloodnet .pl files

> Reply from dragonzh
>
> Maybe, image compression format .FLC helps.
If this helps, the videos in this games are .flc files (plays in VLC).
