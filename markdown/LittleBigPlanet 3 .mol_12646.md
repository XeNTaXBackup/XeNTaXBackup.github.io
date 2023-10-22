## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-02-23T21:18:40+00:00
- Post Title: LittleBigPlanet 3 .mol?

LittleBigPlanet 3's meshes use .mol as their format, with the header MSHb. They seem to be compressed, though using offzip on them gives a few files that may be the mesh. Any help would be appriciated, thank you.

[http://puu.sh/g9Ley.zip](http://puu.sh/g9Ley.zip)

If more samples are needed, let me know.
## Post #2
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-02-24T00:02:09+00:00
- Post Title: LittleBigPlanet 3 .mol?

I am also interested in seeing someone help out with this. 3DFormat wrote a script for the first game over at ps23dformat, but the format changed from 1 to 2/3. [http://ps23dformat.wikispaces.com/file/ ... sUVexp.bms](http://ps23dformat.wikispaces.com/file/view/LBP1MSHBto3dsUVexp.bms/479484100/LBP1MSHBto3dsUVexp.bms)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-24T09:58:22+00:00
- Post Title: LittleBigPlanet 3 .mol?

these are the nearest hits I could make for meshes in 0000001E.dat:



0000001E.JPG (84.56 KiB) Viewed 542 times
## Post #4
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-02-27T00:31:50+00:00
- Post Title: LittleBigPlanet 3 .mol?

We found some uncompressed meshes. Any ideas?

[http://puu.sh/gebkx.zip](http://puu.sh/gebkx.zip)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-27T10:18:49+00:00
- Post Title: LittleBigPlanet 3 .mol?

? same idea as before:



data_001_farc_2441.JPG (38.52 KiB) Viewed 501 times
## Post #6
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-03-11T00:27:27+00:00
- Post Title: LittleBigPlanet 3 .mol?

I'm trying to load a model from LittleBigPlanet 3. I'm having some issues here, he's coming out flat and corrupted-looking...



the model in question is this: [http://puu.sh/gvbW3.mshb](http://puu.sh/gvbW3.mshb)

any idea what I might be doing wrong?
## Post #7
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-03-11T02:24:29+00:00
- Post Title: LittleBigPlanet 3 .mol?

Oh, nevermind, the start address for the vertices was wrong.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-11T08:47:30+00:00
- Post Title: LittleBigPlanet 3 .mol?

where would be the fun with hex2obj if it weren't the guessing for the starting addresses?  
Same goes for the uvs:



marlom_mol_1__.JPG (239.83 KiB) Viewed 465 times



btw: your face indices count is too small
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-11T09:50:38+00:00
- Post Title: LittleBigPlanet 3 .mol?

marlom_mol_1_.JPG (46.91 KiB) Viewed 465 times
## Post #10
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-14T16:45:04+00:00
- Post Title: LittleBigPlanet 3 .mol?

We've been using a lot of trial and error to get these models to work, many of them with success:





Though there's a few we can't figure out where the UV's start. Some come out really screwed up.



Here's a few models we're having trouble with, along with h2o's.
[http://puu.sh/gzZya.zip](http://puu.sh/gzZya.zip)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-14T20:35:15+00:00
- Post Title: LittleBigPlanet 3 .mol?

Finding the uv's starting address for char_birds_v2 is a very simple calculation:
0x11403A - 2568x24 (dec.) = 0x104F7A (combined with a courageous step 3 bytes back -> 0x104F77  )
(because there are 3 unknown bytes before 0x11403A)



bird_v2_uvs.JPG (121.56 KiB) Viewed 436 times



What I'm a little bit worried about is the holes in the mesh.

Thought I needed to debug the tri strips algo when it switches to 
     // non-terminal index
     else
        b++;

but then I saw that increasing the number of face indices in hex2obj
forces the vertex count to be exceeded. Strange models?
## Post #12
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-14T21:33:34+00:00
- Post Title: LittleBigPlanet 3 .mol?

Got them working! Thanks.
## Post #13
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-15T00:19:51+00:00
- Post Title: LittleBigPlanet 3 .mol?

There's two more I can't figure out, even using that method:
[http://puu.sh/gAy2s.zip](http://puu.sh/gAy2s.zip)
## Post #14
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-03-15T07:21:50+00:00
- Post Title: LittleBigPlanet 3 .mol?

Newton:


As for sackboy I'm stumped. I think the UVB size needs to be 20, not 24, but I don't know why it would be any different.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-15T08:44:18+00:00
- Post Title: LittleBigPlanet 3 .mol?

sack_boy.JPG (161.18 KiB) Viewed 416 times
## Post #16
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-15T17:39:33+00:00
- Post Title: Re: LittleBigPlanet 3 .mol?

There's one more we're having trouble with. Sorry if we're bothering you. Is there another way of getting UV's mathematically? The method you posted earlier hasn't been working on this model.
[http://puu.sh/gBsV9.zip](http://puu.sh/gBsV9.zip)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-15T22:41:55+00:00
- Post Title: Re: LittleBigPlanet 3 .mol?

> Reply from lemurboy12
>
> Is there another way of getting UV's mathematically? The method you posted earlier hasn't been working on this model.this model has another extension. You need to look for the file's structure before you use a method:



feathers.JPG (144.85 KiB) Viewed 95 times
## Post #18
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-03-16T01:01:01+00:00
- Post Title: Re: LittleBigPlanet 3 .mol?

We've finally completed this model. 



I think we're good to go now, we've learned a lot. Thanks.
## Post #19
- Username: LBPPlayer7
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 21, 2017 5:01 am
- Post datetime: 2019-01-14T22:10:53+00:00
- Post Title: Re: LittleBigPlanet 3 .mol?

I know that this topic is a bit, old, I guess...
But I'm a bit confused by this lol
