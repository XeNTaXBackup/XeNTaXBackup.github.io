## Post #1
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-06T03:55:08+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

EDIT:

The actual animation format is .MTN (DMTN header).

From what I can tell "30 01 12 00 F5 4B 3F 3E" denotes a frame
and "20 01 11 00 41 0B 34 3E" is unknown

File: [http://www.mediafire.com/download/qa4p3lmqbh42h6q](http://www.mediafire.com/download/qa4p3lmqbh42h6q)
## Post #2
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-07T20:50:14+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

Bump: I really need help with this,
my efforts in cracking these files have been fruitless.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-08T16:53:18+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

In my experience nobody cares for such animation requests.
You don't even tell us the number of bones.

Uploading a suiting skeleton will increase chances that somebody will look at.
## Post #4
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-08T19:40:24+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from shakotay2
>
> 
Uploading a suiting skeleton will increase chances that somebody will look at.

My apologies, I have uploaded the player model in Ninja Chunk Model format and COLLADA.

PS. The model has 62 bones, some are used for attachments and others are "physics" bones.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-08T21:59:41+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

use the sequence E0033D00 to give the walk_x.mtp file a structure.
There's 112 finds, maybe 112 frames, each frame with data for 61 bones (just a wild guess).

Question is how to make sense out of the data (offset 0xC8; bone 0, bone 1):

```
 01 00 02 00 27 4B 2D BC 65 46 2F 41 A0 6B 5F 3D

0x1070:
 00 00 01 00  A8 E4 77 96 76 15 10 8C F6 A2 CB D9  
 01 00 02 00  D5 D7 77 6F B7 14 6D DA F5 F1 67 D9
```

Maybe treating them as words in a first approach?
Where 00 00 00 80 1C 53  for position and 2E 41 13 F3 2C BB for rotation for example?

There should be symmetrical values for these bones then:
12 - 15, 31 - 38, 34 - 41, 35 - 42, 49 -57
but I don't see such.
## Post #6
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-11T05:39:05+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from shakotay2
>
> use the sequence E0033D00 to give the walk_x.mtp file a structure.
There's 112 finds, maybe 112 frames, each frame with data for 61 bones (just a wild guess).

Question is how to make sense out of the data (offset 0xC8; bone 0, bone 1):
Code: Select all 00 00 01 00 00 00 00 80 1C 53 2E 41 13 F3 2C BB  
 01 00 02 00 27 4B 2D BC 65 46 2F 41 A0 6B 5F 3D

0x1070:
 00 00 01 00  A8 E4 77 96 76 15 10 8C F6 A2 CB D9  
 01 00 02 00  D5 D7 77 6F B7 14 6D DA F5 F1 67 D9
Maybe treating them as words in a first approach?
Where 00 00 00 80 1C 53  for position and 2E 41 13 F3 2C BB for rotation for example?

There should be symmetrical values for these bones then:
12 - 15, 31 - 38, 34 - 41, 35 - 42, 49 -57
but I don't see such.

Have you found anything else?
I really need your help with this,
If you're able to do it I will make sure to credit you


P.S I'm autistic (high functioning).
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-11T22:05:13+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from Morolian
>
> If you're able to do itwell, this reminds me of a german joke which says "Ich bin zu allem fähig, aber zu nichts zu gebrauchen"   (capable of everything (i.e. worst things  ) but helpful for nothing)

So, sadly I ran out of ideas atm.

Though that's a nice girl with skeleton you've uploaded, so maybe someone else gets interested:



ulala.jpg (55.46 KiB) Viewed 212 times
## Post #8
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-12T08:03:33+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from shakotay2
>
> 
Though that's a nice girl with skeleton you've uploaded, so maybe someone else gets interested:
ulala.jpg

Well, it was a b*tch to get the model.
For some reason it was in a pseudo-archive ("model".CD1) that contained pointers, an NJCM header and a PVMH.
It was simple to separate the nj and the pvm since they weren't compressed in any form,
but Noesis still doesn't like to export the models with the correct textures, uvs and normals so you have to edit the model a bit for it to look as it does in game,



Also, for some reason, in offsets 08 and 0A (09 and 0B stay as 00), after E0033D00,
It seems to count up:

```
00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
Hex data:
00 00 00 00 00 00 00 00 00 00 01 00 DD AD 7B CE 
4B 17 BF ED 06 AB 49 16 01 00 02 00 3F 13 7B 13 
DD 15 7F 48 07 5E 8F 1A 02 00 03 00 85 F7 79 FB 
C4 13 CB BC 07 70 84 20 03 00 04 00 F9 C7 77 10 
99 14 26 32 09 C0 15 27 04 00 05 00 7A 9B 74 D3 
65 19 ED 36 0C 22 A3 2C 05 00 06 00 09 B7 70 2D 
12 22 66 D4 10 4B 47 2F 06 00 07 00 46 86 6D E1 
81 29 80 8E 14 14 5C 2F 07 00 08 00 A5 1D 6C FA 
CD 2C F7 27 16 3E DE 2E 08 00 09 00 37 5F 6D 91 
DA 2A 30 FC 14 49 50 2E 09 00 0A 00 3C B7 70 92

```


Maybe its pointing to the bone number, as the models bones are bone01, bone02 and so on.
But I wouldn't know, I'm not a hex reverse engineer god like you .

Also, it appears as if the position and rotation is reversed from what you suggested (rotation then position not vice versa) and from origin not from previous bone position and rotation, so it assumes that all bones lay flat, pointing south and all with no position (e.g at origin).
It might not be like that though, as I translated the hex as "## ## = ##.##°" (e.g 2E 41 = 46.65°).

Again, Also only the root bone (bone 0) has positional data, since the game can retarget any animation to any model, and some models have VERY different skeletons, such as Purge's robots, they are in a T pose instead of an I pose like Ulala and various other models (there are even some in an A pose).

P.S. It would make sense for them to be pointers for the bones, since before 00000100 on the first line the hex is just null, so there is only data after that pointer.

P.P.S. Just realized you may have already known about the bones, as I said before, I am not good with hexadecimal code.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-12T10:40:00+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from Morolian
>
> Also, it appears as if the position and rotation is reversed from what you suggested (rotation then position not vice versa)possibly - but why do you think so?

> and from origin not from previous bone position and rotation,I didn't mean the coords to be parent relative, if you're speaking about that. (Most skeletons I've created smds from had absolute bone positions.)

Bone numbers are not the problem here; where I got stuck is not finding symmetrical values for the positions of left leg, right leg and so on.
## Post #10
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-13T00:20:53+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from shakotay2
>
> possibly - but why do you think so?

Because, when typing the values in Blender, it looked more correct using rotation first then position.

Also, an easier starting point would be the first games animation files, It's probably an NMDM (.njm) derivative
since the header for the file is DMDM, and it's stored in an RB file (Space Channel 5 Archive).

If you want to have a look at the DMDM file (I've decided to call them dmd's or sc5a's), It's attached to this post, And since it's in IFF/RIFF (idk) format, It might be easier to reverse engineer.


 report1_01.rar
RAR archive containing model and animation from Space Channel 5 (the first one for the DC). (28.56 KiB) Downloaded 17 times
## Post #11
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-15T06:55:03+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

Bump: Yet again, I really need help with this.

You expect a 14 yo autistic kid to reverse engineer a file format by themselves?
## Post #12
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-20T17:44:41+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

Bump, yet again
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-20T19:50:03+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

your thread is not forgotten so you don't need to bump, Sir.  

Thing is that I'm thinking about a simple approach to a quick animation test.
Simple ways require a lot of thinking in many cases.

Since we've a skeleton (to be loaded into Noesis for example) here you could think of creating an animation file
and drag it onto Noesis then.

Here's an example where I did it with an md5anim file:
[viewtopic.php?f=16&t=12979&p=107262&hil ... me#p107262](http://forum.xentax.com/viewtopic.php?f=16&t=12979&p=107262&hilit=+frame#p107262)

But .x animation is easier to build from assumed 3D animation data than md5anim, I think:

> Frame root_hips {
>
> 
>
> 
>
> FrameTransformMatrix {
>
> -0.000000,-0.000000,1.000000,0.000000,-0.000000,1.000000,0.000000,0.000000,-1.000000,0.000000,-0.000000,0.000000,49.748032,-0.000008,0.000006,1.000000;;
>
> }
>
> That should be a 4x4 rotation matrix and the position (x,y,z, w=1.0).
Another way would be using maxscript.

btw: I was talking about "symmetrical values" but that was rubbish since it was related to the skeleton which we've already.
There's no reason why animation data should contain symmetrical data for symmetrical (mirrored) bones (left arm, right arm)
except for idle pose for example.
## Post #14
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-20T20:49:53+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

> Reply from shakotay2
>
> 
Another way would be using maxscript.

Well, I don't have the money for 3DSMax....
So lets go with DirectX .X.

Also, even the idle animations may be asymmetrical since it is a rhythm/dancing game.

So what have we got at this point apart from a perplexing animation file, a model and the proposed .X file to write the bone data into.
## Post #15
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-08-23T22:54:31+00:00
- Post Title: Space Channel 5 Part 2 (PC) MTN Animation file: Help needed

Bump
## Post #16
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-09-10T08:37:16+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

Bump.....

Yet again.....
## Post #17
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-09-13T15:26:53+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

this thread might as well have goosebumps
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-13T15:57:40+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

I wouldn't know why it should have - like to take it humorous?

There's an interesting thread concerning animation research with a 26 bones skeleton
and a working blender animation file:
[viewtopic.php?f=16&t=15030](http://forum.xentax.com/viewtopic.php?f=16&t=15030)

You might try to understand how it works - could help you with your problem here - a little bit at least.
## Post #19
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-09-15T14:10:35+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

This might be a breakthrough but idk,

In 1ST_READ.bin there are a few strings referencing the MTP files (and "motion files" which have the header, i think DMTN)

It mainly says stuff like "Angle X: %08x Y: %08x Z: %08x" "Sequence Step %02d" "Start SEQ is %-6s",

Apparently the game uses a system called "CharMan" or "Character Sequence Manager" to handle the animation,

And looking through the disassembled code the numbers after the % are integers and floats like "ANG: X = % 8.2f"

I don't know what to do with all this data but I will carry on digging through the jumbled mess that is the disassembled code.

EDIT: The game has a DEBUG MODE, if I can figure out how to enable it it might help us with the file format,
And I'm not sure if the mtp files are animation files anymore because the code does mention NJM files.
## Post #20
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-09-15T15:16:13+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

BREAKTHROUGH:

The MTP files are MulTi Partition files,
and are loaded and referred to in memory as %08x,

They have multiple functions,
But mainly they handle events,
Like with REZ (another game by UGA).

How could I be so stupid   

PS: The game uses quaternion rotation
## Post #21
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-09-21T20:41:54+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

Bump
## Post #22
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-04T05:28:39+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

I randomly reversed and added support for DMDM animations in Noesis last night, and just happened to spot this thread. Looking into it had actually been on my todo list for like...years now? Lucky coincidence!

The DMDM data is similar to NMDM, but much simpler with only 2 potential data types. It's just a list of offsets and counts followed by the uncompressed rotations and optionally translations. The translation for the root is always provided even if translation channels otherwise aren't present.

Haven't looked at the files in question in this thread, but they probably didn't change much (if anything) considering it's an up-port and they're sticking with the same Ninja formats. Support for the DMDM's (automatically loaded from the .rb files and paired to any model with the same number of bones, with an option to load NMDM's from one .rb and pair them to models in any other .rb) will be in the next Noesis build, whenever I get around to that.
## Post #23
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-10-06T21:32:16+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

Could you pm me the python scripts so I might test them on the files I have?
I'm pretty sure these are the same files as you are talking about since they look similar to Ninja Motion Data files with the NMDM header
## Post #24
- Username: Morolian
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Aug 06, 2016 6:24 am
- Post datetime: 2016-10-24T17:46:34+00:00
- Post Title: Re: Space Channel 5 Part 2 (PC) MTP Animation file: Help nee

bump
