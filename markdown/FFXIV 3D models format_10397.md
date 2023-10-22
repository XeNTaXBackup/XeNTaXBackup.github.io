## Post #1
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2013-05-06T07:50:39+00:00
- Post Title: FFXIV 3D models format

Hey!

I was curious if anyone knew how to read the format for ffxiv v2 3D models, I already tried Noesis with no success and went through the topics to find informations but I didn't suceed to find anything relevant.
I'm pretty novice in 3D formats so maybe it is very obvious but that's just not my field of expertise.

Here is an extract of:
.mdl : model
.sklb : skeleton
.pap : animation

It would be greatly appreciated if somebody was interested in looking into this 
[ffxiv.zip](https://xentaxbackup.github.io/file/6387_ffxiv.zip)
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-05-06T13:21:10+00:00
- Post Title: FFXIV 3D models format

Where/How did you get the example ?

T.
## Post #3
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2013-05-06T14:17:53+00:00
- Post Title: FFXIV 3D models format

I extracted it from the dat files. (you can downlaod it here: [http://eu.finalfantasyxiv.com/benchmark/en/index.html](http://eu.finalfantasyxiv.com/benchmark/en/index.html))

btw, I found that the .sklb files are easy to read with the Havok Content Tools, just need to truncate the header of the file.
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-05-06T15:43:37+00:00
- Post Title: FFXIV 3D models format

Don't extract the dat. Just rename from .dat to .trb and it will load in Noesis.
## Post #5
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2013-05-06T18:02:17+00:00
- Post Title: FFXIV 3D models format

Thanks for your input MrAdults, however either I didn't do properly what you said or it doesn't work. 

This is FFXIV v2 which has a different file structure from v1, I renamed the concerned .dat0 in .trb and noesis is not able to open the file.
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-05-06T23:18:19+00:00
- Post Title: FFXIV 3D models format

If they changed the format, then no, it won't work. (nor will it probably ever, because I don't intend on ever downloading or playing FF14)
## Post #7
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-08-30T22:56:36+00:00
- Post Title: FFXIV 3D models format

Apologies in advance for this somewhat Necro-post However I have some info.

Now that the NDA on FFXIV ARR has dropped, the WebGL based Model viewer is now in beta.([http://xivmodels.com/](http://xivmodels.com/)) This makes me wonder if it would be possible to start coding a plugin for Noesis, if people are up for doing so, this would have to include the ability to load character data from the client if installed on your PC as well as load the normal models from the game.

.dat0 files appear to be archives and the .index files appear to be what they're name suggests, an index of the files in the corresponding .dat0.

Here are small example files from the game:
[http://www.mediafire.com/download/5ae15 ... _files.zip](http://www.mediafire.com/download/5ae15zwywx144vp/ffxiv_dat0_index_example_files.zip)

Hopefully this is of some use and if any of the .dat files for client character costumes is needed I will attempt to post it here as-well.
## Post #8
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2013-08-30T23:35:03+00:00
- Post Title: FFXIV 3D models format

Reborn? did SE changed the entire engine for reborn?
## Post #9
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-08-30T23:46:06+00:00
- Post Title: FFXIV 3D models format

It uses archive files for faster file access and has a unique setup...
