## Post #1
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-10-05T17:35:29+00:00
- Post Title: Payday 2 model format

Hey everyone..

Im hoping someone might be able to look into this model format and maybe create an import script or a small converter or something.
The unpacking of the payday 2 .Bundle files is now known, so i had a go at unpacking a few of them.

I went for a couple of the smaller ones and it seems like i got a couple of the weapon modification parts..
Heres the file list for one of those weapon mods..

wpn_fps_pis_1911_b_vented.0.cooked_physics
wpn_fps_pis_1911_b_vented.0.material_config
wpn_fps_pis_1911_b_vented.0.model
wpn_fps_pis_1911_b_vented.0.object
barrel_vented_df.0.texture
barrel_vented_nm.0.texture
slide_vented_df.0.texture
slide_vented_nm.0.texture
wpn_fps_pis_1911_b_vented.0.unit

Now i know the .Textures are just DDS files. I dragged one into Notepad++ and right at the start it said DDS, so i tried renaming one to a DDS file and i was able to load it into gfx viewers no problem. 
The .Model file i presume to be the actual model and between the .Material_config and.object files it seems to control the materials, but i dont know how that would translate into say Max materials or an OBJ's .Mat file.

So yeah... If someone feels like having a crack at this model format and see if its possible to maybe write a max script or an OBJ converter or something for it, i would be eternally grateful. 
I have a buddy who has a 3d printer at his works and id love to have a crack at printing a couple of masks and weapons ( with their mod parts) on it   

Finally here's a [Rar](http://www.mediafire.com/download/m2ho3ud5lblpi37/Bundles.rar) file which contains those 2 bundles i unpacked..

I really do hope someone can figure this out, id so love to be able to mess with the models
## Post #2
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-05T18:35:05+00:00
- Post Title: Payday 2 model format

Wait, hold up. So you can just rename a .texture to .dds and it will open?

Also, I support this. If model modding for Payday 2 is possible it would open up a plethora of opportunities. Imagine robbing a bank as Wei Shen!
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-05T20:12:40+00:00
- Post Title: Payday 2 model format

> Reply from Nobby
>
> If someone feels like having a crack at this model formatYou don't need to crack this - just analyze. These are the params of a submesh of wpn_fps_pis_1911_b_vented.0.model:
file offset 0x668 -0x251C 655 * x,y,z vertex (3 floats)

0x95CC - 0xA381
585*3 faceindices uint16

