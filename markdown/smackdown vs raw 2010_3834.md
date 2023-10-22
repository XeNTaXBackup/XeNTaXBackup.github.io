## Post #1
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-11-03T18:55:16+00:00
- Post Title: smackdown vs raw 2010

here is the savedata.dat file from the paint tool can any one come up with a way to edit it on a pc so we could import images to the game 
I beleave its a refrence file and the game uses it to make textures
please help.. 
If you open this in note pad you see the image but not if you use a hex editor...

[http://www.box.net/shared/524pyoh761](http://www.box.net/shared/524pyoh761)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-07T08:51:09+00:00
- Post Title: smackdown vs raw 2010

firstimage_256_256.jpg (50.03 KiB) Viewed 3008 times



Here's what I think:
There's a list of 256x256 images, 8-bit, 256 colours, in that SaveData.dat file. 
They start with a palette and then the raw image data. There are only two images, I saw, the rest is all blank. 

For instance, the first imagedata starts at 1068 (the palette is before that, 1024 in size (4 bytes per colour? RGB-alpha?). It depends on what the colour should be in the original game?


 image1raw.zip
(1.72 KiB) Downloaded 79 times





image1.png (2.51 KiB) Viewed 3002 times
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-03T10:20:57+00:00
- Post Title: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-03T13:09:18+00:00
- Post Title: smackdown vs raw 2010

Thanks Mr.Mouse..

plodtrew ur on the ball.. lol Mr.Mouse how would I make a normal image in to this format.. 

Thanks
## Post #5
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-04T03:04:18+00:00
- Post Title: smackdown vs raw 2010

this would elevate caw making ten fold easily imagine....
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-04T06:42:29+00:00
- Post Title: smackdown vs raw 2010

> Reply from snyperstyle
>
> this would elevate caw making ten fold easily imagine....

What????
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-04T06:44:49+00:00
- Post Title: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-04T08:08:16+00:00
- Post Title: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-04T08:10:46+00:00
- Post Title: smackdown vs raw 2010

what was meant by my statement mr mouse is that if we could edit images in photoshop and insert them into the game by using this save file it would be incredibly easy to make perfect attires, tattoos, logos or other textures from the created wrestler feature in the game.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-04T09:02:54+00:00
- Post Title: smackdown vs raw 2010

I see!  ok, let's have a look then.
## Post #11
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-04T09:10:53+00:00
- Post Title: smackdown vs raw 2010

Yeah this would be amazing!  The possibilities would be endless.

Also plodtrew just so you know I downloaded the file and resigned it and it worked great on my profile..... Nice Hogan and Razor logos! They are awesome!  Any chance you could make a good tna logo? (I tried and failed miserably)
## Post #12
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-04T10:19:25+00:00
- Post Title: smackdown vs raw 2010

> Reply from JBP
>
> Yeah this would be amazing!  The possibilities would be endless.

Also plodtrew just so you know I downloaded the file and resigned it and it worked great on my profile..... Nice Hogan and Razor logos! They are awesome!  Any chance you could make a good tna logo? (I tried and failed miserably)

What tool did you use to resign it?
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-04T23:09:29+00:00
- Post Title: smackdown vs raw 2010

Okay, there are graphics in it, like two PNGs and more. Got more examples? I need those to compare general structure.
[png1.png](https://xentaxbackup.github.io/file/2590_png1.png)
## Post #14
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-05T04:00:43+00:00
- Post Title: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-05T07:56:25+00:00
- Post Title: smackdown vs raw 2010

Okay, but your file has bytes of 0x20 (32) in stead of 0's where 0's should be. Did you do something to the file, or had the other paintool.pt file been altered somehow? I would prefer if that could be fixed somehow.
## Post #16
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-05T08:32:36+00:00
- Post Title: Re: smackdown vs raw 2010

This file came straight off of my 360 hdd.  I have an older version of the file on my desktop, but I'm not near it now. I will upload asap.
## Post #17
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-05T10:07:03+00:00
- Post Title: Re: smackdown vs raw 2010

I didnt alter my paint tool file at all. Jst have more logo's in it. The wwe png file you posted seems to be in all the save files, not just the paint tool files.
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-05T11:04:32+00:00
- Post Title: Re: smackdown vs raw 2010

well, that is odd then. bytes of 32 where 0 should be. hmm. anyway, i can get to the tattoos. I will try to create an extractor/inserter.If you've got more examples then please do upload them.
## Post #19
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-05T11:34:00+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Okay, there are graphics in it, like two PNGs and more. Got more examples? I need those to compare general structure.
Those two PNG files are the logos used in the 360 dashboard when you look at the saves for your game.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-07T22:56:03+00:00
- Post Title: Re: smackdown vs raw 2010

Do you have any screenshots of the tattoos in action? It would help to compare. I have a "Hollywood" tattoo for instance, but I need to know the width + height that it has in your game.
## Post #21
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-08T01:13:40+00:00
- Post Title: Re: smackdown vs raw 2010

This isn't my file but I'll go ahead and answer, because I think I know what you are talking about.  The hollywood image is at the bottom of a 256x256 image.
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-08T22:34:38+00:00
- Post Title: Re: smackdown vs raw 2010

Yes,okay, these are some I can extract:



cond.JPG (9.67 KiB) Viewed 650 times





Kopie (2) van cond.JPG (10.29 KiB) Viewed 651 times





Kopie van cond.JPG (11.58 KiB) Viewed 651 times



Are they all correct?
## Post #23
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-09T00:04:53+00:00
- Post Title: Re: smackdown vs raw 2010

The Hollywood one seems to look correct.  The others look doubled, but they don't appear that way in the game.  Do you have an idea on what format these are in and if it would be possible to hex an image in over the ones you found.
## Post #24
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-09T06:13:59+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Yes,okay, these are some I can extract:
cond.JPG
Kopie (2) van cond.JPG
Kopie van cond.JPG

Are they all correct?

the hollywood logo is corect, the others are doubled. I think the reason for this is that the game allows you to create logo's in either "lowres" (128x128) or hi-res (256x256). the hollywood logo is 256x256 and the other two are 128x128. 

also the black areas above and below the logos are supposed to be transparent. I'm away from home at the moment so I cant post any in game pics.

This is looking really promising, looking forward to what you come up with.
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-09T08:59:42+00:00
- Post Title: Re: smackdown vs raw 2010

Okay, good, that helps. If you can confirm that these indeed are 128x128, then it makes sense. I'm trying to find a variable in the file that will tell the game that a picture is in high or low res. I will see again.

Also, please do post in-game pics, so I can compare colours.
## Post #26
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-10T02:37:46+00:00
- Post Title: Re: smackdown vs raw 2010

yeah mr mouse they are 128x128 and the other is 256x256 so those are correct. Now all we need is a way to insert new images into that save file
## Post #27
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-10T05:03:26+00:00
- Post Title: Re: smackdown vs raw 2010

Why are you spending so much time trying to add a custom logo for a CAW.  You'd be better off spending time adding custom textures to the in-game wrestlers or better yet, making a new model for the game.
## Post #28
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-10T05:13:09+00:00
- Post Title: Re: smackdown vs raw 2010

true brienj but alot of people dont have the know how to texture edit the ingame models and would like to have CAWs of other wrestlers like aj styles, great muta etc. Its not like we can rip a tna model convert it to a svr model and add it to the game.
## Post #29
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-10T05:35:52+00:00
- Post Title: Re: smackdown vs raw 2010

The blood drip and freakzilla logos are definitely 128x128. I away from my xbox for the next few weeks and cant take grid pics. However I can post in game pics of the logos. I hope it helps:










@brianej, there are some wrestlers who dont have thq made models e.g steiner, goldberg, hollywood hogan, nash, hall ,etc. Until there is a easy way to edit the in game models and convert back into yobj, we're stuck with caws. Also if reinjecting is possible, we can inject the textures of models from other games and apply it to caws.
## Post #30
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-10T07:03:07+00:00
- Post Title: Re: smackdown vs raw 2010

Okk, thanks , this certainly helps. When you get the chance please also take pics from the grid. I think I know where the information on image size is stored.
## Post #31
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-10T09:45:12+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from plodtrew
>
> @brianej, there are some wrestlers who dont have thq made models e.g steiner, goldberg, hollywood hogan, nash, hall ,etc. Until there is a easy way to edit the in game models and convert back into yobj, we're stuck with caws. Also if reinjecting is possible, we can inject the textures of models from other games and apply it to caws.

Mate It would be the same as style as wwe raw, but, copy the wrestler model rename it edit textures and re-pac the file.. I'm waitin for a way to add textures as I have a updated big show and so far working on goldberg based off SCSA, Shamus based off Mr K, and slammaster J based off shad.. see as the chEtc.pac you can resize the models..
## Post #32
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-10T12:33:00+00:00
- Post Title: Re: smackdown vs raw 2010

Well I guess I'm just unsure how to re-pac the files. I could do it in a hex editor but the files I would reinsert would likely be larger just because I don't know how to recompress to bpe.  If I reinseted them my offsets would be off due to the larger files. Would this matter or could I just continue adding the rest of the files?  If it does matter does anyone know what needs to be fixed?

Also what plodtrew said about addidng textures to paint tool would be amazingly nice.  Making CAWS would be inzane.
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-10T13:25:54+00:00
- Post Title: Re: smackdown vs raw 2010

From what I've gathered so far from these painttool files is that they can have up to 20 tattoo images or so. Is this correct? Do you know how many you can create?
## Post #34
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-10T13:35:04+00:00
- Post Title: Re: smackdown vs raw 2010

Yeah 20 slots is correct.
## Post #35
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-10T13:58:48+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from JBP
>
> Well I guess I'm just unsure how to re-pac the files. I could do it in a hex editor but the files I would reinsert would likely be larger just because I don't know how to recompress to bpe.  If I reinseted them my offsets would be off due to the larger files. Would this matter or could I just continue adding the rest of the files?  If it does matter does anyone know what needs to be fixed?

Also what plodtrew said about addidng textures to paint tool would be amazingly nice.  Making CAWS would be inzane.

I'm in the same boat as you mate I've only just started looking in to hexing last time I did any hexing was wwe raw, i would guess the size wouldnt matter due to the fact your not replacing a model, but adding it to the game?
## Post #36
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-10T14:22:32+00:00
- Post Title: Re: smackdown vs raw 2010

@mr mouse, I'm away for the next few weeks. Getting married next week so I wont be able to post grid pics soon. I did take a pic some time back and I'm nor sure if the design is in one of the designs I posted. The grid pic is the small pic inset:



@draven, already retextured hogan to an nwo version, check out my thread in the compressed files section. Also made some model edits to scsa into goldberg using misfit 3d. Just have no idea how to reinject the images and convert back into yobj.
## Post #37
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-10T14:33:27+00:00
- Post Title: Re: smackdown vs raw 2010

Excellent plodtrew, that image is indeed in ! And congratulations!! (have a wonderful marriage and time!).
## Post #38
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-10T18:10:26+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from plodtrew
>
> @mr mouse, I'm away for the next few weeks. Getting married next week so I wont be able to post grid pics soon. I did take a pic some time back and I'm nor sure if the design is in one of the designs I posted. The grid pic is the small pic inset:



@draven, already retextured hogan to an nwo version, check out my thread in the compressed files section. Also made some model edits to scsa into goldberg using misfit 3d. Just have no idea how to reinject the images and convert back into yobj.

You could just edit the textures not the models  this is what we did to model swap in wwe raw..
## Post #39
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-10T20:01:39+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from DRAVEN
>
> 
You could just edit the textures not the models  this is what we did to model swap in wwe raw..

Then the faces and body dont neccesarily have the same shape as the wrestler you are trying to emulate. It only has a texture applied over the same mesh. model editing allows you to e.g. increase austins jaw height and get rid of his knee braces when creating a goldberg mod. 

Check out my sf4 mods on my blog to see what I mean.

@mr mouse, thank you
## Post #40
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-10T21:54:49+00:00
- Post Title: Re: smackdown vs raw 2010

yer I know m8 but we make best of what we have  I hope someone can make the export tool thats needed also a way to repack the pac files..
## Post #41
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-10T22:39:16+00:00
- Post Title: Re: smackdown vs raw 2010

I hope we figure that out also.  Life would be much easier lol

I also hope we figure out this paint tool thing.  If we could somehow insert our own images then we wouldn't need to reskin in game models.
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-11T18:24:33+00:00
- Post Title: Re: smackdown vs raw 2010

Tell me, are all 20 slots for images filled? Or only some? Is this sequential or can you leave some slots blank and fill others?
## Post #43
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-11T20:35:22+00:00
- Post Title: Re: smackdown vs raw 2010

I dont think all 20 slots are filled, not sure though. It's not sequential, you can select which slot you want you picture to fill and delete any slots you choose.
## Post #44
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-12T08:33:34+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from plodtrew
>
> 
@brianej, there are some wrestlers who dont have thq made models e.g steiner, goldberg, hollywood hogan, nash, hall ,etc. Until there is a easy way to edit the in game models and convert back into yobj, we're stuck with caws. Also if reinjecting is possible, we can inject the textures of models from other games and apply it to caws.
Hogan has a model in 2007, as well as an even more retro one in LOW.  The model in 2007 can easily have the textures redone to make Holywood Hulk Hogan.  The PAC files are easy to rebuild, it just takes some time, and you can put non-BPE compressed DDS files into them, the game will read them.  

If you are going to do the logo thing for CAWs, you might as well go all out and find the in-game logos in the edXX.pac files and replace those instead.  You have a limit to the amount you can use with custom logos, but not the in-game logos.  Also, the in-game logos are all high quality.
## Post #45
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-12T08:41:23+00:00
- Post Title: Re: smackdown vs raw 2010

I've been wondering where these files were.
Thanks for your help, but I'm having a problem finding these files in the edxx.pac.

All I'm getting is yobj and pof0 files.  I noticed the casThumb one had about a ton of dds files in it but they are just the thumb of the file I assume. Like in the selection screen.
## Post #46
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-12T12:03:48+00:00
- Post Title: Re: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #47
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-12T22:11:48+00:00
- Post Title: Re: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #48
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-13T17:05:51+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from brienj
>
> If it ever downloads, I'll check them out.  

Edit:  That's right, the 2007 models have a TON of dds files, which makes it more of a pain to retexture and rebuild a new pac file, but it does make it better to modify them and make it look better.  I don't have the time to rebuild a pac file with that many new offsets.  Hopefully when I got time, I can make something to repack files.  If someone can make a Yukes BPE compressor, that would work too.  Also, I am almost positive the game can read ZLIB files, the problem is that I don't know how to properly make it read them correctly.  I am almost certain that one of the pac files in the game had some ZLIB compressed data in them, if anybody finds those, then we could always recompress hacked textures with ZLIB (which compresses them more than BPE) and they should go into the PAC file with very little modification to the header.

A repacker wold be great. I've also done the same mod with low hogan and can upload that if it's easier to repack. There is only one dds texture for the character. The only downfall was that the hair wasnt accurate for that era and he doesnt have a bandanna. I can upload the texture if you can repack it.
## Post #49
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-13T18:56:03+00:00
- Post Title: Re: smackdown vs raw 2010

If anyone else has got such a painttool.pt file for me, I need them to compare with what I got. The second one I have does look corrupted, to be honest.
## Post #50
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-13T23:54:14+00:00
- Post Title: Re: smackdown vs raw 2010

Okay, so I confirmed at least where in the file the resolution of the images is stored.

At 0xD000 there is this: 

```
[1]  Byte (3)

// Then comes the list of slots used in the order of the textures in the file. 

[20]  Byte : 0 means slot unused, 1 means slot used

// Now comes the resolution of the textures, as a list.

[20]  Byte: 0 means 128x512 (or perhaps 128x128, but the image data is 65536 in size), 1 means 256x256


```


Now, halfway through the file the image data (texture 11) is interrupted by some other stuff. This is 0x4000 (16K) in size. After that, the image data continues, until all 20 textures are stored. At the end of the image data, a part of 0x1ee0 is stored. 
Now, the whole texture image part (savedata.dat section) starts at 0xc000 and is 0x148000 bytes big, excluding the interrupting part I mentioned before. Therefore, the last section of 1ee0 is merely filling up to a bank size of 16k (or perhaps a clustersize of 16k?). 0x148000 /  0x4000 = 52.  The savedata.dat section in size is actually 0x146120, so the last part of the file is needed to get to 52 banks/reads for the data. 
Okay, so far so good, but the second file I examined is misaligned from texture 2. The image data should be 0x10400 big, including 0x400 palette data, but it is in fact 0x103ec,there's 20 bytes lacking! Because of this, the rest of the file is out of phase too. 
This is why I think the second file is corrupted somehow.
## Post #51
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-14T00:16:44+00:00
- Post Title: Re: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
## Post #52
- Username: JBP
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-14T06:48:12+00:00
- Post Title: Re: smackdown vs raw 2010

Yes, that´s much better, now we are getting somewhere. I can whip up an extractor, replacer for this.
## Post #53
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-14T08:29:57+00:00
- Post Title: Re: smackdown vs raw 2010

That would be so amazingly increadible lol.  I can't wait to try it out when you get it done!
## Post #54
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-14T08:31:36+00:00
- Post Title: Re: smackdown vs raw 2010

You probably get this alot but im naming my son after you  lol. Thanks alot though for all the work It truly is appreciated I can honestly say between this and brienj's tutorial this is gonna be the most fun xmas ever lol
## Post #55
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-14T09:29:20+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from JBP
>
>  Do you know what format the images are in, and if they look like they could easily be replaced?

Basically, the image are 256-colour bitmaps. Each byte is one pixel, so an image can be up to 256x256 (or 128x512) bytes big. There is a RGBA palette I think, each of the 256 colours is written in big endian (A B G R), but it could be ARGB (this should be tested). The alpha transparency value mostly is 255 or 0xFF (i.e. the pixel is not transparant).  

Using a standard 8-bit .BMP header I can convert them to images you can edit.
## Post #56
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-14T10:28:54+00:00
- Post Title: Re: smackdown vs raw 2010

Sounds a bit complicated, but maybe not to bad when I'm not as tired and can wrap my head around it.   I look forward to the  extractor/replacer.  Do you have an eta? 

(I'm not trying to rush you into making it right away or anything by asking that lol.  I understand we all have life's to live, and if your answer is "I'll get it done when I get it done" Thats fine lol.)
## Post #57
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-14T14:50:13+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Yes, that´s much better, now we are getting somewhere. I can whip up an extractor, replacer for this.

Awesome news. Really looking forward to the release of this tool.
## Post #58
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-15T23:20:27+00:00
- Post Title: Re: smackdown vs raw 2010

Okay here's a preview. At the moment just a simple .PT explorer.



ptexp.jpg (183.95 KiB) Viewed 1272 times





ptexp2.jpg (166.4 KiB) Viewed 1265 times



It just opens and saves .PT files. Not idiot-proof mind you and a pre-alpha version, will probably crash when corrupted files are attempted to be opened. 

I've been thinking, perhaps these are textures were originally DDS files, you know, the 8-bit, palette + 256 colours + alpha type with uncompressed bitmap. Would make sense in terms of xbox ?


 ptexplorer.zip
(13.97 KiB) Downloaded 115 times

 
^--- new one!
## Post #59
- Username: coroner
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Dec 06, 2009 9:12 am
- Post datetime: 2009-12-16T05:24:25+00:00
- Post Title: Re: smackdown vs raw 2010

I have an idea of what the DDS texture image consists of, but not nearly enough info on the exact settings when editing/replacing an actual DDS file from the game.

I'm using the NVIDIA plug-in for photoshop which has a multitude of options when saving DDS, instead of just auto saving any change it requires you to know the format settings,  is there a more appropriate tool for editing these textures?
## Post #60
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-16T06:43:29+00:00
- Post Title: Re: smackdown vs raw 2010

Oops, in my haste a forgot to include the bmp header....will upload tonight.

[EDIT] Ok, there's a new zip file, with bmp_header. Should work now.
## Post #61
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-16T08:42:21+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Okay here's a preview. At the moment just a simple .PT explorer.
ptexp.jpg
ptexp2.jpg

It just opens and saves .PT files. Not idiot-proof mind you and a pre-alpha version, will probably crash when corrupted files are attempted to be opened. 

I've been thinking, perhaps these are textures were originally DDS files, you know, the 8-bit, palette + 256 colours + alpha type with uncompressed bitmap. Would make sense in terms of xbox ?
ptexplorer.zip 
^--- new one!

At a guess I would say it's DDS as it does have a alpha channel in the game plus all other textures I have seen in the game are..
Also Great work again Mr.Mouse
## Post #62
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-16T17:29:56+00:00
- Post Title: Re: smackdown vs raw 2010

I keep getting the error "Invalid picture runtime error 481" when trying to open the paint file. 

The format of the model textures are dxt5 dds files with a custom alpha channel and mip maps. The alpha channel contains the same wrestler texture with sweat which appears as the match progesses.   

Its likely that the paint tool would have the same format minus the mip maps as its the native format of the game.
## Post #63
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-16T22:54:16+00:00
- Post Title: Re: smackdown vs raw 2010

Strange, did you copy all the files (2 of them into the same folder?)
## Post #64
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-17T06:14:04+00:00
- Post Title: Re: smackdown vs raw 2010

Managed to get it to work. I replaced my COMDLG32.OCX file with a newer version and put everything into the same folder. Tool is awesome
## Post #65
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-17T08:20:34+00:00
- Post Title: Re: smackdown vs raw 2010

any news on how the import export part of the tool is coming?
## Post #66
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-17T10:59:46+00:00
- Post Title: Re: smackdown vs raw 2010

Well, it can extract now. I think the textures are not DXT5 as they are uncompressed. BMP with alpha does seem likely. 

Here's the update:


 ptexplorer_0_1_2.7z
Use 7Zip (13.5 KiB) Downloaded 117 times
## Post #67
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-17T17:43:03+00:00
- Post Title: Re: smackdown vs raw 2010

Awesome!  I love how this is coming along.  If you need help testing anything just let me know.
## Post #68
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-17T22:39:35+00:00
- Post Title: Re: smackdown vs raw 2010

Okay, so test this. Backup your .pt file. Please export a slot as .bmp, then import it back into the same slot from that file. Now save the .pt file and try that one out in the game. Is that accurate in the game?


 ptexplorer_0_1_3.7z
(15.81 KiB) Downloaded 72 times
## Post #69
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-17T23:14:48+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Okay, so test this. Backup your .pt file. Please export a slot as .bmp, then import it back into the same slot from that file. Now save the .pt file and try that one out in the game. Is that accurate in the game?
ptexplorer_0_1_3.7z
I tried this.  It seemed to import fine, although the images were upside down in the preview window.  When I get it back into the game and go to the Paint tool, I get a message telling me that the Paint data is corrupted and cannot be used.

Can I make a suggestion, as long as you're in this working on it?  When you go to save the *.pt file (File/Save), the file dialog is asking you to save it as a *.bmp.  You might want to change that to a *.pt to prevent confusion.
## Post #70
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-17T23:33:05+00:00
- Post Title: Re: smackdown vs raw 2010

....
## Post #71
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-17T23:38:59+00:00
- Post Title: Re: smackdown vs raw 2010

Well I decided to rehash and resign the file for save measures after I tested and it seemed to have worked.  I exported and reimported the same file with success, and then opened it up in game and everything was good.  The only weird thing I had happen is in your preview in your program and in the preview in the game the logos I did this to ended up being all blue and white, but then when I opened them up in game they looked normal.... Kinda odd. I'll try importing a different file over one and see how that goes.
## Post #72
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-17T23:42:34+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Hmmm.  The "Export" feature seems to not work on the BMPs that I've imported.  I hit Export, I pick the destination folder, I type in the file name, I hit Save....the dialog box goes away but there's no file where I told it to put one.

Okay, so which files were you trying to import? Can you upload one of them?
## Post #73
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-17T23:44:31+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from JBP
>
> Well I decided to rehash and resign the file for save measures after I tested and it seemed to have worked.  I exported and reimported the same file with success, and then opened it up in game and everything was good.  The only weird thing I had happen is in your preview in your program and in the preview in the game the logos I did this to ended up being all blue and white, but then when I opened them up in game they looked normal.... Kinda odd. I'll try importing a different file over one and see how that goes.

This is VERY important. Can you explain EXACTLY what you did? Because at least you ended up with a file that worked in-game. Please include all procedures and programs you used.
## Post #74
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-17T23:45:53+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Okay, so which files were you trying to import? Can you upload one of them?
Sorry, just noticed I was doing something wrong on that point.  After I realized that, I tried Exporting an Imported one and it worked fine.  I edited out my post but you're too quick for me!
## Post #75
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-17T23:47:44+00:00
- Post Title: Re: smackdown vs raw 2010

lol
## Post #76
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-17T23:54:37+00:00
- Post Title: Re: smackdown vs raw 2010

Okay before I go into detail I'd like to say I didn't have success replacing one file with another.  I tried replacing a 128 one.  It was File 0 with which ever one the "outsiders" one is.

Anyways what I got to work the first time was I exported files 0 and 6 to bmp and reimported them as bmp files.  Like I said they worked fine but when in the previews looked blue for some reason.  After I reimported them I then saved the file as the default name of the file (00painttool.pt or something like that)  Next I used the rehash and resigner tool that comes with Modio.  Then I just put the file onto my harddrive using Xport 360.

Now I wanna try extracting a file and editing it, and then replacing the same file.  Maybe for some reason you couldn't replace one file with another but editing a file, and replacing it with the same one might work.
## Post #77
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-18T00:17:25+00:00
- Post Title: Re: smackdown vs raw 2010

Well no luck editing the same file and replacing it.  It did the upside down logo thing in the preview and then the game said it was corrupt.  Maybe it's because I just tried editing it in paint lol.
## Post #78
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-18T00:59:17+00:00
- Post Title: Re: smackdown vs raw 2010

After a little more experimentation, I can confirm JBP's experience.  

(1) If I Export the image, then Import that same image into that same slot, the game will recognize it as long as I rehash and resign the *.pt file.

(2) If I Import an image I've created over the top of an existing image, the game thinks the Paint Tool data has become damaged and will not load any of it.

I also get the "blue color" effect, FWIW
## Post #79
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-18T01:00:10+00:00
- Post Title: Re: smackdown vs raw 2010

Oh -- and I'm using Paint Shop Pro 9 to save out the new file as an 8-bit 256x256x256 BMP file.  Still no go.
## Post #80
- Username: ahon
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Dec 17, 2009 12:35 pm
- Post datetime: 2009-12-18T02:07:08+00:00
- Post Title: Re: smackdown vs raw 2010

how do i get it to work?
## Post #81
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T06:45:19+00:00
- Post Title: Re: smackdown vs raw 2010

OK, thanks. Editing a file and resaving it will chance the colour palette probably. Can you upload some edited BMPs that failed in the game ?
## Post #82
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-18T06:55:00+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Oh -- and I'm using Paint Shop Pro 9 to save out the new file as an 8-bit 256x256x256 BMP file.  Still no go.
I would seriously consider using Adobe Photoshop, because years ago there was some game we edited the textures and no matter what we did, Paint Shop Pro would not save the image format correctly.  We had people having problems and it took us forever to figure out all the people using PSP were the ones having problems.  JBP said he was only editing in Paint and Paint Shop Pro isn't much better than Paint.  

I'm not trying to ridicule you personally for using the program, because it is presented as a very good program, and most people think it is, but in reality it is shit.
## Post #83
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-18T07:01:13+00:00
- Post Title: Re: smackdown vs raw 2010

I have photoshop and will try in a few.  I just used paint to try it real quick because I only had a second to mess with it earlier.  I will post if I have better results.
## Post #84
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T07:23:07+00:00
- Post Title: Re: smackdown vs raw 2010

Okay, but don't forget to upload images that failed after importation. 

Another test, please use a .pt that works IN GAME. Now change the image in slot 0, but just slightly IN GAME. Now upload the new .pt file, together with the original. I will need to see what changed between the two. Because if the game uses some kind of checksum on the images, it may be stored somewhere and I need to find out.
## Post #85
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-18T08:19:58+00:00
- Post Title: Re: smackdown vs raw 2010

Ok I have the edited photo (scribble in photoshop) and the .pt file I injected it in, in one folder of the zip
and in the other I edited image 0 by just putting a black line right beneath the image.  I hope these help!
[PT.zip](https://xentaxbackup.github.io/file/2627_PT.zip)
## Post #86
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T08:43:37+00:00
- Post Title: Re: smackdown vs raw 2010

I'm soryy, but can you also do this with the in-game tool? That's what I meant. 
So load up .pt file (A) that works for you. Edit slot 0 in-game / with the game's tool and then take out the updated .pt file (B). I want to compate both A and B.
## Post #87
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-18T08:48:16+00:00
- Post Title: Re: smackdown vs raw 2010

Sorry I should have specified more clearly. The slight edit folder was done in game.
## Post #88
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-18T09:55:59+00:00
- Post Title: Re: smackdown vs raw 2010

The .pt file is a container file it has a savedata inside I beleave it is the same as the normal save games having its own checksum...
Thats why it says curupt save...

See the File I uploaded in my first post...
## Post #89
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T10:02:37+00:00
- Post Title: Re: smackdown vs raw 2010

I think so too. Do we know the checksum location already? JBP, can you re-edit the lsightly changed slot 0 in game back to how it was? We should have 3 pt files: Before, After slight edit, Restored Edit to original state.
## Post #90
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-18T10:31:45+00:00
- Post Title: Re: smackdown vs raw 2010

No sorry, maybe brienj may have a clue? hes edited the save game and has it working in game..
## Post #91
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-18T10:39:52+00:00
- Post Title: Re: smackdown vs raw 2010

Here is the file with the picture edited back to its original state.
[After.zip](https://xentaxbackup.github.io/file/2628_After.zip)
## Post #92
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-18T15:21:48+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from brienj
>
> FatalArms wrote:Oh -- and I'm using Paint Shop Pro 9 to save out the new file as an 8-bit 256x256x256 BMP file.  Still no go.
I would seriously consider using Adobe Photoshop
To be fair, PSP has improved a lot over the years.  I never run into anything it can't do when I need graphics.  (I mean, I'm sure there are things it can't do, but for my personal needs it always does the trick.)

But if Photoshop is the only way to get this process to work, then Photoshop I'll use
## Post #93
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T16:05:32+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from JBP
>
> Here is the file with the picture edited back to its original state.

Thanks. Say, in the game, do you have to save the pictures each time you want to edit them? What if you use file A, open the game's editor, don't do anything but save? Would that still alter the file, I wonder.
## Post #94
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T19:19:31+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from JBP
>
> Here is the file with the picture edited back to its original state.

Oh and by the way, the picture was not back to its original state. The bitmap was, but not the palette. Did you change a colour? There seems to be one or two colours different.
## Post #95
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-18T20:02:09+00:00
- Post Title: Re: smackdown vs raw 2010

Odd.... I didn't change any colors. All I did was delete the black line I had placed on there, and then resaved it. It looks identical to the original on my game. As for the  opening and then saving without doing anything I can try that later tonight, but it'll probably be about 10 hours from now.
## Post #96
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-18T20:41:01+00:00
- Post Title: Re: smackdown vs raw 2010

Mouse, these might be of some use to you:

[http://www.stormclad.com/PaintToolTesting.zip](http://www.stormclad.com/PaintToolTesting.zip)

It contains three paint files.

1.  My working in-game Paint file
2.  Same file - I opened up the first image in the game, made NO changes, saved it
3.  Same file - I opened up the first image in the game, made a small change, saved it
## Post #97
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-18T23:00:39+00:00
- Post Title: Re: smackdown vs raw 2010

Thanks! Now I see that even saving without editing alters the file, including the palette! Again the same colour that changes. Until we find out where in the file the checksum is, we're lost. We need to know the structure of the file.
## Post #98
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-19T03:42:09+00:00
- Post Title: Re: smackdown vs raw 2010

well ive used the tool with success so far. all you have to do is go to the paint tool in game select each image and save again to correct the color in pallette in game. only thing is that since black is the transparent color in the in game pallette you need to change the black slightly in PS so it doesnt appear as a transpararent in game. I.E. in my case my design was black outline with red design I just changed the black to a dark as hell shade of red and presto no problems
## Post #99
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T04:40:09+00:00
- Post Title: Re: smackdown vs raw 2010

Snyperstyle, can you elaborate?  Are you saying you save the image in-game first to correct the palette, then you can overwrite it on the pc with an image you made in PhotoShop?  If so, can you post the exact sequence of events?  

Here's what I did, and had no success with:

1. Open an image in-game in the Paint tool.
2. Make no changes
3. Save it
4. Transfer it to PC and extract it using PTExplorer
5. Open the bmp in PSP, change the image there, save it as a bmp of the same size & color depth.  Reimport it into the .pt file.
6. Transfer it to the XBox, overwriting the old Paint Tool .pt file
7. Go to the Paint Tool in-game

At that point, I get an error saying that the file is damaged.  I can't do anything with it in-game other than overwrite it.
## Post #100
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-19T05:13:59+00:00
- Post Title: Re: smackdown vs raw 2010

when u ovewrite the logos will be there make sure u use modio to rehash and resign the .pt file before putting it back on ur 360 hdd as well. everything else ur doing  is perfect
## Post #101
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T05:49:36+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from snyperstyle
>
> when u ovewrite the logos will be there make sure u use modio to rehash and resign the .pt file before putting it back on ur 360 hdd as well. everything else ur doing  is perfect
Right, I forgot to say that heh.  Tried it again, making sure I rehashed and resigned with Modio.  Still didn't work.

I even tried editing with PhotoShop instead of Paint Shop Pro this time.  Still no go.
## Post #102
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-19T07:39:27+00:00
- Post Title: Re: smackdown vs raw 2010

Awesome! It did work just like you said.  When the game ask you if you would like to create a new paint tool file do that and it works great!  All the logos are still there.  WARNING THOUGH! Don't create your logo on slot 0 because the game will overwrite it with the default Dolph Ziggler logo. Now I'm gonna try to put in an nWo and TNA logo over something and see how that goes.  Have you tried doing this, with more than one image at a time?
## Post #103
- Username: Diesl
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-19T08:12:03+00:00
- Post Title: Re: smackdown vs raw 2010

An excellent work-around that will enable you fans to use PTExplorer at least !

So here's the sequence of events that will work, please correct me if there's a mistake:

1. Transfer your .PT  (Paint Tool) file to PC and extract images using PTExplorer as (*.bmp)
2. Open the bmps in PSP or Photoshop and edit them 
Remember that since black is the transparent color in the in-game pallette you need to change the black slightly in PS so it doesnt appear as a transparent in game.
3. Save the bmps of the same size & color depth. 
4. Reimport the bmps into the .pt file to slots of your choice with PTExplorer, but don't use slot 0.
5. Save the *.PT file from PTExplorer
6. Use modio to rehash and resign the .pt file
7. Transfer it to the XBox, overwriting the old Paint Tool .pt file
8. Go to the Paint Tool in-game: the game will detect a corrupted file and when asked to overwrite the file, do it! The game will correct the file, make slot 0 the default logo, but keep the other logo's intact. 
[ptexplorer_0_1_3.7z](https://xentaxbackup.github.io/file/2630_ptexplorer_0_1_3.7z)
## Post #104
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-19T08:45:29+00:00
- Post Title: Re: smackdown vs raw 2010

sounds good to me Mr. Mouse thanks alot this has already made the game way more fun
## Post #105
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-19T09:01:30+00:00
- Post Title: Re: smackdown vs raw 2010

Sounds awesome!  I would add at the very start that they need to open up paint tool in game and then save the file without making ANY adjustments.

And yes I did it with 3 images at once so you can do multiple images at one time.
## Post #106
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-19T10:04:01+00:00
- Post Title: Re: smackdown vs raw 2010

Excellent that multiple images also work, I would have thought so.  

Yet, I don't think that it is necessary to go into Paint Tool first and save the file without making any adjustments. If you're a first time user, you will have saved it at some point already. Unless there is a specific time frame for it to work (save and then immediately alter the .pt file), but I don't assume that is the case here.
## Post #107
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-19T10:15:25+00:00
- Post Title: Re: smackdown vs raw 2010

Well I am very pleased with your work and myself and many many others will get a lot of use out of this.  I did have one more glitch.... Anytime I try to replace image 10 then it corrupts the file.  Not sure why but I tried it with several different images and they all crashed it. Im going to try changing image 10 in the game and maybe that'll fix it or something.
## Post #108
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-19T10:18:12+00:00
- Post Title: Re: smackdown vs raw 2010

Ah! Thanks for that bug report. I know what the problem is, I forgot about something.

[EDIT] I also think the thing with the colours changed after importation in PT Explorer needs some attention. 

Anyone got screenshots of the new logo you imported into the game this way ?
## Post #109
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-19T10:32:48+00:00
- Post Title: Re: smackdown vs raw 2010

Well once you save it in game the color goes back to normal so its not a big deal.  First preview is kinda scary though lol
## Post #110
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T15:42:40+00:00
- Post Title: Re: smackdown vs raw 2010

Aha!  The only one I was trying to replace was image 0.  If it works on the others, that's awesome.  

Thanks so much, guys!
## Post #111
- Username: BxNight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 18, 2009 11:52 am
- Post datetime: 2009-12-19T17:56:29+00:00
- Post Title: Re: smackdown vs raw 2010

This tool is amazing i was able to fix up my Desmond Wolfe logo b/c of this tool so thanks alot
## Post #112
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T18:17:55+00:00
- Post Title: Re: smackdown vs raw 2010

Just tried it with success to get one of Brock's DeathClutch t-shirts made for him.  Niiiiiiiice!
## Post #113
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-19T19:16:30+00:00
- Post Title: Re: smackdown vs raw 2010

Wow, don't forget to post screenshots of your edits if you can. I'd love to see some.
## Post #114
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-19T19:21:51+00:00
- Post Title: Re: smackdown vs raw 2010

Its not working for me.....

I do as it says and when svr2010 fixs the save all the pics are gone???
## Post #115
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T20:25:49+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Wow, don't forget to post screenshots of your edits if you can. I'd love to see some.
Here's my Brock ( [http://www.youtube.com/watch?v=1j8J29zSulw](http://www.youtube.com/watch?v=1j8J29zSulw) ).  Notice his DeathClutch t-shirt and all of the sponsor logos on his trunks.

Now if only I can con someone into making his tats in PhotoShop....
## Post #116
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-19T20:34:10+00:00
- Post Title: Re: smackdown vs raw 2010

fatal i have his wrestle kingdom textures if you want them they have all of his tats. Add me on aim or msn and ill send them to you. AIM- Donchihm3 MSN- [Snyperstyle@yahoo.com](mailto:Snyperstyle@yahoo.com)
## Post #117
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T20:45:10+00:00
- Post Title: Re: smackdown vs raw 2010

Awesome!  I just added on you MSN/Windows Live Messenger
## Post #118
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-19T21:55:59+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Mr.Mouse wrote:Wow, don't forget to post screenshots of your edits if you can. I'd love to see some. 
Here's my Brock ( http://www.youtube.com/watch?v=1j8J29zSulw ).  Notice his DeathClutch t-shirt and all of the sponsor logos on his trunks.

Now if only I can con someone into making his tats in PhotoShop....

Nice man! But where's PTExplorer in your description
## Post #119
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-19T22:21:26+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> 
Nice man! But where's PTExplorer in your description
Oh, right!    

It's in there now.
## Post #120
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-19T22:57:15+00:00
- Post Title: Re: smackdown vs raw 2010

accepted ur add on msn lemme know when you want the textures. I have all of his tats
## Post #121
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-19T23:58:55+00:00
- Post Title: Re: smackdown vs raw 2010

Latest update:

- added readme.txt
- fixed a colour bug when loading from BMP. May even help corruption problem in-game. 
- fixed bug with slot 10 and importing
- added View Alpha to show the intensity of each colour in the image in-game
- added tool-tip text when hovering over a button
- fixed dialogs 



Please confirm that this new version still does the trick!  


 ptexplorer_0_1_4.7z
Use 7Zip (19.23 KiB) Downloaded 96 times



[EDIT] Still a bug with slot 10. Will fix soon.
## Post #122
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-20T00:29:30+00:00
- Post Title: Re: smackdown vs raw 2010

Is this Brock texture detailed enough for you to use it?



Edit: 16MB 2048 x 2048 x 32bpp bmp file was taken off server, message me if you didn't get it.
## Post #123
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-20T00:40:49+00:00
- Post Title: Re: smackdown vs raw 2010

I may have found a bug.  I put in some new images - the first couple were 128x128.  The last couple were 256x256.  When I went to use them in the game, the first ones had been changed to 256x256, so the images were doubled-up inside there.

Now, maybe that was ME doing something stupid so I don't want to call it a bug just yet until I replicate it.  I just might not get a chance to post again for a couple hours so I wanted to let you know while I'm still on.
## Post #124
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-20T00:50:47+00:00
- Post Title: Re: smackdown vs raw 2010

Argh.  Just tried it again.  Seems like whenever I try to put an image in slot 10, the game thinks the entire file is corrupted and wipes out everything in the Paint tool.  (And yes, I'm using the newest version)
## Post #125
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-20T05:38:52+00:00
- Post Title: Re: smackdown vs raw 2010

OK, I've had some more time to mess with it.  I've stopped bothering with slot 10 for now, and have had no cases of the game wiping out the whole save file since I stopped using slot 10.  

That "resetting small images to be doubled-up big ones" has happened a couple more times.  I started making sure I use PTExplorer to manually set it to the smaller size even if it looks like it already is the smaller one.  Since I started doing that, this has yet to happen again.

One unexpected thing I've noticed - the threshold for transparency seems to be wider than just (0,0,0).  I've had a couple images where I used the color black set to about (3,5,6) and the game still recognized those as transparent.  I ended up making those parts lime green in PSP/PhotoShop, then changing them to black with the in-game paint tool.  Not a big deal, but a little wonky.

All in all, this is a wonderful little program.  I don't know why I'm so amused at having the actual "Full Tilt Poker" logo on Kimbo Slice's shorts, but there you are.  I also found a perfect "praying hands" graphic for Mark Briscoe's tattoo.

Speaking of tattoos:  I made a lot of headway on Brock's back tattoo today.  I have a decent looking in-game version of it now, but I'm going to improve on that when I can.  

We now return you to your regularly-scheduled Paint Tool talk.
## Post #126
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-20T08:56:46+00:00
- Post Title: Re: smackdown vs raw 2010

Thanks for the reports, FatalArms!

Actually, the slot 10 problem I warned about in my post above 

The resolution bit interest me, especially the notion that you have to manually set it in PT Explorer, even though it may show correct in the preview window. I will look into that. Are you using 0.1.4 version of PT Explorer, because I did work on that. 

The other thing is with the colour black. The game uses colour 15 (0x0f) in the colour table as black. I think it may even expect that, I don't know. In any event, by just changing to colour to none-black you won't succeed in making it non-transparent. There is a fourth value, the alpha, that is set to 0, and I wonder whether Photoshop or so edits this value or leaves it alone.
## Post #127
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-20T09:11:03+00:00
- Post Title: Re: smackdown vs raw 2010

I can confirm that editing with Photoshop changes transparency from FF to 00 for each colour, as the BMP format is not really equipped for a alpha value as fourth variable in the palette table. Thae game uses BGRA, while BMP uses BGR and then a dummy variable, which PS sets to 0. What I can do is build in an option to save the alpha map separately, and let you import it once you got the raw image data back in.
## Post #128
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-20T14:48:35+00:00
- Post Title: Re: smackdown vs raw 2010

On the other hand, these might simply be .TGA files, with an alpha channel in a 32-bit palette. I will change the program to save .TGA files as well.
## Post #129
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-20T21:08:03+00:00
- Post Title: Re: smackdown vs raw 2010

I still cant get this tool to work I do as directed but when it says the file is currupt or damage it delets all the images
## Post #130
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-21T08:27:19+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> I can confirm that editing with Photoshop changes transparency from FF to 00 for each colour, as the BMP format is not really equipped for a alpha value as fourth variable in the palette table. Thae game uses BGRA, while BMP uses BGR and then a dummy variable, which PS sets to 0. What I can do is build in an option to save the alpha map separately, and let you import it once you got the raw image data back in.
You need to maybe update your plugins or version of Photoshop.  

Also, I deleted the Brock BMP off my webspace, it was taking up lot of space, if somebody didn't get it and still needs it, message me.
## Post #131
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-21T09:21:10+00:00
- Post Title: Re: smackdown vs raw 2010

Well, which plugin do you use brienj?
## Post #132
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-21T16:01:02+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Well, which plugin do you use brienj?
I'm away from home on my laptop, don't know the exact one, but I know there are many extended options for saving BMP files on  my version of Photoshop, not sure if it's the extra plugins I have, or the version I have.  I'll send you the package of plugins I have, next time I go home, there are around 100+ plugins I have from what I remember.  

I know that I can save BMP format with a bunch of different variations of ARGB and XRGB.
## Post #133
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-21T16:13:26+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from brienj
>
> Mr.Mouse wrote:Well, which plugin do you use brienj?
I'm away from home on my laptop, don't know the exact one, but I know there are many extended options for saving BMP files on  my version of Photoshop, not sure if it's the extra plugins I have, or the version I have.  I'll send you the package of plugins I have, next time I go home, there are around 100+ plugins I have from what I remember.  

I know that I can save BMP format with a bunch of different variations of ARGB and XRGB.

Cool! Will the alpha channel then also show? Because that is really screwed in the latest version of Photoshop (take the dreaded support for .TGA (=alpha) for instance).
## Post #134
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-21T20:39:07+00:00
- Post Title: Re: smackdown vs raw 2010

Okay, so maybe I got this all wrong. The number of colours in one picture is obviously limited to 256, judging from the palette. But the RGB values of the palette can be anything, right? The game does not care about that? Or will each slot have the same palette you create?
## Post #135
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T02:51:14+00:00
- Post Title: Re: smackdown vs raw 2010

Some more pics of stuff made with this tool.  A few of these are blurry.  They look pretty decent in-game.

["Will Fight For Money" shirt w/logo](http://www.stormclad.com/PaintTool/pt01.jpg)
[shirt w/ "Dirty Boxer" logo](http://www.stormclad.com/PaintTool/pt02.jpg)
[Trunks w/ sponsor logos](http://www.stormclad.com/PaintTool/pt03.jpg)
[Kimbo wearing an ornate Kimbo shirt!](http://www.stormclad.com/PaintTool/pt04.jpg)
[Brock shirt, logos](http://www.stormclad.com/PaintTool/pt05.jpg)
[Trunks w/logos](http://www.stormclad.com/PaintTool/pt06.jpg) (er, didn't mean for it to be so crotchtastic a shot)
[Brock's back tattoo](http://www.stormclad.com/PaintTool/pt07.jpg)
[Brock's skull tattoo](http://www.stormclad.com/PaintTool/pt09.jpg)
## Post #136
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T08:12:26+00:00
- Post Title: Re: smackdown vs raw 2010

Nice, just thought to show them here. Anyway, I still need some answers to my questions.  



pt01.jpg (30.7 KiB) Viewed 576 times





pt02.jpg (39.29 KiB) Viewed 575 times





pt05.jpg (28.95 KiB) Viewed 575 times





pt07.jpg (29.97 KiB) Viewed 574 times
## Post #137
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-22T09:49:11+00:00
- Post Title: Re: smackdown vs raw 2010

fatal those are sick!!! hope you have characters on live for download
## Post #138
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T14:08:43+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Okay, so maybe I got this all wrong. The number of colours in one picture is obviously limited to 256, judging from the palette. But the RGB values of the palette can be anything, right? The game does not care about that? Or will each slot have the same palette you create?
Honestly I'm not sure.  (I'm good enough with graphics to fumble my way around, but it's not my area of expertise.)  I'm going to share something with you that seems like evidence that the game expects the same 256 colors every time, though.

I imported Brock's sword tattoo, flesh and all, into the game.  To do this I used one of the exported bmp files, set it to 16 million colors, pasted the tat over that one, then decreased it back to 256 colors.  It still looked pretty good in PSP, since PSP picked which 256 colors to keep.  So far so good, right?

When I got it into the game, it looked like a dog had vomited up pixelated Atari colors all over the place.  The sword was more or less discernible, but it was nowhere near good enough to use.

FWIW, I'm using PTExplorer 0.1.4.
## Post #139
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T14:10:31+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from snyperstyle
>
> fatal those are sick!!! hope you have characters on live for download
Unfortunately I no longer have Live.  What can I do to help you out?  If I posted bitmaps or save files, could you use them?
## Post #140
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T14:25:44+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Mr.Mouse wrote:Okay, so maybe I got this all wrong. The number of colours in one picture is obviously limited to 256, judging from the palette. But the RGB values of the palette can be anything, right? The game does not care about that? Or will each slot have the same palette you create?
Honestly I'm not sure.  (I'm good enough with graphics to fumble my way around, but it's not my area of expertise.)  I'm going to share something with you that seems like evidence that the game expects the same 256 colors every time, though.

I imported Brock's sword tattoo, flesh and all, into the game.  To do this I used one of the exported bmp files, set it to 16 million colors, pasted the tat over that one, then decreased it back to 256 colors.  It still looked pretty good in PSP, since PSP picked which 256 colors to keep.  So far so good, right?

When I got it into the game, it looked like a dog had vomited up pixelated Atari colors all over the place.  The sword was more or less discernible, but it was nowhere near good enough to use.

FWIW, I'm using PTExplorer 0.1.4.

Definitely helpful. Can you upload the one that got screwed up in the game? Did it look ok to you in PTExplorer?
## Post #141
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T14:28:52+00:00
- Post Title: Re: smackdown vs raw 2010

It looks fine in PTExplorer.

Here it is, exported back out of PTExplorer.
[BrockSword.zip](https://xentaxbackup.github.io/file/2645_BrockSword.zip)
## Post #142
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T14:35:56+00:00
- Post Title: Re: smackdown vs raw 2010

Here's what that looks like in-game:
## Post #143
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T14:43:06+00:00
- Post Title: Re: smackdown vs raw 2010

This one was exported from my game save just now.  It has been changed in-game and saved.  Still looks fine in PTExplorer, but looks horrid in the game.
[BrockSword-after-saving-in-game.zip](https://xentaxbackup.github.io/file/2646_BrockSword-after-saving-in-game.zip)
## Post #144
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T15:11:17+00:00
- Post Title: Re: smackdown vs raw 2010

Indeed. I took the palette from one of the other textures from a .pt file and replaced the one in the BrockSword of yours. 
Here's what I got (look familiar?) 



BrockSword_pal.png (30.19 KiB) Viewed 531 times



So it seems the game does not care about the palette (it has a standard one). Does the game first nag that there's something corrupted? And that it will resave the file? I may be that it resets the palette as well at that time. 

Can you actively change the palette in the PaintTool? I notice a palette on screen, can you change any of them colours? It says "NORMAL PALETTE", are there others?

Here's your sword back, I think that one will show okay in PaintTool. I opened a picture with the correct palette then copied your image onto that image (Photoshop then looks for the most closest colour before copying).


 BrockSword_stdpal.7z
(11.53 KiB) Downloaded 30 times
## Post #145
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T15:25:18+00:00
- Post Title: Re: smackdown vs raw 2010

Wow, that's much better.  Although it is...blinking 

Yes, it does say it's corrupted and asks you to save.

Here's a vid I created to show you what it looks like now.  This also shows you what happens when you cycle through the various palettes in Paint Tool.

[zipped video file here](http://www.stormclad.com/SwordBackIn.zip)
## Post #146
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T15:48:02+00:00
- Post Title: Re: smackdown vs raw 2010

Haha awesome. I don't have an XBox and not even the game, so I have no way of testing stuff in game. That sort of video is great ! 
So, all in all, you have the option to cycle through a number of palettes, but once chosen one, you are stuck with it for that image, that slot right? 

Can you save images in each of the possible palettes (say slot 0 to whatever the number of palettes is?).

As for the blinking colours, can you tell which colour that must be? Is that an option in the game tool? Do the colours blink when on a character as well?
## Post #147
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-22T16:05:30+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Haha awesome. I don't have an XBox and not even the game, so I have no way of testing stuff in game. That sort of video is great !
You rock for helping us all out even though you don't have the game  

> So, all in all, you have the option to cycle through a number of palettes, but once chosen one, you are stuck with it for that image, that slot right?
Kinda.  You can switch back to the normal palette if you want to, it'll just change the look of the image.  If you want to, you can copy the image to a different slot and change the palette in that new slot so you can have multiple versions of the image with multiple palettes.

> Can you save images in each of the possible palettes (say slot 0 to whatever the number of palettes is?).
Yep, by the method I just spoke of.

> As for the blinking colours, can you tell which colour that must be? Is that an option in the game tool? Do the colours blink when on a character as well?
No, not while on the character.  My box is off at the moment, but I'll get back to you on that color.  I've seen it happen before, but only with PTExplorer images.  It's a shade of white that seems to cause this.  If you use the Paint Tool bucket tool to fill it in with white, it stops blinking and becomes pure white.  It never blinks on the wrestler.  I think it might show up as transparent on the wrestler, but today I've been viewing it through my Gamebridge and the picture quality is not the highest so take that with a grain of salt.
## Post #148
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T21:05:52+00:00
- Post Title: Re: smackdown vs raw 2010

Okay, but can anyone use up he slots and each a different palette from the PaintTool and then upload the .pt file?
## Post #149
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T23:09:53+00:00
- Post Title: Re: smackdown vs raw 2010

Here's what I'm trying to do:



progress.png (23.34 KiB) Viewed 492 times
## Post #150
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-23T01:57:26+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Mr.Mouse wrote:Okay, so maybe I got this all wrong. The number of colours in one picture is obviously limited to 256, judging from the palette. But the RGB values of the palette can be anything, right? The game does not care about that? Or will each slot have the same palette you create?
Honestly I'm not sure.  (I'm good enough with graphics to fumble my way around, but it's not my area of expertise.)  I'm going to share something with you that seems like evidence that the game expects the same 256 colors every time, though.

I imported Brock's sword tattoo, flesh and all, into the game.  To do this I used one of the exported bmp files, set it to 16 million colors, pasted the tat over that one, then decreased it back to 256 colors.  It still looked pretty good in PSP, since PSP picked which 256 colors to keep.  So far so good, right?

When I got it into the game, it looked like a dog had vomited up pixelated Atari colors all over the place.  The sword was more or less discernible, but it was nowhere near good enough to use.

FWIW, I'm using PTExplorer 0.1.4.
This is exactly why we need to work on a model exporter, this is the only way to get a really nice looking new character.  The limitations in CAWs are pretty bad.  CAWs don't even sweat or bleed like normal characters, they just look out of place.
## Post #151
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-23T02:27:47+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> Okay, but can anyone use up he slots and each a different palette from the PaintTool and then upload the .pt file?
OK, here you go 

Slot 02 = Normal Palette
Slot 03 = Monochromatic
Slot 04 = Cool Colors
Slot 05 = Warm Colors
Slot 06 = Pastels
Slot 07 = Forest Colors

Those are all of the different palettes in the game.  File is attached.
[00PaintTool.zip](https://xentaxbackup.github.io/file/2652_00PaintTool.zip)
## Post #152
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-23T02:30:21+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from brienj
>
> This is exactly why we need to work on a model exporter, this is the only way to get a really nice looking new character.
I expect this on my desk tomorrow morning
## Post #153
- Username: snyperstyle
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-23T14:36:43+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> 
Those are all of the different palettes in the game.  File is attached.

Do you start counting from 0 or 1? I see more palettes in the file:

slot 0 - Normal  
slot 1 - Normal
slot 2 - Greyscale
slot 3 - Cool colors
slot 4 - Warm colors
slot 5 - Warm colors (but slight difference in one color!)
slot 6 - Pastels
slot 7 - Forest colors



painttoolpalettes.png (16 KiB) Viewed 1240 times



As you can clearly see, the palettes are arranged in lines of 16 x 16. And each 16th colour is a special one, and has transparency.
## Post #154
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-23T14:45:09+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> FatalArms wrote:
Do you start counting from 0 or 1? I see more palettes in the file:
From 1.  Sorry, should've started at 0 I guess 

There are others in there too, just because I have more images.  Here's a screenshot of my paint tool data just to clarify.
## Post #155
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-12-23T21:45:48+00:00
- Post Title: Re: smackdown vs raw 2010

wow just wanna thank you again mouse for all the hard work ive been away from my xbox for a few days and havent been able to try out the newest version but it looks awesome, Cant wait for the next release
## Post #156
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-23T23:22:08+00:00
- Post Title: Re: smackdown vs raw 2010

Then try this one, it should fix the slot 10 import issue as well.  



ptexp.png (71.51 KiB) Viewed 1287 times




 ptexplorer_0_1_5.7z
(60 KiB) Downloaded 231 times
## Post #157
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-24T07:56:17+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from DRAVEN
>
> I still cant get this tool to work I do as directed but when it says the file is currupt or damage it delets all the images

Havent tried the tool as yet, but are you using the pal version? Modio says that it's only been tested on the ntsc version.
## Post #158
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-24T10:29:11+00:00
- Post Title: Re: smackdown vs raw 2010

I have used it on the PAL version it does work but I have only been able to get it to work using the pt file that JB uploaded, when ever I use my own pt file it deletes all the images off it...
## Post #159
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-24T11:55:19+00:00
- Post Title: Re: smackdown vs raw 2010

I keep getting accessing error? the it deletes all textures
## Post #160
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-24T12:31:36+00:00
- Post Title: Re: smackdown vs raw 2010

Please upload the one that fails.
## Post #161
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-24T13:10:52+00:00
- Post Title: Re: smackdown vs raw 2010

here it is...

The only file I have had working is a edited on that JB uploaded all others fail including my original pt file..
[00PaintTool.7z](https://xentaxbackup.github.io/file/2657_00PaintTool.7z)
## Post #162
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-24T13:47:20+00:00
- Post Title: Re: smackdown vs raw 2010

Well, I can open that file no problem with PT Explorer. Can someone try it in their game and confirm it fails of works?

Also, can you upload the one that results after it creates a new one for you (the one with the missing images?).
## Post #163
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-12-24T18:04:14+00:00
- Post Title: Re: smackdown vs raw 2010

will do once I get home 
thanks Mr.Mouse

Merry christmas hope you have a good one
## Post #164
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-24T18:40:22+00:00
- Post Title: Re: smackdown vs raw 2010

Yes, merry christmas to you all as well.   

Oh and please also upload two images you wanted to use. They are upside down in the file, I want to try and import them using PT Explorer myself, and perhaps the others can also try and see if it works for them.
## Post #165
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-25T23:27:04+00:00
- Post Title: Re: smackdown vs raw 2010

Here you go with version 0.1.6:

```

- Perfected Alpha (transparency) view option
- perfected interface
- enabled editing of colours in palette
```




screen_0_1_6.png (57.2 KiB) Viewed 1157 times




 ptexplorer_0_1_6.7z
(42.86 KiB) Downloaded 1415 times
## Post #166
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2009-12-25T23:34:26+00:00
- Post Title: Re: smackdown vs raw 2010

Nice!

I'm busy with in-laws overrunning my house all weekend.  No time for play
## Post #167
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-25T23:41:59+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Nice!

I'm busy with in-laws overrunning my house all weekend.  No time for play

Lol! They're your family, dude. Don't tell my you don't play with your family...
## Post #168
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-28T10:45:20+00:00
- Post Title: Re: smackdown vs raw 2010

I think the colours for transparency are very specific each 16th colour in the palette. Also, you must save bitmaps with reverse order than standard (because standard bmps save the data upside down), and most programs have this option before you save. 

It could be that when you save a bmp using photoshop and all the transparency values are 0 (as in my case, I have yet to find a plugin that can retain the 4th byte in my palette!!! brienj?), the game detects an error.
## Post #169
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-31T06:58:44+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> I think the colours for transparency are very specific each 16th colour in the palette. Also, you must save bitmaps with reverse order than standard (because standard bmps save the data upside down), and most programs have this option before you save. 

It could be that when you save a bmp using photoshop and all the transparency values are 0 (as in my case, I have yet to find a plugin that can retain the 4th byte in my palette!!! brienj?), the game detects an error.
I don't know if this will work for sure, but it has a lot of advanced options for BMP files.  Sorry about last time I came home, I forgot about you.
[BMP.rar](https://xentaxbackup.github.io/file/2684_BMP.rar)
## Post #170
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-31T08:37:08+00:00
- Post Title: Re: smackdown vs raw 2010

Thanks, but the problem is the same. If you want to save as an 8-bit. indexed BMP (what we need) then the palette is 32-bit per colour, but the last byte is always 0 and not the actual alpha value of that colour. In the game the palette format is B G R A , but if you want to have alpha channels in Photoshop (and BMP) you can't have a palette and each pixel has his own alpha.
## Post #171
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-01-06T08:10:15+00:00
- Post Title: Re: smackdown vs raw 2010

First off, Mr Mouse, thanks for the ptexplorer tool. It is freaking amazing!!!   

I've been able to import textures into the game and apply to created wrestlers with no issues. 

The only problem is that that when you try to edit the texture with the in game paint tool, the pallette gets messed up. However applying the texture ingame shows no graphical errors. 

I am using paint.net to create bmp files. It loses the tranparency though. To overcome this, I selct the colour in ptexplorer and manually set the alpha to 0. 

Once again thank you for your hard work in creating this amazing tool. 

Paint tool:



nwo Version:



Red and yellow version:



in game:
## Post #172
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-06T11:07:31+00:00
- Post Title: Re: smackdown vs raw 2010

Excellent!  Thanks a bundle for your post, man! I'll update the program some more soon. It can now also save and load palettes, that should help.

[EDIT] After re-reading your post, it would seem that you don't need to use the build in palettes in painttool, right?  You can create any picture with any palette, edit the alpha in PTExplorer and it works perfectly in-game?
## Post #173
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-01-06T12:26:48+00:00
- Post Title: Re: smackdown vs raw 2010

I havent tried editing the textures with the ingame paint tool at all and edit it on the pc instead. 

I didnt give any consideration to which palette was being used, only thing I did was to save the file as bmp8 in paint.net and set tranparencies in ptexplorer. 

As I said though the image looks messed up if you try to edit it in using the in game paint tool, but appears fine in the tumbnail previews and when used in game.
## Post #174
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-06T13:03:50+00:00
- Post Title: Re: smackdown vs raw 2010

That is great news then!  That gives you guys much more freedom to create whatever you wish, and you are not bound to any specific in-game palette.
## Post #175
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-06T14:48:34+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from plodtrew
>
> only thing I did was to save the file as bmp8 in paint.net and set tranparencies in ptexplorer.
Hmmm.  I'm trying this, but I get "Slot 4 not loaded with new file" in PTExplorer.
## Post #176
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-06T14:57:51+00:00
- Post Title: Re: smackdown vs raw 2010

The accepted image resolution is 128x128 or 256x256.
## Post #177
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-06T15:17:18+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> The accepted image resolution is 128x128 or 256x256.
Aha!  I did have that wrong on the image I was trying to bring in.  Figures.  Works now 

I really like this bit of info, plodtrew!  I find it makes it simpler to get tattoos to look right too.  I sometimes had trouble with getting them to come out dark enough after putting them through the in-game paint tool.  If you just bypass the in-game paint tool entirely, it's simple.
## Post #178
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-07T05:01:53+00:00
- Post Title: Re: smackdown vs raw 2010

Plodtrew, I've noticed that the face morphing still matters quite a bit in importing the faces over a CAW.  Did you spend a long time "perfecting" Hogan before applying the paint tool logo to his face?  If not, do you have any tips in making the paint tool logos more realistic than mine?

For example's sake, here's a vid of me playing around with a David Bowie paint tool face.  I haven't done any morphing at all on the default face(s), so the guy doesn't look a thing like Bowie even though the logo on its own does.

[http://www.stormclad.com/bowie.avi](http://www.stormclad.com/bowie.avi)
## Post #179
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-01-07T07:14:03+00:00
- Post Title: Re: smackdown vs raw 2010

@fatalarms, You have to get a solid morphing first before you can apply the texture.
## Post #180
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-07T19:54:37+00:00
- Post Title: Re: smackdown vs raw 2010

I took the time to do a video tutorial on this today.

[http://www.youtube.com/watch?v=DvMMlfinY7k](http://www.youtube.com/watch?v=DvMMlfinY7k)
## Post #181
- Username: Zurick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 25, 2008 10:37 pm
- Post datetime: 2010-01-07T20:41:51+00:00
- Post Title: Re: smackdown vs raw 2010

I obviously don't post much, but I been here for a while. Last time I was active though, it was figured how to pull the models from HCTP and put them on stuff like Poser, were the textures from that ever found?
## Post #182
- Username: Bunky
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Dec 23, 2009 10:06 am
- Post datetime: 2010-01-07T21:27:42+00:00
- Post Title: Re: smackdown vs raw 2010

Nice video FatalArms!!
## Post #183
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-01-08T07:26:54+00:00
- Post Title: Re: smackdown vs raw 2010

@zurick, good to see you on these forums as well. The hctp textures are extractable using rrunpack to unpack the pac files and then using rtxexplorer to extract the textures. Both apps are on this forum, you just have to look for it.
## Post #184
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-08T18:38:11+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> I took the time to do a video tutorial on this today.

http://www.youtube.com/watch?v=DvMMlfinY7k

Brilliant job! Sorry for my slow routine to preview the Alpha (   ). Great tutorial.
## Post #185
- Username: Owen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2010 10:57 pm
- Post datetime: 2010-01-08T19:25:38+00:00
- Post Title: Re: smackdown vs raw 2010

Mr.Mouse, thanks for the tool.  After following FatalArms video tutorial, I noticed that when I tried using a Cactus Jack shirt logo that the image got mirrored in PTExplorer v0.1.6 so the text stayed mirrored in the game as well.  I may have missed the mention of this happening before but I just wanted to pass it along just in case.  

Also for anyone running Windows 7 64 Bit, you will get an error that the Comdlg32.ocx is missing when trying to start PTExplorer.  I was able to figure out how to fix it using this topic

[http://www.vistax64.com/vista-general/1 ... 2-ocx.html](http://www.vistax64.com/vista-general/185313-comdlg32-ocx.html)

Just make sure put the file in C:\Windows\SysWOW64 like mentioned a little further down and register it correctly corresponding to the directory C:\Windows\SysWOW64.
## Post #186
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-08T19:53:28+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Owen
>
> Mr.Mouse, thanks for the tool.  After following FatalArms video tutorial, I noticed that when I tried using a Cactus Jack shirt logo that the image got mirrored in PTExplorer v0.1.6 so the text stayed mirrored in the game as well.  I may have missed the mention of this happening before but I just wanted to pass it along just in case.
Yeah, I did mention that in the "more info" tab on the video.  I should've flipped the image in Paint.net before saving.  Would've made the tutorial a wee bit more accurate.

If you flip it vertically, I think you'll find the image works fine in-game.
## Post #187
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-01-12T17:56:25+00:00
- Post Title: Re: smackdown vs raw 2010

can someone explain me step by step how to make an alpha map ??


wouldnt it be easier if you can choose first the main and then the alpha texture for the next pte tool update ?


thanx
## Post #188
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-12T18:38:38+00:00
- Post Title: Re: smackdown vs raw 2010

The next update you can at least save and load only the alpha values. 

Look, what you should do is chose a colour that will be fully transparent. Mostly this is colour 0 (make it black or something). Then whenever you wish parts of the picture to be fully transparent, you draw with this colour. 

If you load it up in PTE you select colour 0 in the palette and manually set the alpha value (see Active Colour box) to 0 (0 opacity = 100% transparent). The next PTE will also have the Set All Alpha option, to quicly set all alpha to a certain value.
## Post #189
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-12T18:41:26+00:00
- Post Title: Re: smackdown vs raw 2010

Oooh, you're working on a new version?  Can I suggest adding a "flip pic" option in case you import one and it shows upside down?
## Post #190
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-12T19:35:17+00:00
- Post Title: Re: smackdown vs raw 2010

I might do that.
## Post #191
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-01-12T20:34:48+00:00
- Post Title: Re: smackdown vs raw 2010

thanx mouse. you did a fantastic job. works fine now !
## Post #192
- Username: ExtremEnigma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 18, 2010 2:24 am
- Post datetime: 2010-01-17T19:57:34+00:00
- Post Title: Re: smackdown vs raw 2010

When trying to install and open PTExplorer, any version, I get a ERROR MESSAGE. On Widnows 7, it says Component "MSCOMCTL.OCX" or one of its dependencies not correctly registered, a file is missing or invalid. When I download the file and place it in either system or system 32 folders, and then register it, I get another error message. Any ideas?
## Post #193
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-17T20:00:46+00:00
- Post Title: Re: smackdown vs raw 2010

What's the other error message that you get?
## Post #194
- Username: ExtremEnigma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 18, 2010 2:24 am
- Post datetime: 2010-01-17T20:07:35+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> What's the other error message that you get?


The module "mscomct.ocx" failed to load. Make sure the binary is stored at the specified path or debug it to check for problems with the binary or dependent .DLL files. The specified module could not be found
## Post #195
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-17T20:10:57+00:00
- Post Title: Re: smackdown vs raw 2010

Are you on Vista?  Could be a User Account thing.

This thread might help:

[http://social.technet.microsoft.com/For ... 424db3589f](http://social.technet.microsoft.com/Forums/en-US/w7itprohardware/thread/93272511-43b5-42af-9468-46424db3589f)
## Post #196
- Username: ExtremEnigma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 18, 2010 2:24 am
- Post datetime: 2010-01-17T20:20:29+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> Are you on Vista?  Could be a User Account thing.

This thread might help:

http://social.technet.microsoft.com/For ... 424db3589f

I found that, but no luck. All of my pcs are running 7 ultimate
## Post #197
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-01-19T09:40:47+00:00
- Post Title: Re: smackdown vs raw 2010

first download all the missing files. search them per google.

then you must start the prog as an admin - right click, start as admin.
## Post #198
- Username: Petchy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 06, 2010 8:50 pm
- Post datetime: 2010-01-21T17:24:09+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from plodtrew
>
> @zurick, good to see you on these forums as well. The hctp textures are extractable using rrunpack to unpack the pac files and then using rtxexplorer to extract the textures. Both apps are on this forum, you just have to look for it.
The first app seemed to work, but I cannot find the second one - 'rtxexplorer'. Any chance of linking me to the topic/application?
## Post #199
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-21T21:27:10+00:00
- Post Title: Re: smackdown vs raw 2010

[viewtopic.php?f=18&t=4043&start=0&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=18&t=4043&start=0&st=0&sk=t&sd=a)
## Post #200
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-01-22T13:47:15+00:00
- Post Title: Re: smackdown vs raw 2010

i think im to dump. i put a pac file from svr on the rrunpack.exe put nothin happen.
## Post #201
- Username: ExtremEnigma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 18, 2010 2:24 am
- Post datetime: 2010-01-23T03:41:09+00:00
- Post Title: Re: smackdown vs raw 2010

Got everything working and so forth. However Xport wont let me drag the 00painttool.pt file back into the needed folder on the 360 hdd. any suggestions? When I try and drag it over, it just shows a circle with a line through it. Thanks
## Post #202
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-01-23T09:59:17+00:00
- Post Title: Re: smackdown vs raw 2010

dont do it with xport. try "Xplorer360_extreme2" with the version for your hdd (20gb, 60, 120 and 250gb).
[Xplorer360_extreme2.rar](https://xentaxbackup.github.io/file/2753_Xplorer360_extreme2.rar)
## Post #203
- Username: bugsybuff
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 24, 2010 6:20 am
- Post datetime: 2010-01-24T05:58:59+00:00
- Post Title: Re: smackdown vs raw 2010

My computer cant read the paint tool , i cant even see it when i open the xbox hard drive plus it wont load the bmp header for the ptexplorer ...please someone help
## Post #204
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-24T08:46:56+00:00
- Post Title: Re: smackdown vs raw 2010

Please explain exactly what you do, step by step,with PTExplorer.
## Post #205
- Username: bugsybuff
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 24, 2010 6:20 am
- Post datetime: 2010-01-24T16:20:37+00:00
- Post Title: Re: smackdown vs raw 2010

when i click on PTExplorer its opening and i see the svr logo but i cant press export or import image and i see at the botom just under (log)
 24/01/2010-11:13:37 AM: Loading bitmap header ,but it seem that its never loading and it wont reconize any pics probably because of the header or i dont know
## Post #206
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-25T00:02:27+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from bugsybuff
>
> when i click on PTExplorer its opening and i see the svr logo but i cant press export or import image and i see at the botom just under (log)
 24/01/2010-11:13:37 AM: Loading bitmap header ,but it seem that its never loading and it wont reconize any pics probably because of the header or i dont know

That is all quite normal. You can't press import or export, because you have not opened a .PT file. So there is nothing to export and nothing to import into.
## Post #207
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-01-26T08:03:12+00:00
- Post Title: Re: smackdown vs raw 2010

Is it possible to have ptexplorer import graphics in another file format? Downscaling graphics to bmp8 works ok for some but with skin textures, the lack of colours are really noticeable in game. 

I'm not sure if the colour limitation when importing graphics comes from the graphic format of the in game tool?
## Post #208
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-27T18:41:53+00:00
- Post Title: Re: smackdown vs raw 2010

Can anyone help me?

When I try to iport the picture into ptexplorer, it kkeps telling me that the slot wasn't replaced with the new file. It worked twice but that it, is it the type of picture I'm using or what?
## Post #209
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-27T18:44:30+00:00
- Post Title: Re: smackdown vs raw 2010

Doublecheck your image size.   It has to match the slot requirements exactly.
## Post #210
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-27T18:52:14+00:00
- Post Title: Re: smackdown vs raw 2010

Well I went by ur video u posted and did it just like u did.... Do I need to manually change the size instead of having it adjust for me?
## Post #211
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-27T18:56:01+00:00
- Post Title: Re: smackdown vs raw 2010

The program won't adjust the image size for you - you have to manually do it every single time.

The only thing it will adjust size-wise is to switch the slot designation from the lo-res size to the hi-res size.  The image itself, you still have to change in another program.
## Post #212
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-27T19:08:51+00:00
- Post Title: Re: smackdown vs raw 2010

Oh I know tht I've been using paint.net like in ur video and using resize. But it don't seem to import
## Post #213
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-27T19:26:52+00:00
- Post Title: Re: smackdown vs raw 2010

You sure you have your 00PaintTool file open in PTExplorer before you try to import?  And do you already have an image in the slot you're trying to use?
## Post #214
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-27T19:38:56+00:00
- Post Title: Re: smackdown vs raw 2010

Yes to both.... Like I said I got it to work twice but that's it
## Post #215
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-27T19:44:22+00:00
- Post Title: Re: smackdown vs raw 2010

Post a link to the image you're trying to import.
## Post #216
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-27T19:49:38+00:00
- Post Title: Re: smackdown vs raw 2010

[http://th04.deviantart.com/fs25/300W/f/ ... grafix.jpg](http://th04.deviantart.com/fs25/300W/f/2008/034/e/8/Bret_Hitman_Hart_Logo_by_dwgrafix.jpg)


[https://steelcitycrusade.com/images/scm_logo2_gegn.gif](https://steelcitycrusade.com/images/scm_logo2_gegn.gif)
## Post #217
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-01-27T19:54:28+00:00
- Post Title: Re: smackdown vs raw 2010

Thanks, but I mean the BMP files you're trying to import.  As in, ready-to-go.  I want to nail down exactly what's going wrong.

These are not Jpegs and are not the correct sizes.  Give your BMPs ready to import, pretty please.
## Post #218
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-27T20:21:09+00:00
- Post Title: Re: smackdown vs raw 2010

Oh sorry. I'm actually at wok I've been posting from my iPhone lol
## Post #219
- Username: anthonym
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 27, 2010 11:21 pm
- Post datetime: 2010-01-28T02:43:39+00:00
- Post Title: Re: smackdown vs raw 2010

hey Fatal Arms...thanks for all the help today..

i figured out what the problem was, it was changing the ratio to 256x258 when i had it do it atomatically so i have to do it manually and its working fine now.


again thanks for your time.
## Post #220
- Username: jamie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 04, 2010 4:40 am
- Post datetime: 2010-02-07T10:35:54+00:00
- Post Title: Re: smackdown vs raw 2010

I'm having a bit trouble, any help will be appreciated.

I'm on windows 7 and I tried to download the PT Explorer 1.6 from the bottom of page 11 of this topic that someone had attached to their post. I downloaded really quick and when I went to open the file it came up that the file wasn't found and gave a list of programs on my laptop that I could use to try and find the file... 

Is the file corrupted or does it just not work on windows 7?
## Post #221
- Username: jamie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 04, 2010 4:40 am
- Post datetime: 2010-02-07T10:35:55+00:00
- Post Title: Re: smackdown vs raw 2010

I'm having a bit trouble, any help will be appreciated.

I'm on windows 7 and I tried to download the PT Explorer 1.6 from the bottom of page 11 of this topic that someone had attached to their post. I downloaded really quick and when I went to open the file it came up that the file wasn't found and gave a list of programs on my laptop that I could use to try and find the file... 

Is the file corrupted or does it just not work on windows 7?
## Post #222
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-02-07T18:29:14+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from jamie
>
> I'm having a bit trouble, any help will be appreciated.

I'm on windows 7 and I tried to download the PT Explorer 1.6 from the bottom of page 11 of this topic that someone had attached to their post. I downloaded really quick and when I went to open the file it came up that the file wasn't found and gave a list of programs on my laptop that I could use to try and find the file... 

Is the file corrupted or does it just not work on windows 7?
OK, I'm a firm believer in the "teach a man to fish" theory, so here goes:

Whenever you open a file and get a list of programs that you can use to try to open it, that means your computer doesn't currently have a program assigned to that file type.  What you need to do is get the extension (that's in the file name - there's a dot and then a few characters after that; usually three characters but not always) of the file then go to Google and look it up to see what program you need to open it.

In this case, you're talking about the file which ends in .7z.  So you need to Google and see what how to open a .7z file.  Once you figure that out, you need to download the program Google says you need, and use that to open the file.

I could tell you exactly what you need, but again...teach a man to fish 

Learn how to do this and you're saving yourself a lot of headaches in your many years of computer use to come!
## Post #223
- Username: TZC
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jan 29, 2010 6:20 pm
- Post datetime: 2010-02-18T22:55:18+00:00
- Post Title: Re: smackdown vs raw 2010

Hi. Thanks a lot for this tool, it is pretty fantastic, the options available in game with it   

I've had a lot of fun using it so far, there's just a couple of suggestions I have to make things easier if you don't mind.

The main one being - if possible, to select multiple colour pallette slots at the same time for the transparancy selections, colour too but that's less important imo..

It seems that saving things to .BMP in Paint.net blurs edges of colour sometimes spreading 2 single colours into anything from 3 colours up to 24 or so, which can be a pain to click through each and set to 0 for the look originally intended. I try to leave the background colour that is to be transparent on something not used in the actual texture but sometimes it gets split into loads and I have to go through the pallette. If a picture is split into 2 or 4 parts, it can get very long and tedious to tidy the pallette.

I tried being very careful, not resizing before finishing textures and saving them with zero dithering - no luck so far.. well I can limit it, but not cut it out completely.

I have no idea how feasible it is to allow multiple selection like that or how much work it is I admit   

It would be great to be able to at some point though.


Also just an idea, to allow mirroring and flipping textures in the explorer. 

I've been creating face 'skin' textures to use, and mostly settled on using 4 128x128 slots, making a 256 for the face in total. Gives the higher resolution like using a 256 in the first place but allows 6 more 128's to be used instead of one more 256 on a caw.

Anyway, if I could simply load in one upper side and one lower side twice, then flip them in two of the slots, it'd just make things a little quicker and easier.

Thanks again for what it already is!
## Post #224
- Username: KingBradders
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 27, 2010 6:37 pm
- Post datetime: 2010-03-05T10:17:58+00:00
- Post Title: Re: smackdown vs raw 2010

i'm having trouble getting this to work this is the image i'm trying to import to svr2010 

[http://danburtan.com/stuff/rise-logo.jpg](http://danburtan.com/stuff/rise-logo.jpg)

iv done everything from the video tutorial with the exception that iv used PS CS4 Extended instead of Paint.net, iv reisgned ans rehashed using Modio but after iv drag the paint tool file back to my 360 hdd and loaded up svr2010 it tells me the data is corupt using the menu from the 360 dashboard in game and then wen i use the paint tiool it gives the same message asks if i want to overwrite the file i click on yes and the image iv imported just isn't there. please help me
## Post #225
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-05T11:48:55+00:00
- Post Title: Re: smackdown vs raw 2010

Is the image 256x256 or 128x128 in size?
## Post #226
- Username: KingBradders
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 27, 2010 6:37 pm
- Post datetime: 2010-03-06T15:09:25+00:00
- Post Title: Re: smackdown vs raw 2010

i changed my copy of the image to 256x256 in phototshop
## Post #227
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-06T15:11:39+00:00
- Post Title: Re: smackdown vs raw 2010

ok, and it did not work?
## Post #228
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-03-06T15:25:10+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from KingBradders
>
> loaded up svr2010 it tells me the data is corupt using the menu from the 360 dashboard in game and
What do you mean the "360 dashboard in game?"  

> then wen i use the paint tiool it gives the same message asks if i want to overwrite the file i click on yes and the image iv imported just isn't there. please help me
As the "more info" part of the video clearly states, you cannot take this into the in-game Paint Tool.
## Post #229
- Username: KingBradders
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 27, 2010 6:37 pm
- Post datetime: 2010-03-08T09:11:10+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Mr.Mouse
>
> ok, and it did not work?

yeah it didn't work

> Reply from FatalArms
>
> KingBradders wrote:loaded up svr2010 it tells me the data is corupt using the menu from the 360 dashboard in game and 
What do you mean the "360 dashboard in game?"  

then wen i use the paint tiool it gives the same message asks if i want to overwrite the file i click on yes and the image iv imported just isn't there. please help me
As the "more info" part of the video clearly states, you cannot take this into the in-game Paint Tool.

as in a menu from the 360 dashboard, like when it's telling you there is an update for a game, telling me the file is corrupt so the only other thing i can do is go to the paint tool in game and try to get it to work from there. i did watch the video very closely and did wot it said, but wen it didn't work i tried the in-game paint tool just incase
## Post #230
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-08T09:16:58+00:00
- Post Title: Re: smackdown vs raw 2010

Well, as so many people got it to work, there should be something that we are missing. Try upload a .PT file BEFORE updating it with a new file, and AFTER udating it. Also, DO NOT use Slot 0.
## Post #231
- Username: Diesl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 18, 2010 2:54 am
- Post datetime: 2010-03-17T19:41:03+00:00
- Post Title: Re: smackdown vs raw 2010

i'm pretty new to the Xentax Family(as u can c on my profile lol)

but i wanna share with people who are interested in face/body ect. Textures my collection from SvR 2006,07,08,09,10 & LoW(nearly all texures are in these folders. but sum pac files i opend didnt had any texures in it! good example i still try 2 get a Chris Benoit out of the SvR2007)

i would put the link list with the downloads here in this post but i know here are also sum "old friends" from CAWS.ws who dont help people for shit & just take and give nothing not even a bit back if they get sumthin or better if they get what they want!

i dont say any names here, coz i'm not playing there kindergarten BS,

but so yea would b fine if u interessted guys msg me & i send u the link list then!

BTW...i also try to get RAW 2 & Wrestlemania(last game on old xbox i'll guess) texures

and would go crazy if sum1 explains me or help me with gettin the textures ouf of UFC2009!

cant wait 2 enter the ring with Rampage haha

oh b4 i'll forget....heres my email [schwarz4life@yahoo.de](mailto:schwarz4life@yahoo.de) or my xbl GT BD2 I2oCkNeSs

UPDATE:
so since last night i also find a way 2 get the textures out of TNA iMPACT and will also load them up soon so u guys can download them

1 noob question haha how can i open briens UFC quick .bms files
can sum1 of u guys or "the great" Brienj himself explain how i can open these files or scripts?
## Post #232
- Username: naneek
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 21, 2010 7:57 pm
- Post datetime: 2010-03-22T01:37:43+00:00
- Post Title: Re: smackdown vs raw 2010

I download the latest version PTexplorer1.6.7z. First i tried to open and it says file not found. i downloaded a winzip app. and manage to get past the first part of my "why isnt this working problem". so now i can open it up inside my winzip application. I double click ptexplorer to open it up and it says Run Error 53. " File not found 'C:\Users\owner\appdata\local\temp\wz6f94\placeholder.bmp'. I already had to get past a obstacle earlier of a a run issue where i had to put in regsvr32 \windows\system32\COMDLG32.OCX.. i guess that was due to my windows xp 7 or whatever. I pretty much got everything i need to start transfering images into the game, just this Error 53 is being a dick. I google'd it and it told me just reinstall the programs. I re-installed the PTexplorer and the winzip a few times and still no luck.

anybody that would know how to get around this?
## Post #233
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-22T06:48:09+00:00
- Post Title: Re: smackdown vs raw 2010

Forgive me if I say: DUHH... Get yourself 7zip, then UNPACK ALL of the files to a folder of your choice. Now go to the folder and start the program. Starting an executable from inside a WinZip program is seldom possible, as the executable relies on other files in the archive that are not extracted.
## Post #234
- Username: dmasta
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2010 6:26 pm
- Post datetime: 2010-03-25T10:54:08+00:00
- Post Title: Re: smackdown vs raw 2010

i've been using ptexplorer for sometime now but as of late, i have been using it to import face textures. Now what i do is cut and parse each face part instead importing the face as a whole. But the only problem is making the background of the face part transparent. For example i may have a nose part i want to import and i made my background black just to make it easier to transparent when i put it in ptexplorer. i just click on the background and change the alpha from 255 to 0. Now when i do this, the majority of the background is gone (transparent) but there are still bits and pieces left around the edges of my face part  . I was just wondering is there an easier way to do this without having to go back, click on each background piece that is left, and transparent it manually. It'll be a whole easier if i could just eliminate the whole background all in one step. Can someone help me on this problem?
## Post #235
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-25T11:44:27+00:00
- Post Title: Re: smackdown vs raw 2010

This is probably due to an anti-aliasing/dithering effect done by your own paint program when you created the image. black around the edges then won't be the black you want, but a little brighter (and in effect a different colour).
## Post #236
- Username: dmasta
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2010 6:26 pm
- Post datetime: 2010-03-25T12:18:43+00:00
- Post Title: Re: smackdown vs raw 2010

so what do you think the best solution for this? like a different background color or is there any way to start off my background as transparent so i won't have to worry about changing the alpha.
## Post #237
- Username: TZC
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jan 29, 2010 6:20 pm
- Post datetime: 2010-03-27T01:32:02+00:00
- Post Title: Re: smackdown vs raw 2010

Hi. The best solutions are,

 Don't edit before the final resize. Put the resize on then cover the parts of a texture you want to be transparent.

If not, line around the shape with the bg colour you're going to use as transparent for - also bright pink or yellow, or something unused in the final work like that is easier to check

Not sure what prog you're using to save the final work but in paint.net, or any other, make sure dithering is set to 0.

When I was using this, I managed to keep the bg colours down to 1,2 or 3 ish

I'm not sure why but sometimes a few slip through. It's a lot better than having 32 to deal with though.
## Post #238
- Username: dmasta
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2010 6:26 pm
- Post datetime: 2010-03-27T05:50:28+00:00
- Post Title: Re: smackdown vs raw 2010

thx TZC for the reply...i'll keep that in mind;).
## Post #239
- Username: SuSpiRia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 07, 2010 1:30 am
- Post datetime: 2010-04-07T11:44:01+00:00
- Post Title: Re: smackdown vs raw 2010

I am having certain trouble actually trying to get PTExplorer to work and I need some help. 

When I have downloaded the program, i extract it using Winrar, which places it on my desktop etc. Yet, when I go to open up PTExplorer, I get the message ''Component 'comdlg32.ocx' or one of its dependencies not correctly registered: a file is missing.''

Now I'm completely new to this sort of thing, and help would be greatly appreciated.
## Post #240
- Username: Lashley
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 12, 2010 4:45 am
- Post datetime: 2010-04-11T22:09:22+00:00
- Post Title: Re: smackdown vs raw 2010

This is awesome. Can this be used to import faces, etc?
## Post #241
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-04-11T23:10:17+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from SuSpiRia
>
> I am having certain trouble actually trying to get PTExplorer to work and I need some help. 

When I have downloaded the program, i extract it using Winrar, which places it on my desktop etc. Yet, when I go to open up PTExplorer, I get the message ''Component 'comdlg32.ocx' or one of its dependencies not correctly registered: a file is missing.''

Now I'm completely new to this sort of thing, and help would be greatly appreciated.
read the "more info" part of the video.
## Post #242
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-04-19T06:23:50+00:00
- Post Title: Re: smackdown vs raw 2010

Hey guys. 

As many of you know, the latest xbox dash update allows you to save games on a usb flash/pen drive. By saving on a usb drive instead of the hardrive, you can access your paint tool file without using xsata or any other complicated methods. Here's how:

1. Download a programme called usb xtaf (google it). This programme allows you to explore the contents of your flash drive. 
2. Plug you flash drive with your saves into you pc and the start up xtaf. 
3. Select "file -open drive". This should give you a list of all the saves on your drive. 
4. Browse to the folder where the svr2010 save is (mine is called 54510844) and look for your 00painttool.pt file. 
5. Right click the file and select extract. Save it where you please. dont close xtaf, you will use again below.  



Now that you have your Paint tool fle on your hdd, you edit it with pt explorer in the normal way i.e. inject graphics, resign & rehash with modio when you are done. 

6. Now that you have finished working with your paint tool file, go back to xtaf and delete the paint tool file on the flash disc. Right click in the same directory location in xtaf as the old file and select "inject". Browse for your new paint tool file and inject it. 

Thats it, the file should now work in game.
## Post #243
- Username: immortalbeloved
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 20, 2010 5:50 pm
- Post datetime: 2010-04-20T21:38:20+00:00
- Post Title: Re: smackdown vs raw 2010

anyone think they can upload a video of the   Texture hacks using USB pen drive very hard to understand need a video please someone
## Post #244
- Username: Reaper2190
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 15, 2010 2:54 am
- Post datetime: 2010-04-24T18:35:48+00:00
- Post Title: Re: smackdown vs raw 2010

Hello There, I'm having a problem.

It will not let me copy my Paint tool file back into my xport. It just shows me the "No Entry" symbol. Like: (\) That. 

Any  ideas?
## Post #245
- Username: ThePanda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 16, 2010 3:21 am
- Post datetime: 2010-05-15T21:47:36+00:00
- Post Title: Re: smackdown vs raw 2010

Hi guys,

I'm getting a weird one, I'm following the instructions on how to do this exactly but whenever I try to open the file through the game it says the Paint Tool is damaged. Any ideas?
## Post #246
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-05-15T22:31:48+00:00
- Post Title: Re: smackdown vs raw 2010

Reaper and Panda:  You guys should read the "more info" section on my tutorial video.   Both questions are answered there.

Reaper: Turn off User Account Control
Panda:  Don't use it in the in-game paint tool.
## Post #247
- Username: ThePanda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 16, 2010 3:21 am
- Post datetime: 2010-05-16T11:02:40+00:00
- Post Title: Re: smackdown vs raw 2010

Thanks very much for the info, I'll try that and see how I get on. Much appreciated
## Post #248
- Username: gothmickey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 14, 2010 6:55 am
- Post datetime: 2010-05-22T02:40:09+00:00
- Post Title: Re: smackdown vs raw 2010

Hello people.... Question...

I was able to get the image I want into ptexplorer... I rehashed and redesigned... saved.. moved the paint tool file from my device back to 360 HDD... I started the game, went to paint tool, only to receive a message saying NO PAINT TOOL FILE, DO YOU WANT TO CREATE ONE NOW? What did I do wrong??
## Post #249
- Username: FatalArms
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Dec 11, 2009 4:49 am
- Post datetime: 2010-05-22T02:57:56+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from gothmickey
>
> I started the game, went to paint tool, only to receive a message saying NO PAINT TOOL FILE, DO YOU WANT TO CREATE ONE NOW? What did I do wrong??
If you'd read the "more info" section of my tutorial video, you'd know the answer to this question.
## Post #250
- Username: gothmickey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 14, 2010 6:55 am
- Post datetime: 2010-05-22T04:00:43+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from FatalArms
>
> gothmickey wrote:I started the game, went to paint tool, only to receive a message saying NO PAINT TOOL FILE, DO YOU WANT TO CREATE ONE NOW? What did I do wrong??
If you'd read the "more info" section of my tutorial video, you'd know the answer to this question.

It worked...

Fatal, thanks for the video... I followed it word for word, action for action... and yes, I read your more info section... thank you... Yes, I am a noob LOL...
## Post #251
- Username: Pare71
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:04 pm
- Post datetime: 2010-05-23T11:23:27+00:00
- Post Title: Re: smackdown vs raw 2010

When i try to open my .pt file with PTExplorer,they said ''Run-Time Error 9,subscript out of range''

What can i do??

Thanks!!
## Post #252
- Username: Pare71
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-23T12:45:06+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from Pare71
>
> When i try to open my .pt file with PTExplorer,they said ''Run-Time Error 9,subscript out of range''

What can i do??

Thanks!!

Read up at this forum. Honestly, also read instructions that come with it. And always unpack everything in an archive that you download.
## Post #253
- Username: nirvanafanehw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 18, 2010 11:05 am
- Post datetime: 2010-05-24T21:39:54+00:00
- Post Title: Re: smackdown vs raw 2010

I Keep getting this message...I've looked around the forum and I didn't find anything
## Post #254
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-24T21:44:59+00:00
- Post Title: Re: smackdown vs raw 2010

Windows 7?
## Post #255
- Username: nirvanafanehw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 18, 2010 11:05 am
- Post datetime: 2010-05-24T21:46:25+00:00
- Post Title: Re: smackdown vs raw 2010

No, XP...
I Tried deleting the files and extracting them again but the same thing still happens
## Post #256
- Username: Pare71
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:04 pm
- Post datetime: 2010-05-25T05:53:00+00:00
- Post Title: Re: smackdown vs raw 2010

Pare71 wrote: When i try to open my .pt file with PTExplorer,they said ''Run-Time Error 9,subscript out of range''

What can i do??

Thanks!!


Mr.Mouse wrote: Read up at this forum. Honestly, also read instructions that come with it. And always unpack everything in an archive that you download.




i have not found anything about that on this forum,i think i'm alone in this haha!  but,thank you for your reply
## Post #257
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-25T07:36:56+00:00
- Post Title: Re: smackdown vs raw 2010

Exactly which PTExplorer pack did you download?
## Post #258
- Username: Pare71
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:04 pm
- Post datetime: 2010-05-25T08:44:55+00:00
- Post Title: Re: smackdown vs raw 2010

i have downloaded this one (PT Explorer 0.1.6) in the 'tools' section in this website.I have tried some registry scans and repairs,but,the same problem came when i try to open my .pt file in PTExplorer.I can open otherelse .pt file,but when i open my .pt file, ''RunTime Error 9 Subscript Out of Range'' appear.i'm desperate haha =)
## Post #259
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-25T13:24:00+00:00
- Post Title: Re: smackdown vs raw 2010

It could be that your PT file is corrupt. Please zip it and upload it here. (Attach)
## Post #260
- Username: nirvanafanehw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 18, 2010 11:05 am
- Post datetime: 2010-05-30T18:05:31+00:00
- Post Title: Re: smackdown vs raw 2010

No one has a solution to my problem?
## Post #261
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T18:22:20+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from nirvanafanehw
>
> No one has a solution to my problem?

Please zip up the files you extracted again and upload it here.
## Post #262
- Username: nirvanafanehw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 18, 2010 11:05 am
- Post datetime: 2010-05-30T18:31:01+00:00
- Post Title: Re: smackdown vs raw 2010

Done.
[PTExplorer.rar](https://xentaxbackup.github.io/file/3090_PTExplorer.rar)
## Post #263
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:29:20+00:00
- Post Title: Re: smackdown vs raw 2010

It works at my end. 
This could be a problem with Windows's stuff:

```
C:\WINDOWS\system32\oleaut32.dll
C:\WINDOWS\system32\olepro32.dll
C:\WINDOWS\system32\asycfilt.dll
C:\WINDOWS\system32\stdole2.tlb
C:\WINDOWS\System32\COMCAT.DLL
C:\WINDOWS\system32\comdlg32.ocx
C:\WINDOWS\system32\mscomctl.ocx

```


Especially mscomctl. What XP SP have you got. Any word on the version of any of those above?
## Post #264
- Username: nirvanafanehw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 18, 2010 11:05 am
- Post datetime: 2010-05-30T22:37:20+00:00
- Post Title: Re: smackdown vs raw 2010

How do I find that out?

It worked once since I first had the problem. I was getting error messages telling me to run the chkdsk utility. when it worked those errors didn't show up. they're now showing up again and it's not working. Could that be the problem
## Post #265
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-01T21:30:10+00:00
- Post Title: Re: smackdown vs raw 2010

You might have a virus or malware. In any event, for version info go to the windows/system32 folder and right click on any of the above mentioned files.
## Post #266
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-02T05:28:05+00:00
- Post Title: Re: smackdown vs raw 2010

[blog/](http://forum.xentax.com/blog/) version 0.1.7 of PT Explorer.
## Post #267
- Username: dmasta
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2010 6:26 pm
- Post datetime: 2010-06-03T02:24:16+00:00
- Post Title: Re: smackdown vs raw 2010

Don't mean to sound like a noob mouse but how exactly does the "set all alpha at once" feature work? I've been wanting to this for a long time but don't know how to it in the program. Could u help plz?
## Post #268
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-03T09:05:49+00:00
- Post Title: Re: smackdown vs raw 2010

Simple, it sets all Alpha values in the palette to one value. The palette has 256 colours, each with a red, green, blue and alpha value. The alpha sets te transparency for that colour. 0 is totally transparent, 255 is solid (not transparent).
## Post #269
- Username: nirvanafanehw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 18, 2010 11:05 am
- Post datetime: 2010-06-04T23:28:16+00:00
- Post Title: Re: smackdown vs raw 2010

C:\WINDOWS\system32\mscomctl.ocx



this one says 
6.1.95.45
## Post #270
- Username: jhonsadins
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 02, 2010 9:09 pm
- Post datetime: 2010-07-03T07:53:27+00:00
- Post Title: Re: smackdown vs raw 2010

statement mr mouse is that if we could edit images in photoshop and insert them into the game by using this save file it would be incredibly easy to make perfect attires, tattoos, logos or other textures from the created wrestler feature in the game.
## Post #271
- Username: JVZBrowser
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 24, 2010 5:34 am
- Post datetime: 2010-07-26T18:27:31+00:00
- Post Title: Re: smackdown vs raw 2010

Can anybody give me the texture of Batistas Face and Body??
## Post #272
- Username: mcbride56
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 29, 2010 7:28 pm
- Post datetime: 2010-07-26T22:07:53+00:00
- Post Title: Re: smackdown vs raw 2010

When trying to open ptexplore i get the message "component  'comdlg32.ocx' or one of its dependencies not correctly registered: a file is missing or invalid". Im on windows 7 is there any way to help me   ?
## Post #273
- Username: B7TNR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 17, 2010 12:45 pm
- Post datetime: 2010-07-28T18:45:12+00:00
- Post Title: Re: smackdown vs raw 2010

> Reply from mcbride56
>
> When trying to open ptexplore i get the message "component  'comdlg32.ocx' or one of its dependencies not correctly registered: a file is missing or invalid". Im on windows 7 is there any way to help me   ?

I get the same error. It's stopped me from going nuts with textures on a much, much faster laptop. Any help?
## Post #274
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-09-29T15:37:21+00:00
- Post Title: Re: smackdown vs raw 2010

The contents of this post was deleted because of possible forum rules violation.
