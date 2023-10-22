## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-08T11:48:47+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

Hello fellow Xentax members! 

I was browsing my bucket list of nostalgic games and couldn't help but remember the amazing classic MDK packed with amazing action and graphics for its time, it still holds up today with its weird designs, yet cohesive to its own style. I absolutely love the coil suit and I'd love to get the model seen in the freefall/tunnel sections after the level's boss. From what I can tell, the models must be in the FALL3D folder, in the .bni, .sni or .mti files. I've uploaded some samples and I hope there's a way to get those awesome models and textures! Thanks in advance, I'm looking forward to this thread.

[https://www.dropbox.com/s/2h3qpj0ceerlq ... s.rar?dl=0](https://www.dropbox.com/s/2h3qpj0ceerlq5n/MDK%20Files.rar?dl=0)

Here are the files, I wish you best of luck!  
[Untitled.png](https://xentaxbackup.github.io/file/15144_Untitled.png)
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-09T10:36:20+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

*bump* Please? Anyone?..
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-12T18:03:24+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

Is there absolutely any way to get the models/textures? Ninja Ripper doesn't work for me (x86 - DDRAW), it doesn't launch at all
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-12T18:35:19+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

Don't expect anyone to do the tedious task which you could do yourself.

I didn't see face indices in the files but in FALL3D.SNI I found the string WAVEfmt, so maybe it's a sound file.

For the other files: you could try finding textures using TextureFinder or point clouds using hex2obj.
So why not?
## Post #5
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-13T20:09:08+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

Sorry to bug everyone... I used Texture Finder and got only distorted textures as for the Hex2Obj I could never get it to work, I can't understand it no matter how much time I spend looking at tutorials... I try and try and I just can't figure it out, it's insanely tricky...
## Post #6
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-11-19T05:00:55+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

From a quick glance I can say that the *.SNI is just embeded wav files (I'll write a parser for that tomorrow) since the format is really easy. For *.MTI contains materials (could be the textures?) and the *.BNI seems to have mesh data, since I found this point cloud in submesh "Head" on the first C3B file:



Screenshot_1.png (27.08 KiB) Viewed 102 times


Seems to be a jester head.... don't know though. That's all I could draw up tonight. Seems that the BNI stores "C3B" files which have submeshes. (There's three uint16's that maybe the index for each vertice, with the uv info?).
## Post #7
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-20T01:40:38+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

Good luck and thanks a ton!
## Post #8
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-11-20T05:16:09+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

I was able to extract files from two of the three formats, here's my work in-progress script for QuickBMS:

```

if ext == "SNI"
	get ARKSIZE long #arksize - 4
	getdstring FILEID 0xC
	get EOFPOINTER long
	get FCOUNT long
	set FEXT string ".WAV"

	for i = 0 < FCOUNT
		getdstring NAME 0xC
		get NULL long
		get OFFSET long
		math OFFSET + 4
		get SIZE long
		string NAME += FEXT
		log NAME OFFSET SIZE
	next i 
elif ext == "BNI"
	get ARKSIZE long #arksize - 4
	get FCOUNT long
	set FEXT string ".BIN"
	for i = 0 < FCOUNT
		getdstring NAME 0xC
		get OFFSET long
		savepos CUR_OFF
		set CHECK long 0 
		xmath CHECK "FCOUNT - 1"
		string NAME += FEXT
		if i != CHECK
			getdstring SKIP 0xC
			get SECONDVAL long
			set SIZE long 0 
			xmath SIZE "SECONDVAL - OFFSET"
			goto CUR_OFF
		else
			set SIZE long 0 
			xmath SIZE "ARKSIZE - OFFSET"
		endif
		log NAME OFFSET SIZE
	next i 
elif ext == "MTI"

else
	print "Wrong file format."
	cleanexit
endif


```


SNI dumps out sounds, and BNI is probably binary model data, which I have no interest in looking at any further. I will need some time on the MTIs.
## Post #9
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-20T12:15:47+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

This is amazing work so far! Are you continuing on textures then models? I'm looking to get Kurt's model in the skydiving/post-level tunnel sections..
[kurt.png](https://xentaxbackup.github.io/file/15209_kurt.png)
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-11-28T16:27:35+00:00
- Post Title: MDK (PC 1997) 3d models and 2d sprites

*bump* Any more progress?
