## Post #1
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-08T19:06:38+00:00
- Post Title: Space Channel 5 Part 2: Model format help

First of all,
I have gotten a hang of the .CD1 files used for character models (pointer info, a Ninja Model and a corresponding PVM archive)
Next up are the .RBP files, They are just a newer version of the .RB files from Space Channel 5 (the first one that is),
And as such they also contain camera data, map data and textures.

There are also these CDR files that seem to be containers for report data,
They have LOD models for characters as well as animations and what can only be assumed to be command data for the actual gameplay part of things.

The animation data and the LOD models are what I need help with,
The animation data (.MTN files ive been calling them since they have the header DMTN) are an enhanced form of DMDM (again from Space Channel 5)
which in turn is an enhanced form of NMDM animations (standard Ninja animations)

I have tried forcing Noesis to load the CDR files as RB files to little success.
And forcing Noesis to read just the DMTN files with a python script causes the animations to come out horribly deformed.

As such I am requesting help from these lovely forums
Hope I get a responce soon.

Links:
[http://www.mediafire.com/file/dd141odkp ... round1.cdr](http://www.mediafire.com/file/dd141odkpdchj5d/round1.cdr) - CDR file
[http://www.mediafire.com/file/8769dqz52 ... title0.rbp](http://www.mediafire.com/file/8769dqz52mgb5l9/title0.rbp) - RBP file
## Post #2
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-10T11:10:30+00:00
- Post Title: Space Channel 5 Part 2: Model format help

bump
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-10T12:11:55+00:00
- Post Title: Space Channel 5 Part 2: Model format help

> Reply from Morolian
>
> And forcing Noesis to read just the DMTN files with a python script causes the animations to come out horribly deformed.1) you should be more clear what you tried exactly.
2) what about the py script?

.rb seems to be a format handled internally by Noesis.
So there's no python source, hard/not to handle.



title0-rb.jpg (64.4 KiB) Viewed 108 times



The exported skeleton bones (pilot?) don't help either, no specific names, no hierarchy:
  2 "bone000"  -1
  3 "bone001"  2
  4 "bone002"  2
  5 "bone003"  2
  6 "bone004"  2
  7 "bone005"  2
  8 "bone006"  2
  9 "bone007"  2
  10 "bone008"  2
  11 "bone009"  2
  12 "bone010"  2
  13 "bone011"  2
  14 "bone012"  2
  15 "bone013"  2
  16 "bone014"  2
  17 "bone015"  2
  18 "bone016"  2
  19 "bone017"  2
  20 "bone018"  2
  21 "bone019"  2
  22 "bone020"  2
  23 "bone021"  2
  24 "bone022"  2
  25 "bone023"  2

There's several submeshes with bones.

State of now I guess it's very unlikely that someone will dig deeper into this. Just my 2 cents.
## Post #4
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-10T12:19:50+00:00
- Post Title: Space Channel 5 Part 2: Model format help

> Reply from shakotay2
>
> Morolian wrote:And forcing Noesis to read just the DMTN files with a python script causes the animations to come out horribly deformed.1) you should be more clear what you tried exactly.
2) what about the py script?

The python script was something my friend cooked up,
It was originally for .NJMs but he edited it so that it wouldnt make Noesis crash when loading the DMTN files,

As I said,
My main gripe is the DMTN files,
The .RBP files are no problem (for the most part).
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-10T12:32:44+00:00
- Post Title: Space Channel 5 Part 2: Model format help

I see.

You really should have mentioned that you opened a SC5 animation thread 9 months ago:
[viewtopic.php?f=16&t=14805&p=122534&hilit=dmtn#p122534](http://forum.xentax.com/viewtopic.php?f=16&t=14805&p=122534&hilit=dmtn#p122534)
## Post #6
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-10T12:35:33+00:00
- Post Title: Space Channel 5 Part 2: Model format help

Yes,
But that one only got as far as the animation files for Space Channel 5 (Part 1)
and those are different from the animation files for Space Channel 5 Part 2.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-10T12:42:45+00:00
- Post Title: Space Channel 5 Part 2: Model format help

what about the DMDM format? Did you examine it?

I feel you want to keep things secret? That's ok but it may take another 9 months until MrAdults will implemet DMDM support into Noesis (don't have DMDM samples to check that) and another 2 months to understand how DMTN works
## Post #8
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-10T12:48:36+00:00
- Post Title: Space Channel 5 Part 2: Model format help

> Reply from shakotay2
>
> 
I feel you want to keep things secret? That's ok but it may take another 9 months until MrAdults will implemet DMDM support into Noesis (don't have DMDM samples to check that) and another 2 months to understand how DMTN works

He already implemented it a while back lol.

check with these rb files (open R11 then R10 then scroll through the sub meshes until you get to Ulala's mesh, thats the animated mesh)
[http://www.mediafire.com/file/u56an8twr9tj62w/DMDM.7z](http://www.mediafire.com/file/u56an8twr9tj62w/DMDM.7z)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-10T16:04:16+00:00
- Post Title: Space Channel 5 Part 2: Model format help

> Reply from Morolian
>
> He already implemented it a while back lol.aah, see. had to update to 428 to get the anim played. That's cool. 



Ulala_DMDM.jpg (70.12 KiB) Viewed 93 times


But when I try to export Ulala (sub-model123/135 or 127/135) with anim (as fbx, collada or smd) it always exports the first sub-model (1/135). Skinned mesh but without animation data.

(Having the DMDM animation data might help to understand NMTN animation format.)
## Post #10
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-10T16:06:22+00:00
- Post Title: Space Channel 5 Part 2: Model format help

You need to export anims as a multi fbx for it to work
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-10T16:15:01+00:00
- Post Title: Space Channel 5 Part 2: Model format help

how? There's 35 of -fbx... params in Noesis but none of them appears to switch to "multi"

-fbxmultitake?
## Post #12
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2017-07-10T17:56:03+00:00
- Post Title: Space Channel 5 Part 2: Model format help

It's not a parameter, its a file format
.multifbx to be exact (its like the opposite of a psf the multifbx being a psflib and the multiple separate fbxs being the psflib)
