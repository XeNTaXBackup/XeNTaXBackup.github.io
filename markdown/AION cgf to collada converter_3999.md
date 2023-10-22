## Post #1
- Username: microkong
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 16, 2009 10:13 pm
- Post datetime: 2009-12-29T15:42:41+00:00
- Post Title: AION cgf to collada converter

* Convert AION mesh, skin and animation to .dae
* Running on python 2.5/2.6
* Modify the path and mesh/animation name in the aion2collada.py
* Use RPGViewer to unpack the aion pak
* The .dae can be imported to 3dsmax9 using OpenCOLLADA 3ds Max Plugin 1.2.5
* The code is base on cgf reader in PyFFI 2.0.5 and collada writer in Collada Blender 0.3.159
[aion2collada.zip](https://xentaxbackup.github.io/file/2676_aion2collada.zip)
## Post #2
- Username: microkong
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 16, 2009 10:13 pm
- Post datetime: 2009-12-29T15:50:50+00:00
- Post Title: AION cgf to collada converter

screen shot
[.jpg](https://xentaxbackup.github.io/file/2679_.jpg)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-29T18:40:52+00:00
- Post Title: AION cgf to collada converter

Nice! you should post this also at the Game Tools forum
## Post #4
- Username: Jaggedge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 18, 2009 1:00 am
- Post datetime: 2010-01-27T14:24:51+00:00
- Post Title: AION cgf to collada converter

Hi I'm having a little trouble following the steps here, could you explain in a little more detail?

I have RPGViewer30Build1024, and a bunch of AION files, such as 
shugofemale_Animations.pak
shugofemale_Meshes.pak
shugofemale_Textures.pak

What should I do first? I'm not sure how to use RPGViewer to unpack the pak files..
## Post #5
- Username: microkong
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 16, 2009 10:13 pm
- Post datetime: 2010-02-02T14:19:47+00:00
- Post Title: AION cgf to collada converter

File->Open->Online Games->(NcSoft) AION-永恒之塔
And then set the game path. 
It will list all the .pak in that path to the tree. Select the pak and use Addon->Archive->Extract...
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-02T16:50:08+00:00
- Post Title: AION cgf to collada converter

sorry, I have read this thread before and it is among the etiqutte to actually thank creators so here you go: Thank you 

A great tool indeed. Wish it could be imported directly to max with script but this will absolutly do for now
## Post #7
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-02-17T18:16:15+00:00
- Post Title: AION cgf to collada converter

how do you use this converter? When I modify the paths and run it, look what happens:

```
Adding Mesh lf001_head
No handlers could be found for logger "pyffi.cgf.data"
Traceback (most recent call last):
  File "C:\Users\Edvinas1\Desktop\Downloads\aion2collada\aion2collada\aion2colla
da.py", line 876, in <module>
    ConvertMeshAnimation("")
  File "C:\Users\Edvinas1\Desktop\Downloads\aion2collada\aion2collada\aion2colla
da.py", line 826, in ConvertMeshAnimation
    converter.AddMesh(name, r"%s\%s.cgf" % (meshPath, name))
  File "C:\Users\Edvinas1\Desktop\Downloads\aion2collada\aion2collada\aion2colla
da.py", line 133, in AddMesh
    self.ReadCgf(cgfPath)
  File "C:\Users\Edvinas1\Desktop\Downloads\aion2collada\aion2collada\aion2colla
da.py", line 112, in ReadCgf
    self.data.read(stream)
  File "C:\Users\Edvinas1\Desktop\Downloads\aion2collada\aion2collada\pyffi\form
ats\cgf\__init__.py", line 778, in read
    if not chunkhdr.version in chunk.getVersions(self.game):
  File "C:\Users\Edvinas1\Desktop\Downloads\aion2collada\aion2collada\pyffi\obje
ct_models\xml\Struct.py", line 472, in getVersions
    return cls._games[game]
KeyError: 'Aion'
```


Anyone tried converting and succeeded? What am i doing wrong?

thanks
## Post #8
- Username: microkong
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 16, 2009 10:13 pm
- Post datetime: 2010-03-23T14:41:57+00:00
- Post Title: AION cgf to collada converter

Can you post your "lf001_head.cgf"?  Your AION may be a different version.
## Post #9
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2010-05-01T21:00:23+00:00
- Post Title: AION cgf to collada converter

I have extract CFG but i dont understand why to convert CFG to DAE
## Post #10
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-05-02T18:47:52+00:00
- Post Title: AION cgf to collada converter

I have some problems to converting because I don't know all the places to edit the file 

And, it seems we need to extract the cgf files in the aion install dir right? I have the cgf files in another place right now
## Post #11
- Username: Kunigunde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 22, 2010 1:20 pm
- Post datetime: 2010-05-23T23:49:24+00:00
- Post Title: AION cgf to collada converter

It would be nice to convert Aion models to official cryengine 1 format: it can be imported with “Takaro CryImporter script, version 1.2.1, “imports geometry and animation from Crytek CGF, CGA, CAF and CAL files into 3ds max 7 or above”:

[http://www.takaro.net/downloads.html](http://www.takaro.net/downloads.html)

The hope is that using official Max exporter from cryengine_mod_sdk_v1.4 it would be possible to bring these models back in the game.
## Post #12
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-07-11T07:36:39+00:00
- Post Title: AION cgf to collada converter

I think this post its fake, i try all the ways, and i think he make the skeletal meshes and rip the model in the screenshot with 3d ripper or 3d via printscreen, the py files to converto to dae not works nothink, in the steps you tell this
and all the people ask you something problems and you not give answer, i dont know why.
to adde other bad point you tell this in the steps.

* Modify the path and mesh/animation name in the aion2collada.py? yes edit edit, where man? wath lines? have you something screenshots?
## Post #13
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-07-11T14:28:20+00:00
- Post Title: AION cgf to collada converter

I have not been able either but in the PY far down there is lines about paths etc. You just have to look. I do not believe it's fake, it's just you and me who are stupid
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-07-11T16:54:49+00:00
- Post Title: AION cgf to collada converter

> Reply from Kunigunde
>
> It would be nice to convert Aion models to official cryengine 1 format: it can be imported with “Takaro CryImporter script, version 1.2.1, “imports geometry and animation from Crytek CGF, CGA, CAF and CAL files into 3ds max 7 or above”:

http://www.takaro.net/downloads.html

The hope is that using official Max exporter from cryengine_mod_sdk_v1.4 it would be possible to bring these models back in the game.

Absolutely fake, the Takaro CryImporter script, version 1.2.1 not import geometry files CGF, CGA, CAF from Aion, in max 7 i try and i give this message winndow ¨NOT A VALID CRYTEK FILE¨
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-11T18:25:16+00:00
- Post Title: AION cgf to collada converter

This script works fine it just needs some manual editing in a few places.
## Post #16
- Username: Kunigunde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 22, 2010 1:20 pm
- Post datetime: 2010-07-11T22:22:17+00:00
- Post Title: Re: AION cgf to collada converter

```
Absolutely fake
```


Aion uses modified (not original) CryEngine 1 files that could be also encrypted. 
But can Aion “understand” original CryEngine 1 format? In case “yes”, official exporter can be used.
Chrrox, how to modify the files?

Thanks.
## Post #17
- Username: Kunigunde
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-11T22:43:25+00:00
- Post Title: Re: AION cgf to collada converter

they modified the material data slightly other then that its just the first few bytes of the header one says crysis or soemthing and the other says aion if you change it you can use any crytec importer.
## Post #18
- Username: Kunigunde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 22, 2010 1:20 pm
- Post datetime: 2010-07-14T00:35:38+00:00
- Post Title: Re: AION cgf to collada converter

That works, many thanks. But materials are not imported.
## Post #19
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-09-10T00:39:43+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from Kunigunde
>
> That works, many thanks. But materials are not imported.
Works? can you please post a screenshots step by step how this works??? thanks.
## Post #20
- Username: deronar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 04, 2010 10:27 pm
- Post datetime: 2010-09-22T17:32:50+00:00
- Post Title: Re: AION cgf to collada converter

Thank you very much everything works great! It works even with animation - it's just a gift for me!
## Post #21
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-09-30T21:38:03+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from deronar
>
> Thank you very much everything works great! It works even with animation - it's just a gift for me!

Deronar can you post how this works, it try all the ways and not works for me and other users.
can you make screenshots of wath places need edit in the .cfg files?
## Post #22
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2010-10-12T08:31:44+00:00
- Post Title: Re: AION cgf to collada converter

Any solution for the morphs target ?
## Post #23
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-09T23:15:42+00:00
- Post Title: Re: AION cgf to collada converter

Tried to use this script, I've changed the header of cgf file, but there is error

raise ValueError("Invalid File Type.")
ValueError: Invalid File Type

?
## Post #24
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-10T10:18:13+00:00
- Post Title: Re: AION cgf to collada converter

Or maybe someone who sucessfully used this script will help....what exactly need to be changed in header?
I tried to change first six bytes in Hexeditor to CMAion or CryTek, but that doesn't help.
Or maybe the problem is in verson of the game, say on what version it was sucessfully converted.
## Post #25
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2010-11-10T13:24:00+00:00
- Post Title: Re: AION cgf to collada converter

ok guys great thread
 i was able to extract the files using rpg viewer but how do i bring the files into max with animation. I tried the scripts but they don't seem to run
## Post #26
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-10T13:52:27+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from jin76
>
> ok guys great thread
 i was able to extract the files using rpg viewer but how do i bring the files into max with animation. I tried the scripts but they don't seem to run

A s you see i also have a problem with script...do you have the same error as in my case, or you have another obstacle?.
## Post #27
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2010-11-11T19:02:25+00:00
- Post Title: Re: AION cgf to collada converter

actually the script does not run at all

btw Mr. Mouse how did u get it to work. can you please share the method
## Post #28
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2010-11-13T18:30:43+00:00
- Post Title: Re: AION cgf to collada converter

I have a .cgf file, and now? i dont understand convert .cgf to collada for open in 3d max.
## Post #29
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-13T20:45:54+00:00
- Post Title: Re: AION cgf to collada converter

Maybe someone who succeed with this script can upload some cgf file that works with script, to understand where the problem is - in script or in cgf.  I think that maybe the problem is in game version. I tried two version of Aion 2.0 and 1.5.1.4 (i couldn't find older versions) and both doesn't work...it gives me the same error message "Invalid File Type". 

Here is one of my cgf files
[http://www.multiupload.com/E0KJL8K9IB](http://www.multiupload.com/E0KJL8K9IB)
## Post #30
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-14T09:31:04+00:00
- Post Title: Re: AION cgf to collada converter

Hi, At last i solved my problem with script.
The problem was not in the version of the game and not in the script, the problem was in Unpacker. I used RPGViewer to extract cgf from .Pak files, it show no errrors, extracted files but this files i think was with encrypted header, about 30 first bytes of every files was wrong. So, when i tried to use the unpack tool from this topic [viewtopic.php?f=10&t=2848&p=32129&hilit=aion#p32129](http://forum.xentax.com/viewtopic.php?f=10&t=2848&p=32129&hilit=aion#p32129) everything gone well.

I don't even think taht problem was in unpacking  ...

P.S. And one more, this wasn't worth spended time, the models are dull and rough, who want some interesting models better to try LA2 for example...and sorry for my bad english
## Post #31
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2010-11-14T20:38:55+00:00
- Post Title: Re: AION cgf to collada converter

yes i was also able to get the cgf files but am stuck at that part. I am pretty sure there must be a program that can export these files to max or something
## Post #32
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-14T20:58:52+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from jin76
>
> yes i was also able to get the cgf files but am stuck at that part. I am pretty sure there must be a program that can export these files to max or something

This program is python script that is attached in first post. But as i wrote be sure that you have right cgf files couse firse i also thouth that i had cgf files, but the problem was in them. Don't use RPGviewer to unpak archives.
Then use the script from the first post, but you must manually edit all the paths to files, and create output folder (the script cannot create it by itself)
## Post #33
- Username: fewks
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 28, 2010 6:05 pm
- Post datetime: 2010-12-15T16:40:34+00:00
- Post Title: Re: AION cgf to collada converter

dunno if anyone still interested in it, but i imported models into 3ds max with CryImporter, it have bones and skin but, i cannot import animation . When im trying to open animation - it changes timeline but no animation appears. Does anyone have the same problem? maybe you know how to solve it
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-12-15T17:20:00+00:00
- Post Title: Re: AION cgf to collada converter

I think animations are internal and made by AION so it cannot be imported. It is not standard so someone needs to figure it out separatly
## Post #35
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-06T12:56:39+00:00
- Post Title: Re: AION cgf to collada converter

The contents of this post was deleted because of possible forum rules violation.



Update: 2014-12-08
Aion Blender importer.
It requires Blender version 249 and Python 26

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select cgf file for meshes and skeleton
3.for animation press alt+p and select caf file
[Blender249[AionOnline][cgf][caf][2014-12-08].zip](https://xentaxbackup.github.io/file/8216_Blender249[AionOnline][cgf][caf][2014-12-08].zip)
## Post #36
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-21T20:57:44+00:00
- Post Title: Re: AION cgf to collada converter

To be honest Szkaradek123, this its one of the best contributions i see in the last 6 months man here in xentax man, congratulations.
## Post #37
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2011-02-22T16:32:52+00:00
- Post Title: Re: AION cgf to collada converter

great work   

sorry for my stupid question but can you tell me how i can run this in blender. I have never used blender before and have been trying to get this to work for long time but i am unable to do so. I installed blender 2.49b and python 2.6.1 and each time i try to open the .blend file i am unable to see the code or run the script i am getting some machine code. Please help 


edit 1

ok now i am able to import the script in but keep getting the error "Convert Game Engine script from 4.48 API to 2.49 API" and which wont go away
can some one help
## Post #38
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2011-02-22T21:00:54+00:00
- Post Title: Re: AION cgf to collada converter

Szkaradek123 great work, thanks.
But is it possible to see something like this script for 3ds Max?
## Post #39
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2011-03-20T08:04:41+00:00
- Post Title: Re: AION cgf to collada converter

Nice Blender script.
It would be great if the script supports the latest version of "Blender 2.56a" and latest "Python 3.2"
## Post #40
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2011-03-20T15:33:17+00:00
- Post Title: Re: AION cgf to collada converter


## Post #41
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-07-16T01:20:14+00:00
- Post Title: Re: AION cgf to collada converter

trying this out to now on blender 2.49 and python 2.6.2. I get this error:

```
File "aion importer.py", line 507, in bevent
File "aion importer.py", like 172 in read_cgf_data
AttributeError: 'MtlChunk' object has no attribute 'texD'
```


This I get with the example models provided and also others
## Post #42
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-23T19:28:53+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from Axolotl
>
> Szkaradek123 great work, thanks.
But is it possible to see something like this script for 3ds Max?

Its not posible i think cause its more dificulty make this for max.
## Post #43
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-23T19:39:23+00:00
- Post Title: Re: AION cgf to collada converter

its possible someone just has to have interest to do it.
## Post #44
- Username: kylem
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 27, 2011 9:31 am
- Post datetime: 2011-08-27T20:01:39+00:00
- Post Title: Re: AION cgf to collada converter

pixellegolas, you're not alone..... I got the same error w/ blender 2.49b using python 2.6.6
## Post #45
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-27T22:56:00+00:00
- Post Title: Re: AION cgf to collada converter

If someone provides a max import template then more people would probably volunteer to write one.
## Post #46
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-27T23:30:51+00:00
- Post Title: Re: AION cgf to collada converter

I already did in the tutorial section.
## Post #47
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-27T23:38:43+00:00
- Post Title: Re: AION cgf to collada converter

Maybe people didn't notice it. It doesn't seem like tutorial section gets a lot of views.
Or at least, I'd expect more questions if people were actually interested but don't know what to do.
## Post #48
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-28T00:10:54+00:00
- Post Title: Re: AION cgf to collada converter

most people 99% just want people to do it for them.
## Post #49
- Username: person123456
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 03, 2011 11:21 am
- Post datetime: 2011-09-13T04:08:33+00:00
- Post Title: Re: AION cgf to collada converter

can someone tell us exactly what the "NCAion" in the header needs to be changed to in order for us to import this using the crytek importers? thx
## Post #50
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-09-20T00:18:00+00:00
- Post Title: Re: AION cgf to collada converter

Does RPG viewer really support AION animation extraction? I mean, I extracted part of the Monsters models and such, but then my drive filled up and the extraction stopped without completing, so I am not sure if the animations were extracted or not. Right now, I am not the position to check my personal computer for a week.

If RPG viewer does support animation extraction, how do I get the animations and textures to view with the models? Neosis didn't seem to open the cfg files that extracted (amoung other non-supporting files). And it says the models are supposed to be extracted in dae format! Why didn't RPGviewer make it so?

EDIT: Okay... so this is aiontocollada... haven't gotten that far yet.

What should I use to extract AION models, animations, and such, and should I use the tool on the last page to convert it... or open it as the picture nearby shows (if that is the tool...)

Or is that blender in the picture? Does that mean animations are actually possible with AION files so far??
## Post #51
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T16:15:59+00:00
- Post Title: Re: AION cgf to collada converter

Try with Blender and it should work, with animations and all. I had really really big trouble to actually get it working first but I had to uninstall piffy I think and also get rid of it from registry.

If you have a clean blender 2.49 and python 2.6 you should be able to get it to work. But just uninstalling pyffi does not work. It still keeps some reference in registry
## Post #52
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-09-20T18:57:58+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from pixellegolas
>
> Try with Blender and it should work, with animations and all. I had really really big trouble to actually get it working first but I had to uninstall piffy I think and also get rid of it from registry.

If you have a clean blender 2.49 and python 2.6 you should be able to get it to work. But just uninstalling pyffi does not work. It still keeps some reference in registry

I do not have python. How do I get it?
## Post #53
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T19:09:17+00:00
- Post Title: Re: AION cgf to collada converter

[http://www.python.org/getit/releases/2.6/](http://www.python.org/getit/releases/2.6/)

I think it is a good idea to actually use the 2.6 and not 2.6.6 witch is newer
## Post #54
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-09-20T19:28:28+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from pixellegolas
>
> http://www.python.org/getit/releases/2.6/

I think it is a good idea to actually use the 2.6 and not 2.6.6 witch is newer

What's wrong with 2.6.6? I really like keeping up to date, so I need to know the setbacks of 2.6.6. that come with the bug fix. What exactly was the bug fix?
## Post #55
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T23:03:06+00:00
- Post Title: Re: AION cgf to collada converter

I don't know if it works with 2.6.6 but I had alot of problem so I backtracked by uninstalling everything and cleaning registry. I then downloaded blender 2.49 + pythong 2.6. Mainly because the script was written for that combo. Might work for 2.6.6 to
## Post #56
- Username: AiramCruz™
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 17, 2011 2:30 am
- Post datetime: 2011-10-22T07:53:14+00:00
- Post Title: Re: AION cgf to collada converter

ola sou novo no forum.
tentei modificar o script do topico principal mais nao obtive sucesso.
ai tentei o do Szkaradek123  e nao conseguir abrir no Blender.
Sera que alguem poderia postar onde devo modificar o script do topico princial ou algum outro script que funcione ?
Print do script do Szkaradek123  :
## Post #57
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-27T03:52:46+00:00
- Post Title: Re: AION cgf to collada converter

here is a english forum so don't put other languages!!! read forum rules!!!
## Post #58
- Username: s25jin
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 15, 2011 1:11 am
- Post datetime: 2012-02-17T22:55:43+00:00
- Post Title: Re: AION cgf to collada converter

The contents of this post was deleted because of possible forum rules violation.
## Post #59
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-01-22T00:15:16+00:00
- Post Title: Re: AION cgf to collada converter

> .. can someone tell us exactly what the "NCAion" in the header needs to be changed to..

"NCAion" needs to be changed to "CryTek".
## Post #60
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-01-24T10:54:38+00:00
- Post Title: Re: AION cgf to collada converter

Pes have you been able to make this work? need some guidance man
## Post #61
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-01-24T16:46:43+00:00
- Post Title: Re: AION cgf to collada converter

In order to use CryImporter v1.2.1, you need to use a hex-editor to change the first six bytes in a model file from "NCAion" to "CryTek".

Apart from that, I don't know how to edit the CryImporter script(s) for proper materials import. chrrox might shed a light on that.

<Edit>
( also read: [http://niftools.sourceforge.net/forum/v ... f=7&t=2383](http://niftools.sourceforge.net/forum/viewtopic.php?f=7&t=2383) ).
## Post #62
- Username: Jopsi332
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 14, 2014 12:37 am
- Post datetime: 2014-02-13T21:59:27+00:00
- Post Title: Re: AION cgf to collada converter

hi
i'm new to this blender stuff.
How to run this script?
When i try to install it as addon nothing appears
## Post #63
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-02-13T23:09:41+00:00
- Post Title: Re: AION cgf to collada converter

I've never used it, but the author suggests it is a stand-alone tool. According to the brief instructions, there are some modifications required in the aion2collada.py file (likely near the end starting at line 831) to adapt it to your file locations and names. It looks like aion2collada.py can be run from the command line to perform the desired operation once you have set your paths and names.
## Post #64
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-02-14T16:03:21+00:00
- Post Title: Re: AION cgf to collada converter

You have to install Python first. I think only v2.5 or v2.6 (I installed Python v2.6.6).

Then running the script is very easy: start a command prompt, navigate to the location of the Aion2Collada.py file and simply type "Aion2Collada.py".

BUT (!): befor you run it, you must edit this script in a text editor.
Browse to the end of the script, and you will see a listing of directories and model files.
You need to change those directories, so that everything corresponds to your Aion set-up on your HDD.

Fiddle a bit with this to get the proper script set-up.
Whenever you get errors, read them closely to find out what (other) directories or files you need to configure / remove.

You might also have to put a '#' in front of the very last line where it says "ConvertMeshAnimation("..")".

I've tested this with a few Aion 4.0 models and it works OK.
For the rest you'd have to do a little trial & error yourself..
## Post #65
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-06-25T05:21:28+00:00
- Post Title: Re: AION cgf to collada converter

many thanks for all, just got some problem with materials, maybe this can be fixed?

and some models give error like this.




> --  Frame:
>
> --   modelFilename: "C:\Users\GAMEMASTER\Desktop\Book\bo_drakanbook01.cgf"
>
> --   reader: (ChunkReader chunkArchive:(CryChunkArchive meshChunks:#() helperChunks:#() vertAnimChunks:#() boneAnimChunks:#() boneNameListChunks:#() scenePropChunks:#() lightChunks:#() nodeChunks:#((CryNodeChunk header:(CryChunkHeader type:11 version:2083 fileOffset:212 chunkID:2) name:"BO_DrakanBook01" objectID:5 parentID:-1 materialID:3 isGroupHead:false isGroupMember:false TransMatrix:(CryMatrix44 row1:[1,0,0,0] row2:[0,1,0,0] row3:[0,0,1,0] row4:[0,0,0,1]) position:[0,0,0] rotation:(quat 0 0 0 1) scale:[1,1,1] posCtrlID:"ffffffff" rotCtrlID:"ffffffff" scaleCtrlID:"ffffffff" property:"" childNodes:#())) materialChunks:#() controllerChunks:#() timingChunks:#((CryTimingChunk header:(CryChunkHeader type:14 version:2328 fileOffset:144 chunkID:1) secsPerTick:0.000208333 ticksPerFrame:160 globalRange:(CryRange name:"GlobalRange" start:0 End:100) subRanges:#())) boneMeshChunks:#() boneLightBindingChunks:#() meshMorphTargetChunks:#() boneInitialPosChunks:#() sourceInfoChunks:#((CrySourceInfoChunk header:(CryChunkHeader type:19 version:0 fileOffset:20 chunkID:0) sourceFile:"D:\perforce\AION\AION_Data\OBJECTS\items\Max\NPC_Drop_item\BO_DrakanBook01.max" date:"11/28/2011  14:10" user:"Administrator@AIONBUILD")) numChunks:3 geomFileName:"C:\Users\GAMEMASTER\Desktop\Book\bo_drakanbook01.cgf" separatePhysicsMesh:false) log:log() bs:<BinStream:C:\Users\GAMEMASTER\Desktop\Book\bo_drakanbook01.cgf> fs:<File:C:\Users\GAMEMASTER\Desktop\Book\bo_drakanbook01.cgf>)
>
> --   ret: undefined
>
> --   called in btnCgfImport.pressed(); filename: C:\Program Files (x86)\Autodesk\3ds Max 2013\scripts\CryImporter\CryImporter.ms; position: 3598; line: 116
>
> --  Frame:
>
> >> MAXScript Rollout Handler Exception:
>
> -- Unable to convert: undefined to type: Float <<

this is what I got whem import a bow, the model imported fine but ofc got error with materials, and about animation got error too.

> Set the following shaders for the given materials:
>
> -- Error occurred in x loop; filename: C:\Program Files (x86)\Autodesk\3ds Max 2013\scripts\CryImporter\CryImporter.ms; position: 8479; line: 301
>
> --  Frame:
>
> --   r: undefined
>
> --   path: undefined
>
> --   tempChunkArchive: undefined
>
> --   ret: undefined
>
> --   x: (CAFRecord name:"cdraw_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined)
>
> --   called in calImport(); filename: C:\Program Files (x86)\Autodesk\3ds Max 2013\scripts\CryImporter\CryImporter.ms; position: 9268; line: 329
>
> --  Frame:
>
> --   reader: (CALReader STATE_STARTLINE:0 STATE_GETNAME:1 STATE_GETEQUALS:2 STATE_GETPATH:3 state:3 animList:#((CAFRecord name:"cdraw_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cdraw_bow_run_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cidle_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cidle_bow_gasp_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cjump_start_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cjump_air_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cjump_end_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crun_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crunL_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crunR_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crunB_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattack_bow_001" path:"Items\bow_cattack_bow_001.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattackL_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattackR_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattack_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattackB_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cdamage_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cstumble_start_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cstumble_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cstumble_end_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), ...) currentCAF:(CAFRecord name:"Xfire_bow_powershot_001" path:"Items\Bow_Cfire_bow_powershot_001.caf" startframe:undefined endframe:undefined))
>
> --   animFilename: "C:\Users\GAMEMASTER\Desktop\Bow\bw_drakanbow01.cal"
>
> --   s: undefined
>
> --   list: #((CAFRecord name:"cdraw_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cdraw_bow_run_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cidle_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cidle_bow_gasp_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cjump_start_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cjump_air_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cjump_end_bow_001" path:"Items\Bow_Cidle_Bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crun_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crunL_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crunR_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"crunB_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattack_bow_001" path:"Items\bow_cattack_bow_001.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattackL_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattackR_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattack_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cattackB_bow_run_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cdamage_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cstumble_start_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cstumble_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), (CAFRecord name:"cstumble_end_bow_001" path:"Items\bow_Cidle_bow_001_loop.caf" startframe:undefined endframe:undefined), ...)
>
> --   ret: OK
>
> --   called in btnCalImport.pressed(); filename: C:\Program Files (x86)\Autodesk\3ds Max 2013\scripts\CryImporter\CryImporter.ms; position: 3921; line: 137
>
> --  Frame:
>
> >> MAXScript Rollout Handler Exception:
>
> -- Unable to convert: undefined to type: String <<
## Post #66
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-10-19T19:31:23+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from Szkaradek123
>
> The contents of this post was deleted because of possible forum rules violation.
Hello my friend, thank you for your great work,  your script has been deleted, can upload, thank you for your help
## Post #67
- Username: ivanches
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 9:54 am
- Post datetime: 2014-11-09T05:26:45+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from Szkaradek123
>
> The contents of this post was deleted because of possible forum rules violation.
Holy fuckin shit.
## Post #68
- Username: ivanches
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 9:54 am
- Post datetime: 2014-11-09T09:06:29+00:00
- Post Title: Re: AION cgf to collada converter

```
import bpy,struct,os
import Blender,glob
from Blender import *
from struct import *
from Blender.Mathutils import *
from Blender import Armature as A
import math
import pyffi
from pyffi import *
from pyffi.formats.cgf import CgfFormat
from Blender.Draw import *
from Blender.BGL import *



def printchunk(data):
   opath = path[path.rfind('\\')+1:]+'.txt'
   ostream = open(opath, 'wb')
   for chunk in data.chunks:
        ostream.write(str(chunk))
        ostream.write('\n')
   ostream.close()


def check_armature():
    global armobj,arm
    armobj=None
    arm=None
    scn = Scene.GetCurrent()
    scene = bpy.data.scenes.active
    for object in scene.objects:
        if object.getType()=='Armature':
            if object.name == 'armature':
                scn.unlink(object)
    for object in bpy.data.objects:
        if object.name == 'armature':
            armobj = Blender.Object.Get('armature')
            arm = armobj.getData()
            arm.makeEditable()         
            for bone in arm.bones.values():
                del arm.bones[bone.name]
            arm.update()
    if armobj==None: 
        armobj = Blender.Object.New('Armature','armature')
    if arm==None: 
        arm = Armature.New('armature')
        armobj.link(arm)
    scn.link(armobj)
    arm.drawType = Armature.STICK
    armobj.drawMode = Blender.Object.DrawModes.XRAY
    arm.makeEditable()

def editbone(namenode,parent):
    parentlist[namenode]=parent
    eb = A.Editbone()   
    arm.bones[namenode] = eb
    bone = arm.bones[namenode]

def makeparents(bonename):
    bone = arm.bones[bonename]
    if parentlist[bonename]!=-1:
        parent = arm.bones[str(parentlist[bonename])]
        bone.parent = parent 

def read_cgf_data():
    global vertexy,faces,normalne,uvcoord,uvfaces,matface,mesh,obiekt,groups,bonenamelist
    global parentlist
    parentlist={}
    vertexy=[]
    faces=[]
    normalne=[]
    uvcoord=[]
    uvfaces=[]
    nummat=0 
    matface = [] 
    groups={}  
    bonenamelist = {}
    stream = open(filename, 'rb')
    data = CgfFormat.Data()
    data.read(stream)
    stream.close()
    mesh = bpy.data.meshes.new(namemodel)
    scene = bpy.data.scenes.active
    obiekt = scene.objects.new(mesh,namemodel) 
    for chunk in data.chunks: 
        #printchunk(data)
        #print chunk.__class__
        #=== GEOMETRY ===
        if chunk.__class__ == CgfFormat.MeshChunk:
            numvertices = chunk.numVertices
            numfaces = chunk.numFaces
            print 'numvertices=',numvertices
            print 'numfaces=',numfaces
            for vert in chunk.vertices:
                vertexy.append([vert.p.x,vert.p.y,vert.p.z])
                normalne.append([vert.n.x,vert.n.y,vert.n.z])   
            for uv in chunk.uvs:
                uvcoord.append([uv.u,uv.v]) 
            for f in chunk.faces:
                faces.append([f.v0,f.v1,f.v2])
                matface.append(f.material)
            for uv in chunk.uvFaces:
                uvfaces.append([uv.t0,uv.t1,uv.t2])
            nrvert = 0
            for vw in chunk.vertexWeights:
                for m in vw.boneLinks:
                    group = m.bone
                    weight = float(m.blending)
                    if weight!=0:
                        if str(group) not in groups:
                            groups[str(group)]=[]              
                            mesh.addVertGroup(str(group))
                        groups[str(group)].append([nrvert,weight]) 
                nrvert+=1 
        #===BONES === 
        #=== BONES relation===
        if chunk.__class__ == CgfFormat.BoneAnimChunk:
            check_armature()
            armobj.makeParentDeform([obiekt],1,0)
            numbones = chunk.numBones 
            #print 'numbones=',numbones   
            for bone in chunk.bones:
                boneid = bone.boneId
                parentid = bone.parentId 
                #print 'bone=',boneid,'parent=',parentid 
                editbone(str(boneid),parentid)  
            arm.update()
            arm.makeEditable()
            for i in range(numbones):
                makeparents(str(i)) 
            arm.update()         
        #=== BONES names===
        if chunk.__class__ == CgfFormat.BoneNameListChunk:
            print 'numbones=',chunk.numNames 
            boneid = 0
            for name in chunk.names:
                print 'bone=',name
                bonenamelist[str(boneid)]=name  
                boneid+=1             
        #=== BONES initial position===
        if chunk.__class__ == CgfFormat.BoneInitialPosChunk:
            #print 'numbones=',chunk.num_bones  
            arm.makeEditable()
            numbone = 0  
            for initial in chunk.initialPosMatrices:
                matrix = Matrix()
                mat = CgfFormat.Matrix44()
                mat.setIdentity
                mat.setMatrix33(initial.rot)
                mat.setTranslation(initial.pos)
                matrix =  mat.asList()
                matrix = Matrix(matrix[0],matrix[1],matrix[2],matrix[3])
                arm.bones[str(numbone)].matrix = matrix
                numbone+=1
            for bone in arm.bones.values():
                bone.name = bonenamelist[bone.name] 
            arm.update() 
        #=== MATERIAL === 
        if chunk.__class__ == CgfFormat.MtlChunk:
            try:
                mat = Material.Get('mat-'+str(nummat)+namemodel)
            except:
                mat = Material.New('mat-'+str(nummat)+namemodel)    
            try:
                mesh.materials+=[Material.Get('mat-'+str(nummat)+namemodel)]
            except:
                pass
            nummat+=1
            tex = Texture.New('diff')
            tex.setType('Image')
            imagepath = chunk.texD.longName
            imagepath = imagepath.split(os.sep)
            imagepath = imagepath[-1].split('.')[0]
            imagename = imagepath
            imageext = ['dds','png','tga']
            for ext in imageext:
                try:
                    img = Blender.Image.Load(tex_dir.val+os.sep+imagename+'.'+ext)
                    tex.image = img
                    print imagename,'===========found' 
                    break
                except:
                    print imagename,'========no found' 
            mat.setTexture(0,tex,Texture.TexCo.UV,Texture.MapTo.COL)


def makemesh(): 
    mesh.verts.extend(vertexy)
    mesh.faces.extend(faces,ignoreDups=True)
    for id in range(len(mesh.verts)):
        mesh.verts[id].no = Vector(normalne[id])
    for id in range(len(uvfaces)):
        face = mesh.faces[id]
        uv1 = Vector(uvcoord[uvfaces[id][0]])
        uv2 = Vector(uvcoord[uvfaces[id][1]])
        uv3 = Vector(uvcoord[uvfaces[id][2]])
        face.uv = [uv1, uv2, uv3]
        face.smooth=True
        try:
            face.mat = matface[id] 
        except:
            pass  
    mesh.recalcNormals(0)
    obiekt.makeDisplayList()
    mesh.update()
    for vgroup in groups:
         for dane in groups[vgroup]:
             mesh.assignVertsToGroup(vgroup,[dane[0]],dane[1],1)
    mesh.update()
    for name in bonenamelist:
        try:
            mesh.renameVertGroup(name,bonenamelist[name])
        except:
            pass
    mesh.update()
    Redraw()

def read_caf():
    global rotKeys
    global posKeys,matrixkeys
    rotKeys = {}
    posKeys = {}   
    matrixkeys = {}
    stream = open(filename, 'rb')
    data = CgfFormat.Data()
    data.read(stream)
    stream.close()
    for chunk in data.chunks: 
        #printchunk(data)
        #print chunk.__class__
        #=== ANIMATION ===
        if chunk.__class__ == CgfFormat.TimingChunk:
            secspertick = chunk.secsPerTick
            ticksperframe = chunk.ticksPerFrame
            #print secspertick,ticksperframe
        if chunk.__class__ == CgfFormat.BoneNameListChunk:
            bonelist = chunk.names
            #for i in range(chunk.numNames):
            #   print bonelist[i]
    idbone = 0 
    for chunk in data.chunks: 
        if chunk.__class__ == CgfFormat.ControllerChunk:
            name = bonelist[idbone]
            #name = str(idbone)
            rotKeys[name]=[]
            posKeys[name]=[]
            matrixkeys[name] = []
            for key in chunk.keys:
                time = key.time/160#*secspertick
                pos = key.relPos.asList()
                pos = (pos[0],pos[1],pos[2])
                rot = key.relQuat
                rot = Quaternion(rot.w,rot.x,rot.y,rot.z)
                rot = rot.toMatrix().invert() 
                #matrix = rot*pos
                matrix = Matrix()                  
                matrix[0][:3] = rot[0]
                matrix[1][:3] = rot[1]
                matrix[2][:3] = rot[2]
                matrix[3][:3] = pos
                rotKeys[name].append([time,rot])
                posKeys[name].append([time,pos])
                matrixkeys[name].append([time,matrix]) 
                #print time#pos,rot 
            idbone+=1


def check_armature_for_animation():  
    global armobj,newarm 
    scene = bpy.data.scenes.active
    for object in scene.objects:
        if object.getType()=='Armature':
            if object.name == 'armature':
                armobj = object
                newarm = armobj.getData()

def makeanimation():
    global pose,action
    pose=0
    action=0
    #print armOb.name
    nameaction = sys.basename(filename).split('.')[0]
    pose = armobj.getPose()
    action = Blender.Armature.NLA.NewAction(nameaction)
    action.setActive(armobj)
    for name, pbone in pose.bones.items():
        if name in matrixkeys:
            for id in range(len(matrixkeys[name])):
                matrix = matrixkeys[name][id][1]
                time   = int(matrixkeys[name][id][0])
                if pbone.parent:
                    pbone.poseMatrix =  matrix*pbone.parent.poseMatrix
                else:
                    pbone.poseMatrix = matrix
                pbone.insertKey(armobj,time,[Object.Pose.LOC,Object.Pose.ROT],True)
                pose.update()
    scn = Scene.GetCurrent()
    context = scn.getRenderingContext()
    context.eFrame = time
    Redraw()
    
 

def armatureobject():
    scene = bpy.data.scenes.active
    for obj in scene.objects:
        if obj.type == 'Armature':# and obj.name == 'Arm-'+nameob[:-4]:
            armobj = Object.Get(obj.name) 
    return armobj 

def makeparent():
    scene = bpy.data.scenes.active
    for obj in scene.objects:
        try:
          if obj.type == 'Mesh':
              if nameob[:-4] in obj.name:
                  armOb.makeParentDeform([obj],1,0)
        except:
          pass 
    scene = bpy.data.scenes.active 

def select_caf_dir(filename):
    global caf_dir
    caf_dir.val = sys.dirname(filename)

def select_cgf_dir(filename):
    global cgf_dir
    cgf_dir.val = sys.dirname(filename)


def select_tex_dir(filename):
  global tex_dir
  tex_dir.val=sys.dirname(filename)


def create_cgf_toggles():
    global cgf_toggles
    cgf_toggles = {}
    extends=['cgf']
    cgf_list_dir = os.listdir(cgf_dir.val)
    cgf_list_dir.sort()
    for file in cgf_list_dir:
        extend = file.split('.')[-1].lower()
        if extend in extends:
            cgf_toggles[file] = Create(0)


def create_caf_toggles():
    global caf_toggles
    caf_toggles = {}
    extends=['caf']
    caf_list_dir = os.listdir(caf_dir.val)
    caf_list_dir.sort()
    for file in caf_list_dir:
        extend = file.split('.')[-1].lower()
        if extend in extends:
            caf_toggles[file] = Create(0)


rollx = 0
skala_model = Create(1)
skala_bones = Create(1)
flip_uv_toggle = Create(0)
flip_yz_toggle = Create(0)
quick_toggle = Create(1)
caf_dir = Blender.Draw.Create("")
cgf_dir  = Blender.Draw.Create("")
tex_dir  = Blender.Draw.Create("")
tab = 0

def draw():
    global id_but,namemodel,dx,skala_model,skala_bones,flip_uv_toggle,flip_yz_toggle
    global size,rollx,quick_toggle,caf_dir,tab,cgf_dir,tex_dir

    size = Window.GetAreaSize()

    glClearColor(0.1, 0.1, 0.1, 0.0)
    glClear(GL_COLOR_BUFFER_BIT)
    id_but = 1
    dx = 10
    if tab == 2:        
        names=[]    
        for file in cgf_toggles:
            names.append(file)
        names.sort()
        for file in names:
            if rollx+dx<size[1]:
                cgf_toggles[file]  = Toggle(file, id_but ,15,dx+rollx, 300, 15,cgf_toggles[file].val, '')
                id_but+=1
                dx+=20
        glColor3f(0.6,0.6,0.6)
        glRasterPos2i(15,dx+rollx)
        Text('SELECT  CGF  FILES:')
    if tab == 1:        
        names=[]    
        for file in caf_toggles:
            names.append(file)
        names.sort()
        for file in names:
            if rollx+dx<size[1]:
                caf_toggles[file]  = Toggle(file, id_but ,15,dx+rollx, 300, 15,caf_toggles[file].val, '')
                id_but+=1
                dx+=20
        glColor3f(0.6,0.6,0.6)
        glClearColor(0.9, 0.9, 0.9, 0.0)
        glRasterPos2i(15,dx+rollx)
        Text('SELECT  CAF   FILES:')
    """
    skala_model = Slider('SCALE MODEL   ', id_but, 430, 10, 255, 25,skala_model.val, 0.1, 5, 0.1, '')
    id_but+=1
    skala_bones = Slider('SCALE BONES   ', id_but, 430, 40, 255, 25,skala_bones.val, 0, 3, 1, '')
    id_but+=1
    flip_uv_toggle = Toggle('FLIP U-V   ', id_but ,430,70, 255, 25,flip_uv_toggle.val, '')
    id_but+=1
    flip_yz_toggle = Toggle('FLIP Y-Z   ', id_but ,430,100, 255, 25,flip_yz_toggle.val, '')
    id_but+=1
    quick_toggle = Toggle('SHOW QUICK MODEL', id_but ,430,130, 255, 25,quick_toggle.val,\
                          'deselect if problem with material')
    id_but+=1
    """
    cgf_dir = Blender.Draw.String("CGF  DIR:",id_but,515,410,170,25,cgf_dir.val,255, "CGF  FILE")
    id_but+=1
    Button("SHOW  CGF  FILES",id_but,430,380,255,25,'')
    id_but+=1
    Button("BROWSE",id_but,430,410,80,25, "Specify cgf dir")
    id_but+=1

    glColor3f(0.6,0.6,0.6)
    glRasterPos2i(430,440)
    Text('SELECT  CGF  DIR:')

    caf_dir = Blender.Draw.String("CAF  DIR:",id_but,515,320,170,25,caf_dir.val,255, "CAF DIR")
    id_but+=1
    Button("SHOW  CAF  FILES",id_but,430,290,255,25,'')
    id_but+=1
    Button("BROWSE",id_but,430,320,80,25, "Specify caf dir")
    id_but+=1

    glRasterPos2i(430,350)
    Text('SELECT  CAF  DIR:')
    
    tex_dir = Blender.Draw.String("TEXTURE  DIR:",id_but,515,230,170,25,tex_dir.val,255, "TEXTURE DIR")
    id_but+=1
    Button("SHOW  TEXTURES",id_but,430,200,255,25,'')
    id_but+=1
    Button("BROWSE",id_but,430,230,80,25, "Specify texture dir")
    id_but+=1

    glRasterPos2i(430,260)
    Text('SELECT  TEXTURE  DIR:')
    
    Button('LOAD',id_but,320,10,50,dx+rollx,'') 
    id_but+=1
    Button('EXIT',id_but,375,10,50,dx+rollx,'') 
        

def event(evt,val):
    global rollx
    if (evt== QKEY and not val): Exit()
    if evt == WHEELDOWNMOUSE:
        if (rollx < 0):
            rollx += 100
            Draw()
    elif evt == WHEELUPMOUSE:
        if (rollx+dx > size[1]):
            rollx -= 100
            Draw()
def bevent(evt):
    global namemodel,skala,skalabones,flipuv,flipyz,quick,tab,anim,filename
    flipuv = flip_uv_toggle.val
    flipyz = flip_yz_toggle.val
    quick  = quick_toggle.val
    if evt == id_but-9:#show psk files
        if len(cgf_dir.val)>0: 
            create_cgf_toggles()
            tab = 2
            Draw()
    if evt == id_but-8:#browse psk
        Blender.Window.FileSelector(select_cgf_dir, "Select cgf dir...") 
        Draw()  
    if evt == id_but-6:#show animation
        if len(caf_dir.val)>0: 
            create_caf_toggles()
            tab = 1
            Draw()
    if evt == id_but-5:#browse psa
        Blender.Window.FileSelector(select_caf_dir, "Select animation file .psa...") 
        Draw()  
    if evt == id_but-4:#show textures
        pass
    if evt == id_but-2:#browse texture
        Blender.Window.FileSelector(select_tex_dir, "Select texture dir...") 
    if evt == id_but-1:#LOAD
        if tab == 2:
            for file in cgf_toggles:
                if cgf_toggles[file] == True:
                    skala = skala_model.val
                    skalabones = skala_bones.val
                    filename = cgf_dir.val+os.sep+file 
                    realnamemodel = sys.basename(filename).split('.')[0]
                    timenamemodel = str(sys.time())
                    if len(realnamemodel)>20:
                        namemodel=timenamemodel
                    else:
                        namemodel=realnamemodel
                    read_cgf_data()
                    makemesh()
                    Blender.Redraw()
        if tab == 1:   
            for file in caf_toggles:
                if caf_toggles[file] == True:
                    filename = caf_dir.val+os.sep+file 
                    check_armature_for_animation()
                    read_caf()
                    makeanimation()
    if evt == id_but:#EXIT    
        Blender.Draw.Exit()
    

Register(draw, event, bevent)
```
The code aion importer.py
## Post #69
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-09T11:58:16+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from ivanches
>
> Code: Select all#2011-02-06 Mariusz Szkaradek Glogow Poland
import bpy,struct,os
import Blender,glob
from Blender import *
from struct import *
from Blender.Mathutils import *
from Blender import Armature as A
import math
import pyffi
from pyffi import *
from pyffi.formats.cgf import CgfFormat
from Blender.Draw import *
from Blender.BGL import *



def printchunk(data):
   opath = path[path.rfind('\\')+1:]+'.txt'
   ostream = open(opath, 'wb')
   for chunk in data.chunks:
        ostream.write(str(chunk))
        ostream.write('\n')
   ostream.close()


def check_armature():
    global armobj,arm
    armobj=None
    arm=None
    scn = Scene.GetCurrent()
    scene = bpy.data.scenes.active
    for object in scene.objects:
        if object.getType()=='Armature':
            if object.name == 'armature':
                scn.unlink(object)
    for object in bpy.data.objects:
        if object.name == 'armature':
            armobj = Blender.Object.Get('armature')
            arm = armobj.getData()
            arm.makeEditable()         
            for bone in arm.bones.values():
                del arm.bones[bone.name]
            arm.update()
    if armobj==None: 
        armobj = Blender.Object.New('Armature','armature')
    if arm==None: 
        arm = Armature.New('armature')
        armobj.link(arm)
    scn.link(armobj)
    arm.drawType = Armature.STICK
    armobj.drawMode = Blender.Object.DrawModes.XRAY
    arm.makeEditable()

def editbone(namenode,parent):
    parentlist[namenode]=parent
    eb = A.Editbone()   
    arm.bones[namenode] = eb
    bone = arm.bones[namenode]

def makeparents(bonename):
    bone = arm.bones[bonename]
    if parentlist[bonename]!=-1:
        parent = arm.bones[str(parentlist[bonename])]
        bone.parent = parent 

def read_cgf_data():
    global vertexy,faces,normalne,uvcoord,uvfaces,matface,mesh,obiekt,groups,bonenamelist
    global parentlist
    parentlist={}
    vertexy=[]
    faces=[]
    normalne=[]
    uvcoord=[]
    uvfaces=[]
    nummat=0 
    matface = [] 
    groups={}  
    bonenamelist = {}
    stream = open(filename, 'rb')
    data = CgfFormat.Data()
    data.read(stream)
    stream.close()
    mesh = bpy.data.meshes.new(namemodel)
    scene = bpy.data.scenes.active
    obiekt = scene.objects.new(mesh,namemodel) 
    for chunk in data.chunks: 
        #printchunk(data)
        #print chunk.__class__
        #=== GEOMETRY ===
        if chunk.__class__ == CgfFormat.MeshChunk:
            numvertices = chunk.numVertices
            numfaces = chunk.numFaces
            print 'numvertices=',numvertices
            print 'numfaces=',numfaces
            for vert in chunk.vertices:
                vertexy.append([vert.p.x,vert.p.y,vert.p.z])
                normalne.append([vert.n.x,vert.n.y,vert.n.z])   
            for uv in chunk.uvs:
                uvcoord.append([uv.u,uv.v]) 
            for f in chunk.faces:
                faces.append([f.v0,f.v1,f.v2])
                matface.append(f.material)
            for uv in chunk.uvFaces:
                uvfaces.append([uv.t0,uv.t1,uv.t2])
            nrvert = 0
            for vw in chunk.vertexWeights:
                for m in vw.boneLinks:
                    group = m.bone
                    weight = float(m.blending)
                    if weight!=0:
                        if str(group) not in groups:
                            groups[str(group)]=[]              
                            mesh.addVertGroup(str(group))
                        groups[str(group)].append([nrvert,weight]) 
                nrvert+=1 
        #===BONES === 
        #=== BONES relation===
        if chunk.__class__ == CgfFormat.BoneAnimChunk:
            check_armature()
            armobj.makeParentDeform([obiekt],1,0)
            numbones = chunk.numBones 
            #print 'numbones=',numbones   
            for bone in chunk.bones:
                boneid = bone.boneId
                parentid = bone.parentId 
                #print 'bone=',boneid,'parent=',parentid 
                editbone(str(boneid),parentid)  
            arm.update()
            arm.makeEditable()
            for i in range(numbones):
                makeparents(str(i)) 
            arm.update()         
        #=== BONES names===
        if chunk.__class__ == CgfFormat.BoneNameListChunk:
            print 'numbones=',chunk.numNames 
            boneid = 0
            for name in chunk.names:
                print 'bone=',name
                bonenamelist[str(boneid)]=name  
                boneid+=1             
        #=== BONES initial position===
        if chunk.__class__ == CgfFormat.BoneInitialPosChunk:
            #print 'numbones=',chunk.num_bones  
            arm.makeEditable()
            numbone = 0  
            for initial in chunk.initialPosMatrices:
                matrix = Matrix()
                mat = CgfFormat.Matrix44()
                mat.setIdentity
                mat.setMatrix33(initial.rot)
                mat.setTranslation(initial.pos)
                matrix =  mat.asList()
                matrix = Matrix(matrix[0],matrix[1],matrix[2],matrix[3])
                arm.bones[str(numbone)].matrix = matrix
                numbone+=1
            for bone in arm.bones.values():
                bone.name = bonenamelist[bone.name] 
            arm.update() 
        #=== MATERIAL === 
        if chunk.__class__ == CgfFormat.MtlChunk:
            try:
                mat = Material.Get('mat-'+str(nummat)+namemodel)
            except:
                mat = Material.New('mat-'+str(nummat)+namemodel)    
            try:
                mesh.materials+=[Material.Get('mat-'+str(nummat)+namemodel)]
            except:
                pass
            nummat+=1
            tex = Texture.New('diff')
            tex.setType('Image')
            imagepath = chunk.texD.longName
            imagepath = imagepath.split(os.sep)
            imagepath = imagepath[-1].split('.')[0]
            imagename = imagepath
            imageext = ['dds','png','tga']
            for ext in imageext:
                try:
                    img = Blender.Image.Load(tex_dir.val+os.sep+imagename+'.'+ext)
                    tex.image = img
                    print imagename,'===========found' 
                    break
                except:
                    print imagename,'========no found' 
            mat.setTexture(0,tex,Texture.TexCo.UV,Texture.MapTo.COL)


def makemesh(): 
    mesh.verts.extend(vertexy)
    mesh.faces.extend(faces,ignoreDups=True)
    for id in range(len(mesh.verts)):
        mesh.verts[id].no = Vector(normalne[id])
    for id in range(len(uvfaces)):
        face = mesh.faces[id]
        uv1 = Vector(uvcoord[uvfaces[id][0]])
        uv2 = Vector(uvcoord[uvfaces[id][1]])
        uv3 = Vector(uvcoord[uvfaces[id][2]])
        face.uv = [uv1, uv2, uv3]
        face.smooth=True
        try:
            face.mat = matface[id] 
        except:
            pass  
    mesh.recalcNormals(0)
    obiekt.makeDisplayList()
    mesh.update()
    for vgroup in groups:
         for dane in groups[vgroup]:
             mesh.assignVertsToGroup(vgroup,[dane[0]],dane[1],1)
    mesh.update()
    for name in bonenamelist:
        try:
            mesh.renameVertGroup(name,bonenamelist[name])
        except:
            pass
    mesh.update()
    Redraw()

def read_caf():
    global rotKeys
    global posKeys,matrixkeys
    rotKeys = {}
    posKeys = {}   
    matrixkeys = {}
    stream = open(filename, 'rb')
    data = CgfFormat.Data()
    data.read(stream)
    stream.close()
    for chunk in data.chunks: 
        #printchunk(data)
        #print chunk.__class__
        #=== ANIMATION ===
        if chunk.__class__ == CgfFormat.TimingChunk:
            secspertick = chunk.secsPerTick
            ticksperframe = chunk.ticksPerFrame
            #print secspertick,ticksperframe
        if chunk.__class__ == CgfFormat.BoneNameListChunk:
            bonelist = chunk.names
            #for i in range(chunk.numNames):
            #   print bonelist[i]
    idbone = 0 
    for chunk in data.chunks: 
        if chunk.__class__ == CgfFormat.ControllerChunk:
            name = bonelist[idbone]
            #name = str(idbone)
            rotKeys[name]=[]
            posKeys[name]=[]
            matrixkeys[name] = []
            for key in chunk.keys:
                time = key.time/160#*secspertick
                pos = key.relPos.asList()
                pos = (pos[0],pos[1],pos[2])
                rot = key.relQuat
                rot = Quaternion(rot.w,rot.x,rot.y,rot.z)
                rot = rot.toMatrix().invert() 
                #matrix = rot*pos
                matrix = Matrix()                  
                matrix[0][:3] = rot[0]
                matrix[1][:3] = rot[1]
                matrix[2][:3] = rot[2]
                matrix[3][:3] = pos
                rotKeys[name].append([time,rot])
                posKeys[name].append([time,pos])
                matrixkeys[name].append([time,matrix]) 
                #print time#pos,rot 
            idbone+=1


def check_armature_for_animation():  
    global armobj,newarm 
    scene = bpy.data.scenes.active
    for object in scene.objects:
        if object.getType()=='Armature':
            if object.name == 'armature':
                armobj = object
                newarm = armobj.getData()

def makeanimation():
    global pose,action
    pose=0
    action=0
    #print armOb.name
    nameaction = sys.basename(filename).split('.')[0]
    pose = armobj.getPose()
    action = Blender.Armature.NLA.NewAction(nameaction)
    action.setActive(armobj)
    for name, pbone in pose.bones.items():
        if name in matrixkeys:
            for id in range(len(matrixkeys[name])):
                matrix = matrixkeys[name][id][1]
                time   = int(matrixkeys[name][id][0])
                if pbone.parent:
                    pbone.poseMatrix =  matrix*pbone.parent.poseMatrix
                else:
                    pbone.poseMatrix = matrix
                pbone.insertKey(armobj,time,[Object.Pose.LOC,Object.Pose.ROT],True)
                pose.update()
    scn = Scene.GetCurrent()
    context = scn.getRenderingContext()
    context.eFrame = time
    Redraw()
    
 

def armatureobject():
    scene = bpy.data.scenes.active
    for obj in scene.objects:
        if obj.type == 'Armature':# and obj.name == 'Arm-'+nameob[:-4]:
            armobj = Object.Get(obj.name) 
    return armobj 

def makeparent():
    scene = bpy.data.scenes.active
    for obj in scene.objects:
        try:
          if obj.type == 'Mesh':
              if nameob[:-4] in obj.name:
                  armOb.makeParentDeform([obj],1,0)
        except:
          pass 
    scene = bpy.data.scenes.active 

def select_caf_dir(filename):
    global caf_dir
    caf_dir.val = sys.dirname(filename)

def select_cgf_dir(filename):
    global cgf_dir
    cgf_dir.val = sys.dirname(filename)


def select_tex_dir(filename):
  global tex_dir
  tex_dir.val=sys.dirname(filename)


def create_cgf_toggles():
    global cgf_toggles
    cgf_toggles = {}
    extends=['cgf']
    cgf_list_dir = os.listdir(cgf_dir.val)
    cgf_list_dir.sort()
    for file in cgf_list_dir:
        extend = file.split('.')[-1].lower()
        if extend in extends:
            cgf_toggles[file] = Create(0)


def create_caf_toggles():
    global caf_toggles
    caf_toggles = {}
    extends=['caf']
    caf_list_dir = os.listdir(caf_dir.val)
    caf_list_dir.sort()
    for file in caf_list_dir:
        extend = file.split('.')[-1].lower()
        if extend in extends:
            caf_toggles[file] = Create(0)


rollx = 0
skala_model = Create(1)
skala_bones = Create(1)
flip_uv_toggle = Create(0)
flip_yz_toggle = Create(0)
quick_toggle = Create(1)
caf_dir = Blender.Draw.Create("")
cgf_dir  = Blender.Draw.Create("")
tex_dir  = Blender.Draw.Create("")
tab = 0

def draw():
    global id_but,namemodel,dx,skala_model,skala_bones,flip_uv_toggle,flip_yz_toggle
    global size,rollx,quick_toggle,caf_dir,tab,cgf_dir,tex_dir

    size = Window.GetAreaSize()

    glClearColor(0.1, 0.1, 0.1, 0.0)
    glClear(GL_COLOR_BUFFER_BIT)
    id_but = 1
    dx = 10
    if tab == 2:        
        names=[]    
        for file in cgf_toggles:
            names.append(file)
        names.sort()
        for file in names:
            if rollx+dx<size[1]:
                cgf_toggles[file]  = Toggle(file, id_but ,15,dx+rollx, 300, 15,cgf_toggles[file].val, '')
                id_but+=1
                dx+=20
        glColor3f(0.6,0.6,0.6)
        glRasterPos2i(15,dx+rollx)
        Text('SELECT  CGF  FILES:')
    if tab == 1:        
        names=[]    
        for file in caf_toggles:
            names.append(file)
        names.sort()
        for file in names:
            if rollx+dx<size[1]:
                caf_toggles[file]  = Toggle(file, id_but ,15,dx+rollx, 300, 15,caf_toggles[file].val, '')
                id_but+=1
                dx+=20
        glColor3f(0.6,0.6,0.6)
        glClearColor(0.9, 0.9, 0.9, 0.0)
        glRasterPos2i(15,dx+rollx)
        Text('SELECT  CAF   FILES:')
    """
    skala_model = Slider('SCALE MODEL   ', id_but, 430, 10, 255, 25,skala_model.val, 0.1, 5, 0.1, '')
    id_but+=1
    skala_bones = Slider('SCALE BONES   ', id_but, 430, 40, 255, 25,skala_bones.val, 0, 3, 1, '')
    id_but+=1
    flip_uv_toggle = Toggle('FLIP U-V   ', id_but ,430,70, 255, 25,flip_uv_toggle.val, '')
    id_but+=1
    flip_yz_toggle = Toggle('FLIP Y-Z   ', id_but ,430,100, 255, 25,flip_yz_toggle.val, '')
    id_but+=1
    quick_toggle = Toggle('SHOW QUICK MODEL', id_but ,430,130, 255, 25,quick_toggle.val,\
                          'deselect if problem with material')
    id_but+=1
    """
    cgf_dir = Blender.Draw.String("CGF  DIR:",id_but,515,410,170,25,cgf_dir.val,255, "CGF  FILE")
    id_but+=1
    Button("SHOW  CGF  FILES",id_but,430,380,255,25,'')
    id_but+=1
    Button("BROWSE",id_but,430,410,80,25, "Specify cgf dir")
    id_but+=1

    glColor3f(0.6,0.6,0.6)
    glRasterPos2i(430,440)
    Text('SELECT  CGF  DIR:')

    caf_dir = Blender.Draw.String("CAF  DIR:",id_but,515,320,170,25,caf_dir.val,255, "CAF DIR")
    id_but+=1
    Button("SHOW  CAF  FILES",id_but,430,290,255,25,'')
    id_but+=1
    Button("BROWSE",id_but,430,320,80,25, "Specify caf dir")
    id_but+=1

    glRasterPos2i(430,350)
    Text('SELECT  CAF  DIR:')
    
    tex_dir = Blender.Draw.String("TEXTURE  DIR:",id_but,515,230,170,25,tex_dir.val,255, "TEXTURE DIR")
    id_but+=1
    Button("SHOW  TEXTURES",id_but,430,200,255,25,'')
    id_but+=1
    Button("BROWSE",id_but,430,230,80,25, "Specify texture dir")
    id_but+=1

    glRasterPos2i(430,260)
    Text('SELECT  TEXTURE  DIR:')
    
    Button('LOAD',id_but,320,10,50,dx+rollx,'') 
    id_but+=1
    Button('EXIT',id_but,375,10,50,dx+rollx,'') 
        

def event(evt,val):
    global rollx
    if (evt== QKEY and not val): Exit()
    if evt == WHEELDOWNMOUSE:
        if (rollx < 0):
            rollx += 100
            Draw()
    elif evt == WHEELUPMOUSE:
        if (rollx+dx > size[1]):
            rollx -= 100
            Draw()
def bevent(evt):
    global namemodel,skala,skalabones,flipuv,flipyz,quick,tab,anim,filename
    flipuv = flip_uv_toggle.val
    flipyz = flip_yz_toggle.val
    quick  = quick_toggle.val
    if evt == id_but-9:#show psk files
        if len(cgf_dir.val)>0: 
            create_cgf_toggles()
            tab = 2
            Draw()
    if evt == id_but-8:#browse psk
        Blender.Window.FileSelector(select_cgf_dir, "Select cgf dir...") 
        Draw()  
    if evt == id_but-6:#show animation
        if len(caf_dir.val)>0: 
            create_caf_toggles()
            tab = 1
            Draw()
    if evt == id_but-5:#browse psa
        Blender.Window.FileSelector(select_caf_dir, "Select animation file .psa...") 
        Draw()  
    if evt == id_but-4:#show textures
        pass
    if evt == id_but-2:#browse texture
        Blender.Window.FileSelector(select_tex_dir, "Select texture dir...") 
    if evt == id_but-1:#LOAD
        if tab == 2:
            for file in cgf_toggles:
                if cgf_toggles[file] == True:
                    skala = skala_model.val
                    skalabones = skala_bones.val
                    filename = cgf_dir.val+os.sep+file 
                    realnamemodel = sys.basename(filename).split('.')[0]
                    timenamemodel = str(sys.time())
                    if len(realnamemodel)>20:
                        namemodel=timenamemodel
                    else:
                        namemodel=realnamemodel
                    read_cgf_data()
                    makemesh()
                    Blender.Redraw()
        if tab == 1:   
            for file in caf_toggles:
                if caf_toggles[file] == True:
                    filename = caf_dir.val+os.sep+file 
                    check_armature_for_animation()
                    read_caf()
                    makeanimation()
    if evt == id_but:#EXIT    
        Blender.Draw.Exit()
    

Register(draw, event, bevent)The code aion importer.py
My friend, thank you very much for your help
## Post #70
- Username: ivanches
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 9:54 am
- Post datetime: 2014-11-10T08:25:21+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from CriticalError
>
> many thanks for all, just got some problem with materials, maybe this can be fixed?

and some models give error like this.Use the script of the title theme! After converting uncover everything in a blender 2.72.
I have all the fine imported without error. Some textures have to manually install.
Not complex manipulations but routine.

In a blender 2.72 standard import collada .dae correctly translates everything. In older versions do not correctly!
## Post #71
- Username: ivanches
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 9:54 am
- Post datetime: 2014-11-10T08:33:00+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from raykingnihong
>
> 
My friend, thank you very much for your help
Unable to open the animation does - does not load, gives an error with this script. You have this script animation work?

I use script of the title theme, and then open in blender 2.72
Animations converts without problems!
## Post #72
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-09T19:18:18+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from Szkaradek123
>
> The contents of this post was deleted because of possible forum rules violation.



Update: 2014-12-08
Aion Blender importer.
It requires Blender version 249 and Python 26

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select cgf file for meshes and skeleton
3.for animation press alt+p and select caf fileHello my friend, thank you always for your great contribution, I think most of friends want to try, this script runs perfectly, you can import actions, models, textures. Very good, thanks again,Szkaradek123
## Post #73
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-09T05:54:10+00:00
- Post Title: Re: AION cgf to collada converter

Everything is working here!
## Post #74
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-01-09T18:01:26+00:00
- Post Title: Re: AION cgf to collada converter

The Blender script was written for version 2.49. You can run multiple versions of Blender side by side. Get 2.49 for the sake of using the script then export to whatever version of Blender you use.
## Post #75
- Username: ZaTii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 10, 2014 5:43 am
- Post datetime: 2015-01-30T23:04:02+00:00
- Post Title: Re: AION cgf to collada converter

Hey Guys

That Python script with the Blender standalone is great!

I can import the Model and Skeleton without a problem. But when i wanna import a animation the Bones change and the animation looks destroyed. Is there something that i must look on?
## Post #76
- Username: kamikaze88
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 05, 2012 3:10 am
- Post datetime: 2015-04-10T07:25:35+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from blackfoxeye
>
> 

Hi, how did you get the scripts user interface to look like that? would you mind sharing? mine looks very basic
## Post #77
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-06-16T16:51:45+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from kamikaze88
>
> blackfoxeye wrote:

Hi, how did you get the scripts user interface to look like that? would you mind sharing? mine looks very basic

Need can share > <
## Post #78
- Username: Alukardqwe
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 07, 2017 5:59 am
- Post datetime: 2017-08-05T14:16:58+00:00
- Post Title: Re: AION cgf to collada converter

> Reply from microkong
>
> * Convert AION mesh, skin and animation to .dae
* Running on python 2.5/2.6
* Modify the path and mesh/animation name in the aion2collada.py
* Use RPGViewer to unpack the aion pak
* The .dae can be imported to 3dsmax9 using OpenCOLLADA 3ds Max Plugin 1.2.5
* The code is base on cgf reader in PyFFI 2.0.5 and collada writer in Collada Blender 0.3.159

Who can tell me what to write these scripts? Should it be a max or a blender? Or Nemesis
## Post #79
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2023-02-11T17:40:19+00:00
- Post Title: Re: AION cgf to collada converter

hello any have tools scripts I need extract aion online models animations
