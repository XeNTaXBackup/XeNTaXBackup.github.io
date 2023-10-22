## Post #1
- Username: Doomer022
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 15, 2020 4:22 am
- Post datetime: 2020-02-14T20:28:20+00:00
- Post Title: Ripping sounds from Ford Racing 3? (.SPC)

Hello people! First post here! I was guided to over here from "The VG Resource" website. Im asking this question in regards with Ford Racing 3's .SPC sound files.

I tried many programs to open or extract the sound files from this format, but so far, nothing worked. I wanted to ask: How can you open these .SCP files, and how can you put your own custom files into this format?

Im currently working on a small hobbyist modification for this game, and I want to replace the old with new sounds. Thanks in advance!
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2020-02-21T17:46:58+00:00
- Post Title: Ripping sounds from Ford Racing 3? (.SPC)

Script for QuickBMS:

```


get FCOUNT long
savepos CUR_OFF
xmath OFFSET "(FCOUNT * 0x4C) + CUR_OFF"
for i = 0 < FCOUNT
	getdstring NAME 0x20
	goto 0x28 0 SEEK_CUR
	get SIZE long
	string NAME + ".WAV"
	log NAME OFFSET SIZE
	math OFFSET + SIZE
next i 

```


Download QuickBMS here, and run it on the SPC archives:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Should be playable with any standard wave player.
