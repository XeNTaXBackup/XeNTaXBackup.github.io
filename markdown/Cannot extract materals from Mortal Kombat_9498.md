## Post #1
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-08-17T15:04:39+00:00
- Post Title: Cannot extract materals from Mortal Kombat

So I ripped the xbox 360 version of Mortal Kombat Komplete Edition and Im using UE Viewer to rip the meshes and I am able to export the mesh but I cannot export materials. I know you cannot export animations so I use the command umodel -noanim then I get errors about missing materials so I use umodel -noanim -notex <name of asset> then I can get the mesh without the textures, so anyone know how I can get the textures?
## Post #2
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-08-17T19:25:05+00:00
- Post Title: Cannot extract materals from Mortal Kombat

For me, umodel.exe -export -noanim <nameoffile> works correctly.
## Post #3
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-08-18T11:28:04+00:00
- Post Title: Cannot extract materals from Mortal Kombat

Nope still getting the same error
## Post #4
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-08-18T12:58:32+00:00
- Post Title: Cannot extract materals from Mortal Kombat

Thats wierd mine works perfectly
## Post #5
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-08-18T14:50:00+00:00
- Post Title: Cannot extract materals from Mortal Kombat

> Reply from farakh
>
> So I ripped the xbox 360 version of Mortal Kombat Komplete Edition and Im using UE Viewer to rip the meshes and I am able to export the mesh but I cannot export materials. I know you cannot export animations so I use the command umodel -noanim then I get errors about missing materials so I use umodel -noanim -notex <name of asset> then I can get the mesh without the textures, so anyone know how I can get the textures?

umodel -export -lzo -noanim -dds -all "the_name_of_the_pack_you_want"

That problem is beacuase of the zlib compression and you must indicate that to umodel with the -lzo.

See ya
## Post #6
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-08-18T18:03:49+00:00
- Post Title: Cannot extract materals from Mortal Kombat

OK, now some textures work and some dont. The reflection texture for the low poly model works but the texture for the high poly doesnt work.





TRDaz are youextracting meshes from the komplete edition or the normal one?
## Post #7
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-08-18T18:34:50+00:00
- Post Title: Cannot extract materals from Mortal Kombat

My UE viewer shows the same results as the pics above, but when I export the stuff, the textures are extracted just fine. What do you need materials for? You can just apply the textures manually in whatever program you're using.

Beware of a few things though... 

1. I wasn't getting the high poly model with regular export. I had to add the -md5 switch to get high poly counts. 
2. The high poly models have a lot of extra stuff in them you'll want to delete. 
3. The diffuse textures are relatively low detail. The models rely heavily on the normals and specular maps for detail.
## Post #8
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-08-19T10:57:03+00:00
- Post Title: Cannot extract materals from Mortal Kombat

> Reply from farakh
>
> 
TRDaz are youextracting meshes from the komplete edition or the normal one?
Normal, but I also tried Komplete Edition, worked fine.
