## Post #1
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2010-12-28T07:19:06+00:00
- Post Title: Could it be, Metal Gear?!

[http://i54.tinypic.com/2j0f869.jpg](http://i54.tinypic.com/2j0f869.jpg)
Colors are, obviously, faked. I haven't worked out how it handles textures yet. Guessing it loads them all into VRAM and refers to them by texture page. It's also backwards ~shrug~.
## Post #2
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2010-12-28T08:41:27+00:00
- Post Title: Could it be, Metal Gear?!

[http://i55.tinypic.com/5ybzux.png](http://i55.tinypic.com/5ybzux.png)
Fixed orientation. Helps to not use GLuint when I should be using GLfloat.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-28T09:33:26+00:00
- Post Title: Could it be, Metal Gear?!

??????????????
## Post #4
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2010-12-29T21:57:43+00:00
- Post Title: Could it be, Metal Gear?!

Shadow Moses?
## Post #5
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-12-30T05:30:48+00:00
- Post Title: Could it be, Metal Gear?!

Looks like Shadow Moses helipad area.
I can only assume you're working on a tool that lets you extract/view map meshes from MGS1, is that correct?
## Post #6
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2010-12-30T07:21:13+00:00
- Post Title: Could it be, Metal Gear?!

Yeah more or less. It's actually kind of neat because all the meshes are in the same format. I don't have animations, textures or lights right now, haven't looked at it yet. But every mesh is working at least to basic extent. So simple, I should have done this ages ago. Also yes, that is the helipad area.
## Post #7
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-01-09T01:33:26+00:00
- Post Title: Could it be, Metal Gear?!

Got export working. Still needs textures and stuff.
[http://neko68k.blogspot.com/2011/01/mgs-export.html](http://neko68k.blogspot.com/2011/01/mgs-export.html)
## Post #8
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-01-09T13:44:08+00:00
- Post Title: Could it be, Metal Gear?!

Oh wow, that actually happened huh? Good work on the tool.
## Post #9
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-06-06T14:31:25+00:00
- Post Title: Could it be, Metal Gear?!

So I was revisiting MGS tonight after I had an idea about textures while investigating something else. It turns out they are storing data in the NULL reserved section of the PCX header. This is at least referencing the VRAM x,y location of the texture and of its associated CLUT entry. It doesn't always reflect what I see in PSX VRAM dumps but its right a lot of the time. I'll probably build a VRAM simulator for it pretty soon and test it out. This also partly explains why my texture repack tests didn't work. Naturally there aren't any PCX compatible editors that embed this extra data and so it is lost and causes the game to die. There is hope yet for this game
## Post #10
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-06-06T14:47:37+00:00
- Post Title: Could it be, Metal Gear?!

Wicked news.
Hey, are object/character models stored in the same format as levels?
I'm guessing they would be at least slightly different, but could you shed some light on it?
## Post #11
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-06-06T14:55:53+00:00
- Post Title: Could it be, Metal Gear?!

Ameneko, did you researched on the MGS PC/PSX sound (VOX and others, not the sfx .wavs) format?
## Post #12
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-06-07T04:42:42+00:00
- Post Title: Could it be, Metal Gear?!

> Reply from Friedslick6
>
> Wicked news.
Hey, are object/character models stored in the same format as levels?
I'm guessing they would be at least slightly different, but could you shed some light on it?

Yeah they're all the same. There is separate animation data and script data also but all the models are the same. Only problem is that the characters and stuff are segmented and broken into separate files.

> Reply from McCuñao
>
> Ameneko, did you researched on the MGS PC/PSX sound (VOX and others, not the sfx .wavs) format?
No I haven't. I guess I could take a look sometime.
