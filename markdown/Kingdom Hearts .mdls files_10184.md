## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-03-01T17:06:29+00:00
- Post Title: Kingdom Hearts .mdls files

So I was wondering how the kingdom hearts .mdls files work. 
I was messing with some .wpn files from the game, cutting some pieces here and there to get it to look somewhat similar to the .mdls files and I almost got the load load up fully in noesis. Everything is there like the textures, UVs, bones, # of meshes and the like it's just that all the vertices are all in the exact same spot.
So what part of the mdls file determines where all the vertices are supposed to go? I'm pretty sure that is all i need to know to get them to work.
## Post #2
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-03-02T02:18:56+00:00
- Post Title: Kingdom Hearts .mdls files

The only members who know that format are yaz0r and Revelation. yaz0r made a MDLS viewer/animator for KH1 models, you could try running them in that maybe. It would be enlightening to know the process you went through to get the WPNs to work.
## Post #3
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-03-02T03:03:48+00:00
- Post Title: Kingdom Hearts .mdls files

I really did nothing special.
For example, I took the wpn file for the kingdom key and put in in a hex editor.
looked for "MENV" 


took everything from between that to this



delete it, rename MENV to MOBJ and save the file as a mdls.

Everything seems to be correct except for where the vertices go. they just all seem to be gathered in the exact same spot as one another. I'm pretty sure some of the information I deleted from the file is relevant to that but I don't know what.
## Post #4
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-03-05T09:46:52+00:00
- Post Title: Kingdom Hearts .mdls files

The Dream Staff and the Dream Rod have mdls and wpn files, maybe it's possible to find the verticals by comparing these two files.
## Post #5
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-03-05T19:52:38+00:00
- Post Title: Kingdom Hearts .mdls files

Well after comparing I found where the main model data is stored. 
It's a section that starts with

```
.....@>0........
```

and ends with

```
................
....€.€.........
....€.€.........
```


Between the wpn and mdls of the dream weapons that section is completely different. 
I'm not sure why though
