## Post #1
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2007-11-26T14:46:10+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2007-12-30T19:47:08+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

140 Views and 0 replies? Anybody?
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-30T21:29:56+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

hmm sdt was sound archive format for Dungeon Keeper 2 
Have you looked if the game uses common EA formats?
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-12-31T13:11:36+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

The .sdt file it's a audio Ea (old format) you can reconvert to wav using the conversor explained [Here](http://forum.xentax.com/viewtopic.php?t=1932&highlight=harry)
And [HERE](http://forum.xentax.com/viewtopic.php?p=23975#23975) you can download the reconversor
## Post #5
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2008-01-02T18:10:48+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

Thanks a lot for the replies, but I'm afraid your program doesn't really work with me. When I open sx.exe, I see a flickering black box. (Like a MS-DOS/command-line-thing) I see the program for about a tenth of a second and then it disappears. That's not good, I guess?

The SDT file has a header like this, by the way:
SCHl<...PT......

The FFS & SHD file both have a header like this:
FFS: MRTSd...PRGA....
SHD: MRTS.t?.PRGA....
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-02T19:15:07+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

> Reply from GTADarkDude
>
> Thanks a lot for the replies, but I'm afraid your program doesn't really work with me. When I open sx.exe, I see a flickering black box. (Like a MS-DOS/command-line-thing) I see the program for about a tenth of a second and then it disappears. That's not good, I guess?
This is a command line tool, you need to pass the right options to it: [viewtopic.php?p=15542#15542](http://forum.xentax.com/viewtopic.php?p=15542#15542)

some information on the sdt format can be found here: [http://wiki.multimedia.cx/index.php?tit ... _Arts_SCxl](http://wiki.multimedia.cx/index.php?title=Electronic_Arts_SCxl)
## Post #7
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2008-01-02T19:40:15+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

Yes I knew it's a command line tool and I knew how to type the right commands, but the problem is that I don't get the chance to type these commands.
The window of the tool flickers and then it disappears again, like I had never ran sx.exe. Changing the compatiblity mode doesn't work, by the way.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-02T20:41:23+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

You need to pass them via command line, you can't type them into the window. create a shortcut to the exe and edit the target (adding the correct options)
## Post #9
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2008-01-04T16:14:11+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

Oh, right, now I get it... Sorry that was quite stupid of me    

Wel thanks for that, only 2 file formats to go
## Post #10
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2008-01-09T08:10:30+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

i have question about sound this game
do u help me
[viewtopic.php?p=23918#23918](http://forum.xentax.com/viewtopic.php?p=23918#23918)
## Post #11
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2008-01-21T17:19:21+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

In the mean time, I've mailed the (Dutch) EA Technical Support, but the guy didn't really understand what I wanted. He said he would send the problem to the main office, but I haven't heard of that since.

In the mean time I looked at this video on YouTube
( [http://www.youtube.com/watch?v=Eiw6fRdrxK0](http://www.youtube.com/watch?v=Eiw6fRdrxK0) )
and I saw some images from the sowftware EA uses to make the models.
Perhaps anybody here can tell me what program this is?










Perhaps that my files can be opened with this/these program(s)?
## Post #12
- Username: GTADarkDude
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 26, 2007 4:01 am
- Post datetime: 2008-01-22T13:20:48+00:00
- Post Title: Files in Harry Potter (.BIG) Archive

When I look into the SHD file with Hex Workshop, I notice there's lots of times "5445 5341 2800" or "TESA( ". Could this mean anything?
I also discovered a whole lot of text starting at Offset 3632 (or 0x00000E30) hinting towards some .fsh texture files. Could this .SHD file be another GRA inside the .BIG Game Resource Archive?
In that case, the so-called GRAIS would be "MRTS" or "4D52 5453"
