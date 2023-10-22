## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-08-07T23:55:16+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

ello, I want to rip models from offroad legends (dogbyte studios game) and the files are encrypted

in the android version it is in an unopenable obb file
and in the ios version it is just called data.xpk

I put them in a hex editor and it they both have the same ASCII headers (XPAK) 

but idk what this XPAK/XPK/OBB thing is...heLLp!

IOS XPK:
[https://drive.google.com/file/d/10rM0Ei ... sp=sharing](https://drive.google.com/file/d/10rM0EipZL7RzpI7ngA7yXQb_xU3b2nfJ/view?usp=sharing)

Android FAKE ! OBB:
[https://drive.google.com/file/d/15mmtW0 ... sp=sharing](https://drive.google.com/file/d/15mmtW0EElKh-jp3cnNhrp53aGmXLlS2r/view?usp=sharing)
## Post #2
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-08-15T00:07:24+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

all the other topics are getting replied to but not mine... bump
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-15T00:37:03+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

> Reply from LetMeDownloadPervert ↑Sat Aug 15, 2020 8:07 am at Sat Aug 15, 2020 8:07 am
>
> 
all the other topics are getting replied to but not mine...
And you're wondering why?
## Post #4
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-08-17T10:35:11+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

> Reply from LetMeDownloadPervert ↑Sat Aug 08, 2020 7:55 am at Sat Aug 08, 2020 7:55 am
>
> 
ello, I want to rip models from offroad legends (dogbyte studios game) and the files are encrypted

in the android version it is in an unopenable obb file
and in the ios version it is just called data.xpk

I put them in a hex editor and it they both have the same ASCII headers (XPAK) 

but idk what this XPAK/XPK/OBB thing is...heLLp!

how could anyone help you if you don't at least upload sample?
## Post #5
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-08-18T22:17:58+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

> Reply from Drawing ↑Mon Aug 17, 2020 6:35 pm at Mon Aug 17, 2020 6:35 pm
>
> 
LetMeDownloadPervert wrote: ↑Sat Aug 08, 2020 7:55 am
ello, I want to rip models from offroad legends (dogbyte studios game) and the files are encrypted

in the android version it is in an unopenable obb file
and in the ios version it is just called data.xpk

I put them in a hex editor and it they both have the same ASCII headers (XPAK) 

but idk what this XPAK/XPK/OBB thing is...heLLp!


how could anyone help you if you don't at least upload sample?

uploaded ios and android file
## Post #6
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-08-24T17:58:49+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

Update: the game runs on a really obscure engine called horde3d.
## Post #7
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-09-01T22:42:20+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

sorry if you can't bump here but bump
## Post #8
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-18T17:24:34+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

So I am trying to unpack this file from a game called Offroad Legends by Dogbyte Games. Every other game by Dogbyte seems to use this encrypted file. Sadly I have no experience in programming so I turned to this forum. All I know is that the game is rendered using Horde3D, and the header starts with XPAK.
Data file: [http://www.mediafire.com/file/4xi26ah3r ... a.xpk/file](http://www.mediafire.com/file/4xi26ah3rtgp9hx/data.xpk/file)
## Post #9
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-11-16T16:07:30+00:00
- Post Title: Offroad Legends data.xpk/obb how to open?

I have some good news and some bad news.

Good news! The data is compressed with zlib and I was able to get data out easily. Using texturefinder can find the textures of the trucks.

Bad news... They are all named after bytes and loading them with texturefinder makes some textures look corrupted.
