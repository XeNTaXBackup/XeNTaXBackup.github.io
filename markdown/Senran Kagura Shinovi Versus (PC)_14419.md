## Post #1
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-06-02T03:02:56+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

So with Senran Kagura coming to PC, I'm hoping someone will be so kind as to create some tools/scripts/etc for the lovely ladies. Fortunately the files are organized fairly nicely so it's easy to get the model/texture package. Here is a .rar of several models (I believe I grabbed body, head, hair and a few accessories as well as the associated textures). The files are *.cat format. If more are needed I'm happy to share. 

[http://www.mediafire.com/download/kddlc ... 9x3/SK.rar](http://www.mediafire.com/download/kddlc0agag9h9x3/SK.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-02T03:27:48+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

> Reply from ssringo
>
> So with Senran Kagura coming to PC, I'm hoping someone will be so kind as to create some tools/scripts/etc for the lovely ladies.Are you a lovely lady?  

> Fortunately the files are organized fairly nicely so it's easy to get the model/texture package.yep they are. And it would be rather easy imho to create some maxscript (or Noesis python script) for yourself if you'd take up some spare minutes of your free time to learn how to do it.

Problem, of course, will be to find the starting addresses of face indices and vertex block programmatically.
(For face indices block a search for 0000 0100 0200 should do the trick,
vertex blocks start 16 bytes after 01000000 00000000 01.)



acc_body_00-mdl.jpg (170.74 KiB) Viewed 2356 times

face indices count = face count * 3
## Post #3
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-06-02T03:47:26+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

> Reply from shakotay2
>
> Are you a lovely lady?

Not exactly    Edit: Didn't realize colon+x was a "mad" emoticon

> yep they are. And it would be rather easy imho to create some maxscript (or Noesis python script) for yourself if you'd take up some spare minutes of your free time to learn how to do it.

While I'm not opposed to learning how, I would be starting from scratch as I have zero knowledge or experience with doing so. I've see some of the scripts folks have posted on xentax (some of which were yours IIRC) and they could be in a long lost language and it'd make as much sense   Hell, I'm currently scratching my head trying to figure out Gedosato so I can knock out those nasty jaggies in the game.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-02T04:04:41+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

> Reply from ssringo
>
> shakotay2 wrote:Are you a lovely lady?  

Not exactlytoo bad - I'm pretty sure some coder in this forum would like to create a script for a lovely lady.

> Hell, I'm currently scratching my head trying to figure out Gedosato so I can knock out those nasty jaggies in the game.understand - you're more an artist than a coder. But that's okay, imho.
## Post #5
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-06-02T11:17:13+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

The model format's pretty much the exact same as the one from Neptunia U (or is it the other way around?), just without a couple of vertex values. So basically, the work's already done since I already made a MaxScript for the former.
[https://mega.nz/#!DtBGVCoI!bSttjzKNf2Vg ... PjdCUvcJTY](https://mega.nz/#!DtBGVCoI!bSttjzKNf2Vg5RRog8a-JghHJZkqYmYMNPjdCUvcJTY)
## Post #6
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2016-06-02T12:17:29+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

A extractor for the CAT archives. There doesn't seem to be any file type identifiers in this version so I could only auto detect extensions for the tmd files not the gxt so they will come out as .dat but they are usually the larger files in the _tex archives. The old GXT extractor for NeptuniaU should work on them fine.
[TamsoftSKPC_CAT.zip](https://xentaxbackup.github.io/file/11006_TamsoftSKPC_CAT.zip)
## Post #7
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-06-02T23:48:03+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

Thank you for the script mikulover39. Spent an hour or so extracting and organizing the characters and everything seems to be working fine.   

Thank you Random for your continued efforts with the format. I didn't have time to test on much other than some Asuka model parts but it did work for me on Max10. Unfortunately I don't have 3DS Max on my work laptop so I can't do much else for now. I am glad to see actual face bones on the models though. Facial texture swapping can stay in the Neptunia series. 

Edit: Messed about with a few models. Found one issue so far. File name is pl13_hair_mdl_hi and upon importing to max the mesh is messed up although the skeleton is intact. Here is a copy of the file if needed. 

[https://www.mediafire.com/?3m3u0gsrpca446f](https://www.mediafire.com/?3m3u0gsrpca446f)
## Post #8
- Username: b59943201
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 14, 2015 1:14 am
- Post datetime: 2016-06-03T06:01:27+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

del
## Post #9
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-06-03T10:43:23+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

> Reply from ssringo
>
> Edit: Messed about with a few models. Found one issue so far. File name is pl13_hair_mdl_hi and upon importing to max the mesh is messed up although the skeleton is intact. Here is a copy of the file if needed. 

https://www.mediafire.com/?3m3u0gsrpca446fAh, excellent! That'll help me with figuring out the vertex setups! While I work on updating the script, if you wanna get it to import that particular model correctly, temporarily add 
```
fseek f 0x04 #seek_cur
```
 directly underneath
```
tv = ((readshort f as float / 1024) * -1)
```
 at line 190, for whatever reason that model has two UV mapping layers compared to everything else, but they're both the exact same. Hrm. 

And don't worry about sending me the files to test, I have 'em all downloaded already.

(EDIT: Think I might've found the byte, but I'm gonna do some more experimentation first.)
(EDIT 2: Script has been updated, in the same link above. Delete the previous ones you may have downloaded too since I renamed the file (now TamsoftPC_TMD). Now works with both Neptunia U and Senran Kagura models in the same script, and fixes two-UV layer SK models. Still gotta unpack and look through the rest of the models, so expect another update.)

> Reply from b59943201
>
> sorry my eng is so poor..

someone can tell me how to extractor the _tex archives plz?

use TamsoftSKPC_CAT.zip to extractor will become .dat

and

use Tamsoft_CAT.bms or Tamsoft_GXT.bms (ttp://forum.xentax.com/download/file.php?id=10666) will become .dds but can't use..

someone help plz..I'll look into fixing the GXT script to extract the textures (and their filenames) properly soon.
## Post #10
- Username: b59943201
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 14, 2015 1:14 am
- Post datetime: 2016-06-03T13:58:14+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

del
## Post #11
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-06-03T16:21:17+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

Thanks for the updates Random. Will be making a bigger effort to check model parts tonight/through the weekend and will update if I find anything else. 

As an aside, Onechanbara Z2 Chaos came out last night. The game is also from Tamsoft and the file structure looks just like Senran Kagura and uses *.cat format as well. Current tools start extracting into .dat files but crashes so maybe it's similar in format. Any plans to look at that game after Senran Kagura?
## Post #12
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-06-03T18:39:22+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

> Reply from ssringo
>
> Thanks for the updates Random. Will be making a bigger effort to check model parts tonight/through the weekend and will update if I find anything else. 

As an aside, Onechanbara Z2 Chaos came out last night. The game is also from Tamsoft and the file structure looks just like Senran Kagura and uses *.cat format as well. Current tools start extracting into .dat files but crashes so maybe it's similar in format. Any plans to look at that game after Senran Kagura?It'll probably be something like stage models that my script will crash on, since I haven't looked into those yet.

Anyway, since Onechanbara uses a completely different model format (a variation on the Phyre format), I think it's safe to say that I won't be looking into researching it, sorry.
## Post #13
- Username: Singe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 03, 2016 9:18 pm
- Post datetime: 2016-06-03T19:10:53+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

Would it be possible to get model rips from the game that can be opened in something like Open 3D Model Viewer?
## Post #14
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-06-03T21:33:57+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

Ah, the dreaded phyre format. That's the format FFX/X-2 uses and why nobody wants to create scripts for that one either. Sad to hear but oh well, can't always get what you want   

Back on topic with SK though. Even though I can't do anything with meshes until I get home, I have continued extracting and sorting with the current bms scripts. I'm not sure what issues the other guy was having with the dds textures. Everything regarding textures  seemed to extract correctly and was viewable/usable on meshes. Maybe the person doesn't have a program or plugin able to view dds files? Noesis can certainly view them (is how I was sorting characters without being able to see the mesh).

Edit: Forgot to mention, there does seem to be some issues extracting textures from some of the files in the /dlc000/nnj/ folder with the GTX script. quickbms hangs for a minute then errors out with 

"error in src\xalloc.c line 617: xdbg_malloc<>

Error: memory allocation problem
         No error"

Haven't had time to go through everything but files in the /std/ folder seem to work fine.
## Post #15
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2016-06-03T22:23:54+00:00
- Post Title: Senran Kagura Shinovi Versus (PC)

@ssringo
Strangely enough the textures in that folder are using the vita version of GXT which I looked into a couple of weeks back and made a noesis script to extract them. Re-download the CAT bms script above and it should extract the vita version of the files with the extension .gxt and then use this noesis script to open them, .dat textures still require the neptuniaGXT script. I also added detection for the vita version of the tmd files since I found some still left in the pc version.

It seems as if the /dlc0/nnj/ folder has them and some in the /enemy/ folder but I haven't found any in /patch/ or /npc/ yet

@b59943201
By "will become .dds but can't use.." do you mean you don't have a program to open the dds files? noesis supports them or there's even plugins for Photoshop and gimp and a windows photo viewer plugin that comes with microsoft xna framework.

It's a shame about onechanbara but I think they have been using the phyre format since the ps3 games. You can still extract the models using hex2obj like I did before but it's tedious and no bones or rigging. [viewtopic.php?f=16&t=8193&p=91327#p91327](http://forum.xentax.com/viewtopic.php?f=16&t=8193&p=91327#p91327)
[fmt_SenranKaguraSV_gxt.zip](https://xentaxbackup.github.io/file/11005_fmt_SenranKaguraSV_gxt.zip)
## Post #16
- Username: b59943201
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 14, 2015 1:14 am
- Post datetime: 2016-06-04T02:16:05+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

sorry everybady 

now i get it...

big to thank you every one!!
[20160604.jpg](https://xentaxbackup.github.io/file/11007_20160604.jpg)
## Post #17
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-06-04T20:18:18+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

^^ I dunno why you're having issues. Everything extracts fine for me with current quickbms and the scripts linked in this thread. Are you using the GTX script mikulover posted [in this thread](http://forum.xentax.com/viewtopic.php?f=16&t=12753&start=15)?

I haven't found any further issues with extraction or importing of models (thus far). I am wondering if anyone else has found the underwear models? I figured the characters would at least have their default with the "std" files but nope, they're all going commando apparently and I can't seem to find them elsewhere. I know in the /compose/ folder there is a bunch of "bura" and "pants" gtx files but no mesh to put on the bodies and I'm not even sure those textures are the correct ones.
## Post #18
- Username: punhete
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 06, 2016 6:24 am
- Post datetime: 2016-06-05T22:35:04+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

Hi,

Regarding the models, do you think there's any chance that a Blender-compatible tool will be available? That script is only for Max, right?
## Post #19
- Username: tcl36478655
- Rank: beginner
- Number of posts: 34
- Joined date: Mon Apr 08, 2013 9:22 am
- Post datetime: 2016-06-06T11:19:45+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

> Reply from b59943201
>
> sorry everybady 

now i get it...

big to thank you every one!!

hi,you should use TamsoftSKPC_CAT.bms first.  
that makes .cat ==>.dat
then use Tamsoft_GXT.bms.
so the .dat ==>.dds
## Post #20
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-07-15T06:20:53+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

Does anyone have Tamsoft_GXT.bms script?
## Post #21
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-15T09:58:28+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

here   
[download/file.php?id=10666](http://forum.xentax.com/download/file.php?id=10666)

found that link in this post
[viewtopic.php?p=119206#p119206](http://forum.xentax.com/viewtopic.php?p=119206#p119206)
## Post #22
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-07-16T16:34:19+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

> Reply from AceWell
>
> here   
download/file.php?id=10666

found that link in this post
viewtopic.php?p=119206#p119206

Thanks a lot:))
## Post #23
- Username: cascraft
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 22, 2016 7:33 am
- Post datetime: 2016-10-23T02:25:43+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

any german tutorial how to do that? i dident get it
## Post #24
- Username: atlus59
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 25, 2017 6:17 am
- Post datetime: 2017-03-25T00:12:11+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

hello everybody !! im kinda new to this and i absolutely dont know how to have the SK  models on 3ds Max. I use the script but i got nothing and all the files are protected or something. Can somebody can explain step by step how to get the models on 3ds Max please ?
## Post #25
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-02T03:33:42+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

Might as well mention that I've updated the script now.
[https://mega.nz/#!ulpnmaJS!ffrdVu0T81lK ... 8Ac8hYL6FM](https://mega.nz/#!ulpnmaJS!ffrdVu0T81lKBKR3FVkFO4K3jYPi5jtwd8Ac8hYL6FM)

```
Changed bone numbers to bone checksums instead.
Added a ton of replacement bone names to replace the checksums, don't expect hair bones (especially SK's) to be named correctly.
Optimized polygon group importing a bit so things will load a bit faster.
Fixed rigging being broken in one way or another for newer 3DS Max versions.
```


(EDIT: [Here's mikulover39's QuickBMS scripts](https://mega.nz/#!Lg5hCRRZ!9HtOVAUV8Fi8SY86yKXMI4a612TBW5YguD2lZHzac4w) for the .CAT archives in Estival Versus, hope it's alright that I'm sharing them here.)

(EDIT 2: Updated the script again.)

```
Fixed models with three UV mapping layers not importing correctly.
```
## Post #26
- Username: Infomaniac95
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 09, 2017 7:12 am
- Post datetime: 2017-04-08T23:15:36+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

I have a few questions about this. Where are the character models located at in Estival Versus? Where are the dds texture files? How do i open these models in 3ds max?
## Post #27
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-04-09T09:56:29+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

> Reply from Infomaniac95
>
> I have a few questions about this. Where are the character models located at in Estival Versus? Where are the dds texture files? How do i open these models in 3ds max?

-Characters are separated into 3 parts: head, hair and body. Head and hair are located in the /model/playable folder. hr__ are the hairs and pl__ are the heads. Bodies are in the /model/costumes/___ folders. The 'H' and 'L' refer to the quality of the model with 'H' being the high quality version (so use that one). Characters are, for the most part, organized by number if you're looking at default costumes. So, for example, Asuka's parts are hr00 (hair), pl00_00 (head) and 00_00_H (body). Some models require bra textures from the 'bura' folder and some require panty meshes/textures from the 'swim' folder. 

-textures are extracted from the .cat files just like the meshes. 

-use quickbms and the script RTB posted above to extract the .cat files. You have to run the script on the .cat file which extracts more .cat files so keep running the script on the new files (can ignore the very small .cat files that are only a few kb in size) until you get .tmd files (these are meshes that you import in 3DS max). You'll also get .dat files during extraction. Run the .gtx quickbms script (found on the previous page) on the .dat files to get the textures. 

-run RTB's script in 3DS max, select the 'Estival Versus' option and import the tmd. 

Good luck. The tools work fine but these models take a lot of work to put together.
## Post #28
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2017-04-25T18:21:41+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

thanks for the scripts.  i got mesh and bones from estival versus.  is there a way to get animations as well?
## Post #29
- Username: asdronin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 11, 2017 1:23 pm
- Post datetime: 2017-05-11T05:33:50+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

Hi all, 
I have seen the work that you have done ripping the models and textures from this game and I think its great, well done =). I can model in 3D (average level) and I would like to check these models as how are them constructed, specially the eyes and bone structure, well many of you surely checked this for same reasons, but I find the cat script link is down and I think I cant do anything without it, right? Im new to modding scene so please keep that in mind if my question sounds too silly, could you please provide a valid link for the script? my plan is to check this in 3D Studio (main tool I use) so do I need any other script after extracting with the cat script? I have read in other thread there is script to import but the link to the one I think I need is still working just havent verified as I havent completed first step.
Thanks in advance for any help =)



Edit: All solved, sorry about trouble, I hope its ok to edit this many times, well I finally managed to import into 3d Studio with bone structure and full geometry, thank you for sharing this and posting about it I will be having a look at how they build their models, in a first look its impressive that they dont build the whole body in one mesh, surely because clothing will interfere with body in bending areas so if they put on a shirt part then of the body is removed, this is clarifying, I never thought it could be like that, more considering that clothing can be ripped but then again it means the ripped clothing  is merged with part of body or something to allow the effect to work
## Post #30
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2017-05-16T18:25:33+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

intel frame analyzer has come a long way since i last used it.  estival versus models can be ripped t-posed (IA) and posed (VS) and it also works for a few other games i tried.  it can't do VS for DX9, but DX10 and DX11 should work for most games.  DX12 captures way too much data to sort through, and i couldn't find VS in rise of the tomb raider, but switching back to DX11 makes VS available in ROTTR.



to get the posed model below was a bit of a hassle but not too bad overall.  had to piece it together, then import it into old blender and run correct3dripper.py to get rid of the skew and level it.
for me, it works out great, but there might be some other useful data that can be extracted (textures for sure) for people wanting t-posed models.
## Post #31
- Username: Just4TheModels
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 07, 2017 7:58 pm
- Post datetime: 2017-06-07T12:12:57+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

Sorry I'm a bit of an idiot..
I been trying to figure this all out for a while and managed to extract .DAT & .TMD using
QuickBMS& TamsoftSKEV_CAT then QuickBMS& Tamsoft_GXT on the .DAT but it always says;

'Error: Incomplete input file 0: C:\Users\Just4TheModels\Desktop\NewFolder\pl28_00_L_0\pl28_00_L_0_0.dat
Can't read 4 bytes from offset 0000000c.
Anyway don't worry, it's possible that the BMS script has been written to exit in this way if it's reached the end of the archive so check it or contact its author or verify all the files have been extracted.
Please check the following coverage information to know if it's ok.
Coverage file 0 100% 12 12 .offset 0000000c

Last script line before the error or that produced the error: 9 get FILESIZE long:

And theres nothing there; I've absolutely no idea on what to do
Please help if possible, thanks for reading
## Post #32
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-06-08T00:01:08+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

I'm not on my home PC and haven't messed with these models in a while but I'll try to help. I'm assuming you're doing all this with the Estival Versus models and not the outdated Shinovi Versus models. 

First of all, from the error you gave, you seem to be using the low quality models/textures. You should be using the models that have "H" instead of "L" in the filenames. I only messed with the "H" models and had no issues so there could be problems using the "L" models. 

Next, make sure you are using the latest (or at least a fairly recent version of) quickbms and the scripts linked earlier in the thread. 

Okay, if those aren't the problem lets make sure you're extracting properly. After extracting the initial .cat file you get more .cat files (and so on) until you're in a folder looking at a .TMD and .DAT file right? That .DAT file isn't the textures for the model. The .dat files with textures are extracted into separate folders from the model (but from the same initial .cat file). Run the gtx script on THOSE .dat files for textures. 

If this doesn't help you can upload whatever model it is that you're working with and I'll try to help figure out the issue.
## Post #33
- Username: Just4TheModels
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 07, 2017 7:58 pm
- Post datetime: 2017-06-08T09:05:16+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

> Reply from ssringo
>
> I'm not on my home PC and haven't messed with these models in a while but I'll try to help. I'm assuming you're doing all this with the Estival Versus models and not the outdated Shinovi Versus models. 

First of all, from the error you gave, you seem to be using the low quality models/textures. You should be using the models that have "H" instead of "L" in the filenames. I only messed with the "H" models and had no issues so there could be problems using the "L" models. 

Next, make sure you are using the latest (or at least a fairly recent version of) quickbms and the scripts linked earlier in the thread. 

Okay, if those aren't the problem lets make sure you're extracting properly. After extracting the initial .cat file you get more .cat files (and so on) until you're in a folder looking at a .TMD and .DAT file right? That .DAT file isn't the textures for the model. The .dat files with textures are extracted into separate folders from the model (but from the same initial .cat file). Run the gtx script on THOSE .dat files for textures. 

If this doesn't help you can upload whatever model it is that you're working with and I'll try to help figure out the issue.

Thank you so much for the fast and helpful response; it is greatly appreciated!
You're right; I'm attempting to extract from Estival Versus & I tried to use the H models (and again just now) and extracted them all until I ended up with only TMD & DAT + DAT&DAT in every other folder ( I tried to extract DAT into a new folder incase it was a naming issue but still didn't work : ( )

The versions I am using are: BMS0.8, TamsoftGXT from the previous page, SKEV_CAT & TPK from Randomtalkingbush's list of scripts (ty for all the models and scripts btw! absolutely love what you've done)

I also just tried to extract all the .DAT at once (was individual and then in 2s at first) but now it says 'impossible to write 0xfffffff0 bytes (total 0xfffffff0) check your disk space (i've 100gb) Last script line before the error or that produced the error 29 log name fileoffset fileend' and leaves me with 1 0byte DDS file 00_00_H_0_0

Thanks again for your wonderful help!

--

Oh wait, i think its working now; I extracted the .DAT with bigger file sizes and got some textures
## Post #34
- Username: Lotus06
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 20, 2022 4:12 pm
- Post datetime: 2022-09-21T02:06:43+00:00
- Post Title: Re: Senran Kagura Shinovi Versus (PC)

> Reply from RandomTBush ↑Sun Apr 02, 2017 11:33 am at Sun Apr 02, 2017 11:33 am
>
> 
Might as well mention that I've updated the script now.
https://mega.nz/#!ulpnmaJS!ffrdVu0T81lK ... 8Ac8hYL6FM
Code: Select allAdded support for Senran Kagura: Estival Versus (both Vita and PC versions).
Changed bone numbers to bone checksums instead.
Added a ton of replacement bone names to replace the checksums, don't expect hair bones (especially SK's) to be named correctly.
Optimized polygon group importing a bit so things will load a bit faster.
Fixed rigging being broken in one way or another for newer 3DS Max versions.

(EDIT: Here's mikulover39's QuickBMS scripts for the .CAT archives in Estival Versus, hope it's alright that I'm sharing them here.)

(EDIT 2: Updated the script again.)
Code: Select allFixed models with over 65535 vertex points not importing.
Fixed models with three UV mapping layers not importing correctly.
Hello sorry for necro posting but I’d appreciate your help 
We’re currently trying to access the .tpk files for Senran Kagura Estival Versus for PS4 but all the .tpks are compressed. we don’t know what compression was used on it. We cannot edit anything until the tpk files are decompressed. Can you please identify what compression was used and how to decompress it? This is just a portion of the .tpk files for examination. Thank you so much 

[https://drive.google.com/file/d/1TL4Vwv ... p=drivesdk](https://drive.google.com/file/d/1TL4Vwv0YCI58y1qPu0f5VEJ1HIiAVqai/view?usp=drivesdk)
