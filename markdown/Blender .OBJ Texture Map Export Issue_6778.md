## Post #1
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-06-13T17:24:04+00:00
- Post Title: Blender .OBJ Texture Map Export Issue

Hi again everyone! 

     After playing F.E.A.R. and the expansions the only weapons that I thought looked awesome were in Persues Mandate which were the VES Advanced Rifle, LP4 Lightning Gun and the Type-12 Laser Carbine. Since the F.E.A.R. mod kit didn't support the file format in any of the expansions I used 3D Ripper DX to get the VES from a frame. 

     I opened the mesh .OBJ file in Blender and removed everything but the weapon mesh, all good. Then I went through the .DDS files for the UV Map and the Normal Texture. Found both and successfully mapped both of them to the model in Blender which looks fine in the program. Problem comes when I try to export it as an .OBJ file through Blender. The model comes out right but the mapping for the texture is all wrong when I opened it in Noesis.

     I've uploaded a Word Doc with a screen-shot of what I'm talking about in Noesis.

     So I know that Blender is a complex program and considering I'm totally new at it I'm fairly sure that there is some setting that I'm not using correctly. I keep both the .BLEND files, the .OBJ file, the .MTL file, the .DDS UV and Normal Texture files all in the same place so I know it isn't that. I've also tried opening the .OBJ file in Nifskope for testing and while it shows the mesh it gives an error 

"failed to open "C:/Users/Matthew/Desktop/Game Models/Advanced" material "material_769_Advanced_Rifle.dds" not found in mtllib". 

     Now before when I opened the file in Noesis it didn't show any textures at all so I went into the .MTL file and did some google searching and found that the mapping coordinates were referencing a file that didn't exist! I had named the normal .DDS as "Advanced Rifle.dds" and the UV as "Advanced Rifle UV.dds". I renamed the normal .DDS to match the file above and while the texture actually showed up as you can see in the picture it came out wrong.

     Any help, tips or insights would be appreciated.
