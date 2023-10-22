## Post #1
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2014-04-20T07:20:09+00:00
- Post Title: Kinect Star Wars .smf

I happen to go back into the Kinect Star Wars Models the other night and was wondering where all the ships are like the venator,malevolence providence and ect... so i went into this dreadful game and though okay lets see if these are cutscene only models or not since i never really played the game and i happen to see that nope they aren't, so i said maybe there is a porblem with the bms script not extracting them and nope that wasn't the problem.

So i went and extracted very single .pod and podlzx and a couple files happen to spit out .lvl files and so i opened it in a hex editor and happen to realize this can just be opened in notepad++ so what it does is display every model in said level this is one here is from j_adv_felucia_6.lvl.

I scrolled down and came across these, there are thousands of models in these formats that aren't in the normal dfm format they range from vehicles to ships,more characters and weapons.  

```
	models\\ships_flight\\SP_CR90.smf
	models\\ships_flight\\SP_Delta_7b.smf
	models\\ships_flight\\SP_Delta_7b_Blue.smf
	models\\ships_flight\\SP_Delta_7b_Green.smf
	models\\ships_flight\\SP_Delta_7b_Yellow.smf
	models\\ships_flight\\SP_Lucrehulk.smf
	models\\ships_flight\\SP_Missile_Conc.smf
	models\\ships_flight\\SP_Munificent.smf
	models\\ships_flight\\SP_Recusant.smf
	models\\ships_flight\\SP_Subjugator.smf
	models\\ships_flight\\SP_Venator.smf
	models\\ships_flight\\turrets\\Launcher_A.smf

```


Here is a sample of some of models that are in this format.

