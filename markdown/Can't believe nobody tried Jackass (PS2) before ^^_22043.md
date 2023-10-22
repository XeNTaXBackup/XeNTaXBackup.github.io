## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-20T13:38:25+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

Since T.H.U.G. PRO, VR Chat and GTA games make it kinda easy to import custom models, I can't believe I couldn't find anything about Jackass: The Game (PS2) models/textures on the internet.


I quickly looked through the games files and saw that textures use .txd format...
So I tried a couple of things and eventually was able to extract most of the textures using this PS2 .txd-viewer: [http://www.thegtaplace.com/downloads/f4 ... txd-viewer](http://www.thegtaplace.com/downloads/f457-ps2-txd-viewer)
(sadly you are not able to extract multiple files at once)
Here are a few examples:


DOWNLOAD .TXD FILES:
[https://cdn.discordapp.com/attachments/ ... amples.zip](https://cdn.discordapp.com/attachments/628005960471805972/701780766270685274/Problem_Samples.zip)
These are 2 files I had problems with (except ryans face)

Most of the games sounds and music can be extracted by either cubeplayer or psound:
[https://tcrf.net/File:Jackass_voice_bam ... player=yes](https://tcrf.net/File:Jackass_voice_bam_abuse_01.ogg?embedplayer=yes)
Sounds are stored as .fsb files
towav also seems to open jackass .fsb files regarding this site: [http://www.ctpax-x.org/?goto=files&show=24](http://www.ctpax-x.org/?goto=files&show=24)

Models are .rws files....it seems to be a common renderware filetype.....although there are various kinds of .rws in non GTA games out there...
I used RWANALYZE to have it.....analyzed....I don't really know how to use the resulting info but it looks promising and spits out a few hex values and offsets.
DOWNLOAD IT HERE:
[http://files.steve-m.com/rwanalyze-0.4b.zip](http://files.steve-m.com/rwanalyze-0.4b.zip)

Can you guys please have a look at the models? Maybe there already is a script that extracts jackass .rws files aswell 
DOWNLOAD .RWS FILES:
[https://cdn.discordapp.com/attachments/ ... amples.zip](https://cdn.discordapp.com/attachments/628005960471805972/701775973242109962/Jackass_RWS_Samples.zip)
Johnnys and Ryans character models

Other than that...you might wanna give the game a try yourself....its great multiplayer fun!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-20T15:42:07+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from Henchman800 ↑Mon Apr 20, 2020 9:38 pm at Mon Apr 20, 2020 9:38 pm
>
> 
I used RWANALYZE to have it.....analyzed....I don't really know how to use the resulting info but it looks promising and spits out a few hex values and offsets.A few?   No, many too many... tedious task (the submeshes have about 42 vertices only).
.



johnny_costume01_lod-rws.png (17.92 KiB) Viewed 370 times
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-21T18:09:09+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from shakotay2 ↑Mon Apr 20, 2020 11:42 pm at Mon Apr 20, 2020 11:42 pm
>
> 
A few?   No, many too many... tedious task (the submeshes have about 42 vertices only).

Well ... damn xD
So every model consists out of like 20+ submeshes, each being more of a Puzzle piece other than actual sub objects like glasses or shoes and stuff?

Is every geometry-tab in the Analyzer useable at least?

Can you please let me know what settings you used for hex2obj?
Id like to at least start of the character extraction process by submitting one model to the models-resource.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-21T18:37:58+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from Henchman800 ↑Wed Apr 22, 2020 2:09 am at Wed Apr 22, 2020 2:09 am
>
> Is every geometry-tab in the Analyzer useable at least?Maybe, but I searched the start of vertices manually.  

> Can you please let me know what settings you used for hex2obj?Here you go (use 'Strip' and 'Fake' for auto generating FIs):


 johnny_costume01_lod_.zip
(1.4 KiB) Downloaded 16 times

(no uvs, sorry)

Here's the shoes with uvs:

0x0 500
Vb1
12 99
0x2EA26 42
021000
0x2EC36 8
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-22T18:57:21+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

Just in case you didn't start so far:


 Johnny_36SM.zip
(41.81 KiB) Downloaded 14 times


(ugly as always  , some superfluous faces, some missing, especially for his head)
head vertex start addresses:

0x3a58d
0x3aa8d
0x3af8d
0x3b48d
0x3b98d
0x3be8d
0x3c38d
0x3c88d

well, here's the missing head part:

0x0 30
Vb1
12 99
0x3CD8D 30
021000
0x3CF0D 8

(what an annoying format...)
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-23T10:28:45+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from shakotay2 ↑Thu Apr 23, 2020 2:57 am at Thu Apr 23, 2020 2:57 am
>
> 
Just in case you didn't start so far
(what an annoying format...)

Wow, thank you Very much man!   
I didn't statt converting by now... i gotta finish up two edits toll monday...this eats my time right now... :-/
But i cant wait to try it!

Doesn't RWAnalyze help with finding faces and offsets?
It looks so promising to me :-/
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-24T19:38:50+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from Henchman800 ↑Thu Apr 23, 2020 6:28 pm at Thu Apr 23, 2020 6:28 pm
>
> Doesn't RWAnalyze help with finding faces and offsets?
It looks so promising to me :-/Can't read the contents of the righthanded window of the tool and
maybe I'm to dumb, but no, I can't find data concerning the meshes which could ease the task:

```
		Struct  (4 bytes @ 0x2C454) - [0x01]
		Geometry  (76259 bytes @ 0x2C464) - [0x0F]
			Struct  (40 bytes @ 0x2C470) - [0x01]
			Material List  (490 bytes @ 0x2C4A4) - [0x08]
				Struct  (12 bytes @ 0x2C4B0) - [0x01]
				Material  (225 bytes @ 0x2C4C8) - [0x07]
					Struct  (28 bytes @ 0x2C4D4) - [0x01]
					Texture  (92 bytes @ 0x2C4FC) - [0x06]
						Struct  (4 bytes @ 0x2C508) - [0x01]
						String  (20 bytes @ 0x2C518) - [0x02]
						String  (4 bytes @ 0x2C538) - [0x02]
						Extension  (16 bytes @ 0x2C548) - [0x03]
							Sky Mipmap Val  (4 bytes @ 0x2C554) - [0x110]
					Extension  (69 bytes @ 0x2C564) - [0x03]
						UNKNOWN  (1 bytes @ 0x2C570) - [0x1FE]
						UNKNOWN  (44 bytes @ 0x2C57D) - [0x1DE]
				Material  (217 bytes @ 0x2C5B5) - [0x07]
					Struct  (28 bytes @ 0x2C5C1) - [0x01]
					Texture  (84 bytes @ 0x2C5E9) - [0x06]
						Struct  (4 bytes @ 0x2C5F5) - [0x01]
						String  (12 bytes @ 0x2C605) - [0x02]
						String  (4 bytes @ 0x2C61D) - [0x02]
						Extension  (16 bytes @ 0x2C62D) - [0x03]
							Sky Mipmap Val  (4 bytes @ 0x2C639) - [0x110]
					Extension  (69 bytes @ 0x2C649) - [0x03]
						UNKNOWN  (1 bytes @ 0x2C655) - [0x1FE]
						UNKNOWN  (44 bytes @ 0x2C662) - [0x1DE]
			Extension  (75693 bytes @ 0x2C69A) - [0x03]
>>>				Bin Mesh PLG  (28 bytes @ 0x2C6A6) - [0x50E]
				Native Data PLG  (73822 bytes @ 0x2C6CE) - [0x510]
					Struct  (73810 bytes @ 0x2C6DA) - [0x01]
<<<				Skin PLG  (1733 bytes @ 0x3E738) - [0x116]
					Struct  (1721 bytes @ 0x3E744) - [0x01]
				User Data PLG  (62 bytes @ 0x3EE09) - [0x11F]
	Atomic  (60 bytes @ 0x3EE53) - [0x14]
```
Seems the interesting part for (">>>") meshes, "Native Data PLG" is not unfoldable.
The "Section Data" exports are just copied bytes from the .rws loaded

You need to do the boring stuff, as always, find  the patterns, create a script.
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-24T20:00:27+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from shakotay2 ↑Thu Apr 23, 2020 2:57 am at Thu Apr 23, 2020 2:57 am
>
> 
well, here's the missing head part:

0x0 30
Vb1
12 99
0x3CD8D 30
021000
0x3CF0D 8


Can you help me out here please?
These settings for the missing head/hand part dont look right :-/

other than that.....thx for an almost complete johnny ^^
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-24T20:58:27+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

Maybe pay more attention to what I post? 

> Reply from shakotay2 ↑Wed Apr 22, 2020 2:37 am at Wed Apr 22, 2020 2:37 am
>
> 
"Here you go (use 'Strip' and 'Fake' for auto generating FIs)"

-> use Fake face indices (toggle uppermost right button) and "Strip"

btw: in your schreenshot, why is the uv address, 0x3a79d missing?

Full params of johnny_costume01_lod.rws_29.h2o is:

0x0 39
Vb1
12 99
0x3a58d 42
021000
0x3a79d 8

and it's NOT for the "missing head part", that is

0x0 30
Vb1
12 99
0x3CD8D 30
021000
0x3CF0D 8

Here's Ryan, btw:


 Ryan_costume01.zip
(154.32 KiB) Downloaded 14 times
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-25T12:00:23+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from shakotay2 ↑Sat Apr 25, 2020 4:58 am at Sat Apr 25, 2020 4:58 am
>
> 
Maybe pay more attention to what I post? 
shakotay2 wrote: ↑Wed Apr 22, 2020 2:37 am
"Here you go (use 'Strip' and 'Fake' for auto generating FIs)"

-> use Fake face indices (toggle uppermost right button) and "Strip"
sorry alter ^^



These settings got me the missing head part

So I found Johnnys missing head part (thx to you) but some of the uvs are merged together to one coordinate at 0,0 :-/
(and I'm still missing a small part of his left hand ^^)



Cleaned up Ryan (intro)

So with every costume comes 2 .rws files (like in the sample i attached to the first post), one being labled "intro". I assume you used this file for Ryan, right? Since he got 5 fingers per hand while johnnys model uses snow gloves as hands haha^^

looking at it right now:
johnny_costume01_intro.rws  --->  400 KB
johnny_costume01_lod.rws  --->  251 KB

So high and low res models for cutscenes and ingame i guess?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-26T14:48:37+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

> Reply from Henchman800 ↑Sat Apr 25, 2020 8:00 pm at Sat Apr 25, 2020 8:00 pm
>
> 
(and I'm still missing a small part of his left hand ^^)Simply copy/mirror/rotate his right hand.  

> one being labled "intro". I assume you used this file for Ryan, right?No, it's ryan_costume01.rws.

> So high and low res models for cutscenes and ingame i guess?Sounds logic.
.


 Johnny_intro.zip
(159.75 KiB) Downloaded 18 times
## Post #12
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-28T21:45:47+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

Thank you for all your help!
I got a clean ryan and johnny now   


it was still some work to clean up redundant edges...
will there ever be the chance for a jackass-.rws script or is the format to random to setup a proper one?

models are in queue for models-resource
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-28T22:10:23+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

There's no script afaik, this is what I used (unfinished, so probably at least one small mesh will always be missing):
.


 Make_obj-rws jackass.zip
(29.23 KiB) Downloaded 23 times


Use dlls from zip here:

> Reply from shakotay2 ↑Mon Apr 27, 2020 2:52 pm at Mon Apr 27, 2020 2:52 pm
>
> 
(There's a modified version of hex2obj needed for this format only, see next post.)
Good night.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-29T12:32:21+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

This is a modified version of hex2obj for Jackass (PS2) .rws files (you need the H2O files created by the above Makeobj, too).
It's not intended to be used with other formats!


 Hex2obj-rwx.zip
(204.46 KiB) Downloaded 27 times

(You shouldn't miss to read setup_FI-txt.txt!)

The exe doesn't work "standalone", it requires other files contained in the zip file here:

> Reply from shakotay2 ↑Tue Oct 22, 2013 10:06 pm at Tue Oct 22, 2013 10:06 pm
>
>
## Post #15
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-29T13:34:16+00:00
- Post Title: Can't believe nobody tried Jackass (PS2) before ^^

danke dir man! Ich werde es die tage ausprobieren
