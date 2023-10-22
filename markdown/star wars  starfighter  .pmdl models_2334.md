## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2006-12-30T14:31:36+00:00
- Post Title: star wars : starfighter  .pmdl models

hello to eveybody ..
someone know this extension or know how to import it ???

please .. help me ...

best regards

here the link to the link .RAR
[http://www.rapidfile.fr/wget.php?id=wCk7zEzP](http://www.rapidfile.fr/wget.php?id=wCk7zEzP)
## Post #2
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-01-09T10:05:05+00:00
- Post Title: star wars : starfighter  .pmdl models

up ... 
anyone have an idea ????
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-09T11:06:49+00:00
- Post Title: star wars : starfighter  .pmdl models

This is what is found in the file : 

> Exported from MAX file S:\ART\lores_models\vehicles\dagger\Exported\newdag_jg_vaportrail.max
>
> by jgabriel on JGABRIEL-A-98
>
> at Thu Nov 02 18:56:11 2000
>
> 
>
> dagger-rotor03.msh Ë—  *  K):dagger-rotor04.msh õ›  *  K):dagger.mdl

MSH is obviously a mesh. Reportedly Orbiter is using the same format 
[http://orbit.medphys.ucl.ac.uk/orbit.html](http://orbit.medphys.ucl.ac.uk/orbit.html)
It is a stretch, but you never know.
## Post #4
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2007-01-09T22:22:11+00:00
- Post Title: star wars : starfighter  .pmdl models

great news ... but i think the .pmdl is a compliation of .msh files by this way .. right ??
how extract .msh files from this .pmdl file ?? could i read directly the .pmdl file with one importer ???

and .msh files isn't a generic format ?? i have read it exist many version of .msh files ...
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2007-12-01T19:16:42+00:00
- Post Title: star wars : starfighter  .pmdl models

On this website, I have found an unpacker for Star Wars Starfighter.
[http://gamefileformats.netfirms.com/](http://gamefileformats.netfirms.com/)

Star Wars Starfighter unpacker 1.0
[http://gamefileformats.netfirms.com/fil ... ak-1.0.zip](http://gamefileformats.netfirms.com/files/lec/sfdepak-1.0.zip)

You can extract the .msh/mtl files from the (packed) .pmdl file like this:
sfdepak.exe neutralfreighter.pmdl
## Post #6
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2008-06-25T17:53:13+00:00
- Post Title: star wars : starfighter  .pmdl models

Hello, I'm new here...
I'm not a coder nor do I have any skills when it comes to figuring out file formats. There is only one program I know of that can actually read/import the .pmdl files and that is [http://web.axelero.hu/karpo/](http://web.axelero.hu/karpo/) (3D Object Converter). The downside is that it doesn't support the textures or UV map coordinates and it also imports many of the meshes wrong.

The .pmdl format is just a container file containing the following:

"info.txt" - Likely only used for developement and not in-game.
"xxxx.mdl" - Contains the reference coordinates for the different model parts allowing them to be put together. It also has reference data for camera positions, emitters, and weapons.
"xxxx.msh" - The model geometry.
"xxxx.mtl" - The material/shader data for the model.

This looks to be a fairly simple format to decode, why hasn't anyone figured this out yet?
Here is a sample with the contents of an extracted .pmdl along with the associated textures:
[http://sharebee.com/7a6fd3fa](http://sharebee.com/7a6fd3fa)
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2008-06-25T18:23:47+00:00
- Post Title: star wars : starfighter  .pmdl models

Gwlogan,

Did you find my program (3D Object Converter) ?  
It is funny.
## Post #8
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2008-06-26T16:57:24+00:00
- Post Title: star wars : starfighter  .pmdl models

> Reply from Karpati
>
> Gwlogan,

Did you find my program (3D Object Converter) ?  
It is funny.

Actually YES, that's it 3D Object Converter! I just have the demo/trial version but it is the only program that works with .pmdl. Great program by the way!
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-14T07:24:03+00:00
- Post Title: star wars : starfighter  .pmdl models

Reviving this thread because 3d Object Converter is the only program that can open this msh format but it has zero support for UVs, and basically what gwlogan said here

> Reply from gwlogan
>
> I'm not a coder nor do I have any skills when it comes to figuring out file formats. There is only one program I know of that can actually read/import the .pmdl files and that is 3D Object Converter. The downside is that it doesn't support the textures or UV map coordinates and it also imports many of the meshes wrong.
The developer will not respond to questions about the format and seems to have no intention on adding further support.

> Reply from gwlogan
>
> Here is a sample with the contents of an extracted .pmdl along with the associated textures:
http://sharebee.com/7a6fd3fa
fixed link

```
http://www.mediafire.com/download/60cr1zlwpsp3cwa/Sith_Infiltrator.7z
```


I'm making a final plea for someone to take a look at these msh files and post a solution to this so we can finally move forward.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-14T08:25:00+00:00
- Post Title: star wars : starfighter  .pmdl models

> Reply from AceWell
>
> Reviving this thread [...]do u like riding dead horses? 



infiltrator-body_msh.JPG (54.95 KiB) Viewed 154 times
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-14T09:41:34+00:00
- Post Title: star wars : starfighter  .pmdl models

shakotay to the rescue yet again!   Thanks a bunch!
## Post #12
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-21T08:22:17+00:00
- Post Title: star wars : starfighter  .pmdl models

> Reply from AceWell
>
> Reviving this thread because 3d Object Converter is the only program that can open this msh format but it has zero support for UVs, and basically what gwlogan said here
gwlogan wrote:I'm not a coder nor do I have any skills when it comes to figuring out file formats. There is only one program I know of that can actually read/import the .pmdl files and that is 3D Object Converter. The downside is that it doesn't support the textures or UV map coordinates and it also imports many of the meshes wrong.
The developer will not respond to questions about the format and seems to have no intention on adding further support.
gwlogan wrote:Here is a sample with the contents of an extracted .pmdl along with the associated textures:
http://sharebee.com/7a6fd3fa
fixed link
Code: Select allhttp://www.mediafire.com/download/60cr1zlwpsp3cwa/Sith_Infiltrator.7z

I'm making a final plea for someone to take a look at these msh files and post a solution to this so we can finally move forward.

Ace, nice to see you again on it ...
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-08-22T12:09:36+00:00
- Post Title: star wars : starfighter  .pmdl models

> Reply from AceWell
>
> Reviving this thread because 3d Object Converter is the only program that can open this msh format but it has zero support for UVs, and basically what gwlogan said here.

I improved the  Star Wars : Starfighter .msh loader module about 3 months based on a user request (UV vertex support, loads the real texture filename), but I did not published it officially yet:

[http://3doc.i3dconverter.com/downloads/ ... 150822.zip](http://3doc.i3dconverter.com/downloads/3doc_v6304_20150822.zip)
## Post #14
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-22T13:12:26+00:00
- Post Title: star wars : starfighter  .pmdl models

> Reply from Karpati
>
> AceWell wrote:Reviving this thread because 3d Object Converter is the only program that can open this msh format but it has zero support for UVs, and basically what gwlogan said here.

I improved the  Star Wars : Starfighter .msh loader module about 3 months based on a user request (UV vertex support, loads the real texture filename), but I did not published it officially yet:

http://3doc.i3dconverter.com/downloads/ ... 150822.zip

nice !!! it work fine with the Infiltrator, i will test it with some others models

it can be usefull, if for december, Disney, redesign for PS4 ,  the Star Wars : Starfighter
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-22T14:53:42+00:00
- Post Title: star wars : starfighter  .pmdl models

[out]
## Post #16
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-22T17:59:25+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

a quick test with the new plugin from Unwrap3D
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-22T19:53:57+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

So many import options to choose from now!   Thanks everyone!    


> Reply from Karpati
>
> On this website, I have found an unpacker for Star Wars Starfighter.
http://gamefileformats.netfirms.com/

Star Wars Starfighter unpacker 1.0
http://gamefileformats.netfirms.com/fil ... ak-1.0.zip

You can extract the .msh/mtl files from the (packed) .pmdl file like this:
sfdepak.exe neutralfreighter.pmdl
since that webpage is gone here is a local backup of the pak/pmdl unpacker


 sfdepak-1.0.zip
(16.64 KiB) Downloaded 48 times


and this is the archived webpage where the tool used to be downloaded from
[http://web.archive.org/web/200806111010 ... =LucasArts](http://web.archive.org/web/20080611101050/http://gamefileformats.netfirms.com/cgi-bin/list.cgi?cat=LucasArts)
## Post #18
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-22T20:38:14+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

agree , Ace ...

but the sfdepack , fail on many .pmdl files , like cruisers, capital ships ....
we need to find a new way to unpack them correctly .. since now we can import them perfectly ....
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-22T20:53:28+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

[out]
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-23T02:33:41+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

[out]
## Post #21
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-23T07:51:02+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

2 tests this night ...





i need just now to work on BGR , to have RGB
[viewtopic.php?f=18&t=2504&p=20126&hilit ... ars#p20126](http://forum.xentax.com/viewtopic.php?f=18&t=2504&p=20126&hilit=.tex+star+wars#p20126)
## Post #22
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-25T16:14:06+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

@ Wobble ...
i don't think the .mdl file is read ...
i have do a quick test, delete the .mdl file , and import the .msh file...
with or without .. i have the same 3D position ....
i have redo the test, with text modifications into the .mdl file .. nothing change during the import of the model ...

the sfdepak maybe don't unpack and read perfectly the .pmdl file
maybe we need a better extractor ...

with the correct color code:
## Post #23
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-25T18:51:04+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

[out]
## Post #24
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-29T08:33:53+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

Wobble, i have discuss with Acewell

it seems we use the same tool,same version, same pluggin ,  but my import don't put elements into the right position
i'm looking for the reason now ... sadly
## Post #25
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-29T19:03:23+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

[out]
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-29T19:49:33+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

[out]
## Post #27
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-30T07:33:52+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

on some  models: 

the Toth Fighter 
right and left canons are set to the middle into the cockpit, instead the right position close to the wings

the DeathBoat
the top turret and canon aren't in right position ...

coupe of others models, have some wrong position of parts
## Post #28
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-30T16:48:52+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

Update your plugin and see how they look. The toth fighter side barrels look correct now and the deathboat looks ok to me though i don't quite remember where the location of the top turret is supposed to be.
## Post #29
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-30T17:18:29+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

> Reply from AceWell
>
> Update your plugin and see how they look. The toth fighter side barrels look correct now and the deathboat looks ok to me though i don't quite remember where the location of the top turret is supposed to be.

i use the last version of the plugin ... still the same ...
laserturrets left and right, are always under the cockpit instead on wings ...



same problems , for turrets, canons on some models

ChemBomber , wrongs positions of wings



correct position:
## Post #30
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-30T18:21:04+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

Those are fixed in latest plugin update.
## Post #31
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-30T18:54:16+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

i have uninstall all, delete folder, and reinstall ...
it work now, thks
## Post #32
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-08-31T19:22:47+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

[out]
## Post #33
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-26T18:29:09+00:00
- Post Title: Re: star wars : starfighter  .pmdl models

wrote a bms script for fun to mimic what the sfdepak.exe does to extract pak and pmdl files, reimport should work too  

```

get BNAME basename
idstring "Europa Packfile"
goto 0x15
get TABLE_OFFSET long
get TABLE_SIZE long
get FILES long
goto TABLE_OFFSET
for i = 0 < FILES
	get NAME_SIZE byte
	get NAME string
	get OFFSET long
	get SIZE long
	get UNK long
	string NAME p= "%s\%s" BNAME NAME 
	log NAME OFFSET SIZE
next i
```
