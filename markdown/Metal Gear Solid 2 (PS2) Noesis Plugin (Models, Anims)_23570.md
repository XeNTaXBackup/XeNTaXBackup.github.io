## Post #1
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-10T13:52:22+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

I've released a plugin which you can grab from the link below which will allow you to view textured models and animations from the game Metal Gear Solid 2 on the PS2. To view animations you have to select 'Prompt for Motion Archive' in the tool menu. You can get the plugin here;

[https://github.com/Jayveer/MGS-KMS-EVM-Noesis/releases](https://github.com/Jayveer/MGS-KMS-EVM-Noesis/releases)

The game uses 2 different formats for models, KMS and EVM, both are supported by the plugin.

To extract Face and Stage files you can use the plugin below, if everything is in the right place textures should auto-apply etc. I still need to do some work on the material flags and texture conversion in general.

[https://github.com/Jayveer/Arsenal/releases](https://github.com/Jayveer/Arsenal/releases)
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-03-11T13:33:45+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

I love these plugins, I only have one question: Is it possible to export the format to .SMD or .FBX and have the animations split up instead of all of them in one file? It's awfully difficult to split them up.. 
Also the weights on the MGS3 models are all messed up..

Great work however, this tool is godsend for every MGS fan out there!
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-11T15:55:19+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

Hi, yeah splitting up the animation is something I'd like to do, I asked in a previous thread how I could go about doing that with Noesis but didn't get a reply on it. I think I just need to dig into the API more. Do you have an example of an mgs3 file that has messed up weighting so I can look into it, thanks.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-03-11T17:10:02+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from JayK ↑Thu Mar 11, 2021 11:55 pm at Thu Mar 11, 2021 11:55 pm
>
> 
Hi, yeah splitting up the animation is something I'd like to do, I asked in a previous thread how I could go about doing that with Noesis but didn't get a reply on it. I think I just need to dig into the API more. Do you have an example of an mgs3 file that has messed up weighting so I can look into it, thanks.

Sure! Basically all models I exported had horrible rigging. Specifically I can pinpoint you:

```
slot/21/413aa8.mdl
slot/8/f395b8.mdl
slot/663/f49119.mdl
```


Hope this helps, keep up the great work!
## Post #5
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-11T17:33:14+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

Hm, I just tried with 'slot/8/f395b8.mdl' and it was fine for me. I'm wondering if it's a problem on export, what program are you exporting it into? Have you tried playing an animation for the file within Noesis? For that one you can pair it with 83eea9.mtar in stage/s045a, should be the animation for when you hold an unconscious enemy.

Also you should try using the dictionary.txt as well that  can be placed in the same directory as Shagohod.exe as it will convert a bunch of the hashes into real file names.
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-03-12T12:25:16+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from JayK ↑Fri Mar 12, 2021 1:33 am at Fri Mar 12, 2021 1:33 am
>
> 
Hm, I just tried with 'slot/8/f395b8.mdl' and it was fine for me. I'm wondering if it's a problem on export, what program are you exporting it into? Have you tried playing an animation for the file within Noesis? For that one you can pair it with 83eea9.mtar in stage/s045a, should be the animation for when you hold an unconscious enemy.

Also you should try using the dictionary.txt as well that  can be placed in the same directory as Shagohod.exe as it will convert a bunch of the hashes into real file names.

I'm trying to get them into Blender but the insanely long animations make me have 0.73 fps, so I try to import them in 3DS Max. As for rigging it's the same no matter what format I export it into and no matter which software I use to import.
## Post #7
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-12T17:22:57+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

Have you tried playing an animation in Noesis directly? Just trying to find out where exactly this problem is happening.
## Post #8
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2021-03-12T19:13:34+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from Pepsee ↑Fri Mar 12, 2021 8:25 pm at Fri Mar 12, 2021 8:25 pm
>
> ...

Here is how I would do it:
[https://youtu.be/j1BfsEbVc_c](https://youtu.be/j1BfsEbVc_c)

The Notepad++ with Regex part is just to match my textures location.

Don't forget to export WITHOUT the "-fbxascii" parameter from Noesis because Blender only supports BINARY FBX, not ASCII FBX.
I forgot how to change animations FPS in Blender so I also opened into Marmoset.
## Post #9
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-12T19:21:15+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from devilsnake88 ↑Sat Mar 13, 2021 3:13 am at Sat Mar 13, 2021 3:13 am
>
> 
Pepsee wrote: ↑Fri Mar 12, 2021 8:25 pm...


Here is how I would do it:
https://youtu.be/j1BfsEbVc_c

Ah  thanks for this, so by rigging you meant the textures? Sorry, I usually relate rigging to bones/weight. I did a new release that should auto apply textures, it appears I needed to explicitly put the extension on the filename when making a noetexture. The updated version is on the top of the release page.
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-03-26T22:42:10+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from JayK ↑Sat Mar 13, 2021 3:21 am at Sat Mar 13, 2021 3:21 am
>
> 
devilsnake88 wrote: ↑Sat Mar 13, 2021 3:13 am
Pepsee wrote: ↑Fri Mar 12, 2021 8:25 pm...


Here is how I would do it:
https://youtu.be/j1BfsEbVc_c


Ah  thanks for this, so by rigging you meant the textures? Sorry, I usually relate rigging to bones/weight. I did a new release that should auto apply textures, it appears I needed to explicitly put the extension on the filename when making a noetexture. The updated version is on the top of the release page.

Will there be Metal Gear Solid 1 support for animations? That'd be really awesome.
## Post #11
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-27T02:09:41+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

Yeah, the only thing I have left for mgs1 animations is the position bitstream, but it looks fine without it as well so I may just end up releasing it without that.
## Post #12
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-29T15:25:19+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

Just wanted to let you know about something


For some reason, the textures on the Mass Produced Ray seem to display weirdly in Noesis (mostly an invisible texture issue.)
[https://imgur.com/a/mYWSGle](https://imgur.com/a/mYWSGle)
## Post #13
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-29T20:35:25+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

And just to clarify, this also happens with the Prototype Ray too.

And in the Prototype's case, it also seems to be missing textures.

[https://imgur.com/a/tg48XBG](https://imgur.com/a/tg48XBG)
## Post #14
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-30T10:51:33+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

That could also be related to me not decompressing the Tri file properly. As I think that's happening with a few textures.
## Post #15
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-03-30T13:23:32+00:00
- Post Title: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from JayK ↑Thu Mar 11, 2021 11:55 pm at Thu Mar 11, 2021 11:55 pm
>
> 
Hi, yeah splitting up the animation is something I'd like to do, I asked in a previous thread how I could go about doing that with Noesis but didn't get a reply on it. I think I just need to dig into the API more. Do you have an example of an mgs3 file that has messed up weighting so I can look into it, thanks.

Single fbx file with the animations split inside instead of a single one long animation : -fbxmultitake
One fbx file per animation : -animoutex .noefbxmulti

You can either tell the user to put these manually in the advanced options or put them automatically using your plugin's options and the following function [https://github.com/Joschuka/Project-G1M ... ce.cpp#L65](https://github.com/Joschuka/Project-G1M/blob/main/Source/Private/Source.cpp#L65)
## Post #16
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-30T19:09:06+00:00
- Post Title: Re: Metal Gear Solid 2 (PS2) Noesis Plugin (Models, Anims)

> Reply from Joschka ↑Tue Mar 30, 2021 9:23 pm at Tue Mar 30, 2021 9:23 pm
>
> 

Single fbx file with the animations split inside instead of a single one long animation : -fbxmultitake
One fbx file per animation : -animoutex .noefbxmulti

You can either tell the user to put these manually in the advanced options or put them automatically using your plugin's options and the following function https://github.com/Joschuka/Project-G1M ... ce.cpp#L65

That is awesome, thanks a lot for that info.
