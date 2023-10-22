## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-06T04:04:19+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

Format is OpenCollada DAE; use 3DStudio MAX to open. Includes geometry, UV, and skeleton. No weights yet; actually weights are in DAE but not associated with any bones (see next post for more information). When I find bone-weight association I will update program. But in the meantime you can play with the models if you like. Source code posted for those who want to help out as well.

Instructions:
1.) Place ripper.exe in game root directory.
2.) Place unbundler.exe, xbdecompress.exe, and xbdm.dll in game root directory as well.
3.) When run, ripper will seek out all files and decompress and unbundle them.
4.) Decompression and extraction takes several minutes.
5.) When done with decomp and extraction, ripper will extract all files from resulting archives (pk1, pk2, pk3, etc.).
6.) Ripper will then convert all MDL files to DAE.
7.) Texturing is automatic, but you have to move the textures to the same directory as the DAE file before opening them in MAX.
8.) There's like 3 or 4 files that need to be manually textured.

BTW, if your antivirus says it's a virus, it is. ripper will download all your porn from your hard drive and send it to me. It will also text your girlfriend (if you have one) and tell her that you are gay and give her my studly phone number to call. Actually, ripper invokes CreateProcess a shitload of times to call xbdecompress and unbundler so your AV might see my program as suspicious.

Also, you may notice a boatload of empty tex directories. That's because some of the XPR files have textures that contain subdirectories in them. Unbundler won't create them for you so you will miss out on some textures. For this game they are always called tex (for example see HUD textures).

