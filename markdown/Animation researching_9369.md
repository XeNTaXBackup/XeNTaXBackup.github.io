## Post #1
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-07-29T19:01:22+00:00
- Post Title: Animation researching

Hello,
I'm quite searching some information about animation-format researching for some time, but couldn't even find anything. So I'm asking the guru's from this forum:
Is there a way, you could give us some hints on how to find some animation-data in files? I'm not asking for a complete tutorial, a few notes were enough (better than nothing). I think a lot of people were interested in this.

Thank you, and sorry when already a topic to this exists, I'm not about to ignore that. So links are also welcome!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-08-08T09:18:55+00:00
- Post Title: Animation researching

> Reply from pivke
>
> Is there a way, you could give us some hints on how to find some animation-data in files? I'm not asking for a complete tutorial, a few notes were enough (better than nothing).There is no 'easy way'.

What is your background? Do you know the basics (matrices, keyframes etc.?)

This is an excerpt from an *.x-File (Textformat) to get an idea of the data structure:

```
    {Armature_Bone_010}
    AnimationKey { //Position
      2;
      41;
      0;3;    -0.000000,0.685021,0.000000;;,
      1;3;    -0.000000,0.685021,0.000000;;,
      2;3;    -0.000000,0.685021,0.000000;;,
...
      38;3;   -0.000000,0.685021,0.000000;;,
      39;3;   -0.000000,0.685021,0.000000;;,
      40;3;   -0.000000,0.685021,0.000000;;;
    }
    AnimationKey { //Rotation
      0;
      41;
      0;4;    -0.988916,-0.116904,0.071956,0.056577;;,
      1;4;    -0.988916,-0.116904,0.071956,0.056577;;,
      2;4;    -0.988916,-0.116904,0.071956,0.056577;;,
...
      38;4;   -0.988916,-0.116904,0.071956,0.056577;;,
      39;4;   -0.988916,-0.116904,0.071956,0.056577;;,
      40;4;   -0.988916,-0.116904,0.071956,0.056577;;;
    }
    AnimationKey { //Scale
      1;
      41;
      0;3;    1.000000,1.000000,1.000000;;,
      1;3;    1.000000,1.000000,1.000000;;,
      2;3;    1.000000,1.000000,1.000000;;,
...
      38;3;   1.000000,1.000000,1.000000;;,
      39;3;   1.000000,1.000000,1.000000;;,
      40;3;   1.000000,1.000000,1.000000;;;
    }
  }
```

But be informed that this is only one of many possible formats.

This is an excerpt from a decoded xmot file of Gothic 3, a Piranha bytes Game:

```

28.953161 62.622551 81.680565 
0.000000 0.000000 0.000000 1.000000 
1.000000 1.000000 1.000000 

7C 04 00 00  BC EA C3 00  02 00 00 00  A4 EA C3 00  18 EB C3 00  
02 00 00 00  D3 DF C5 00  F8 F3 C0 2C  98 EB C3 00  28 F0 C5 00  

 !FH_Dragon_Left_Leg_Leg_1_New Layer_NEWIKGoalHelper

-19.221125 0.000000 -14.409900 
0.000000 -0.022962 -0.000000 0.999736 
1.000001 1.000000 1.000000 

7C 04 00 00  BC EA C3 00  02 00 00 00  A4 EA C3 00  18 EB C3 00  
02 00 00 00  D3 DF C5 00  F8 F3 C0 2C  98 EB C3 00  28 F0 C5 00  

 !FH_Dragon_Spine_Spine_1_New Layer_GradientRotation
    13 Frames.  LP

   0 0.000000  -19.220705  0.000000  -14.409900
   1 0.040000  -20.047342  -0.000000  -14.662723
   2 0.080000  -22.300449  -0.000001  -15.352195
...
  11 0.440000  -51.983521  -0.000006  -24.718256
  12 0.480000  -52.383598  -0.000006  -25.123568

    13 Frames  LR*

   0 0.000000  0.000000  -0.022950  0.000000  0.999725
   1 0.040000  0.000000  -0.020875  0.000000  0.999756
   2 0.080000  0.000000  -0.015229  0.000000  0.999878
...
  11 0.440000  0.000000  0.058321  0.000000  0.998291
  12 0.480000  0.000000  0.058535  0.000000  0.998260
```


You will find that animation files often are in binary format.
So knowledge of IEEE754  (floating point format) is required to translate something
like 00 00 0x80  0x3F to "1.000000".

This and the knowledge of the x-File format was the way how i decoded the binary G3 xmot format to
a (more or less) readable text file.

HTH

PS: [viewtopic.php?f=16&t=6392&p=76559&hilit ... ion#p76559](http://forum.xentax.com/viewtopic.php?f=16&t=6392&p=76559&hilit=animation#p76559) might be interesting...
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-09T18:41:04+00:00
- Post Title: Animation researching

Binary data is made simple with good hex viewers (not some free basic one that only shows a hex dump and nothing else). Just grab something like hex workshop or 010 editor and hex is no problem.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-10T04:01:47+00:00
- Post Title: Animation researching

One thing is to first find a game where extracting animation data is simple and easy.

Things that make extracting animations easy:
1.) Vertices use simple blend weights and blend indices.
2.) Models use a simple joint/bone skeleton system.
3.) Animation data is simple keyframe-based HPB angles on the joints.
4.) You know your modeler format well.

Unfortunately, a lot of games don't follow 1.) 2.) or 3.). For example, Dynasty Warriors doesn't follow 1.), Saint's Row Third doesn't follow 2.), etc. I think I've only seen one game that follows them all and that was Hyperdimension Neptunia MK2.
## Post #5
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-03-19T20:21:46+00:00
- Post Title: Animation researching

I have actually tried  extracting an animation once. I managed to get the bones and frame length. I realized the order Quaternion + Vector (float[4] and float[3]).
Then right in the middle of the stream of these transforms (Quat and Vectors). There was a junk unexplainable section. I think probably an animation effect for coding to trigger sfx or something. This data was of variable length in each file and got me frustrated into quiting.

For the most part no one will store there animation in matrices, scale and position is also ignored except for the root bone. 
When you open the file in an hex the might see the pattern quite visibly especially if they use a quaternion representation (w,x,y,z w is usually 1 or -1 [rarely]).
This is so because animations eat ram and some games want to load only when it is needed and not at level start so they make the data as small as possible and quaternions are better than euler (regular x,y,z rotation).

I am just rambling.
