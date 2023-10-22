## Post #1
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2012-03-25T01:19:02+00:00
- Post Title: League of legends model problems....

Hello, I'm sorry to bother you, but I have some problems and I think you could be able to help me. 
Well I'm trying toget my hands on League of Legends models...
I'm using Szkaradek's blender imported for the skn files (blender 2.49); then i export the models as colada or fbx (in order to editthem in milk shape 3d; the same black turned faces are shown in 3d max too) and when i import i got the faces turned back... (the surface of the model is black; and the skin applys on the backfaces...) When I import those models in noesis I see part of the model skinned part of the model missing... When I turn on/off toggue face cull (in noesis) I see the missing faces... But still I can't get the model exported right.
I have tried the other skn plugin for blender 2.5x and the plug in for maya... and the result is still the same... faces turned back... I'm attaching asample file plus some screans of my problem.
I hope you can tell me what I'm doing wrong.. and how can I get it fixed...

Thanks for your time and understanding.
## Post #2
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2012-03-28T00:43:20+00:00
- Post Title: League of legends model problems....

...bump...
Anyone out there having the same issues? Or maybe someone know how to avoid them?
## Post #3
- Username: Helop
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 28, 2012 7:25 pm
- Post datetime: 2012-03-28T11:40:32+00:00
- Post Title: League of legends model problems....

I don't know if this is a LoL specific problem, but I also had major difficulties exporting the models.

I think I tried it the way you described but I'm not 100% sure since I was just mindlessly following some tutorial.

So yeah... no solution from me since I'm justa noob with this stuff.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-28T14:09:54+00:00
- Post Title: League of legends model problems....

Was the model like that in blender or only after you exported it?
## Post #5
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2012-03-28T23:37:41+00:00
- Post Title: League of legends model problems....