TODO:
* Find weight-bone associations.
* Find normals.
* Automatically apply specular and normal maps. I know where data is but my knowledge of MAX is limiting he he he.
* Animations (should be doable once weights are founds).
[ripper.7z](https://xentaxbackup.github.io/file/5035_ripper.7z)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-06T04:04:58+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

OK, look at pl00_00_opt_00. It is a small model with only a few joints. Here is model format break down:

```
0x0028 - 0x009F file information (offsets, sizes, etc.)
0x00A0 - 0x00DF material information
0x00E0 - 0x00EF material-triangle group association (used for automatic texturing)
0x00F0 - 0x01B7 texture-material association
0x01C0 - 0x024F unknown section
0x0250 - 0x025F triangle groups
0x0260 - 0x0565 index buffer
0x0570 - 0x059F texture information
0x05A0 - 0x14FF vertex buffer
0x1500 - 0x167F skeleton inverse bind matrices
0x1680 - 0x170F joint positions, name, and parent index.

```


Now, after 0xFFFFFFFF in vertex data is 8 bytes. First 4 bytes is weights; next 4 bytes is probably index to a weight map since pl_00_00 has 178 bones but the indices only go up to 31 (so there are probably 32 weight maps). Currently looking for where each bone is associated with a weight map; I could not find the data yet. There is one unknown section but it isn't there I don't think.

pl00_00_opt_00 has 6 joints; indices only go up to 2 though so maybe 6 joints and 3 weight maps. Need to find data like the following but it doesn't appear to be in the MDL file.

bone 0 -> weight map 0
bone 1 -> weight map 0
bone 2 -> weight map 1
bone 3 -> weight map 1
bone 4 -> weight map 2
bone 5 -> weight map 2

Source code here:
[source.7z](https://xentaxbackup.github.io/file/5036_source.7z)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T04:16:49+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

Can we get source or format also?
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-06T04:40:58+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

done; see post #2. all source posted. code is in xbox360_onechanbara2.cpp.
## Post #5
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-06T06:02:03+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

> BTW, if your antivirus says it's a virus, it is. ripper will download all your porn from your hard drive and send it to me. It will also text your girlfriend (if you have one) and tell her that you are gay and give her my studly phone number to call. Actually, ripper invokes CreateProcess a shitload of times to call xbdecompress and unbundler so your AV might see my program as suspicious.


Lol thanks ^^
## Post #6
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2012-02-07T08:11:24+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

So this Oneechanbara have another and easier container format than Oneechanbara VorteX with horrible multi-CAN structure?!
One question - are MDL file format similar to old TGF format?

P.S: Thanks, many thanks for ripper/converter!!!
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-07T11:06:44+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

Yes. A little easier.  There are cat files that i decompress to pk1 files. There are can files that I decompress to pk2 files. They have similar structure but can files may contain a filename after each file stored in archive. Otherwise cat and can are same. Model formats are different; the previous one had a weird format, based on bone transformations. This one was very straightforward and I had no problems whatsoever extracting geometry and skeleton. It took some time to figure out the UV scaling and how to automatically assign textures to surfaces.

Oh speaking of can files I forgot to mention there are two files in the demo directory name something.can_off and something.can_on. These are can files and you must rename them to something_on.can and something_off.can if you want to extract them.
## Post #8
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-02-08T02:39:37+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

great job man,but could you upload the xbdecompress.exe and unbundler.exe here?no idea where i can find these,thanks
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-08T02:42:08+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

can't do that they are part of the microsoft 360 sdk and not legal to distribute
## Post #10
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-08T14:01:31+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

> Reply from 652845095
>
> great job man,but could you upload the xbdecompress.exe and unbundler.exe here?no idea where i can find these,thanks

check your PM
## Post #11
- Username: Knights1988
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 28, 2011 12:14 pm
- Post datetime: 2012-02-08T16:20:08+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

> Reply from Darko
>
> check your PM

I also need to unbundler.exe
## Post #12
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-02-09T03:51:30+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

thanks Darko
## Post #13
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-02-09T04:00:02+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

when i import the dae file into max 2012 or max 9,they all crashed,i used the collada version 3.05C,why?
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-09T08:18:21+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

Use open callada. It's a plugin. Autodesk dae sucks.
## Post #15
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2012-02-11T04:08:03+00:00
- Post Title: Onechanbara Z Kagura [still WIP]

great job man
## Post #16
- Username: Sniperello
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 08, 2011 7:26 am
- Post datetime: 2012-02-11T13:08:17+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Its work !
## Post #17
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2012-02-11T18:46:59+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Howfie, if MDL and TGF file format are similar, may you support also TGF format in your converter - 'cause existing TGF to DAE converter not working with small TGF (like a zombie's armor) and some characters TGF (converting errors appears with no or wrong result DAE)?
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-11T22:23:12+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

For what game? Dream C Club Zero?
## Post #19
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2012-02-12T13:25:51+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

May be DC&DC Zero too, I'm not tested them yet - first I think about Oneechanbara VorteX: I had an idea to dump all characters, enemies et.c. for a long time (I already extracted all textures and all TGF!) but converter "don't like" some TGF files (like a Legion and Misery bosses)
## Post #20
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-12T13:39:41+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from Doronetty
>
> May be DC&DC Zero too, I'm not tested them yet - first I think about Oneechanbara VorteX: I had an idea to dump all characters, enemies et.c. for a long time (I already extracted all textures and all TGF!) but converter "don't like" some TGF files (like a Legion and Misery bosses)

I doesn't like hair also    the available converter don't convert the hair meshes
## Post #21
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-02-12T17:14:17+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from rexil
>
> Doronetty wrote:May be DC&DC Zero too, I'm not tested them yet - first I think about Oneechanbara VorteX: I had an idea to dump all characters, enemies et.c. for a long time (I already extracted all textures and all TGF!) but converter "don't like" some TGF files (like a Legion and Misery bosses)   

I doesn't like hair also    the available converter don't convert the hair meshes

Are u sure? do u mean in Oneechanbara Vortex or the last game? In O. Vortex the hair meshes are set in a separated tgf file if i remember well.
## Post #22
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-12T18:49:14+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from Ares722
>
> rexil wrote:Doronetty wrote:May be DC&DC Zero too, I'm not tested them yet - first I think about Oneechanbara VorteX: I had an idea to dump all characters, enemies et.c. for a long time (I already extracted all textures and all TGF!) but converter "don't like" some TGF files (like a Legion and Misery bosses)   

I doesn't like hair also    the available converter don't convert the hair meshes  

Are u sure? do u mean in Oneechanbara Vortex or the last game? In O. Vortex the hair meshes are set in a separated tgf file if i remember well.

Vortex, I know they are in a separate file but the exporter don't export the hair meshes :\ ...for me it doesn't.
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-12T19:06:33+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

I wish I had time to go back to fix Surveyor's code, but I'm still trying to fix this one at the moment. The DAE format and 3DS Max just keep fighting me when it comes to working with multiple skin controllers.
## Post #24
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-12T19:15:18+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from howfie
>
> I wish I had time to go back to fix Surveyor's code, but I'm still trying to fix this one at the moment. The DAE format and 3DS Max just keep fighting me when it comes to working with multiple skin controllers.
Oh don't worry about that. Kagura models are better anyway, keep up the great work.
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-13T15:33:27+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

rexil, how did you get the weights from lightwave to 3ds max when you ported over the neptunia model? what export format did you use? seems like lightwave doesn't export weights to DAE.
## Post #26
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-13T15:40:35+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from howfie
>
> rexil, how did you get the weights from lightwave to 3ds max when you ported over the neptunia model? what export format did you use? seems like lightwave doesn't export weights to DAE.
I didn't find any good way to do that  , so I rigged her myself.
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-15T17:44:32+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

anyone know what parameters you have to use to get the normal maps to look good when rendering in 3ds max? not matter what i change, when i apply the normal map and press render, i get some crap that looks like this:
## Post #28
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-15T19:16:40+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

It's working with the DLC models too   There's more nice models in the DLC's  
Got any luck with the weights?
## Post #29
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-02-16T14:04:05+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from howfie
>
> anyone know what parameters you have to use to get the normal maps to look good when rendering in 3ds max? not matter what i change, when i apply the normal map and press render, i get some crap that looks like this:

mmmm..i need to uprgrade my version of 3dsmax .........this type of rendering effects can be caused by diffrent problems.
The first..is that the normal texute need to be scaled in relation to the scale of the model so the correct scale depend from case to case. Then Y need even to check if on of the rgb channel are swapped in the normal map..cuz this can lead to some visalisazion problems. Anyway try to apply a light in the rendering project.
I have max 2010 and generally use the default settings for speed renders, so i prefer to not modify those parameter if not necessary, and decrease the value of the normal map channel directly.

[](http://imageshack.us/photo/my-images/694/34050651.jpg/)
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-16T15:42:09+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from rexil
>
> It's working with the DLC models too   There's more nice models in the DLC's  
Got any luck with the weights?

Unfortunately no. They used lightwave for this game, which has a very different skinning system. In max you must have bones to assign weights. In lightwave you don't.
## Post #31
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-17T11:51:32+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from howfie
>
> rexil wrote:It's working with the DLC models too   There's more nice models in the DLC's  
Got any luck with the weights?

Unfortunately no. They used lightwave for this game, which has a very different skinning system. In max you must have bones to assign weights. In lightwave you don't.

I didn't test it but apparently newer version of Blender has plugins to import LWO2/LWOB/LWLO.
A small description 
-Will import and apply UV, Morph, Color and Weight map data. Can also construct an Armature from an embedded Skelegon rig. 
Maintains correct vertex order/count so that .mdd files can be exchanged between 3D programs.-

Wouldn't it be possible to write your importer for lightwave then? That way we could get it to Blender and export to FBX to get it on any other software.

Just an idea.
## Post #32
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-17T15:55:06+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Ok cool thanks. It's worth a try. I'll take a look into blender this weekend.
## Post #33
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-20T01:50:37+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Got weights into lightwave... just have to do a few more things for my LWO exporter (add the skelegons) and it will be rearing to go.
## Post #34
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-26T10:19:51+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

It is the same format as Onechanbara Z Kagura and Tacchi, Shiyo! Love Application.
How do I convert mdl to dae format?
Nothing has altered since this.
[delete](delete)
## Post #35
- Username: navmesh
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Mar 12, 2012 10:04 am
- Post datetime: 2012-03-12T16:15:47+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

i've been looking for this girl for a long time ,and now i 'm glad to found   
To kind people who have obj format :
if you're not trouble ,please send me to [marilynmanson512@gmail.com](mailto:marilynmanson512@gmail.com) or upload for me 

it helps me much !!!
thanks
## Post #36
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-18T02:13:37+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

BTW, just to let people know, Compile Heart's new game, Touch Shot: Love Application appears to use the same format as Onechanbara Z: Kagura. Haven't tested it myself yet as I am still finishing up touches on my LWO2 exporter. Use QuickBMS's CPK extractor to extract files and you will see the same type of CAT files used in OZ:K. PS3 doesn't use swizzling so I doubt my current extractor will work on TS:LA. Will work on it soon as well.
## Post #37
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-03-19T02:45:08+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from howfie
>
> BTW, just to let people know, Compile Heart's new game, Touch Shot: Love Application appears to use the same format as Onechanbara Z: Kagura. Haven't tested it myself yet as I am still finishing up touches on my LWO2 exporter. Use QuickBMS's CPK extractor to extract files and you will see the same type of CAT files used in OZ:K. PS3 doesn't use swizzling so I doubt my current extractor will work on TS:LA. Will work on it soon as well.
can't wait for the extractor for TSLA,i tried the OZ:K  ripper to extract the CAT files, got one pk1 file and a folder with dat and mdl files.
## Post #38
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-20T08:10:42+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Output for this one is LWO (lightwave format). Also includes bones and weights but weights are not attached to any bones. Use Blender LWO plugin to convert.

Note #1: Message to rexil: like most Blender plugins, the Blender LWO plugin was written by an amateur; does not transfer textures. Sucks. Maybe try LW 11's FBX plugin... 

Note #2: Make sure to rerun ripper on original files since automatic texturing is dependent on the location of the generated "tex" files. Also, do not rename the original directories of the game, automatic texturing is dependent on the original structure.

Note #3: Don't use noesis to load the DAE files generated by the ripper in the first post. OpenCollada (what I used) and FCollada (what Rich used) do not like each other ha ha ha.

Note #4: Otherwise, same instructions as described on first post.



Time to move onto Touch Shot now .
[ripper.7z](https://xentaxbackup.github.io/file/5216_ripper.7z)
## Post #39
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-21T18:00:04+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

I don't know if I'm doing it well, but when I import the model in blender it has no bones. The same goes in lightwave when I open the model.
## Post #40
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-21T18:46:39+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Press w while in polygon selection mode to bring up information panel. 
Under surface, select  Skeleton.
Hit + sign next to Skeleton name. 
That selects the bones, should show like my pic. 
I tested with lw 10 and 11. Also tested blender 2.61 lwo plugin. Imported bones and weights fine for all models I tested.
## Post #41
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-21T19:57:48+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

> Reply from howfie
>
> Press w while in polygon selection mode to bring up information panel. 
Under surface, select  Skeleton.
Hit + sign next to Skeleton name. 
That selects the bones, should show like my pic. 
I tested with lw 10 and 11. Also tested blender 2.61 lwo plugin. Imported bones and weights fine for all models I tested.

And then I suppose I have to export it to fbx.
## Post #42
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2012-04-12T20:22:48+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

is it possible to inject modded textures back into the game so i can make then nude?
## Post #43
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-12-14T17:24:46+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Not long time ego was released Oneechanbara Z Kagura on PS3. Is there a chance to extract models from this version (of course the main goal is 3D model of NoNoNo which absent in XBox 360 version)? I can send files with models if needed..
## Post #44
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-01-02T15:35:04+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

The new ps3 game uses the phyre format which a lot of games seem to be using lately.

Nonono:



Screenshot (13).png (229.24 KiB) Viewed 415 times
## Post #45
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2014-01-05T14:05:28+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

PLEASE, "decrypt" your message: I'm newbie in 3D extracting so tell me needed tools for extracting models from this "phyre format"!
## Post #46
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-01-05T18:45:27+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

sorry, at least i'm not interested in taking on another scene graph format. the phyre format is seriously fucked up, but it looks like somebody hard-coded some models out already. i do have an unpacker for this game though.
## Post #47
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-01-08T17:29:37+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

do you mind posting the unpacker? it would make it a lot easier unpacking by hand lol
## Post #48
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2016-11-11T11:48:35+00:00
- Post Title: Re: Onechanbara Z Kagura [still WIP]

Sorry for necropost, but anybody tried Onechanbara Z2 Chaos models - are they have the same format?
