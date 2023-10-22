## Post #1
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-18T18:07:20+00:00
- Post Title: Tekken Tag Tournament 2 Tools

I DID NOT MAKE THE TOOLS, HOWFIE HAS CREATED THE TOOLS, BUT TOLD ME TO RELEASE THEM AS HE CANNOT AT THE TIME.

Hey, im here to release the Tekken Tag Tournament 2 tools for the models. I have also written a tutorial and included screens 

WHAT YOU WILL NEED:
[Noesis](http://forum.xentax.com/viewtopic.php?f=33&t=4582)
[Tekken Tag Tournament 2 Tools [All credits go to howfie]](http://www.mediafire.com/?pa4cpic4m6vr9en)
TTT2 files (ofc. I am using the xbox 360 files here, I dont know if this will fully work with PS3 files, though I think howfie will be testing that out when he recieves the game)

So, to begin with, you need to decompress the .bin's with xbdecompress. This will give out your decompressed.bin. For this I seperated the data000.bin into another folder to avoid the of the extraction of every .bin as I have already done that.
So, here is what I have in the folder, the compressed.bin and bin2nmd:


Now, you need to use the cmd (or in my case Total Commander, I dont know how to use cmd on its own, TC is easier for me)
Enter in the following (common sense lol)


This will appear:


Then, it will continue on and on until every bin is extracted (that is if all the compressed bin's are in the same folder, but in my case I only have one) once each bin is extracted this will appear underneath:

NDXR = Models
NTXR = Textures
BONE = Well... Bones xD

This will generate a folder with all the nmd's extracted:


Now its time to open Noesis, in this part I am using data014 as data000 doesnt have the main models and has no bones for the models.
Opening the models will something like this (there are only a few combined models like Anna's Octopus costume, Kunimitsu's Alt, Tiger Jackson model etc the rest are uncombined and you will have to join all the parts of the model together)


Loading textures will show something like this (all textures for a certain model are in one _texture file, like this model has around 70-ish textures in one file, so it will show them moving through each texture when loading it)


Bone files wont load, it will show a "File could not be previewed" error unless Noesis is updated to let the bone files load up alone.
When you find which files you need (model, tex and bone. textures and bones are stored after the models, so there is a batch of models, and one of them is the one you need, there will then be a batch of texture files, one of them will be the one you need, same with the bone files) I usually put them in their own folder so its easier to find. You need mergenmd in that folder too like so:


Load up mergenmd (dont need cmd or anything this time) and you will get these:



Just load up the files that the program asks for.
This will then let you save the combined .nmd which is perfect for loading into Noesis, just name it whatever you want:


So, once you do this, you will get your nmd. Load this nmd into Noesis and you have your model! The texture will not be assigned correctly, you will need to load it into whatever program you use afterwards and re-texture it. So here is what it should look like:


As you can tell this is the incorrect bone file, you will just have to test every bone file in the batch after the model you want, it is time consuming, but this is the only way to do it, unless Noesis gets updated for support of these bone files. Some meshes will seem like they have dissapeared but they havent, they are just randomly transparent.
So thats how you do it  Hope you like this tutorial and enjoy the epic tools howfie made!
## Post #2
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-09-18T18:11:53+00:00
- Post Title: Tekken Tag Tournament 2 Tools

Thanks for tutorial Kim, and for tool howfie!
## Post #3
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-18T18:16:14+00:00
- Post Title: Tekken Tag Tournament 2 Tools

> Reply from Kamillho
>
> Thanks for tutorial Kim, and for tool howfie!
Im not Kim! D: Yesh, everyone thank the epic howfie.
## Post #4
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2012-09-18T18:24:37+00:00
- Post Title: Tekken Tag Tournament 2 Tools

Yess, we shall hail Howfie for this blessedness he gave to us.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-18T19:23:51+00:00
- Post Title: Tekken Tag Tournament 2 Tools

np guys. remember, these tools are for the desperate; they are for those who can't wait for rich to update noesis and don't mind doing a little work to get what they want.

as daz mentioned there are several problems.

#1 the model format changed slightly (textures are wrong on everything but the NPCs).
#2 level geometry format changed slightly (many static models have polygons strewn all over the place).
## Post #6
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-09-18T20:10:43+00:00
- Post Title: Tekken Tag Tournament 2 Tools

Marvelous job by howfie, as usual.
Thanks for the tutorial TRdaz, helpful indeed!
It's amazing how I've been playing this game for only about 5 days (I pre-ordered btw) and you already have this joint project of yours released here. Howfie's got some mad skills!
Can't wait to browse through the files.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-18T20:48:55+00:00
- Post Title: Tekken Tag Tournament 2 Tools

the xbox360 version of the game was leaked almost a week before the official release i think, so sample were easy to obtain. rich did all the work. my tools are nothing more than a chunk extractor and a file merger. lol back to trying to pass the combot tutorial ha ha ha. no worky on ps3 version of game... just got it today from gamestop and the data is compressed (don't think it is zlib).
## Post #8
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-09-18T23:47:35+00:00
- Post Title: Tekken Tag Tournament 2 Tools

and ever so modest. Credit where credit is due!
TTT2 fightlab is crazy fun. Going for S-rank on stage 4 made me feel like a noob.
## Post #9
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-19T06:46:50+00:00
- Post Title: Tekken Tag Tournament 2 Tools

> Reply from IvoryCutter
>
> 
Thanks for the tutorial TRdaz, helpful indeed!
It's amazing how I've been playing this game for only about 5 days (I pre-ordered btw) and you already have this joint project of yours released here. Howfie's got some mad skills!
Can't wait to browse through the files.
Your welcome man  Though, howfie made the tools so there is no point in thanking me for anythin lol xD I just made the tutorial xD
TTT2 is addicting. I cant stop playing!
## Post #10
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-19T07:06:17+00:00
- Post Title: Tekken Tag Tournament 2 Tools

Good job.
But, PS3-version is not supported
## Post #11
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-19T17:45:28+00:00
- Post Title: Tekken Tag Tournament 2 Tools

> Reply from dj082502
>
> Good job.
But, PS3-version is not supported
Yep, thats why I said I used 360 files
## Post #12
- Username: DeathBillZhao
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 28, 2011 4:11 pm
- Post datetime: 2012-09-19T20:07:55+00:00
- Post Title: Tekken Tag Tournament 2 Tools

Great Job!
If this works on the others BINs cannot be decompressed? The BINs seemed that are not be compressed or compressed by a different way.
And the animations are another thing which I cared.
## Post #13
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-09-20T02:48:29+00:00
- Post Title: Tekken Tag Tournament 2 Tools

Thanks 
Btw , will MrAdults update noesis that supports nmd to get the models in the future?
## Post #14
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-20T06:26:51+00:00
- Post Title: Tekken Tag Tournament 2 Tools

> Reply from DeathBillZhao
>
> Great Job!
If this works on the others BINs cannot be decompressed? The BINs seemed that are not be compressed or compressed by a different way.
And the animations are another thing which I cared.
Do you mean some of the bins in the game wont decompress? Yeah, some of them wont. Most of them are not model/textures, most of em are random effects or sound/video.

> Reply from DOTAPRINCE
>
> Thanks 
Btw , will MrAdults update noesis that supports nmd to get the models in the future?
Hopefully he will
## Post #15
- Username: xemnas26
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2011 2:03 pm
- Post datetime: 2012-09-30T03:52:51+00:00
- Post Title: Tekken Tag Tournament 2 Tools

has any one found all the parts to yoshimitsu? ive only found parts of him with out his armor and i cant find any ones heads
## Post #16
- Username: cgjeff
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 27, 2011 7:09 am
- Post datetime: 2012-11-10T04:51:38+00:00
- Post Title: Re: Tekken Tag Tournament 2 Tools

Has anyone found the texture files for Kunimitsu's regular outfit yet?  I found the models just fine, but Have not been able to find the textures.
## Post #17
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-12-11T21:49:56+00:00
- Post Title: Re: Tekken Tag Tournament 2 Tools

> Reply from cgjeff
>
> Has anyone found the texture files for Kunimitsu's regular outfit yet?  I found the models just fine, but Have not been able to find the textures.

I've got the same error. Some models dont have all textures. Like Anna in dress, Nina default outfit, Jun lower part, etc. I hope someone will update tool for TTT2 models.
## Post #18
- Username: wajahat122
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 19, 2012 10:25 pm
- Post datetime: 2013-01-03T11:23:23+00:00
- Post Title: Re: Tekken Tag Tournament 2 Tools

i have iso
## Post #19
- Username: misquared
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 26, 2010 8:32 am
- Post datetime: 2013-01-19T07:15:23+00:00
- Post Title: Re: Tekken Tag Tournament 2 Tools

ew, I figured I didn't have space enough to get the whole Tekken file ;n;
Does anybody have the TTT2 Alisa models set? D;
## Post #20
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2014-02-12T13:49:24+00:00
- Post Title: Re: Tekken Tag Tournament 2 Tools

is there any tool etc to extract stuff from ps3 version of the game?  i tried bin2nmd on ttt2 .bin files i got but it didn't work as i expected  it just sat there.  is it possible extraction from ps3 .bins?
thanks
