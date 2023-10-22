## Post #1
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-23T06:38:37+00:00
- Post Title: Please, help add animation to the blender2.49 script.

I have blender script (for blender version 2.49).
Script load fine bones and model. But not load anm(animation key data).
Please, help add support animation file (anm) to the script.

I put all files (blender script\model.s3d\modelbone.b3d\modelanim.anm)


 wrencher.rar
(194.4 KiB) Downloaded 27 times



In file *.anim 13 byte it is bones num.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-23T11:08:03+00:00
- Post Title: Please, help add animation to the blender2.49 script.

> Reply from Roman
>
> Please, help add support animation file (anm) to the script.Hi Roman,
from my experience noone will/can add animation support to (blender) python files.
Only the author of the script could. (Meanwhile you should know that, too.  )

My suggestion would be to try it with Noesis. But you'll need to follow my idea.
(I can't help, if you don't. And even if you do I can't promise anything, as always.)

As you've noticed correctly the bone's count is 27. That's a good starting point!  

Here you go:
You've bugged off the py extension from s3d_blenderscript2-49.py
So add it.

Start blender 2.49b, open text window, open the above mentioned py script,
hover mouse cursor over text window, press alt-p, load wrencher.s3d,
again alt-p, load wrencher.b3d

hover cursor over 3D view window, press 'a' (select all)
export to Autodesk fbx (increase Precision to 6 before exporting!)
--------------------------

start Noesis, drag fbx onto 3D view window
drag wrencher_uvmap.dds if required, press 'no' on notification window
press 'F4' to toggle face cull

tell me when you're done.

We could try to analyze the attack_lash_left.anm file then.



wrencher3D.jpg (52.83 KiB) Viewed 247 times



btw: I just noticed that Noesis adds some bones on export so be prepared to make a second run where you only export the b3d from blender. (For some strange reason blender 2.49b has two 'armatures' in its outliner when imorting s3d and b3d.)

nodes
  0 "model-1"  -1
  1 "model-0"  -1
  2 "foot_l_upper"  9
  3 "tail_upper"  22
  4 "foot_l_lower"  2
  5 "foot_r_upper"  17
  6 "fingers_l_upper"  15
  7 "thumb_r"  20
  8 "leg_r_upper"  22
  9 "leg_l_lower"  19
  10 "finger_r_lower"  25
  11 "arm_r_lower"  13
  12 "fingers_l_lower"  6
  13 "arm_r_upper"  28
  14 "thumb_l"  15
  15 "wrist_l"  16
  16 "arm_l_lower"  23
  17 "leg_r_lower"  8
  18 "foot_r_lower"  5
  19 "leg_l_upper"  22
  20 "wrist_r"  11
  21 "tail_lower"  3
  22 "hip"  29
  23 "arm_l_upper"  28
  24 "head"  28
  25 "finger_r_upper"  20
  26 "tail_tip"  21
  27 "jaw"  24
  28 "torso"  29
  29 "armature"  30
  30 "blend_root"  -1
end
## Post #3
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-23T14:36:17+00:00
- Post Title: Please, help add animation to the blender2.49 script.

I did what you told me.
What's next we do ?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-23T15:01:39+00:00
- Post Title: Please, help add animation to the blender2.49 script.

we must give attack_lash_left.anm a structure. Then search for transitions, rotations.

I don't have a clue whether we'll be successful but it's a small file only so if we fail we won't have lost too much time.  

What are your skills? Can you convert hex values such as 5E AF 34 3F to a float? (You could use hex2obj for it.)

Hopefully there are 27 blocks (one for each bone).

Then I plan to put the transitions, rotations into a fake .x file and drag it onto the skeleton in Noesis.

(This worked for Monster Hunter TRI (brres -> md5anim), didn't check it with .x so far.)
[viewtopic.php?f=16&t=12979&p=107315&hil ... an#p107315](http://forum.xentax.com/viewtopic.php?f=16&t=12979&p=107315&hilit=+indian#p107315)

btw: I don't have too much time for such - the more you can help the better.

search for 0000000000000000000000 gives 22 finds, 0E0000000000000000000000: 17, well it will not be simple, I guess

First block: 0x25 to 0x1E1, 37x12 bytes

2nd block: 0x1ED to 0x301, 23x12 bytes

That's something you cold check for the remaining blocks.
## Post #5
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-23T17:09:22+00:00
- Post Title: Please, help add animation to the blender2.49 script.

Aha   
Thanks.
3d max have text format animation keys *.xaf
And i simple try write values from attack_lash_left.anm to xaf and load text animation keys in 3d max.
This method help me understood *.anm data. Some like debug mode 
This is *.xaf data:

```
    <SceneInfo fileName="" startTick="0" endTick="3520" frameRate="30" ticksPerFrame="160" />
    <CustomData />
    <Node name="GOB" parentNode="Scene Root" parentNodeIndex="0" numChildren="3">
        <Samples count="22">
            <S t="0" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="160" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="320" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="480" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="640" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="800" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="960" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="1120" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="1280" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="1440" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="1600" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="1760" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="1920" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="2080" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="2240" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="2400" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="2560" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="2720" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="2880" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="3040" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="3200" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
            <S t="3360" v="1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000 1.000000 0.000000 0.000000 0.000000" />
        </Samples>
    </Node>

```
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-25T04:49:03+00:00
- Post Title: Please, help add animation to the blender2.49 script.

You're on a good way; as you may have noticed the frame blocks in the .anm file have different sizes.

(Using max script could solve this, iirc because max can interpolate missing time frames.)
Read here: [viewtopic.php?f=16&t=13759&p=114649&hil ... te#p114649](http://forum.xentax.com/viewtopic.php?f=16&t=13759&p=114649&hilit=+interpolate#p114649)

Another problem is that there's less frame blocks than bones, afaics.
## Post #7
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-25T09:27:22+00:00
- Post Title: Please, help add animation to the blender2.49 script.

In anm file i see 27 bones and 14
File size 5 441 bytes.

27*14*16 = 6 048 bytes.
if 27-1 = 26 and 14-1= 13
26*13*16 = 5 408 bytes. And 33 bytes file header

May be using quaternions for animation keys.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-25T21:12:40+00:00
- Post Title: Please, help add animation to the blender2.49 script.

> Reply from Roman
>
> In anm file i see 27 bones and 1414 frames? Agreed.
There's a count (27) at 0x0D but where do you see 27 bones (blocks)?

> 26*13*16 = 5 408 bytes.a brave calculation, but I fear, it doesn't represent the structure of that anim file.

what I found is this, 18 blocks starting at:
0x21, 0x1E9, 0x309, 0x429, 0x559, 0x679, 0x799, 0x8B9, 0x9E9,
0xB19, 0xC39, 0xD59, 0xE79, 0xF99, 0x10C9, 0x11E9, 0x1309, 0x1429

There's a frame time (in ms) of
0, 40, 80, 120, 160, 200, 240, ..., 480, 498(?) in most blocks

block size is
1st: 14x(4+28) +8 bytes
others: 14x(4+16)+8= 0x120

0x429..0x559: 14x(4+16)+16+8= 0x130

last: 14x(4+16)+8

Where the 4 bytes are  the frame time DWord. The 8 bytes are 0E 000000 00000000 in most cases.

Block size (except for the first block) is 0x120 or 0x130 (16 additional zero bytes)
## Post #9
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-26T04:01:26+00:00
- Post Title: Please, help add animation to the blender2.49 script.

I look at file 0x64 and see : 40, 0.70485, 0.70234, 0.09644 , 0.02439, -0.00486 , 1.12999, 0.14428
Then at file 0x96 next time 80

Question why using 7 floats numbers for one animation time step ?
If this matrix3x3 then must be 9 floats numbers.

Four floats for quaternion and three floats for position ?!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-26T07:55:07+00:00
- Post Title: Please, help add animation to the blender2.49 script.

> Reply from Roman
>
> Question why using 7 floats numbers for one animation time step ?
[...]
Four floats for quaternion and three floats for position ?!yep, I'd say so. Where it might be 3 floats for position and then 4 for quaternion.
no time to check it atm.

There should be functions in the web to check whether 4 floats build a quaternion.
There's also QuaternionToEuler(), if required, which transforms a quaternion into 3 Euler angles (for an aeroplane they are called yaw, pitch, roll. Keep in mind to use radians in some cases, not degrees.)
## Post #11
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-26T16:29:25+00:00
- Post Title: Please, help add animation to the blender2.49 script.

Very interesting.
In anm file from 0x1450 i see 0x50 then four floats like quaternion and next num 0x78 and four floats for quaternion
## Post #12
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-28T12:28:34+00:00
- Post Title: Please, help add animation to the blender2.49 script.

How load anm data.

```
    :   bone_id(0),
    loop_time(0),
    reference_count(1)
{
    successfullyLoaded = false;

    filesystem::FB_FILE *fp = filesystem::fb_fopen(file_name, "rb");
    if (fp == 0)
        return;

    char header[5] = { 0 };
    filesystem::fb_fread(header, sizeof(char), 5, fp);
    if ( (memcmp(header, "ANM11", 5) != 0) ) {
        filesystem::fb_fclose(fp);
        return;
    }

    // Bone id
    filesystem::fb_fread(&bone_id, sizeof(int), 1, fp);

    // Loop time in ms
    filesystem::fb_fread(&loop_time, sizeof(int), 1, fp);

    int bone_count = 0;
    filesystem::fb_fread(&bone_count, sizeof(int), 1, fp);

    // resize containers
    bone_rotations.resize(bone_count);
    bone_positions.resize(bone_count);

    // For every bone
    for (int i = 0; i < bone_count; ++i) {
        int key_count = 0;
        filesystem::fb_fread(&key_count, sizeof(int), 1, fp);

        int position_key_count = 0;
        filesystem::fb_fread(&position_key_count, sizeof(int), 1, fp);

        for (int j = 0; j < key_count; ++j) {
            int time;
            Rotation rotation;
            Vector position;

            filesystem::fb_fread(&time, sizeof(int), 1, fp);
            filesystem::fb_fread(&rotation, sizeof(float), 4, fp);

            bone_rotations[i].push_back( std::pair<int, Rotation>(time, rotation) );

            if (position_key_count > 0) {
                filesystem::fb_fread(&position, sizeof(float), 3, fp);
                bone_positions[i].push_back( std::pair<int, Vector>(time, position) );
            }
        }
    }                                    
}

```
## Post #13
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-31T01:40:41+00:00
- Post Title: Please, help add animation to the blender2.49 script.

I do maxscript 2014 load anm.
But animation not look right in 3d max.
How must look right animation [https://www.youtube.com/watch?v=1DPM0l9 ... e=youtu.be](https://www.youtube.com/watch?v=1DPM0l9aFg0&feature=youtu.be)
Help right transform bones.
In file max 3d mesh wrencher with bones and script(run script and simple select btn LoadANM and select file attack_lash_left.anm from [viewtopic.php?p=121880#p121880](http://forum.xentax.com/viewtopic.php?p=121880#p121880)).


 wrencher.rar
(56.97 KiB) Downloaded 21 times
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-31T06:34:01+00:00
- Post Title: Please, help add animation to the blender2.49 script.

Nice script for testing skeletons!  

Sadly I can't load your Max scene because I'm limited to Max 2009 now.
Could you show your bones hierarchy, please?

Mine is like this but doesn't seem to work with your script correctly:
0 "blend_root" -1
1 "hip" 0
2 "tail_upper" 1
3 "tail_lower" 2
4 "tail_tip" 3
5 "leg_r_upper" 1
6 "leg_r_lower" 5
7 "foot_r_upper" 6
8 "foot_r_lower" 7
9 "leg_l_upper" 1
10 "leg_l_lower" 9
11 "foot_l_upper" 10
12 "foot_l_lower" 11
13 "torso" 0
14 "arm_r_upper" 13
15 "arm_r_lower" 14
16 "wrist_r" 15
17 "thumb_r" 16
18 "finger_r_upper" 16
19 "finger_r_lower" 18
20 "arm_l_upper" 13
21 "arm_l_lower" 20
22 "wrist_l" 21
23 "fingers_l_upper" 22
24 "fingers_l_lower" 23
25 "thumb_l" 22
26 "head" 13
27 "jaw" 26

btw: you seem to read the data for 12 bones only. Why?

(Could you tell where you got this formulae from? g = (angleaxis (57.2957*w) [-x,-z,-y]) 
It's more than simply converting radians to degrees, isn't it?)
## Post #15
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-31T07:17:17+00:00
- Post Title: Please, help add animation to the blender2.49 script.

Yes.
(180/pi) = 57.29577


In Max 2009 my script work too.

My hierarchy:



dds.jpg (104.3 KiB) Viewed 130 times
## Post #16
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-31T08:06:02+00:00
- Post Title: Re: Please, help add animation to the blender2.49 script.

shakotay2
Special for you fbx file.
I check this fbx file in 3d max 2009.


 www.rar
(83.9 KiB) Downloaded 21 times
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-31T11:46:34+00:00
- Post Title: Re: Please, help add animation to the blender2.49 script.

thx - since we don't know how the attack sequence should look like it would be a good idea to test your script with a walk_anim, wouldn't it?

How did you chose the sequence of bones? In the wrencher.b3d it starts with hip and ends with fingers_l_lower, so totally different from that in your fbx file.
## Post #18
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-08-31T12:54:38+00:00
- Post Title: Re: Please, help add animation to the blender2.49 script.

We know it !
On video i show right animation
[https://www.youtube.com/watch?v=1DPM0l9 ... e=youtu.be](https://www.youtube.com/watch?v=1DPM0l9aFg0&feature=youtu.be)


I using blender script to load in blender wrencher.s3d and b3d.
Then i export fbx from blender. And load fbx(with bones) wrencher to 3d max
And i don't know what happens bones hierarchy in fbx
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-31T18:44:41+00:00
- Post Title: Re: Please, help add animation to the blender2.49 script.

> Reply from Roman
>
> We know it !
On video i show right animationwell, how was this created then?

> I using blender script to load in blender wrencher.s3d and b3d.The script from Mariusz in blender 2.49b, right?

> Then i export fbx from blender.Which blender fbx plugin did you use?

(The one from Campbell Barton for Blender 2.49, export_fbx.py, version 1.2 creates fbx files which crash Max 2009.)

For me it seems as if you used the Autodesk FBX converter to convert that fbx, did you?
## Post #20
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-09-01T12:03:35+00:00
- Post Title: Re: Please, help add animation to the blender2.49 script.

The blender script author #2011-04-19 Glogow Poland Mariusz Szkaradek

Nick Szkaradek123 is this Mariusz Szkaradek ?
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-09-02T14:47:22+00:00
- Post Title: Re: Please, help add animation to the blender2.49 script.

> Reply from Roman
>
> Nick Szkaradek123 is this Mariusz Szkaradek ?yeah
