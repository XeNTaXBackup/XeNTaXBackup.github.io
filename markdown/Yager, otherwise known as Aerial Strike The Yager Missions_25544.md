## Post #1
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-19T12:25:11+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

Has anyone ever had any success extracting anything from this apparently very obscure game? I can get some audio and almost all textures out, but they use their own file format and im really a newb at this stuff, I dont really know what im doing.

I'll attach some files from a single mission, which is legal under fair use for research and education, dont @ me mods haha.

Everything comes from a YRF file, which there is an unpacker floating around here already. They are just in a big list in the data folder, separated by mission(map).

Inside the file are YODS, which I think are the 3d models, YWMs which I think have all the contents of a game map? The textures come out as DDS which is more obscure but actually readable format, bunch of apps can read those.

[https://drive.google.com/file/d/1-imCzX ... sp=sharing](https://drive.google.com/file/d/1-imCzXnow69mu6ouk1PS5QJZ9GxcGZCl/view?usp=sharing)

Anyone thats got more neurons than me wanna have a crack?
[FileStructure.JPG](https://xentaxbackup.github.io/file/22385_FileStructure.JPG)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-19T15:08:01+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from urammar ↑Sun Jun 19, 2022 8:25 pm at Sun Jun 19, 2022 8:25 pm
>
> 
file are YODS
i made plugin for *.YOD

(perhaps I will add support for materials)
[fmt_yod.zip](https://xentaxbackup.github.io/file/22387_fmt_yod.zip)
## Post #3
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-19T15:37:27+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from Durik256 ↑Sun Jun 19, 2022 11:08 pm at Sun Jun 19, 2022 11:08 pm
>
> 

Woah....

Are you some manner of mythical beast? I thought maybe, at best, people might be looking at hex code or something and pointing me to tutorials.

In less than just a couple of hours you just have a noesis plugin ready to respond with?

Woah.

Amazing I cant thank you enough! This is incredible!

Hey look, just to push my luck, if you could do materials that would just be, I wouldn't know what to do with myself. I think its just basic textures, nothing fancy. Pretty old game.

But the only other thing im really gonna ask for is that the levels are heightmaps. Theres a shadowmap for the level, but no height information. Im guessing thats in the level file under map->Mission00_159 whatever .ylm

I just dont know where else it could be. It doesnt seem to be stored in the alpha channel of any of the map relevant textures either.

But even what you've done, thank you sir! I dont see how I could ever have got these open, and to just be handed it, im speechless
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-19T16:01:51+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from urammar ↑Sun Jun 19, 2022 11:37 pm at Sun Jun 19, 2022 11:37 pm
>
> 
materials
perhaps when unpacking, '.[***...]' is added to the file name.
so you have to look for a texture by name among the rest.

textures should be one directory up in the "texture" folder.
example:
path models >> "C:\Users\Admin\Desktop\Extract\yod"
path textures >> "C:\Users\Admin\Desktop\Extract\texture"



> Reply from urammar ↑Sun Jun 19, 2022 11:37 pm at Sun Jun 19, 2022 11:37 pm
>
> 
.ylm
I can't promise anything. I'll look 

update: fix materials

[fmt_yod_withMAT.py.zip](https://xentaxbackup.github.io/file/22389_fmt_yod_withMAT.py.zip)
## Post #5
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-19T16:26:26+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from Durik256 ↑Mon Jun 20, 2022 12:01 am at Mon Jun 20, 2022 12:01 am
>
> 
I can't promise anything. I'll look

Can I buy you a beer or something man?

Oh also, I dunno if this is a bug in your plugin or just how the game works (there might be scripts that place stuff? Dunno) but the models meshes all get placed at world origin so they just kinda collapse inward, stuff isnt being offset to their correct locations.

Eg the pilot of a ship is put in the middle of the ship, not in the cockpit, for instance, but some of these meshes have a ton of sub meshes. If I have to place them by hand thats... okay haha. But perhaps the offsets are in the file already?

I feel like such a jerk even bringing this up haha, its already far ahead of what I could possibly do on my own.
## Post #6
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-19T16:56:14+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

Just to demonstrate the problem im talking about, this is the main ship from the game, the Saggiatius, as in your last screenshot.

You can see the engines out to the far left and right on struts, the laser guns just under them. The cockpit is also quite forward.

I guess these are actually separate meshes, and they are all getting placed at world origin, without their offsets is my guess.

Again its MAYBE possible to restore these things manually, but they dont keep their rotation either. It would be a big job, but if it has to be that way then so be it. Still, if thats possible to fix and you are up to the challenge, that would be perfection!
[screenshot_pc_yager016.jpg](https://xentaxbackup.github.io/file/22390_screenshot_pc_yager016.jpg)
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-19T21:54:27+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from urammar ↑Mon Jun 20, 2022 12:26 am at Mon Jun 20, 2022 12:26 am
>
> 
Can I buy you a beer or something man?
of course 

> Reply from urammar ↑Mon Jun 20, 2022 12:26 am at Mon Jun 20, 2022 12:26 am
>
> 
Just to demonstrate the problem
I immediately understood what you were talking about.

so it is as you wrote: '(there might be scripts that place stuff?)'
i add support animation. (need parent)

sample inside script 'player-sagittarius-0.[52a13cc4fa019c94ea35eca1].ysc':

```
with player_mainframe
setpos 0.727441 0.702623 2.08256
setscale 1
setyod player-sagittarius-0_player_mainframe

```

do not load animation, comment out line 95 '#'
[fmt_yod_ANIM.zip](https://xentaxbackup.github.io/file/22394_fmt_yod_ANIM.zip)
## Post #8
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-20T10:00:45+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

Oh god we are so close to perfect exports, though this is already totally workable.

I've noticed a bunch of the objects have bad animations. Picking on player_repair_point_pro.[b67956168ecc1c2db07b63f2].yod the arms for instance are totally broken.

[https://youtu.be/AybuqMGE4hE?t=2271](https://youtu.be/AybuqMGE4hE?t=2271) Heres a timestamped youtube link to the use of one of these repair platforms.

I'm wondering if theres some kind of right handed/left handed coordinate shenanigans happening here. Perhaps some of the rotations need to be inverted? Negative rotations should actually be positive? Or offset by 90 degrees?

The sagittarius for instance, that very first animation the weapon pods should swing UNDER the ship, but they go over and through it, so im guessing its adding rotation where it should be subtracting.

Also some of the text on the ships is also inverted.

--------

Actually just looking further as I type this, looking at the Sagittarius the rocket launcher on the roof of the ship is actually on the wrong side of it, you can see that from the game screenshot, too.

I think thats exactly the problem, left handed -> right handed co-ordinate system. Actually just inverting that might fix a lot of the problems, the gun pods for instance, if on the other side of the ship and inverted, would rotate correctly.

Is that possible?
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-20T15:09:17+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from urammar ↑Mon Jun 20, 2022 6:00 pm at Mon Jun 20, 2022 6:00 pm
>
> 
Is that possible?

yesterday you were going to arrange everything manually, 
and today you don’t like animation anymore. how fast requests are growing.  

new .ysc parsing, add bone parents_ID, fix anim quat (rotations).

(I'm too lazy to redo. upload as is) 
[fmt_yod.zip](https://xentaxbackup.github.io/file/22400_fmt_yod.zip)
## Post #10
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-20T15:54:33+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from Durik256 ↑Mon Jun 20, 2022 11:09 pm at Mon Jun 20, 2022 11:09 pm
>
> 

yesterday you were going to arrange everything manually, 
and today you don’t like animation anymore. how fast requests are growing.

I knoowwww :'(
I said I feel like such an arse even asking, I do! I really do! Its just.. I know that once this thread ends thats it, it goes back to being a totally forgotten game that like 5 people know about and 2 care about.

I literally called up YAGER, the studio that made the game yager, the first game they released and named their studio after, asking if they are doing anything with it and if they might licence it, and they didnt know what I was talking about. About a month later they added the game to their website in their list of games they made.

Yager studios doesnt even know what yager is.

I REALLY DO FEEL BAD! But every single little patch you make just gets so close to killer features its like... imagine if he just patched that one little thing.

Like, really, I didnt even think animations were possible, I was fully gonna re-create everything by hand rotation. And then youre like oh but maybe I could do materials with correct UV's and everything, and its like, yeah if thats not much effort that would be amazing! And then youre like yeah I did that and also placed everything properly, but also animations! And its like you are SO CLOSE, maybe even so close if you could just change like a few variables to correct  a few rotations!

Im sorry, I know its asking so much I feel like a jerk. i promise I really am happy with even this! Its just nobody is coming to do the 2nd round so its you putting this effort in right now or nobody ever again!

Really, im so happy with what youve done its not right to push, if you wanna stop thats totally fine, you have already done way more than is expected of anyone, way more. WAY MORE.

> Reply from Durik256 ↑Mon Jun 20, 2022 11:09 pm at Mon Jun 20, 2022 11:09 pm
>
> 
new .ysc parsing, add bone parents_ID, fix anim quat (rotations).
I want to change the plugin completely. I will upload later.

You're an actual legend and im serious about that beer, do you have like a patreon or something?

Really, thank you so much for every second you have thrown into this. Every post you have made has blown me away one after the other, im not just saying that. Its probably one of the nicest things Ive ever seen anyone do.
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-22T20:08:32+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

terrain format *.yml

terrain separata on chunks 16x16 and maybe have info in rgb color. ?
but for some reason each chunk consists of 1156 bytes. not 1024.
if load chunks as rgba32 texture (17x17)



structure YML:

```
-file_size    INT 
-unk          INT 
-num_file     INT

for num_file:
	-header      4 BYTES (MAP [4D 41 50 20])
	-size        INT 
	-unk         INT have normals?
	-unk         INT have tx?
	-x_terrain   INT
	-y_terrain   INT 
	-x_chunk     INT (+1?)
	-y_chunk     INT (+1?)
	-uv_size     INT
	-height_map  INT
	
	-unk_info       ARRAY_BYTES[x_terrain*y_terrain] (4 tx? (x_terrain/2, y_terrain/2)(maybe index normals))
	-offset chunk   ARRAY_INT[x_terrain*y_terrain] (if -1 skip)
	-num_chunks     INT
	-chunk_data     ARRAY_BYTES[(x_chunk*y_chunk) *num_chunks] 
	
	normals block:
		-header    4 BYTES (NRML[4E 52 4D 4C])
		-size      INT
		-num_nrm   INT 
		
		for num_nrm:
			-norm       VEC3 (x-float, y-float, z-float)
			
         texture block:
		-header    4 BYTES (TEX [4D 41 50 20])
		-size      INT 
		-num_tx    INT	for num_tx:
		
		for num_tx    :
			name_tx    string (to the first zero)
```

[fmt_ylm.zip](https://xentaxbackup.github.io/file/22408_fmt_ylm.zip)
## Post #12
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-22T23:35:55+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from Durik256 ↑Thu Jun 23, 2022 4:08 am at Thu Jun 23, 2022 4:08 am
>
> 
terrain separata on chunks 16x16 and maybe have info in rgb color. ?

Yeah it 100% is. This is where I get to feel useful all of a sudden, haha!

Okay, so, from limited testing so far with this it looks like the height information is stored in the red channel.

I tessellated the planes and used the red values of the pixels for world height information, multiplied by a 3 vector, and got pretty reasonable results, im able to match locations from the game. Right now im picking on the tutorial island as theres quite a lot of footage of that and it saves me from loading up the game, I can just keep it on one of my other monitors.



I will note that heights of certain tiles seem inconsistent with the heights of other tiles, especially when compared with in game footage, but when I overlay just the red as the base colour so I can see both the distortion and the height information it seems like the heightmap is nice, smooth and correct.

You can see here very clearly the holes for the drones that pop up you're instructed to shoot in level 2.



The height problem, though, for instance the proteus base hangar is tiny compared to tutorial island when set to the same height values. Perhaps theres a multiplier stored per tile somewhere? Thats just me thinking out loud.

Also, the mesh is currently breaking its seams for some reason even though... there are actually no seams, this is a connected plane, so... Thats a bug to be fixed.

So, okay, the other channels I strongly suspect are colour masks for detail textures, although im still reverse engineering the exact method. I'm not 100% convinced because a lot of what im seeing looks straight up random. A good thought I had was I think they might be using them as UV offsets for the level texture found in the textures folder, which makes double sense because otherwise I have no idea how they are sampling that texture. 

It makes a lot of sense to me, and i'll write the changes to the shader for it later on in the afternoon and test that theory.

I'm quite sure its not a direct texture paint like I initially thought, where you interpolate between the colours and draw the appropriate texture, although im not ignoring the fact that each island only has a max of 3 textures it would seem from a glance. They are using the alpha of the textures as an extra mask also, its not being used for transparency, it contains some kind of masking data they are making use of.

I'll attach some screenshots of my at a glance research and i'll update as I play with this more.
[yager1.JPG](https://xentaxbackup.github.io/file/22411_yager1.JPG)
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-23T08:05:41+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

last unk its height.
shadow_tx as texture..

[fmt_ylm.zip](https://xentaxbackup.github.io/file/22417_fmt_ylm.zip)
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-24T23:11:05+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

chunk contains 4BYTE(RGBA) info for 289 vertices (17x17)
R - height (R/6) + (255/6*mul)
G - uv_Y step 8 = (G*8)/2048  the value is a multiple of 8, the remainder is the height multiplier.
(sample '241': mul = (241 - (241//8*8) = 1), height = R/6 + (255/6*mul))
B - first half byte rotate_uv, second half byte uv_X = (B[1]*64)/1024 
rotate_uv:

    0 - default
    2 - flip_Y
    4 - flip_X
    6 - rot_180 ->
    8 - rot_90 ->
    10 - rot_90 <- and flip_Y
    12 - rot_90 -> and flip_Y
    14 - rot_90 <-
A - normal_id

plugin for test, if unpack all chunks as *.chunk
[fmt_ylm_chunk.zip](https://xentaxbackup.github.io/file/22427_fmt_ylm_chunk.zip)
## Post #15
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-27T22:41:56+00:00
- Post Title: Yager, otherwise known as Aerial Strike: The Yager Missions

finalize

game archive *.yrf, unpacker (click on arrow):

> Reply from Darkfox ↑Thu Jul 14, 2011 6:31 pm at Thu Jul 14, 2011 6:31 pm
>
> 
AerialStrike_Util_V1_00.rar

game 3d model *.yod, plugin for Noesis (click on arrow):

> Reply from Durik256 ↑Mon Jun 20, 2022 11:09 pm at Mon Jun 20, 2022 11:09 pm
>
> 
fmt_yod.py

game terrain *.yml plugin for Noesis:
(very slow work, one terrain contains ~800 000 vertices and ~400 000 tris)

[fmt_ylm.zip](https://xentaxbackup.github.io/file/22428_fmt_ylm.zip)
## Post #16
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-06-29T21:24:50+00:00
- Post Title: Re: Yager, otherwise known as Aerial Strike: The Yager Missions

> Reply from Durik256 ↑Tue Jun 28, 2022 6:41 am at Tue Jun 28, 2022 6:41 am
>
> 
finalize
fmt_yod.py

And the award for absolute most legendary user on these forums goes to..

Both a well deserved well done and a thank you from me. Both the effort and straight up speed that went into this was an actual marvel to behold. I dunno what you do for your day job but I hope you get paid really well for it, because youre far too smart to be worth anything less.

Thanks mate. You're an actual legend.
