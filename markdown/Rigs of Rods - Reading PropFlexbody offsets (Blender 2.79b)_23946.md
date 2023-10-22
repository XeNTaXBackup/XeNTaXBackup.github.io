## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-05-25T21:53:57+00:00
- Post Title: Rigs of Rods - Reading Prop/Flexbody offsets? (Blender 2.79b)

I am trying to convert vehicle models from Rigs of Rods.
I do get the meshes/textures converted successfully, with OgreXMLConverter (comes packaged with the game) and [RoROgreAddons.](https://github.com/CuriousMike56/RoROgreAddons)
But the problem is that the meshes imported do not get their positions imported.
The .truck file (that comes with the vehicle,) contains properties and mesh offsets.
I've tried to read these mesh offsets with no avail.
To read these offsets, the truck file uses their Nodes/Beams to calculate where it should go.
I have found a addon for Blender that imports the N/B structure, and there is a way to see where the nodes are numbered. (check discussion  )
[https://forum.rigsofrods.org/resources/ ... plugin.25/](https://forum.rigsofrods.org/resources/blender-n-b-import-export-plugin.25/)
There is also the [source code](https://github.com/RigsOfRods/rigs-of-rods) for the game. It contains how it is calculated (Forgot where the code for it went so find it yourself, sorry!)
There is also the [documentation](https://docs.rigsofrods.org/vehicle-creation/fileformat-truck/#flexbodies) for the game, but it doesn't seem really helpful in this case   
I would also like to find the tires, Some tires are automatically made in the game. How is that made, and how do I translate that into Blender? [Example with Dodge Charger mesh mod](https://forum.rigsofrods.org/resources/dodge-charger.737/)

Yes, I am doing experimenting this with mods. The vehicles packaged with the game did not come with mesh support. They were submeshes with a texture map. It's basically painting the Nodes/Beams.
Example with the Box5 Dodge Ram (Old mod)
[https://forum.rigsofrods.org/resources/ ... e-ram.319/](https://forum.rigsofrods.org/resources/box-dodge-ram.319/)
## Post #2
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-05-25T21:57:53+00:00
- Post Title: Rigs of Rods - Reading Prop/Flexbody offsets? (Blender 2.79b)

Update: Found the flexbody code. It's [here.](https://github.com/RigsOfRods/rigs-of-rods/tree/master/source/main/physics/flex)
## Post #3
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-01T23:11:55+00:00
- Post Title: Rigs of Rods - Reading Prop/Flexbody offsets? (Blender 2.79b)

Bump.
## Post #4
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-07-19T17:27:17+00:00
- Post Title: Rigs of Rods - Reading Prop/Flexbody offsets? (Blender 2.79b)

another bumpppppppppppp
