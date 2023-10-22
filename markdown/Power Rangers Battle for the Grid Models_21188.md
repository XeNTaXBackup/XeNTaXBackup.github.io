## Post #1
- Username: zirio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 26, 2019 4:28 pm
- Post datetime: 2019-09-29T12:05:08+00:00
- Post Title: Power Rangers: Battle for the Grid Models?

I need help to extract models from Game.

The file is in .DAT format, can be used with AssetStudio but it does not extract the whole datai.

[https://mega.nz/#!jtkmwaRQ!DABQYKJWwm1f ... tYQJp1fJRQ](https://mega.nz/#!jtkmwaRQ!DABQYKJWwm1fq22yqY1yontlWQH6lg54StYQJp1fJRQ)
## Post #2
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2019-10-10T11:36:35+00:00
- Post Title: Power Rangers: Battle for the Grid Models?

bump.
hope someone could help with this.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-10T15:05:41+00:00
- Post Title: Power Rangers: Battle for the Grid Models?

Guess, it's very unlikely someone downloads 773 MB of data just to check a model format...
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-10T16:09:47+00:00
- Post Title: Power Rangers: Battle for the Grid Models?

I'm not familiar with parsing, but I think it's just a Unity AssetBundle concatenation file.
I think you should use the quickbms script (generic splitter) created by AlphaTwentyThree.
## Post #5
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-10-10T17:10:16+00:00
- Post Title: Power Rangers: Battle for the Grid Models?

(try to split the file. use a hex editor. search for "unityfs" and set a reminder on the start and ends. then c/p the subcontainers into seperate files. I tested 1, 2, blah. asset studio can open those subcontainers. i guess it's just glued together and you missing the descriptor file for the glue offsets. looks like it can be bypassed this way. )

script for convenience. you gotta dump the last subcontainer manually. the findloc terminates at eof, so... it won't math the end and dump it.

```

goto 0
savepos fstart

for
	goto fstart
	goto 1 0 seek_cur
	findloc foffset string "UnityFS"
	xmath fsize "foffset - fstart"
	math count + 1
	get oname basename 0
	string cnt p "_%03d" count
	string oname + cnt
	log oname fstart fsize 0
	math fstart + fsize
next

```
