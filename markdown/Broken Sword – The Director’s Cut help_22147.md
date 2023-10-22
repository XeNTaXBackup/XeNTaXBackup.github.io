## Post #1
- Username: ellonh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 18, 2019 2:06 am
- Post datetime: 2020-05-14T20:19:00+00:00
- Post Title: Broken Sword – The Director’s Cut help

I am in need of help to extract and import the files of this game more precisely the file with that name and extension bs1dc.dat that I am not finding anywhere, so I would like to know if anyone can help me, I have already seen some posts on the forum older ones are not taking the only scripct that I found from this game and for that menu_gfx.dat file then I put the codes down here.
## Post #2
- Username: ellonh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 18, 2019 2:06 am
- Post datetime: 2020-05-14T20:19:54+00:00
- Post Title: Broken Sword – The Director’s Cut help

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "RARC"
get FILES long

for i = 0 < FILES
getdstring NAME 0x40
get OFFSET long
get SIZE long
log NAME OFFSET SIZE
next i
```
## Post #3
- Username: ellonh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 18, 2019 2:06 am
- Post datetime: 2020-05-14T20:24:00+00:00
- Post Title: Broken Sword – The Director’s Cut help

I need this for a translation of the game into my native language, the only translation I found for this game is in Hungarian, which was the one I saw that it was possible to do a translation for this game. here is the link for the translation I found: [https://magyaritasok.hu/magyaritasok/br ... -cut-/1442](https://magyaritasok.hu/magyaritasok/broken-sword-the-shadows-of-the-templar/broken-sword-shadow-of-the-templars-directors-cut-/1442)

I hope I'm not doing something contrary to the forum rule
## Post #4
- Username: damra74
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 01, 2020 9:55 pm
- Post datetime: 2020-11-01T14:01:27+00:00
- Post Title: Broken Sword – The Director’s Cut help

> Reply from ellonh ↑Fri May 15, 2020 4:19 am at Fri May 15, 2020 4:19 am
>
> 
Code: Select all# Revolution obb (dat) archives
# script for QuickBMS http://quickbms.aluigi.org

idstring "RARC"
get FILES long

for i = 0 < FILES
getdstring NAME 0x40
get OFFSET long
get SIZE long
log NAME OFFSET SIZE
next i

Unfortunatelly I can not translate by this code:
  offset   filesize   filename
--------------------------------------

- signature of 4 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: "AUFS"
  41 55 46 53                                       AUFS

  expected: "RARC"
  52 41 52 43                                       RARC

- 0 files found in 0 seconds
  coverage file 0     0%   4          147876374  . offset 00000004

Press ENTER or close the window to quit
[https://drive.google.com/file/d/10JwOs3 ... sp=sharing](https://drive.google.com/file/d/10JwOs3lNXRBRHaA3DNpPIkKBOUizaHLA/view?usp=sharing)

Could you help please again?
I do it at the first time 
Thank you
DM.
