## Post #1
- Username: Gauze
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 12, 2012 2:39 am
- Post datetime: 2012-03-11T19:58:14+00:00
- Post Title: Deadly Premonition file archive types.

Recently I decided to try and extract textures and models from the xbox360 game Deadly Premonition. On the disc there was a folder called pack which had a lot of .pkg files. I managed to find a way to extract data from these file types with offzip. After I extracted these files i got a bunch of new file types (.xpc .xmd and .xam) I used a hex editor to look inside, and they appear to be archive files also. I personally have no experience hex editing files, so I've been researching but I'm stuck. I've included a sample of each file type. So if somebody could take a look and give some advice about getting the data I would be very appreciative. Thanks in advance.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-11T20:39:53+00:00
- Post Title: Deadly Premonition file archive types.

xpc is a texture archive. It is pretty simple to parse, but will need files with different number of textures to verify a couple values (like number of textures, and whether some values are actually offsets or not)

xmd files contain model. You can see an index buffer and vertex buffer. Sounds like a good start.

xam probably just animation.

Upload some pkg's
I am usually never interested in offzip dumps except that now we know what compression it uses...
## Post #3
- Username: Gauze
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 12, 2012 2:39 am
- Post datetime: 2012-03-11T21:35:42+00:00
- Post Title: Deadly Premonition file archive types.

I'll post a few more if needed.

Could you explain the process of how you got the texture by any chance?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-11T22:31:11+00:00
- Post Title: Deadly Premonition file archive types.

Looks like chrrox already write an importer.

Textures I just wrote a plugin for noesis.

[http://db.tt/hVmq82OB](http://db.tt/hVmq82OB)
## Post #5
- Username: Gauze
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 12, 2012 2:39 am
- Post datetime: 2012-03-11T22:43:33+00:00
- Post Title: Deadly Premonition file archive types.

Sweet. Thank you! I've been trying to figure out getting the textures for days.
After using the plugin for a bit, some textures get an error. But I'm guessing its because the files contained in those xpc files are structured slightly differently. Maybe I can figure it out. having at least some textures that work is awesome still.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-29T02:48:50+00:00
- Post Title: Deadly Premonition file archive types.

BMS script to unpack with names would be nice.
This game doesn't store filenames anywhere?

I don't see any names unfortunately so this pretty much doing what offzip is doing.

```

findloc IDX string "XZP1"
do
	goto IDX
	get idstring long
	get FILES long
	get SIZE long
	get ZSIZE long
	savepos OFFSET
	clog OFFSET OFFSET SIZE ZSIZE
	math NEXT = IDX
	math NEXT += 1
	goto NEXT
	findloc IDX string "XZP1"
while IDX > -1

```
## Post #7
- Username: RuffalowMan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-29T03:04:14+00:00
- Post Title: Deadly Premonition file archive types.

your better off doing clog "" OFFSET SIZE ZSIZE instead of clog OFFSET OFFSET SIZE ZSIZE then it will attempt to identify the extension.
## Post #8
- Username: RuffalowMan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 15, 2012 9:25 pm
- Post datetime: 2012-04-15T13:47:11+00:00
- Post Title: Deadly Premonition file archive types.

Thank you Finale00 & Chrrox, I really appreciate you both spending time on this overlooked gem, however is there a way to fix the error in line 67? I've attached a screenshot just in case you don't know what I'm referring to.
[deadlyPre_PYerror.png](https://xentaxbackup.github.io/file/5307_deadlyPre_PYerror.png)
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-15T13:55:48+00:00
- Post Title: Deadly Premonition file archive types.

No, because I don't have any files to see what the issue is.
## Post #10
- Username: RuffalowMan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 15, 2012 9:25 pm
- Post datetime: 2012-04-15T14:10:22+00:00
- Post Title: Deadly Premonition file archive types.

Thanks all the same
## Post #11
- Username: simkas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 21, 2012 5:42 pm
- Post datetime: 2012-05-22T11:23:23+00:00
- Post Title: Deadly Premonition file archive types.

I'm currently trying to get textured character models from DP and chrrox's plugin works perfectly for models, but the noesis plugin that finale00 posted doesn't seem to work, I just get the same error as RuffalowMan posted for every file I tried. It seems like finale was actually able to get the textures so I'm assuming the plugin should work, so what might be the problem here?
## Post #12
- Username: Gauze
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 12, 2012 2:39 am
- Post datetime: 2012-08-14T16:56:24+00:00
- Post Title: Deadly Premonition file archive types.

Tis been a long time since I checked here, my comp crashed so I was set back awhile. 
Here are three files with the error described by RuffalowMan

[http://www.mediafire.com/?u11jwobuh2eu6tx](http://www.mediafire.com/?u11jwobuh2eu6tx)

If there is any interest still about these files.
## Post #13
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2014-01-17T11:46:38+00:00
- Post Title: Deadly Premonition file archive types.

Sorry to bump this very old thread, but has anybody looked into recompressing the XPC texture packages for the PC version of DP? Chrrox made a [Noesis script](http://forum.xentax.com/viewtopic.php?f=16&t=11003) for importing the models + textures. I'm really interested in adding new content to Deadly Premonition. As it stands, creating new addons for the DLC picker is incredibly easy. It's just not very useful right now if texture editing isn't possible. Technically you can use Durante's DPFix texture override system to overwrite specific hashes, but this is not nearly as powerful as editing the texture packages in the game for new costumes/scripts. Anyone want to take a look if they have some free time?
