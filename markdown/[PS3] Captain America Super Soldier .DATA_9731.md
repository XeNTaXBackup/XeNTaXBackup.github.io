## Post #1
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2012-10-12T07:06:50+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

[Captain America: Super Soldier](http://www.youtube.com/watch?v=e5EEhanNb8I)! It's like that one Batman game where you jump & flip around all the while dropping baddies! Except with a shield and spangly outfit!

Nabbed the PS3 version and extracted the game.psarc and am now looking at what I assume are the files that hold the character models/textures. Honestly don't know how to work with them, so I turn to this community for help. [Here's a screenshot of the files.](http://imageshack.us/a/img9/9821/capture045.jpg) (Ignore that 7-Zip thinks that it can open them) [Here's what one of the .DATA files look like opened up.](http://imageshack.us/a/img33/4580/capture048.png)

Info on what engine the console versions run is scarce, though UE3 gets (falsely) brought up a lot. Looking at the box art for clues doesn't seem to help, that or I'm just missing it. ([360 Box Art](http://www.covergalaxy.com/forum/attachments/microsoft-xbox-360/12255d1318776642-captain-america-super-soldier-ntsc-cover-disc-captain-america-super-soldier-cover-.jpg)/[PS3 Box Art](http://www.hkofferhouse.com/images/cover/ps3/Captain%20America%20Super%20Soldier%20-%20U.S%20Ver.%20%28PS3%29%20cover%20back.jpg))

I'm willing to provide whatever I can in return for someone's help, I'd be eternally grateful.
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-10-12T08:56:25+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

Possibly the game engine is Havok (unless its for the physics...) according to cover and audio is handled by wwise seemingly thus wwise adpcm/vorbis used if after the audio.

The files screenshot is really useless as what matters is the content, like some hex dump small view or PM sample if anyone gets interested enough.
## Post #3
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2012-10-12T08:57:50+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

> Reply from Apollo
>
> Possibly the game engine is Havok (unless its for the physics...) according to cover and audio is handled by wwise seemingly thus wwise adpcm/vorbis used if after the audio.

The files screenshot is really useless as what matters is the content, like some hex dump small view or PM sample if anyone gets interested enough.

Something like [this](http://imageshack.us/a/img33/4580/capture048.png) right?
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-10-12T08:59:18+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

yes but please use a actual hex editor not Notepad for it.
## Post #5
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2012-10-12T09:00:29+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

> Reply from Apollo
>
> yes but please use a actual hex editor not Notepad for it.

Got a suggestion for a hex editor? I'll take a shot of that then.
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-10-12T09:06:02+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

XVI32 for one but any of them would do, anyhow it gives those talented enough something to look at if seems familiar archive type or whatever.
If lucky somebody helps, whatever your after for, I would only know about the audio aspect due wwise, not workings of Havok engine else.

EDIT: looks like potentially a file list table or such of an archive, anyhow I wouldn't hold breath for getting what you are after unless some expert shows up and is motivated to work it.
## Post #7
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2012-10-12T09:12:06+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

> Reply from Apollo
>
> XVI32 for one but any of them would do, anyhow it gives those talented enough something to look at if seems familiar archive type or whatever.
If lucky somebody helps, whatever your after for, I would only know about the audio aspect due wwise, not workings of Havok engine else.

Well I'm specifically looking for help on character models, but I'll provide info and samples of the other files if asked. I've updated my links with shots of XVI32 as opposed to Notepad++. Thanks for setting me straight on that.

> Reply from Apollo
>
> EDIT: looks like potentially a file list table or such of an archive, anyhow I wouldn't hold breath for getting what you are after unless some expert shows up and is motivated to work it.

Wasn't holding my breath as this hinges on someone's help, though what you say isn't exactly a confidence boost. Doesn't hurt to try though!
## Post #8
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-13T18:35:01+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

For what it's worth, I also think this would be a great game to convert. There's an xbox version too so it's very doable.
## Post #9
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2012-10-14T00:05:05+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

> Reply from dragbody
>
> For what it's worth, I also think this would be a great game to convert. There's an xbox version too so it's very doable.

pic

If I recall correctly the files were locked away in big DATA packs on the 360 version, Tosyk's thread [here](http://forum.xentax.com/viewtopic.php?f=10&t=7016&p=56711&hilit=captain+america#p56711) confirms this.

Though the support is appreciated.
## Post #10
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-29T04:54:15+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

good news, I can extract meshes with hex2obj tool from shakotay but I don't know how to convert the uv data
## Post #11
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2013-11-30T04:02:00+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

Ha, nice!

Maybe shakotay could help with the uv data?
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-30T09:18:11+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

If someone will try real hard, we could get those models with bones+weights.
[cap.jpg](https://xentaxbackup.github.io/file/6811_cap.jpg)
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-05-09T11:07:38+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

> Reply from zaramot
>
> If someone will try real hard, we could get those models with bones+weights.hey, i would like to help with this. can you explain the process?

p.s.: i can even upload converted meshes after all.
## Post #14
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2014-06-08T07:05:35+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

> Reply from zaramot
>
> If someone will try real hard, we could get those models with bones+weights.

Is there any update on this?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-08T11:10:03+00:00
- Post Title: [PS3] Captain America: Super Soldier .DATA

someone would have to check these blocks in captainamerica.mesh:

```

062670  >00 01 02 00 6D 16 11 3F  01 A7 00 00 0C E0 3F D4
062680   BA 0D 2E 49 39 2C BC 00  39 A2 3B 9C 39 A2 3B 9C
062690   39 A2 3B 9C C3 0A CB 4D >00 01 02 00 72 D1 0B DE
0626A0   01 4E 00 00 0C E0 3F D4  BA 0D 2E 5A 39 2B BC 00
0626B0   39 A1 3B A5 39 A1 3B A5  39 A1 3B A5 C1 C7 CB 53
0626C0   >00 01 03 00 76 40 08 3E  01 7E 00 00 0C A0 3F D6
0626D0   BA 0D 2E 2B 39 2C BC 00  39 A9 3B D4 39 A9 3B D4
0626E0   39 A9 3B D4 B5 A7 CB 7B >00 01 03 00 77 B5 06 BD...
```

These are 3 blocks of 1735 (for upper left body) with a size of 40 bytes each.
Maybe weights contained.
At offset 24 could be uv data (0x39A2, 0x3B9C, big endian, word/unsigned int16):



captnA_upperLeftBody.JPG (107.85 KiB) Viewed 146 times
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-07T12:02:25+00:00
- Post Title: Re: [PS3] Captain America: Super Soldier .DATA

> Reply from shakotay2
>
> someone would have to check these blocks in captainamerica.mesh:
Code: Select allOffset    0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

062670  >00 01 02 00 6D 16 11 3F  01 A7 00 00 0C E0 3F D4
062680   BA 0D 2E 49 39 2C BC 00  39 A2 3B 9C 39 A2 3B 9C
062690   39 A2 3B 9C C3 0A CB 4D >00 01 02 00 72 D1 0B DE
0626A0   01 4E 00 00 0C E0 3F D4  BA 0D 2E 5A 39 2B BC 00
0626B0   39 A1 3B A5 39 A1 3B A5  39 A1 3B A5 C1 C7 CB 53
0626C0   >00 01 03 00 76 40 08 3E  01 7E 00 00 0C A0 3F D6
0626D0   BA 0D 2E 2B 39 2C BC 00  39 A9 3B D4 39 A9 3B D4
0626E0   39 A9 3B D4 B5 A7 CB 7B >00 01 03 00 77 B5 06 BD......, I preferred improving hex2obj's multi mesh feature:



CaptainAmerica_1.JPG (134.97 KiB) Viewed 60 times


But creating the H2O files automatically still requires too much format analysing.
## Post #17
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-04-13T06:58:37+00:00
- Post Title: Re: [PS3] Captain America: Super Soldier .DATA

Yes its around 2 years since but whatever happened to zaramot's findings with this one?
