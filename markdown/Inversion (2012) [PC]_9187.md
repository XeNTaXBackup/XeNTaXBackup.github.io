## Post #1
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-07-01T14:22:17+00:00
- Post Title: Inversion (2012) [PC]

Hello,

I'm going to translate this cool game, does anyone know, where the texts are? The game has FSB archives.

Thank for any tips.
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-07-01T18:05:35+00:00
- Post Title: Inversion (2012) [PC]

FSB files are sounds.
All stuff are in .s3darc files.
## Post #3
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-07-02T08:39:36+00:00
- Post Title: Inversion (2012) [PC]

OK and is there any tool for extracting from these files? I tried to find something, but I hadn't luck.

Thanks
## Post #4
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-07-02T14:44:49+00:00
- Post Title: Inversion (2012) [PC]

Need a sample file.
## Post #5
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-07-02T17:26:29+00:00
- Post Title: Inversion (2012) [PC]

Ok, here is one file: [http://depositfiles.com/files/x0gcjw9nq](http://depositfiles.com/files/x0gcjw9nq)
## Post #6
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-07-02T17:46:31+00:00
- Post Title: Inversion (2012) [PC]

Try [GameExtractor](http://watto.org/extract/info.html).
It support Timeshift s3darc file, but maybe works with this too.
## Post #7
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-07-02T20:42:04+00:00
- Post Title: Inversion (2012) [PC]

Here are the texts for translation.
Open it in a good text editor, like Notepad++.

[http://www.mediafire.com/?qy9jusc3kyt9tzp](http://www.mediafire.com/?qy9jusc3kyt9tzp)

I will write repacker later and post here, but no free time now.

Stay tunned.
## Post #8
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-07-03T13:25:45+00:00
- Post Title: Inversion (2012) [PC]

Thanks  repacker will great, because import is not working. Actually I'm trying to find and edit fonts but they look encrypted... The fonts are in files with GFX ext. But there is no header of GFX.

Here is a sample file with english fonts: [http://depositfiles.com/files/io6kl3c34](http://depositfiles.com/files/io6kl3c34) I still don't know how to get into it...

THX
## Post #9
- Username: pesicha
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 17, 2010 6:16 pm
- Post datetime: 2012-07-04T19:33:25+00:00
- Post Title: Inversion (2012) [PC]

> Reply from phill05
>
> Thanks  repacker will great, because import is not working. Actually I'm trying to find and edit fonts but they look encrypted... The fonts are in files with GFX ext. But there is no header of GFX.

Here is a sample file with english fonts: http://depositfiles.com/files/io6kl3c34 I still don't know how to get into it...

THX

are classic gfx fonts
not encrypted
are compressed zlib
 1 Font Name, Korataki Rg
 2 Font Name, Magistral Medium
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-28T23:49:48+00:00
- Post Title: Inversion (2012) [PC]

hey

i'm bumping this thread because i just wrote a locale patching tool (inversionloc). see the attached zip.

to use my tool, first dump the english strings (unless you have them by another means..)

> inversionloc.exe u out_patch.s3darc english.txt

edit away..

then repack like so:

> inversionloc.exe p out_patch.s3darc patched_.s3darc english.txt

sourcecode was written in pascal and in a mess. i will post it later  
[inversionLoc.zip](https://xentaxbackup.github.io/file/5617_inversionLoc.zip)
## Post #11
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-07-29T19:02:37+00:00
- Post Title: Inversion (2012) [PC]

> Reply from WRS
>
> hey

i'm bumping this thread because i just wrote a locale patching tool (inversionloc). see the attached zip.

to use my tool, first dump the english strings (unless you have them by another means..)
inversionloc.exe u out_patch.s3darc english.txt

edit away..

then repack like so:
inversionloc.exe p out_patch.s3darc patched_.s3darc english.txt

sourcecode was written in pascal and in a mess. i will post it later

I gave a try to your patcher, did just like you wrote, but the text remains English whatever I do. I tried renaming english.txt to locale.txt, and even tried putting the patched file next to out_patch, and also overwriting the out_patch file. None of them has worked so far. Is there a "trick" to use it, which I should know?
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-29T20:10:53+00:00
- Post Title: Inversion (2012) [PC]

> Reply from Rion
>
> I gave a try to your patcher, did just like you wrote, but the text remains English whatever I do. I tried renaming english.txt to locale.txt, and even tried putting the patched file next to out_patch, and also overwriting the out_patch file. None of them has worked so far. Is there a "trick" to use it, which I should know?

when you do the repacking (with option 'p') the s3darc filenames you give must be different. once the patcher has created the new file, it replaces out_patch.s3darc
## Post #13
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-07-29T21:48:15+00:00
- Post Title: Inversion (2012) [PC]

> Reply from WRS
>
> when you do the repacking (with option 'p') the s3darc filenames you give must be different. once the patcher has created the new file, it replaces out_patch.s3darc

I apologize, but this one still eludes me. You mean the created file is to replace the "old" out_patch file, am I right? If this is the case, then the one your program creates - after copying it under preload/paks, then renaming it from "patched_" to "out.patch" - is just being ignored by the game for some reason. Which means whenever it should use the modified file, it "switches to" - more precisely, it keeps using -  English. So, would you might list (or PM) for me some kind of guide to make it work? I've got the feeling I'm still missing something.
## Post #14
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-29T22:33:01+00:00
- Post Title: Inversion (2012) [PC]

> Reply from Rion
>
> WRS wrote:when you do the repacking (with option 'p') the s3darc filenames you give must be different. once the patcher has created the new file, it replaces out_patch.s3darc

I apologize, but this one still eludes me. You mean the created file is to replace the "old" out_patch file, am I right? If this is the case, then the one your program creates - after copying it under preload/paks, then renaming it from "patched_" to "out.patch" - is just being ignored by the game for some reason. Which means whenever it should use the modified file, it "switches to" - more precisely, it keeps using -  English. So, would you might list (or PM) for me some kind of guide to make it work? I've got the feeling I'm still missing something.

if you have a file named 'patched_' after you run my program, rename it to 'out_patch.s3darc', which replaces the one you used to extract the strings from.

and yes, it uses the english strings file - so be sure to set the games language to english if you dont already (i don't have this game)

if i am misunderstanding you, then here are a few things to try:
check that the filesize of the new out_patch.s3darc file you create is smaller than the original
try editing a different string
look for any inversion log file and see if you can find a mention of 'strings_english'
## Post #15
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-07-30T15:08:24+00:00
- Post Title: Inversion (2012) [PC]

> Reply from WRS
>
> if you have a file named 'patched_' after you run my program, rename it to 'out_patch.s3darc', which replaces the one you used to extract the strings from.

and yes, it uses the english strings file - so be sure to set the games language to english if you dont already (i don't have this game)

if i am misunderstanding you, then here are a few things to try:
check that the filesize of the new out_patch.s3darc file you create is smaller than the original
try editing a different string
look for any inversion log file and see if you can find a mention of 'strings_english'

I did rename it numerous times to 'out_patch'. I rewrote some dialog strings of the game's prologue and some menu texts (don't know if editing is char-limited?), compiled the modded file and checked the size: 17 951 756 bytes, so it's smaller. Yet, no strings has changed in-game. I checked game.cfg, and saw the language was set to Russian (it is English in-game, however). I set all three options to force using English locale. Still, no luck. I've run out of options.
## Post #16
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-07-30T15:27:57+00:00
- Post Title: Re: Inversion (2012) [PC]

I have the same problem as Rion. I changed some strings, ex. every "Options", made new s3darc, renamed it to out_patch, and no change in the game, it's still in english.
## Post #17
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-07-31T01:38:59+00:00
- Post Title: Re: Inversion (2012) [PC]

The pure game (without update) reads the texts from out.s3darc.
The usage to get the texts and insert it back is the same as out_patch.s3darc.
## Post #18
- Username: pesicha
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 17, 2010 6:16 pm
- Post datetime: 2012-07-31T08:43:18+00:00
- Post Title: Re: Inversion (2012) [PC]

I just wanted to help

deleting it - sorry
## Post #19
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-07-31T16:58:46+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from pesicha
>
> 

 file strings_english.str place the into the folder  

 Inversion\prebuild\texts\strings_english.str

Yes, text now works, but what about fonts? I modified fonts_en.gfx and gfxfontlib.gfx and put them to \prebuild\swf\ but fonts are still original - english. 

Any suggestions?

UPDATE: correct name of font file is fonts_en_pc.gfx
## Post #20
- Username: pesicha
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 17, 2010 6:16 pm
- Post datetime: 2012-07-31T18:30:05+00:00
- Post Title: Re: Inversion (2012) [PC]

I just wanted to help

deleting it - sorry
## Post #21
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-07-31T19:58:43+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from merlinsvk
>
> 
Yes, text now works, but what about fonts? I modified fonts_en.gfx and gfxfontlib.gfx and put them to \prebuild\swf\ but fonts are still original - english. 

Any suggestions?
Could you explain how to edit those .gfx fonts?
## Post #22
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-07-31T20:31:04+00:00
- Post Title: Re: Inversion (2012) [PC]

They are Scaleform GFx files (modified flash) so change their header from GFX to FWS, then you can decompile them to .fla files and edit in Adobe Flash for example. 
Also you will need Scaleform SDK (im using version 3.0, from older version of UDK, october 2011 I think) linked with Adobe Flash to make new .gfx files.
## Post #23
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-07-31T22:44:14+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from merlinsvk
>
> They are Scaleform GFx files (modified flash) so change their header from GFX to FWS, then you can decompile them to .fla files and edit in Adobe Flash for example. 
Also you will need Scaleform SDK (im using version 3.0, from older version of UDK, october 2011 I think) linked with Adobe Flash to make new .gfx files.
And where can I download Scaleform SDK?
Found no good links here after do a research.
## Post #24
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-07-31T22:47:06+00:00
- Post Title: Re: Inversion (2012) [PC]

It's a part of Unreal UDK.
## Post #25
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-08-01T02:30:08+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from Herdell
>
> merlinsvk wrote:They are Scaleform GFx files (modified flash) so change their header from GFX to FWS, then you can decompile them to .fla files and edit in Adobe Flash for example. 
Also you will need Scaleform SDK (im using version 3.0, from older version of UDK, october 2011 I think) linked with Adobe Flash to make new .gfx files.
And where can I download Scaleform SDK?
Found no good links here after do a research.
There are other ways to edit them... if you stay visible on MSN...
## Post #26
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-08-01T09:49:27+00:00
- Post Title: Re: Inversion (2012) [PC]

Can you explain that other ways?
## Post #27
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-08-01T16:17:44+00:00
- Post Title: Re: Inversion (2012) [PC]

Delutto, can you explain that for me, too? Now that the know-how of using external string file is revealed, only the method of fonts GFX editing is all I need for localizing the game.
## Post #28
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-01T21:00:47+00:00
- Post Title: Re: Inversion (2012) [PC]

good to know my work on the locale tool has gone to waste  
it kills my motivation to help you translator people
## Post #29
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-08-01T21:09:51+00:00
- Post Title: Re: Inversion (2012) [PC]

WRS: I wouldn't call your efforts wasted. Your tool needs only to be improved to allow the repacked locale text to be used by the game engine.
## Post #30
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-01T21:19:40+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from Rion
>
> WRS: I wouldn't call your efforts wasted. Your tool needs only to be improved to allow the repacked locale text to be used by the game engine.

from how i understand it, i just gave the wrong file to patch:

> Reply from Herdell
>
> The pure game (without update) reads the texts from out.s3darc.
The usage to get the texts and insert it back is the same as out_patch.s3darc.
## Post #31
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-08-01T22:14:07+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from WRS
>
> good to know my work on the locale tool has gone to waste  
it kills my motivation to help you translator people
Not a waste.
Game runs better and fastest when read file from conteiner.
When the game read files from a folder when are originally
intend to run it from conteiner, some slowdown may occur.

Your tool is great.
## Post #32
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-08-02T23:26:13+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from merlinsvk
>
> Can you explain that other ways?
I need the file. Someone can send me?
## Post #33
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-08-03T12:59:22+00:00
- Post Title: Re: Inversion (2012) [PC]

> Reply from delutto
>
> I need the file. Someone can send me?

'Far as I know, font files are contained within out.s3darc, which is almost 1,6 GB in size. My upload is sluggish, it'd take almost a week, but maybe someone else...?
## Post #34
- Username: linimil
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 24, 2012 4:46 am
- Post datetime: 2012-09-04T18:09:33+00:00
- Post Title: Re: Inversion (2012) [PC]

Somebody may explain for me, how to use this program exactly? i could extract the text file, but i can't put it back. i read all of the post, but however i tried, it never be good. 

Thanks for the answer.
