## Post #1
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-21T23:20:23+00:00
- Post Title: Mortal Kombat 9 uModel

I am having issues extracting the models from the 360's .xxx packages.

Whenever I attempt to extract something, I am given an error similar to this

******** Startup.xxx ********

ERROR: Wrong tag in package: 6E8A5276
FPackageFileSummary<<:Ver=0/0 <- UnPackage::UnPackage:Startup.xxx, game=0 <- UnPackage::LoadPackage:Startup.xxx <- Main

I am using this uModel command- "umodel -noanim -extract Startup.xxx"

Any help would be appreciated!
## Post #2
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-04-21T23:30:49+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from Alexis
>
> I am having issues extracting the models from the 360's .xxx packages.

Whenever I attempt to extract something, I am given an error similar to this

******** Startup.xxx ********

ERROR: Wrong tag in package: 6E8A5276
FPackageFileSummary<<:Ver=0/0 <- UnPackage::UnPackage:Startup.xxx, game=0 <- UnPackage::LoadPackage:Startup.xxx <- Main

I am using this uModel command- "umodel -noanim -extract Startup.xxx"

Any help would be appreciated!

Download this:

[http://www.gildor.org/smf/index.php/topic,330.0.html](http://www.gildor.org/smf/index.php/topic,330.0.html)

Put the UEV in the same folder as the GUI program and assign the path folder where the packages are and then select -noanim, after that just do right click and select export and that's all. UEV doesn't support MK9 animations.
## Post #3
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-21T23:40:44+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from maniacoloco
>
> Alexis wrote:I am having issues extracting the models from the 360's .xxx packages.

Whenever I attempt to extract something, I am given an error similar to this

******** Startup.xxx ********

ERROR: Wrong tag in package: 6E8A5276
FPackageFileSummary<<:Ver=0/0 <- UnPackage::UnPackage:Startup.xxx, game=0 <- UnPackage::LoadPackage:Startup.xxx <- Main

I am using this uModel command- "umodel -noanim -extract Startup.xxx"

Any help would be appreciated!

Download this:

http://www.gildor.org/smf/index.php/topic,330.0.html

Assign the path folder where the packages are and then select -noanim, after that just do right click and select export and that's all. UEV doesn't support MK9 animations.

Sadly, Still no luck. I get the Same errors. Oddly Enough, I can extract the sample packages posted on Gildor's forums... But I cannot extract my own.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-22T00:37:23+00:00
- Post Title: Mortal Kombat 9 uModel

if its xbox 360 add the -lzo option. so for mk9


c:\umodel\umodel.exe -lzo -noanim c:\package.xxx
## Post #5
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-22T00:44:22+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from chrrox
>
> if its xbox 360 add the -lzo option. so for mk9


c:\umodel\umodel.exe -lzo -noanim c:\package.xxx

Yes, It is for the 360... The -lzo doesn't work either. It is odd... I can extract the 'Char_Jade.xxx" that I obtained from Gildor's forums... But I cannot extract the same file that I have extracted from the disc.

Both files are identical in size.

Do the packages need to be decompressed prior to use like Soul Calibur? 

I can upload both 'Jade' Files if needed.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-22T01:13:37+00:00
- Post Title: Mortal Kombat 9 uModel

how did you dump it from your xbox.
## Post #7
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-22T01:22:24+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from chrrox
>
> how did you dump it from your xbox.

I am using the marvel group's dump.. I have no way to dump my copy from my slim Xbox... Unless You can somehow dump a usb install.
## Post #8
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-04-22T06:29:48+00:00
- Post Title: Mortal Kombat 9 uModel

You could create an iso of your game disk and then extract the content with wx360.
Anyway have you tried with an hex editor to understand if there are differences between these two files ?
## Post #9
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-22T12:17:32+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from Ares722
>
> You could create an iso of your game disk and then extract the content with wx360.
Anyway have you tried with an hex editor to understand if there are differences between these two files ?

I would love to create my own Iso, but I don't have the means... I don't have a modified Xbox or anything like that.
## Post #10
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-04-22T17:13:52+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from Alexis
>
> 
I would love to create my own Iso, but I don't have the means... I don't have a modified Xbox or anything like that.

You don't need to a modified xbox to create an iso from your disk. You can do this with a normal pc. 
This guide is only an example of what you can find on the web:

[http://www.ehow.com/how_6737051_extract ... -disc.html](http://www.ehow.com/how_6737051_extract-file-xbox-360-disc.html)
## Post #11
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-22T19:23:51+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from Ares722
>
> Alexis wrote:
I would love to create my own Iso, but I don't have the means... I don't have a modified Xbox or anything like that.

You don't need to a modified xbox to create an iso from your disk. You can do this with a normal pc. 
This guide is only an example of what you can find on the web:

http://www.ehow.com/how_6737051_extract ... -disc.html

I am pretty certain that the tutorial you have posted won't work. I know most standard PC drives will not see the entire 360 game disc. 

I would love to be mistaken, though...
## Post #12
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-04-23T07:04:47+00:00
- Post Title: Mortal Kombat 9 uModel

Just use XboxBackup Creator, mount the X360Iso then Image Browse and extract them.
## Post #13
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-23T15:45:18+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from CMihai
>
> Just use XboxBackup Creator, mount the X360Iso then Image Browse and extract them.

As in... Place the disc in the PC dvd drive (unmodified)?
## Post #14
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-04-24T11:00:10+00:00
- Post Title: Mortal Kombat 9 uModel

yes^^ ....for the xbox360 games it works. They are simply dvd double layer.
## Post #15
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-24T14:49:14+00:00
- Post Title: Mortal Kombat 9 uModel

> Reply from Ares722
>
> yes^^ ....for the xbox360 games it works. They are simply dvd double layer.

Strange last time I tried... I could only see Audio_ts and Video_ts. So. I should be able to load my retail disc, and Use Xbox backup creator to create a usable image?!
## Post #16
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-05-02T14:17:06+00:00
- Post Title: Re: Mortal Kombat 9 uModel

i know this thread is slightly old now, so i apologise for bumping but i thought id speak up anyway.

The marvel groups dump of MK works perfectly fine with umodel. i also didn't use the -lzo tag either,  the only tags i used was " -export -all -noanim "  i copied the main texture archive to the same folder as umodel, then copied each .xxx file i wanted to extract to umodels folder also, then i ran umodel. It extracted first go perfectly.
## Post #17
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-05-02T22:32:00+00:00
- Post Title: Re: Mortal Kombat 9 uModel

> Reply from Nobby
>
> i know this thread is slightly old now, so i apologise for bumping but i thought id speak up anyway.

The marvel groups dump of MK works perfectly fine with umodel. i also didn't use the -lzo tag either,  the only tags i used was " -export -all -noanim "  i copied the main texture archive to the same folder as umodel, then copied each .xxx file i wanted to extract to umodels folder also, then i ran umodel. It extracted first go perfectly.

Strange! I just ended up using another dump. 

Any luck on how the textures are set up... Obviously you have the diffuse, spec and normals (DXT5)... but there are a few things that have me confuzzled.

The diffuse texture has an alpha channel. I am not sure what it's main use in engine is.. (Seems to be Color change mask).

The Specular color texture also has an alpha channel. It is hard to tell what it's exact purpose is. (Perhaps it is the overall specular mask, or gloss texture, inverted?).

On top of those, the Pmsk textures. They almost seem to mask off the detail bumps... I do know that the alpha is an AO.
## Post #18
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-05-03T01:08:45+00:00
- Post Title: Re: Mortal Kombat 9 uModel

> Reply from Alexis
>
> 
Strange! I just ended up using another dump. 

Any luck on how the textures are set up... Obviously you have the diffuse, spec and normals (DXT5)... but there are a few things that have me confuzzled.

The diffuse texture has an alpha channel. I am not sure what it's main use in engine is.. (Seems to be Color change mask).

The Specular color texture also has an alpha channel. It is hard to tell what it's exact purpose is. (Perhaps it is the overall specular mask, or gloss texture, inverted?).

On top of those, the Pmsk textures. They almost seem to mask off the detail bumps... I do know that the alpha is an AO.
As far as i can tell the pmsk files are mixer maps. Ex, the red controls one thing, the blue controls another and same with the green. similar to what soul calibur has. not too sure about the alpha maps on the diffuse and spec, my best guess would be, they have transparent parts to the models ( such as hair or clothing ) To be honest i haven't looked into it much, i only extracted them a couple of days ago and haven't had much chance to play with them since.

Have a look at [THIS](http://forum.xentax.com/viewtopic.php?p=44157#p44157)... It is a tutorial for texturing Soul Calibur4 models correctly  ( which also uses mix maps ) it might explain it a little better than i can    as far as i can tell it should be a fairly similar process.

Good luck..
Nobby
## Post #19
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-05-03T01:48:35+00:00
- Post Title: Re: Mortal Kombat 9 uModel

> Reply from Nobby
>
> Alexis wrote:
Strange! I just ended up using another dump. 

Any luck on how the textures are set up... Obviously you have the diffuse, spec and normals (DXT5)... but there are a few things that have me confuzzled.

The diffuse texture has an alpha channel. I am not sure what it's main use in engine is.. (Seems to be Color change mask).

The Specular color texture also has an alpha channel. It is hard to tell what it's exact purpose is. (Perhaps it is the overall specular mask, or gloss texture, inverted?).

On top of those, the Pmsk textures. They almost seem to mask off the detail bumps... I do know that the alpha is an AO.
As far as i can tell the pmsk files are mixer maps. Ex, the red controls one thing, the blue controls another and same with the green. similar to what soul calibur has. not too sure about the alpha maps on the diffuse and spec, my best guess would be, they have transparent parts to the models ( such as hair or clothing ) To be honest i haven't looked into it much, i only extracted them a couple of days ago and haven't had much chance to play with them since.

Have a look at THIS... It is a tutorial for texturing Soul Calibur4 models correctly  ( which also uses mix maps ) it might explain it a little better than i can    as far as i can tell it should be a fairly similar process.



Good luck..
Nobby

Thanks for the input. Only the hair and damage textures seem to use the alphas for opacity. I figured the pmsk were masks, but who knows for what.

I have a half decent Kahn render from random fiddling, haha. The spec alpha seems to be an inverted reflection mask.

[http://i1086.photobucket.com/albums/j45 ... nder-2.jpg](http://i1086.photobucket.com/albums/j458/tflalexis/kahnrender-2.jpg)
## Post #20
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-05-03T16:32:00+00:00
- Post Title: Re: Mortal Kombat 9 uModel

Liking the picture, very swish    
I really should get to work with setting up all the characters and playing arenas. but lazyness prevails hehe  plus ive just got around to installing test drive unlimited 2 ( first game ive got legit in about 2 years ) so im  gonna be hammering through that for the next few weeks.
## Post #21
- Username: XLAX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Oct 04, 2011 8:18 am
- Post datetime: 2011-11-11T00:21:10+00:00
- Post Title: Re: Mortal Kombat 9 uModel

is there any easier way to import the textures in 3dsmax rather then doing it manually?
## Post #22
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-12T01:19:18+00:00
- Post Title: Re: Mortal Kombat 9 uModel

> Reply from XLAX
>
> is there any easier way to import the textures in 3dsmax rather then doing it manually?

Yep, just select the area you want to texture by selecting an alement of the mesh (editable mesh > element) and drag and drop the texture you want from windows explorer.
## Post #23
- Username: XLAX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Oct 04, 2011 8:18 am
- Post datetime: 2011-11-12T04:20:08+00:00
- Post Title: Re: Mortal Kombat 9 uModel

so no matter what i do,  importing mk9 models in max will never be like a typical ue3 game whereas all that would need to be done is to extract the mesh with ueviewer then import into max and the models would be textured and ready to go.

its pretty wierd when using the actorx importer in max.
when importing a character it will ask for over 100 materials(material_1,material_2,etc...).
as far as selecting an element on the mesh, if you export as an obj from noesis first then import into max the model will already be broken up by element so i guess it makes it a bit easier to texture from that standpoint.
## Post #24
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-11-14T13:34:45+00:00
- Post Title: Re: Mortal Kombat 9 uModel

> Reply from XLAX
>
> so no matter what i do,  importing mk9 models in max will never be like a typical ue3 game whereas all that would need to be done is to extract the mesh with ueviewer then import into max and the models would be textured and ready to go.

its pretty wierd when using the actorx importer in max.
when importing a character it will ask for over 100 materials(material_1,material_2,etc...).
as far as selecting an element on the mesh, if you export as an obj from noesis first then import into max the model will already be broken up by element so i guess it makes it a bit easier to texture from that standpoint.

Yep, MK9 materials are not fully supported by umodel.
