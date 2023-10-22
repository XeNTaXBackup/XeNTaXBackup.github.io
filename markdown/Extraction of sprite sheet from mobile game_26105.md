## Post #1
- Username: Carvalho243
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 26, 2021 8:46 pm
- Post datetime: 2022-12-20T21:59:26+00:00
- Post Title: Extraction of sprite sheet from mobile game

Hi everyone,

first post here and I wished it wasn't to ask things, but here we are.

I've extracted the files of a game using apktool searching for the sprite sheet of the characters, but stumbled upon a wall of encrypted files that I just have no clue on how to pass. Could anyone here help me on how to extract the PNGs from these files?

The files can be found here:
[https://drive.google.com/drive/u/2/fold ... C8-Vid5SF6](https://drive.google.com/drive/u/2/folders/1mRm3nN5RXq3j4Q9NYPf617C8-Vid5SF6)

I may be wrong, but the path in which I think the PNG are is assets>bin>data

Thanks in advance everyone!

Ps: If the part with the link to the files is not allowed, please delete the post or take this part down. I'm new in this business.
## Post #2
- Username: hanamon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 13, 2023 5:19 am
- Post datetime: 2023-01-12T22:38:48+00:00
- Post Title: Extraction of sprite sheet from mobile game

Please, anyone more knowledgeable on the topic do chime in or correct me if I'm wrong! I really know nothing about KGC, but most mobile games don't just have the image files sitting there to be extracted. Usually they are file types associated with whatever the mobile game is running on. I don't particularly have the time to play KGC and a brief search told me nothing about how the game runs, but since you play, it's probably easy enough for you find out. That information tends to come up while you're first loading the game. From there, it would take a bit of research and the correct tools to extract the images you're looking for, but it's most likely doable.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-13T14:18:24+00:00
- Post Title: Extraction of sprite sheet from mobile game

> Reply from Carvalho243 ↑Wed Dec 21, 2022 5:59 am at Wed Dec 21, 2022 5:59 am
>
> 
Hi everyone,

first post here and I wished it wasn't to ask things, but here we are.

I've extracted the files of a game using apktool searching for the sprite sheet of the characters, but stumbled upon a wall of encrypted files that I just have no clue on how to pass. Could anyone here help me on how to extract the PNGs from these files?Hi,

didn't check for encrypted files, if any.
What I see is characters_assets_all_1fcde29b1fb942c38d3dee08bd933c14.bundle which contains UnityFS in its header (search forum).
(version?  5.x.x 2021.3.13f1)

btw, maybe there's newer versions of UABE (as of 8/2019) meanwhile?
