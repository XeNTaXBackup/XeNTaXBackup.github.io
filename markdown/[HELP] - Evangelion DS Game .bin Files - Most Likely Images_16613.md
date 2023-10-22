## Post #1
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2017-07-30T21:59:31+00:00
- Post Title: [HELP] - Evangelion DS Game .bin Files - Most Likely Images

Unfortunately I'm using a mac, so I can't use some of the nds tools like CrystalTile.

I'm trying to extract all images from a DS game: "Evangelion - Ayanami Raising". I've managed to unpack the .nds but the files inside are still compressed in an mystery .bin format. I've tried every tool I could find, but so far no luck.

If anyone knows a good workflow, or can take a look at the file below and see what they can do, that'd be great. If successful, I'll reproduce your steps.

*Note*
I changed the extension to .zip, just change it back to .bin.
There is no .cue file, and from the file name/game type i'm pretty sure it's just an image.
[cg_angel.zip](https://xentaxbackup.github.io/file/13156_cg_angel.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-02T04:27:47+00:00
- Post Title: [HELP] - Evangelion DS Game .bin Files - Most Likely Images

i don't know what the files contain or what compression etc if any is used but this bms script will at least split the files  

```

get FILES long
for i = 0 < FILES
	get OFFSET long
	get SIZE long
	get NAME basename
	string NAME + _
	string NAME + i
	string NAME + .dat
	log NAME OFFSET SIZE
next i
```
