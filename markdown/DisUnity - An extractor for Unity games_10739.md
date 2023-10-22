## Post #1
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-09-01T18:07:42+00:00
- Post Title: DisUnity - An extractor for Unity games

I've been working on an asset extraction tool for Unity-based games, since I needed such a tool for two Unity games I have. Moreover, the game engine has become very popular, so the unpacker should theoretically work with thousands of different games.

Right now, it supports text, audio clips, most textures (including movie textures), fonts and [substances](http://www.allegorithmic.com/) from Unity versions ranging from 2.6 to 4.2. Support for static meshes is also planned, but will be added later, due to the complexity of the mesh data.

There's no GUI for the tool yet, since it's still in an early experimental stage. So if you want to use it, you should have at least basic knowledge with the command line interface. 

Both source code and compiled builds are available on GitHub [here](https://github.com/ata4/disunity). It is written in Java, so you'll also need to install the [Java VM](http://www.java.com/).

For a quick start, you can use DisUnity like this:

```
disunity "resources.assets"
```

(also works with .unity3d files)

which is equivalent to:

```
disunity -c extract "resources.assets"
```


If that doesn't work, try this:

```
java -jar disunity.jar "resources.assets"
```


The files should then appear in a subfolder with the same name as the file. You can also try to play with the other parameters and commands that are listed with the -h parameter, but I think most normal people won't need these right now.

Download on GitHub
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-09-11T18:16:48+00:00
- Post Title: DisUnity - An extractor for Unity games

Are the images automatically converted?
## Post #3
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-09-11T23:22:20+00:00
- Post Title: DisUnity - An extractor for Unity games

Image textures are extracted as DDS files. However, they're not always loaded correctly with the Nvidia Photoshop DDS plugin for some reasons. In that case, the [Nvidia Texture Tools](https://developer.nvidia.com/content/texture-tools-208-64-bit) should be able to decompress them.

In other news, I uploaded version 0.1.1 and also updated the readme on GitHub, which now explains the other commands.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-09-13T18:05:35+00:00
- Post Title: DisUnity - An extractor for Unity games

Can you put in an option to convert them to PNG's?
While I can convert DDS using noesis it's just an extra step for the most part.
## Post #5
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-09-14T14:42:11+00:00
- Post Title: DisUnity - An extractor for Unity games

Not sure yet. If I find a good DDS library for Java, then I could add it as an option.
## Post #6
- Username: Acewell
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-14T18:02:16+00:00
- Post Title: DisUnity - An extractor for Unity games

You could write a Noesis script to invoke his tool, then pick up and convert all the output images. There's a script on the repo that invokes ffmpeg to display codec info, that should be a good example to go from.
## Post #7
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-10-18T13:00:54+00:00
- Post Title: DisUnity - An extractor for Unity games

Thanks for the tool, barracuda, but there's a problem. I added your rep to my github acc, but still I can't find disunity.jar in it. And without it I cannot even try your tool. 

Edit: Nevermind, I've found the compiled ones.
## Post #8
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-12-11T18:10:17+00:00
- Post Title: DisUnity - An extractor for Unity games

[DisUnity v0.1.3](https://github.com/ata4/disunity/releases/tag/v0.1.3) is out now. It can now extract meshes, at least from newer Unity 4 games, and there's also a bunch of bugs fixed.
## Post #9
- Username: mikaslayton
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 18, 2013 12:24 pm
- Post datetime: 2013-12-18T05:35:57+00:00
- Post Title: DisUnity - An extractor for Unity games

Hey barracuda,

First of all, thank you so much for this amazing program.  

Second, I'm having problems extracting models from a Unity Player.  I type:

java -jar disunity.jar "resources.assets"

and I get a response from disunity like this:  "resources assets file not found"

I have the player open in a tab in firefox.  Am I doing anything wrong?  Will extraction work with certain web browsers over others?  

Sorry about the rookie/newbie question.  If anyone else can help me other than barracuda (to save them the trouble), I'd appreciate the help.  I know little java, but have done a lot of searching on Google to figure out how to get things running.  ...just need a little tutorial for a rookie, perhaps, to help me with my issue.  

Thanks again, barracuda/everyone.
## Post #10
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-12-18T07:38:38+00:00
- Post Title: DisUnity - An extractor for Unity games

Is the resources.assets in the same folder as disunity.jar? If not, then you need to specify the full path as argument, like C:\ProgramFiles\YourGame\resources.assets (assuming you're using Windows). The player also doesn't need to run in the background, DisUnity is completely standalone. You just need to download the .assets or .unity3d files you want to extract.
## Post #11
- Username: mikaslayton
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 18, 2013 12:24 pm
- Post datetime: 2013-12-18T14:12:36+00:00
- Post Title: DisUnity - An extractor for Unity games

Hey barracuda,

Thank you so much for the personal response.  It really set me in the right direction.  

If you don't mind, I have one final question.  I now have the .unity3d file.  I loaded it up in disunity and extracted, but a mesh didn't extract.  I simply got 'Shader' and 'Texture2D'.  I then tried to 'unbundle' so I could examine the resource.assets file within the .unity3d file, thinking that, perhaps, this was the way to get the model -- run an extract on the resource.assets file.

Neither direction got me anything other than folders and files for 'Shader' and 'Texture2D'.  I was hoping to get a .obj file, as this is possible in the latest disunity, correct?  

I'm not sure which version of Unity this .unity3d file is.  Perhaps that is the problem?  

And pardon the newbie question, but if I have the shaders, I can't somehow view the model yet, right?  I need the mesh, correct?  

Sorry to be such a rookie.  :-/
## Post #12
- Username: blaar
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 03, 2011 3:12 pm
- Post datetime: 2013-12-19T23:13:51+00:00
- Post Title: DisUnity - An extractor for Unity games

Just want to say thanks. Tested on MW Tactics and it extracted the mesh with no problems.

Any future plans to have a GUI based interface ?

Once again great work and thanks.
## Post #13
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-12-23T09:38:41+00:00
- Post Title: DisUnity - An extractor for Unity games

> Reply from mikaslayton
>
> Hey barracuda,

Thank you so much for the personal response.  It really set me in the right direction.  

If you don't mind, I have one final question.  I now have the .unity3d file.  I loaded it up in disunity and extracted, but a mesh didn't extract.  I simply got 'Shader' and 'Texture2D'.  I then tried to 'unbundle' so I could examine the resource.assets file within the .unity3d file, thinking that, perhaps, this was the way to get the model -- run an extract on the resource.assets file.

Neither direction got me anything other than folders and files for 'Shader' and 'Texture2D'.  I was hoping to get a .obj file, as this is possible in the latest disunity, correct?  

I'm not sure which version of Unity this .unity3d file is.  Perhaps that is the problem?  

And pardon the newbie question, but if I have the shaders, I can't somehow view the model yet, right?  I need the mesh, correct?  

Sorry to be such a rookie.  :-/
Yes, if there are supported models, the latests version should produce .obj files (or error messages, in case they're not supported). It's possible that the meshes are stored in a separate .unity3d file. Or maybe the game doesn't use any meshes at all, or they're generated procedurally. Is there a public, legal link to the game?

> Reply from blaar
>
> Just want to say thanks. Tested on MW Tactics and it extracted the mesh with no problems.

Any future plans to have a GUI based interface ?

Once again great work and thanks.
It's definitely planned, but the current code base isn't really suitable for that. At this stage, a CLI program is definitely easier to (re)write. Once the deserializer is mostly flawless, I could think about that.
## Post #14
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-12-24T12:00:18+00:00
- Post Title: DisUnity - An extractor for Unity games

@barracuda, it's works! Thank you for it! But i have a little problem.
I have unity game that have over 1000 little files inside with this header every of them (attached)
and i need to extract ALL files in one, like using UltraIso and create one iso file with all content inside (extract it together) or using hex split or association, you know...
so, your tool can ONLY extract one little file in once and each file in one directory, i need to extract big package, will be any fix for that? thanks
[screen.PNG](https://xentaxbackup.github.io/file/6873_screen.PNG)
## Post #15
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-12-24T14:49:03+00:00
- Post Title: DisUnity - An extractor for Unity games

Sorry for double post, but finally i figured out how to work with multiple files. So, in my game i have "download_root" folder with 1608 files without names and extensions, only named with hashes.
first three files:
```
000da68fbdc216e002ebc5bad84db238
00380e3b27f7aed490969dd980a98d71
```
1. start total commander, select all 1608 files, click "File - Multi-Rename Tool" and set custom extensions same for all files, like ".file"
will be like:Code: Select all0005fa49ffbf99e77797b64ab47d2010.file
000da68fbdc216e002ebc5bad84db238.file
00380e3b27f7aed490969dd980a98d71.file
2. again select all 1608 files in TC and click "mark - copy selected names to clipboard"
3. start notepad++, create new file, paste all names inside from clipboard, then push and hold "Alt+Shift+DownKey" on the first string at the beginning of all, then keep holding Alt+Shift push downkey many times to the end of the text file (don't select all text, be careful with last string), then unhold buttons and press "Alt+c", paste "java -jar disunity.jar " (WITH ONE SPACE white space i mean - after) and press ok button, you will see something like:Code: Select alljava -jar disunity.jar 000da68fbdc216e002ebc5bad84db238.file
java -jar disunity.jar 0005fa49ffbf99e77797b64ab47d2010.file
java -jar disunity.jar 00380e3b27f7aed490969dd980a98d71.file
4. Save your txt file as "run.bat" in tool directory, place all 1608 files files with custom extensions inside directory of this tool "disunity_v0.1.3", start run.bat and wait...
5. you will see many directories with extracted stuff, you can use windows 7 search tool to copy all textures in one directory by searching with ".dds" tag, view .dds files with Xnview tool, it's fastest way.
(attached result) he he
[T0051_hair_girl.png](https://xentaxbackup.github.io/file/6874_T0051_hair_girl.png)
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-24T20:34:53+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

anyone happen to know what type of swizzling Unity uses?
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-12-24T22:43:16+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

its not morton order?
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-24T23:05:03+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

yes, it is some kind of morton, but the morton i use didnt work perfect (though it works for other games like neptunia that use morton).  i could see chopped patterns after reordering. is there more than one way to implement z-order? i post sample pics when i get home.
## Post #19
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-12-25T07:50:11+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from SILENTpavel
>
> Sorry for double post, but finally i figured out how to work with multiple files. So, in my game i have "download_root" folder with 1608 files without names and extensions, only named with hashes.
first three files:Code: Select all0005fa49ffbf99e77797b64ab47d2010
000da68fbdc216e002ebc5bad84db238
00380e3b27f7aed490969dd980a98d711. start total commander, select all 1608 files, click "File - Multi-Rename Tool" and set custom extensions same for all files, like ".file"
will be like:Code: Select all0005fa49ffbf99e77797b64ab47d2010.file
000da68fbdc216e002ebc5bad84db238.file
00380e3b27f7aed490969dd980a98d71.file
2. again select all 1608 files in TC and click "mark - copy selected names to clipboard"
3. start notepad++, create new file, paste all names inside from clipboard, then push and hold "Alt+Shift+DownKey" on the first string at the beginning of all, then keep holding Alt+Shift push downkey many times to the end of the text file (don't select all text, be careful with last string), then unhold buttons and press "Alt+c", paste "java -jar disunity.jar " (WITH ONE SPACE white space i mean - after) and press ok button, you will see something like:Code: Select alljava -jar disunity.jar 000da68fbdc216e002ebc5bad84db238.file
java -jar disunity.jar 0005fa49ffbf99e77797b64ab47d2010.file
java -jar disunity.jar 00380e3b27f7aed490969dd980a98d71.file
4. Save your txt file as "run.bat" in tool directory, place all 1608 files files with custom extensions inside directory of this tool "disunity_v0.1.3", start run.bat and wait...
5. you will see many directories with extracted stuff, you can use windows 7 search tool to copy all textures in one directory by searching with ".dds" tag, view .dds files with Xnview tool, it's fastest way.
(attached result) he he
That's a complicated way to do it. Wildcards should work, too:

```

```


Or:

```

```


("should", because there's a bug in the JVM I'm currently using which disallows wildcards when using quotes in the arguments)

And the files you've got are asset bundles, which normally have .unity3d as file extension. Luckily, DisUnity parses the actual header and ignores the extension.
## Post #20
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-01-14T08:37:04+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

This is a great tools,but anyone know how to open those ktx files?
## Post #21
- Username: Epik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 02, 2014 3:18 pm
- Post datetime: 2014-01-17T17:57:28+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

absolutely fantastic!
nice works with webplayer files

sad that there are no repacking support
## Post #22
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2014-01-19T00:23:30+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from amzerof6
>
> This is a great tools,but anyone know how to open those ktx files?
[PVRTexTool](http://www.imgtec.com/powervr/insider/powervr-pvrtextool.asp)
## Post #23
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-01-19T08:47:11+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from Epik
>
> sad that there are no repacking support
Try:
[http://www.zoneofgames.ru/forum/index.p ... opic=29884](http://www.zoneofgames.ru/forum/index.php?showtopic=29884)
## Post #24
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2014-04-03T22:18:31+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Does this tool support the extraction of .resS files?
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-04-04T20:08:25+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

I've got a 2 gig resource archive.
Tried to open it, managed to do it, but it ate up 3 gigs of memory and was hitting the heap size. Really slow during extraction process due to JVM doing all the swapping to disk.

Should I just ignore the GUI? lol
## Post #26
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2014-04-17T02:39:29+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from mazor
>
> Does this tool support the extraction of .resS files?
Yes. These files are linked with .asset files and are loaded automatically when extracting sounds.

> Reply from finale00
>
> I've got a 2 gig resource archive.
Tried to open it, managed to do it, but it ate up 3 gigs of memory and was hitting the heap size. Really slow during extraction process due to JVM doing all the swapping to disk.

Should I just ignore the GUI? lol
Is the resource archive a .unity3d file? I haven't seen files that large so far... what game uses such files?
## Post #27
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-04-19T14:31:25+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from barracuda
>
> mazor wrote:Does this tool support the extraction of .resS files?
Yes. These files are linked with .asset files and are loaded automatically when extracting sounds.

hi~~barracuda

How to extract. ResS files?
use java -jar disunity.jar extract resources.assets
resources.assets.resS not work
## Post #28
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2014-04-20T12:05:02+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

You can't extract .resS files on their own, they're just headerless files that contain concatenated audio data. If you extract all sounds from resources.assets, resources.resS will be extracted as well.
## Post #29
- Username: audreyisme
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 13, 2014 12:03 pm
- Post datetime: 2014-05-15T01:00:23+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Hello there Barracuda, I hope that you do not mind me reposting the PM I sent you prior. Best wishes.

A very fine day to you Barracuda,

I do hope that this message finds you well.

Thank you for having shared your Disunity tool. I have no programming experience what so ever however, stumbled across your post in my ongoing attempts to source the 3D mesh and textures elements from an online Unity project.

I will be straight forward. I am a full time medical student with next to no income and am seeking to obtain for personal study use only the elements from either here:

[https://www.primalpictures.com/regional](https://www.primalpictures.com/regional) ... ltime.aspx

or even here:

[http://www.3dscience.com/3D_Models/Huma](http://www.3dscience.com/3D_Models/Huma) ... ection.php

If I had the finance I would without question make payment for the Real Time anatomy set however, both sources are completely beyond my scope and whilst there are 'cheaper' anatomical model elements online, only the Primal Pictures anatomy set comes closer to anatomic accuracy, obviously important to me.

So why am I troubling you with such things?

Well in an aim to at the very least view the Real Time 3D elements offline I have been able to locate 'some' of what I believe to be the .unity3d files for the Real Time project. One example is attached although there are a number of essential more and I was simply wondering if you might be willing to assist me in trying to extract/obtain the 3D objects (i.e. mesh/textures) from these files for the sole purpose of my own study requirements.

I have attached one such example file however, it may not even be the right type. I have attempted to use your Disunity tool and managed to extract/expand various elements from it but none appear to be the files I need. I even tried to run the .unity3d file locally through placing a script on a .html page however, I only managed to get so far as to run the page with a message indicating that I must run the .unity3d file on the owners website. Understandable.

I am also prepared to provide a small monetary sum if you feel that you might be able to assist me in this and again in no way seek to commercialize nor profit from this request nor pirate the material. I simply want it for my own study means.

Either way I wish you the very best in all your own endeavors and thank you for your time.

with regards.
## Post #30
- Username: zaphiel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 21, 2012 9:11 am
- Post datetime: 2014-05-21T15:31:25+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Hi barracuda,

First up, let me thank you for creating DisUnity. I am a soundtrack junkie so now I can finally get my mitts on the music from the games I play.

I'm having some trouble with .resS files. When I try to extract a sharedassets#.assets file with a corresponding resS file, I get "Audio clip {0} uses an external .resS file that doesn't exist!" for each file. Does DisUnity only find the .resS files for resources.assets?
All .assets and .resS files are in the same directory, by the way.
## Post #31
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2014-05-24T02:32:48+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from zaphiel
>
> Hi barracuda,

First up, let me thank you for creating DisUnity. I am a soundtrack junkie so now I can finally get my mitts on the music from the games I play.

I'm having some trouble with .resS files. When I try to extract a sharedassets#.assets file with a corresponding resS file, I get "Audio clip {0} uses an external .resS file that doesn't exist!" for each file. Does DisUnity only find the .resS files for resources.assets?
All .assets and .resS files are in the same directory, by the way.
DisUnity should automatically locate and load the corresponding .resS files for every asset file. If you have a pair of files that doesn't seem to work, you may have to send them to me for investigation.

And I also just noticed that the log message is broken, the placeholder {0} should actually contain the audio clip name. Shall be fixed. 

Edit: It turns out that the whole .resS loading system is currently broken in 0.3.0. It will be fixed in 0.3.1.
## Post #32
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-08-01T08:46:14+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

hi~~barracuda

i use DisUnity0.31 extract Pineview Drive game, sharedassets2.assets，
not work,get some error。
## Post #33
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-08-01T10:22:50+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Probably the same error as I get. I have only 2GB of RAM and this error occurs only with files ~500MB big (or bigger). 

```
[error] DisUnityProcessor: Can't process sharedassets2.assets, caused by java.io.IOException: Map failed
        at sun.nio.ch.FileChannelImpl.map(Unknown Source)
        at info.ata4.io.buffer.ByteBufferUtils.openReadOnly(ByteBufferUtils.java:156)
        at info.ata4.io.buffer.ByteBufferUtils.openReadOnly(ByteBufferUtils.java:170)
        at info.ata4.unity.asset.AssetFile.load(AssetFile.java:93)
        at info.ata4.unity.asset.AssetFile.open(AssetFile.java:58)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:239)
        at info.ata4.unity.cli.DisUnityProcessor.run(DisUnityProcessor.java:119)

        at info.ata4.unity.cli.DisUnityCli.run(DisUnityCli.java:119)
        at info.ata4.unity.cli.DisUnityCli.main(DisUnityCli.java:55)

Caused by: java.lang.OutOfMemoryError: Map failed
        at sun.nio.ch.FileChannelImpl.map0(Native Method)
        ... 9 more

```
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-08-06T02:44:34+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

I want to get the compiled scripts.
The game I'm looking at uses monoscript so a dll is generated.

How can I extract the DLL?

EDIT: got it, I used bundle-extract
## Post #35
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2014-11-24T02:21:41+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

can it unpack anim files and 3d models yet?
## Post #36
- Username: Jim Di
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 16, 2012 3:50 pm
- Post datetime: 2014-12-16T05:25:19+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Hi! Thx for useful tool.

Sometimes extractor crhases while working Texture2D data with command 'extract', 

```
        at java.util.ArrayList.<init>(Unknown Source)
        at info.ata4.unity.serdes.Deserializer.readArray(Deserializer.java:238)
        at info.ata4.unity.serdes.Deserializer.readCollection(Deserializer.java:250)
        at info.ata4.unity.serdes.Deserializer.readValue(Deserializer.java:126)
        at info.ata4.unity.serdes.Deserializer.readObject(Deserializer.java:95)
        at info.ata4.unity.serdes.Deserializer.readValue(Deserializer.java:134)
        at info.ata4.unity.serdes.Deserializer.readObject(Deserializer.java:95)
        at info.ata4.unity.serdes.Deserializer.deserialize(Deserializer.java:72)
        at info.ata4.unity.cli.extract.AssetExtractor.extract(AssetExtractor.java:160)
        at info.ata4.unity.cli.cmd.ExtractCmd.processAsset(ExtractCmd.java:43)
        at info.ata4.unity.cli.cmd.AssetCommand.processAssetFile(AssetCommand.java:100)
        at info.ata4.unity.cli.cmd.AssetCommand.processFile(AssetCommand.java:90)
        at info.ata4.unity.cli.cmd.FileCommand.processPath(FileCommand.java:58)
        at info.ata4.unity.cli.cmd.FileCommand.run(FileCommand.java:76)
        at info.ata4.unity.cli.DisUnityCli.run(DisUnityCli.java:110)
        at info.ata4.unity.cli.DisUnityCli.main(DisUnityCli.java:123)
```


but all ok with command 'extract-raw'
## Post #37
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-07T19:13:14+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from Starlow
>
> can it unpack anim files and 3d models yet?

Anims: NO
3D Models: YES
## Post #38
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2015-03-22T13:57:34+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

But it won't extract models into .obj format it just has an error.
please help!
## Post #39
- Username: Teddy84
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 09, 2015 11:51 pm
- Post datetime: 2015-06-09T15:54:01+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Thanks a lot for your tool.
However, I get an error as soon as disunity reach a 3D Model to extract... 

```
 caused by java.lang.IllegalArgumentException: Illegal Capacity: -1112068434
        at java.util.ArrayList.<init>(Unknown Source)
        at info.ata4.unity.serdes.Deserializer.readArray(Deserializer.java:224)
        at info.ata4.unity.serdes.Deserializer.readComplex(Deserializer.java:198)
        at info.ata4.unity.serdes.Deserializer.readFieldValue(Deserializer.java:134)
        at info.ata4.unity.serdes.Deserializer.readField(Deserializer.java:114)
        at info.ata4.unity.serdes.Deserializer.readObject(Deserializer.java:97)
        at info.ata4.unity.serdes.Deserializer.readComplex(Deserializer.java:205)
        at info.ata4.unity.serdes.Deserializer.readFieldValue(Deserializer.java:134)
        at info.ata4.unity.serdes.Deserializer.readField(Deserializer.java:114)
        at info.ata4.unity.serdes.Deserializer.deserialize(Deserializer.java:74)

        at info.ata4.unity.cli.extract.AssetExtractor.extract(AssetExtractor.java:170)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:136)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:59)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:71)
        at info.ata4.unity.cli.DisUnityProcessor.run(DisUnityProcessor.java:249)

        at info.ata4.unity.cli.DisUnityCli.main(DisUnityCli.java:53)

[error] DisUnityCli: Fatal error, caused by java.lang.OutOfMemoryError: Java heap space
        at java.util.ArrayList.<init>(Unknown Source)
        at info.ata4.unity.serdes.Deserializer.readArray(Deserializer.java:224)
        at info.ata4.unity.serdes.Deserializer.readComplex(Deserializer.java:198)
        at info.ata4.unity.serdes.Deserializer.readFieldValue(Deserializer.java:134)
        at info.ata4.unity.serdes.Deserializer.readField(Deserializer.java:114)
        at info.ata4.unity.serdes.Deserializer.deserialize(Deserializer.java:74)

        at info.ata4.unity.cli.extract.AssetExtractor.extract(AssetExtractor.java:170)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:136)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:59)
        at info.ata4.unity.cli.DisUnityProcessor.processAsset(DisUnityProcessor.java:71)
        at info.ata4.unity.cli.DisUnityProcessor.run(DisUnityProcessor.java:249)

        at info.ata4.unity.cli.DisUnityCli.main(DisUnityCli.java:53)
```
## Post #40
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2017-03-25T16:49:50+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

So i have  disunity 0.3.4 and i get an error when i try to extract sharedassets 
C:\Windows\Disunity>disunity extract sharedassets90.assets
[info] DisUnity v0.3.4
[info] sharedassets90.assets
[warning] FileCommand: Can't process sharedassets90.assets, caused by info.ata4.unity.asset.AssetException: Unknown asset format 15
        at info.ata4.unity.asset.AssetFile.load(AssetFile.java:145)
        at info.ata4.unity.asset.AssetFile.load(AssetFile.java:105)
        at info.ata4.unity.asset.AssetFile.open(AssetFile.java:58)
        at info.ata4.unity.cli.cmd.AssetCommand.processAssetFile(AssetCommand.java:97)
        at info.ata4.unity.cli.cmd.AssetCommand.processFile(AssetCommand.java:90)
        at info.ata4.unity.cli.cmd.FileCommand.processPath(FileCommand.java:58)
        at info.ata4.unity.cli.cmd.FileCommand.run(FileCommand.java:76)
        at info.ata4.unity.cli.DisUnityCli.run(DisUnityCli.java:110)
        at info.ata4.unity.cli.DisUnityCli.main(DisUnityCli.java:123)
game was made using unity 5.  i also tried disunity 0.5.0 but same here.  anyone help
## Post #41
- Username: DrMcCoy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 20, 2016 12:17 pm
- Post datetime: 2017-05-17T01:17:32+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

> Reply from hesanda
>
> So i have  disunity 0.3.4 [...] game was made using unity 5.  i also tried disunity 0.5.0 but same here.  anyone help

> Reply from DisUnity README.md
>
> 0.3 works best with Unity 3.x and has most of the original extraction features.
=> DisUnity 0.3.4 can't extract Unity 5 (nor 4, for that matter) data files.

> Reply from DisUnity README.md
>
> 0.5 is a code rewrite to properly support all Unity games from 2 to 5 that also comes with unit tests. Right now, it only supports raw file reading and writing without any object deserialization, therefore it also can't extract any asset data directly.
=> DisUnity 0.5.0 isn't ready yet either.

TL;DR: You can't extract Unity 5 data files with DisUnity.
## Post #42
- Username: Iareanab
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 31, 2017 7:34 pm
- Post datetime: 2017-06-01T07:19:43+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Thanks, your program is amazing, it already helped me once)
## Post #43
- Username: wellspokenrambler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 03, 2018 8:18 pm
- Post datetime: 2018-02-03T12:39:48+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Hi barracuda,

First, I'd like to thank you for creating this tool in the first place: the only other tool I've been able to find along these lines is the DevXDevelopment application - which I can only run as a trial version, since I don't have the 258 dollars to spare to upgrade it to the full, object-extracting package.

The file I'm interested in extracting is a demo for the 2010 Gorillaz "Escape To Plastic Beach" game: the motivation being to obtain the materials and objects necessary to render the "Plastic Beach" island in Unity. According to the DevX trial, the .unity3d file in question contains these as several .obj and .mat files. According to UniPlayer.exe, the demo runs on Unity 2.x, due to the game being released over 7 years ago.

Having run DisUnity ver. 0.3.4 upon it with the command "disunity extract GorillazDemo.unity3d", it has successfully managed to retrieve the following kinds of files: .tga, .shader, and .dss: but every other file type, including .cs, .fbx and, crucially, the .mat and .obj files has not been brought through. 

Attempting the "extract -f" command and parameter resulted in an "unknown option" error. I did successfully get the BINs of every file, but this did not lead anywhere due to a lack of BIN experience.

Is this problem due to the age of the game, or is there another workaround I can try?

Thanks for taking the time to read this.
## Post #44
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2021-06-28T11:35:25+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

Can anyone tell me how to use it step by step in more details? I tried to follow what's it says in this thread but i keep getting the same error message.
## Post #45
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2022-02-06T13:55:11+00:00
- Post Title: Re: DisUnity - An extractor for Unity games

This is very outdated and it won't work with anything much newer of 2015 (if even that)
These are some alternatives, from the still-older to newest
[https://github.com/DerPopo/UABE](https://github.com/DerPopo/UABE)
[https://github.com/mafaca/UtinyRipper](https://github.com/mafaca/UtinyRipper)
[https://github.com/Perfare/AssetStudio](https://github.com/Perfare/AssetStudio)
[https://github.com/AssetRipper/AssetRipper](https://github.com/AssetRipper/AssetRipper)