[VES Advanced Rifle Noesis.doc](https://xentaxbackup.github.io/file/4330_VES Advanced Rifle Noesis.doc)
## Post #2
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-06-13T17:26:40+00:00
- Post Title: Blender .OBJ Texture Map Export Issue

Since I'm still limited to one upload and a max file size of 256 KB I've uploaded the blender picture here for comparison. Oh and in case somebody asks I haven't gone and tried to get the Laser carbine or the Lightning gun yet.
[VES Advanced Rifle Blender.doc](https://xentaxbackup.github.io/file/4331_VES Advanced Rifle Blender.doc)
## Post #3
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-06-14T01:12:06+00:00
- Post Title: Blender .OBJ Texture Map Export Issue

As an update I tried re-importing the textured model which blender just plain did nothing as far as I could tell. I then tried making a new file with the model but no texture, exported then re-imported fine. I've also tried to export it in other formats that Noesis can read, the other ones just come out with no texture. It seems like the texture is partially set with the model but not all the way which is why the exports aren't working.
## Post #4
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-06-16T07:16:34+00:00
- Post Title: Blender .OBJ Texture Map Export Issue

Check the mtl file and make sure that all the definitions are pointing at valid paths and that the definition that causes the error in particular even exists at all. It might not hurt to cross reference with the obj file and make sure there isn't just naming weirdness that causes it to explode. I've done lots of importing/exporting of obj/mtl files from blender and had no issues.
## Post #5
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-06-24T09:46:19+00:00
- Post Title: Blender .OBJ Texture Map Export Issue

Okies. As you said you was new to all this ill take that as literal and do objects 101 for you   

The first thing to realise is, when a model is in a 3d editor like blender, max, maya etc. file formats dont actually mean anything. you only create a file format when you save/extract the model. What i mean is you could import a model from a game or create a simple model within blender if you looked at them they would both be handled exactly the same. The mesh itself consists of points, edges and polygons, the materials are done the same way too. its only when you export the model that things change between formats. A perfect example of this is with .obj itself. Almost all ( standard 3d editor ) model formats hold the material information within the object itself but with .OBJ the materials are stored in the separate .MTL file. You only then get a problem next time you try importing that format and some information is either wrong or missing.

For wavefront OBJ files you have 2-3 components ( usually 3 ) they are. The object itself, the material file and any relevant textures. Now i said 2 to 3 components, 2 being object and material file, you don't always need textures, but usually you have them. You can't have textures without a material file tho, but you can have textures without UV info as you will see why in a bit..

For now dont think too much about .obj specifically i wanna talk about models in general.. as i said with obj you get the mesh, the material file and the textures with almost all other formats you get a mesh and the textures. A mesh does many different things within it, a texture does only one thing. 
The reason i say this is because it seemed like you are a little confused regarding UV. UV has nothing to do with textures ( or pictures if you like, same difference ) i noticed you said at one point "Then I went through the .DDS files for the UV Map and the Normal Texture. Found both and successfully mapped both of them to the model in Blender which looks fine in the program" those are actually called the Colour map and Normal map textures, UV plays no part in them really. so when you come to renaming textures files your really better off calling "Advanced Rifle UV.dds" - " Advanced Rifle C.dds " and "Advanced Rifle.dds" as "Advanced Rifle N.dds". If your gonna call any of them "Advanced Rifle.dds" then make it the Colour map not the normal map as the colour map is nearly always the primary image used ( just better house keeping).

OK back to objects... like i said an object does many different things but it is mainly controlled by 3 basic things. The actual mesh itself, the materials/surfaces and the UV coordinates ( if they are needed ) not all meshes need UV info. As i said, in general all this is contained within the mesh ESP while in the 3d program but also when exporting. The only exception to this is with obj where it takes the material info and stores it in the MTL file

MESHES. We dont need to talk about meshes too much as ive already gone over them a little, suffice to say, meshes are a result of points and edges being combined to create a small flat sheet, a polygon ( a polygon is an enclosed shape, the first and last points MUST join together ) the minimum amount of points you can have in a polygon is 3, a triangle but often you can find models made in quads ( a 4 sided sheet ) and sometimes its handy to use +4 point polygons but for efficiency reasons often they split into several triangles at optimisation. A very simple example of this is a basic cylinder object, say.. a 12 sided cylinder. It's made up of 12 long sides and 2 ends. The 12 sides are gonna be quads so they each one can join the polygon above it on both the left and right edges and the same for the polygon below it, but the 2 ends are made of flat 12 point polygons, so each join on the side polygons can join the end piece. Then often what will happen at optimisation is that 12 point polygon will get split into 12 triangles all joining at the center (kinda like getting a whole pizza and cutting it into 12 equal slices, all the cuts intersect at the center ). Many polygons joined together create a mesh object.. ok thats basic meshes over....

MATERIALS/SURFACES. All mesh objects have at least one material/surface even if its just the default ( usually grey and has basic settings applied ) A surface is just a collection of polygons grouped together to allow them to have visual information applied to them. A material is those various different visual elements applied to that surface group. You can have pretty much as many surface groups as you like.
The most common elements are Colour, Luminosity/self illumination ( how much light it gives off ) Diffuse ( how much light it receives ) Specular ( how bright a highlight it has ) Glossiness ( how sharp the highlight is, a billiard ball has a high gloss finish like 90% where as a rubber tyre  does have a highlight but its very spread out like 10%) reflectivity and finally bump/normal ( height data, make a flat polygon appear to have extra detail like grooves when really its just flat )

All of these elements can either be used with there own settings or you can control them with an image/texture, for example... You make a ball, you want it orange and quite shiny. You could just go to the colour setting and set it to orange, the diffuse to 100 so it receives as much light as it can, you then give it a high specular level ( so it has a bright highlight) and you give it a high gloss level ( to make it a very defined highlight ). You wouldn't bother creating a pure orange picture and applying it to make the grey ball look orange, why create it when the setting is already there for you in the program.. 
But... If say you created a wall for inside a room, you could either just colour the wall whatever way you liked or you might wanna make it look like it has wall paper, so you apply your wallpaper C.dds image to that wall surface then you need to set the image scale and coordinates to fit the surface area ( kind of like if you are setting up a projector, you put the screen up which is 2 meters by 2 meters, you turn on the projector and find its not quite in the right place and it doesnt fit the screen. so you move the projection into the right place then you scale it up to fill the screen.) the same works with surfaces. you have a 2 meter high wall and a wallpaper texture you could either set the image scaling to be 1 meter and have the image repeat twice vertically or set the scaling to 2 meters and it will stretch the image to fit the height of the wall. 
This method can be applied to all of the other surface settings, so if you also had a normal map for the same wallpaper texture you would load that in, apply it to the normal channel and give it the same scaling ratio as the colour map, then they will line up perfectly, which gives your flat wall several different colours and makes it look bumpy. So thats how you can have objects with or without textures and Not using any UV info. 
The difference between the two methods, UV's vs No UV's is you can only use this method on objects that will not move, a wall doesnt move so its fine, but if going back to the projector screen setup.. You have it all set up great and someone moves the screen a bit, the projection stays where it is it's the object ( screen ) thats moved now so the texture wont line up properly. Thats where UV comes in.....

UV's are used for controlling many things but its mainly for mapping textures to meshes, they are also used to control things like weight maps, deformation maps and lots of other things, but for games its mainly apply textures accurately. UV's are nothing more than Exploded/flattened out versions of the mesh, all laid out flat .
Kinda like.. almost everybody at some point at school made a dice out of card or paper, when you made that you started with what looks like a cross or T shape, which was really just all 6 of the cubes panels unfolded, well thats what a set of UV coordinates are. you can either have one set of UV coords for the whole object in which case you would make your Dice texture in the same cross/T pattern as the uv and just have one surface/material group and tell that surface to use that UV set and use that dice texture. OR.. you could select each side of the cube and give it it's own uv set, then you need to make 6 surface groups and 6 individual dice images, then map one image and uv set to each surface.
The reason you could do it either way is this.. if you go the multiple uv sets method, it means you have say 6 512x512 images each with there own fairly high quality dice texture, Or you you have 1 512x512 image with all 6 sides on the texture, which means to make them all fit on the image you have to make each of the sides images smaller ( less detail ) 

OK thats 3d models 101 over with hopefully that has given you some insight into models, so things wont seem quite as daunting when messing with stuff.. " PHEW! " 

ONTO your problem specifically... its fine that you renamed the textures ( god those dx ripper names are annoying.. 69AF43 etc grr ) but if you renamed them After you mapped them to tor object then thats why it was having trouble finding them, which you tried to remedy after. you just have to remember to rename the files before first applying them to the object.
So you gather the original obj, mtl and image files together, rename the image files to obvious things like Rifle C.dds and rifle N.dds, load them all in and map the images to the correct material channels, also if you happened to notice any other images that looked like your colour map but were in black and white ( or rather shades of grey ) then keep those too as they will be things like specular maps or diffuse maps... Now you should have your model textured and looking nice, time for export... if you have them make sure settings like, "keep file links" and "keep surface/material settings". Altho from the sounds of things you already had. Then export and all should be fine. The .obj will keep the surface groups in the mesh, while the .MTL file will contain all the material info weather it be basic settings or images and how its linked to the surface groups . To be honest i think the only reason you had a problem was coz you renamed those images and it didnt match up with what the mtl file said. ive done the same and also with me when i tried to edit the mtl file and correct the mistake it didnt work properly. it was only after i re-exported the object with the new links to the the images saved in the mtl ( rather than edited in ) did it work..

Ok hopefully that can help you along the way, i think i covered " help, tips and insight ".... have fun.    

Nobby.