[http://www.mediafire.com/download/k73b0 ... flight.rar](http://www.mediafire.com/download/k73b0nbag7l2w68/ships_flight.rar)

This is my first thread i've ever made on this site and i hope this is proper and really hope it wont get over looked cause a lot of these ships and models look really amazing from looking at them ingame.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-20T11:12:27+00:00
- Post Title: Kinect Star Wars .smf

using hex2obj (view link in my sig):



SP_ARC170_UVssmf.JPG (124.7 KiB) Viewed 769 times
## Post #3
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2014-04-20T18:49:59+00:00
- Post Title: Kinect Star Wars .smf

> Reply from shakotay2
>
> using hex2obj (view link in my sig):
SP_ARC170_UVssmf.JPG

Alright so i was able to get the arc-170 working but some odd reason it has no wings and there isn't another file for that so i'm not sure if it's stored in there or not.

But i'm not very good with this program and those numbers don't work for the rest of the models. Is it just about guessing random numbers or is there away to go about getting them?

Edit: Where in the Hex editor did you look for those numbers cause i've been reading up on your tutorial on hex2obj?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-20T22:18:40+00:00
- Post Title: Kinect Star Wars .smf

> Reply from JakeGreen
>
> Alright so i was able to get the arc-170 working but some odd reason it has no wings and there isn't another file for that so i'm not sure if it's stored in there or not.
Guess there's another submesh at 0xAEC0.



wings.JPG (38.59 KiB) Viewed 744 times



> But i'm not very good with this program and those numbers don't work for the rest of the models.You don't expect every model having the same vertex and face indices count, do you?

> Is it just about guessing random numbers or is there away to go about getting them?
>
> 
>
> Edit: Where in the Hex editor did you look for those numbers cause i've been reading up on your tutorial on hex2obj?You need to get the end of the face index list. For the first submesh
it's 0xAEBB. So the face indices block lenght is 0xAEBC-0x9500 =  6588 dec. /2 = 3294 (face indices count)
(other than the 3275 from the pic but that was just a quick hack.)
div 2 because the face indices are WORDs (2 bytes).

From the tut you'll know that the vertex count is calculated automatically so you don't need to care for it other than entering its value into the corresponding edit box.
## Post #5
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2014-04-21T00:51:28+00:00
- Post Title: Kinect Star Wars .smf

> Reply from shakotay2
>
> JakeGreen wrote:Alright so i was able to get the arc-170 working but some odd reason it has no wings and there isn't another file for that so i'm not sure if it's stored in there or not.
Guess there's another submesh at 0xAEC0.
wings.JPG
But i'm not very good with this program and those numbers don't work for the rest of the models.You don't expect every model having the same vertex and face indices count, do you?
Is it just about guessing random numbers or is there away to go about getting them?

Edit: Where in the Hex editor did you look for those numbers cause i've been reading up on your tutorial on hex2obj?You need to get the end of the face index list. For the first submesh
it's 0xAEBB. So the face indices block lenght is 0xAEBC-0x9500 =  6588 dec. /2 = 3294 (face indices count)
(other than the 3275 from the pic but that was just a quick hack.)
div 2 because the face indices are WORDs (2 bytes).

From the tut you'll know that the vertex count is calculated automatically so you don't need to care for it other than entering its value into the corresponding edit box.

So i pretty much got this down with using a calculator. but when it comes to the other models i don't know where to start in the hex editor on these models could you possible tell me where to start? Is the starting point the same for each model or does it change from model to model?

Sorry if i'm bugging you on it i'm just new to this.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-21T06:25:15+00:00
- Post Title: Kinect Star Wars .smf

> Reply from JakeGreen
>
> Is the starting point the same for each model or does it change from model to model?It changes for this game.
As another example take SP_Delta_7b.smf.
Search for 00 00 00 01 00 02. There are 6 finds (so 6 submeshes to be expected).

First find at 0x1490. Scroll up through the previous vertex block for the first FFFFFFFF pattern.
It's at 0x1210. Subtract 0x20 to find the startaddress of the block (0x11F0).

edit: vertex and face counts (DW, DW, little endian!) easily to be found after fifteen FFFFFFFF 00000000 00000000 patterns
But don't confuse the FFFFFFFF from these  patterns with the ones in the vertex blocks.
(and keep in mind that the face indices count is 3x face count)

For the 3rd submesh create a h2o file (textfile renamed to *.h2o)
and copy/paste these lines into it:
0x4E090 26994
Vb1
36 16
0x1830 8706
120100
0x0 255
## Post #7
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-24T12:51:37+00:00
- Post Title: Kinect Star Wars .smf

some one can generate a noesis pluggin ?? for .smf file ...

sample + texture files:
[http://www.filedropper.com/spscimitarsithinfiltrator](http://www.filedropper.com/spscimitarsithinfiltrator)

best regards
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-24T17:44:10+00:00
- Post Title: Kinect Star Wars .smf

I would create a Make_H2O project of it if I had time...
(Sadly there are no users of this C-project with sources.)

Vertex and face counts (DW DW, little endian!) easily to be found after fifteen FFFFFFFF 00000000 00000000 patterns.



SP_Scimitar.JPG (63.21 KiB) Viewed 609 times
## Post #9
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-05-24T18:03:10+00:00
- Post Title: Kinect Star Wars .smf

> Reply from CZW
>
> some one can generate a noesis pluggin ?? for .smf file ...

sample + texture files:
http://www.filedropper.com/spscimitarsithinfiltrator

best regards

I would second a Noesis Plugin or whatever would make it easy to get the models out cause i know very little about hex editing so like i said in my first post there is a lot of great star wars models in this game that are in SMF
## Post #10
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-24T21:25:30+00:00
- Post Title: Kinect Star Wars .smf

> Reply from shakotay2
>
> I would create a Make_H2O project of it if I had time...
(Sadly there are no users of this C-project with sources.)

Vertex and face counts (DW DW, little endian!) easily to be found after fifteen FFFFFFFF 00000000 00000000 patterns.
SP_Scimitar.JPG

thks ...
i have test the second part of this submeshes ... 





thks alot ...
## Post #11
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-24T23:34:28+00:00
- Post Title: Kinect Star Wars .smf

second test
## Post #12
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-05-25T00:36:36+00:00
- Post Title: Kinect Star Wars .smf

So i took a little time an was able to got back at it and was able to get a couple models out but why doesn't any of them have a UV like i can view it in the uv tab and it exports to testuv.obj but i'm not sure how to get the uv with the model itself.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-25T05:37:36+00:00
- Post Title: Kinect Star Wars .smf

> Reply from JakeGreen
>
>  and it exports to testuv.obj but i'm not sure how to get the uv with the model itself.did you try
File/ SaveAs mesh?
## Post #14
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-05-25T06:12:09+00:00
- Post Title: Kinect Star Wars .smf

> Reply from shakotay2
>
> JakeGreen wrote: and it exports to testuv.obj but i'm not sure how to get the uv with the model itself.did you try
File/ SaveAs mesh?

Ah i completely forgot about that thanks that worked.
## Post #15
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-25T07:44:31+00:00
- Post Title: Kinect Star Wars .smf

thks shakotay2 

the 0.24 , crash for me for a missing dll
but your 0.24_W8, work fine, past into the 0.22 directory

i can continue on big files
## Post #16
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-25T19:33:23+00:00
- Post Title: Re: Kinect Star Wars .smf

thks again shakotay2

new test on more complex sample
## Post #17
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2015-06-19T01:50:58+00:00
- Post Title: Re: Kinect Star Wars .smf

Hey, does anybody on this thread now the file format or type as to where the sound effects are stored?
## Post #18
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-06-19T06:07:21+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from ARAJediMaster
>
> Hey, does anybody on this thread now the file format or type as to where the sound effects are stored?

look like the sound folder
extension .wem

on my side, i'm still looking for a Noesis plugin for .smf files
abandoned Battlefront 3 and Kinect, share the same models database , most are in .smf format
## Post #19
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2015-06-19T13:43:01+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from CZW
>
> look like the sound folder extension .wem

on my side, i'm still looking for a Noesis plugin for .smf files
abandoned Battlefront 3 and Kinect, share the same models database , most are in .smf format

With all due respect, another user disagrees:

> Reply from durandal217
>
> Your looking for xb2pkgsnd.POD for the sound effects..

I wonder know how I would be able to extract the sound effects themselves.
## Post #20
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-06-20T06:40:26+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from ARAJediMaster
>
> CZW wrote:look like the sound folder extension .wem

on my side, i'm still looking for a Noesis plugin for .smf files
abandoned Battlefront 3 and Kinect, share the same models database , most are in .smf format

With all due respect, another user disagrees:
durandal217 wrote:Your looking for xb2pkgsnd.POD for the sound effects..

I wonder know how I would be able to extract the sound effects themselves.

as you want, trust me or not .... but as soon as you unpack the xb2pkgsnd.POD
the unpacker create a folder sound, with files and extension  .wem

because i have unpack it, the file xb2pkgsnd.POD ....



if you want a sample
[http://www.filedropper.com/412339922](http://www.filedropper.com/412339922)

you need to find the way to convert it in wave format ....

> The RIFX file format is identical to the RIFF file format except that all values
>
> are in Motorola byte order.
>
> OFFSET              Count TYPE   Description
>
> 0000h                   4 char   ID='RIFX'
>
> 0004h                   1 dword  Block size. This size is the size of the block
>
> 								 controlled by the RIFX header.
>
> 								 ="BSZ"
>
> 0008h                   4 char   Format name.
>
> REFERENCE:DDJ0994
>
> SEE ALSO:RIFF

Edit: Mr Aluigi have done a BMS script for this RIFX / RIFF format
## Post #21
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-06-26T19:33:16+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from CZW
>
> some one can generate a noesis pluggin ?? for .smf file ...

sample + texture files:
http://www.filedropper.com/spscimitarsithinfiltrator

best regards

a little up ...
if someone can do it ...
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-16T19:22:10+00:00
- Post Title: Re: Kinect Star Wars .smf

yep, a Noesis plugin would be nice but guess those who could create one are too busy or not interested in these models.

But accidently I managed to fulfill your request by PM for some H2O files:


 Make_H2O_KinectSW.zip
(54.14 KiB) Downloaded 72 times



Be sure to read the contained How-to-use_KinectStarWars.txt before proceeding.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-16T19:23:45+00:00
- Post Title: Re: Kinect Star Wars .smf

here's some result with 102 submeshes (not all are visible of course):



Lucrehulk_.JPG (223.47 KiB) Viewed 257 times



 --- VERY important! ---

You'll need to understand this OR you will fail. Promissed!

Now I found that you just need to >adjust< the vertices start address for the very first mesh
and then let it go. Works for some models.

For Scimitar you've to change the proposed address in the editbox from 3470 to 3550,
for Tran_DropShip from 1210 to 1220
and for SP_Lucrehulk from 17FA0 to 19250 manually.

How to get that damned 19250?

You'll have to find the 4 FFs at 19270 and those characteristic zeroes at 1924A
then subtract 0x20 from 0x19270 to get 0x19250.

```

019240  4E 45 14 DE C4 43 8F 5E  99 45 00 00 00 00 00 00   NE.ÞÄC^™E......
019250  44 6F AB 23 42 4F 4C 98  C5 D2 9A 66 81 82 00 40   Do«#BOL˜ÅÒšf‚.@
019260  38 02 37 FB 08 00 03 FF  F8 20 08 00 00 00 00 00   8.7û...ÿø ......
019270  FF FF FF FF 44 7A CE 14  C2 62 BC 6A C5 D2 9B 33   ÿÿÿÿDzÎ.Âb¼jÅÒ›3
```


That's all what I can tell.
(If you can't take this hurdle I'm sorry to say that you're lost then.)

Example:
 start Make_H2O
 File/open SP_Lucrehulk.smf
 change 17FA0 to 19250 in the editbox as told above
 File/open SP_Lucrehulk.smf AGAIN (yes, prefer to waste your time rather than mine;-)- Creates 108 H2O files then. (last 6, 103 to 108 to be erased because they are dummies only)

and 'yes', I had no time to separate the LODs, if any, so you'll have them all-in-one.
Sry for that.
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-16T22:06:50+00:00
- Post Title: Re: Kinect Star Wars .smf

Providence; but there's some caveats to quarrel with before I can update the exe:



Providence.JPG (158.47 KiB) Viewed 252 times
## Post #25
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-17T03:34:33+00:00
- Post Title: Re: Kinect Star Wars .smf

Awesome!  



venswk.PNG (224.77 KiB) Viewed 244 times



i've been tinkering around with the dfm script to work with these smf files but i just don't know enough about programming to know when, where or how to use code.
## Post #26
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-10-17T07:41:17+00:00
- Post Title: Re: Kinect Star Wars .smf

great work Shakotay

@Ace, you have say .tex are the same as .tga file

[https://drive.google.com/file/d/0B38_2a ... sp=sharing](https://drive.google.com/file/d/0B38_2aQCnZ7bUGlIdE5oNDBKcWM/view?usp=sharing)

i have adapt the .tga to read .tex file directly without renaming into .tga
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-17T08:28:46+00:00
- Post Title: Re: Kinect Star Wars .smf

I don't know, i never use the tex files in this game. i just convert the game tga into usable tga with chrrox's  fmt_star_wars_kinect_tga.py script. are they higher res than the game tga files?
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-17T11:09:42+00:00
- Post Title: Re: Kinect Star Wars .smf

I've updated the zip in my first post as of Fri Oct 16, 2015.
Providence should work now. But it's huge (that's 235359 vertices) and maybe some submeshes have wrong positions.
Use 14D50 as vertices start address instead of proposed 132ae.
(yeah, you've to subtract 0x24 from FFs address 14D74 here because of FVF 40= 36+4)

Tried blender 2.75 but it's a little bit unhandy with displaying the whole thing, even if scaled down.
So I exported it as obj then displayed it in Noesis (while in blender some SMs are displaced for whatever reason you can have a nice look into the interiors there):



Providence_N.JPG (95.15 KiB) Viewed 222 times



btw: hold a backup from the old Make_H2O_KinectSW.exe.
(Not sure whether I introduced new bugs while fixing it.  )

When I imported the exported obj into 3dsmax the mesh was totally f. up.
gw:OBJ-Importer's option 'Import as single mesh' did the trick.
## Post #29
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-17T19:07:58+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from AceWell
>
> Awesome!  
venswk.PNG

i've been tinkering around with the dfm script to work with these smf files but i just don't know enough about programming to know when, where or how to use code.

Was that done with the new tool here or with you messing around with the script?
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T16:52:51+00:00
- Post Title: Re: Kinect Star Wars .smf

well, three years later - new models to come. Seems the Make_H2O tool needs some patching; the face indices start address is deadly wrong, and FVF is 40 instead of 36 here:



sail_barge-smf.jpg (222.93 KiB) Viewed 84 times
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T19:34:32+00:00
- Post Title: Re: Kinect Star Wars .smf

well, for some funny reason I compiled the source and it worked with the sail_barge.smf (must have done some change without a note):



sail_barge.jpg (223.64 KiB) Viewed 157 times
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T19:38:32+00:00
- Post Title: Re: Kinect Star Wars .smf

Here's the new Make_H2O.exe plus readme:


 Make_H2O-KinectStarwarsNew.zip
(160.84 KiB) Downloaded 28 times


Make_H2O needs a dll from the zip here:
[https://forum.xentax.com/viewtopic.php? ... st#p111156](https://forum.xentax.com/viewtopic.php?f=16&t=11436&p=111156&hilit=who+would+request#p111156)

(py script for blender also contained,
the pattern FFFFFFFF in smfs, mentioned in the old readme has changed to 00000000, followed by one FF, btw)

(Be sure to get hex2obj.exe and the dlls in case you don't have it.)
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T19:59:54+00:00
- Post Title: Re: Kinect Star Wars .smf

Subjugator (has the 4 FFs again):



Subjugator.jpg (222.86 KiB) Viewed 157 times


vAddr is 0x15070
## Post #34
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-09-30T07:44:57+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from shakotay2
>
> Here's the new Make_H2O.exe plus readme:
Make_H2O-KinectStarwarsNew.zip
Make_H2O needs a dll from the zip here:
https://forum.xentax.com/viewtopic.php? ... st#p111156

(py script for blender also contained,
the pattern FFFFFFFF in smfs, mentioned in the old readme has changed to 00000000, followed by one FF, btw)

(Be sure to get hex2obj.exe and the dlls in case you don't have it.)

Hi shakotay ...

i try to use your new H2O
but it seems for me , it doesn't work ... it cannot generate h2o parts ... the old work , not the new ..

the new ..

[https://ibb.co/dea5Bz](https://ibb.co/dea5Bz)
address set, i select the .smf ... nothing append

the old

[https://ibb.co/j2hfde](https://ibb.co/j2hfde)
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-30T08:53:47+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from CZW
>
> 
the new ..

https://ibb.co/dea5Bz
address set, i select the .smf ... nothing append

the old

https://ibb.co/j2hfdeHi CZW,
yeah, you need to select KinectSW in the lower right combo box (not CaptnAmerica). Should have mentioned that in the readme.
## Post #36
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-09-30T09:47:35+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from shakotay2
>
> CZW wrote:
the new ..

https://ibb.co/dea5Bz
address set, i select the .smf ... nothing append

the old

https://ibb.co/j2hfdeHi CZW,
yeah, you need to select KinectSW in the lower right combo box (not CaptnAmerica). Should have mentioned that in the readme.

KinectSW is not into the list , into your new file
H2O maker, Don't give the choice as your previous


[https://ibb.co/hHqdgz](https://ibb.co/hHqdgz)
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-30T12:30:48+00:00
- Post Title: Re: Kinect Star Wars .smf

you need to scroll down the list 'til its end using the cursor down key:



KinectSW.jpg (45.24 KiB) Viewed 133 times


(yeah, sorry, "secret feature", I did miss the scroll wheel handling with this ugly combo box  )
## Post #38
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-09-30T13:32:39+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from shakotay2
>
> you need to scroll down the list 'til its end using the cursor down key:
KinectSW.jpg
(yeah, sorry, "secret feature", I did miss the scroll wheel handling with this ugly combo box  )

loool !! nice trick !!
## Post #39
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-18T17:12:43+00:00
- Post Title: Re: Kinect Star Wars .smf

A few weeks ago someone asked for help for that format on the discord server and I ended up making a Noesis script for it, I forgot to post it on the forums (wish I knew about that thread before, would have saved me some time).
It will extract all submeshes with UVs, along with the collision shapes meshes if the option at the top of the script is set to True.

I won't update it if some models don't work but there are a lot of comments so it'll be easily fixable  if needed.
[fmt_smf.zip](https://xentaxbackup.github.io/file/18760_fmt_smf.zip)
## Post #40
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2020-09-19T04:25:46+00:00
- Post Title: Re: Kinect Star Wars .smf

> Reply from Joschka ↑Sat Sep 19, 2020 1:12 am at Sat Sep 19, 2020 1:12 am
>
> 
A few weeks ago someone asked for help for that format on the discord server and I ended up making a Noesis script for it, I forgot to post it on the forums (wish I knew about that thread before, would have saved me some time).
It will extract all submeshes with UVs, along with the collision shapes meshes if the option at the top of the script is set to True.

I won't update it if some models don't work but there are a lot of comments so it'll be easily fixable  if needed.

Thanks so much for this, but i have a problem i can't open any smf file in noesis it just throws me this error,i've tried opening files that i've seen others open in it just fine but just won't open for me so i know they work it's just something on my end. Oh and yes Noesis is fully updated.


UPDATE IGNORE THIS I REDOWNLOADED NOESIS INSTEAD OF UPDATING AND IT FINALLY WORKED.
