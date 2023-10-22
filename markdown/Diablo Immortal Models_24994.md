## Post #1
- Username: sanktanglia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 28, 2022 4:16 am
- Post datetime: 2022-01-27T20:25:53+00:00
- Post Title: Diablo Immortal Models

Im working on writing an importer for diablo immortal files, using a template [https://github.com/CucFlavius/Zee-010-Templates](https://github.com/CucFlavius/Zee-010-Templates). I can render out the mesh, but im currently stuck on the texture coordinates. The vertex buffer has the following structure
        VECTOR4H tangentAsQuat;
        VECTOR2H uv;
but the uv values arent in the 0-1 as id expect, instead normally being between .3 and .5 and -.3 and -.5 Im assuming this has something to do with the tangent but the math behind it is a bit above my knowledge level. Im attaching some copies of models. I will also pay whoever helps solves this!


[https://www.dropbox.com/s/2up7266hjpsb2 ... .Mesh?dl=0](https://www.dropbox.com/s/2up7266hjpsb22m/Mesh_boss_leoric.Mesh?dl=0)
[https://www.dropbox.com/s/siqi6dr1vuqqv ... .Mesh?dl=0](https://www.dropbox.com/s/siqi6dr1vuqqvse/Mesh_potion_nec.Mesh?dl=0)
[https://www.dropbox.com/s/4y7xoi5hgt22m ... .Mesh?dl=0](https://www.dropbox.com/s/4y7xoi5hgt22muu/Mesh_potion_mk.Mesh?dl=0)
