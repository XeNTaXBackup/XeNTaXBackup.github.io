## Post #1
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2014-05-03T05:54:16+00:00
- Post Title: Survarium models (from the makers of STALKER)

Thanks to the BMS script from aluigi, the archives for Survarium can be unpacked. (as seen in this thread: [viewtopic.php?f=10&t=11424](http://forum.xentax.com/viewtopic.php?f=10&t=11424))

The textures unpack in perfectly normal dds format. The models, on the other hand, do not have file extensions and I'm unable to detect the file types in my very limited understanding of hex. 

Sample of models here: [https://www.mediafire.com/?ar87s7xt2f7l05i](https://www.mediafire.com/?ar87s7xt2f7l05i)

Is anyone is able to look at this file format and make any sense of it?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-03T10:51:08+00:00
- Post Title: Survarium models (from the makers of STALKER)

using hex2obj (view link in my sig):



boot.JPG (73.61 KiB) Viewed 1596 times



The model file is converted_model in the subfolder
base_character_boot.skinned_model\render\base_character_boot_s

Due to a bug in hex2obj converted_model has to be renamed to converted_model.mdl for example
before loading the model.

This is only required because there is an unusual '.' contained in the subfolder name.

For the model in base_character_torso_s1.skinned_model\render\base_character_torso_s
the H2O file is like this:
0x9D08 4146
Vb1
48 40
0xC 837
020000
0x0 255
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-05-03T11:58:10+00:00
- Post Title: Survarium models (from the makers of STALKER)

Hi Dragbody! 
If no one will do it faster I'll post maxscript soon. Format looks quite basic, maybe I'll ask you for more samples later.
[sur.jpg](https://xentaxbackup.github.io/file/7293_sur.jpg)
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-05-05T07:01:14+00:00
- Post Title: Survarium models (from the makers of STALKER)

So, here's maxscript to import Survarium PC models with bones+weights (3ds max 2009-2012)

Instruction:
1) Run script, it will ask you to load file "export_properties" (stores important info), import this file from same folder where model file "converted_model" located.
2:) Hardest part   Locate file "bind_pose" (bone file) And import it! It's not hard, but someone may have problems with it, since this file stored not in each model folder+for all chars in different location 
For Example -"character\human\base\base_character_boot.skinned_model\render\bind_pose" Skeleton for base male models
3:) Script will ask you to load "converted_model" do it. 
And Done! Result:

[](http://piccy.info/view3/6337486/5678ad81cc12a1a29dea7361bff79a3f/1200/)[](http://i.piccy.info/a3c/2014-05-05-07-00/i9-6337486/744x574-r)
[Survarium.7z](https://xentaxbackup.github.io/file/7300_Survarium.7z)
## Post #5
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2014-07-22T04:31:54+00:00
- Post Title: Survarium models (from the makers of STALKER)

Hi zaramot,

Thank you once again for the work here. If you have time and it's not too much trouble, I wonder if you would be able to look at this script one more time. It does not work when importing most of the headgear (though for everything else it works perfectly). It wasn't worth mentioning before but the game has just been updated with lots of great new content. 

Thanks!
## Post #6
- Username: ShooRuP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 03, 2014 1:08 am
- Post datetime: 2014-08-02T19:33:00+00:00
- Post Title: Survarium models (from the makers of STALKER)

> Reply from zaramot
>
> So, here's maxscript to import Survarium PC models with bones+weights (3ds max 2009-2012)

Instruction:
1) Run script, it will ask you to load file "export_properties" (stores important info), import this file from same folder where model file "converted_model" located.
2:) Hardest part   Locate file "bind_pose" (bone file) And import it! It's not hard, but someone may have problems with it, since this file stored not in each model folder+for all chars in different location 
For Example -"character\human\base\base_character_boot.skinned_model\render\bind_pose" Skeleton for base male models
3:) Script will ask you to load "converted_model" do it. 
And Done! Result:

Hi! And opening the weapon models? Tell me please
## Post #7
- Username: WarLeader
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 05, 2014 8:26 pm
- Post datetime: 2014-08-05T16:46:05+00:00
- Post Title: Survarium models (from the makers of STALKER)

Hey, what about another models from game, vehicles, weapons, etc?
## Post #8
- Username: ShooRuP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 03, 2014 1:08 am
- Post datetime: 2014-08-06T08:25:24+00:00
- Post Title: Survarium models (from the makers of STALKER)

