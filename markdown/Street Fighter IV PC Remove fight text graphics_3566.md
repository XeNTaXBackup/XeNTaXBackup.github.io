## Post #1
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-04T12:38:12+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

For Street Fighter IV PC, does anyone know how to remove the beginng and end fight text graphics so that they don't show up?  Perhaps by replacing them with invisible transparent graphics?  Fight text graphics such as: "round 1, fight", "KO", etc.--but not any of the HUD graphics.  I already can hide the HUD in the game options, but I want to be able to remove the fight text graphics, too.  By hiding the interface elements during gameplay, I think the game has a more "movie" feel [for casual play of course].
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-10T23:16:50+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

I wouldn't know. Haven't got the game.
## Post #3
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-11T06:24:11+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

i haven't tried but i guess since the graphics are all in dds format and the fight etc. graphics have transparency, you can use the method i found to rip the dds graphics, set the alpha channel to all black and reinject... that SHOULD remove the graphics
## Post #4
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-11T06:38:42+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

does multiex rip dds graphics?  or do i have to use something else?
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-11T09:09:19+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

forgot the thread link sorry 
[viewtopic.php?f=10&t=3364](http://forum.xentax.com/viewtopic.php?f=10&t=3364)
## Post #6
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-17T00:03:18+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

I've removed EVERYTHING on-screen already, you can see it in action here:
[http://www.youtube.com/watch?v=maDe7_5ds7c](http://www.youtube.com/watch?v=maDe7_5ds7c)

All you have to do is make all files transparent in "announce.tex.emz"
But I've done that for you already, enjoy 

What this does:

REMOVES: "KO", "Draw", "Round 1-7", "Fight", "Time over", (challenge mode >>) "Success", "Clear", and some more I think.
DOES NOT REMOVE: Everything else, like full HUD (cockpit), Challenge Instructions, "Sakura Wins"
I think stuff like "Reversal, Combo..., Technical, Counter" are included with the HUD.
[SF4_announce.tex.emz_CLEAR.rar](https://xentaxbackup.github.io/file/2202_SF4_announce.tex.emz_CLEAR.rar)
## Post #7
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-17T10:32:01+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

thanks but how come your file with the removed stuff is so much larger?  the original is 843 KB but yours is 8.31 MB...

btw: pretty cool moves swap!
## Post #8
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-17T10:36:19+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

Because it's uncompressed
## Post #9
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-17T11:20:32+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

i tested it and it works, thanks!  it's pretty cool.  please let us know if you make any updates and improvements for it in the future. 

btw: can you make a recompressed version so that it's smaller?
## Post #10
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-17T21:22:24+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

Yes I can, yesterday I investigated how to compress back to EMZ.
Gimme a moment, and I will create a *New* version, that will probably be less than 800Kb Uncompressed and a couple Kb compressed (if everything goes as planned) 

Well it didn't go exactly as planned, the Uncompressed version stays 8.* MB even when I put 1x1 px DDS files in it.
I guess it's because of Infuser just inserts these couple Byte files at their proper position.

Fortunately, when I compress the EMB posted earlier, which has the original image dimensions only the images are all black + full alpha, it turns out pretty small 
The EMZ in this RAR file is 27.4 KB
[SF4_announce.tex.emz_CLEAR_(Compressed_EMZ).rar](https://xentaxbackup.github.io/file/2204_SF4_announce.tex.emz_CLEAR_(Compressed_EMZ).rar)
## Post #11
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-18T00:25:24+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

great! thanks
## Post #12
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-18T00:28:49+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

BTW: Do you happen to know how to turn off subtitles during fights for Street Fighter IV PC? I already turned off subtitles in settings, but they still show during fights...
## Post #13
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-18T03:11:43+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

I want them gone too, I just haven't looked into it ever since SF4 got cracked open.
AFAIK all text in game are actually textures, so it should be the same for subs.

EDIT:
As I though, it was obvious...

From  \Battle\Hud\ENG\subtitle_CNL.tex.emz
## Post #14
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-18T03:38:29+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

sweet!  so its just a matter of time now, right?
## Post #15
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-18T09:58:47+00:00
- Post Title: Street Fighter IV PC: Remove fight text graphics?

hey i noticed that the "chun li wins" etc. red text still appears after winning fights.  can you please remove that also?
## Post #16
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-18T14:11:40+00:00
- Post Title: Re: Street Fighter IV PC: Remove fight text graphics?

> Reply from TsunamiZ
>
> hey i noticed that the "chun li wins" etc. red text still appears after winning fights.  can you please remove that also?
I dunno, I bet it's possible.

> Reply from LouNGeR
>
> DOES NOT REMOVE: Everything else, like full HUD (cockpit), Challenge Instructions, "Sakura Wins"
## Post #17
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-18T21:51:46+00:00
- Post Title: Re: Street Fighter IV PC: Remove fight text graphics?

can you make an alternate version that also removes the "chun li wins" etc. red text?
## Post #18
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-18T23:25:51+00:00
- Post Title: Re: Street Fighter IV PC: Remove fight text graphics?

No, because that means editing 25 files.

The images are in:
\Battle\Hud\ENG\chara_???.tex.emz
## Post #19
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2009-07-19T13:53:22+00:00
- Post Title: Re: Street Fighter IV PC: Remove fight text graphics?

what program do you use to extract and reimport files for this game?  is it hard to edit myself?
## Post #20
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-19T16:10:01+00:00
- Post Title: Re: Street Fighter IV PC: Remove fight text graphics?

> Reply from TsunamiZ
>
> what program do you use to extract and reimport files for this game?  is it hard to edit myself?
You should really ask less and read more.
