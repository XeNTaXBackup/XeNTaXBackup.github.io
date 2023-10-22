## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T11:59:05+00:00
- Post Title: Ascendancy documentation

Guys, this request I got. I don't have such material. Perhaps someoneelse can help him?

> Hi!
>
> 
>
> I am working a little bit on Ascendancy
>
> 
>
> Now I need the documentation or the tools for:
>
> - FNT font file format
>
> - some of the non-creative VOC files
>
> - HAZ, expected to be the "haze" or highlight in the game, a sort of bitmap mask
>
> - TMP (what are these?)
>
> 
>
> Mark's site is broken, do you still have its pages? A lot of useful stuff was there but through the google cache I could get only the shp.html page
>
> 
>
> Sad Please help me
>
> If you have contacts of people who has material about Ascendancy I you should also let them contact me.
>
> 
>
> Thank you,
>
> --
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T13:55:38+00:00
- Post Title: Ascendancy documentation

Hi mate,

Um no, unfortunately I don't know anything about these files - Mark added in the website links himself and I couldn't get access to them either, and I am unable to contact him.

In regards to the FNT file - it is probably a font-related file, maybe a list of points of something that would allow you to construct the vector-based font text. I know *.fnt files are used in many games, but I don't think they are a standard format

The TMP files - they are probably just temporary files, like a cache - you probably don't want to bother with them as they would be overwritten by the game all the time.

The VOC files - not sure - possibly they would be standard *.wav audio, with or without the headers, or just some kind of raw audio format. Perhaps try Game Audio Player - see if that program does it - if it does then there are some audio specs on the same website. Also try opening the file in an audio editing program like Cool Edit. Finally, consider looking for text strings in the game *.exe file - maybe you can find a reference to the format there, or even in the readme file or the game credits.

Good luck. Sorry it isn't anything specific, but hopefully it is a step in the right direction.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T13:58:55+00:00
- Post Title: Ascendancy documentation

Oh, I missed one 

The HAZ files - if they are what you expect, it would probably be structures similarly to a BMP image (you can find BMP specs everywhere on the net), or more probably it would just be a 2D array of bits that represent the alpha. In other words, if the image is 4x4, it would just be 16 bytes where each byte told the alpha value of the related pixel. Not sure how the game engine works, but it could also be just some co-ordinates, light intensity values, reflectivity, etc that would just be fed into the game engine.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-02T15:54:29+00:00
- Post Title: Ascendancy documentation

Where can I download files from this game? =O
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T16:05:28+00:00
- Post Title: Ascendancy documentation