well in blender it does look nice... flatshaded (since i don't know how to apply the texturesin blender); but itdoesnot look like that in blender... The funny thing is that i exported the same way from max and maya and the result was the same... btw i could post the blend file too...
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-29T21:26:12+00:00
- Post Title: League of legends model problems....

[http://db.tt/tGUTfJrg](http://db.tt/tGUTfJrg)

I found a problem with the noesis plugin I wrote some months ago but I never went back to fix it until napoleon mentioned it. It was with how it was parsing materials; it uses index ranges to indicate which faces use which material, but I didn't realize that.

I've also changed the texture-finding function to basically brute-force the model folder in search of a dds file that has the model's name in it (just cause I can't find where the texName is stored and there's no consistent pattern to the texture names). For the base models, I simply checked whether an underscore was in the model's name and added "_base" if it wasn't.

Also...there are some models where the texture name is not even the same as the model name (eg: DestroyedTower.skn vs. tower_destroyed_diff.dds). This indicates that there must be some file that connects the two...but I can't find it.

Since a blender importer is already available I could just look up the skl format and copy it over...but maybe later.

Oh and I took out the Sanae3D dependency cause it takes away from the whole "Stand-alone plugin" idea.
## Post #7
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2014-04-17T10:12:44+00:00
- Post Title: League of legends model problems....

I would like to notify you that riot has updated their skn file format. On the new models they have released the Noesis script does not work. (3d maya, the 3d max script and the blender script does not work too). The updated file format is currently on the new skins tehy have released, including on the visual update of twitch. I'll upload sample files here:

[https://www.dropbox.com/s/htr36uyt3cob8u7/samples.zip](https://www.dropbox.com/s/htr36uyt3cob8u7/samples.zip)

Any help here would be really appreciated.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-17T12:38:10+00:00
- Post Title: League of legends model problems....

Twitch.JPG (170.7 KiB) Viewed 568 times
## Post #9
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2014-04-17T13:57:51+00:00
- Post Title: League of legends model problems....

Wait is that in Noesis? It does not look like Noesis to me... please post your answer not in just screenshots... I don't recognize the tools you have used, and I suppose most of the members here does not... And here's the error message I get in the latest version of noesis.
[Screenshot 2014-04-17 17.02.04.png](https://xentaxbackup.github.io/file/7227_Screenshot 2014-04-17 17.02.04.png)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-17T14:45:06+00:00
- Post Title: League of legends model problems....

It's hex2obj.exe (view link in my sig for it).

using Noesis:



Twitch_Noesis.JPG (19.58 KiB) Viewed 559 times


changes in fmt_LeagueOfLegends_skn.py:
Only tested with Twitch.skn!

```
        
        idstring = self.inFile.readUInt()
        hasMat, numMesh = self.inFile.read('2H')
        if hasMat:
            numMat = self.inFile.readUInt()
            for i in range(numMat):
                name = self.read_name(64)
                self.inFile.read('4L')
            
            #just hardcode matName for now
            matName = self.parse_material()
            self.inFile.readUInt() # skip 2 bytes, for updated skn format
            numIdx = self.inFile.readUInt()
            numVerts = self.inFile.readUInt()
        else:
            matName = self.parse_material()
            #self.inFile.readUInt()  # ? untested
            numIdx, numVerts = self.inFile.read('2L')

        self.inFile.readBytes(48) # skip 48 bytes, updated skn format
        idxBuff = self.parse_faces(numIdx, matName)
        self.parse_vertices(numVerts)
```
## Post #11
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2014-04-17T16:41:02+00:00
- Post Title: League of legends model problems....

Excuse my stupidity.. but can you post the edited file? I can't seems to place the edited part in the right place. Thank you.

Edit here's the error message i get after placing the edited part...
[Screenshot 2014-04-17 20.50.15.png](https://xentaxbackup.github.io/file/7229_Screenshot 2014-04-17 20.50.15.png)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-17T21:01:13+00:00
- Post Title: League of legends model problems....

well,...
the >>> were just thought to be markers.
They're NOT part of the code.

Try it such as:

```
           self.inFile.readUInt()
```


and 
```
        idxBuff = self.parse_faces(numIdx, matName)

```
## Post #13
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2014-04-18T05:38:13+00:00
- Post Title: League of legends model problems....

Thank you! Now it loads properly. I hope Riot will not change more the file format...
## Post #14
- Username: Prettyfloralbonnet
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 25, 2014 4:44 am
- Post datetime: 2014-07-30T23:16:57+00:00
- Post Title: League of legends model problems....

I just wanted to throw in here that after numerous failed attempts to load the newer (post 4.11 LoL patch) Mecha Aatrox .skn file into anything viewable, this thread and the changes shakotay2 posted finally gave me results.  I tried Maya, Blender, Milkshake, 3DS Max, and a variety of other programs plus any .skn related plugins with no success.
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-07T09:01:58+00:00
- Post Title: League of legends model problems....

[out]
## Post #16
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-07T23:03:04+00:00
- Post Title: Re: League of legends model problems....

Hi all,

This forum gave me a huge hint when they change the .skn format, but now they implemented this new 5 version for animation. And I have already stuck in back engineering using my poor amount of knowledge.

Regarding the new model importer, I have made some changes in Maya plugin and everything works fine. But I could not find how to fix animation imported for version 5.
And all latest models will have this version of animations.

I have uploaded the new aatrox .skn+.skl and 2 .anm files (one with 4 version, another with 5 version).

I will not start the discussion of version 4 format as it is somewhere on the forum, but 5 version seems totally different compare to the 4.
What I have found is: that the new format bones' indexes(names) are located in one row begging from 00002e24 address and total amount is 99 as it mentioned in header.
But still can't understand where to get pos and rotation values =\


 aatrox.7z
skn+skl+anm (249.12 KiB) Downloaded 64 times
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-08T05:46:49+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-08T18:14:16+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #19
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-08T18:45:39+00:00
- Post Title: Re: League of legends model problems....

what do you mean under the completely idle? Maybe I have got your wrong, but all of them have some moves. Sorry, English is not my native.
I honestly can be not the best guy to discuss all this reverse engineering stuff as have no knowledge in this =( 
But I am trying my best to understand what is going on here
## Post #20
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-08T19:35:01+00:00
- Post Title: Re: League of legends model problems....

maybe this archive (skn+skl+anm) will help.


 gnar.7z
idle animation (243.06 KiB) Downloaded 49 times
## Post #21
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-09T01:24:39+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-09T07:54:03+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-09T15:20:57+00:00
- Post Title: Re: League of legends model problems....

> Reply from Wobble
>
> The position and rotation values are the same, but the lists are sorted and indexed differently.
(BFFF, DFFF, 6FFF) is definitely zero rotation, but I don't know how to unpack it.not sure whether I understood you correctly. How you know the values in both anm files are the same?

For aatrox_run.anm the index list starts at 0x794C with 1904 entries.
with these max indices for pos: 1116 and rot: 1099.

First entry's indices are: pos= 619 (26Bh), rot= 921 (399h)

From the quaternion section: rot[921]: [0.134571,-0.0432734,0.0153366,0.98984]
This rotation should be compared to the compressed values the first entry's rot index (of the below mentioned index list) points to, correct?

Does Aatrox_Skin02_Run.anm have the same entry counts for pos and rot (1116/1099)?

Did you create the index list for this anm?

The list at 0x2FB0 with a max index of 1049 seems a little bit strange to me:
1 0 0 
2 0 1 
3 0 2 
4 0 3 
5 0 4 
6 0 5 
7 0 6 
7 0 6 
8 0 7 
9 0 8 
...

81 0 66 
7 0 11 
82 0 67 
83 0 68 
84 0 68 
85 0 68 
84 0 68 
86 0 68 
87 0 69 
88 0 70 
89 0 11 
90 0 11 
91 0 11

btw: "compressed", wouldn't it make more sense if the 3 WORDs for rotation just were yaw, pitch, roll in radians for example (*2PI/65536)?
## Post #24
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-09T19:50:11+00:00
- Post Title: Re: League of legends model problems....

> Reply from Wobble
>
> not a problem.

idle = little or no movement

Some of these "_idle" animations are not actually idle.  They might contain a lot of movement.

Here's a good site to view character animation online:
http://www.lolking.net/models

Although, character models can be complex with many bones.  Here is a better candidate:

SightWard_Futbol.skn
SightWard_Futbol.skl
Sightward_Futbol_Idle1.anm

Very simple model, non-character, only 5 bones.  
Animation only has 3 rotation values.
Code: Select all[ 0] rot: BFFF, DFFF, 6FFF	-> zero rotation?
[ 1] rot: 458E, 27F1, 28A8 
[ 2] rot: 5D5E, 980E, 5163


I don't know how to convert these values into a quaternion rotation.

Thx Wobble for your explanations. It have sense to do the research for the simplest models. 
How do we know that animation has only 3 rotations? I checked sightward_mecha_idle1.anm and found this values between position block and bones block

```
bfff 9fff 7140 
bfff dfff 0fff

```

Using your logic these values refer to rotation.
But if we compare the header block for both sightward_mecha_idle1.anm and Sightward_Futbol_Idle1.anm, we see difference there, so I didn't get where we find this number 3 =\
## Post #25
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-10T02:22:36+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-10T12:53:14+00:00
- Post Title: Re: League of legends model problems....

the WORD/radians solution doesn't work:

```

v5: rot  [0]   C15F, 5DFB, 730B    ->    49503    24059     29451
-----------------------

v4: pos[461] [0,7.2594,-0.150847]  rot[903] [0.0920504,0.000548487,0.00319343,0.995749]
   			                                0.184364 0.000504 0.006461   radians (Yaw,Pitch,Roll)
 
v5:    pos[2] [0,7.2594,-0.15085]    rot[1] [49225,     8197,   29205]
```


Especially when it comes to "zero rotation"
v4:
257 511  [257] [-16.9732,-2.48539e-007,0]  [511] [0,0,0,1]
262 512  [262] [-16.9732,-2.54371e-007,0]  [512] [0,0,0,1]

v5:
70 23   [70] [-16.9732,0,0]  [23] [49151,57343,28671]
102 23 [102] [-16.9732,0,0]  [23] [49151,57343,28671]

it seems you'll need a "number expert" to solve this
## Post #27
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-08-10T14:34:29+00:00
- Post Title: Re: League of legends model problems....

dose it make more sense if you break that 48-bits in 3-15-15-15(high to low) format!?
eg: R_Thumb2
6F FF DF FF BF FF -> 011  011111111111111  011111111111111  011111111111111 -compare to-> quat 0 0 0 1 (eulerAngles 0 0 0)

and C_Buffbone_Glb_Layout_Loc
2F FF DF FF BF FF -> 001  011111111111111  011111111111111  011111111111111 -compare to-> quat 0 1 0 0 (eulerAngles 180 0 180)

for Buffbone_Glb_Weapon_1
2F FF DF FF FF FF -> 001  011111111111111  011111111111111  111111111111111 -compare to-> quat 0 0.707107 0 0.707107 (eulerAngles 0 -90 0)
## Post #28
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-10T18:11:29+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #29
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-08-10T19:15:04+00:00
- Post Title: Re: League of legends model problems....

Sorry, I didn't figure it out yet!

The arrow -> just mean compare to to value! 
I simplely compared the 1st frame of aatrox_skin02_run.anm  and  aatrox_run.anm.
## Post #30
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-10T22:51:29+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #31
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-08-11T10:33:36+00:00
- Post Title: Re: League of legends model problems....

Got it!
Indeed, it is using that 15-bit nonsense format:

assume those 3-15-15-15 value are axisflag s2 s1 s0

```
  s1 = 1.41421*(s1-0x3FFF)/0x7FFF
  s2 = 1.41421*(s2-0x3FFF)/0x7FFF
  s3 = sqrt(1-(s0^2+s1^2+s2^2))

  case AxisFlg of (
   3: return (quat s2 s1 s0 s3)
   2: return (quat s2 s1 s3 s0)
   1: return (quat s2 s3 s1 s0)
   0: return (quat s3 s2 s1 s0)
  )--end case
```
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-11T13:37:06+00:00
- Post Title: Re: League of legends model problems....

wow, you're absolutely incredible!  

checked this with

730b 5dFB c15F
011 100110000101101 011101111110111 100000101011111

which should uncompress to
float x=0.134586, y=-0.044547, z=0.015197, w=0.989783 ;

and, yes, it works!

Only "issue" I have is that x and z values are swapped.
edit: errr, I mixed the params s0 and s2, sry
## Post #33
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-08-11T14:17:03+00:00
- Post Title: Re: League of legends model problems....

Sorry, I didn't check on the actual animation yet, but

In my defination 3-15-15-15 in axisFlag s2 s1 s0 (High to low)
so:
730b 5dFB c15F
011 100110000101101 011101111110111 100000101011111
3   4C2D   3BF7   415F

calculate by hand:

axisFlag = 3 (quat s2 s1 s0 s3)
s2 = 0x4C2D =result=> 0.13457157444990386669515060884426
s1 = 0x3BF7 =result=> -0.044540687887203588976714377269814
s0 = 0x415F =result=> 0.015192172612689596240119632557146

exactly = quat x=0.134586, y=-0.044547, z=0.015197, w=0.989783 !?

PS:
Just before I forgot about the indices part of the animation

```
   dword        Bone_Hash
   word         Index_of_Translation    //Reference to Translation_Table
   word         Index_of_Scale          //Reference to Translation_Table(Vector3_Table)
   word         Index_of_Rotation       //Reference to Rotation_Table
   word         null        
}

Struct AmnIdx_ver_5 {
   word         Index_of_Translation    //Reference to Translation_Table
   word         Index_of_Scale          //Reference to Translation_Table(Vector3_Table)
   word         Index_of_Rotation       //Reference to Rotation_Table
}
```
## Post #34
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-11T14:41:16+00:00
- Post Title: Re: League of legends model problems....

Guys, you did an incredible work!!!

I don't want to bother you, but could any one explain this stuff on the example? I am not a total noob, but want to understand the algorithm to convert this logic into code.
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-11T15:26:24+00:00
- Post Title: Re: League of legends model problems....

@Fatduck: you're right (as always)
Stupid me called such a function:
Quat Fatduck_quatDecompress(short AxisFlag, short s0, short s1, short s2)
but passed AxisFlag, s2, s1, s0 to it.

@krolik: you've to be more precise. (Do you mean "C" code?)
## Post #36
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-11T18:47:08+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #37
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-11T19:39:31+00:00
- Post Title: Re: League of legends model problems....

> Reply from shakotay2
>
> 
@krolik: you've to be more precise. (Do you mean "C" code?)

Actually C++, but I would like to understand the logic even in pseudo code.
## Post #38
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-11T22:59:48+00:00
- Post Title: Re: League of legends model problems....

I was tried to understand all your discussion and stuck at the point that I totally got lost.
Could someone share his code here how to read this anm file?
## Post #39
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-08-17T14:21:11+00:00
- Post Title: Re: League of legends model problems....

As I finished coding, I would like to share an additional information. Maybe, it would be helpful for someone.

The right CASE for decompression will look like:

```
case AxisFlg of (
   3: return (quat s0 s1 s2 s3)
   2: return (quat -s0 -s1 -s3 -s2)
   1: return (quat s0 s3 s1 s2)
   0: return (quat s3 s0 s1 s2)
)
```


The header block changed his structure:

```
   char magic[8]; //always r3d2anmd
   int version;
   int data_size; //size of file = data_size + 12
   char skip1[12]; //skip this block
   int num_bones;
   int num_frames;
   float fps;
   int data_offset1;
   char skip2[8]; 
   int data_offset2;
   int data_offset3;
   int data_offset4;
   char skip3[12];
)
num_pos = (data_offset3 - data_offset2)/12;
num_quat = (data_offset1 - data_offset3)/6;
```
## Post #40
- Username: hypnolem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 18, 2014 7:41 pm
- Post datetime: 2014-08-18T11:44:06+00:00
- Post Title: Re: League of legends model problems....

wow
## Post #41
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-09-02T14:06:37+00:00
- Post Title: Re: League of legends model problems....

So uh, hate to be a bother again, but is there a completed Noesis Script after all this information, or a method of editing the models so they can be viewed? I went over the whole topic but this is a bit over my head...
## Post #42
- Username: finitebytes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 30, 2014 1:06 pm
- Post datetime: 2014-09-14T00:14:20+00:00
- Post Title: Re: League of legends model problems....

So, theoretically, could we get the work done here patched into Riotfiletranslator so that the new model formats can be opened as well has have files saved into that same format?
## Post #43
- Username: vossphorus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 13, 2014 7:02 am
- Post datetime: 2014-10-13T01:01:29+00:00
- Post Title: Re: League of legends model problems....

Hey guys,

First off: I'm really amazed by your detective work on the new *.anm files!

I'm pretty new to this community but I've read all recent posts about League of Legends and it's depending file formats.
I hope I don't ask for something which is already covered somewhere else.

Since the import/export scripts for Maya and Blender are outdated and no longer supported by the developers there's (imho) a need for a simple way to import, modify and export the models.
I'm willing to write an import/export script for Blender (I decided to go with Blender since it's free) but I need some help by a few professionals on this topic.
I've already opened and analyzed the *.skn and *.skl files in a hex editor but I don't quite grasp how it's structured (mainly because I'm relying on old references).

Please don't be too harsh if there's a major fallacy in my naive approach   .
It would be really awesome if someone could explain to me how the position of vertices and faces (etc.) is represented in the files.

Thanks in advance
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-13T15:37:56+00:00
- Post Title: Re: League of legends model problems....

> Reply from vossphorus
>
> I'm willing to write an import/export script for Blender (I decided to go with Blender since it's free) 
[...]
It would be really awesome if someone could explain to me how the position of vertices and faces (etc.) is represented in the files.Afair there's nothing special with the static mesh. Vertex stride of the Twitch is 52 bytes.
Use hex2obj or Noesis to export this model as a wavefront obj. (View posts in this thread as of Thu Apr 17, 2014 1:38 pm
and Thu Apr 17, 2014 3:45 pm.)
## Post #45
- Username: vossphorus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 13, 2014 7:02 am
- Post datetime: 2014-10-13T15:48:54+00:00
- Post Title: Re: League of legends model problems....

> Use hex2obj or Noesis to export this model as a wavefront obj.

I did that already. But there's no way to export *.obj files to *.skn files to create remodels for the game.

But could you please elaborate on the structure of the file itself? What's in the header and where does it end? How are the vertex strides themselves structured?
And maybe someone could take a look at this resource and tell me if it's still useable or just totally outdated: [https://code.google.com/p/lolblender/wiki/fileFormats](https://code.google.com/p/lolblender/wiki/fileFormats).

I'm sorry to bother you with these questions but I'm not a pro at this and I'm still in the process of figuring out what is what.
## Post #46
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-10-14T02:05:24+00:00
- Post Title: Re: League of legends model problems....

Edit: Fixed it forgot to remove the null read which is in v4 but not v5

Maya 2015 64 bit plugin attached

Note: bunch-o debug code still attached.
[RiotFileTranslator.zip](https://xentaxbackup.github.io/file/7944_RiotFileTranslator.zip)
## Post #47
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-10-15T22:19:08+00:00
- Post Title: Re: League of legends model problems....

Also with the introduction of Azir there is a new type of animation format which is "r3d2canm" where all the others have been "r3d2anmd"

Attached Azir's Run which has the new format.

I haven't got further than the header which is
8 Byte - "r3d2canm"
4 byte - version? - 1
4 byte - Length of File - 0xC
4 Byte - "canm"
4 Byte - Sub-version? - 3

Any help would be great!  Unfortunately models, skeletons and animations are my weakest area.
[Azir Run.zip](https://xentaxbackup.github.io/file/7951_Azir Run.zip)
## Post #48
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-16T06:22:27+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #49
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-10-16T22:10:34+00:00
- Post Title: Re: League of legends model problems....

> Reply from Wobble
>
> 
Also with the introduction of Azir there is a new type of animation format which is "r3d2canm" where all the others have been "r3d2anmd"


It looks like it contains the same information from the last .anm format.  But, the data appears to be re-organized in new sections.  It would help if you could find and post the same .anm file, but in an older format.  And maybe the .skn file too.

Attached Azir Solider as it had animations which went from v5 to this new format.
[Azir Soldier.zip](https://xentaxbackup.github.io/file/7961_Azir Soldier.zip)
## Post #50
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-17T00:09:18+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #51
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-10-17T01:55:39+00:00
- Post Title: Re: League of legends model problems....

Awesome, thanks for that!

Time to try work out the position compression then, probably 11-11-10 format.
## Post #52
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-17T03:51:00+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #53
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-17T09:27:10+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #54
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-10-17T12:57:12+00:00
- Post Title: Re: League of legends model problems....

Anytime Riot do a file format it always comes out screwy, tried digging through the assembly but its a nightmare to read.

In other Riot formats 0x40 has been Vector3<Byte> and 0x80 has been Vector3<Float> but there has never been a section for key 0, was me being hopeful for a second but its probably an entire new key list for the file.  I'm struggling to think/find anything at present
## Post #55
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-17T22:34:06+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #56
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-10-18T18:39:30+00:00
- Post Title: Re: League of legends model problems....

```

```


```
[ 1] pos: 0.252120, 91.229507, -20.523630
```


if those are meant to be the same position (Hope they are) then its literally taking the short and divide by 65535.

Going to test on a larger scale

decompressed gives:
0.252728, 91.229667, -20.523630.

```
57897 / 65535
0 / 65535

0.49225604638742656595712214847028          = 0.252728163552
0.88345159075303273060196841382467           = 91.229667763103685053788052185854
0                                           = -20.523630

```


Edit:
Altered it to scale between -1 and 1 instead of whats posted exactly above, obvious what I changed to do that.

Edit 2:
Scale between 0 and 1:
[http://i.imgur.com/x6jWA4p.png](http://i.imgur.com/x6jWA4p.png)

Scale between -1 and 1:
[http://i.imgur.com/QIsbvCj.png](http://i.imgur.com/QIsbvCj.png)


The initial scale between 0 and 1 feels more accurate in terms of numbers instead of scaling it over -1 and 1.
Just need to work out how it all comes together now in terms of what bones are related to what frame.

I have a slight concern about how some seem to have multiple of the same values, unsure if its just for the first frame or not.
## Post #57
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-19T10:57:34+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #58
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-11-13T20:50:41+00:00
- Post Title: Re: League of legends model problems....

Hey, Uli!

Could you please share the Maya plugin code including last changes (better with source code)?   
or may anyone explain the order of the steps during reading this new animation format? v5 anm were more clear for me
to program it.

I have been trying to understand what you were discussing, but it seems like you are talking on unknown language =)
## Post #59
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-11-14T09:20:08+00:00
- Post Title: Re: League of legends model problems....

> Reply from krolik
>
> Hey, Uli!

Could you please share the Maya plugin code including last changes (better with source code)?   
or may anyone explain the order of the steps during reading this new animation format? v5 anm were more clear for me
to program it.

I have been trying to understand what you were discussing, but it seems like you are talking on unknown language =)

The new animation format which we were just discussing needs a better layout mainly because I haven't implemented it yet so unsure on how indexing is done and it be nice to have a explanation just so there isn't any gaps but for v5 its perfectly documented.
## Post #60
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-11-14T18:03:09+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #61
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-11-16T22:43:28+00:00
- Post Title: Re: League of legends model problems....

> Reply from Wobble
>
> The new animation format has reduced the file size in half.  They are now compressing rotation, position, scale, and time.  

The previous versions stored keys by frame number.  Now, keys are stored by time.  This is why they replaced num_frames with anim_length in the header.
I still don't know how to use section #2, but you can probably ignore it.

It looks like there are 2 subsections in section #1.  The first subsection seems to be a fixed list of starting and ending keytimes for each bone.  (e.g. 0x0000 and 0xFFFF).  This is always present.

The second subsection contains a varying number of keyframes, with varying key type (pos/rot/scl), sorted by time (0x0000 to 0xFFFF).  Since each keyframe has a time value, there doesn't seem to be a need to index it.  That's why I don't see the purpose of section #2.

Hey Wobble,

As you told seems that section 1 divided to 2 subsection, so you helped a lot. I don't really understand why subsection1 has 3 blocks with 4 10-bytes lines for rot, pos and scale. You told that we have starting and ending keytimes for each bone, but in this case there should be 2 lines for rot,pos,scale blocks.  

I am stuck with converting keytime to frame number. Do you have any idea how it can be converted? In previous version we have fill frames with position and rot values for all bones. I think this new format could be converted into the same structure. 

Thanks in advance,
You all did the great research job.
## Post #62
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-11-17T01:33:55+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #63
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-11-17T11:11:16+00:00
- Post Title: Re: League of legends model problems....

> Reply from Wobble
>
> 
Time is packed into an unsigned WORD (0x0000 to 0xFFFF).  Use 0 for min value, anim_length for max value to unpack it.

I've got it, but can't unpack time anyway =((.

For example, 
(0C03 0000) EF46 9D31 7876

0C03 = 3075 => 3075 / 65535 = 0.047 * anim_length = 0.1314 or frame number 4.
Is it right?
In this case bone (497252) will stop changing its rotation at frame number 4, but in the old format rotation changed from 0 to 30.

Sorry if I wrote something stupid above, but this format looks strange.

If the 1st subsection has starting and ending keyframes, why 2nd section has keyframes that are outside of range?
For example,
Rotation block for bone 124534019 (subsection1)

```
(0000 0100) B837 965E 826E
(0000 0100) B837 965E 826E
(3C0F 0100) F7B7 AE1E 8F6E
(FF1F 0100) 29B8 5E5E 696E

```


Rotation block - Varying values for bone 124534019 rot (subsection2)

```
(3C2F 0100) 3FB9 E71C F26D
[5798]
(DB36 0100) E2B9 2BDC C76D
[6158]
(FF3F 0100) E2B9 2BDC C76D
[6348]
(FF7F 0100) E2B9 2BDC C76D
[6448]
(FFFF 0100) E2B9 2BDC C76D
[7228]
(FFFF 0100) E2B9 2BDC C76D
```


I also attached the file with old format unpacked data.
[v5_unpacked.zip](https://xentaxbackup.github.io/file/8085_v5_unpacked.zip)
## Post #64
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-11-17T14:42:55+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #65
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-11-25T00:28:38+00:00
- Post Title: Re: League of legends model problems....

Thx Wobble,

I did it! Still need to optimize some parts and play around with TangentType as some animations are playing with "crappy jumps".
## Post #66
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-11-27T23:26:15+00:00
- Post Title: Re: League of legends model problems....

Plugin for Maya 2015 x64
[RiotFileTranslator.zip](https://xentaxbackup.github.io/file/8155_RiotFileTranslator.zip)
## Post #67
- Username: Risky
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 30, 2014 10:05 am
- Post datetime: 2014-11-30T02:45:58+00:00
- Post Title: Re: League of legends model problems....

I would like to thank you guys for the amazing work. The Maya pluggin is pretty much working, I can now import .skn from new skn format, but there is an error on the options. I think the module developer forgot to put the settings, so the part where I could import the .skl alongside with the .skn isn't showing and working. This means that I have to import the .skn and then the .skl, having them both not attached by default.

This isn't reaaally a huge problem because obviously editing the mesh would cause the skeleton to deattach so I would have to paint the connections again anyway, but it can help a bit by knowing the original mesh-bone connections.

I know you guys are also doing a great job in the animations part, I don't usually touch the animations a lot but I wish you the best for making everything work.

Again, many thanks
(and also sorry for my english)
## Post #68
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2014-11-30T16:12:58+00:00
- Post Title: Re: League of legends model problems....

> Reply from Risky
>
> The Maya pluggin is pretty much working, I can now import .skn from new skn format, but there is an error on the options. I think the module developer forgot to put the settings, so the part where I could import the .skl alongside with the .skn isn't showing and working. This means that I have to import the .skn and then the .skl, having them both not attached by default.

Hey Risky,

Importing skn that bonded together with skl is working. While first time importing, change a file type from "All files" to "League of Legends - skin". There you will see File Type Specific Options with Import skeleton checkbox - use it. Next time you don't need to change a file type, this manipulation is needed for the first time you enable the plugin. I didn't try to fix this issue from the original source code.
## Post #69
- Username: Risky
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 30, 2014 10:05 am
- Post datetime: 2014-11-30T16:28:31+00:00
- Post Title: Re: League of legends model problems....

> Reply from krolik
>
> Risky wrote:The Maya pluggin is pretty much working, I can now import .skn from new skn format, but there is an error on the options. I think the module developer forgot to put the settings, so the part where I could import the .skl alongside with the .skn isn't showing and working. This means that I have to import the .skn and then the .skl, having them both not attached by default.


Hey Risky,

Importing skn that bonded together with skl is working. While first time importing, change a file type from "All files" to "League of Legends - skin". There you will see File Type Specific Options with Import skeleton checkbox - use it. Next time you don't need to change a file type, this manipulation is needed for the first time you enable the plugin. I didn't try to fix this issue from the original source code.

I know, that was working on the thispawn's version of the plugin, but on your version it simply gives an error when I select the LoL - Skin option and the box wount appear. I can screenshot it to you.

I was using the thispawn's version without problems on Maya 2013 but now I'm testing your .mll in Maya 2015 and the error is this:

[http://imgur.com/a/jZVwj](http://imgur.com/a/jZVwj)

Maybe I am missing something in the plugin installation?

Thanks for your help!

quick edit: Just to mention, I am using Maya 2015 64bits with the 64bits plugin, it might be relevant

edit2: Just fixed it! I added the scripts and icons from the Thispawn's plugin for the older maya's and it is working now 100%! Thanks a lot for your help! Dumb me, should have remembered there were extra files besides the .mll that I also needed to take care of!
## Post #70
- Username: WarlordShadow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 01, 2015 4:14 am
- Post datetime: 2015-02-01T12:15:10+00:00
- Post Title: Re: League of legends model problems....

Hello!

I'm new to this forum but it has been a week of extreme struggle to export Braum's shield model into any reasonable file format. 
Here are the steps I was following:
1. Export Braum's .skn file using Wooxy or Skin Installer Ultimate (I recommend the former).
2. Open it in Maya 2015 using provided Riot skil translator.
3. Delete Braum or separate the shield in any other way.
4. Export it to .obj, .dxf or .dwg.

And now I'm hitting the wall trying to open it with CorelDraw!!! The damn thing crashes (freezes) Corel every time I try to import it, either in .dxf or .dwg both of which are AutoCAD file extensions. 

Any ideas why is it happening or how to convert it to a .cdr file?

The main goal is to obtain the file with .cdr extension so that it can be used as a template for a polistyrene-cutting machine.
## Post #71
- Username: baeckerskins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 30, 2015 5:54 am
- Post datetime: 2015-08-01T11:36:52+00:00
- Post Title: Re: League of legends model problems....

By the way, is there any way to fix the issue with champions with more complicated animations? Basically theres champions with seperate animations for the torso so that the model can move his arms freely while the legs keep running smoothly. One of these champions would be draven, or hecarim- You can check the animations here [http://www.lolking.net/models?champion=120&skin=0](http://www.lolking.net/models?champion=120&skin=0)

The problem is, if you try to export models with the most recent file translator for maya 2015, the animations are really buggy. Is this fixable? I would appreciate help
## Post #72
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-01T15:29:57+00:00
- Post Title: Re: League of legends model problems....

[out]
## Post #73
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2015-08-11T18:34:25+00:00
- Post Title: Re: League of legends model problems....

> Reply from baeckerskins
>
> By the way, is there any way to fix the issue with champions with more complicated animations? Basically theres champions with seperate animations for the torso so that the model can move his arms freely while the legs keep running smoothly. One of these champions would be draven, or hecarim- You can check the animations here http://www.lolking.net/models?champion=120&skin=0

The problem is, if you try to export models with the most recent file translator for maya 2015, the animations are really buggy. Is this fixable? I would appreciate help

Please, specify in more details ur problem. Or read what Wobble wrote.
## Post #74
- Username: cagil99
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 11, 2015 11:43 pm
- Post datetime: 2015-08-12T15:49:22+00:00
- Post Title: Re: League of legends model problems....

Hello, my problem is same as Risky's. [https://gyazo.com/67bb9f15761f9fb34a82c2733179aa33](https://gyazo.com/67bb9f15761f9fb34a82c2733179aa33) I have this error when I want to import. I am using krolik's plugin. I dont know where to find thespawn's plugin or those "extra files" . I use Maya 2015 btw. Thanks
## Post #75
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2015-08-12T20:07:51+00:00
- Post Title: Re: League of legends model problems....

> Reply from cagil99
>
> Hello, my problem is same as Risky's. https://gyazo.com/67bb9f15761f9fb34a82c2733179aa33 I have this error when I want to import. I am using krolik's plugin. I dont know where to find thespawn's plugin or those "extra files" . I use Maya 2015 btw. Thanks

Catch it! Archive with scripts and icons that were missed. Plugin, I assume,  you already have.
[RiotFileTranslator.7z](https://xentaxbackup.github.io/file/9522_RiotFileTranslator.7z)
## Post #76
- Username: cagil99
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 11, 2015 11:43 pm
- Post datetime: 2015-08-13T12:18:22+00:00
- Post Title: Re: League of legends model problems....

I have one more problem that I couldnt figure out. I use blender so I imported for example katarina to maya and then exported as fbx and dae (tried both ) then imported to blender worked on it exported to maya and then to league of legends but in game characters always look deformed. I can't figure out what causes this but I am sure something happens between maya and blender import export because when I imported to maya and then exported directly to league nothing bad happened. Can you help me out on this? I dont want to learn maya as I am used to blender for 2 years.

[https://gyazo.com/64774340e9435eeb62e61e13efb1d3e2](https://gyazo.com/64774340e9435eeb62e61e13efb1d3e2) Here is the bug
## Post #77
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2015-08-16T09:25:10+00:00
- Post Title: Re: League of legends model problems....

> Reply from cagil99
>
> I have one more problem that I couldnt figure out. I use blender so I imported for example katarina to maya and then exported as fbx and dae (tried both ) then imported to blender worked on it exported to maya and then to league of legends but in game characters always look deformed. I can't figure out what causes this but I am sure something happens between maya and blender import export because when I imported to maya and then exported directly to league nothing bad happened. Can you help me out on this? I dont want to learn maya as I am used to blender for 2 years.

https://gyazo.com/64774340e9435eeb62e61e13efb1d3e2 Here is the bug

Sry, I will not be able to help or advice you with this. Not familiar with Blender at all
## Post #78
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-09-08T00:22:34+00:00
- Post Title: Re: League of legends model problems....

Greetings everyone!

I'm kinda new to this forum and the first thing that I wanna say is that you guys make a lot of good work. I wanted to ask for 2 models from LoL, both which I couldn't get it from neither SIU+Maya's Riot File Translator nor woxxy. I'm looking for Braum's classic with shield and Tristana with Visual Upgrade Classic in .obj format. If anyone got these models would be kind enough to share with me?

A great thanks in advance!
## Post #79
- Username: krolik
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Apr 18, 2014 7:50 pm
- Post datetime: 2015-09-12T13:23:50+00:00
- Post Title: Re: League of legends model problems....

> Reply from VoliPanda
>
> Greetings everyone!

I'm kinda new to this forum and the first thing that I wanna say is that you guys make a lot of good work. I wanted to ask for 2 models from LoL, both which I couldn't get it from neither SIU+Maya's Riot File Translator nor woxxy. I'm looking for Braum's classic with shield and Tristana with Visual Upgrade Classic in .obj format. If anyone got these models would be kind enough to share with me?

A great thanks in advance!

There are lots of manuals in internet. Seems you are a lazy =)) I did it for you
[https://mega.nz/#!U0sDCKTS!kHn_KjNrXr03 ... jZeJyavSRE](https://mega.nz/#!U0sDCKTS!kHn_KjNrXr03HR5rqFVOlQ1PriFOQ_jwCjZeJyavSRE)
[https://mega.nz/#!0pMVWJwY!M1FcDQNTnOup ... GAofcjbqSY](https://mega.nz/#!0pMVWJwY!M1FcDQNTnOupte0pAky47tynbHcWiSvTaGAofcjbqSY)

PS: Please, create a new topic for such request. Don't use this one.
## Post #80
- Username: VoliPanda
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 07, 2015 4:49 am
- Post datetime: 2015-09-19T16:50:36+00:00
- Post Title: Re: League of legends model problems....

> Reply from krolik
>
> VoliPanda wrote:Greetings everyone!

I'm kinda new to this forum and the first thing that I wanna say is that you guys make a lot of good work. I wanted to ask for 2 models from LoL, both which I couldn't get it from neither SIU+Maya's Riot File Translator nor woxxy. I'm looking for Braum's classic with shield and Tristana with Visual Upgrade Classic in .obj format. If anyone got these models would be kind enough to share with me?

A great thanks in advance!

There are lots of manuals in internet. Seems you are a lazy =)) I did it for you
https://mega.nz/#!U0sDCKTS!kHn_KjNrXr03 ... jZeJyavSRE
https://mega.nz/#!0pMVWJwY!M1FcDQNTnOup ... GAofcjbqSY

PS: Please, create a new topic for such request. Don't use this one.

Thank you so much for the models!
I actually spent one entire month looking for those. And without any chances of getting, I kindly got Braum's with the help of one folk from here.
I use SIU, I have the Maya import + all of it updated. Even the skntoobj file. I have found their files in the folder. But when I tried opening it, Braum file kept me getting nothing and for Tristana's, her Old model. Could you please point me these manuals? Because I looked almost everywhere and didn't find the proper way to get the files "after Yasuo", as people are talking about.
## Post #81
- Username: baeckerskins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 30, 2015 5:54 am
- Post datetime: 2016-01-10T14:06:19+00:00
- Post Title: Re: League of legends model problems....

Oh man I hope this thread isn't too dead yet, but I still have the problem with the seperate animations. I can specify it this time, though:
This is what using a certain ability should look like: [https://gyazo.com/d3fc3d377333d50f47803630477b35eb](https://gyazo.com/d3fc3d377333d50f47803630477b35eb)
However, when I take that very same base model, still bound, and export it with the tool it looks like this: [https://gyazo.com/733127a36d75252a020fdd3e9759a9db](https://gyazo.com/733127a36d75252a020fdd3e9759a9db)

That happens with every champion that has a certain way of animation: If you look at the animations it is made that they are 2 seperate ones. One is just the champion in basically t-pose with only the axes moving and they are spinning, and the other one is just his idle. I presume the game somehow overlays them to make it look smother so that his hand moves without his entire body pose resetting.
I really hope theres a fix for this since it makes modding for some champions completely impossible, I would greatly appreciate it if anyone was able to figure it out!
## Post #82
- Username: cookiezeater
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 19, 2016 3:13 am
- Post datetime: 2016-03-18T20:53:55+00:00
- Post Title: Re: League of legends model problems....

I'm wondering is anyone is still working on maya plugin? Looks like it does not support anm v4 and skn files released after 4.11 patch.
You can check lol models viewer source code here - uploaded it to pastebin [http://pastebin.com/ZZMsYNJ3](http://pastebin.com/ZZMsYNJ3)
Its written in js. Looks like this viewer supports all model and animation types..
## Post #83
- Username: BakaSora
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 13, 2016 12:52 am
- Post datetime: 2016-05-17T01:42:00+00:00
- Post Title: Re: League of legends model problems....

hello , i am new to trying to mod lol skins ( have little exp in maya ) and i dont seem to be able to get the plug-in to work 
i always get error msgs like this when i try to load it: Error: file: Autodesk/Maya2015/scripts/others/pluginWin.mel line 777: Unable to dynamically load : Autodesk/Maya2015/bin/plug-ins/RiotFileTranslator.mll

any1 has a idea how i can fix this ?