[](http://www.pic-upload.de/view-20926319/wpn_fps_pis_1911_b_vented.0.model.jpg.html)

[weap.zip](http://www.uploadmb.com/dw.php?id=1381003406)

Sadly I'm not interested in guns.
## Post #4
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-10-05T22:58:48+00:00
- Post Title: Payday 2 model format

> Reply from SergeantJoe
>
> Wait, hold up. So you can just rename a .texture to .dds and it will open?Yes.. Exactly that!


> Reply from shakotay2
>
> You don't need to crack this - just analyze. These are the params of a submesh of wpn_fps_pis_1911_b_vented.0.model:
file offset 0x668 -0x251C 655 * x,y,z vertex (3 floats)

0x95CC - 0xA381
585*3 faceindices uint16



weap.zip

Sadly I'm not interested in guns.
You will have to excuse me but, I honestly dont know what that means, i really am dumb when it comes to this kind of thing.  . Do i have to input those numbers somewhere? if so where? do i have to edit the file somehow to change something to these numbers? i really dont know what im supposed to do with that information.
If you could please explain in "tard" terms how i use the above information to load/convert the .model files into a useable format, or into a 3d app, that would be awesome.

Also, guns isnt my main concern either, once i know how to get objects into a 3d app like max or lightwave. i will unpack everything and get all the masks, characters, weapons and any other models i can find.

I see in that zip file, you managed to convert the file into an .obj, that is exactly what i am looking to do. Did you also manage to work out how the material files work for what surface is what.. or are they just one material per mesh ??  I guess as long as the UV map is still intact then the textures can be manually re-applied and a new Material file will be saved then.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-06T06:48:08+00:00
- Post Title: Payday 2 model format

> Reply from Nobby
>
> Do i have to input those numbers somewhere? if so where? do i have to edit the file somehow to change something to these numbers? i really dont know what im supposed to do with that information.
That info maybe useful for someone with a basic understanding of 3D modelling.

> If you could please explain in "tard" terms how i use the above information to load/convert the .model files into a useable format, or into a 3d app, that would be awesome.Please read this thread from the 3rd post: [viewtopic.php?f=16&t=10720&p=87592&hili ... tut#p87592](http://forum.xentax.com/viewtopic.php?f=16&t=10720&p=87592&hilit=chrrox+tut#p87592)
read the mentioned tutorial from chrrox.

After you read/understood it (and the crash course for DragonBall meshes, too) I can give you some details for" Payday 2 models.
"But so far I did only get one kind of submesh. There are other data to be explored."

> Did you also manage to work out how the material files work for what surface is what.. or are they just one material per mesh ??Speaking of wpn_fps_pis_1911_b_vented.0.material_config? It contains two material definitions which each have a file path to a diffuse and a bump-normal map.

Since I found the uv data (texture coords): [weap_tex.zip](http://www.uploadmb.com/dw.php?id=1381041378) it should be possible to apply the four *.texture files to the weapon.

The uv data (655*2 floats, x,y) is to be found directly after the vertex data.
## Post #6
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-10-06T15:19:25+00:00
- Post Title: Payday 2 model format

i had a look through the tutorial, it really didnt make much sense to me, but im not very good at understanding that kind of thing anyway. So nothing is new there..

Is anyone able to create a little batch script or a max script to be able to convert/import the files. i would find that a lot easier to handle.
If anyone needs more examples of meshes, just say, ive now unpacked all of them in anticipation of being able to load them into something  characters, weapons, vehicles, masks, equipment and some of the level objects, like safes..
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-06T15:36:32+00:00
- Post Title: Payday 2 model format

Ok, if you could upload 2 or 3 of your preferred vehicle models I could have a look at/try to convert them.
(But don't expect a converter from me.)

While it's often easy to convert a single model it's time consuming to create a universal converter.
There's in general no "little script" like the ones used for unpacking archives.
## Post #8
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-10-06T21:58:44+00:00
- Post Title: Payday 2 model format

For sure i can post a few more models, in fact heres a link to 3 vehicles i just bundled up  [LINK](http://www.mediafire.com/download/0uqei4ttncqcnny/Bundles_2.rar) 
These might be multi part objects, as there is a cop car and a swat van, both which have doors that open, third is the cocaine boat....

I know its not really just a case of, knocking up a script, like when you do package unpacking, esp when the process normally requires a couple of different programs to work. 
And i know it sounds like im just being lazy and want the easy option. But in all honesty is have a "thing" regarding trying to learn new languages, it just doesnt sink in.. I took French class at school for about 5 years, i can say hello and good bye, but thats about it. 
I cant even learn computer "Basic" other than the regular .. 
10 print " hello world" 
20 goto 10 
RUN.

Unless someone is sat down beside me to explain it all step by step, so i can copy cat them, it wont sink in. So really what im after is some way even if its just streamlining how you do the adjustment to the file to convert it, so even i could do it.. 
I understand if you do not have the time to make a converter, i wasnt expecting you to, hoping maybe, but not expecting  but perhaps you might be able to recommend someone, who might be able to help in some way with making this process a little less " file edit'y " for dummies like me..

Thanks again, for looking into this for me.

PS, i have posted in the Archive unpacking section about unpacking payday2 .bundle files [HERE](http://forum.xentax.com/viewtopic.php?f=10&t=10848) so everyone can have a mess with the files. 
The unpacker also does repack, so if we can get the models converted a little easier, then it should be possible to do some kind of model/texture modding for the game.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-07T22:45:58+00:00
- Post Title: Payday 2 model format

> Reply from Nobby
>
> For sure i can post a few more models, in fact heres a link to 3 vehicles[...]thx.

> These might be multi part objects[...]yep. Especially the cop car is. Took me more time than expected since there are 3 collision (or LOD?) models contained and 2 officer chars.
[](http://www.pic-upload.de/view-20949477/car_pol_chars.jpg.html)
Finally I found the car model itself and it's uv data which I zipped.
[](http://www.pic-upload.de/view-20949476/car_police_uv.jpg.html)
[car_police.zip](http://www.uploadmb.com/dw.php?id=1381184209)
(The other two models I will care for later.)
edit: well, seems, noone's interested so I'll stop my investigations

> I cant even learn computer "Basic" other than the regular .. 
>
> 10 print " hello world" 
>
> 20 goto 10 
>
> RUN.You really should have tried to plot a cube, too.  

> but perhaps you might be able to recommend someone, who might be able to help in some way with making this process a little less " file edit'y " for dummies like me..I fear I can't. I think you missed "plotting the cube". I guess anyone who's dealing with 3D modelling did this step (or a similar one). You can't expect to fully understand how to get the data if you did not do this basic step, imho. (And there are some further steps than just plotting a cube.) But it depends on your ambition. Try little steps. I really would recommend you try plotting a cube using basic to get an understanding of vectors.
After this plotting the cop car (or maybe a simpler model) could be your next task.

edit: here's how to plot a sine curve.

```
    dumx = x * 3.14159 / 180!
    y = SIN(dumx)
    PSET (x, y)
NEXT x
```
## Post #10
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-21T23:56:30+00:00
- Post Title: Payday 2 model format

I hate to be a gravedigger, but just fyi there is a Blender .model import script [here](https://bitbucket.org/zabb65/payday-2-modding-information/src/8fb3648f12bba0bc3f3860b132fc8169961e364e/python%20scripts/?at=default).
It kind of works for meshes, although for some reason doesn't support UVs/materials even though it says it does.

Those guys were even planning to make an export script, but they haven't touched it since October. Maybe someone else can pick it up?
## Post #11
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2014-01-08T01:31:32+00:00
- Post Title: Payday 2 model format

> Reply from SergeantJoe
>
> I hate to be a gravedigger, but just fyi there is a Blender .model import script here.
It kind of works for meshes, although for some reason doesn't support UVs/materials even though it says it does.

Those guys were even planning to make an export script, but they haven't touched it since October. Maybe someone else can pick it up?
Just to give a bit of an update, plus breath some life into this dead old horse of a thread..

I tried the above mentioned import script ( i had to DL blender just to try it as i normally stay far FAR away from blender) 
Yes it worked exactly how you said it would, it imported the mesh perfectly but without the UV map ( materials are easy to get hold of, they are just .texture files, which you just rename to .DDS ) but as it didnt read the UV info there is no way to get the texture applied properly to the mesh ( pointless )
BUT.. i did find a solution.. NinjaRipper ( basically a reworked version of 3dRipperDX) just set it to DX9 mode and you can rip any of the models you like and them import the ripped file into 3dsMax.. i just tested it with a mask and it came out pretty much fine. The only issue it has is.. Occasionally one or two of the UVmaps will be upside down, which isnt really a problem, just flip it and it all lines up perfectly.

So yeah to rip any of the models form PD2 just use NinjaRipper, it works a treat.. Now comes the long job of ripping every mask available.

Big thanks to BlackNinja and Tosyk for their work on NinjaRipper.. i like it very much.. i was a big user of 3DripperDX and this works better than that, so im a happy man
