## Post #1
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-08-15T18:48:22+00:00
- Post Title: Gladius Animation Help

I'm looking for a bit of help with some animation files for Lucas Arts Gladius.


I've attached a couple of sample files from the demo, one (the smallest) a training dummy and one for a standard barbarian character.
I've so far figured out the simple info below, but am struggling to get out the actual keyframe data. I've extracted and build the skeletons (though struggling to skin them) , and ideally i'd like to at least test running the animations on the skeletons.
Code for this and other things is at : 
[https://code.google.com/p/xexuxjy-xna-g ... ModelNamer](https://code.google.com/p/xexuxjy-xna-games/source/browse/#svn%2Ftrunk%2FGladius%2FUnpacking%2FModelNamer)

Thanks to anyone looking at this.

(all the files work on a series of 4byte section tags, followed by an int32 containing the section length)

For a given animation file :
PAK1 , sectionlenght, numAnimations, animationNameStart

null separated list of animation names.

Then for each animation
VERS tag and length
CPRT tag and length
HEDR tag and length
NAME tag and length <-- names of bones used in this anim
BLNM tag and legnth <-- event names ?
MASK tag and length <-- ??

BKTM tag and length  <-- This section seems to be a list of animation timesteps (0.033,0.066,etc) with a float32 for each timestep
BOOL tag and length <-- seems to contain same number of entries as bktm above, with an int32 for each, seems to be alimited set of values , might be animation events
DCRT tag and length <-- not sure, one of the following values is the number of bones from the NAME tag. might be header info for dcrd below
DCRD tag and length <-- assuming this is the main anim data, pos,rotation, scale etc, but doesn't seem to be in an open format. possibly packed

These two tags only appear in some anim files, not all.
DCPT tag and length 
DCPD tag and length


--------

I've since found out that the animations are done using a discrete cosine transform system, similar to mp3 encoding so the usual approach of modifying fields and checking for results doesn't work so well....
[anim-zip.7z](https://xentaxbackup.github.io/file/7663_anim-zip.7z)
