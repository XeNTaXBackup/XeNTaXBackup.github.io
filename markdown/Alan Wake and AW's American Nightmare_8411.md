## Post #1
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-27T16:32:05+00:00
- Post Title: Alan Wake and AW's American Nightmare

Alan Wake Tool v0.5: [https://www.dropbox.com/s/qinph0o9dr6yv ... ol.7z?dl=0](https://www.dropbox.com/s/qinph0o9dr6yv4a/AWTool.7z?dl=0)  (.Net4 required!)

Change log since v0.0.1:
-faster exporting/importing
-3GB+ file support
-text repack
-tex2dds2tex converter, PC ONLY
-X360/PC file support
-American Nightmare file unpack/repack, TESTED (it seems works fine)
-other details in the info.rtf file!

v0.4c
-fixed a Russian text bug
-filter the unpacked/repacked files by extension
-3GB+ file writing bug fixed

v0.5
- AW's American Nightmare PC support

If you find bug, let me know. I'll try to fix it.
## Post #2
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-02-28T00:21:03+00:00
- Post Title: Alan Wake and AW's American Nightmare

Awesome tool and awesome guy.

Thank you!
## Post #3
- Username: miGma
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 19, 2012 3:34 am
- Post datetime: 2012-02-28T08:46:46+00:00
- Post Title: Alan Wake and AW's American Nightmare

Firstly, thanks for the tool.

Secondly, I can't import the text file I translated.. It says "Succesfully imported 0 file(s)." I even tried to import the original text file without any editing, but it said the same. What I do is: 
I choose the bin file in game's data folder as the input direction, and choose the folder which contains the text file I edited as the output folder and click Import. "Convert text file" option is checked. Am I doing somethin wrong or?
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-28T09:33:05+00:00
- Post Title: Alan Wake and AW's American Nightmare

First, unpack the bin/rmdp file. Because you need the string_table.bin file from the bin/rmdp. You can delete the other unpacked files.
## Post #5
- Username: miGma
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 19, 2012 3:34 am
- Post datetime: 2012-02-28T10:28:43+00:00
- Post Title: Alan Wake and AW's American Nightmare

> Reply from evin
>
> First, unpack the bin/rmdp file. Because you need the string_table.bin file from the bin/rmdp. You can delete the other unpacked files.

What will I do with string_table.bin? I already have the .txt file (which you sent me) and when I unpack the bin/rmdp file and put the text file into locale\en folder, I try to import but it doesn't work. Do I need to delete the string_table.bin file which comes when I unpack the bin/rmdp file? Do I need to convert the text file I have to .bin format? What should I do exactly.. Can you tell me?

And If I need to edit the .bin file - can you tell me a program to view it?
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-28T17:14:28+00:00
- Post Title: Alan Wake and AW's American Nightmare

> Reply from miGma
>
> evin wrote:First, unpack the bin/rmdp file. Because you need the string_table.bin file from the bin/rmdp. You can delete the other unpacked files.

What will I do with string_table.bin? I already have the .txt file (which you sent me) and when I unpack the bin/rmdp file and put the text file into locale\en folder, I try to import but it doesn't work. Do I need to delete the string_table.bin file which comes when I unpack the bin/rmdp file? Do I need to convert the text file I have to .bin format? What should I do exactly.. Can you tell me?

And If I need to edit the .bin file - can you tell me a program to view it?

Steps:
-Unpack everything from the bin/rmdp
-delete everything, what you won't edit or change, so in this case, leave only the string_table.bin and it's subfolder
-paste there the translated string_table.bin.txt
-run the tool if you closed, open the bin file, Import
## Post #7
- Username: Aiser
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 25, 2012 1:06 am
- Post datetime: 2012-02-28T17:21:54+00:00
- Post Title: Alan Wake and AW's American Nightmare

How to add language to the game?

```
.\data\config\locale_config.xml
```
Add:

```
    <!-- XC_LANGUAGE_RUSSIAN -->                        <config xgetlanguage_id="12"    xgetlocale_id="0"   folder="ru"   subtitles_default="1"     bink_voiceover_channel="2"  use_only_one_font="0" />
<!-- End Partial+ localizations -->
```
Language is added, but no text.

```
[MENU_WELCOME]
```
Does anyone know what to do?
## Post #8
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-28T17:46:31+00:00
- Post Title: Alan Wake and AW's American Nightmare

Like this:
locale_config.xml

```
<!-- XC_LANGUAGE_FAKELANG -->                        <config xgetlanguage_id="12"    xgetlocale_id="0"   folder="fake"   subtitles_default="1"     bink_voiceover_channel="2"  use_only_one_font="0" />
```


And need in the data folder these files:
ep999-000-fake.bin
ep999-000-fake.rmdp

fake = a language ID

But the game contain already the Russian language.
## Post #9
- Username: miGma
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 19, 2012 3:34 am
- Post datetime: 2012-02-28T17:52:00+00:00
- Post Title: Alan Wake and AW's American Nightmare

Now it's been like this:

[](http://img41.imageshack.us/i/alanwake201202281945406.jpg/)

[](http://img818.imageshack.us/i/alanwake201202281946043.jpg/)

See the subtitles.
## Post #10
- Username: Aiser
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 25, 2012 1:06 am
- Post datetime: 2012-02-28T18:15:38+00:00
- Post Title: Alan Wake and AW's American Nightmare

In Alan Wake American Nightmare is not Russian.
I have created:

```
ep999-000-ru.rmdp
```
Add:

```
    <!-- XC_LANGUAGE_RUSSIAN -->                        <config xgetlanguage_id="12"    xgetlocale_id="0"   folder="ru"   subtitles_default="1"     bink_voiceover_channel="2"  use_only_one_font="0" />
<!-- End Partial+ localizations -->

```
+ Replaced the font (customer_facing.binfnt, customer_facing_typewriter.binfnt) (from Alane Wake - Russian)
But still no text.
If replace text:
```
ep999-000-en.rmdp
```
It works.
## Post #11
- Username: LonelyDragon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 25, 2012 6:36 am
- Post datetime: 2012-02-29T08:38:14+00:00
- Post Title: Alan Wake and AW's American Nightmare

I have problem with fonts in book:
[http://puu.sh/iQNZ](http://puu.sh/iQNZ)
I repacked japanese file (replaced fonts and text, even tried to change use_only_one_font from "1" to "0" in locale_config.xml)
In menu and in game everything ok, only in book i have that problem.
Please, help me
## Post #12
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-29T10:56:13+00:00
- Post Title: Alan Wake and AW's American Nightmare

"use_only_one_font" means: the use only the customer_facing.binfnt font file.
The customer_facing_typewriter.binfnt is smaller, and not contain special characters. And this font not contain those characters, you using. And you cannot add new characters!
## Post #13
- Username: LonelyDragon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 25, 2012 6:36 am
- Post datetime: 2012-02-29T11:14:04+00:00
- Post Title: Alan Wake and AW's American Nightmare

Well, which font uses Alan Wake for books? Or what files I need to add to the package?
As you can see buttons in right bottom displays normally. (And any other text too.)
## Post #14
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-29T11:24:04+00:00
- Post Title: Alan Wake and AW's American Nightmare

The manuscript pages use customer_facing_typewriter.binfnt font, IF use_only_one_font = 0.
Write back the use_only_one_font to 1. That's all you can do.
## Post #15
- Username: LonelyDragon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 25, 2012 6:36 am
- Post datetime: 2012-02-29T12:39:07+00:00
- Post Title: Alan Wake and AW's American Nightmare

Thanks. It works for now...
## Post #16
- Username: miGma
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 19, 2012 3:34 am
- Post datetime: 2012-02-29T14:49:20+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from miGma
>
> Now it's been like this:





See the subtitles.

Why does this happen? I do everything correctly.
## Post #17
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-29T16:37:35+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I have to see your files to find out what's wrong.
## Post #18
- Username: miGma
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 19, 2012 3:34 am
- Post datetime: 2012-03-01T16:00:21+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Okay, the text file was faulty I guess, it works awesome now! Thanks for the tool again.
## Post #19
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2012-03-02T23:04:44+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Can you also add an option to filter files when extracting? For instance only extract texture files, only extract sound files etc.
Thanks.
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-03-03T07:54:53+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I think. But I need a couple days.
## Post #21
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-03-05T16:04:23+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from JPulowski
>
> Can you also add an option to filter files when extracting? For instance only extract texture files, only extract sound files etc.
Thanks.
Done. First post updated.
## Post #22
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-03-06T11:13:47+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

what type of modding is available? only subtitle changes?
## Post #23
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-03-06T11:41:49+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I have no idea. I made this tool, to I can translate the game, maybe edit the textures.
But you can unpack everything from bin/rmp, and as far as I know, the game can read from folder, os probably you can do everything you want.
## Post #24
- Username: lunu1997
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 31, 2012 11:54 pm
- Post datetime: 2012-03-31T16:06:40+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

PLease Can you find a way to disable the shadows in ALan Wake b'cause i am having performance issues
Before i found a way to disable the Motion Blur And Vectur BLur & i was asked to replace two .obj files from a youtube video to here
Alan Wake\shaders\build\pc
I saw there were shadow**.obj files

Can You please find a way to disable the shadows
i really appreciate the work you've done in making the alan wake mod tool
and i would be very much greatful if you find a way to disable the shadows
## Post #25
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-04-01T13:26:23+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I don't know the .obj file. How they works, how they can edit etc.
I made the opportunity, to anyone can get the files, change them, and put them back into the game. If you want to disable the shadows, you have to figure out how. I'm not modder.
## Post #26
- Username: NateChad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 05, 2012 1:44 am
- Post datetime: 2012-04-04T18:29:46+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hello, sorry for my english.
I want to dub this game. I was unpacking ep999-000-en then creating my .fsb (IMA ADPCM). After that .fsb was being copied to the folder ep999-000-en into the respective directory. All was being packed and I was starting the game, but still original tracks sounded.
Where does it take the original sounds, if they are absent in ep999-000-en?
How do I get my records sounded?
And who knows where is "CINE" audio files?

P.S. Evin, thanks for your tool.
## Post #27
- Username: eaman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 12, 2012 8:37 pm
- Post datetime: 2012-04-12T12:40:37+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hi,
Great tool mate ,i tried to change the buttons2.binft in font folder with another font and my game is not starting,please soembody share there buttons2.binft in fonts folder of ep999-001.bin.thanks
## Post #28
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-04-17T11:18:20+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hi evin
Thanks for great tool.
I tried to edit some textures from ep999-000.rmdp (the big rmdp file) and then imported them but no matter what I do the game don't start.(black screen)
I noticed the rmdp file your tool generates doesn't have some of the first starting bytes of the original rmdp file.and it's size is a little smaller.then I checked the size fixer option and it added some null bytes at the end of the rmdp file but it still doesn't have those first bytes and the game still doesn't start.
Could that be a problem?
Or maybe I'm not doing it the right way.
## Post #29
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-04-18T13:24:31+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

You have to use the compression of original DDS file. If you don't, the size of the new dds will change. The size of the files itself doesn't matter, but the wrong compression can cause this. I can tell, if I could see the original and new dds files.
I edited too textures in the game, and still works everything fine.
## Post #30
- Username: Xeifab
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 01, 2012 12:03 am
- Post datetime: 2012-04-18T16:44:19+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hi and good job for your mod tools. But have you any idea how to open the models 3d of Alan Wake (.binmsh)? Because there were so many models that should be present if Alan Wake was an open world. Thanks.
## Post #31
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-04-19T08:22:39+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

No, I'm not interested in 3D stuff.
## Post #32
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-04-19T09:39:31+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from evin
>
> You have to use the compression of original DDS file. If you don't, the size of the new dds will change. The size of the files itself doesn't matter, but the wrong compression can cause this. I can tell, if I could see the original and new dds files.
I edited too textures in the game, and still works everything fine.

To test whether importing textures work or not I exported textures and then imported them back without editing them and it still doesn't work.
I touched nothing.Just exported then imported but still black screen.
## Post #33
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-04-20T05:58:15+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

To find out where is the problem, I suggest you: repack the rmdp file, and unpack the new files, and compare the unpacked files from the original and the unpacked files from repacked.
If somewhere is a size different, probably there is the source of the problem.

I hope you use the 0.4b version of tool.
## Post #34
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-04-21T08:45:19+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from evin
>
> To find out where is the problem, I suggest you: repack the rmdp file, and unpack the new files, and compare the unpacked files from the original and the unpacked files from repacked.
If somewhere is a size different, probably there is the source of the problem.

I hope you use the 0.4b version of tool.

I'm using 0.4b version.
I repacked the rmdp file without editing anything and when I tried to unpack the new file I got an error.

Problem signature:
  Problem Event Name:	CLR20r3
  Problem Signature 01:	alanwtool.exe
  Problem Signature 02:	0.4.2.0
  Problem Signature 03:	4f54e272
  Problem Signature 04:	mscorlib
  Problem Signature 05:	4.0.0.0
  Problem Signature 06:	4ba1da6f
  Problem Signature 07:	3dab
  Problem Signature 08:	23b
  Problem Signature 09:	System.IO.IOException
## Post #35
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-04-21T10:44:22+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Did you replaced or renamed the bin2 and rmdp2 file too, to bin/rmdp?

This happens even if you try to do the same with smaller bin/rmdp files?
## Post #36
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-04-21T19:45:33+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Yes,I do rename them.  
I edited some of the textures from smaller bin/rmdp files and repacked it(ep999-000-en).The game runs and it works perfectly.I can see edited textures in game.
I do the same thing with main bin/rmdp file but no luck.Just black screen.
## Post #37
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-04-21T21:27:08+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Fixed, first post updated (v0.4c).
## Post #38
- Username: NateChad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 05, 2012 1:44 am
- Post datetime: 2012-04-23T12:13:05+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I don't know what to do. I made the new .fsb files and replaced the originals, than I imported this files to bin/rmdp(en) and renamed result. But the game still play english versions.
Who can tell me where are "CINE" audio files?
## Post #39
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-04-23T19:57:33+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from evin
>
> Fixed, first post updated (v0.4c).
Thanks.It works perfectly now.
## Post #40
- Username: SaMoPicky
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 30, 2012 10:45 pm
- Post datetime: 2012-04-30T15:07:15+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I extracted the rmdp file with the 2.42 gb 
i chose it then clicked on convert text files & TEX\DDS convertor

   


but i cant find the translation files 
or the graphics files


any one can help and show me where are they and how to edit them 

nessaserly
??
## Post #41
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2012-05-09T07:23:28+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I downloaded the tool, and it works just fine! Thanks!
I am trying to make a font rebuild tool, because I want to translate the game into chinese.
## Post #42
- Username: KlinOK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 10, 2012 11:33 pm
- Post datetime: 2012-05-21T10:56:25+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Steps:
>
> -Unpack everything from the bin/rmdp
>
> -delete everything, what you won't edit or change, so in this case, leave only the string_table.bin and it's subfolder
>
> -paste there the translated string_table.bin.txt
>
> -run the tool if you closed, open the bin file, Import
Respected evin, thank you for the program, but I have it all working.
He did everything as you wrote, but the option "convert text file" does not convert the*.bin file to *.txt.
Sorry for my bad English
## Post #43
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-22T06:16:50+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Did you overwrite or rename any files?
## Post #44
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-05-22T21:47:11+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

I'm trying to open the file ep999-000-en.bin (Alan Wake American Nightmare). Program crashes with an error immediately.
## Post #45
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-05-23T01:06:13+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Crashes for me aswell when I try to unpack the ep999-000.bin
American Nightmare (PC)
## Post #46
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-23T05:42:55+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Yeah, because the AWAN PC version released just yesterday, the tool not tested with those files. I know about the problem, and I'm working on it.
## Post #47
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2012-05-23T08:18:00+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from evin
>
> Yeah, because the AWAN PC version released just yesterday, the tool not tested with those files. I know about the problem, and I'm working on it.

It's because the file in AWAN PC version are all little endian. The first byte in the bin file actually is a bool value which tells you whether the file is BE or LE. I modified your tool, now it works on AWAN PC version. If you want, I can send you the source file I modified.
## Post #48
- Username: OneTwo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 7:01 pm
- Post datetime: 2012-05-23T09:38:38+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Please tell me whether the added support for the unpack\pack files:
ep999-000.rmdp (Alan Wake PC) [2,83 Gb]
ep999-000.rmdp (Alan Wake's American Nightmare PC) [941 Mb]

and support for console commands?
## Post #49
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-27T06:30:27+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Updated tool and AWAN PC text file coming up in few days. I'm testing right now.
## Post #50
- Username: CONSTANT EGO
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 28, 2012 3:19 am
- Post datetime: 2012-05-27T20:12:52+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hi!

Alan Wake's American Nightmare...

Did you know that the game archives contain a secret page of Alan Wake's manuscript?

Here is the original of the image, the text is almost not visible:


I made ​​transcription the best of their ability. But the two words (marked [...]) have remained undeciphered. I would be grateful for any help.

Enjoy:

> In the cabin, two stuffed ravens stare at Wake and Alice from atop a bookshelf. Wake is surprised to find his typewriter sitting on the desk. Alice was planned the whole thing behind Wake's back to get him writing again. The vacation was just a ruse to get Wake here. Wake feels angry and betrayed. Every-one keeps pushing him to do something he is not ready to do. Wake and Alice [...] about it. Suddenly, the lights in the cabin start to flicker. Unseen by Wake and Alice, Barbara Jagger stands in the shadows in the cabin. As soon as it began, the flickering stops and Jagger is gone. Alice is [...] by the flickering lights. Wake is too angry to stay. He needs to cool off, to clear his head. 
>
> 
>
> Wake storms out of the cabin. He is certain that Alice will not follow him into the dark. When Wake gets to the car, he hears Alice. She is screaming in terror, calling his name. There is a splash of water and then silence. Alarmed, Wake pluck up a flashlight from the car and rushes back to the lake. Wake is surprised to see that the cabin is dark, the lights are out. He looks for Alice. Wake round the dark water with his lamp. He seen her form underwater, sinking into the darkness. He draws a shuddering breath and dives into the black water. 
>
> 
>
> Wake wakes up gasping from a nightmare. He is in the car. The car has crashed against a tree. It's night. He is bleeding from his forehead. He has hit his head. He staggers out. He calls out Alice's name. There is no reply.

P.S.: In attachment the english text of Alan Wake's American Nightmare. And there is not this page.
[string_table.bin.rar](https://xentaxbackup.github.io/file/5468_string_table.bin.rar)
## Post #51
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-05-27T20:53:53+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from CONSTANT EGO
>
> Wake and Alice [...] about it.
Wake and Alice argue about it.

> Reply from CONSTANT EGO
>
> Alice is [...] by the flickering lights.
Alice is startled by the flickering lights.
## Post #52
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-28T06:52:24+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Tool updated in the first post.
## Post #53
- Username: adasiuu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 06, 2011 7:21 pm
- Post datetime: 2012-05-28T07:58:58+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

hi guys, how to edit .binfnt font files? thanks
## Post #54
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-28T10:19:20+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Open the file by hex editor, find this text: "DDS". This is where the font texture start. It's end is the end of the font file.
## Post #55
- Username: NateChad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 05, 2012 1:44 am
- Post datetime: 2012-06-04T17:17:38+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hi, where is "CINE" audio files?
## Post #56
- Username: Edudant
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 11, 2012 4:38 am
- Post datetime: 2012-06-10T20:46:24+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Hello there!
thanks for the great tool!

Iam trying to do a simple thing - making game with spanish audio and english subtitles. So I first exported both en.bin and es.bin files and just exchanged the string_table english into string_table spanish one. Then imported the en file. This sounds logical to me. 
But when clicking import, 2 new files are created :
ep999-000-es.bin2
ep999-000-es.rmdp2

the "2" on the end of each file looks strange at first to me. So I just renamed the original files and in those new files just deleted the "2" in the name. But then the game just wont start.

Any idea?

Thanks
e.
## Post #57
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-06-11T05:40:50+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

The "bin2/rmdp2" are the new files, the repacked data.
Move/rename the original bin/rmdp file, than delete the "2" from the end of the new files. That's it.
## Post #58
- Username: Edudant
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 11, 2012 4:38 am
- Post datetime: 2012-06-11T14:32:18+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Yes I did that as I wrote in the post. But then I doble click on the icon and the game wont start.
what could it be?
regards
e.
## Post #59
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-06-11T16:15:21+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Than move the original files.
## Post #60
- Username: Edudant
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 11, 2012 4:38 am
- Post datetime: 2012-06-11T18:37:11+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Yes I did that, but still the game wont start untill I put back the original files.

not sure if doind everything allright, heres what I do: 

1)in AWtool clicked browse in input and chose ep999-000-en.bin
2)chose file type to unpack/repack .bin. there is convert text file option on by default
3)exported
4)did 1)-3) the same for ep999-000-es.bin
5)overwrote string_table.bin from en directory to es directory
6)imported ep999-000-es directory
7)moved the original files to desktop
8)renamed the new files(delete both "2")
9)run the game and nothing happened, stayed in windows
## Post #61
- Username: Aiser
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 25, 2012 1:06 am
- Post datetime: 2012-08-05T19:28:52+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Please convert (Russian Steam PC Licens) string_table.bin in string_table.bin.txt Thank you.
string_table.bin
## Post #62
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-14T21:23:29+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

