## Post #1
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2020-10-03T16:34:20+00:00
- Post Title: Iphone .PAK file Extract (Spy Bot Chronicles)

Hello all,

The contents of the iPhone game (2008) Spy Bot Chronicles by IUGO ([https://www.pocketgamer.com/games/01159 ... hronicles/](https://www.pocketgamer.com/games/011593/spy-bot-chronicles/)) are all contained within a .pak file.

I have tried the usual game extractor .pak extractors but none have worked as of yet.

Any help would be greatly appreciated on extracting this iPhone game .pak file.

File linked here: [https://www.dropbox.com/s/kqhhhcq04qa9n ... t.pak?dl=0](https://www.dropbox.com/s/kqhhhcq04qa9n6p/spybot.pak?dl=0)

Many thanks
S.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-03T23:31:41+00:00
- Post Title: Iphone .PAK file Extract (Spy Bot Chronicles)

Hello. I was able to reverse engineer your PAK file and write a tool for extraction
[https://github.com/bartlomiejduda/Tools ... Chronicles](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Spy%20Bot%20Chronicles)


PNGs are being extracted fine [https://imgur.com/a/aFmPoyi](https://imgur.com/a/aFmPoyi)
but other files are compressed. The only thing to do now is to guess the compression.
You can use aluigi's comtype scanner for this [https://zenhax.com/viewtopic.php?t=23](https://zenhax.com/viewtopic.php?t=23)
## Post #3
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2020-10-05T02:08:39+00:00
- Post Title: Iphone .PAK file Extract (Spy Bot Chronicles)

Thank you so much!! That worked brilliantly - I've been trying to get at those for years.

Many many thanks to you!     
Best wishes
## Post #4
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2020-10-05T02:40:22+00:00
- Post Title: Iphone .PAK file Extract (Spy Bot Chronicles)

The only other files I need from this .PAK are a handful crucial .PVR textures.

I wonder if it would be possible to adjust the code of your tool to also extract these .PVR textures as well as the PNGs?
Thank you ever so much
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-05T07:48:04+00:00
- Post Title: Iphone .PAK file Extract (Spy Bot Chronicles)

> I wonder if it would be possible to adjust the code of your tool to also extract these .PVR textures as well as the PNGs?
>
> Thank you ever so much
Sorry, but it's not possible. Compression type is currently unknown.
## Post #6
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2020-10-05T11:52:53+00:00
- Post Title: Iphone .PAK file Extract (Spy Bot Chronicles)

Ah ok, thanks all the same