> Reply from WarLeader
>
> Hey, what about another models from game, vehicles, weapons, etc?
I too am waiting when it will be open
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-13T09:29:48+00:00
- Post Title: Survarium models (from the makers of STALKER)

Updated for headgear support
[Survarium.7z](https://xentaxbackup.github.io/file/7925_Survarium.7z)
## Post #10
- Username: lafugix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 22, 2011 1:12 am
- Post datetime: 2014-10-14T11:15:18+00:00
- Post Title: Survarium models (from the makers of STALKER)

zaramot, your script works perfectly with 0.24 update models (not just the character modelsbut also weapons), but in the 0.25 update again made ​​changes to the format models. You can see the changes and update the script?
[scavengers_01_torso_s1.skinned_model.7z](https://xentaxbackup.github.io/file/7937_scavengers_01_torso_s1.skinned_model.7z)
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-14T13:35:15+00:00
- Post Title: Survarium models (from the makers of STALKER)

These files are not properly extracted  I'm sure they changed something in new patch, you should contact Aluigi and ask him to update BMS
## Post #12
- Username: lafugix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 22, 2011 1:12 am
- Post datetime: 2014-10-14T14:03:26+00:00
- Post Title: Survarium models (from the makers of STALKER)

zaramot, Thank you for explaining the problem, i asked him in a PM
## Post #13
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2014-10-14T18:08:23+00:00
- Post Title: Survarium models (from the makers of STALKER)

Oh wow. Big update just four days ago! The model format had not changed in several updates so I would be surprised if they changed it now. 

I did also notice that the latest model script works for the weapons too. This was a great bonus 

Aluigi was great in quickly writing the first script. It would be great if he comes through again!
## Post #14
- Username: SanekED
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 01, 2014 5:58 pm
- Post datetime: 2014-10-15T14:36:18+00:00
- Post Title: Survarium models (from the makers of STALKER)

Justa a quick todays test: [http://4put.ru/pictures/max/1002/3078152.jpg](http://4put.ru/pictures/max/1002/3078152.jpg) script works great.
## Post #15
- Username: lafugix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 22, 2011 1:12 am
- Post datetime: 2014-10-17T00:31:36+00:00
- Post Title: Survarium models (from the makers of STALKER)

Yes, aluigi's script works perfectly, it had problems with my unpacker. Sorry for disturb
[](http://imageshack.com/a/img911/9202/hJhSZe.jpg)
## Post #16
- Username: WarLeader
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 05, 2014 8:26 pm
- Post datetime: 2014-11-07T20:34:37+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hey, what about another model?
## Post #17
- Username: gonard
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 01, 2014 7:30 pm
- Post datetime: 2014-12-01T13:38:13+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Who can import Ash-12 weapon model?
## Post #18
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2014-12-10T20:05:50+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Today downloaded the game, and the new version comes out when you try to convert the error:
"unable to convert: undefined to type: float"
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-12-10T21:02:58+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Post samples or send them to me via PM
## Post #20
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2014-12-11T03:32:22+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from zaramot
>
> Post samples or send them to me via PM
example v 0.25d
[http://www.mediafire.com/download/nn3ox ... .12.14.rar](http://www.mediafire.com/download/nn3ox6p1nc4gc02/base_11.12.14.rar)
## Post #21
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2014-12-11T17:56:05+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

example v 0.26a (test)
base character and ash-12 weapon - [http://www.mediafire.com/download/rlc99 ... %2C26a.rar](http://www.mediafire.com/download/rlc99cf9uqsf9mz/example_0%2C26a.rar)
## Post #22
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-12-11T18:12:57+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I checked all samples and I must tell, that they changed something in new patch again, in the archive part, so you should again contact Aluigi and ask him to update his BMS script
## Post #23
- Username: lafugix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 22, 2011 1:12 am
- Post datetime: 2014-12-13T21:43:35+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

But...
[](http://i.imgur.com/gPm73xU.png) [](http://imgur.com/reQiXu2.png)
## Post #24
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2014-12-14T04:34:26+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from lafugix
>
> But...

It'S Great!
You can lay out a script that you do it?
## Post #25
- Username: lafugix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 22, 2011 1:12 am
- Post datetime: 2014-12-14T05:02:27+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Ruyan, i use the same aluigi's script, i don't know what your problem
## Post #26
- Username: SanekED
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 01, 2014 5:58 pm
- Post datetime: 2014-12-21T15:29:25+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I can upload all weapon models in a .obj if someone need it. 0.26 models also included.
## Post #27
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2014-12-22T15:10:12+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from SanekED
>
> I can upload all weapon models in a .obj if someone need it. 0.26 models also included.

I would be very grateful if you do that.
I did not go out to convert the model ....
## Post #28
- Username: captainluckasy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 14, 2014 1:55 am
- Post datetime: 2014-12-22T16:54:12+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from SanekED
>
> I can upload all weapon models in a .obj if someone need it. 0.26 models also included.
I know you are from GOST     but how to import animations
## Post #29
- Username: SanekED
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 01, 2014 5:58 pm
- Post datetime: 2014-12-28T18:32:10+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

So here is a models only [https://www.sendspace.com/file/2vgj6d](https://www.sendspace.com/file/2vgj6d) 

P.S.Textures not included.
## Post #30
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2014-12-30T19:57:29+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from SanekED
>
> So here is a models only https://www.sendspace.com/file/2vgj6d 

P.S.Textures not included.

Thank U.
No more Do you have any of these models in the format .max or .fbx, were integral to the bone. At the moment, all the elements in a single object. So as models do not have the materials, but most have 2 textures ...
## Post #31
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2015-03-21T14:08:18+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Can anyone convert Pecheneg machine gun?
## Post #32
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-21T18:31:03+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

can i also get other models then just guns and chars ?
## Post #33
- Username: yarresh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 08, 2014 2:27 am
- Post datetime: 2015-04-27T18:14:18+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hi, guys!

I tried to run script that zaramot posted, but got some error:
"unable to convert undefined to type string" on 73 line of code.
I unpacked resource files from 0.28a version of game, and also tried to open old models too. Doesn't matter - i got an error.
I have 2009 3dsMax.

Can anybody help me, please?
[asd.jpg](https://xentaxbackup.github.io/file/9115_asd.jpg)
## Post #34
- Username: velfr13666
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 27, 2015 1:50 pm
- Post datetime: 2015-05-02T14:33:41+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Same as yarresh said, MAX 2012.
## Post #35
- Username: talwados
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 04, 2015 4:28 pm
- Post datetime: 2015-07-06T05:33:02+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hey guys, i unpacked the current game files (0.29c), and managed open the models with Zaramot script, but the models doesnt look right, and they missing the textures. (note on that, i dont have much experience with 3dmax and maybe i just missing something)


Loaded in models looks like this; 
[http://imgur.com/LLC7sHn](http://imgur.com/LLC7sHn)

is the bms or the Zaramot scipt is outdated, or i just missing something obvious? 
i attached the m4 model as a sample
[m4a1.rar](https://xentaxbackup.github.io/file/9395_m4a1.rar)
## Post #36
- Username: WarLeader
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 05, 2014 8:26 pm
- Post datetime: 2015-07-09T12:26:41+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

UP
## Post #37
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-07-23T12:02:18+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Marvellous. I downoaded the game just yesterday and it worked with everything i tried, so i suppose both the extracton and model import scripts are in order.
Has anyone found out which bind_pose is necessary for the optical attachments?
## Post #38
- Username: Gioconda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 25, 2015 11:37 pm
- Post datetime: 2015-07-27T20:58:34+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Good evening colleagues. I am the main developer of the mod Metro Lost Faith [http://www.moddb.com/mods/metro-lost-faith-mod](http://www.moddb.com/mods/metro-lost-faith-mod) . And I want to add to your fashion new 3D model of the game Survarium (attached below screenshots)
[https://eu.survarium.com/sites/default/ ... ran-en.jpg](https://eu.survarium.com/sites/default/files/wp/black-market-veteran-en.jpg)
[https://eu.survarium.com/sites/default/ ... oon-en.jpg](https://eu.survarium.com/sites/default/files/wp/black-market-goon-en.jpg)
[https://eu.survarium.com/sites/default/ ... ter-en.jpg](https://eu.survarium.com/sites/default/files/wp/black-market-fighter-en.jpg)
[https://eu.survarium.com/sites/default/ ... hunter.jpg](https://eu.survarium.com/sites/default/files/wp/survariumwallpaperartifacthunter.jpg)
[https://eu.survarium.com/sites/default/ ... ewbies.jpg](https://eu.survarium.com/sites/default/files/wp/survariumwallpaperscavengernewbies.jpg)
[https://eu.survarium.com/sites/default/ ... rksman.jpg](https://eu.survarium.com/sites/default/files/wp/survariumwallpaperscavengerscavengermarksman.jpg)
[https://eu.survarium.com/sites/default/ ... per_22.jpg](https://eu.survarium.com/sites/default/files/wp/wallpaper_22.jpg)
And I have a big request to you, who will be able to load my model (skins, hats, Armor, helmet) and texture? It is desirable in the format Obj. Many thanks in advance.

Yours faithfully Gioconda.
## Post #39
- Username: Murdock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 17, 2015 7:59 am
- Post datetime: 2015-09-11T13:15:28+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hey, hopefully there is someone here who can help me. 
The script from zaramot requires bone files (bind_pose). But I would like to import models without the bones. 
So I wanted to ask if someone knows how I have to edit his script so it doesn't require those bone files.
## Post #40
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-12T17:37:53+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Script to import models without bones (no bind_pose)

Below
## Post #41
- Username: Murdock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 17, 2015 7:59 am
- Post datetime: 2015-09-13T11:18:33+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

hey zaramot, thanks alot for the edited script! 
But it does not work for me... When I try to import the PSO-1 for example, nothing happens. I get no error message, no model or whatsoever. I can get the models which I could also get with your original script and now without importing the bones. But the attachments, grenades and other stuff do not work. 
I tried 3ds max 2010 and 2012. 
Could you maybe take a look at this?
## Post #42
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-13T19:04:55+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Sure, attach some not working files here
## Post #43
- Username: Murdock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 17, 2015 7:59 am
- Post datetime: 2015-09-13T20:31:23+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hey, these are attachments and grenades that do not work. I think props also don't work. 
Thanks for your time!
[Survarium attach.7z](https://xentaxbackup.github.io/file/9734_Survarium attach.7z)
## Post #44
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-14T07:00:06+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Test this one, but should work correct


[Survarium_no_bones_fix.7z](https://xentaxbackup.github.io/file/9735_Survarium_no_bones_fix.7z)
## Post #45
- Username: Murdock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 17, 2015 7:59 am
- Post datetime: 2015-09-14T10:39:33+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Yep, now it works! 
Thanks alot, really appreciated!
## Post #46
- Username: yarresh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 08, 2014 2:27 am
- Post datetime: 2015-09-20T14:28:04+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hi to everyone!
I have tried to open models from levels, and got an error. Look at the screenshots.
(for example with models\level\03\arsenal.model\render\stucco_cement_burn_s_vc).
Can anybody help me, please?
## Post #47
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-20T17:21:40+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Well, maxscript is for characters/weapons/ now for props  - I never had samples of levels, so most likely they will not work in many cases xD
## Post #48
- Username: borovos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 22, 2015 1:16 am
- Post datetime: 2015-11-21T17:23:00+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hello Zaramot,

Few guys from gameru.net forum are working on GSC's resources (source code) for Stalker 2. They started the Stalker 2 SDK few days ago. 
It seems than Survarium code is the same as in Stalker 2 archive.

I don't know but maybe some data can help you about your converter.

Please, can you edit your script to open static object? A lot of object from level design are really fine.

Thanks
## Post #49
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-21T17:33:25+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I don't have the game, so I can't test static object files. But if someone provide them, I'll take a look
## Post #50
- Username: borovos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 22, 2015 1:16 am
- Post datetime: 2015-11-21T18:16:33+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I didn't start survarium since months, so update is in progress. I'll upload few files asap.

Thanks
## Post #51
- Username: borovos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 22, 2015 1:16 am
- Post datetime: 2015-11-22T19:07:41+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

For testing, one example of background building, files from models/level/04 folder:
[https://dl.dropboxusercontent.com/u/325 ... zaramot.7z](https://dl.dropboxusercontent.com/u/32595810/for_zaramot.7z)

If you want something, tell me.
## Post #52
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-22T19:59:40+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Okay, thanks I'll take a look
## Post #53
- Username: lovepsone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 05, 2014 9:35 pm
- Post datetime: 2016-08-05T08:15:57+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hello! Somebody tried to import the animation?
## Post #54
- Username: zeyd6796
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 27, 2016 11:54 pm
- Post datetime: 2016-09-27T16:32:06+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I am new at this work. Are the tools are still working correctly? I have tried several times but I could not extract the "MP5 A1/A3" from v0.44b.

Edit// Anyway, thank you for your great works guys. I can use some old data as samples/examples.
## Post #55
- Username: player147proman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 09, 2016 8:14 am
- Post datetime: 2017-04-02T13:04:25+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I hate to revive a dead topic but is there plans on updating the 3ds max script, after the latest update, I can't specific models like the glock 17 for example.
## Post #56
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2017-05-14T10:22:21+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from zaramot
>
> I don't have the game, so I can't test static object files. But if someone provide them, I'll take a look
Hi, here is sample of file which cannot be imported/exported. If you can take a look. It's from latest build.

Thanks!
[supressor_sr3m_s.7z](https://xentaxbackup.github.io/file/12883_supressor_sr3m_s.7z)
## Post #57
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2017-12-01T13:43:46+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

The main weapon files still work for me, it's once again the attachments that make problems.
For some i get an "no + function for undefined" error(line 394), but most of the time it would import an object without any vertices whatsoever.
I'd really appreciate if you could look into that, i've provided an example of both types of errors.

[https://en.file-upload.net/download-128 ... v.rar.html](https://en.file-upload.net/download-12843783/Surv.rar.html)
## Post #58
- Username: synthosc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 06, 2017 5:59 am
- Post datetime: 2017-12-11T15:21:55+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

is extracting maps yet buggy? like models coming out with uv errors or models broken?
## Post #59
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-11T17:44:21+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from synthosc
>
> is extracting maps yet buggy? like models coming out with uv errors or models broken?

No one actually looked at maps yet. I didn't have any samples of them, just weapons/characters. So, I bet they wouldn't work
## Post #60
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2017-12-16T18:37:35+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Bumping it up. There area lot of new models after update, but very few can be imported using old scripts. It would be great if someone find solution for this.
## Post #61
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-16T21:48:51+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Should update the script then. It was a big update?
## Post #62
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2017-12-17T09:48:09+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Probably big. Even folders tree are changed. Now weapons are sorted in categories like assault, pistols, sniper, etc. I don't play this game, I'm only looking for a models to port them to Stalker. I'm not sure but it looks like the export_properties files are built different now.

Here is whole weapons models folder: [http://www.mediafire.com/file/d3i8w6g74 ... weapons.7z](http://www.mediafire.com/file/d3i8w6g740ew8e9/weapons.7z)
## Post #63
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2017-12-30T19:37:49+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Sometimes this error appears:

```
"Vertex End @ 0xcL"
-- Error occurred in x loop; filename: C:\Program Files\Autodesk\3ds Max 2012\scripts\Survarium_Static.ms; position: 9256; line: 394
--  Frame:
--   f3: undefined
--   x: 2646
--   f1: 16026
--   f2: undefined
-- Error occurred during fileIn in #C:\Program Files\Autodesk\3ds Max 2012\scripts\Survarium_Static.ms; line number: 394
--   called in execute(); filename: C:\Program Files\Autodesk\3ds Max 2012\scripts\Survarium_Static.ms; position: 9323; line: 397
--  Frame:
--   called in anonymous codeblock
--  Frame:
>> MAXScript MacroScript Error Exception:
-- No ""+"" function for undefined <<
```

and sometimes there is no error, just invisible object without any vertices, faces, etc.
## Post #64
- Username: vaseker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 06, 2016 1:21 pm
- Post datetime: 2018-01-05T14:08:59+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from zaramot
>
> Should update the script then. It was a big update?
Yes it is.
Current version of game have updated weapons modules system, new game mode and level, and possible big updates in level encoding.

Also again updated options file encoding, my tool [https://github.com/survarium/survarium- ... er/decoder](https://github.com/survarium/survarium-tools/tree/master/decoder) unable to convert few non- important files. (In weapon options files should be positions of weapon modules bind points)


Did you tried to decode level geometry?
## Post #65
- Username: RedMiller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 10, 2017 12:19 am
- Post datetime: 2018-01-23T16:42:16+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)


## Post #66
- Username: RedMiller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 10, 2017 12:19 am
- Post datetime: 2018-01-23T16:54:25+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Tool for viewing and saving models in .fbx.

[https://mega.nz/#!mZpFRIDb!jkZHJxvFc4iL ... -EVm3vGqwg](https://mega.nz/#!mZpFRIDb!jkZHJxvFc4iL2NQW8D8yxkbrTyNgTDLlI-EVm3vGqwg)
## Post #67
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2018-01-25T17:00:50+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from RedMiller
>
> Tool for viewing and saving models in .fbx.

https://mega.nz/#!mZpFRIDb!jkZHJxvFc4iL ... -EVm3vGqwg

Could you tell me how to use this tool？
## Post #68
- Username: RedMiller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 10, 2017 12:19 am
- Post datetime: 2018-01-25T18:48:40+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from WPH93
>
> 

Could you tell me how to use this tool？

1) Run vetool.exe
2) File - > Open
3) Find folders named .model
4) Select folder and open
5) Save this model to .fbx
## Post #69
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2018-01-26T10:15:15+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from RedMiller
>
> WPH93 wrote:

Could you tell me how to use this tool？

1) Run vetool.exe
2) File - > Open
3) Find folders named .model
4) Select folder and open
5) Save this model to .fbx
Thx，bro:p
## Post #70
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2018-01-27T17:09:26+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from RedMiller
>
> Tool for viewing and saving models in .fbx.

https://mega.nz/#!mZpFRIDb!jkZHJxvFc4iL ... -EVm3vGqwg

Great, but unfortunately it doesn't work with .skinned_model files 

EDIT - but it's sufficient to export all models incompatible with zaramot's scripts
## Post #71
- Username: RedMiller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 10, 2017 12:19 am
- Post datetime: 2018-01-27T20:42:26+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

[https://youtu.be/DFzzJcVLZA0](https://youtu.be/DFzzJcVLZA0)
## Post #72
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2018-01-28T19:42:34+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Another discovery: the .model folder along with render folder has to contain settings file, otherwise vetool doesnt import anything. I had this with aks74u muzzle. But you can simply copy settings file from another muzzle model (ak74 i.e.) and it will work.
## Post #73
- Username: parysek123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 12, 2018 8:04 am
- Post datetime: 2018-09-12T19:07:11+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hi guys,
I downloaded a pack of all guns but MSBS model is missing.
Also i tried to unpack it with RedMiller script but it doesnt work.
I have MSBS textures but the model is needed   
Can someone tell me how to extract it?
Thanks
## Post #74
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2018-10-07T11:27:47+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Hello everyone in this thread!
Now Survarium has version 0.54 [https://survarium.com/en/news/survarium ... e-play-now](https://survarium.com/en/news/survarium-patch-054-live-play-now). 
I tried to pull character and weapons models from the game into 3ds max 2010. Unpacker from aluigi still works, but when I try to open the unpacked models in 3ds max 2010 by script of zaramot, I get an error. Could you tell me how to fix this error?

After recent updates of Survarium, a module system for weapons was introduced. There is a separate folder in the game resources for modules, and vetool from RedMiller does not display (and save in fbx) modules meshes, although still perfectly displays and seves meshes of old weapons. In addition, vetool from RedMiller does not correctly display character models, they have completely broken UVW coordinates for texture.
[3ds max 2010 Error.jpg](https://xentaxbackup.github.io/file/14981_3ds max 2010 Error.jpg)
## Post #75
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-10-07T14:23:05+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Script needs an update, but I guess vetool will be updated faster xD Also, maybe bms script extracting files not correctly, I mean from latest update (you should upload some not working models)
## Post #76
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2018-10-07T15:59:32+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Here is an example of the files that make error of the script for 3ds max.
[Files from Survrium 0.54.zip](https://xentaxbackup.github.io/file/14982_Files from Survrium 0.54.zip)
## Post #77
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2018-10-07T16:26:40+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Here is an example of modules for weapons, which are not displayed and not saved using vetool from RedMiller.
There are a magazines for example, but the same goes for the other modules for weapons.
[modules from Survrium 0.54.zip](https://xentaxbackup.github.io/file/14983_modules from Survrium 0.54.zip)
## Post #78
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2018-10-07T17:05:56+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

An example of files, which displayed and saved by vetool from RedMiller with incorrect UVW coordinates for texture.
[Example of broken UVW in vetool.zip](https://xentaxbackup.github.io/file/14984_Example of broken UVW in vetool.zip)
## Post #79
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2018-11-03T08:28:14+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

I am very sorry that this topic is dead   In any case, many thanks to this site and to all of you, for your work and for your stuff. Thank you very much!
## Post #80
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-11-04T19:37:19+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

Format is quite easy. I already have all weapons/modules converted to *.obj with my 010 HEX Editor Template. But... it has some fails like missing vertex normals because i don't know how to read/print them.

Here is sruct for static meshes without bones.

```
int VBSize;
int VertexCount;

struct VTXBLOCK {

for (i=0;i<VertexCount;i++)

struct VTX {
        float VX;
        float VY;
        float VZ;
struct VTN {
        hfloat UNK0;
        float UNK1;
        float UNK2;
struct UV {
        hfloat VTU;
        hfloat VTV;
            }unitvector;
        }vertexnormal;
    }vertices;
}vtxblock;
```
## Post #81
- Username: Antnigm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 03, 2015 5:59 pm
- Post datetime: 2019-03-04T19:19:48+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from GRiNDERKILLER ↑Mon Nov 05, 2018 3:37 am at Mon Nov 05, 2018 3:37 am
>
> 
Format is quite easy. I already have all weapons/modules converted to *.obj with my 010 HEX Editor Template. But... it has some fails like missing vertex normals because i don't know how to read/print them.
Here is sruct for static meshes without bones.
Can you make a short tutorial of converting with 010 HEX Editor for beginners? I think many people will be grateful.
## Post #82
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2019-04-09T06:16:55+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from GRiNDERKILLER ↑Mon Nov 05, 2018 3:37 am at Mon Nov 05, 2018 3:37 am
>
> 
Format is quite easy. I already have all weapons/modules converted to *.obj with my 010 HEX Editor Template. But... it has some fails like missing vertex normals because i don't know how to read/print them.

Here is sruct for static meshes without bones.
Code: Select allint vertID;
int VBSize;
int VertexCount;

struct VTXBLOCK {

for (i=0;i<VertexCount;i++)

struct VTX {
        float VX;
        float VY;
        float VZ;
struct VTN {
        hfloat UNK0;
        float UNK1;
        float UNK2;
struct UV {
        hfloat VTU;
        hfloat VTV;
            }unitvector;
        }vertexnormal;
    }vertices;
}vtxblock;

When I execute template I get this:
ERROR Line 19: Variable 'i' is undefined
## Post #83
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2019-05-25T17:19:17+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from rpopulik ↑Tue Apr 09, 2019 2:16 pm at Tue Apr 09, 2019 2:16 pm
>
> 
GRiNDERKILLER wrote: ↑Mon Nov 05, 2018 3:37 am
Format is quite easy. I already have all weapons/modules converted to *.obj with my 010 HEX Editor Template. But... it has some fails like missing vertex normals because i don't know how to read/print them.

Here is sruct for static meshes without bones.
Code: Select allint vertID;
int VBSize;
int VertexCount;

struct VTXBLOCK {

for (i=0;i<VertexCount;i++)

struct VTX {
        float VX;
        float VY;
        float VZ;
struct VTN {
        hfloat UNK0;
        float UNK1;
        float UNK2;
struct UV {
        hfloat VTU;
        hfloat VTV;
            }unitvector;
        }vertexnormal;
    }vertices;
}vtxblock;


When I execute template I get this:
ERROR Line 19: Variable 'i' is undefined

Add on first line
local int i;
## Post #84
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2019-05-28T18:30:38+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from GRiNDERKILLER ↑Sun May 26, 2019 1:19 am at Sun May 26, 2019 1:19 am
>
> 
Add on first line
local int i;

Ok. Template executed succesfully. But what next ? Where is obj file ? Or should I save as obj opened converted model ?
## Post #85
- Username: mortany
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 12, 2019 8:28 pm
- Post datetime: 2019-12-31T03:14:38+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

updated script ( 0.59b0 ), maybe working with latest versions
edit: updated it again, now mesh importing with normal vectors from model 
download link : [https://yadi.sk/d/YdECOSb5_OdrIw](https://yadi.sk/d/YdECOSb5_OdrIw)
## Post #86
- Username: Keksolom
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 22, 2016 8:34 am
- Post datetime: 2022-02-08T09:26:59+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

> Reply from RedMiller ↑Wed Jan 24, 2018 12:54 am at Wed Jan 24, 2018 12:54 am
>
> 
Tool for viewing and saving models in .fbx.

https://mega.nz/#!mZpFRIDb!jkZHJxvFc4iL ... -EVm3vGqwg

File not found.   
Survarium will be shut down at the end of May ...
## Post #87
- Username: sergeygovno
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 05, 2022 9:50 pm
- Post datetime: 2022-08-06T17:53:25+00:00
- Post Title: Re: Survarium models (from the makers of STALKER)

try "vetool" on the enternet