The dropbox link on the first post is down.
## Post #63
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2017-04-16T16:47:59+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from AnonBaiter
>
> The dropbox link on the first post is down.

Updated!
## Post #64
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-05-13T19:43:50+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

how do you convert the extracted .bin files to be editable?
## Post #65
- Username: Mostafa MandoO
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 17, 2017 9:40 pm
- Post datetime: 2017-10-17T23:49:27+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

i want add new language in alan wake ,,,,,i can't open (customer_facing_typewriter.binfnt ) to add new language...  can anyone help me
## Post #66
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2017-10-22T05:07:09+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

> Reply from Mostafa MandoO
>
> i want add new language in alan wake ,,,,,i can't open (customer_facing_typewriter.binfnt ) to add new language...  can anyone help me

Open the file customer_facing_typewriter.binfnt with hex editor. Search this text with uppercase "DDS". Copy the data from here until the end of the file. Now you have the font texture.
But as far as I know, adding new language is not possible, only replace an exist one.

Btw the customer_facing.binfnt contain the main font file. The extraction is the same.
## Post #67
- Username: nourancairo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 02, 2019 12:05 am
- Post datetime: 2019-03-19T22:41:47+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

hi  

can  anyone  help me   

i  have translate   alan wake text language   from english to arabic  

and  i do import  with  aw tools   

