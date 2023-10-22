## Post #1
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2006-11-05T13:52:19+00:00
- Post Title: Marvel: Ultimate Alliance

I was wondering if adding support for Marvel: Ultimate Alliance would be doable. I haven't been able to find a demo for Marvel: Ultimate Alliance, so the only real test would be to test it with the retail DVD release. Here's a quick tree of the game's folders:+---actors
+---automaps
+---conversations
+---data
+---dialogs (*.engb,*.itab,*.xmlb)
+---Docs
+---effects
+---hud
+---maps
+---models
+---motionpaths
+---movies (*.sfd)
+---packages
+---scripts
+---shaders
+---skybox
+---sounds (*.zsm,*.zss)
+---subtitles
+---texs
+---textures (*.igb, *.igt)
\---uiSince the main priority would be having sound ripping supported, I uploaded an [archive](http://www.megaupload.com/?d=WMYYLA9Z) of what I believe is the sound pack for the Wolverine playable character (found in /sounds/eng/w/o). I added both .zsm and .zss files to the [archive](http://www.megaupload.com/?d=WMYYLA9Z).

In case anyone wonders about the movie format, I also added the smallest movie file I could find (found in /movies/ntsc/eng/e/t/etrans.sfd). You can find it in [the same zip archive](http://www.megaupload.com/?d=WMYYLA9Z).
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-05T19:50:38+00:00
- Post Title: Marvel: Ultimate Alliance

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2006-11-07T18:19:27+00:00
- Post Title: Marvel: Ultimate Alliance

> Reply from Savage
>
> The movie it's a dreamcast movie, you can recode with "Dreamcast Movie Maker"I tried that, yet the program does not seem to be able to DECODE the movie, only ENCODE movies to said Dreamcast movie format?

I did some googling and found [http://neo-igc.tripod.com/Tutorials/downsample_dc.txt](http://neo-igc.tripod.com/Tutorials/downsample_dc.txt) which deals with sfd files too, unfortunately that approach does not seem to work on the Marvel movies. Perhaps the filetype could be something else?
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-07T20:21:24+00:00
- Post Title: Marvel: Ultimate Alliance

Try to reeencode with tmpgenc [http://www.tmpgenc.net](http://www.tmpgenc.net) and after this use the Dreamcast convertor
## Post #5
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2006-11-11T22:53:16+00:00
- Post Title: Marvel: Ultimate Alliance

Well, the problem with the movies is the fact that the devs seem to use their own codec, with a decoder for it added to the game. I can't play nor recode the movies from outside the game. 

Furthermore, TMPGEnc does not find any audio information in the movie file, and I'm specifically looking for a way to get the speech ripped from the characters in the game.
## Post #6
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-11-13T05:43:08+00:00
- Post Title: Marvel: Ultimate Alliance

Silver did some work on the igb spec in a thread related to the prequel. I want the xmlb files. The prequel used standard xml files and allowed you to edit most fo the properties of the game. The only thing I could find on xmlb files were some python blurb saying they were supported.
## Post #7
- Username: Supermann
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 09, 2006 2:04 pm
- Post datetime: 2006-12-16T03:42:46+00:00
- Post Title: Marvel: Ultimate Alliance

What a pity that we can't extract the music, pictures, and movie of this game. Haven't play English Action RPG for years. Last time it's Metal Solid 1. Hope the support plug-in can be released ASAP.
## Post #8
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-11T19:48:40+00:00
- Post Title: Marvel: Ultimate Alliance

Bump. Any progress on this one?
## Post #9
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-12T20:35:51+00:00
- Post Title: Marvel: Ultimate Alliance

See my other thread. I was able to unpack and decode the sound and pull audio from the SFD movies.
## Post #10
- Username: Supermann
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 09, 2006 2:04 pm
- Post datetime: 2007-07-13T17:11:18+00:00
- Post Title: Marvel: Ultimate Alliance

> Reply from Dandapani
>
> See my other thread. I was able to unpack and decode the sound and pull audio from the SFD movies.

Where's the link to your other thread? Thanks
## Post #11
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-13T17:54:14+00:00
- Post Title: Marvel: Ultimate Alliance

> Reply from Supermann
>
> Dandapani wrote:See my other thread. I was able to unpack and decode the sound and pull audio from the SFD movies.

Where's the link to your other thread? Thanks
[viewtopic.php?t=2703&highlight=](http://forum.xentax.com/viewtopic.php?t=2703&highlight=)
