## Post #1
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-04-28T05:08:35+00:00
- Post Title: Frostbite .xml levels to UE4 .T3D?

Anyone think they could take a look at these two map formats?
The .t3d file is easy enough to understand, and is essentially "copy/paste data" for UE4. This information is stored in the clipboard when you hit copy, and modifying it allows you to paste in different information. 1uu (Unreal Unit) is equivalent to 1cm.

The .xml file is from Battlefront 2, and is slightly more complex. It also stores the locations/rotations/scales of different meshes and their model paths, but rotations seem to be stored in radians rather than degrees.

Everything is in human-readable ASCII - I'd make a converter myself and will probably attempt it later, but I've never really done this sort of thing before. If someone thinks they could figure it out, please give it a shot - it would be a very valuable resource to the machinima community if we could port these levels into UE4.
[Examples.7z](https://xentaxbackup.github.io/file/18051_Examples.7z)
## Post #2
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-29T16:02:01+00:00
- Post Title: Frostbite .xml levels to UE4 .T3D?

What game is the .t3d from?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-07T20:04:40+00:00
- Post Title: Frostbite .xml levels to UE4 .T3D?

> Reply from TrumpetPro ↑Tue Apr 28, 2020 1:08 pm at Tue Apr 28, 2020 1:08 pm
>
> If someone thinks they could figure it out, please give it a shotSeems you know about coordinates, rotation and so on, so what is your specific question?

Just a wild guess, I don't have/mod this game so
Area01 contains a list of 119 objects. They have reference guids which refer to the Blueprints (which have master/creator guids, whatever) in the lower part of the xml.
With "00000000-0000-0000-0000-000000000037" [Ebx] Objects/Architecture/_GalacticEmpire/Deathstar_Debris/DeathStar_Debris_L_02 is referenced.
From the transform vector 
```
                <Vec3>
                    <x>-1115.701</x>
                    <y>596.9235</y>
                    <z>-344.3748</z>
                </Vec3>

```
you know where to find the object on the map.

In a first step I'd try to replace an object in the t3d map by one in the Area01 map. So you need to know the format of the objects.

From my experience the main problem could be the mesh formats. Dunno, whether they are similar?
## Post #4
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-05-08T00:28:18+00:00
- Post Title: Frostbite .xml levels to UE4 .T3D?

> Reply from shakotay2 ↑Fri May 08, 2020 4:04 am at Fri May 08, 2020 4:04 am
>
> what is your specific question?

To put it simply, while I understand the differences between the two formats I don't know where to start with actually making a converter. To rephrase, would someone be willing to either create this tool or point me in the direction of some resources on learning how to do so?

> Reply from EPYCSPYDER ↑Thu Apr 30, 2020 12:02 am at Thu Apr 30, 2020 12:02 am
>
> 
What game is the .t3d from?

.T3D is a generic UE4 format with no specific game, I made it myself by pressing Ctrl+C in the editor.
