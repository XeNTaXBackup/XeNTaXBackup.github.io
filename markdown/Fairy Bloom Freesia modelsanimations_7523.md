## Post #1
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-18T13:51:46+00:00
- Post Title: Fairy Bloom Freesia models/animations

If it's not too much trouble, I'd like to ask if anyone here would be able to write a converter or script to unpack/import the game's models/animations to a common 3d software package. I looked around the internet and couldn't find any information on the formats used in this game, but they look pretty simple (ie. the mesh data is written in plain text). I just don't know how to write a converter myself.

The game's assets are inside simple uncompressed container files, with the index at the start. The index looks simple, with the filename, hex address and file size for each file. The textures are in DDS format. I've uploaded the container file that has models/textures/animations, and also a few character model/animation files that I pulled out using a hex editor.
[http://www.sendspace.com/filegroup/ChY6 ... qr4uHCbAuF](http://www.sendspace.com/filegroup/ChY6CfTKNuVTG83PAKYGs3qr4uHCbAuF)

Here's an image of the models from the game:
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-19T05:59:05+00:00
- Post Title: Fairy Bloom Freesia models/animations

I've seen that file format before; I think finale00 posted a game archive that used that strange textfile-like format before. I will put it on my todo list.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-20T05:11:15+00:00
- Post Title: Fairy Bloom Freesia models/animations

well a new update of this game, anyway all files in 1 package :S animations,textures and mesh o_O

[http://edelweiss.skr.jp/works/fbfreesia/index.html](http://edelweiss.skr.jp/works/fbfreesia/index.html)
## Post #4
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-20T13:01:50+00:00
- Post Title: Fairy Bloom Freesia models/animations

> Reply from howfie
>
> I've seen that file format before; I think finale00 posted a game archive that used that strange textfile-like format before. I will put it on my todo list.

Thanks  The files I uploaded are from version 1.05, which should be the latest.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T02:41:39+00:00
- Post Title: Fairy Bloom Freesia models/animations

I am currently working on it now. Pretty easy format. These developers are either nice or stupid because they could cut down the size of their model files by 75% if they switched to binary instead of text. Are the TGP files in the demo the same as the ones in the full version?
## Post #6
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-21T10:49:31+00:00
- Post Title: Fairy Bloom Freesia models/animations

Thanks for the update. I get the impression that most Japanese PC games just leave files in their original format. The demo's TGP files are a lot smaller, so they probably only contain what's used in the demo. By the way, this game is a really great platformer/beat'em up. It starts out slow, but gets much better. The animations, sounds, special effects, etc. are all done very well.

Here's a list of what I've found in each archive:
0000.tgp = Sounds, effects and interface. Sound is OGG, interface is DDS/PNG. I can't tell what format the effects are in. Didn't see a header or any text. The effects are fully 3d and the color of them seems to be defined either by texture (in some cases), or in the effect file. There's one general font in PNG format, but the color gradient for the font is separate from the font table.
0001.tgp = Game script data. Unknown format. The scripts should contain stuff like the story mode dialogue/scenes, character/animation/attack properties, effect triggers and also the menu/interface text that isn't in the executable. I can't seem to find those things anywhere else.
0010.tgp = Character/enemy models, animations, poses (?), textures, eye/mouth textures, facial animation, etc. Weapons are attached to the character models. Model and animation data are in plain text. Textures in DDS. Eye info, facial animation and poses are in small, unknown formats. It's likely that each byte corresponds to position, texture number or frame, but I haven't touched it.
01xx.tgp = Stage data (models, DDS textures).
020x.tgp = Story mode character art (DDS).
025x/026x.tgp = Story mode environment art (PNG).
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T16:24:52+00:00
- Post Title: Fairy Bloom Freesia models/animations

Put exe in same directory where all TGP files are.
Must have Visual Studio 2010 redistributables installed.
It will extract all files from the TGP archives.
Then it will scan all subdirectories for MDL files and process them into LS files.
Program puts LS files in same directory as MDL files.
Run LS files in LightWave.
Manually apply textures (sorry, no bones or animations, don't have time to finish this... going to disappear for a few months to finish thesis due in December).
Laterz everyone!


[template.7z](https://xentaxbackup.github.io/file/4798_template.7z)
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T16:29:17+00:00
- Post Title: Fairy Bloom Freesia models/animations

source for those who care.
[source.7z](https://xentaxbackup.github.io/file/4799_source.7z)
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-21T16:33:21+00:00
- Post Title: Fairy Bloom Freesia models/animations

wow thats cool howfie, thanks a lot for great contribution man

PD: well I try import it and don't have luck, this is the error.
[LS Import.jpg](https://xentaxbackup.github.io/file/4800_LS Import.jpg)
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T16:47:52+00:00
- Post Title: Fairy Bloom Freesia models/animations

what are the steps that you take to run it? what version of LW are you running to?
does it work on the demo files but not on the full version files?
i can make a video if you like.
## Post #11
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-21T16:56:34+00:00
- Post Title: Fairy Bloom Freesia models/animations

I didn't realise you were so busy, howfie. Thanks for your hard work, and good luck with your thesis!
If anyone would like to do the bones/animation, please do
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-21T17:10:17+00:00
- Post Title: Fairy Bloom Freesia models/animations

> Reply from howfie
>
> what are the steps that you take to run it? what version of LW are you running to?
does it work on the demo files but not on the full version files?
i can make a video if you like.well yes my mistake, I use full files, about program I use 3D Studio Max 9, it's possible make tool for get OBJ files? because I don't have VS or VB for write it now, and honestly i'm not good compiling x_X
## Post #13
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T17:36:29+00:00
- Post Title: Fairy Bloom Freesia models/animations

next game i do i will do OBJ as well; seems easy enough.
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T17:42:18+00:00
- Post Title: Fairy Bloom Freesia models/animations

video is coming up 
[http://www.youtube.com/watch?v=8ZatI9BImJM](http://www.youtube.com/watch?v=8ZatI9BImJM)
## Post #15
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-21T18:32:23+00:00
- Post Title: Fairy Bloom Freesia models/animations

I tried using Lightwave demo version but it only imported a small part of the meshes I tried it on. Probably a limitation of the demo version.
To be honest, I'd also prefer it as OBJ or FBX. I don't want to bug you about it, though.
## Post #16
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-21T18:39:30+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

> Reply from RandomRipper
>
> I tried using Lightwave demo version but it only imported a small part of the meshes I tried it on. Probably a limitation of the demo version.
To be honest, I'd also prefer it as OBJ or FBX. I don't want to bug you about it, though.yes right, the registration process is a pain ass, I do it but really in every boot when turn on your PC need press F8 is not a good way anyawy thanks.
## Post #17
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T20:16:51+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

I'll see what i can do about obj.
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T21:58:25+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

obj support is almost done.
trying to figure out how to get dds alpha channels to work in obj file. anyone know how as I am not so great in Maya/Max?
## Post #19
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-21T23:23:26+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

Maya's transparency doesn't quite work properly a lot of the time. I don't know if that's been fixed in 2011/2012. Try turning on high quality rendering mode. If it's not transparent at all, you;ll need to go to hypershade and check whether the materials have transparency. If they don't, you'll need to assign the DDS to them. Even then, it might not show up properly.
## Post #20
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T23:40:26+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

yep, i tried all that and more and still no go. i am updating my ATI drivers and upgrading to SP1. in the meantime... an obj and mtl file are generated now as well.
[template.7z](https://xentaxbackup.github.io/file/4801_template.7z)
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-21T23:49:49+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

Actually, if I just reopen the textures in the File node, transparency works! Buggy ass software lol!
## Post #22
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-21T23:55:09+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

Thanks for the update.
Reopening it probably used Maya's default in that it connects the texture to both color and transparency automatically. If you load textures in certain ways, it doesn't always do that. I forget which ways do and which don't. There's also an "alpha is luminance" checkbox under the texture "color balance" or something. It sometimes affects whether transparencies work or not, and I think it also sometimes turns itself on and off.
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-22T00:10:24+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

new source for those that want to dwelve into code
[template.7z](https://xentaxbackup.github.io/file/4802_template.7z)
## Post #24
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-22T01:56:51+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

thanks a lot howfie, really grateful for this awesome work, you did a great job here I appreciate it.
## Post #25
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-22T07:01:55+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

I really appreciate it as well, thanks a bunch!
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-22T07:19:45+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

no problem guys. in december when i start messing with formats again if no one picks this up i will finish the bones and animations.
## Post #27
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-22T16:01:18+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

> Reply from howfie
>
> no problem guys. in december when i start messing with formats again if no one picks this up i will finish the bones and animations.perfectly bro, very interesting, about bones and animations would be nice., cya take care.
## Post #28
- Username: RandomRipper
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 16, 2011 4:24 pm
- Post datetime: 2011-10-22T21:23:52+00:00
- Post Title: Re: Fairy Bloom Freesia models/animations

> Reply from howfie
>
> no problem guys. in december when i start messing with formats again if no one picks this up i will finish the bones and animations.
Awesome! Looking forward to it.
