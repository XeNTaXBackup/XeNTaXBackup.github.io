## Post #1
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-12-24T21:38:59+00:00
- Post Title: HAVOK *.hkx

Hi All!

I've searched the forum, checked most of result topics and still have a doubt whether this format was ever explored and/or any documentation was made available.

May be some of you have valuable links to any tools that can deal with these files and/or have some drafts of binary file format that I could start with?

Also, if someone knows or have any tool that can visualize the *.hkx file, this could make things much easier, as it's really hard to explore or finally create a modded file with no chance to visualize result.


Background: Ubisoft Disrupt engine is under a scalpel. Model format and materials are almost done, but physics model is the problem now.
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-24T22:20:51+00:00
- Post Title: HAVOK *.hkx

Volfin and I are working on hkx for alien isolation. I have most the data structures dumped from 2013
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-24T23:43:57+00:00
- Post Title: HAVOK *.hkx

Just get the free sdk or havok tool. Its pretty easy
## Post #4
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-25T00:29:41+00:00
- Post Title: HAVOK *.hkx

I'm working on a tool to convert HKX to SMD to enable transfer of skeletons and eventually animations. But it still needs a lot of work. As Cra0 mentioned we are using it primarily for Alien: Isolation (skeleton only) at this time, but eventually i want to clean it up and make it more generic. It's just a matter of having the time to refine it. Also need to find more examples of various files created with various SDK versions.
## Post #5
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-12-25T05:53:44+00:00
- Post Title: HAVOK *.hkx

> Reply from volfin
>
> Also need to find more examples of various files created with various SDK versions.
Well you can easily get files from Skyrim, Sleeping Dogs, Alien Isolation, and Sleeping Dogs DE. That's Havok 2010, 2011, 2012, and 2013 right there.

And plus there's already an open-source extractor for 2010.
## Post #6
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-12-25T11:08:49+00:00
- Post Title: HAVOK *.hkx

I've skim through some of hkx files related to vehicle physics and these seems to contain quite a lot of info. For example, the general collision volumes (visually looks like vertices and faces/connectivity_links indices) for all vehicle objects end up on about 20Kb of data and the overal hkx file is about 180-200Kb. Looking at class list I can't say clearly which data requires that much of info followed by collision volumes.

hkClass
hkClassMember
hkClassEnum
hkClassEnumItem
nomadVehiclePhysResourceData
hkpRigidBody
kpListShape
hkpConvexVerticesShape
hkpConvexVerticesConnectivity
hkpCylinderShape
hkpConvexTransformShape
hkpBoxShape
hkpConvexTranslateShape
hkpConstraintInstance
hkpLimitedHingeConstraintData
hkpPositionConstraintMotor
hkpStaticCompoundShape
hkpBvCompressedMeshShape

I can say that geometry file (xbg) contains pre-defined vertices deformation data, so barely the hkx file will have the deformation. However, it can contain mapping of physical volume to geometry vertices, so hit/damage on collision vertex would cause visual geometry vertices to increase level of deformation. Additionally, geometry vertices utilize some ID assignment in a mesh that is used by game for emissive mesh lights (headlights, taillights) and these are bounded to some physics in hkx too (probably just a bit of info needed to save I guess).

Looking at the rest of the data, it doesn't make any sense to me at the moment as it's very irregular. Probably, this is a "BvCompressedMeshShape".

Unfortunately, it doesn't seem to be possible to create .hkx file for the game separately from the affecting geometry data, so external tools could barely be used. So, the free sdk with havok tool is not a solution. I still wonder whether some visualization or dumping tools avail? Can original havok tool visualize the hkx file?

As my tool is a payware solution, I can't ask for any others work, but if someone can share initial info for inspiration, it would be very helpful. 

P.S. the skeleton seems to be out of hkx file, as each model is equipped with "reference skeleton" file (XML converted to binary) and the file looks to be included for reference only, as damaging the file or zeroing-out it and putting into a mod does not cause any changes in game.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-25T13:10:57+00:00
- Post Title: HAVOK *.hkx

> Reply from Oleg
>
> Can original havok tool visualize the hkx file?which hkx file do you mean?

Generally the havok standalone tool can visualize hkx files. (But I didn't check it with "hkx files related to vehicle physics")
It also allows saving as XML:



HavokToolsFramework-Standalone.JPG (15.1 KiB) Viewed 379 times



As I wrote here (post as of Thu Dec 05, 2013 1:11 pm): [viewtopic.php?f=16&t=10730&hilit=hkx&start=105](http://forum.xentax.com/viewtopic.php?f=16&t=10730&hilit=hkx&start=105)

> You load the mesh, add the skeleton and the animation
It was GirlMesh.hkx, GirlSkeleton.hkx, girlrunningAnim.hkx
I found the hkx files here at the end of Civfreak's post:
[http://forums.elementalgame.com/398524](http://forums.elementalgame.com/398524)
## Post #8
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-26T00:12:08+00:00
- Post Title: HAVOK *.hkx

> Reply from SergeantJoe
>
> volfin wrote:Also need to find more examples of various files created with various SDK versions.
Well you can easily get files from Skyrim, Sleeping Dogs, Alien Isolation, and Sleeping Dogs DE. That's Havok 2010, 2011, 2012, and 2013 right there.

And plus there's already an open-source extractor for 2010.

Yeah i have a few. as for Hkxcmd, it only converts between HKX and XML, which isn't that handy. being able to convert from HKX diretcly to SMD/BVH or other directly importable format is better.
## Post #9
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-12-26T08:25:40+00:00
- Post Title: HAVOK *.hkx

> Reply from volfin
>
> being able to convert from HKX diretcly to SMD/BVH or other directly importable format is better.
If you convert it to xml you can open it in the Havok standalone tool, which can then convert into a useable format I believe. I think Shako made a post on that.

But you're right, it's better to convert it directly to SMD.
## Post #10
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-26T23:25:52+00:00
- Post Title: HAVOK *.hkx

> Reply from SergeantJoe
>
> volfin wrote:being able to convert from HKX diretcly to SMD/BVH or other directly importable format is better.
If you convert it to xml you can open it in the Havok standalone tool, which can then convert into a useable format I believe. I think Shako made a post on that.

I'd be intersted in more info about that. But all my experience with the havok creation tools is they are made to convert things to HKX, not the other way around. If by standalone tool you mean the Filter Manager, i've never got it to work on any file i've tried. always exits with no explaination.
## Post #11
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2014-12-27T17:16:45+00:00
- Post Title: HAVOK *.hkx

there is a utility AssetCc2 (hkSDK_Root\Tools\BatchProcess\AssetCc). It can convert any erialized .HKX file to xml .hkx
## Post #12
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2014-12-27T17:54:17+00:00
- Post Title: HAVOK *.hkx

> Reply from Skykila
>
> there is a utility AssetCc2 (hkSDK_Root\Tools\BatchProcess\AssetCc). It can convert any erialized .HKX file to xml .hkx

this seems to fail on .hkx files I have. but it can convert tagged xml file into native xml version and native xml into binary file. at least I have something to start from by comparing xml and associated binary file.
