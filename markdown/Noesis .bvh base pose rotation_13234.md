## Post #1
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-08-22T14:10:15+00:00
- Post Title: Noesis .bvh base pose rotation

As the title implies, I'm looking for a way to rotate a bvh AND its base pose in Noesis(Because of stupid Blender's inverted axis). The rotate 90 feature affects the animations only
This is the file I want to fix: [http://sta.sh/01hcj35lowhd](http://sta.sh/01hcj35lowhd) It doesn't matter whether the motion gets rotated too(if there's a way to actually do this)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-22T16:47:24+00:00
- Post Title: Noesis .bvh base pose rotation

nice one  !

> Reply from MarieRose1301
>
> The rotate 90 feature affects the animations onlysince the skeleton is in the mesh file, I guess.
If so it could be helpful if you uploaded it, too.
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-08-22T17:45:33+00:00
- Post Title: Noesis .bvh base pose rotation

It's actually the opposite of that, Noesis is ignoring the bones created by the BVH importer since they have no associated mesh and it's only applying transforms to the animations. It's just an oversight brought about by there being too many ways for pose data to come along with an animation.

I have no idea when I could get to doing a Noesis build to address that, but you can probably work around it by exporting with some geometry data to another format (like FBX) and then back to BVH, or write a script to do it, or just use some other software to transform the skeleton.
## Post #4
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-08-22T18:33:12+00:00
- Post Title: Noesis .bvh base pose rotation

> Reply from shakotay2
>
> nice one  !
MarieRose1301 wrote:The rotate 90 feature affects the animations onlysince the skeleton is in the mesh file, I guess.
If so it could be helpful if you uploaded it, too.

Here it is [http://sta.sh/05p2y9tu608](http://sta.sh/05p2y9tu608)
## Post #5
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-08-22T18:34:15+00:00
- Post Title: Noesis .bvh base pose rotation

> Reply from MrAdults
>
> It's actually the opposite of that, Noesis is ignoring the bones created by the BVH importer since they have no associated mesh and it's only applying transforms to the animations. It's just an oversight brought about by there being too many ways for pose data to come along with an animation.

I have no idea when I could get to doing a Noesis build to address that, but you can probably work around it by exporting with some geometry data to another format (like FBX) and then back to BVH, or write a script to do it, or just use some other software to transform the skeleton.

So basically I should export the motion in .fbx from blender with a mesh, export it as fbx with 90 rotation and then export as bvh?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-22T19:36:40+00:00
- Post Title: Noesis .bvh base pose rotation

Noesis complains about a "Bone count mismatch".

There are indeed Bip01_L_Toe01, Bip01_R_Toe01 for example in your fbx mesh
that I can't find in the bvh anim file.

Sure you uploaded they suiting fbx mesh file?

> So basically I should export the motion in .fbx from blenderI wouldn't rely too much on blender concerning anims.
Noesis seems to be the better tool here, imho (tried dae and md5anim export).
## Post #7
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-08-22T19:49:52+00:00
- Post Title: Noesis .bvh base pose rotation

> Reply from shakotay2
>
> Noesis complains about a "Bone count mismatch".

There are indeed Bip01_L_Toe01, Bip01_R_Toe01 for example in your fbx mesh
that I can't find in the bvh anim file.

Sure you uploaded they suiting fbx mesh file?
So basically I should export the motion in .fbx from blenderI wouldn't rely too much on blender concerning anims.
Noesis seems to be the better tool here, imho (tried dae and md5anim export).

I'm working on getting the correct fbx, I'm sorry
I have no alternatives because the animation was converted using blender, there are no means of getting it without blender

EDIT

Here it is, it's with another animation [http://sta.sh/01htsdkw09qv](http://sta.sh/01htsdkw09qv)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-23T14:39:28+00:00
- Post Title: Noesis .bvh base pose rotation

well, it's better (concerning the rotation) - but still reminds me of Ripley7:



ripley7.JPG (67.36 KiB) Viewed 160 times



(If you display the skeleton (F6) you'll see that it's moving correctly.)
## Post #9
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-08-23T18:35:22+00:00
- Post Title: Noesis .bvh base pose rotation

> Reply from shakotay2
>
> well, it's better (concerning the rotation) - but still reminds me of Ripley7:
ripley7.JPG

(If you display the skeleton (F6) you'll see that it's moving correctly.)

Looks like a model when you import it in brres file lol
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-25T20:19:45+00:00
- Post Title: Noesis .bvh base pose rotation

oh well, I've overviewed that your animation fbx file containes the mesh already.
Everything is working fine:



meshplusanim.JPG (24.27 KiB) Viewed 141 times



(I previously dragged this anim onto the mesh you uploaded.
That's the reason for the ugly result in my last post.)


But the really great thing with Noesis is that you can export from that fbx to smd with 
an additional .bvh animation output.

Then you can load the smd (mesh) and drag the .bvh animation onto it.
