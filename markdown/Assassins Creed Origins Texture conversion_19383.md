## Post #1
- Username: zerozone
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 16, 2015 3:17 pm
- Post datetime: 2019-01-25T22:48:07+00:00
- Post Title: Assassins Creed Origins Texture conversion

Guys I'm trying to convert ACO Textures to any known format but I can't get anything to work, the code looks extremely complex (at least for me) :/
Anyone would be able to help?

Thank you!!! 



Capture2.jpg (185.06 KiB) Viewed 102 times



Original file:

[https://we.tl/t-hpJbhbqO5X](https://we.tl/t-hpJbhbqO5X)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-26T01:52:45+00:00
- Post Title: Assassins Creed Origins Texture conversion

looks like 2048x2048 BC7,  need more samples for examination.
## Post #3
- Username: zerozone
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 16, 2015 3:17 pm
- Post datetime: 2019-01-26T10:56:10+00:00
- Post Title: Assassins Creed Origins Texture conversion

Here is some more files:

[https://we.tl/t-4triB9Qlq9](https://we.tl/t-4triB9Qlq9)

The ones calles 0 1 and 2 are terrain textures, I think they have de difuse and displacement map (probably this one in a lower res) I get to see some of the difuse but always with errors 

BC7 I think I'm using the wrong tool   what are you using to convert it?

Thank you!!!!:D
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-26T12:15:51+00:00
- Post Title: Assassins Creed Origins Texture conversion

> Reply from zerozone
>
> BC7 I think I'm using the wrong tool   what are you using to convert it?
i'm using RawTex tool by daemon1 to test for formats
[viewtopic.php?f=18&t=16461](http://forum.xentax.com/viewtopic.php?f=18&t=16461)

all of your samples with file names containing "NormalMap" are BC7
the rest are BC1 (dxt1)

the headers vary in length and the stored width and height in a couple
doesn't work with the data provided so i can't make a script to open all
just yet. maybe there was a problem with extraction? i don't know.
## Post #5
- Username: zerozone
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 16, 2015 3:17 pm
- Post datetime: 2019-01-26T14:25:59+00:00
- Post Title: Assassins Creed Origins Texture conversion

mmm... that's a good question :/
I used 2 tools made by Delutto, Ubisoft Forge Tool and Ubisoft Data Tool
I managed to convert some diffuse textures and some 3d models, and look like they are good, but of course they can have errors on some other areas I'm not using

Will it work better if I send you the packed files or more samples?

Thank you man! you are awesome!
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-26T22:29:55+00:00
- Post Title: Assassins Creed Origins Texture conversion

> Reply from zerozone
>
> Will it work better if I send you the packed files or more samples?
yeah upload some packed files so i can take a peek.
