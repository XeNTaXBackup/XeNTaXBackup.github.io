## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-19T20:38:29+00:00
- Post Title: [PC] Hard Reset files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2011-09-22T09:33:15+00:00
- Post Title: [PC] Hard Reset files

Nobody knows how to decrypt the str files?
## Post #3
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-22T10:48:30+00:00
- Post Title: [PC] Hard Reset files

there thumb.bin file, it has also same textures but small version maybe it can be reason of these blurring.
Also, in Adobe while editing you should choose all alpha-RGB channels,  this can be reason either.
## Post #4
- Username: tsl16b
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 8:16 pm
- Post datetime: 2011-09-25T18:11:51+00:00
- Post Title: [PC] Hard Reset files

Text files aren't encrypted, they're in Squirrel script compiled byte code, but the game engine has no problem reading them from source format, as in the attachment.
[hard_reset_v1.01_text.zip](https://xentaxbackup.github.io/file/4740_hard_reset_v1.01_text.zip)
## Post #5
- Username: yulei
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 30, 2011 12:22 am
- Post datetime: 2011-09-26T13:41:05+00:00
- Post Title: [PC] Hard Reset files

And which tool or program can be used to edit the texts?
## Post #6
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-09-26T13:55:50+00:00
- Post Title: [PC] Hard Reset files

> Reply from tsl16b
>
> Text files aren't encrypted, they're in Squirrel script compiled byte code, but the game engine has no problem reading them from source format, as in the attachment.
Is this zip contains all of the texts or just a part of the texts?
## Post #7
- Username: tsl16b
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 8:16 pm
- Post datetime: 2011-09-26T17:16:36+00:00
- Post Title: [PC] Hard Reset files

> Reply from yulei
>
> And which tool or program can be used to edit the texts?
Don't let the ".str" extension fool you, these are plain text files. Any text editor should do it.

> Reply from qabRieL
>
> Is this zip contains all of the texts or just a part of the texts?
As far as I know that's all. All other in-game textual information are printed onto textures (.DDS files). To create a decent localisation we'll have to redraw them too.
## Post #8
- Username: yulei
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 30, 2011 12:22 am
- Post datetime: 2011-09-27T15:29:37+00:00
- Post Title: [PC] Hard Reset files

I get it,thanks.However,there's still a problem.I can't input more than the number of the original words.If you input one more letter,the game just doesn't work.
## Post #9
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-27T15:55:06+00:00
- Post Title: [PC] Hard Reset files

> Reply from qabRieL
>
> tsl16b wrote:Text files aren't encrypted, they're in Squirrel script compiled byte code, but the game engine has no problem reading them from source format, as in the attachment.
Is this zip contains all of the texts or just a part of the texts?
game cutscenes are comics, and text are hardcoded into only comics. There is no subtitles for cutscenes.
## Post #10
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-10-10T06:37:01+00:00
- Post Title: [PC] Hard Reset files

Is somewhere Squirrel decompiller to download?
## Post #11
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2016-06-19T11:41:35+00:00
- Post Title: [PC] Hard Reset files

> Reply from tsl16b
>
> but the game engine has no problem reading them from source format, as in the attachment.
Where should they go?
In
data\scripts\localisation\en
or
data\scriptsbin\localisation\en (game crashes)
and
data\localisation\en
they don't work.
