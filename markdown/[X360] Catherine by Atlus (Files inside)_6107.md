## Post #1
- Username: IronShoujo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 13, 2011 2:31 pm
- Post datetime: 2011-02-20T07:06:17+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-20T07:50:11+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

This is in regards to the PS3 version, it probably applies to 360 too.

.pac files are generic Atlus containers (one of them described in [the Trauma Center thread](http://forum.xentax.com/viewtopic.php?f=10&t=5918)).
.nif files are Gamebryo models, obviously. They probably are in a newer format/version which NifSkope probably can't function on.
.dds are little-endian DDS textures (I was surprised they didn't use big-endian for DDS, maybe different for 360 version?)
.sp2 are Atlus sprite containers, they'll contain DDS data among others.
.bmd are Atlus binary message data (contains dialogue / subtitles / etc), new format for Catherine.
.bf are Atlus binary scripts, same as earlier games (like Persona 3 Portable) but I have not looked into it in detail yet.
## Post #3
- Username: IronShoujo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 13, 2011 2:31 pm
- Post datetime: 2011-02-20T11:20:47+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

Thank you. I've been able to extract the .PAC files and inside them were .kf files and a .kfm.

I have no idea what those are but I managed to open the .kf files. The .kfm though, like you said, NifSkope doesn't support the version 20.6.0.b

Any idea what I should do to the .nif and .kfm files so I could properly export and use them? To be honest though, I only need the textures and the models. The .DDS files, I also have no clue what to do with them. You mentioning that they are little-endian probably means I'd have to convert them as well so programs like Photoshop, 3DS/Maya/Blender can open them properly.

Again, thanks for the help!

Here's the .kfm and .kf files if you wanna tinker around with it.
[kfm and kf files.rar](https://xentaxbackup.github.io/file/3949_kfm and kf files.rar)
## Post #4
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-02-20T17:19:58+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

kfm are motions and nif is a new version, all files are little edian , i extracted this one manually:



maybe nifskope authors can add support to it by changing the xml format? ask them :p
## Post #5
- Username: IronShoujo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 13, 2011 2:31 pm
- Post datetime: 2011-02-21T03:31:36+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

May I ask how you extracted the model and textures manually? Also, did you find out if the mesh and the textures can be exported for Maya/Blender/3DSMax? Thank you for sharing!
## Post #6
- Username: Tensh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 22, 2011 7:36 pm
- Post datetime: 2011-02-22T11:47:44+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

Hey, guys.
Is there a way to open .bmd files?

I want to do a  translation for PS3 version, it's too long to wait for september release. -_-

I'm kinda new at all these. 
Can I pack all data to .cpk back?
I used script from [here](http://forum.xentax.com/viewtopic.php?f=10&t=4220) to unpack it, I had an error at the end, something about offset, but looks like all files is alright.
## Post #7
- Username: IronShoujo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 13, 2011 2:31 pm
- Post datetime: 2011-02-23T05:57:58+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

Can anyone make a script for QuickBMS that can extract the .nif files please? Thank you!
## Post #8
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-02-25T11:23:13+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

nif is the model file lol it doesn't need to be extracted
## Post #9
- Username: IronShoujo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 13, 2011 2:31 pm
- Post datetime: 2011-02-26T01:25:49+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

Good lord, I just realized how hard I failed. Well, I guess I'll be waiting until the NifSkope authors update their program. Or is that even gonna happen?
## Post #10
- Username: khaze
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 27, 2011 1:57 am
- Post datetime: 2011-02-26T18:06:22+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

Hello everyone.

I started a "quest" to translate Catherine over at psx-scene.
We made some progress already, so I'd like to invite those of you who may be interested and request some help from the more experience ones 

[http://psx-scene.com/forums/f180/cather ... les-81355/](http://psx-scene.com/forums/f180/catherine-subtitles-81355/)

We're having some trouble figuring out the *.bmd files used for cutscene substiles I think  

Thanks
## Post #11
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2011-03-09T18:36:11+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

> Reply from khaze
>
> Hello everyone.

I started a "quest" to translate Catherine over at psx-scene.
We made some progress already, so I'd like to invite those of you who may be interested and request some help from the more experience ones 

http://psx-scene.com/forums/f180/cather ... les-81355/

We're having some trouble figuring out the *.bmd files used for cutscene substiles I think  

Thanks

Found this can't vouch for it though.
[http://forum.ragezone.com/f197/bmd-edit ... es-348339/](http://forum.ragezone.com/f197/bmd-editor-1-04-files-348339/)

And file extension info if you need it
[http://filext.com/file-extension/BMD](http://filext.com/file-extension/BMD)

I'm also working on translating a game, but its for the X360 "Akatsuki no Amaneka to Aoi Kyojin" I've already translated the scripts and images for it just need to find a way to inject/or/pack them back into the .bin file.  So I'm in the same boat as you are w/ Catherine XD
## Post #12
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-20T01:12:10+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

Sorry for bumping old thread but How do I get the model files?
## Post #13
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-08-29T19:16:33+00:00
- Post Title: [X360] Catherine by Atlus (Files inside)

> Reply from DOTAPRINCE
>
> Sorry for bumping old thread but How do I get the model files?

If I remember correctly, you open up Catherine's iso in wx360, then extract the data.cvm file. Use a program like Apache 3 to extract the cvm file, and there should be a folder called "Character"

The models are the .nif files, use the blender script to import them into blender, the textures will be extracted to the folder the model is in in dds format. Some of the models won't import correctly, no idea why.
