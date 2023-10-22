## Post #1
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-01-16T21:48:00+00:00
- Post Title: Jet Set Radio HD Level Model File

Hello everyone! I'm the developer behind a fan made Jet Set Radio Future game, JSRFMP. ([https://gamejolt.com/games/JSRFMP/336004](https://gamejolt.com/games/JSRFMP/336004))

JSRF is the sequel to Jet Set Radio, but I've gotten a lot of requests to add maps from the original game. I thought it would be a cool idea, so I tried to rip them using Ninja Ripper/3D Ripper DX and no luck, because the models come out flat. (due to the way the dreamcast renders things I guess, since this was originally a dreamcast game)
and there aren't any tools out there to rip models from this game. The only thing that can be ripped is textures at the moment.

Despite not having any prior experience in reverse engineering model formats, I took a crack at getting them out of the files myself using 3D Model Researcher. ([http://mr.game-viewer.org/](http://mr.game-viewer.org/))

I made some decent progress (at least in my eyes) and managed to successfully locate the vertices in the file.


You can clearly see the map in these verts if you look close enough.



Using these settings will get you the vertices: 


So I got the verts, but i'm stumped on the faces. I can't seem to get them. 


After doing research, i've read that faces should be easy to find. I read that they should appear as hex values like "0000 0100 0200..." so I did a search in the file and found those values come up a few times, but when I tried them I never got anything but a garbled mess like the image above. But while looking, I noticed some oddities in the file, maybe suggesting it could be a container with several models inside. Since I found multiple blocks of vertices creating different road models and a duplicate of the map itself for some reason. It seems that the words "BxNU" appear before the verts in those other models. Not sure if that's a coincidence or what. But if this is a model container, then how come the map itself is in one big block of verts? But I don't have much experience with this kinda stuff, so i'm hoping someone here can help me out.

Here's the file if you wanna give it a shot.
[https://mega.nz/#!R2Q1CSaS!Z_AJJb_wLLZI ... XuLu50YGRE](https://mega.nz/#!R2Q1CSaS!Z_AJJb_wLLZInZzuExmoVEVA4Qky8eGrqXuLu50YGRE)

I can also send other level model files if that helps.
## Post #2
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-08T18:33:55+00:00
- Post Title: Jet Set Radio HD Level Model File

So here's an update on my progress so far.

The verts I found before I think might of been for the maps collision mesh, and not the map itself. Attempting to connect those verts in Blender revealed a lot of it was missing, but it matched up with the games collision detection. For example, take a look at this.

You can see there's a bit of a curb there, but not on the ripped verts.

So that's when I started suspecting that this was the collision mesh. Because if I move the character over that curb, he can clip right through it since the collision mesh doesn't have the curb on it.


So, that explains why I found two duplicates of the maps verts in this file. Not sure why I didn't think of it being the collision mesh originally. But anyway, the other map verts seem to have even less verts, which doesn't make much sense to me. So for now i'm stumped. Here's the settings to get the other verts.

start offset - 0x21e018
count - 13607
end - 0x245dec
format: xyz

I'm not too good with this stuff, so I hope someone who actually knows what there doing can help.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-09T14:17:21+00:00
- Post Title: Jet Set Radio HD Level Model File

> Reply from screenracer ↑Mon Mar 09, 2020 2:33 am at Mon Mar 09, 2020 2:33 am
>
> 
Here's the settings to get the other verts.

start offset - 0x21e018
count - 13607
end - 0x245dec
format: xyzThe FVFsize is 36 here so the count reduces to 4535 and it looks like a map as you stated:
.



st1dat-bin.png (100.31 KiB) Viewed 442 times



Many face indices (for the maps?), yes. Relative, not absolute values, I assume. So you need to get an idea how to build myriads of submeshes
or maybe whether the indices are combined/sorted somehow (different faces for mesh and uv?). Just wild guesses, though.

f ...
f 3 1 7 
f 3 4 2 
f 6 1 5 
f 7 8 5 
f 8 6 4 
f 8 7 4 
f 3 2 3 
f 1 7 3 
f 4 2 6 
f 1 5 7 
f 8 5 8 
f 6 4 8 
f 7 4 3 
f 2 3 1 
f 7 3 4 
f 2 6 1 
f 5 7 8 
f 5 8 6 
f 4 8 7 
f 4 3 2 
f 3 1 7 
f 3 4 2 
f 6 1 5 
f 7 8 5 
f 8 6 4 
f 8 7 4 
f 3 2 3 
f 1 7 3 
f 4 2 6 
f 1 5 7 
f 8 5 8 
f 6 4 8 
f 7 4 3 
f 2 3 1 

btw: you didn't tell which face indices you used for the collision mesh. That might help somehow.

edit: found it - see lower part of pic (uncomplete)
Maybe collision shape is built from two submeshes here? (FIcount=282 gives some superfluous faces.)
## Post #4
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-09T20:00:31+00:00
- Post Title: Jet Set Radio HD Level Model File

I didn't say which values I used for the faces because I didn't think it'd be too useful since I only got it to come out as a garbled mess. I suppose anything is better than nothing, so apologies for that. I should probably just post all my notes on this that i've been making as I went on.

```
----------
max count - 250947
start offset - 0x1e9a60
count - 13725
end - 0x211dbc
format: xyz

vertices (true map verts? lots of junk data though. seems to be a small 0 byte break in the file after every 2 verts)
----------
max count - 250947
start offset - 0x21e018
count - 13607
end - 0x245dec
format: xyz


more verts?
----------
start offset - 0x1c93c0
count - 930
end - 0x1cbf58
format: xyz

bxnu header? might be special stage models like JSRF had. (eg. fences in the JSRF garage)


faces (corrupted)
----------
start offset - 0x211db0
count - 24884
end - 0x21e018
```
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-09T20:29:52+00:00
- Post Title: Jet Set Radio HD Level Model File

sadly I don't have a clue how to get proper faces here:
.



st1dat-bin-faces.png (111.46 KiB) Viewed 430 times


Maybe skip the odd (or even) lines?
f 2 1 8
f 1 3 8
f 8 3 6
f 3 7 6
f 6 7 4
f 7 5 4
f 4 5 11
f 5 21 11
f 11 21 19
f 21 30 19
f 19 30 23
f 30 31 23
f 23 31 32
f 31 19 32
f 32 19 12
f 19 11 12
f 12 11 9
f 11 10 9
f 9 10 14
f 10 15 14
f 14 15 16
f 15 18 16
f 16 18 20
f 18 17 20
f 20 17 22
f 17 34 22
f 22 34 33
f 34 16 33
f 33 16 14
f 16 13 14
f 14 13 31
f 13 32 31
f 31 32 28
f 32 29 28
f 28 29 34
f 29 33 34
f 34 33 25
f 33 27 25
f 25 27 26
f 27 24 26
f 26 24 29
f 24 28 29
f 29 28 4
f 28 2 4
f 4 2 6
f 2 5 6
f 6 5 3
f 5 1 3
f 3 1 2
f 1 4 2
f 2 4 6
f 4 2 6
f 6 2 5
f 2 6 5
f 5 6 1
f 6 3 1
f 1 3 4
f 3 9 4
f 4 9 1
f 9 6 1
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-09T20:45:35+00:00
- Post Title: Jet Set Radio HD Level Model File

This looks at least as if quads could help  
.



even_lines.png (54.3 KiB) Viewed 428 times
## Post #7
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-09T20:51:03+00:00
- Post Title: Jet Set Radio HD Level Model File

I wonder if strange formats like these are common amongst dreamcast/older 3d games.

Here's some other level files and a character model file.
[https://mega.nz/#!lmwkTK6Y!C7C45Sr3ZxFp ... a3qNrK1Di8](https://mega.nz/#!lmwkTK6Y!C7C45Sr3ZxFpvCB_Y9aIpqSPETDS8Yphfa3qNrK1Di8)

Hope it helps. I've tried other level model files, and the same addresses work if you account for the filesize differences. The character model file I haven't been able to get even verts out of, but I thought i'd post it anyway in case there's something in there that could help understand the general model format.

Also do you think the files could be compressed/encrypted in some way? If that were the case than we probably wouldn't of gotten anything though, right?
## Post #8
- Username: jackblack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri May 20, 2011 7:56 am
- Post datetime: 2020-03-10T04:50:01+00:00
- Post Title: Jet Set Radio HD Level Model File

It rips pretty good with 3dripper and 3ds max 2010 (newer versions of max distort models usually), but only what is in camera view.
[jetset.jpg](https://xentaxbackup.github.io/file/17668_jetset.jpg)
## Post #9
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-10T06:03:26+00:00
- Post Title: Jet Set Radio HD Level Model File

> Reply from jackblack ↑Tue Mar 10, 2020 12:50 pm at Tue Mar 10, 2020 12:50 pm
>
> 
It rips pretty good with 3dripper and 3ds max 2010 (newer versions of max distort models usually), but only what is in camera view.

I haven't got max unfortunately, and attempts with 3d ripper and blender ended up with severe distortions
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T07:45:05+00:00
- Post Title: Jet Set Radio HD Level Model File

> Reply from jackblack ↑Tue Mar 10, 2020 12:50 pm at Tue Mar 10, 2020 12:50 pm
>
> 
It rips pretty good with 3dripper and 3ds max 2010 (newer versions of max distort models usually), but only what is in camera view.Maybe you could upload some ripped meshes (as wavefront obj preferred)? But it had to match with the scene in st1dat.bin from this post for comparison. (Otherwise it wouldn't help too much, I guess.)
## Post #11
- Username: jackblack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri May 20, 2011 7:56 am
- Post datetime: 2020-03-10T08:32:53+00:00
- Post Title: Jet Set Radio HD Level Model File

> Reply from shakotay2 ↑Tue Mar 10, 2020 3:45 pm at Tue Mar 10, 2020 3:45 pm
>
> 
jackblack wrote: ↑Tue Mar 10, 2020 12:50 pm
It rips pretty good with 3dripper and 3ds max 2010 (newer versions of max distort models usually), but only what is in camera view.
Maybe you could upload some ripped meshes (as wavefront obj preferred)? But it had to match with the scene in st1dat.bin from this post for comparison. (Otherwise it wouldn't help too much, I guess.)
[https://mega.nz/#!mPBDyYpa!dRAnmaaDCcho ... UQRVWGistI](https://mega.nz/#!mPBDyYpa!dRAnmaaDCchofmrzRUu_S00rsFJoiSYEYUQRVWGistI)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T08:57:08+00:00
- Post Title: Jet Set Radio HD Level Model File

cool! Thanks!
(Interesting to see that face indices for vertices and uvs are identical in the rips. But not sure if it's the same in the .bin game files. )

@screenracer:

> Reply from screenracer ↑Tue Mar 10, 2020 2:03 pm at Tue Mar 10, 2020 2:03 pm
>
> and attempts with 3d ripper and blender ended up with severe distortionsMaybe you could upload rips (wavefront obj) from the scene with the bus anyways?

For st2dat.bin there's some structures but guess it would make more sense for you to get the ripping working:
.



st2dat-bin.png (181.3 KiB) Viewed 395 times
## Post #13
- Username: jackblack
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri May 20, 2011 7:56 am
- Post datetime: 2020-03-10T09:43:41+00:00
- Post Title: Jet Set Radio HD Level Model File

Here is whole distorted scene with bus stop
[https://mega.nz/#!2fI1FaqZ!qWoDWQF7i1_Y ... imgHbVlUZ8](https://mega.nz/#!2fI1FaqZ!qWoDWQF7i1_YXsMXLKCwVJ3S2J6955T9SimgHbVlUZ8)
## Post #14
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-10T10:14:17+00:00
- Post Title: Jet Set Radio HD Level Model File

> Reply from shakotay2 ↑Tue Mar 10, 2020 4:57 pm at Tue Mar 10, 2020 4:57 pm
>
> 
Maybe you could upload rips (wavefront obj) from the scene with the bus anyways?

Here's my rip. Really distorted, not really usable. Might be a decent reference though.
[https://mega.nz/#!t7pGXaKY!K7JTXqo1z4A2 ... heQRctoJcw](https://mega.nz/#!t7pGXaKY!K7JTXqo1z4A2htC4BB83zOMgQAqsAcZHkheQRctoJcw)

Seems like st1dat.bin is Shibuya-Cho level (place with the bus stops) and st2dat.bin is the Kogane-Cho level.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T12:34:03+00:00
- Post Title: Jet Set Radio HD Level Model File

well, not that bad as I thought  :
.



busstop.png (199.89 KiB) Viewed 381 times


What happens if you rotate the scene (by 90 degrees for example) and take another rip? Are the same objects distorted or others?
If 'others' then you could complete the scene combining the results of several rips. Just a wild guess, of course.
## Post #16
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-10T13:16:52+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from shakotay2 ↑Tue Mar 10, 2020 8:34 pm at Tue Mar 10, 2020 8:34 pm
>
> 
What happens if you rotate the scene (by 90 degrees for example) and take another rip? Are the same objects distorted or others?

The rips always export near the origin point at the same spots, so some repositioning is required.


After repositioning, I get something like this.


It seems the farther an object is from the camera the more distorted it gets, and the whole thing appears to be stretched at an odd angle and bent out of proportion. I'm not entirely sure if these rips could be usable, no matter how much I resize or rotate it I can't seem to get it to look right.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T14:07:40+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from screenracer ↑Tue Mar 10, 2020 9:16 pm at Tue Mar 10, 2020 9:16 pm
>
> It seems the farther an object is from the camera the more distorted it gets, and the whole thing appears to be stretched at an odd angle and bent out of proportion.Is this a "known issue" with the ripper tool you used? If not you could inform the author. Might be fixable by applying a suiting matrix multiplication or something like this. (The ripper rips directly from video RAM, doesn't it?)

btw: afair there's more than one 3D ripper available. Did you check a 2nd one?

> It seems the farther an objectSo you could move in the scene, take several rips at different places each and combine them. A tedious task, I know, but should work, shouldn't it? (Better than nothing...  )
## Post #18
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-10T14:11:04+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from shakotay2 ↑Tue Mar 10, 2020 10:07 pm at Tue Mar 10, 2020 10:07 pm
>
> 
Is this a "known issue" with the ripper tool you used?

Not really. It only does it with this game, due to the way the game renders stuff I guess. The same thing happens with other dreamcast games too. I also heard it happens with PS2 games as well, but I haven't tried. All rippers seem to turn out like this if not worse.

Here's how Ninja Ripper rips it...


Very strange rendering method... I can only wonder why they decided to do it this way.



> So you could move in the scene, take several rips at different places each and combine them.

That would work, but the models right up in front of the camera are still distorted, just not as bad as the farther ones.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T18:10:25+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Are the single objects (buses for example) part of the map(s) or in separate files? Can't seem to find them in the points clouds from the st1dat.bin file.
Checking separate files (if any) with objects could help to understand how the face indices are organized.
## Post #20
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-10T18:21:17+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from shakotay2 ↑Wed Mar 11, 2020 2:10 am at Wed Mar 11, 2020 2:10 am
>
> 
Are the single objects (buses for example) part of the map(s) or in separate files? Can't seem to find them in the points clouds from the st1dat.bin file.
Checking separate files (if any) with objects could help to understand how the face indices are organized.

I'm pretty sure they're in seperate files, but I could be wrong. The games files aren't too well organized, so here's a few other files of different objects. Not sure if they are the traffic models or not though.
[https://mega.nz/#!9z5hUbZR!Iwxffx8r2eGS ... V5MQcFMevg](https://mega.nz/#!9z5hUbZR!Iwxffx8r2eGSJhESoBkkUNkM2IFFb6fWZV5MQcFMevg)

I can probably guess what a lot of these might contain, but I may be wrong.

```
bikedat.bin - police bike
keikandat.bin - police officer character
patcardat.bin - police car
people1dat.bin - pedestrians and maybe traffic vehicles
```


I haven't been able to get anything out of anything but the map files. Not even vertices. Though I also don't really know what i'm doing and just go with the trial and error route lol
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T21:36:55+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

For the bikedat.bin I found the vertex blocks are marked by FF000000 patterns, so addr of even find (count start=0) +8 = start of vertex block,
addr of odd find= end of vertex block (seems to be the same for st1dat.bin).

This is the result for the bike (with a normals sphere in the midst):
.



bikedat-bin.png (15.06 KiB) Viewed 317 times


For the face indices: I give up, it's too weird...
## Post #22
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2020-03-10T22:02:24+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from shakotay2 ↑Wed Mar 11, 2020 5:36 am at Wed Mar 11, 2020 5:36 am
>
> 
This is the result for the bike (with a normals sphere in the midst):

So that's what that spherical thingy was that I kept getting when trying to rip character models...

> Reply from shakotay2 ↑Wed Mar 11, 2020 5:36 am at Wed Mar 11, 2020 5:36 am
>
> 
For the face indices: I give up, it's too weird...

Well thanks for the attempts, they got these files locked down like fort knox. I'm gonna keep coming back to it in bursts, Hopefully i'll uncover something one of these days.
## Post #23
- Username: JSS442
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 15, 2020 5:44 pm
- Post datetime: 2020-12-15T14:02:20+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

I spent sometime over the summer trying to crack the format as well. Here's what I found hope it helps.

If you load cheat engine's memory viewer and view the games memory at address 0x20801000 the entire bin file of whatever character you're playing  should be loaded into memory there and you can make live edits. 
I did most of my research on the file EREKIDAT.bin in the PLAYER.afs archive. So the follow info comes from his bin file. Maybe some of it will be applicable to the stage files.

The bin file separates the model into segments for each body part. Each segment has its own set verts, uv, and triangle indices. However the indices of model are the same for all segments. So indices 1 and 2 refer to the same vertices for all model segments. I do not know if all vertices are the same for all segments.

Also there's two models, maybe three models per character.  One for character, one for outline, and another for the shadow.

The indicies are packed right next to uv coords the format is as follows
[size in bytes,purpose]

before the indicator there is 2 bytes that determine how many groups there are. It also used to determine the facing direction of triangles
[2 bytes, IUV Group count]

[2,quad or tri indicator] if tri the next part has 3 groups if quad it has 4

Index UV Group
[2,vertex index][2,UV Cooardinate X][2,UV Cooardinate Y]



Here's an image to illustrate it



all of these offsets map 1:1 at 0x20801000 in game 

pink is a ARGB color overlay 
brown is a different type of indicator. I think it determines whether or not to render the tris or to use them as uvs of some sort. 
purple is the tri/quad indicator
green is IUV Group
orange is the number of tris/quads to render this one is funny it does not always add up to this number
yellow is like purple but its negative and the sign value determines whether or not the tris are front or back facing.

Vertex and Normal are right next to each other as well
[3 floats,XYZ position][3 floats,XYZ Normal]
## Post #24
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-11T20:40:20+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

So I was wandering around the forum to see if there were any posts about Jet Set Radio as someone recently asked if I could take a look at the file format.  Then I saw your screenshot of the mesh in hex and noticed right away that it's a variant of the .nj format.  I've been staring at the .nj format for Rent-A-Hero recently so I recognized it instantly.  The difference though is that it seems that the meshes and pointers are in reverse order compared to the .nj format so renaming it to an .nj and throwing it into Noesis doesn't work since the pointers for the vertices and indices are all off. I was able to reconstruct the first mesh manually for the EREKIDAT.bin file and load it up into Noesis.  It looked like fingers to me but the mesh was a bit off.  I'm planning to write a script (who knows when) to gather the mesh data and reconstruct the pointers to a usable .nj format unless it can get implemented into Noesis directly. 


Beat (Fingers).png (119.2 KiB) Viewed 247 times
## Post #25
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-12T22:38:59+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Worked on it a bit more to test out the structure.  Managed to go a bit further into the model and got his arm loaded up.  Looks like I'm on the right track.


Beat (Arm).png (65.64 KiB) Viewed 243 times
## Post #26
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-13T02:17:38+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

And there we have it.  Beat in .nj format.  I wonder if the .njm is packed in the bin file as well.



Beat.png (73.77 KiB) Viewed 241 times
## Post #27
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-15T08:07:25+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Player models were easy to extract as seen below.  I haven't worked enough with .nj files to get them textured but I figure that it shouldn't be that difficult to do.

I started taking a look at the map file but looks to be a bit more complicated.  The stage 1 data seems to be separate models that get loaded at 0,0,0 and further into the .bin is another "file" that sets the coordinates of each object.  One thing to note is that there seems to be a pointer offset of 0x8CB00000 for the all the 3D models (except for the player ones) so you'd either have to fill in 0x8CB00000 bytes before the file (which I don't recommend as it'll leave you a 2Gb+ file) or subtract that much from each pointer to make things work.  If you've worked with .nj files before then this will make a lot of sense.

[PLAYER.png](https://xentaxbackup.github.io/file/19719_PLAYER.png)
## Post #28
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-03-15T19:32:36+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Mon Mar 15, 2021 4:07 pm at Mon Mar 15, 2021 4:07 pm
>
> 
Player models were easy to extract as seen below.  I haven't worked enough with .nj files to get them textured but I figure that it shouldn't be that difficult to do.

Nice! The rig also looks the same as the future models, which I assumed it would be since they reuse animations between the games and I didn't think that would of been possible unless the rigs were identical. I hope you can manage to get them uv'd/textured, I know the JSR community would love to see these models finally cracked, even if it's just character models.
## Post #29
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-15T22:16:28+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

The UV's seem to be intact so that's a big time saver.  I just need to figure out how .nj files load textures then we should be in business.
## Post #30
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-15T23:42:58+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Well that was quicker than I thought.  I just need to do this for the rest of them and then I guess I can call it a day.
## Post #31
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-03-16T01:33:02+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Tue Mar 16, 2021 7:42 am at Tue Mar 16, 2021 7:42 am
>
> 
Well that was quicker than I thought.  I just need to do this for the rest of them and then I guess I can call it a day.

Huh, nice! Also I'm just curious, is there seperate head/hand models in the bin files? In JSRF they used seperate head/hand models for different facial expressions and hand poses, just curious if JSR did the same
## Post #32
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-16T02:31:43+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

I'll have to check if they use separate models for the head and hand. I would imagine so as there're separate pvr textures with the different expressions in the _txr.bin file and they most likely correspond to a separate mesh that gets swapped out.
## Post #33
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-16T20:02:09+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

So it looks like the .bin data has a few models stored in it.  For Beat there are 5 models: Normal, Glow, Normal with can, Glow with can and then a separate face model for different expressions.  I'm not sure why all the textures won't load (like the spray can) I must not be writing the NJTL section correctly.


[Beat (Models).png](https://xentaxbackup.github.io/file/19732_Beat (Models).png)
## Post #34
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-03-16T22:45:53+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Wed Mar 17, 2021 4:02 am at Wed Mar 17, 2021 4:02 am
>
> 
I'm not sure why all the textures won't load (like the spray can)

I'm pretty sure the spraycan is a separate texture, at least in JSRF it was.
Ya' think you'll be able to grab maps as well? Or is the format too messed up? I can send more level files if it would help.
## Post #35
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-16T23:27:50+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

I have the texture of the can but I'm not sure why Noesis didn't pick it up.  It might be scripting error on my part as I've been doing all this manually and the texture doesn't load on all the other player characters that I've done either.  I'll see what I can do about the maps but that might take some time since it's such a larger file.
## Post #36
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-22T20:13:57+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Started on the map models.  I was able to isolate each of the meshes but they're all centered at the origin instead of their correct locations.  I'll need to find where that data is stored and implement that somehow.
## Post #37
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-22T20:34:42+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Also, here's what I pulled out of bikedat.bin.  Not the cleanest of models but it's something.
## Post #38
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-03-23T23:05:12+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Tue Mar 23, 2021 4:13 am at Tue Mar 23, 2021 4:13 am
>
> 
Started on the map models.  I was able to isolate each of the meshes but they're all centered at the origin instead of their correct locations.

Hmm... I'd imagine getting the map textures to rip with that might be a little difficult too. The level textures are separated into several separate .TXB files as far as I could tell. (inside the .AFS files)

They're still just PVR's though.

Funny enough, the "_ALL" file does not actually contain ALL the textures. I don't get it, these files are wild lol.
## Post #39
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-24T06:30:35+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Yeah, they're just pvr's packed into a single file so I just made a simple Lua script that searched for the header and split them. We could then use PVM Editor to create a PVM out of it.  One thing to note though is that the header info for the file length is incorrect on some of the PVR's so I had to make a file length check in the script to fix the header if it didn't match in order to load those properly.
 


texpack_st1_all.png (47.77 KiB) Viewed 335 times
## Post #40
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2021-03-31T00:25:38+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Got hung up a bit on the map so I wanted to take a stab at the collision map model.  This was a lot more complex than I had hoped for but I managed to figure it out. Aside from the complete triangle strip sequence, there are other tables further into the file that describe the triangle strip length, pointers the start of the tri strip and pointers to the vertex group they belong to (which I used to add up the face count as they start over for each group).  I ended up writing a small Lua script for it but it's not fully automatic just yet as I don't know where in the file these table offsets are stored but it should work for each map as long as you spent the time finding the offsets for each table.

The resulting collision map model looks like this.
## Post #41
- Username: SHUTDOWNOfficial
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 30, 2021 9:42 am
- Post datetime: 2021-05-05T02:04:19+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Wed Mar 17, 2021 4:02 am at Wed Mar 17, 2021 4:02 am
>
> 
So it looks like the .bin data has a few models stored in it.  For Beat there are 5 models: Normal, Glow, Normal with can, Glow with can and then a separate face model for different expressions.  I'm not sure why all the textures won't load (like the spray can) I must not be writing the NJTL section correctly.
Is there any way you could upload these models and/or share the process needed to rip them? I've wanted to rip the JSR models for a long time but have no idea how.
## Post #42
- Username: jetoralive
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 19, 2021 6:54 am
- Post datetime: 2021-05-18T23:03:00+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

please if at all possible share the player character models or the process to extract, I'm also someone who's been looking for them for years. this is awesome work!
## Post #43
- Username: Kexana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 05, 2022 5:36 pm
- Post datetime: 2022-04-05T09:40:43+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Sorry if necro posting, Has there been any update on releasing the models, even only the meshes? I'm very excited and this seems very promising!
## Post #44
- Username: jetoralive
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 19, 2021 6:54 am
- Post datetime: 2022-05-28T07:54:35+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

any new updates for this?
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-05-30T06:40:03+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Sadly egregiousguy left nothing but pictures, afaics. So all his work doesn't help. It's rather unlikely that someone else will take up the tedious analysing, imho.

Latest valuable input came from JSS442, see here (click on up arrow):

> Reply from JSS442 ↑Tue Dec 15, 2020 10:02 pm at Tue Dec 15, 2020 10:02 pm
>
> 
Many thanks again for that!
## Post #46
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2022-06-02T01:25:26+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Totally forgot all about this thread as I'm rarely active on Xentax.

I'll write up a how-to once I get some spare time.  In the meantime, here's some info about the format.  

JSR uses a variant of the SEGA Ninja model format.  By variant, I mean that the structure is aligned in reverse with the binary file heavily reliant on pointer values to locate all the model parts.  Headers are stored at the end of the model data with the hierarchy of sibling/child models going from end to beginning.  Players are stored in player.afs and enemies in enemy.afs in complementing pairs of _dat.bin and _txr.bin. In order to get textures working, you'll have to create a NJTL chunk to reference the extracted pvr textures from _txr.bin. 

Stages are a bit more complicated and tougher to piece together as all the buildings are in separate pieces and a lot of the data relating to texture references and position/rotation info is stored separately in the 1st_read.bin file.  While I've already successfully extracted several maps, it's far too complicated for me to explain so I won't be covering that.

With that being said, once you understand the basic structure of the ninja format then everything else will make sense once I complete the write up.  If you're already familiar with the ninja model format then this should be a piece of cake.
## Post #47
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-06-02T09:18:39+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Thu Jun 02, 2022 9:25 am at Thu Jun 02, 2022 9:25 am
>
> 
Totally forgot all about this thread as I'm rarely active on Xentax.Thanks for your answer!
What about the Noesis script you used here:

> Reply from egregiousguy ↑Tue Mar 23, 2021 4:34 am at Tue Mar 23, 2021 4:34 am
>
> ?

btw: I just realized that Noesis loads .nj files ("NJCM" signature inside) from Grandia 2. Hah, great! And I'm 10 years too late, haha...

> Reply from MrAdults ↑Wed Mar 14, 2012 2:28 am at Wed Mar 14, 2012 2:28 am
>
> 
.............................................
Another 4 years earlier:



nj chunks.png (55.77 KiB) Viewed 154 times
## Post #48
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2022-06-02T16:41:40+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Right, Noesis supports .nj/.pvr files.  The issue is that JSR combines all the data into a single .bin file without any NJCM/NJTL/NMDM... header ID's, therefore as a part of the restructuring process, I had to add those header IDs (with the proper info) to be able to feed it into Noesis.
## Post #49
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-06-04T15:57:47+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Still fiddling around with face indices (while uvs and vertices are no problem).

For EREKIDAT.bin I got this:

#3
f 208 209 203 
#4
f 190 191 175 176 
#3
f 177 178 189 
# new group 5 at 1de
f 189 192 178 193 194 
#3
f 195 196 197 
#3
f 208 207 209 
#4
f 191 190 193 192 
#4
f 203 199 190 192 
# new group 6 at 25a
f 205 189 204 177 210 175 
#3
f 189 201 205 
#3
f 198 204 205 
#19
f 208 210 211 200 208 204 207 198 209 205 203 201 206 189 203 202 199 189 192 
#3
f 210 204 200 
#4
f 178 176 194 191 
# new group 5 at 34a
f 210 175 208 190 203 
#8
f 193 197 191 196 194 195 193 197

Not sure whether they really use those long polygons, #19 etc.
Also tried FI = 255 - FI at no avail.

edit: getting closer; tried an nj file:
.



nj_got_FIs.jpg (75.75 KiB) Viewed 127 times
## Post #50
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2022-06-06T18:11:36+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Here's how face indices work for ninja.  On my snippet from erekidat.bin, you can see I've highlighted a few flags.  I won't go into too much detail but the blue is material, yellow is tiny chunk (which contains info for the external texture number for that mesh), and green is strip chunk.  The thing to look out for in strip chunk is the first byte.  Here we have two types, 0x40 (64) and 0x41 (65).  0x40 uses triangles for the faces while 0x41 uses tri strips.

I've highlighted a few more things on the right side (as well as separated the groups).  The dark orange (2 bytes) is the number of groups and the light orange gives the number of indices in that group.  A negative number of groups means that the group is back faced.  As you can see, everything is sequential and really hard to follow until you split up the groups correctly, then it will all make sense.

Hope that helps.
[Screenshot 2022-06-06 104713.png](https://xentaxbackup.github.io/file/22327_Screenshot 2022-06-06 104713.png)
## Post #51
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-06-09T19:04:53+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

> Reply from egregiousguy ↑Tue Jun 07, 2022 2:11 am at Tue Jun 07, 2022 2:11 am
>
> [...]As you can see, everything is sequential and really hard to follow until you split up the groups correctly, then it will all make sense.

Hope that helps.Thank you very much!  (Yeah, I'm a hard follower.  )

First index of a 3 DWords group each: CF, D0, CA
BD, BE, AE, AF

So the resulting first 7 face indices are (+1 for wavefront obj indices)
#3
f 208 209 203
#4
f 190 191 175 176 

as in my previous post? Which I created using the infos from JSS442 (Dec 15, 2020):

> Reply from JSS442 ↑Tue Dec 15, 2020 10:02 pm at Tue Dec 15, 2020 10:02 pm
>
> 

My main problem still unsolved: 
the first vertex block of EREKIDAT.bin is like so:
# 1. offset 0x446, count (Word) 46 (46 vertices), FVFsize= 24
v  0.076473 -1.186337 0.590292 
v  -0.379762 -1.024303 0.715383 
v  -0.711994 -0.823996 0.767796 
v  -0.218620 -0.985356 0.698208 
v  -0.358527 -0.842449 0.923282 
v  -0.519337 -0.540833 1.019215 
v  -0.659721 -1.221985 1.069119 
[...]

so I'd need face indices in the range of 0..45  for the first sub mesh which I can't seem to find.

(Next sub meshes have 34, 14, 46, 24, 32, 14 vertices and so on.)

edit: well, I've 53 vertex blocks and 77 face index blocks??
Need to check this. 
----------------------------------

For the last bigger vertexblock, 69 vertices:



last_bigger_vertexblock.jpg (47.95 KiB) Viewed 101 times


I get these face indices; don't seem to fit, too.

EREKIDAT.BIN
#7, 0x1f10c
f 45 44 48 52 47 54 56 
# new group 5 at 1f138
f 49 45 46 44 43 
#7, 0x1f158
f 58 51 50 57 49 43 46 
#3, 0x1f184
f 54 53 51 
# new group 5 at 1f198
f 51 55 53 57 52 
#3, 0x1f1b8
f 51 55 57 
#3, 0x1f1cc
f 52 53 54 
#6, 0x1f1e0
f 58 50 47 49 48 45 
#3, 0x1f206
f 47 56 58 
#9, 0x1f21a
f 63 65 66 68 64 60 62 59 61 
# new group 5 at 1f252
f 65 68 67 60 59 
# new group 5 at 1f272
f 66 63 64 61 62

Strange thing is that there's many more to follow:

#7, 0x1f292
f 73 69 74 78 76 79 70 
# new group 18 at 1f2be
f 71 84 83 80 77 84 72 71 70 82 79 81 78 72 69 70 73 75 
#6, 0x1f32c
f 71 82 83 81 77 72 
#3, 0x1f352
f 34 85 33 
#4, 0x1f366
f 31 41 87 33 
#4, 0x1f380
f 86 85 32 34 
#4, 0x1f39a
f 57 52 43 44 
#4, 0x1f3b4
f 70 75 76 74 
# new group 6 at 1f3ce
f 92 93 91 89 90 88 
# new group 6 at 1f3f4
f 98 99 97 95 96 94 
#3, 0x1f41a
f 98 96 97 
#3, 0x1f42e
f 92 90 91 
#12, 0x1f442
f 89 95 93 94 92 96 90 98 88 99 89 95 
# new group 6 at 1f48c
f 104 105 103 101 102 100 
# new group 6 at 1f4b2
f 110 111 109 107 108 106 
#3, 0x1f4d8
f 110 108 109 
#3, 0x1f4ec
f 104 102 103 
#12, 0x1f500
f 101 107 105 106 104 108 102 110 100 111 101 107
## Post #52
- Username: SNRB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 18, 2020 12:56 am
- Post datetime: 2022-08-25T13:57:41+00:00
- Post Title: Re: Jet Set Radio HD Level Model File

Any news on the complete character ripping tutorial (or release of the models)?

Please, this is literally the only topic in the whole internet where someone managed to rip JSR models
