## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-27T17:22:33+00:00
- Post Title: Raw texture previewer/converter

Since I was finally tired of making DDS headers manually every time I need to check images from researched games, I made this tool. It needs microsoft's texconv to work.

It supports all DirectX image types and immediately converts to working DDS and PNG.
Supports PS3, PS4, PS5 and Nintendo Switch swizzle types.

UI version usage:
- drag&drop raw image onto ANY place on a window. This will try and detect image dimensions based on file size, make DDS header, convert to PNG and show it.
- If you don't like the result, change some settings then press SPACE (or click big button).

Command line version usage: 
RawtexCmd <filename> [format] [offset] [width] [height]
   <format> = BC1...BC7,BC5U,BC5S,DXT1,DXT3,DXT5 or decimal DX10 code
   if no format specified, supposed DXT1
   <width>, <height> - decimal
   if no size specified, its guessed, like in UI tool
   <offset> - hex

Examples:
RawtexCmd tex1.raw 
RawtexCmd tex1.raw bc7
RawtexCmd tex1.raw bc7 10CF0
RawtexCmd tex1.raw bc7 10CF0 1024 1024


[Rawtex.rar](https://xentaxbackup.github.io/file/24041_Rawtex.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-17T17:25:47+00:00
- Post Title: Raw texture previewer/converter

All new command line version! You can use it to run batches on thousands of files.
## Post #3
- Username: hi im daft
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 21, 2018 7:13 am
- Post datetime: 2018-05-22T02:07:13+00:00
- Post Title: Raw texture previewer/converter

This may sound dumb, but when previewing a file with this tool, does it change the DXT selection on the left to show what format the image itself is using? Or do you have to manually adjust that yourself? I'm actually trying to possibly use this tool to read what type of DXT file some images I already have are, so I know what to convert modified versions back into.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-22T15:17:18+00:00
- Post Title: Raw texture previewer/converter

there is NO WAY to detect DXT format, so you have to choose yourself
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-07T11:05:35+00:00
- Post Title: Raw texture previewer/converter

New version!
Now supports PS3, PS4 and Nintendo Switch swizzle types.
## Post #6
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2018-07-05T11:51:35+00:00
- Post Title: Raw texture previewer/converter

This is incredibly useful! Any chance that the swizzling options can be added to the command line version too?
## Post #7
- Username: game456a
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 04, 2018 2:40 pm
- Post datetime: 2018-07-09T11:32:50+00:00
- Post Title: Raw texture previewer/converter

i have this problem when use it to open MHXX(MHGU) switch. Can you fix this?
## Post #8
- Username: game456a
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 04, 2018 2:40 pm
- Post datetime: 2018-07-09T14:50:42+00:00
- Post Title: Raw texture previewer/converter

Btw here is a .tex file
[https://cdn.discordapp.com/attachments/ ... yukumo.zip](https://cdn.discordapp.com/attachments/465614093856931854/465837391207464960/yukumo.zip)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-09T17:42:43+00:00
- Post Title: Raw texture previewer/converter

> Reply from game456a
>
> i have this problem when use it to open MHXX(MHGU) switch. Can you fix this?

There's nothing to fix, everything is working perfectly. Use the field with bold letters "OFFSET"
And remove that huge screenshot, its really annoying
## Post #10
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-07-09T23:14:01+00:00
- Post Title: Raw texture previewer/converter

does this work with PS4 texture files that have all the info located at the footer?
## Post #11
- Username: game456a
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 04, 2018 2:40 pm
- Post datetime: 2018-07-10T13:00:26+00:00
- Post Title: Raw texture previewer/converter

> Reply from daemon1
>
> game456a wrote:i have this problem when use it to open MHXX(MHGU) switch. Can you fix this?

There's nothing to fix, everything is working perfectly. Use the field with bold letters "OFFSET"
And remove that huge screenshot, its really annoying
 OMG thank you so much
## Post #12
- Username: jzrh1060
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 11, 2018 12:49 pm
- Post datetime: 2018-07-11T04:56:56+00:00
- Post Title: Raw texture previewer/converter

This is awesome! Could you please add an option for setting texture swizzling type through the Command Line? It'd be incredibly helpful for converting all the textures in an entire game's folders all in one go.

Thanks (and thanks for making this tool in the first place).
## Post #13
- Username: DeathChaos
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 01, 2017 2:27 pm
- Post datetime: 2018-07-19T15:14:55+00:00
- Post Title: Raw texture previewer/converter

I tried this with a PS4 game, Final Fantasy Dissidia NT, textures seem to be swizzled somehow, however it seems to not be the standard PS4 swizzling?

Here are 2 simple sample files, the Square Enix logo and the Koei Tecmo logos shown when booting the game.

[https://cdn.discordapp.com/attachments/ ... /logo_sqex](https://cdn.discordapp.com/attachments/143149082582581258/469518248602501131/logo_sqex)
[https://cdn.discordapp.com/attachments/ ... 84/logo_kt](https://cdn.discordapp.com/attachments/143149082582581258/469518307121168384/logo_kt)

Any ideas on what this could be?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-19T15:36:01+00:00
- Post Title: Raw texture previewer/converter

its standard PS4 swizzling, just set correct size, 1920x1080, the size is in the file
## Post #15
- Username: DeathChaos
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 01, 2017 2:27 pm
- Post datetime: 2018-07-19T16:06:56+00:00
- Post Title: Raw texture previewer/converter

Ah you were correct, thanks!
## Post #16
- Username: Vuze
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 11, 2018 4:33 am
- Post datetime: 2018-08-11T06:57:59+00:00
- Post Title: Re: Raw texture previewer/converter

This is amazing! Thanks a lot for including the different swizzle options too!
## Post #17
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2018-08-15T18:14:43+00:00
- Post Title: Re: Raw texture previewer/converter

has anyone been toying with monster hunter world's textures? The diffuse and normal maps i can get to convert just fine. It's what i assume is the specular map that i'm having trouble finding the right settings for.


em101_00_eye_BML:


em101_00_eye_RMT:

[em101_00_eye_RMT.rar](https://xentaxbackup.github.io/file/14753_em101_00_eye_RMT.rar)
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-15T19:52:28+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from pox911
>
> It's what i assume is the specular map
BC7
## Post #19
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2018-08-15T20:12:35+00:00
- Post Title: Re: Raw texture previewer/converter

So it is. I had to use something else other than gimp to open it since bc7 exports didnt like gimp. Wonder if the color masks use something similar.

edit: Seems that bc7 isnt what is used though on the _RMT textures for armor. Now that i know gimp isnt the best for preview on these, here's hoping the rest is easier to poke though

edit2: seems bc1 is used for the _RMT of armor. Got to love consistency
## Post #20
- Username: Vuze
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 11, 2018 4:33 am
- Post datetime: 2018-08-15T20:31:39+00:00
- Post Title: Re: Raw texture previewer/converter

Speaking of MHW, it seems the PS4 swizzling for the PS4 textures of the game (there are a bunch that aren't in PC version, hence my research) doesn't seem to work. Offset, size, format should be correct I think.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-15T20:38:01+00:00
- Post Title: Re: Raw texture previewer/converter

it works absolutely fine 

your offset is incorrect
## Post #22
- Username: Vuze
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 11, 2018 4:33 am
- Post datetime: 2018-08-15T20:44:48+00:00
- Post Title: Re: Raw texture previewer/converter

Ah, got it now. Thanks for the heads up
## Post #23
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-08-22T07:08:15+00:00
- Post Title: Re: Raw texture previewer/converter

Apparently there is no option for r8g8b8 when art stored is plain RGB24 and you can only choose the 32bit (r8g8b8a8) one that creates holes, I had to make a standard dds (not dx10) with said type and copy header over.

Edit: Apparently this seems to be an limitation of the DX10+++ (?) as I don't see it listed as an option in official docs for the extended dds formats either while original nvidia dds plugin lets write it to the original dds format.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-22T15:23:28+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from Apollo
>
> Apparently there is no option for r8g8b8

Edit: Apparently this seems to be an limitation of the DX10+++
yes, and it means no modern games ever use it.

You must be working with some old game (pre-dx10) ?
## Post #25
- Username: TheGriever
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 20, 2018 5:36 am
- Post datetime: 2018-08-22T23:50:56+00:00
- Post Title: Re: Raw texture previewer/converter

This has been a very handy tool! I'm very new to this scene and am mostly stumbling around lost. Do you know how I can get it to go BACK to TEX from DDS? I'm trying to figure out the hex modification, but I'm just getting lost because I don't know enough to frame my questions properly in google, haha.
## Post #26
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2018-08-23T16:25:06+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1
>
> 
You must be working with some old game (pre-dx10) ?

Well, it was released in 2016 with Unity game engine but yeah such type was just single file.
## Post #27
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-24T12:09:00+00:00
- Post Title: Re: Raw texture previewer/converter

Does this tool support DXGI ASTC compression?
i've been trying to convert some textures from Mario + Rabbids: Kingdom Battle recently but have had no luck.

Stored in a DDS container with a DDS header but uses ASTC compression? it's rather...odd to me.
Best i could get was this:
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-24T15:48:45+00:00
- Post Title: Re: Raw texture previewer/converter

no, ASTC is not supported
## Post #29
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2018-08-24T23:06:08+00:00
- Post Title: Re: Raw texture previewer/converter

Any chance support could be added?

Im not sure how hard this kinda thing is, but i'd greatly appreciate it
## Post #30
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-10-10T06:55:01+00:00
- Post Title: Re: Raw texture previewer/converter

Damn nice daemon1.

This one will help me on future Driveclub reversing work.
## Post #31
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-10-13T03:08:41+00:00
- Post Title: Re: Raw texture previewer/converter

Does this tool support Switch swizzled DDS textures (header "DFvN" and "HBvN")? I am working with Child Of Light for Switch version, could you help me take and look? Thank you very much!

My example file: [https://drive.google.com/file/d/1wDBLpW ... sp=sharing](https://drive.google.com/file/d/1wDBLpWxC1rHndK097BR_muP6MTIM7Hf2/view?usp=sharing)
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-13T05:59:01+00:00
- Post Title: Re: Raw texture previewer/converter


## Post #33
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-10-14T14:22:42+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1
>
> 
Thank for your quick reply! Thank you very much! Could you update this tool for inject new texture (edited) to raw files? Thanks!
P/S: maybe i are wrong topic, you created this tool for preview for main, hope you can help me inject edited texture.
## Post #34
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-10-16T15:42:08+00:00
- Post Title: Re: Raw texture previewer/converter

Could you help me take and look this file, this game use MT Framework Engine, same Monster Hunter U, i can't open it.

My example file: [https://1drv.ms/u/s!AqHXyzDaH_sGiVDOaJQmMqnSKNaG](https://1drv.ms/u/s!AqHXyzDaH_sGiVDOaJQmMqnSKNaG)
Thanks!
## Post #35
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-10-18T09:15:33+00:00
- Post Title: Re: Raw texture previewer/converter

Thanks! My problems solved!
## Post #36
- Username: jeka215
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 01, 2016 9:00 am
- Post datetime: 2018-10-23T21:09:25+00:00
- Post Title: Re: Raw texture previewer/converter

Hello, daemon1!

Looks like with new Paladins update, Hi-Res decided to change format of normal maps. While old normal maps works just fine, new ones looks like this:



As you can see, UModel says, new format is V8U8, but i can't find this format in your tool. I tried almost all of available formats, but nothing. 

Can you please help with this?

Here is example of new texture, if you need it: [https://drive.google.com/open?id=1NbvcI ... g8y_atXVj2](https://drive.google.com/open?id=1NbvcIABEMiZhWgJgmsEO4Sg8y_atXVj2)



upd: nvm, i got it. Thanks for this awesome program!
## Post #37
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2018-12-02T19:16:31+00:00
- Post Title: Re: Raw texture previewer/converter

For some reason preview does not work for me. What might be the issue? Conversion works just fine, but not having a preview makes figuring out the format way more tedious.
[2018-12-02 22-09-36 Raw texture cooker.png](https://xentaxbackup.github.io/file/15267_2018-12-02 22-09-36 Raw texture cooker.png)
## Post #38
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-12-03T11:00:25+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from zheneq
>
> For some reason preview does not work for me. What might be the issue? Conversion works just fine, but not having a preview makes figuring out the format way more tedious.

Oh yeah. I had the same problem. Solution or fix for this would be great.   
I can share some system details by PM if you want @daemon1.
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-03T15:17:00+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from zheneq
>
> For some reason preview does not work for me. What might be the issue? Conversion works just fine, but not having a preview makes figuring out the format way more tedious.
Для превью запускается в виде отдельного модуля TEXCONV.exe который лежит в той же папке.

Варианты:
- нет прав на запуск или что-то его блокирует
- куда-то пропал TEXCONV.exe
## Post #40
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2018-12-03T20:24:18+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1
>
> 
Варианты:
- нет прав на запуск или что-то его блокирует
- куда-то пропал TEXCONV.exe

If only it was that easy. Welp, I don't see what could be the problem.

It seems I'll have to run texconv via console.
## Post #41
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-12-03T20:56:06+00:00
- Post Title: Re: Raw texture previewer/converter

I can’t preview also.
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-04T15:34:52+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from zheneq
>
> If only it was that easy.
ну надо же было уточнить
сегодня сделаю версию, которая скорее всего будет работать
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-04T19:38:37+00:00
- Post Title: Re: Raw texture previewer/converter

try this version
... removed ...
## Post #44
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2018-12-05T11:22:24+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1
>
> try this version

Nothing seems to have changed. No preview; if the png file exists, it is deleted.
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-05T16:41:13+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from zheneq
>
> daemon1 wrote:try this version

Nothing seems to have changed. No preview; if the png file exists, it is deleted.

In this version i specifically point exactly where "texconv.exe" is located.

If this version is not working, it means something in your system prevents the tool to run texconv.exe
Disable antiviruses, windows defenders or anything else that may decide that running texconv.exe is some suspicious activity and block it.
## Post #46
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-12-07T08:28:24+00:00
- Post Title: Re: Raw texture previewer/converter

I have no preview too, downloaded texconv.exe from [here](https://github.com/Microsoft/DirectXTex/issues/17) and put in the same folder with rawtex (D:\Programs\RAWTex\) - nothing changes, tried both versions.
## Post #47
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-07T11:21:37+00:00
- Post Title: Re: Raw texture previewer/converter

The preview works fine for me.



Maybe your "texconv.exe" is blocked. Windows sometimes does that to the downloaded exe/dll files.
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-07T17:01:54+00:00
- Post Title: Re: Raw texture previewer/converter

I found that old (2016) texconv version had no "-y" option to overwrite existing converted file. So there was no preview with it.

So you can either:

- use this "special" rawtex version that will work with OLD texconv
or
- get new texconv and it will work with rawtex posted in the first post
[Rawtex.rar](https://xentaxbackup.github.io/file/15288_Rawtex.rar)
## Post #49
- Username: debido
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 09, 2009 5:22 am
- Post datetime: 2018-12-27T21:35:24+00:00
- Post Title: Re: Raw texture previewer/converter

Just wondering if someone could help me with figuring out this file.

It's the heightfield file for Black Desert Online. While I'm pretty sure it's an image of some type, I just can't figure out what the format it is. 

[https://drive.google.com/open?id=1hb538 ... 2G74sQjVdg](https://drive.google.com/open?id=1hb538Rg0z7-QMDAKoj4sl42G74sQjVdg) for heightfield.zip


Thanks
Dave
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-12T03:25:44+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from jzrh1060
>
> Could you please add an option for setting texture swizzling type through the Command Line?
i would like to request this also. i want to hook RawTexCmd to Noesis but i need to set swizzle type also.
## Post #51
- Username: wood5578
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 10, 2018 2:56 pm
- Post datetime: 2019-01-24T05:04:01+00:00
- Post Title: Re: Raw texture previewer/converter

I'm trying to view and convert a texture that is in a RGBA8888 but the UI version doesn't seem to work for me, the label that's showing the directory of the texture always shows "..." for me, I already drag and drop the file onto the exe.

Command-line seems works but whats the command to convert RGBA8888 format?

EDIT:
I tried drag and dropping.
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-24T15:49:08+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from wood5578
>
> the UI version doesn't seem to work for me, the label that's showing the directory of the texture always shows "..." for me, I already drag and drop the file onto the exe.
I tried drag and dropping.

where did you drag and drop with UI version?
## Post #53
- Username: wood5578
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 10, 2018 2:56 pm
- Post datetime: 2019-01-24T16:36:37+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1
>
> where did you drag and drop with UI version?
Onto the exe. 
My bad, turns out I was reading the description wrongly the whole time, its dragging onto the application and not the exe. Sorry about that.
## Post #54
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2019-02-26T03:47:10+00:00
- Post Title: Re: Raw texture previewer/converter

any chance to support palette RGB 8bpp 256 colors and palette ARGB 8 bpp 256 colors + alpha or just images with palettes?
## Post #55
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-05-21T02:02:40+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Mon Dec 18, 2017 1:25 am at Mon Dec 18, 2017 1:25 am
>
> 
All new command line version! You can use it to run batches on thousands of files.

thx for your good job!
Can you tell me how to use the RawtexCmd.exe?
my Raw file can be exactly exported with Rawtex.exe, with ps4 swizzle.

Rawtex.exe can check PS3/PS4 SWIZZLE, but RawtexCmd.exe has no this option argument...
RawtexCmd <filename> [format] [offset] [width] [height]
so I can't export raw exactly.
Any help will be greatly appreciated !!!!
I need batch to my thousands of files.......
## Post #56
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-05-22T05:18:52+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from Acewell ↑Sat Jan 12, 2019 11:25 am at Sat Jan 12, 2019 11:25 am
>
> 
jzrh1060 wrote:Could you please add an option for setting texture swizzling type through the Command Line?
i would like to request this also. i want to hook RawTexCmd to Noesis but i need to set swizzle type also.

can RawTexCmd.exe use swizzle type???
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-22T05:22:49+00:00
- Post Title: Re: Raw texture previewer/converter

as far as i remember, no
## Post #58
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-05-22T06:29:29+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Wed May 22, 2019 1:22 pm at Wed May 22, 2019 1:22 pm
>
> 
as far as i remember, no

oh, it's a pity.
is any other way to batch the RawTex.exe to deal with textures?
Or, other way to get the imformation about ps4 swizzle source??
## Post #59
- Username: tatsui
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 19, 2019 11:40 pm
- Post datetime: 2019-07-19T17:21:51+00:00
- Post Title: Re: Raw texture previewer/converter

Hello,

thank you very much for this tool, I'm using it for the first time and I probably need some direction. I'm trying to open a .tex file from N. Switch and so far I got the result below

[](https://ibb.co/YX4YJww)

However, I was not able to obtain the appropriate colors. Maybe this is something related to the appropriate offset to be selected by I'm not sure if I am able to identify it, any help appreciated. Thank you very much.
## Post #60
- Username: blizzardy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 24, 2019 9:31 am
- Post datetime: 2019-08-24T01:34:21+00:00
- Post Title: Re: Raw texture previewer/converter

Any plans to support Wii U swizzle?

I think there is some from this repo: [https://github.com/aboood40091/GTX-Extractor](https://github.com/aboood40091/GTX-Extractor)
Sadly I can't convert the .tex to .gtx I provided in the attachment
[samples.zip](https://xentaxbackup.github.io/file/16644_samples.zip)
## Post #61
- Username: xLegacyGT
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 09, 2019 8:43 am
- Post datetime: 2019-09-09T01:11:15+00:00
- Post Title: Re: Raw texture previewer/converter

Thank you for your work daemon1.

I'm having issues with getting the preview to work, I added texconv.exe into the same folder as your tools and it still wont work. I also tried the methods mentioned in previous posts.
## Post #62
- Username: NWPlayer123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 28, 2012 3:27 am
- Post datetime: 2019-09-09T16:49:06+00:00
- Post Title: Re: Raw texture previewer/converter

Any chance you could post the source code? would be pretty useful, even if it isn't the best coding in the world
## Post #63
- Username: Turisto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 31, 2019 3:17 am
- Post datetime: 2019-11-09T11:37:14+00:00
- Post Title: Re: Raw texture previewer/converter

Unfortunately this tool doesn't support uncompressed rgba formats.
There are lot of such textures in PS4 "The Last of us" in swizzled form.
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-11-09T12:38:54+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from Turisto ↑Sat Nov 09, 2019 7:37 pm at Sat Nov 09, 2019 7:37 pm
>
> 
Unfortunately this tool doesn't support uncompressed rgba formats.
There are lot of such textures in PS4 "The Last of us" in swizzled form.
the tool  SUPPORTS uncompressed rgba formats.
## Post #65
- Username: chrnodroid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 17, 2019 5:41 pm
- Post datetime: 2019-12-17T17:57:44+00:00
- Post Title: Re: Raw texture previewer/converter

Sample file:
[https://mega.nz/#!e4UnyCyS!ayMSZh6V38Li ... 2UGICo-_jI](https://mega.nz/#!e4UnyCyS!ayMSZh6V38Lin16PG-ol-2Zb4OUX09fRe2UGICo-_jI)

What's the problem here?

The texture should be b8g8r8a8 with ps4 swizzling



thank you in advance
## Post #66
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2019-12-17T18:53:45+00:00
- Post Title: Re: Raw texture previewer/converter

Because:
1) offset is 1E0
2) format is b8g8r8a8_unorm
## Post #67
- Username: chrnodroid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 17, 2019 5:41 pm
- Post datetime: 2019-12-17T19:17:08+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from TheUkrainianBard ↑Wed Dec 18, 2019 2:53 am at Wed Dec 18, 2019 2:53 am
>
> 
Because:
1) offset is 1E0
2) format is b8g8r8a8_unorm

Thank you very much!!!!   
Have a nice day!
## Post #68
- Username: JahsehLLJ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 29, 2019 1:30 am
- Post datetime: 2019-12-28T17:42:47+00:00
- Post Title: Re: Raw texture previewer/converter

Sample files:
[https://drive.google.com/open?id=102hxJ ... l0sCf6MDX3](https://drive.google.com/open?id=102hxJwISP-32LGPiXUVOhIl0sCf6MDX3)



What i'm supposed to do? I'm almost sure that theses files are textures, but he can't recognize...
## Post #69
- Username: Kabalstein03
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 9:36 am
- Post datetime: 2020-03-30T01:14:42+00:00
- Post Title: Re: Raw texture previewer/converter

Hello there, i'm trying to use this program to convert some textures from Borderlands 3, these "colorize arrays" that can help us paint the model textures with their respective colors, so far I've tried to put them through this software but they come out very pixelated, repeated, or in very low quality.

I'll provide a link for anyone to see if they can manage to port these out successfully, or at least find the right settings to port these out, any help is appreciated, thank you.
[http://www.mediafire.com/file/3eu7oypyy ... y.zip/file](http://www.mediafire.com/file/3eu7oypyy18vurd/VaultHunters_ColorizeArray.zip/file)
[Capture.PNG](https://xentaxbackup.github.io/file/17836_Capture.PNG)
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-06-18T15:11:04+00:00
- Post Title: Re: Raw texture previewer/converter

I should've done that long time ago probably...

PS4 command line version added. Usage is the same as usual command line tool, but textures will be PS4-unswizzled. Now you can run batches on PS4 textures.
## Post #71
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2020-07-03T13:16:12+00:00
- Post Title: Re: Raw texture previewer/converter

The PS4 command line version consistently crashes for me on every file I've tested:

```
   at System.Array.Copy(Array sourceArray, Int32 sourceIndex, Array destinationArray, Int32 destinationIndex, Int32 length, Boolean reliable)
   at RawtexBatch.RawtexBatch.Main(String[] args)
```

If I run the regular command line version with the same parameters, it works (but the file is obviously swizzled).
## Post #72
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-07-03T15:37:48+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from Blorbster ↑Fri Jul 03, 2020 9:16 pm at Fri Jul 03, 2020 9:16 pm
>
> 
The PS4 command line version consistently crashes for me on every file I've tested:
If I run the regular command line version with the same parameters, it works (but the file is obviously swizzled).
Its not crashing here whatever i try on any images.
You must be using some VERY wrong parameters which is impossible to use in swizzling.
## Post #73
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2020-07-03T17:25:43+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Fri Jul 03, 2020 11:37 pm at Fri Jul 03, 2020 11:37 pm
>
> 
Its not crashing here whatever i try on any images.
You must be using some VERY wrong parameters which is impossible to use in swizzling.

The exact command I'm running is:

```
.\rawtexcmd_ps4.exe "ps4texture.example" BC3 0x72cce 1040 1720
```

It works correctly if I use those same parameters with PS4 swizzling in the GUI, or in the non-PS4 version.
## Post #74
- Username: RavenMac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 07, 2019 11:00 am
- Post datetime: 2020-07-03T22:26:06+00:00
- Post Title: Re: Raw texture previewer/converter

Got two questions:
1) To batch process files, do i just select the folder they are all in? I saw it was added quite a while back, but with no explanation.

2) Is there any option to select swizzles in the command line version? Trying to use the switch swizzle on a few thousand files.

Great tool by the way. I love just exploring game files.
## Post #75
- Username: Snake128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 12, 2020 11:26 pm
- Post datetime: 2020-12-16T14:34:34+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Fri Jul 03, 2020 11:37 pm at Fri Jul 03, 2020 11:37 pm
>
> 
Blorbster wrote: ↑Fri Jul 03, 2020 9:16 pm
The PS4 command line version consistently crashes for me on every file I've tested:
If I run the regular command line version with the same parameters, it works (but the file is obviously swizzled).

Its not crashing here whatever i try on any images.
You must be using some VERY wrong parameters which is impossible to use in swizzling.

Hi Master,
I'm working with your program and is amazing, but I have a question about.

Your program get a .nhtex "switch swizzle" file and convert to .dds file perfectly with the correct parameters, but is posible to do the reverse, I mean get a .dds file and convert to a .nhtex "switch swizzle" file?

Thanks.

Best Regards

Rafa
## Post #76
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2020-12-19T21:01:28+00:00
- Post Title: Re: Raw texture previewer/converter

Hi old thread I know but was wondering if a swizzle algorithm could be found for Mask texture in Cyberpunk 2077 - those masks are crucial to the texturing of 90% of the game assets and so we would very much like to get them "un-swizzled" if thats possible. Here are 2 samples, the masks are in BC4 format and sizes are correct

- the DDS is from Renderdoc (also added the normal to see how it should look like once un-swizzled)
- Added also the mlsetup and mlmask and their Json dump as it contains info on the Mask layout / Atlas

It looks like this

[https://www.dropbox.com/s/yudligu0g5jl6 ... derdoc.png](https://www.dropbox.com/s/yudligu0g5jl69z/from_renderdoc.png)



 xentax_cp2077_swizzle.part1.rar
(250 KiB) Downloaded 61 times



Thanks in advance!
## Post #77
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2020-12-19T21:06:11+00:00
- Post Title: Re: Raw texture previewer/converter

Second part of the Rar


 xentax_cp2077_swizzle.part2.rar
(56.81 KiB) Downloaded 60 times
## Post #78
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-21T03:40:33+00:00
- Post Title: Re: Raw texture previewer/converter

preview is not working, and I have added the texconv.exe with admin privileges
## Post #79
- Username: SatansFavSuccubus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 25, 2021 1:30 pm
- Post datetime: 2021-10-29T03:46:43+00:00
- Post Title: Re: Raw texture previewer/converter

Is there a reason the file won't open? I'm running Win10 and every single time I try to open RawTex.exe (GUI version) it shows for a few seconds then immediately closes.

Please help?
## Post #80
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2022-03-07T06:56:27+00:00
- Post Title: Re: Raw texture previewer/converter

Hey, i maybe have a stupid question but i would be glad if someone can help me. How can I find the correct offset of the texture to put it in there?
Is it offset of the whole file, or is it just some specific part? Could someone explain me? 
Thank you!
## Post #81
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-07T12:45:06+00:00
- Post Title: Re: Raw texture previewer/converter

> How can I find the correct offset of the texture to put it in there?
It really depends on the file you are trying to preview.
If your file is just raw image data, then offset 0x00 should be fine.
If your file is an archive or binary blob, then you need to find correct offset manually.
## Post #82
- Username: kenken0215
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 22, 2022 1:00 pm
- Post datetime: 2022-04-26T08:26:40+00:00
- Post Title: Re: Raw texture previewer/converter

hi! 
I can't get it to work, so if anyone can figure it out, I would appreciate your assistance.

xenoblade 2 wilay file
offset 1000
BC7 unorm srgb
switch swizzle

but the output is
The top and bottom are out of alignment and the right side of the bottom half is not output.

Please help me.

[https://www.mediafire.com/file/y73yh4sc ... st.7z/file](https://www.mediafire.com/file/y73yh4sc2396v7t/test.7z/file)
## Post #83
- Username: eaZy41
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 12, 2019 8:30 pm
- Post datetime: 2022-04-29T07:26:40+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from kenken0215 ↑Tue Apr 26, 2022 4:26 pm at Tue Apr 26, 2022 4:26 pm
>
> 
hi! 
I can't get it to work, so if anyone can figure it out, I would appreciate your assistance.

xenoblade 2 wilay file
offset 1000
BC7 unorm srgb
switch swizzle

but the output is
The top and bottom are out of alignment and the right side of the bottom half is not output.

Please help me.

https://www.mediafire.com/file/y73yh4sc ... st.7z/file
Maybe,it's because texture was swizzled with --sparse parameter. Rawtex can't propertly unswizzle this.

UPD. I was wrong. It's 1176x1320 texture. But rawtex still can't propertly extract swizzled "non-standard" sizes
Here is result.
[https://www.mediafire.com/file/o5l0myhd ... 2.dds/file](https://www.mediafire.com/file/o5l0myhdh0jh0eo/fim_bl_002.dds/file)
## Post #84
- Username: kenken0215
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 22, 2022 1:00 pm
- Post datetime: 2022-05-03T10:09:25+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from eaZy41 ↑Fri Apr 29, 2022 3:26 pm at Fri Apr 29, 2022 3:26 pm
>
> 
kenken0215 wrote: ↑Tue Apr 26, 2022 4:26 pm
hi! 
I can't get it to work, so if anyone can figure it out, I would appreciate your assistance.

xenoblade 2 wilay file
offset 1000
BC7 unorm srgb
switch swizzle

but the output is
The top and bottom are out of alignment and the right side of the bottom half is not output.

Please help me.

https://www.mediafire.com/file/y73yh4sc ... st.7z/file

Maybe,it's because texture was swizzled with --sparse parameter. Rawtex can't propertly unswizzle this.

UPD. I was wrong. It's 1176x1320 texture. But rawtex still can't propertly extract swizzled "non-standard" sizes
Here is result.
https://www.mediafire.com/file/o5l0myhd ... 2.dds/file

thanks for reply! Sorry for the late reply.
It looks very nice!!
How can I output like that?
## Post #85
- Username: eaZy41
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 12, 2019 8:30 pm
- Post datetime: 2022-05-04T13:07:39+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from kenken0215 ↑Tue May 03, 2022 6:09 pm at Tue May 03, 2022 6:09 pm
>
> 
thanks for reply! Sorry for the late reply.
It looks very nice!!
How can I output like that?

Without special tool? Just using rawtex You can do it this way:
- rise up width until texture normalize (in this sample - 1184)
- then rise up height to nearest "statndard" value (in this sample - 1536)
- then cut off result texture from top left corner (demensions located at the end of file - 0x20 and 0x1C from end)
## Post #86
- Username: kenken0215
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 22, 2022 1:00 pm
- Post datetime: 2022-05-04T15:41:59+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from eaZy41 ↑Wed May 04, 2022 9:07 pm at Wed May 04, 2022 9:07 pm
>
> 
kenken0215 wrote: ↑Tue May 03, 2022 6:09 pm
thanks for reply! Sorry for the late reply.
It looks very nice!!
How can I output like that?


Without special tool? Just using rawtex You can do it this way:
- rise up width until texture normalize (in this sample - 1184)
- then rise up height to nearest "statndard" value (in this sample - 1536)
- then cut off result texture from top left corner (demensions located at the end of file - 0x20 and 0x1C from end)

thank you! and I tried it.
[https://www.mediafire.com/file/iumori4f ... 2.dds/file](https://www.mediafire.com/file/iumori4ftq7lo6k/fim_bl_002.dds/file)
I'm a little confused about the last line and it came out like this, am I wrong?
## Post #87
- Username: lenetzp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 14, 2022 11:20 am
- Post datetime: 2022-05-14T03:24:28+00:00
- Post Title: Re: Raw texture previewer/converter

nice work
## Post #88
- Username: ividyon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 11, 2022 4:53 am
- Post datetime: 2022-09-10T21:55:39+00:00
- Post Title: Re: Raw texture previewer/converter

I'm desperately trying to use this tool, as it looks very cool and exactly like what I'm looking for, but unfortunately on Windows 11 it's throwing issues:

System.IO.IOException: The process cannot access the file 'C:\Games\Elden Ring Modding\CNT\Unpacked\Images\Menu\convert\MENU_Knowledge_00199.dds' because it is being used by another process.

This happens when I try to squeeze the file through RawtexCmd_PS4.exe (Since the Closed Network Test is a PS4 game), or drag it into Rawtex.exe and press Space.

There is most definitely no application using the file. I have copied the files several times to different locations.

I tried giving administrator rights to texconv and Rawtex.exe to no avail. Giving administrator rights to Rawtex.exe makes it impossible to drag files into the window (there will be a "Denied" sign as the mouse pointer).
## Post #89
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-09-11T05:56:08+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from ividyon ↑Sun Sep 11, 2022 5:55 am at Sun Sep 11, 2022 5:55 am
>
> 
System.IO.IOException: The process cannot access the file 'C:\Games\Elden Ring Modding\CNT\Unpacked\Images\Menu\convert\MENU_Knowledge_00199.dds' because it is being used by another process.
rename your file
## Post #90
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-10-15T16:31:47+00:00
- Post Title: Re: Raw texture previewer/converter

Working on PS5 texture swizzle
## Post #91
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2022-10-25T14:01:36+00:00
- Post Title: Re: Raw texture previewer/converter

what would be the code for r8g8b8a8_unorm? i tried 27/28/29 on a ps4 texture and none of them worked
## Post #92
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-11-05T14:55:23+00:00
- Post Title: Re: Raw texture previewer/converter

New version released, with partial support for PS5 swizzle.

It only works with block-compressed images (BC1-BC7) and 32-bit raw images (such as 4-byte RGBA).
If I can find other types used in PS5 games i can update it.

p.s. tested on Spiderman & Demons Souls. If you find it doesnt work for some game, let me know.
## Post #93
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2022-11-09T17:25:14+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Sat Nov 05, 2022 10:55 pm at Sat Nov 05, 2022 10:55 pm
>
> 
New version released, with partial support for PS5 swizzle.

It only works with block-compressed images (BC1-BC7) and 32-bit raw images (such as 4-byte RGBA).
If I can find other types used in PS5 games i can update it.

p.s. tested on Spiderman & Demons Souls. If you find it doesnt work for some game, let me know.

Awesome work! Do you plan on adding support for other compression types in the future? Like for example most textures under the particles directory from Demon's Souls can't be converted. Thanks!
## Post #94
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2023-01-22T20:56:40+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Sat Nov 05, 2022 10:55 pm at Sat Nov 05, 2022 10:55 pm
>
> 
New version released, with partial support for PS5 swizzle.

Can RawtexCMD be updated to include the PS5 swizzle?
It only seems to be in the GUI version and the CMD version is alot easier for batch operations.
## Post #95
- Username: Ghjkla
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 13, 2023 8:58 pm
- Post datetime: 2023-01-29T18:49:17+00:00
- Post Title: Re: Raw texture previewer/converter

Anyone know any other alternatives to this with same options?
## Post #96
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-29T22:25:59+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from Ghjkla ↑Mon Jan 30, 2023 2:49 am at Mon Jan 30, 2023 2:49 am
>
> 
Anyone know any other alternatives to this with sane options?

Check this out [viewtopic.php?t=15540](https://forum.xentax.com/viewtopic.php?t=15540)
## Post #97
- Username: Ghjkla
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 13, 2023 8:58 pm
- Post datetime: 2023-02-01T08:35:29+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from ikskoks ↑Mon Jan 30, 2023 6:25 am at Mon Jan 30, 2023 6:25 am
>
> 
Ghjkla wrote: ↑Mon Jan 30, 2023 2:49 am
Anyone know any other alternatives to this with sane options?


Check this out viewtopic.php?t=15540

I tried it out and it dosen't seem to work on switch games like metroid dread.
## Post #98
- Username: BigSorLost
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 09, 2022 4:27 am
- Post datetime: 2023-06-27T05:21:02+00:00
- Post Title: Re: Raw texture previewer/converter

How can I get image previews to work?



Screenshot 2023-06-27 012017.png (16.35 KiB) Viewed 186 times
## Post #99
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-27T20:37:54+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from BigSorLost ↑Tue Jun 27, 2023 1:21 pm at Tue Jun 27, 2023 1:21 pm
>
> 
How can I get image previews to work?

You have to put "texconv.exe" file in the same directory as "Rawtex.exe" file.
## Post #100
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-09T06:32:58+00:00
- Post Title: Re: Raw texture previewer/converter

Added cmd version with PS5 swizzle
## Post #101
- Username: kayhotic
- Rank: n00b
- Number of posts: 16
- Joined date: Sat May 16, 2020 12:50 pm
- Post datetime: 2023-07-16T19:33:34+00:00
- Post Title: Re: Raw texture previewer/converter

> Reply from daemon1 ↑Sun Jul 09, 2023 2:32 pm at Sun Jul 09, 2023 2:32 pm
>
> 
Added cmd version with PS5 swizzle

any possibility of getting an xbox one swizzle?
