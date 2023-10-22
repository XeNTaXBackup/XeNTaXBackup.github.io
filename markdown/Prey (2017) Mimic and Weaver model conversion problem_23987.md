## Post #1
- Username: MiTriSite
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 01, 2021 9:17 pm
- Post datetime: 2021-06-01T14:44:37+00:00
- Post Title: Prey (2017) Mimic and Weaver model conversion problem

Okay, so, i've been porting various Typhon models from the unencrypted game files using CGF-converter. I've been following all instructions to the point, and models such as ones of Phantom, Nightmare, Apex etc. were converted just fine. I can open them in Blender and they more or less look like they are in-game, in other words - they are okay. But whenever i input any .skin, .chr or .cgf files of Weaver or Mimic - i get this: 


It seems to cosplay a carpet of some sort Mimic_CompletelyJinxed.JPG (33.79 KiB) Viewed 78 times


As you probably have guessed, i was unable to find any solution to this, even though i searched for the solution to this problem everywhere i could, even on this forum, but, alas, my searh have been found wanting.
Can anyone, please, help me find a workaround for this?
## Post #2
- Username: MiTriSite
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 01, 2021 9:17 pm
- Post datetime: 2021-06-12T18:05:22+00:00
- Post Title: Prey (2017) Mimic and Weaver model conversion problem

Okay, since quite some time has already passed and no one seems to be able to help me as of yet, i figured i might actually need to give some specifications on the matter.
Also, i know that it's probably been quite a looong time since anyone was ever been busy porting models from this game, so i might be giving up hope on this, probably... quite soon.
But anyways, here are the specifics on how i port the models, which may or may not be useful:
1) As per instruction for CGF-converter, i use PowerShell. PowerShell version is 5.1. CGF-converter version is 1.0.8;
2) I "cd" PowerShell to the location of the files for the conversion;
3) I put an example of the following line into the powershell: C:\something\something\Aliens\cgf-converter.exe .\Weaver01.skin -objectdir "C:\something\something\Aliens\Weaver";
Note: There are no spaces in any folder names in the actual address, and all symbols used in the folder names are english letters and symbols not restricted for usage by Windows. Like i said, i ported other models the same way, and they came out just fine.
4) It writes out standart output: 
Input file set to .\Weaver01.skin
Data directory set to C:\something\something\Aliens\Weaver

And there it is, a .dae file in the same folder as the original .skin file.
Except it's all screwed up.
Here's all the specifics i could give. I don't know what else can i add, and i am pretty sceptical it could actually help, but i posted it anyways, just for maybes.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-12T22:11:48+00:00
- Post Title: Prey (2017) Mimic and Weaver model conversion problem

> Reply from MiTriSite ↑Sun Jun 13, 2021 2:05 am at Sun Jun 13, 2021 2:05 am
>
> 
Okay, since quite some time has already passed and no one seems to be able to help me as of yet, i figured i might actually need to give some specifications on the matter.
[...]
Here's all the specifics i could give. I don't know what else can i add, and i am pretty sceptical it could actually help, but i posted it anyways, just for maybes.How can you think that anyone could help without a file sample  
That Weaver01.skin for example. AND a working sample for comparison.

btw: did you try the latest version from here?
[https://github.com/Markemp/Cryengine-Co ... /releases/](https://github.com/Markemp/Cryengine-Converter/releases/)
## Post #4
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-06-13T00:52:03+00:00
- Post Title: Prey (2017) Mimic and Weaver model conversion problem

I released a new version of cgf-converter today, but not sure it will work.  Depends a lot on which version of Cryengine the game was made with.  Please try out the current version (v1.1.1) and if that doesn't work, open up an issue on the Github page.

There is also a thread in the general purpose tools folder here which you might want to check out.  I don't look at this particular folder very often.
## Post #5
- Username: MiTriSite
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 01, 2021 9:17 pm
- Post datetime: 2021-06-13T08:15:40+00:00
- Post Title: Prey (2017) Mimic and Weaver model conversion problem

> Reply from Markemp ↑Sun Jun 13, 2021 8:52 am at Sun Jun 13, 2021 8:52 am
>
> 
I released a new version of cgf-converter today, but not sure it will work.  Depends a lot on which version of Cryengine the game was made with.  Please try out the current version (v1.1.1) and if that doesn't work, open up an issue on the Github page.

There is also a thread in the general purpose tools folder here which you might want to check out.  I don't look at this particular folder very often.
Thanks! This version converts all the models i had problems with properly. Problem resolved!
