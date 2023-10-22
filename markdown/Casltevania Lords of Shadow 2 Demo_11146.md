## Post #1
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-01-19T16:39:43+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Thanks to Ekey for the Castlevania LOS 2 Demo ".packed" archive [script](http://forum.xentax.com/viewtopic.php?f=10&t=5102&start=45). The textures are just plain old .dds files. The models have been changed somewhat from Castlevania LOS format.

Here is a link to some of the .msh files from the characters and levels. Support in Noesis would be unbelievably cool.  The files are from the XBox360 version for no other reason than it was easier to get. The PS3 and Xbox archives are about the same size so I'm guessing there's not much difference in the texture resolutions.

[http://www.sendspace.com/file/mz2osp](http://www.sendspace.com/file/mz2osp)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-02-01T20:50:46+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

I added the Mercury Steam Engine 2  (Castlevania: Lords of Shadow 2) *.MSH loader module to the 3D Object Converter and I uploaded this version to my web page:

[http://3doc.i3dconverter.com/downloads/ ... rtable.zip](http://3doc.i3dconverter.com/downloads/3doc_v5.308_portable.zip)

I did not find the material assignments, but my loader program generates a default material to all subobjects.


You can add the texture file to the material table by hand using the following procedure:
- open the .msh file
- click on the Object, Bone, Material selector on the toolbar (from right the 1st icon on the toolbar)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK

- (Click on the textured view icon.)
## Post #3
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-02-03T16:07:35+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Excellent work, thanks Karpati. I have tested the updated 3D Object Converter and a few of the levels give a "stream read" error or loading, but it works perfectly with all of the character/object models. Thanks!!
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-02-03T19:34:35+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

I did not know that your sample file package have several .msh files in the levels directory.
I did find an unhandled vertex format and I modified my .msh loader module a little bit.

[http://3doc.i3dconverter.com/downloads/ ... rtable.zip](http://3doc.i3dconverter.com/downloads/3doc_v5.309_portable.zip)
## Post #5
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-02-05T00:10:32+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Fantastic, works perfectly!! thanks again Karpati
## Post #6
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-02-28T07:02:46+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

> Reply from Karpati
>
> I did not know that your sample file package have several .msh files in the levels directory.
I did find an unhandled vertex format and I modified my .msh loader module a little bit.

http://3doc.i3dconverter.com/downloads/ ... rtable.zip

This plugin don't work for final version. Did you can update it?
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-02-28T07:34:09+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

> Reply from erik945
>
> This plugin don't work for final version. Did you can update it?

I don't have this game, but can you send some sample .msh files to [3dconverter@gmail.com](mailto:3dconverter@gmail.com) ?
## Post #8
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-02-28T13:21:15+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Hi Karpati, I have sent you a pm
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-28T13:40:57+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Can someone send me model samples from final PC version of the game? I wrote maxscript with bones+weights support for final PS3/Xbox 360 versions of the game, I want to check PC version too. Thanks
## Post #10
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-02-28T15:39:57+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

> Reply from Karpati
>
> erik945 wrote:This plugin don't work for final version. Did you can update it?

I don't have this game, but can you send some sample .msh files to 3dconverter@gmail.com ?

send to e-mail (PC version).

For all:
[http://www.sendspace.com/file/69bfbb](http://www.sendspace.com/file/69bfbb)
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-02-28T16:42:17+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Zardalu, Erik945

Thank you for your great sample files.

I tracked down what was the problem:
The XBOX and the PC version are using different byte order in the .msh files (it is a simple, but classical problem.)

I modified my .msh loader module a little bit and I uploaded it to my web page:
[http://3doc.i3dconverter.com/downloads/ ... rtable.zip](http://3doc.i3dconverter.com/downloads/3doc_v5.310_portable.zip)
## Post #12
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-02-28T17:20:13+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Thank you very much!
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-28T18:59:29+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

Thanks a lot for PC samples, works great. Format is the same as for Xbox-360/PS3 versions  As Karpati said, PC version just using different byte order
[Dracul.jpg](https://xentaxbackup.github.io/file/7053_Dracul.jpg)
## Post #14
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-02-28T19:11:58+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

> Reply from zaramot
>
> Thanks a lot for PC samples, works great
Good!
When you plan release script?
p.s. and, if you can, for Dragon's Dogma.
## Post #15
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2014-03-08T12:43:13+00:00
- Post Title: Casltevania Lords of Shadow 2 Demo

> Reply from Karpati
>
> Zardalu, Erik945

Thank you for your great sample files.

I tracked down what was the problem:
The XBOX and the PC version are using different byte order in the .msh files (it is a simple, but classical problem.)

I modified my .msh loader module a little bit and I uploaded it to my web page:
http://3doc.i3dconverter.com/downloads/ ... rtable.zip


Is this possible to do for LOS2? it works for los1, reverie and ressurection ps3 files! As you can see you did this once and this is a really nice feature. I requested this a long time ago! In LOS2 almost all dds textures are located in other folders than the model foldres so its hard to track down dds files, but in this way it is easy to see exactly what the name of the dds texture file is. if this is possible to make again, then, please make it so. Thank You!!!
[Untitled-1.jpg](https://xentaxbackup.github.io/file/7082_Untitled-1.jpg)
## Post #16
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2014-03-10T15:00:24+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

as enyone found a way to import level models from los2 in the correct spots? for example where things should be placed and/or oriented? And one other thing, how to know exactly witch level models to import to complete a specific level?
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-15T09:21:59+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Hi guys! Here's maxscripts to import Casltevania Lords of Shadow 2 models with bones (3ds max 2009-2011). 
Don't try it on stages, script is for models from "chars" folder. Report errors here, PS3/Xbox-360 and PC version supported

[](http://piccy.info/view3/6068004/1ad37419707bb3006aa4208c4fc47c8b/orig/)[](http://i.piccy.info/a3c/2014-03-15-09-21/i9-6068004/744x574-r)
[LOS2_SCRIPTS.7z](https://xentaxbackup.github.io/file/7105_LOS2_SCRIPTS.7z)
## Post #18
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2014-03-15T18:34:48+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Using it with 3DS max 2011 but getting na error on:

		str += bit.intAsChar (ReadByte bstream #unsigned)

This on the chars folder as advised...
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-15T18:42:30+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

PC, Xbox or PS3? And tell me which model gives an error.
## Post #20
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2014-03-16T13:37:38+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

[quote="zaramot"]PC, Xbox or PS3? And tell me which model gives an error.[/quote]


PC
Model: Dracula
error:" str += bit.intAsChar (ReadByte bstream #unsigned)"


3dsmax2012
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-16T13:41:01+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Send me PC models which doesn't work without textures here or via PM, I don't have PC version to test. Thanks

Edit:
Good news, I tried Dracula PC model, it's an issue with skeleton (not with model )- it's a bit different than consoles have (some extra data), I used skeleton from console version and model imported very well. So, I will fix this soon, keep report problems especially with PC version, since I didn't have much model from there.

Edit2:
Fixed issue with PC Dracula model, but I would like kindly ask for more PC model+skeleton samples to test script (without textures). Thanks
## Post #22
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-17T10:00:42+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Here's fixed maxscript for PC version of the game. Thanks to kalrua for providing samples, I tried them all and they imported fine. 
Also I can't try script with 3ds max 2012, I have only 2009-2011 version, so please report will it work or not.

Edit: Fixed double-scaled UV's

[](http://piccy.info/view3/6078808/2ad83592a12535ff92256dae6c12181f/orig/)[](http://i.piccy.info/a3c/2014-03-17-09-58/i9-6078808/744x574-r)
[LOS_2_PC.7z](https://xentaxbackup.github.io/file/7104_LOS_2_PC.7z)
## Post #23
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2014-03-17T15:07:22+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

3dsmax2012, Pc_version

-UV error: 2*scale size.
Marie:
[url=[http://tof.canardpc.com/view/811f9833-a ... 77b8b1.jpg](http://tof.canardpc.com/view/811f9833-a9e4-4736-8972-79ee4b77b8b1.jpg)][img][http://tof.canardpc.com/preview2/811f98 ... 77b8b1.jpg](http://tof.canardpc.com/preview2/811f9833-a9e4-4736-8972-79ee4b77b8b1.jpg)[/img][/url]

[http://tof.canardpc.com/view/811f9833-a ... 77b8b1.jpg](http://tof.canardpc.com/view/811f9833-a9e4-4736-8972-79ee4b77b8b1.jpg)
## Post #24
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2014-03-17T21:36:46+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

For me this script doesn't work..  i can only import Dracula (wrong weights)  and Dracula RAT  that's all  please fix your script 

the error i have with 99% of the models:
## Post #25
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-18T07:26:01+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Okay, thanks for the bug report. What about you Kalrua? You reported about Uv's error for Marie model, so I guess you managed to import her. Could you confirm script isn't working for 99% of models and about wrong weights?
## Post #26
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2014-03-18T10:24:35+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

> Reply from zaramot
>
> Okay, thanks for the bug report. What about you Kalrua? You reported about Uv's error for Marie model, so I guess you managed to import her. Could you confirm script isn't working for 99% of models and about wrong weights?

well.. i think i used the wrong bms script to extract the packages.. sorry     now all the model are imported correctly and with all correct weights..  just a problem (that i can easy fix myself) the character eyes and teeth are imported away from the mesh..  The eyes on the 3dmax grid and the teeth a lot above the mesh  if you can fix this little issue the script is perfect..  anyway thank you very much for this.
## Post #27
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2014-03-18T13:36:12+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

[quote="zaramot"]Okay, thanks for the bug report. What about you Kalrua? You reported about Uv's error for Marie model, so I guess you managed to import her. Could you confirm script isn't working for 99% of models and about wrong weights?[/quote]

Imported  with all correct weights, for me.

-Smooth group/cutting Error:
[http://tof.canardpc.com/view/151b8e6a-a ... 2b2c56.jpg](http://tof.canardpc.com/view/151b8e6a-a023-464d-b399-07ff5d2b2c56.jpg)
## Post #28
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2014-04-03T13:12:56+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Hi!

fix for Uv PC
Change
[code]append UV_array([value,value,0]*2)[/code]

To

[code]append UV_array([value,(value + 1),0]*1)[/code]

For levels, I do not know.
## Post #29
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2014-04-07T18:31:04+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Anyone knows if this orange map is a tangent space normal map or if it really is something else?
Maybe object space normal or maybe a "flipped" tangent space normal and so because of that it is orange?
This is from los2 dlc (content 4 .packed).
[texture_files.zip](https://xentaxbackup.github.io/file/7188_texture_files.zip)
## Post #30
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-04-08T18:49:04+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Yes, it's a tangent space normal map. If you want it to resemble a "normal" normal map, then take the alpha channel from that image and move it into the red channel. The green channel can stay where it is. I use GIMP 2 for this, (colors -> decompose/compose).  Usually you can leave the blue channel plain white.
## Post #31
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2014-04-21T12:59:08+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

> Reply from zardalu
>
> Yes, it's a tangent space normal map. If you want it to resemble a "normal" normal map, then take the alpha channel from that image and move it into the red channel. The green channel can stay where it is. I use GIMP 2 for this, (colors -> decompose/compose).  Usually you can leave the blue channel plain white.

Another thing: do you know where the dlc contents for "dracula dark skin" and "armored dracula" are? could not find them. not yet at least. if you load dracula model then the meshes for the armored version is there but where to find the textures and all? the same goes for the dark skin. it's not the same textures as it looks like.


And yet another thing comes to mind: what about the e-maps how to best feed those into a shader? normaly there is a "d" for color, a "n" for normal map, a "s" for a specular map. the "b" maps can be used as normal maps as well as like you said they where tangent space normal maps as well. all good but what about those "E" maps? they are king of greenish as well, are those some kind of different specular maps?

Thank you for your time in advance!!...
## Post #32
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-06-21T11:51:22+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

Hi everyone, I've made small plugin for GIMP to convert CLoS2 bump maps. 

The plugin will convert any bump map from CLos2, so it will swap Red and Alpha channels, inverts Blue channel and make result texture.
I believe the red channel is used for specular maps so its in alpha channel as usual.
Same process go reversed, convert normal bump map to CLoS2 color format.

Installation: Put my script to GIMP 2\lib\gimp\2.0\plug-ins\. (Folder ussually stored in "Program Files" or "Program Files (x84)" or where you have it installed)

Usage: In window where you have your bump map navigate to P Tools tab and click on Castlevania LoS 2 Texture Tools.
GIMP will make 4 temp textures and result texture.
[ppc_clos2_texturetools.zip](https://xentaxbackup.github.io/file/7498_ppc_clos2_texturetools.zip)
## Post #33
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-06-22T13:51:31+00:00
- Post Title: Re: Casltevania Lords of Shadow 2 Demo

> Reply from PredatorCZ
>
> Hi everyone, I've made small plugin for GIMP to convert CLoS2 bump maps. 

The plugin will convert any bump map from CLos2, so it will swap Red and Alpha channels, inverts Blue channel and make result texture.
I believe the red channel is used for specular maps so its in alpha channel as usual.
Same process go reversed, convert normal bump map to CLoS2 color format.

Installation: Put my script to GIMP 2\lib\gimp\2.0\plug-ins\. (Folder ussually stored in "Program Files" or "Program Files (x84)" or where you have it installed)

Usage: In window where you have your bump map navigate to P Tools tab and click on Castlevania LoS 2 Texture Tools.
GIMP will make 4 temp textures and result texture.

Nice work!!
