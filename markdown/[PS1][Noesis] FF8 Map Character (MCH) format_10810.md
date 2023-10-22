## Post #1
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2013-09-26T22:07:50+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

So uh... I was unsatisfied that tere wasn't support for this format in Noesis, since the DAT files wee supported.
No fault to MrAdults fr that though, he didn't have to support FF8 at all technically.

Anyway I wrote an importer. Its not perfect, and its frankly the first format I've ever completely finished a working script for.
It doesn't load animations yet, and since all rotation information is in them, you'll have to unfold he skeleton by hand, but it can be done.

Much thanks to chrrox for helping me with some of the Noesis API stuff, and MrAdults for Noesis itself.

I haven't cleaned out the comments yet, since I may revise it, but I wanted to post it so it would be available, and in case I ever need a backup.

If anyone would like to help with the animation format, it would be appreciated. I don't really know much about animation storage.
I'll post some of my notes later.

EDIT: 
It may have been unclear, but the attached file is a noesis script that will properly load FF8 .MCH models, only without any posing information.
[fmt_ff8_mch.rar](https://xentaxbackup.github.io/file/6648_fmt_ff8_mch.rar)
## Post #2
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-09-27T05:57:29+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

You know, i think Milkshape can open those files, im not too sure though, id have to dig my .mch files out.
## Post #3
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-09-28T18:48:53+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

Oh, amazing! Years of hard work paying off 

iirc, Koral had worked out how to get the rotations in a tpose somehow, I'm trying to track down his/her post.

Probably a silly question, but did you try asking Vehek or Mirex for their notes?

EDIT: Reading the old threads, seems like they might not help much :/

But I did find the post I was after:

[http://forums.qhimm.com/index.php?topic ... 6#msg98726](http://forums.qhimm.com/index.php?topic=8130.msg98726#msg98726)
## Post #4
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2013-10-03T13:00:08+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

Ok first off, no I didn't ask for any notes on anything, from what I saw in the file, there's no room for any sort of T-pose data anyway. Much like FF9, this game does not have a bind pose or T-pose of any kind.

I don't know how Koral managed to get a T-pose, but it was likely some sort of complicated script that "guesses" the rotations based on the position in the bone list and the length of the bone chain... That's how I'd do it if it wasn't so ungodly much work and wasn't just a dirty hack anyway.

Also, speaking of dirty hacks, I wrote one to extract -most- of the models from .ONE archives. These hold the NPCs. It also extracts the Animation files, but I haven't parsed them yet so they're useless right now.

I've been trying to figure out the animations, but I really don't know the first thing about animation storage...

From what I can gather, animation files are as thus:

Animation archive header
SHORT: Number of animations

Animation header
SHORT: Number of frames in this animation
SHORT: Number of bones in this animation

Animation Data (Each frame has this format)
Frame 0
SHORT: X position offset? (Changing these files at all in the game's RAM did nothing... I don't know how to test changes to the animations.)
SHORT: Y position offset? (Its noteworthy that these are the same format for the PSX and PC ports, and I am testing on PSX emulation.)
SHORT: Z position offset? (That said, the actual files I've been using are a combination of PSX and PC exports)
INT(1 for each Bone): Rotations for each bone (This seems to be a 10bit sign tuple stored as a 32 bit Int... this is something I found in another game and it seems to apply here but I can't test it)
[SHORT: padding to align to 4 bytes if necessary]
Frame 1 begins here

the final length of each frame should be 4*bonecount + 6 [+2 for 4 byte alignment]

Meaning most characters, whom have 0x19 (25) bones, will have animation frame lengths of 106 bytes. (4*25 + 6)
Main character files (Squall Zell Rinoa... etc.) Appear not to have animations, but in fact they all have a single frame animation at the very end of their files (I believe it is a standing pose.... this is the closest thing to a bind pose probably) but like I said, I don't know how to read the data, nor how to parse it in noesis yet.
This is all I have on animations...

As for the 10 bit tuple format I suspect... 
The other game I mentioned does it this way
INT & 0x000003FF these bits are the -512 - +511 X value
INT & 0x000FFC00 these bits are the -512 - +511 Y value
INT & 0x3FF00000 these bits are the -512 - +511 Z value
INT & 0xC0000000 these bits are a magnitude scale. b00 is 1x, b01 is 2x, b10 is 4x, b11 is 8x (b indicates binary, not hex.)
These ints are Little Endian, (so 0x3FF00FF0 is F0 0F F0 3F, just like a normal Int....)
I don't KNOW that this is the format the animations use, that's why I need your help guys.

The first bone rotation value is almost always 0x00000000 (which seems to coincide with the bones if you manually pose them in Noesis...)

As for the MCH and ONE scripts, I've added some things and cleaned some things, but mostly the only major difference is that the TIM special transparency flag has been decoded into a more proper function of transparency. (Rinoa and Seifer's feet are no longer transparent, which the hair transparency works correctly now. TIM SPF is weird...)

I'd keep both scripts just in case one doesn't work as well for you as it does for me.

(the ONE script doesn't export the models "normally" it has to read the headerless NPC MCH and read the archive header, and extrapolate a new header for the output MCH. As such, I wouldn't expect any Outputted MCH files to work in FF8, but they should parse in noesis just fine.... I did say it was a dirty hack.)
((There are some ONE archives with a different format, they are few, and I haven't touched them. Some models appear to be a white triangle... this is not an error, they ARE just white triangles... with a white texture and everything. My guess is that these are 'invisible entities' in the game, for positioning interactive objects with no model))
[FF8.rar](https://xentaxbackup.github.io/file/6664_FF8.rar)
## Post #5
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2014-02-27T21:26:59+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

Thanks so much satoh!!!!   

This will help me a lot whith some of my little projects !!!

Seems not to be already perfect (the pose of the characters looks like in a sort of strange exorcism   ) but It's a huge step about the npc models!!!

Now the only 2 things I'd really like to see something more about are the terrains model and the G.F. ones !

Thanks again for this!

You're my hero of the 2014
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-02-28T17:38:08+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

I don't currently have the games file formats handy, but does anyone know if this is the same format used for the world map data itself, not the characters but the actual terrain and whatnot.
## Post #7
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2014-02-28T18:38:42+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

I don't know that but I knew in wich files that info were supposed to be..

if I remember right wmsetit should contain at least terrain textures and some veichles ones (train garden cars ragnarok etc..)


Little edit:

I manually fixed some bones angle and..

here it is! 



(Robin Williams!   )
## Post #8
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2014-03-01T15:34:51+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

Ok..after some "excorcisms" I can say that almost all the umanoid characters have the same bone structure and bone order and to put them in the T-Pose you can just apply the same rotation to the same bones and it makes you obtain a result like the Robin Williams" one 

I don't know if this can be useful but I'll write down here the rotation I apply to obtain that T-Pose and which works whith almost ALL characters (I tested it on many and it works)

For rinoa (both ballroom than classic-outfit models) these transformations are ok to obtain a good T-Pose

0 (root)   
1 (upper body)
2 (lower body) x +180
3 clavicle left y +90 x 180
4 neck
5 clavicle right y -90 x 180
6 tail-skirt x+15
7 Hip left x -90
8 hip right x +90
9 left shoulder y 30
10 head
11 right shoulder y-30
12 tail-skirt
13 Left Femur y +90
14 Right Femur y -90
15 left humerus y 30
16 (Hairs) X -160°
17 right humerus y +30° 


What I saw till now on all the models is that the number of the corresponding bone is the needed rotation for hips, shoulders,clavicles, humerus is always the same.
Another interesting fact is that:
bone 0 is always root (ofc   )
bone 1 always controls upper part of the body (head, hairs, arms)
bone 2 always controls lower part of the body (legs,tail,skirt, etc)

Probably apply this rule to every "npc" is not good since there are some animals vehicles and other stuffs that need "custom" angle settings.

I'd write a script for it but I don't have the skills for that even if I'd like to learn if I'll ever find the time to do it..anyway I hope that my little contribution can be useful somehow!


I'm very thankful to this community (and Qhimm's one too i must say it )  because whatching the models structure I learned a lot
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2014-03-16T07:33:40+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

I love this FF8 its one of the best i play years ago, imagine if we can made a upgrade version.
## Post #10
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2014-03-16T08:18:06+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

Actually I saw this video that looks quite interesting..it's the first real graphical working mod of the game I see indeed.. 


[http://www.youtube.com/watch?v=PFfsVcNkUZ4](http://www.youtube.com/watch?v=PFfsVcNkUZ4)

there is still hope i guesss
## Post #11
- Username: dragoncrest
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 21, 2014 11:47 pm
- Post datetime: 2018-02-19T10:55:17+00:00
- Post Title: [PS1][Noesis] FF8 Map Character (MCH) format

anyone know where to export main character's animation? (.MCH or chara.one)
i open MCH with 'fmt_ff8_mch.py' and Noesis show:
