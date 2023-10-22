## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-13T23:45:30+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

I'm sharing my mostly complete but still very much a WIP MaxScript (well, set of scripts) to load Persona 5's (and P4D) animations and models.

Progress log:

13/10/2016: Version 0.8 released
- Initial release
14/10/2016: Version 0.8.1 released
- Fixed typos, issues with declaration order and other oversights due to Max not clearing its own memory properly
- Improved consistency between files
Features:

Proper loading of meshes and materials (additional info in the listener window)
Rigging is applied
Weapon, character and level models are supported and..
Level textures are converted from their custom format into DDS (this requires you to keep the original folder structure intact)
Partial animation support. For now it only loads the first animation in a .GAP file. Sometimes GMD files also contain animations but those will be skipped.
Some MaxScript code you might find useful if you're into developing scripts yourself
Also loads models from Persona 4 Dancing All Night, but does not yet support loading the faces (p5 doesn't use them)
Current issues:

Some models are displaced, and I cannot find the reason as to why. Be sure to check your models thoroughly! If you have any idea, please let me know.
Materials load properly but their parsing is mostly brute forced and can possibly break. Figuring these out has proven to be quite difficult. Again help would be appreciated.
Some models don't load because of embedded particles (most of the enemies in p5). I don't know how to parse these, so until then models containing these will not load.
Rare bug that causes garbage face data to appear, I'm not sure as to why this happens.
Due to use of FileIn to seperate code, the script will now no longer work when run in the editor (Evaluate All). 
In fact, it will completely corrupt 3ds Max's MaxScript memory. Thanks Autodesk
Important notes:
This script is developed for 3ds Max 2016. If you have any issues other than the ones listed above, please make sure you're using this version. I do not intend to support older versions of Max as anyone can get a free download of the latest one and quite a few MaxScript features are blatantly broken in them.
Oh yeah, please retain the folder structure, otherwise the script won't work. All files are needed.

Special Thanks

Atlus for finally (Winter 2014 *cough*) delivering Persona 5
Pan for the preload dump of p5
PolarSoda for his P4D script
mrdudesworkshop for his findings on the animation structure
Download

https://www.dropbox.com/s/tokmx2nvomlcu ... 1.zip?dl=0


 Persona 5 Model & Animation importer v0.8.1.zip
(16.94 KiB) Downloaded 269 times



I hope you enjoy these models as much as I enjoyed (and still do!) working on them.
Eventually I plan on putting custom models into the game, but until then my MaxScript will serve to help me reverse this format.

Cheers.
## Post #2
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-10-14T07:35:55+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Thanks for the release. I hope I can get this working but for now I'm getting an error in the script listener when I load a model (same for all character models)

GFSFileLoader.Load: Chunk 0x1 ver: 0x1105070 sz: 0x0 at 0x4L
GFSFileLoader.Load: GFS start marker chunk

GFSFileLoader.Load: Chunk 0x100fc ver: 0x1105070 sz: 0xb6c45 at 0x10L
	GFSFileLoader.ReadTextureList: Loading 15 textures

	GFSFileLoader.ReadTextureList: Texture "c0001_t01_face01b_low.dds" fmt 0x1 sz 0xaa80 off 0x45L
	GFSFileLoader.ReadTextureList: Writing to E:\Modeling\Persona 5\JP0005-NPJB00769_00-HDDBOOTPERSONA05_bg_1_0682bac23263ecd6e3416c91188109072b9f503f\NPJB00769\USRDIR\model\character\0001\c0001_t01_face01b_low.dds

"-- Runtime error: Struct member access requires instance: CreateWriteableFileStream"

I just installed Max 2016 (thanks for that heads up btw) so it's possible I goofed something. That long ass folder structure was just me moving the files back into the extracted pkg folder to see if it needed to be there. Same error happened when I had the extracted cpk elsewhere. 

Edit: I tried several models and all returned this error. It does load weapons and items but nothing from the character folder.
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-14T15:05:09+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Thanks for the report. I hopely have fixed the issues with the new revision. The download link has been updated.
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-10-14T16:32:37+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Yup. Ran several character models through and each seemed to load fine with correct textures, skeleton and weights. Will spend more time over the weekend playing around with stuff. Thanks for the quick update!
## Post #5
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-10-17T21:27:53+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

So over the weekend I loaded and at least looked at each model in the character folder. Each character seemed to have one model that wouldn't load which I'm guessing has to do with the issue with embedded particles as you mentioned in the OP. That aside, everything seemed to be fine. Weights looked good (had to reparent a couple leg bones to get a single, working leg bone but that's not a script issue) and textures looked fine as well. 

That aside, I do have an issue with something that I'm guessing has more to do with Max16 than your script. Exporting the models to .fbx, which should be a great format, screws up some of the UV maps. They are fine in Max and even exporting to other formats seems to keep the UV mapping correct. It's nothing major requiring massive work to fix manually, just a section or two would get separated from the main UV map and get placed somewhere else. Pretty much every model I exported had a small section on the top of their eyes out of place and a few places on the body/hair. An easy, but irritating fix. Dunno what the issue could be though.

Edit: Forgot to mention. Haven't been able to try out DLC costumes that aren't included in the main game. Haven't been able to get my hands on them.
## Post #6
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2016-10-19T14:49:20+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Thanks for the release. I hope I can get this working but for now I'm getting an error in the script listener when I load a model in character\enemy\

GFSFileLoader.ReadNode: Reading node at 0x1ed33eL
		GFSFileLoader.ReadNode: Node "rot" hash: 0xe03ec02a attachmentCount: 0 

		GFSFileLoader.ReadNode: Reading node at 0x1ed37cL
		GFSFileLoader.ReadNode: Node "Bip01" hash: 0x76946249 attachmentCount: 0 

		GFSFileLoader.ReadNode: Reading node at 0x1ed3bcL
		GFSFileLoader.ReadNode: Node "Bip01 Footsteps" hash: 0xa714e2ba attachmentCount: 1 

		GFSFileLoader.ReadNode: Attachment #1 Type: 7 
"0x1ed401L"
"-- Runtime error: 		GFSFileLoader.ReadNode: Can't handle this attachment type
"
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-23T07:13:04+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

> Reply from liuxing
>
> Thanks for the release. I hope I can get this working but for now I'm getting an error in the script listener when I load a model in character\enemy\

GFSFileLoader.ReadNode: Reading node at 0x1ed33eL
		GFSFileLoader.ReadNode: Node "rot" hash: 0xe03ec02a attachmentCount: 0 

		GFSFileLoader.ReadNode: Reading node at 0x1ed37cL
		GFSFileLoader.ReadNode: Node "Bip01" hash: 0x76946249 attachmentCount: 0 

		GFSFileLoader.ReadNode: Reading node at 0x1ed3bcL
		GFSFileLoader.ReadNode: Node "Bip01 Footsteps" hash: 0xa714e2ba attachmentCount: 1 

		GFSFileLoader.ReadNode: Attachment #1 Type: 7 
"0x1ed401L"
"-- Runtime error: 		GFSFileLoader.ReadNode: Can't handle this attachment type
"

Attachment type 7 is the type of the embedded particles, as pointed out by the OP those do not import yet.

> Reply from ssringo
>
> So over the weekend I loaded and at least looked at each model in the character folder. Each character seemed to have one model that wouldn't load which I'm guessing has to do with the issue with embedded particles as you mentioned in the OP. That aside, everything seemed to be fine. Weights looked good (had to reparent a couple leg bones to get a single, working leg bone but that's not a script issue) and textures looked fine as well. 

That aside, I do have an issue with something that I'm guessing has more to do with Max16 than your script. Exporting the models to .fbx, which should be a great format, screws up some of the UV maps. They are fine in Max and even exporting to other formats seems to keep the UV mapping correct. It's nothing major requiring massive work to fix manually, just a section or two would get separated from the main UV map and get placed somewhere else. Pretty much every model I exported had a small section on the top of their eyes out of place and a few places on the body/hair. An easy, but irritating fix. Dunno what the issue could be though.

Edit: Forgot to mention. Haven't been able to try out DLC costumes that aren't included in the main game. Haven't been able to get my hands on them.

Might have to do with the presence of multiple uv channels, not sure. I'd have to mess with that.
## Post #8
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2016-10-24T09:10:27+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Seems like P5 models have messed up bone links, any chance for that getting worked on?
## Post #9
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-10-24T16:51:14+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

I still can't get the files extracted from the cpk archives honestly.

I' only get this error after a certain point in the extraction, it doesn't get to characters or environments, and ps3.cpk is just odd, the tool doesn't even notice there anything in it.


PC is set to run things in Japanese if non-unicode, so I'm all out of ideas.

Running windows 10 to be clear.
## Post #10
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-26T16:10:52+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

> Reply from Rin
>
> Seems like P5 models have messed up bone links, any chance for that getting worked on?
There's nothing wrong with the bone links. You have to move both the limb and helper bone together to bend the limbs. They just used a weird IK setup.
## Post #11
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-10-29T14:14:02+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Is anyone able to help with the CPK extraction error at all?
## Post #12
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-11-01T21:51:53+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

> Reply from lionheartuk
>
> Is anyone able to help with the CPK extraction error at all?
It might have to do with your system locale as neither me nor others seem to get the error you're seeing.
## Post #13
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-11-02T00:01:20+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

> Reply from lionheartuk
>
> Is anyone able to help with the CPK extraction error at all?

Did you get the game directly from PSN or did you torrent a modded version? Are you using some fan created/edited tool to extract the cpk files and if so, which one? 

I can tell you that using the official files and tools straight from the source have no issues as far as extraction purposes go.

Edit: Don't see why your locale would cause issues. At least during the extraction process. If locale was an issue it should have given an error pretty much immediately. I mean, it's worth changing your locale to English (US) just to see.
## Post #14
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-11-02T15:25:52+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

> Reply from ssringo
>
> lionheartuk wrote:Is anyone able to help with the CPK extraction error at all?

Did you get the game directly from PSN or did you torrent a modded version? Are you using some fan created/edited tool to extract the cpk files and if so, which one? 

I can tell you that using the official files and tools straight from the source have no issues as far as extraction purposes go.

Edit: Don't see why your locale would cause issues. At least during the extraction process. If locale was an issue it should have given an error pretty much immediately. I mean, it's worth changing your locale to English (US) just to see.

My Locale is already set to Eng US on this machine so its not that.

I'm using the tool TGE linked me in the previous thread.
One thing I AM using though is a .bat file, because for the life of me typing the actual commands mentioned in the document.

Even when I type it exactly as the tool says, it doesn't work.

something I should mention is I deleted the PS3.cpk file, the tool read nothing at all from it anyway, so it'll suck if I find out that the other 2 files use that ps3.cpk file to get some data from and thats why I have this error.
## Post #15
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-11-02T20:49:57+00:00
- Post Title: Persona 5 Model and Animation importer v0.8.1 - MaxScript -

Sorry, mispoke about locale. Doing this from my phone do i can't look at the pc settings directly. Meant to say the setting that causes ¥ to display instead of / in the file path (as shown in your screenshot). Something something unicode. Again, don't see why it would be an issue since it didn't error out immediately. Just something that's obviously different. 

Dunno what TGE gave you to use but it's likely not what i used to extract the cpk files. If it worked for him it should work for you. I have the tool licensed from criware so it damn sure doesn't have an issue reading and extracting the format   

The copy of the game i used was downloaded straight from psn to my pc and extracted with pkg extracting tools. Dunno if or why a dump of the game would be different but yeah, it's not what i used.
## Post #16
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2016-11-26T21:46:08+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Bone links, bone rotations or something seems to be screwing up when importing the models.

It seems this problem is present in P4D and P5 models.
## Post #17
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2016-12-01T03:35:07+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Thank you so much for making this possible ;_;
btw i wasn't the one who made the p4d script, i just made the thread xD;;
simguy made the script if i'm not mistaken owo;
## Post #18
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-12-27T08:46:10+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Thank you for the script!
I was just wondering if you're still working on this. I'm still having troubles with the P4D faces that the Noesis script can't open..
## Post #19
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2017-04-16T04:47:38+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Wow finally got it working, yay! Thank you for the amazing script!
## Post #20
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-05-28T03:13:53+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Awesome job with this script.
## Post #21
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-06-08T01:35:42+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

I was wondering if anyone might know, or have put together some sort of list, listing out what environment files coincide with what ingame areas.

As sometimes I import and it appears I get 80% of an area, and other times its 100% of an area, so I'm wondering if some areas are split into several files, ie:Stores are 1 file, props are another, roads are another etc.
## Post #22
- Username: GriffinFire
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 15, 2016 6:19 am
- Post datetime: 2018-01-23T16:25:03+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Sorry if its against the rules to bump threads, but how are the node hashes calculated?
## Post #23
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2018-02-02T03:13:43+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

> Reply from GriffinFire
>
> Sorry if its against the rules to bump threads, but how are the node hashes calculated?
I'll just link you to the code from my (WIP) editor.
[https://pastebin.com/R98eRSna](https://pastebin.com/R98eRSna)
## Post #24
- Username: luiz7429
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 16, 2017 12:26 pm
- Post datetime: 2018-02-19T12:18:00+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

[https://forum.xentax.com/viewtopic.php?f=16&t=17719](https://forum.xentax.com/viewtopic.php?f=16&t=17719)
## Post #25
- Username: autolab
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 25, 2018 8:54 am
- Post datetime: 2018-11-25T12:22:42+00:00
- Post Title: Re: Persona 5 Model and Animation importer v0.8.1 - MaxScrip

Hi. 

I am trying to get the animations from Persona 4 Dance All Night and Persona 3. I'm using this script and sucessfully import the models but I can't import the animations in GAP files.
Can someone explain to me how to correctly import the GAP motions files to the GMD character?

Thanks.
