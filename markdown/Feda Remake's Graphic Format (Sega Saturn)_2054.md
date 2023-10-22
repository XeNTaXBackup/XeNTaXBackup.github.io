## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-21T17:43:09+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

I know, it's an odd console request but I dunno where else to go for this kind of stuff since no tools seem to exist. The graphics seem to be uncompressed, but the format is what bugs me. They have compared it to bitmap but I dunno. Here's a couple of files from the CD.

I'm trying to understand the format as well as extract and view them. Because, quite honestly, nobody really can as it seems.

Very few details exist on this, but I don't know, maybe I'm overcomplicating it?
[AIN.rar](https://xentaxbackup.github.io/file/817_AIN.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-28T01:35:03+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

Here's somthing else to base off of. It is apparently one of two "chara" files. Apparently the overhead view sprites.

As far as I've been able to distinguish is that the graphics do not seem to be compressed, but are in a strange form somewhat resemblant to a bitmap. Not 100% sure here though. I'm not too good with graphic formats afterall O_o.

Edit: When looking at it in a hex editor. I've noticed the reaccurance of "85 84 84 85". Is this a possible header? O_o

Edit 2: Used another hex editor and it was some other number. O_o not sure what exactly I'm looking at here but it appears to be like a form of bitmap.

Edit 3: Yeah, the Chara.bin contains character overhead graphics as well as portraits. I saw them in Texture Finder. Now to figure out how to view them right >_<

Edit 4: Oh yeah. I found something in the game that gives data on each character and refers to the _N BIN files. I am not sure but I believe AIN_N.BIN contains the battle graphics and are of a different format.
[CHARA.rar](https://xentaxbackup.github.io/file/831_CHARA.rar)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-28T05:11:05+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

contains what seems to me as character animations.
(or similiar). (in what i can see 8 bit color), yet......
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-28T06:19:38+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

You are correct, they are 8 bit color graphics. And they are character animations. Your right on the money there. But is there a problem?
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-28T08:37:52+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

There is probably not much of a problem to view or extract them 
at all, i just didnt do much about it. however I didnt see any palette
data in there. You wanted an extractor? =o
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-28T18:57:44+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

No palette data? So the palette data would possibly be in a seperate file?

Well the idea was to be able to extract and view them. I never really could understand the Sega Saturn way of handling graphics. I do have tools that are supposed to convert them, but where would those palettes be?
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-01T23:16:09+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

The only thing I've been able to find is the released development manuals by Sega: [http://www.antime.org/sega/docs.html](http://www.antime.org/sega/docs.html)

Other than that. I am fairly certain they refer to palette data as a "color bank" which I'm trying to figure out at this point. But as I've heard graphics are probably the more confusing things about Sega Saturn. Then again, I dont know much about the sound either >_<. You seem to be interested in music/sound formats though. I dunno. My interest has always been graphics. XD
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T17:24:08+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

Lets revive this.

so obviously the character animations has no palette data.

BUT...the character portraits have!!! =DD

the palette data is however strange, and is stored as 16 bit instead
of 32/24. im currently working on a converter to TGA to save those
images.
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T17:53:20+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

Whos your daddy??  HUH? I cant hear you?!?!! O_____X
[sega_ 518157_xxxx.jpg](https://xentaxbackup.github.io/file/849_sega_ 518157_xxxx.jpg)
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T19:18:03+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

Now this exporter is available in the newest jaeder release :X

However, the palette data is a bit off track. (i know), I had
some troubles trying to understand how to interpret 16 bit palettes,
and i just didnt get hang of it totally.

but overall the exports look pretty readable
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-14T22:58:11+00:00
- Post Title: Feda Remake's Graphic Format (Sega Saturn)

Woah! This is most awsome! O_O

So the character animations have no palette data. That is most strange. But I'll try my part on that. I guess it would be stored in a seperate file? But anyways, I really like what you've been able to do! Thanks!
