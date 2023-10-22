## Post #1
- Username: navmesh
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Mar 12, 2012 10:04 am
- Post datetime: 2012-07-01T08:12:35+00:00
- Post Title: how to combine diffuse ,specular ... texture into "normal" ?

hi
I have a problem about texturing, please help :

many models (such as xnalara models ) has normal ,diffuse and specular ... texture
and i don't know what to do with them to make it into only one texture with normal color,sothat
i can to apply to model ( i use milk shape 3d ))


here 's the preview of texture 
skin_d.DDS



body_l.TGA



body_s.DDS



cloth_d.DDS


cloth_mb.TGA


cloth_n.DDS




the _d.dds texture has color ,but it looks bad if we apply it to models
so i think there 's maybe a way to make these texture into one "normal color" texture

i mean "normal color" texture here is the texture like this







Here is the link to the dds texture and max files , i also converted to bmp and added to this pack

http://www.mediafire.com/?227l9zdasqr7adt


if you know ,please tell me

thanks so much
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-07-01T09:38:26+00:00
- Post Title: how to combine diffuse ,specular ... texture into "normal" ?

I may not have exactly understood what you want you can't make it one texture.
Because the shader is parallax and it means it expects to have diffuse,normal and specular textures.
But if you have extracted the model you can choose a diffuse shader for it(in your 3d software) and it just wants one texture.(normal color one)

If you want to make it into one material then I think you need to change the UV.
## Post #3
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-07-05T05:35:09+00:00
- Post Title: how to combine diffuse ,specular ... texture into "normal" ?

You want to bake those textures in a single difuse texture?? There's a way to do that in 3dsmax with render to texture.

[http://www.youtube.com/watch?v=dNzgq6D8Dlk&feature=plcp](http://www.youtube.com/watch?v=dNzgq6D8Dlk&feature=plcp)

The other way, you need to assign those textures in a correct way in your 3d software or engine.
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-07-20T09:52:09+00:00
- Post Title: how to combine diffuse ,specular ... texture into "normal" ?

As already said, u need to be more clear. Do u want simply apply the different textures in the right way to the mesh to obtain a good render or u want to do more? Bake the texures? I don't user milkshape3d but i don't think that milkhape supports the normal maps, because it doesn't have an avanced render engine. you can combine all those texures in a single material in other 3d apps like 3dsmax, maya and others designed for both modelling and rendering. U should improve ur knowledges on the web about how create  complex materials and where apply the different texures in specific channels of the material.

Another hint: Don't convert the dds textures in bitmap or jpg, because u lose a lot of texures informations like eventual alpha maps. 
A better conversion is dds to tga, if ur softwar doesn't support dds files.