but still  language  is english not arabic   !!!   

what i miss  ?????

and what i need  to  add arabic font  to  the game  subtitles  ?
## Post #68
- Username: muserigtc
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Jul 16, 2016 9:44 pm
- Post datetime: 2020-01-01T03:58:31+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Can you make Update tools with some new fiture "Bin to TXT" and with Update Files?
## Post #69
- Username: kyezer
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Apr 21, 2019 2:52 pm
- Post datetime: 2021-02-10T01:48:56+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Can anyone help me? I want to get all the dialogue audio from both Alan Wake games but right now American Nightmare I am having an issue. I used the tool and extracted from the ep999-000-en file and everything dialogue related was there as far as I know. I started converting the files with the fbs converter. However, when I try to convert some of the .fbs files to .wav files they do convert but they are silent files after extraction. Example, all the files in the 'scratch-videos' folder are all there (each having a corresponding .fbs.meta file to match) but I can't convert them into audio files that aren't silent. What am I doing wrong?
## Post #70
- Username: zoted
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 08, 2021 1:54 pm
- Post datetime: 2021-09-08T06:00:17+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

Found a tool to get the text file, but the game CTD after I import it.
The same thing happens on QuantumBreak

Just found this tool, read all replies, seems no way to turn string_table.bin into a text file? The Alan Wake game has official traditional Chinese localization, just wonder how can I get it.
## Post #71
- Username: MarvelousGamer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 26, 2021 12:27 am
- Post datetime: 2021-12-25T16:28:59+00:00
- Post Title: Re: Alan Wake and AW's American Nightmare

is there any way to convert this to text ?

string_table.bin
