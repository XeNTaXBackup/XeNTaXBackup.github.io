## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-18T19:48:14+00:00
- Post Title: Hex2obj help?

Hi,
I'm trying to use Hex2OBJ to get models from Frogger 3D on the Playstation. I'm having trouble finding the addresses of the vertices and faceindices - I also have pretty much no idea what I'm doing, even with the tutorial provided   

I'm unsure where to begin when using the program and could use a little extra help from someone who knows what they're doing better than I do.

I've provided three files which all have the same headers but all contain different stuff inside, not really sure what I'm looking for in each (are they even models?) and the game's archive itself. If someone could help me out and also tell me what they did it'd be greatly appreciated  [http://puu.sh/eHq3R.zip](http://puu.sh/eHq3R.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-18T20:42:22+00:00
- Post Title: Hex2obj help?

The samples are too small to get a decent point cloud from.
Are there others with about 30..60kB?
## Post #3
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-18T21:07:58+00:00
- Post Title: Hex2obj help?

I sent the game's archive, too, FROGPSX.MWD, which I assume the model header is ".FOM" or 0x02 0x46 0x4F 0x4D
I just extracted a few of my own, which obviously aren't enough to be models  but maybe there's something readable in there?
also, the models in this game are VERY low poly, so I would assume most models have very low filesizes.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-18T21:25:26+00:00
- Post Title: Hex2obj help?

well, one nice structure inside the MWD but sadly I don't have the time to explore it.

Might be the representation of a model or a regular texture, don't know.



FrogPSX-MWD.JPG (39.6 KiB) Viewed 198 times



(PS3 files use big endian, iirc)
## Post #5
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-18T22:24:35+00:00
- Post Title: Hex2obj help?

Interesting. What about face indices?
## Post #6
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-20T03:11:05+00:00
- Post Title: Hex2obj help?

Okay, I've found a way to unpack the PC version correctly, it should use the same formats I think. I have some files which definitely contain models, any chance of finding something in these?
[http://puu.sh/eLp9d.WAD](http://puu.sh/eLp9d.WAD)
[http://puu.sh/eLphN.WAD](http://puu.sh/eLphN.WAD)
## Post #7
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-01-24T19:10:42+00:00
- Post Title: Hex2obj help?

I've been trying to get the models in this game too. A few files have a scrambled alphabet that you've said to look for, but I don't understand how to find the start of the vertices using hex2obj. I've looked all over the forum but I haven't found much helpful information.
