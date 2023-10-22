## Post #1
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-05-31T10:04:02+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

I have been working on a Modding Project for Zoo Tycoon 2.  My Goal is to Convert a number of the Creatures in Star Wars Galaxies into Zoo Animals.

Zoo Tycoon 2 uses the .nif format for their 3D Models, but Star Wars Galaxies uses the .mgn format.  I have a limited knowledge, but I really want to Succeed.  I also have a very limited number of Programs to use in the process, and can't afford the Official Versions of some of these Programs that would probably make this a whole lot easier.  I don't have access to the Popular 3dsMax or Maya Programs.  I haven't had much Success using either Blender or Milkshape, although I've tried my hand at both.

So far, this is what I've been able to do:

I first used the 3d Object Converter ([http://web.axelero.hu/karpo/](http://web.axelero.hu/karpo/)) to convert the .mgn files into WorldToolKit Neutral File Format, which is an .nff file.  From there, I used quick3D Professional ([http://www.freedownloadmanager.org/down ... al_6830_p/](http://www.freedownloadmanager.org/downloads/quick3D_Professional_6830_p/)) to convert the .nff files into Alias|Wavefront Objects, or .obj files.  Using NifSkope ([http://niftools.sourceforge.net/wiki/NifSkope](http://niftools.sourceforge.net/wiki/NifSkope)), I then converted the .obj files into .nif files.  I've been having some trouble, however, with the related Textures.  The Texture Maps and Skeletons seem to get lost in the Transition, and I'm not really sure how to go about finding or re-applying them.  The .nif files from Zoo Tycoon 2  have the Skeletons within them, there are no separate files, but I don't know how to Merge the .mgn and .skt files from Star Wars Galaxies together.  All I end up with are .nif Models with no Bones and Textures that wont apply.

I'm now messing around with Ultimate Unwrap 3d Pro ([http://www.unwrap3d.com/u3d/index.aspx](http://www.unwrap3d.com/u3d/index.aspx)), but Unfortunately I only have a Demo.  That seems to be the only Program that will let me Load up the .mgn Files with the .dds Textures and .skt Skeletons.  Since its only a Demo, it won't let me Save or anything else, so I'm not really sure what to do.  If only I could simply Export those combined Files from that Program into an .nif file that I could open in NifSkope, things would be a lot easier!

Ultimately, the Goal seems fairly simple:  to Convert .mgn Model files and their related .dds Texture (and what I'm assuming are Alpha Textures) files and .skt Skeleton files into the .nif file Format.  In practice, its been a huge Challenge.  I've read the older Threads on the Topic (nothing less than a Year old) but nothing really gets at what I'm looking for.

I hope someone out there will be able to Help.

If anyone needs me to Upload Files or anything, let me know!

Thanks!
## Post #2
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-31T20:46:29+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

The skeletons and textures are lost as soon as you convert the models to OBJ with 3D model converter.

OBJ doesn't support skeletons at all, and 3DMC doesn't save texture coords to OBJ.

Try finding something that will convert the models to to COLLADA's DAE, and then finding a DAE to NIF converter... That would likely be the easiest way to do it.
## Post #3
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-01T10:19:27+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

Thanks for the tip!

Unfortunately, my 3d Object Converter doesn't do .dae files.  It would be so much simpler if it would, or if it would simply convert to .nif files.  Or if NifSkope would load up the .mgn files, or if the Unwrap Programs would convert to .nif files.

Anyways, I'll be looking around for new Programs to convert.  If anyone has any tips, please let me know!

Thanks!
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-06-01T11:53:44+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

You can convert the Star Wars: Galaxies .mgn/sht and the .msh/sht files into Wavefront .obj (fully textured) format using the (registered) 3D Object Converter.
## Post #5
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-01T14:41:38+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

> Reply from Karpati
>
> You can convert the Star Wars: Galaxies .mgn/sht and the .msh/sht files into Wavefront .obj (fully textured) format using the (registered) 3D Object Converter.

If only I could Afford to Register!

I may end up having to go Buy a Program for this.  Seems a bit unnecessary for the types of small Modding Projects I'll be doing, but if its the only way, its the only way.

Anyone know of any Free Programs that can do this?

Thanks anyways!
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-06-01T15:38:33+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

The 3D O. C. supports the following file formats also:
  Star Wars: Battlefront  	.msh
  Star Wars: Battlefront	        .ter
  Star Wars: Empire at War	.alo
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-01T20:39:33+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

For converting Star Wars Galaxies to Gamebryo file!
Try use my maxscript in: [viewtopic.php?f=16&t=1991&hilit=Star+Wars+Galaxies](http://forum.xentax.com/viewtopic.php?f=16&t=1991&hilit=Star+Wars+Galaxies) (it's on page 2)

and then use Nif exporter for max/gamx to export: [http://niftools.sourceforge.net/wiki/NifTools](http://niftools.sourceforge.net/wiki/NifTools)

Should work and 100% free!!!
## Post #8
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-01T22:55:03+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

I just want to reiterate that no matter how you convert the data, if you convert the files to OBJ you WILL lose all bones and rigging information, as well as animation data.
## Post #9
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-02T16:57:27+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

> Reply from fatduck
>
> For converting Star Wars Galaxies to Gamebryo file!
Try use my maxscript in: viewtopic.php?f=16&t=1991&hilit=Star+Wars+Galaxies (it's on page 2)

and then use Nif exporter for max/gamx to export: http://niftools.sourceforge.net/wiki/NifTools

Should work and 100% free!!!

Thanks so much for the help!

I Downloaded the MaxScript and its working nicely.  I can Load my .mgn files into GMax!  Its awesome, thanks!

Unfortunately, I can't seem to figure out how to Configure the NifTools.  The Tutorials on the Website are referencing Files that were not Included in the Download!  Here's the Page with the Information I was looking at:  [http://niftools.sourceforge.net/wiki/Gmax/Installation](http://niftools.sourceforge.net/wiki/Gmax/Installation)

Maybe I'm looking at the wrong Information?  I Followed the Link there, which brought me to Downloading NifScope, but I can't find any of the GMax Plugins it was supposed to Include.

Also, is there a way to select the related Skeleton and Texture Files?  It seems there's a relatively complicated Texturing procedure, I'll have to work on that one, but I see nothing about Importing the Skeletons.

I'll keep working at it, though.  So far, so good!

Thanks!
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-02T21:18:30+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

Try download [the zipped one](http://sourceforge.net/projects/niftools/files/max_plugins/3.4/niftools-max-plugins-3.4.2.4632.7z/download), you can manually copy the files into Gmax's folder! The readme.txt should tell you what to do!

I never play  Star Wars Galaxies, so I don't really know the bones, materials format! But it wasn't too hard to add bones and texture to the models, right!?
## Post #11
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-02T22:42:25+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

The NIF format should contain a skeleton already. If it doesn't, then you likely lost the skeleton when you converted it to whatever format you did, before converting to NIF.

I was trying to warn you about that.
## Post #12
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-04T11:06:57+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

> Reply from fatduck
>
> Try download the zipped one, you can manually copy the files into Gmax's folder! The readme.txt should tell you what to do!

I never play  Star Wars Galaxies, so I don't really know the bones, materials format! But it wasn't too hard to add bones and texture to the models, right!?

Well, in SWG the Bones are in another file.  For Example, I am doing the Blistmok first.  The Blistmok Mesh is blistmok_l0.mgn, the Texture is blistmok_body.dds, and the Bones are in dinosaurid.skt.  There are also files with extensions like .lmg (I think this refers to Level of Detail), .ans (Animations), .lat (I think this contains references to the Animation Files), .sht (Shaders), and .sat (which references the .lmg .skt and .lat files).

I can probably solve the Issue with the Bones, I'll just Load up the closest Animal from ZT2 into NifSkope, then Paste the Blistmok over it, remove the first Animal's Mesh and adjust the Bones to fit the new one.  It may take a bit longer to do each one, but it just might be worth it.

Now the only Problem is the Texture.  When I Load the Mesh into Ultimate Unwrap 3d, the UV Map and Skeleton Load automatically.  This is the only Program that seems to work like this.  When I try to call up the Texture in GMax, there is no UV Map.  That Data seems to be Lost during the Import, and GMax is a bit clumsy when it comes to applying Textures.

Even so, this is Incredible Progress!  Thanks so much!  Now I just need to find a way to Apply the Texture.
## Post #13
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-04T11:11:44+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

> Reply from Satoh
>
> The NIF format should contain a skeleton already. If it doesn't, then you likely lost the skeleton when you converted it to whatever format you did, before converting to NIF.

I was trying to warn you about that.

The .nif files from Zoo Tycoon 2 already have the Skeletons within the Mesh.  The .mgn files from Star Wars Galaxies do not.  Those Skeletons are in .skt files.  Some Programs know what to do, like Ultimate Unwrap 3d, and will call up the related .skt and .dds files when Loading the Mesh.  GMax, unfortunately, does not.

I might just have to make the Skeletons from other Animals fit these Creatures.  Don't know how to handle the Textures, might have to end up Buying Ultimate Unwrap or something.
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-05T07:51:36+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

Could you send me some mgn file that had texture problem? I can take a look on next Tuesday!
## Post #15
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-05T13:41:32+00:00
- Post Title: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: Kunigunde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 22, 2010 1:20 pm
- Post datetime: 2010-06-06T20:49:31+00:00
- Post Title: Re: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

This tutorial is outdated. There is no (no need) nifgmax.exe in the latest releases. Copy dlu and dlls (NifMagic.dll and NifMopp.dll) in “plugins” folder ini in “PlugCFG” folder (edit it if you wish, paths etc.); start gMax as usual from original gmax.exe. 

Sometimes (Divinity 2) nifs do not contain skeleton structure but do contain bones and skin information. Skeleton is stored in another file. So, copy/paste NiTriStrips/ NiTriShape mesh nodes on corresponding bone nodes of skeleton nif in NifScope before importing in Max/gMax.

Usually nif skeletons should be imported first in a Max/gMax scene. Than meshes or kf animations. When you receive a mess try to save and reload Max/gMax scene.

In general such settings are usually working (use suitable nif version format game settings):
[http://i109.photobucket.com/albums/n45/ ... Export.jpg](http://i109.photobucket.com/albums/n45/AxelIP/MWMaxImportExport.jpg)
Sometimes it is necessary to check “Extra Nodes on Mesh” (animations). 

Oblivion like nifs (complete skeleton is stored in a separate nif) and a “Bip01 NonAccum” node present other settings should be used (compare your nifs and some OB ones). I would assemble a complete model in NifScope before gMax import. Havok, collision is another story.
Note that there could be problems in gMax in case skinning pose is wrong (in Max and Blender that can be fixed).
## Post #17
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-07T01:03:05+00:00
- Post Title: Re: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

> Reply from Kunigunde
>
> This tutorial is outdated. There is no (no need) nifgmax.exe in the latest releases. Copy dlu and dlls (NifMagic.dll and NifMopp.dll) in “plugins” folder ini in “PlugCFG” folder (edit it if you wish, paths etc.); start gMax as usual from original gmax.exe. 

Sometimes (Divinity 2) nifs do not contain skeleton structure but do contain bones and skin information. Skeleton is stored in another file. So, copy/paste NiTriStrips/ NiTriShape mesh nodes on corresponding bone nodes of skeleton nif in NifScope before importing in Max/gMax.

Usually nif skeletons should be imported first in a Max/gMax scene. Than meshes or kf animations. When you receive a mess try to save and reload Max/gMax scene.

In general such settings are usually working (use suitable nif version format game settings):
http://i109.photobucket.com/albums/n45/ ... Export.jpg
Sometimes it is necessary to check “Extra Nodes on Mesh” (animations). 

Oblivion like nifs (complete skeleton is stored in a separate nif) and a “Bip01 NonAccum” node present other settings should be used (compare your nifs and some OB ones). I would assemble a complete model in NifScope before gMax import. Havok, collision is another story.
Note that there could be problems in gMax in case skinning pose is wrong (in Max and Blender that can be fixed).

Very insightful, thanks!

The Issue with Importing the Skeletons is that they are .skt files.  I am unsure of how to Import those.  Hopefully there is a way to do so, but until then I'll just Copy the Mesh to another file and adjust that file's Skeleton to fit the Pasted Mesh.  The real Issue is the Texture.  For some reason, Importing into GMax removes the Texture Mapping from the .mgn Mesh files.  I'm very hopeful for a Solution to this Issue. 

Thanks for the Post!
## Post #18
- Username: Kunigunde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 22, 2010 1:20 pm
- Post datetime: 2010-06-08T00:38:31+00:00
- Post Title: Re: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

Sorry, I have never worked with .skt files.
## Post #19
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-08T06:32:13+00:00
- Post Title: Re: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

Hey Jeremonster, I tested your mgn file in gamx and all the UVs and texture are fine!!!
Maybe you don't know how to show it up in gmax's viewport!?

In the material editor, click "New" for a new material and click on the little box next to diffuse color box, a select box show up and select bitmap, then select your texture file(If you have nif plugins installed, you can use dds directly). Select your mesh object by clicking on it, go back to material editor and press "Apply". Now press the little checker box(like in my picture with a yellow circle) and the texture will show.

If you want to make sure the UV are Ok. Select your mesh object, goto modify panel. From the drop down list box select "Unwarp UVW". And press "Edit". you will see something like in my picture.
[SWG.jpg](https://xentaxbackup.github.io/file/3121_SWG.jpg)
## Post #20
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-08T13:21:59+00:00
- Post Title: Re: 3d Model Conversion: .mgn to .nif (SWG - ZT2)

> Reply from fatduck
>
> Hey Jeremonster, I tested your mgn file in gamx and all the UVs and texture are fine!!!
Maybe you don't know how to show it up in gmax's viewport!?

...

Wow!

Thanks so much!

You were right, I'm not very experienced with GMax.  You've helped me out a lot!  I've not only been able to get the Blistmok to Load properly in GMax, but I've also been messing around with the Nif in NifSkope!  Here's a Shot of it:



I'm working on trying to get it into Zoo Tycoon 2 right now, we'll see how good my skills are.  I'll update you guys when I do!

Thanks everyone!