[http://www.the-underdogs.org/downloadfi ... ip&id=1525](http://www.the-underdogs.org/downloadfile.php?file=games/a/ascendancy/files/ascendancy.zip&id=1525)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T10:15:27+00:00
- Post Title: Ascendancy documentation

All sounds seems to be 22Khz 8 bit mono files. 
have not yet found a single header in the archives, but playing these as
pcm with at these settings works terrific.
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T10:34:47+00:00
- Post Title: Ascendancy documentation

is it somehow possible to extract files per file out of the archives?
its a pain in the ass trying to disinguish files in these COB archives,
as all files seems to be headerless in it. =///
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-03T10:36:08+00:00
- Post Title: Ascendancy documentation

COB files are supported by MultiEx Commander.
## Post #9
- Username: legolas
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 02, 2006 6:24 pm
- Post datetime: 2006-01-04T17:00:17+00:00
- Post Title: Ascendancy documentation

> Reply from friendsofwatto
>
> Hi mate,

In regards to the FNT file - it is probably a font-related file, maybe a list of points of something that would allow you to construct the vector-based font text. I know *.fnt files are used in many games, but I don't think they are a standard format
Yeah..Mark had something about Ascendancy FNT format, but neither Google's cache has that page now...

> Reply from friendsofwatto
>
> 
The TMP files - they are probably just temporary files, like a cache - you probably don't want to bother with them as they would be overwritten by the game all the time.
They are in the COB archive, that is intended to be read-only...I have just discovered they are simply SHP files renamed to TMP

> Reply from friendsofwatto
>
> 
Good luck. Sorry it isn't anything specific, but hopefully it is a step in the right direction.
Thank you my friend!

I'll post/ask here when I have news
## Post #10
- Username: legolas
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 02, 2006 6:24 pm
- Post datetime: 2006-04-14T15:31:49+00:00
- Post Title: Ascendancy documentation

The latest MODguide is available at

[http://legolas558.awardspace.com/download.php?list.6](http://legolas558.awardspace.com/download.php?list.6)

Enjoy!
## Post #11
- Username: Pookie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 06, 2006 8:57 pm
- Post datetime: 2006-11-06T13:02:29+00:00
- Post Title: Ascendancy documentation

Heyhey

Im quite a nooby... but I hope you guys are talking here about the files of the game Ascendancy ([http://www.logicfactory.com/games_ascendancy.htm](http://www.logicfactory.com/games_ascendancy.htm)) I really love the music in that game, and I have been searching everywhere and couldn't find a thing. Do you guys maybe have some kind of music file of this background music? You wud surely make my day ^^

Thank u for ur time 

-Gina
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-06T13:12:53+00:00
- Post Title: Ascendancy documentation

> Reply from Pookie
>
> Heyhey

Im quite a nooby... but I hope you guys are talking here about the files of the game Ascendancy (http://www.logicfactory.com/games_ascendancy.htm) I really love the music in that game, and I have been searching everywhere and couldn't find a thing. Do you guys maybe have some kind of music file of this background music? You wud surely make my day ^^

Thank u for ur time 

-Gina

Yeah, people love the music in Ascendancy. In the past I have played it. you can extract music from the Ascendancy files using MultiEx Commander.
## Post #13
- Username: Pookie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 06, 2006 8:57 pm
- Post datetime: 2006-11-06T14:00:51+00:00
- Post Title: Ascendancy documentation

Okay ^^,  so I installed MultiEx Commander and I tried some things and read the manual, but I don't really get it 

Does it have the Ascendancy file itself or do I have to get it from some site ([http://wiki.xentax.com/index.php/Ascendancy#VOC](http://wiki.xentax.com/index.php/Ascendancy#VOC)) ? And then how can I play it? 

Could you help me out? Or tell me to read some tutorial so I can know? 

Thank u for ur trouble.. again 

-Gina
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-06T15:05:39+00:00
- Post Title: Ascendancy documentation

> Reply from Pookie
>
> Okay ^^,  so I installed MultiEx Commander and I tried some things and read the manual, but I don't really get it 

Does it have the Ascendancy file itself or do I have to get it from some site (http://wiki.xentax.com/index.php/Ascendancy#VOC) ? And then how can I play it? 

Could you help me out? Or tell me to read some tutorial so I can know? 

Thank u for ur trouble.. again 

-Gina

Nope, you should open .COB files (It think that's what their extension is) from the game with MultiEx Commander and extract the music. Then you'll need something like Cool Edit Pro to play those files.
## Post #15
- Username: Pookie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 06, 2006 8:57 pm
- Post datetime: 2006-11-07T12:58:21+00:00
- Post Title: Ascendancy documentation

hmmm I'm still kinda confused about this, I looked everywhere for those files , but I don't quite get it. I tried all kind of things, but do you need the full game of Ascendancy to get these files or is there some place where I can get them in some kind of zip file? (or do I need a registered version of MultiEx Commander?)

I know, I probably sound annoying and know that you guys are probably busy with more important things, but I would really appreciate it if you or someone else could tell me step by step how I can get this to work (I already got the Cool Edit Pro program). The background music of Ascendancy is just so nice and I would love it if I could hear it again, so if someone has the time; please help me out.

-Gina
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-07T22:50:49+00:00
- Post Title: 

If you have Ascendancy, then you will find .COB files (files with the extension  COB). These are archives, like ZIP files are archives. In there you will find the music. They are .RAW files. Like theme00.raw and theme01.raw. 

These are 8-bit unsigned raw PCM files, mono, at a frequency of 22050. 

I've converted them for you using Cool Edit and WinGOGO to MP3. 

[http://www.xentax.com/audio/theme00.mp3](http://www.xentax.com/audio/theme00.mp3)
[http://www.xentax.com/audio/theme01.mp3](http://www.xentax.com/audio/theme01.mp3)
[http://www.xentax.com/audio/theme02.mp3](http://www.xentax.com/audio/theme02.mp3)
[http://www.xentax.com/audio/theme03.mp3](http://www.xentax.com/audio/theme03.mp3)
[http://www.xentax.com/audio/theme04.mp3](http://www.xentax.com/audio/theme04.mp3)

Theme00 is long and has pauzes, but it's like it is played in the game. 

There are also race musics in there. But that I'll leave for you to convert.
## Post #17
- Username: Pookie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 06, 2006 8:57 pm
- Post datetime: 2006-11-08T14:44:13+00:00
- Post Title: 

Aww thank you so much ^^   




(I understand it better now, thanks for the explaining  )

<<<<333 !
## Post #18
- Username: lulin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 30, 2007 8:08 pm
- Post datetime: 2010-08-29T20:19:15+00:00
- Post Title: 

Are people still interested in this game? I would love to work on a modern engine / remake. I started a repo at [http://github.com/rogerbraun/Ascendancy-tools](http://github.com/rogerbraun/Ascendancy-tools), right now it only includes a cob extraction tool.
## Post #19
- Username: ForNeVeR
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 11, 2023 6:33 am
- Post datetime: 2023-01-10T22:46:38+00:00
- Post Title: 

I am now slowly working on an open-source remake of another game by The Logic Factory, The Tone Rebellion, which happens to share certain data formats with Ascendancy. This includes the .FNT format that was requested (but never explained) earlier. Incidentally, I have even used code from the previous commenter, Roger Braun, for some purposes other than fonts, in my project.

So, I was able to get some data on said format from other open-source software, and published [an overview](https://github.com/ForNeVeR/overtone/blob/c6eb00a21525ccda8e5c076c95460392991d50ae/docs/fnt.md) on my GitHub repo (all the information sources and credits are listed on the page). A cross-platform font renderer is available as well.

I would maybe like to contribute this information to [the corresponding page of the Xentax Wiki](https://wiki.xentax.com/index.php/Ascendancy), since it still googles as one of the main sources of information about this game's resource formats. But the whole wiki looks very defunct at that point, and I'm not sure how to contribute. Would the registration page work? No idea.
## Post #20
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-11T20:02:27+00:00
- Post Title: 

> But the whole wiki looks very defunct at that point, and I'm not sure how to contribute. Would the registration page work? No idea.

Wiki is functional (well, everything except CSS themes works   )

Public registration is closed (due to spam bots attacks from the past). You can PM me and I will register new account for you.
Or you can tell me what should be updated in the article and I will do it for you.
## Post #21
- Username: ForNeVeR
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 11, 2023 6:33 am
- Post datetime: 2023-07-22T17:01:50+00:00
- Post Title: 

Is it possible to just paste into the FNT section everything I've collected [in my documentation](https://github.com/ForNeVeR/overtone/blob/e98b3f91026134c46d745d9472ee4c54c78fa0e2/docs/fnt.md)?
## Post #22
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-22T18:15:29+00:00
- Post Title: 

> Reply from ForNeVeR ↑Sun Jul 23, 2023 1:01 am at Sun Jul 23, 2023 1:01 am
>
> 
Is it possible to just paste into the FNT section everything I've collected in my documentation?

Done.
