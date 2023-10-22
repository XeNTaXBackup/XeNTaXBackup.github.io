## Post #1
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-01-03T08:08:28+00:00
- Post Title: "The Outforce" .box files.

Watto's Game Extractor is only partially working on the .box format used by "The Outforce". It will extract textures, sounds, and Bink videos but nothing else. The main file is content.box, which in the retail game is over 66 megabytes.

The textures and videos Game Extractor pulls out only total about half the size of the archive, which according to GE is not compressed.

I'd like to be able to extract the 3D models.
## Post #2
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-03T16:18:19+00:00
- Post Title: "The Outforce" .box files.

Should be easy to write a BMS script for that game: [http://wiki.xentax.com/index.php/The_Outforce_BOX](http://wiki.xentax.com/index.php/The_Outforce_BOX)
## Post #3
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2008-01-11T19:27:16+00:00
- Post Title: "The Outforce" .box files.

I just saw the thread and quickly put together this little script. I haven't tested it as I don't have any .box archive. It won't support adding files, but it should be able to extract them all.

```
SavePos TEMP 0 ;
Math TEMP -= 3 ;
GoTo TEMP 0 ;
Get DIRX Long 0 ;
GoTo DIRX 0 ;
Get FILENUM Long 0 ;
For F = 1 To FILENUM ;
Get FNAME String 0 ;
Get FOFFSET Long 0 ;
Get FSIZE Long 0 ;
Log FNAME FOFFSET FSIZE 0 0 ;
Next F ;

```

[box.zip](https://xentaxbackup.github.io/file/1424_box.zip)
## Post #4
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-01-12T07:42:04+00:00
- Post Title: "The Outforce" .box files.

Can I use that with the shareware version?
## Post #5
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2008-01-12T12:23:10+00:00
- Post Title: "The Outforce" .box files.

> Reply from bizzybody
>
> Can I use that with the shareware version?
I'm not sure, Mr.Mouse has to answer that i guess. But there should be a BMS menu in MultiEx where you can select "Add BMS to MRF", use that if it exists.
## Post #6
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-01-13T05:11:13+00:00
- Post Title: "The Outforce" .box files.

Nope, that insists that I register. I tried the online options and those don't work. I'm on dialup. 

If you want files to experiment on, the demo can be downloaded here.

[http://tinyurl.com/2gp8lr](http://tinyurl.com/2gp8lr)
## Post #7
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2008-01-13T23:26:18+00:00
- Post Title: "The Outforce" .box files.

I downloaded the demo and tested my script i uploaded... MEXC didnt even load with it. I recreated the BMS with the same script, tada, worked. And it also extracted all files fine. Just grab the new one. 

By the way, for any bms-guru: is it possible to make mexc support adding files to the archive also? I tested with StandardTail for ImpType and also added the offsets to 'Log', but it totally messed up the archive when i tried replacing some file.
[box.zip](https://xentaxbackup.github.io/file/1426_box.zip)
## Post #8
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-01-14T00:09:28+00:00
- Post Title: "The Outforce" .box files.

What I'd love to find is a copy of the console commands and how to get into the built in map editor in The Outforce.

Unfortunately they were only posted on the original forum for the game and I didn't save a copy before the forum was replaced and all the old posts deleted.  Even worse is the site had a robots.txt file so archive.org didn't save anything.
## Post #9
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-14T07:39:54+00:00
- Post Title: "The Outforce" .box files.

> Reply from bizzybody
>
> What I'd love to find is a copy of the console commands and how to get into the built in map editor in The Outforce.
Why don't you ask once more in the game's forums?
Besides that, if you already know a command, try to search for it in the game's exe with a hex editor, with some luck you also find the other command strings near this one.
## Post #10
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-01-15T05:54:09+00:00
- Post Title: "The Outforce" .box files.

There is no forum for that game anymore. The company that made it, o3games, is now Starbreeze Studios and doesn't answer any questions about The Outforce.

Still no closer to finding the model data. Inside content.box under Units is a file named PackedProject.OPF

Neither MultiEx nor Watto's can pull out all the files from that one. All either sees in it are image files and they both get the wrong data on some of them so they come out corrupted or not at all.

If the model data isn't in there, I've no idea where it's tucked away.

intro.box is nothing but the intro movie, music.box is simply a few MP3 files, campaigns.box is the campaign data and campaigns_movies.box is the videos that play between the maps in the campaign.

I opened the game .exe with a hex editor and scrolled through that but nothing jumped out at me. It's only 1.44 meg. It's rather astonishingly simple, just a single .exe file and 580 megs of various data packed into .box files. (Think of how big the thing would have to be without being able to use DirectX!)
## Post #11
- Username: Kispeti Krisztian
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 25, 2010 4:54 am
- Post datetime: 2010-05-24T21:03:10+00:00
- Post Title: "The Outforce" .box files.

Hi all! I have the full version of The outfoce! And the map editor is working!!!!!!!!
My friend on youtube is a software developer


Here is how to enable the map editor:

Of course, I can. 

Firstly you should edit script-file "Statup.cfg". Insert line "Cheats(true);" (without quotes) before any line in this file. 

This little change allows you to switch on edit-mode without message "m_EditMode(0) cannot be run at this time or gamestate". When desired map (level) is run, open console and input two following commands: "m_DevMapMode(1);" and "m_EditMode(1);". That's all. 

You can exit from this mode by using command sequence "m_DevMapMode(0);" and "m_EditMode(0);". 

However, entering into edit-mode automatically disables fog-of-the-war effect. After exiting from edit-mode you can turn it on by using console-command "Effect_FogOfWar(1);". 

Additionaly, there are many kinds of very usefull console-commands. You can type CmdList("list_of_all_available_console_commands.txt") to save short information about every command to the specified file. Filename can be any. 

Note: because scripting syntax is derived from C/C++, you must escape every special-character in string. So, if you mean backslash ( \ ), you should type \\, if you mean quote-mark, you should type \". So common filename looks following: "c:\\abc\\def\xxx.yyy"
## Post #12
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2010-05-24T23:56:42+00:00
- Post Title: "The Outforce" .box files.

Sweet! Now we need some people to put together campaigns for the Crion and Gobin races and more multiplayer maps.

Would be nice to get the source code released, or find some other way to alter the three races so they're not completely identical other than most unit names, graphics and sounds. For play balance there's zero difference, you can play any of the three the same way.
## Post #13
- Username: Kispeti Krisztian
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 25, 2010 4:54 am
- Post datetime: 2010-05-25T10:42:24+00:00
- Post Title: "The Outforce" .box files.

Hey guys! Please VISIT this site: [http://forum.starbreeze.com/viewtopic.p ... 2858#p2858](http://forum.starbreeze.com/viewtopic.php?pid=2858#p2858)

The forum admin made a topic about The Outforce!


The map editor is working!
You can build Multiplayer and skirmish maps!


We have to make a website where maps and the game and the patches are available!
## Post #14
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2010-05-30T06:10:59+00:00
- Post Title: "The Outforce" .box files.

Far as I know, only the demo, a 1.01 patch for the European version and the "finished" game were released.

Would've been nice had there been Crion and Gobin campaigns, more multiplayer maps and an update to make the three races play different, more like how Starcraft is instead of having all three play exactly the same.
## Post #15
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-16T19:32:14+00:00
- Post Title: "The Outforce" .box files.

> Reply from bizzybody
>
> Nope, that insists that I register. I tried the online options and those don't work. I'm on dialup. 

If you want files to experiment on, the demo can be downloaded here.

http://tinyurl.com/2gp8lr

I know how to edit / make maps with the BUILT IN map editor. I will make a tutorial!
.BOX files can be extracted with game extractor.

The only thing I dont know is how to make (for example) LR Radar (LongRangeRadar) buildable in skirmish.
[game_ex4.jpg](https://xentaxbackup.github.io/file/13693_game_ex4.jpg)
## Post #16
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2017-12-17T00:27:45+00:00
- Post Title: Re: "The Outforce" .box files.

It would be nice if they'd release the source code, or at least what they had done on the Crion and Gobin campaigns.

The trick to beating the final Terran level is to have a teleporter ready and targeted somewhere. Turn the teleporter off and park some ships on it. When you blow up the enemy base, wait for the blast wave to pass the teleporter's target then turn the teleporter on. *zzap* You've survived.
## Post #17
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-17T07:53:05+00:00
- Post Title: Re: "The Outforce" .box files.

Hello, its me again!
Yes it would be nice if they would release the source code... (As Arkane Studios did with Arx fatalis). I can extract and modify every .box files. I also know how to make skirmish maps! I will make a tutorial .pdf and a website.

> Reply from bizzybody
>
> It would be nice if they'd release the source code, or at least what they had done on the Crion and Gobin campaigns.

The trick to beating the final Terran level is to have a teleporter ready and targeted somewhere. Turn the teleporter off and park some ships on it. When you blow up the enemy base, wait for the blast wave to pass the teleporter's target then turn the teleporter on. *zzap* You've survived.
## Post #18
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-18T21:40:11+00:00
- Post Title: Re: "The Outforce" .box files.

Hi, its me again! I have made a skirmish map, its works well. I know how to use the map editor, but I still dont know why i dont have a fu.king radar :'( 

> Reply from bizzybody
>
> It would be nice if they'd release the source code, or at least what they had done on the Crion and Gobin campaigns.

The trick to beating the final Terran level is to have a teleporter ready and targeted somewhere. Turn the teleporter off and park some ships on it. When you blow up the enemy base, wait for the blast wave to pass the teleporter's target then turn the teleporter on. *zzap* You've survived.
[why donthave radar.jpg](https://xentaxbackup.github.io/file/13705_why donthave radar.jpg)
## Post #19
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2017-12-19T01:17:32+00:00
- Post Title: Re: "The Outforce" .box files.

What would be nice to have is a complete list of console commands and their parameters. o3 Games did post a command list on their old forum but I neglected to save a copy.  I do remember that using selectgroup 0 could be used to cheat. Everything not grouped is in group 0, including all the AI's stuff. So you can select everything the *turn it off*, leaving the AI opponent dead in space while you poke around to scout - or destroy.

My favorite thing was building the large generators in the middle of the enemy base then falling back, turning everything back on then watching the enemy blow themselves up.
## Post #20
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T06:48:28+00:00
- Post Title: Re: "The Outforce" .box files.

If you want the full command list, pres F2 during you playing on a map, and type: cmdlist  By the way, can you tell me, why I dont have a radar on my map?

> Reply from bizzybody
>
> What would be nice to have is a complete list of console commands and their parameters. o3 Games did post a command list on their old forum but I neglected to save a copy.  I do remember that using selectgroup 0 could be used to cheat. Everything not grouped is in group 0, including all the AI's stuff. So you can select everything the *turn it off*, leaving the AI opponent dead in space while you poke around to scout - or destroy.

My favorite thing was building the large generators in the middle of the enemy base then falling back, turning everything back on then watching the enemy blow themselves up.
## Post #21
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2017-12-19T09:40:41+00:00
- Post Title: Re: "The Outforce" .box files.

No idea why you don't have RADAR. o3 Games promised a level building tutorial but never delivered. 

One issue that can be a problem, and was never patched, is when the AI builds buildings too close to the bottom edge of the map, it can't figure out how to get newly built ships out of them. Since everything is 3D models the easiest fix for that would have been to make buildings within x distance of a map edge automatically rotate to face away from it.

If you use the selectgroup 0 cheat then go move the AI building with some tow ships, then turn the AI's stuff back on it'll start using the building again.

The only thing this bug doesn't affect are the units with phasing capability because they can simply pass through anything.
## Post #22
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T09:45:30+00:00
- Post Title: Re: "The Outforce" .box files.

Thank you. Regarding radar issiue, I think that problem is that my HM_Central spawns outside of the map... Can you tell me how can I modify my spawnpoint "player1") ?

> Reply from bizzybody
>
> No idea why you don't have RADAR. o3 Games promised a level building tutorial but never delivered. 

One issue that can be a problem, and was never patched, is when the AI builds buildings too close to the bottom edge of the map, it can't figure out how to get newly built ships out of them. Since everything is 3D models the easiest fix for that would have been to make buildings within x distance of a map edge automatically rotate to face away from it.

If you use the selectgroup 0 cheat then go move the AI building with some tow ships, then turn the AI's stuff back on it'll start using the building again.

The only thing this bug doesn't affect are the units with phasing capability because they can simply pass through anything.
## Post #23
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2017-12-19T10:05:47+00:00
- Post Title: Re: "The Outforce" .box files.

Can you open one of the included multiplayer maps? Perhaps examining that will help?

One thing I found about those maps is they're not hard limited to the number of players listed. It will stuff the extras in where ever it can find room.

I used to run 8 players on the Small Encounters map, all AI, just to see the computer play itself. Sometimes free for all, some times with teams. Some of the time I'd have it randomize the difficulty, some times I'd select to have them all the same. Naturally the low difficulty AI players would usually get exterminated pretty quick.

An example of how unfinished the game was when the publisher forced its release is the AI never builds any sort of fence and never uses towships. Unless you let a skirmish drag on a long time and allow the AI to build up a truly massive base, it won't build the huge power plants. IIRC there are some other things I never saw the AI build.

In the campaign my favorite tactic was to harden my defenses, building fences with turbo lasers and the slow ships with the big turret gun behind them. I'd put builders on guard on critical units, along with various ships and turrets scattered throughout to handle the phasing fighter incursions.

Then I'd build up the expeditionary force. A mixed selection of units, including builders for mobile repair and tow ships, each dragging a turbine laser. I'd send a couple of the long range radar ships out to scout, then position a bulwark of turbine lasers. Then I could swoop in, do damage and retreat to repair. Keep that up until defenses were down then advance the turbine lasers to stop rebuilding. I'd also build warp nuke bombs then sling them into the enemy defenses. They shoot it, it goes boom.

There'e one campaign map where it's best to ignore the front door. Work around the back where there's a fence then pull open a hole with tow ships. It takes a lot to get a fence section moving but doesn't trip the attack alarm.  Could also get small asteroids moving to toss in and really upset defenses, but that requires a lot of resource investment into towships and a clear run at the enemy fortifications.
## Post #24
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T10:10:06+00:00
- Post Title: Re: "The Outforce" .box files.

I have made a skirmish map (Revenge) There is max 2 players. But my units spawns outside of the map :\  so do enemy units. I dont know how to modify spawnpoint (in map editor mode there is a "Player0" label on your hm_central. I think that this indicates your spawnpoint.
## Post #25
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T10:11:28+00:00
- Post Title: Re: "The Outforce" .box files.

And Yes, I can open every map
## Post #26
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2017-12-19T10:16:10+00:00
- Post Title: Re: "The Outforce" .box files.

Try opening the maps outside the game, in a text or hex editor. Both one of the included skirmish maps and yours with the problem. Might be able to spot differences and see what's wrong.
## Post #27
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T10:18:49+00:00
- Post Title: Re: "The Outforce" .box files.

> Reply from bizzybody
>
> Try opening the maps outside the game, in a text or hex editor. Both one of the included skirmish maps and yours with the problem. Might be able to spot differences and see what's wrong.
[mymods.jpg](https://xentaxbackup.github.io/file/13707_mymods.jpg)
## Post #28
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T10:19:58+00:00
- Post Title: Re: "The Outforce" .box files.

My map is working well, But I dont have radar and "preview" picture in skirmish...
[mymods2.jpg](https://xentaxbackup.github.io/file/13708_mymods2.jpg)
## Post #29
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2017-12-19T12:46:57+00:00
- Post Title: Re: "The Outforce" .box files.

Good news!!!! I found some useful commands  I have found a useful command  "m_setstartposition()" , "m_setstartpositionbymouse"

M_SetStartPosition (int playerID,float x, float z); sets a start position of a player 


> Reply from bizzybody
>
> I don't know any of the technical details of the game. Not even what any of the actual cheat codes are. Never played it multiplayer against other humans.
## Post #30
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-01-15T10:19:58+00:00
- Post Title: Re: "The Outforce" .box files.

Here is a blend file to extract meshes from "PackedProject.OPF" (from demo game) 

Opf is container but values of offsets where begin each mesh or image propably are outside the file, maybe in exe, i don't know.

My python script search all "CBaseClass" section in *.opf , parse this section and export to binary file with "mesh" extension

Meshes are exported as pure geometry, no weights, no uv ,no bones.



Blend file use only with Blender version 2.49 

[http://www.mediafire.com/view/z5ybhbaqf1hu94m/sc.jpg](http://www.mediafire.com/view/z5ybhbaqf1hu94m/sc.jpg)

You need:
[http://download.blender.org/release/Ble ... indows.exe](http://download.blender.org/release/Blender2.49b/blender-2.49b-windows.exe)
and
[https://www.python.org/ftp/python/2.6.6 ... -2.6.6.msi](https://www.python.org/ftp/python/2.6.6/python-2.6.6.msi)


[http://www.mediafire.com/file/d3whkm9ey ... -15%5D.zip](http://www.mediafire.com/file/d3whkm9ey0f398k/Blender249%5BTheOutforceDemo%5D%5Bopf%5D%5Bmesh%5D%5B2019-01-15%5D.zip)


Unpack archive, doubleclick on file "Blender249.blend" , press alt+p in Blender Text Window
## Post #31
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2019-01-15T11:20:40+00:00
- Post Title: Re: "The Outforce" .box files.

Thank you very much!

Is it possible to convert these .mesh files to an editable file format? These files are contain configs as well, such as: ship speed, which race can build ships, turrets, etc. I just want to edit them.  

The .opf file is about 7,8 mb (full version game) and I was able to extract all the 345 images from .opf (~3,62mb), but there is at least 4 more MB something left (I think config files) I cant pull out of the file
## Post #32
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-01-15T13:30:52+00:00
- Post Title: Re: "The Outforce" .box files.

Do you want edit and change this values like at screen ?
[Zrzut ekranu (13).png](https://xentaxbackup.github.io/file/15477_Zrzut ekranu (13).png)
## Post #33
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2019-01-19T18:01:10+00:00
- Post Title: Re: "The Outforce" .box files.

Dear Szkaradek123! First, I want to turn this characters to normal text in order to edit them. Finally, Watto helped me, so I can extract packedproject.opf file. But still have some problems...

By the way how to turn. CUNIT and .CBASECLASS files to editable files?



opf.png (110.98 KiB) Viewed 198 times



I have sent you 2 pngs. On the second png you can see a "text" I want to edit. In the game there is a unit called "Hm_central" which produces two units: hm_towship and hm_mcu. I just want Hm_central to produce another unit called "RCU", which collect resources in the game. But after I try to edit anything, the game wont load any map... Why is that?

I will send you the other file in a new message

> Reply from Szkaradek123
>
> Do you want edit and change this values like at screen ?
## Post #34
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2020-04-10T15:24:31+00:00
- Post Title: Re: "The Outforce" .box files.

Hi there! 

Cunit | .CUnitWEapon | .CGridmember | .CBaseClass files are binary data containers. I made a deep research to write an extrator, but I can not do it till !d!ot Starbreeze release the source code or the algorithm they use to compress these files.

I have downloaded the official patch files released by O3Games and I opened them in a hex editor. I have found the these files were compressed (packed) with a software called: "Petite compressor" That you can download from: Un4seen.com

[https://media.moddb.com/images/members/ ... petite.png](https://media.moddb.com/images/members/5/4311/4310944/profile/petite.png)

I also found that each .CUnit .CUnitWeapon :CGridMember .CBaseClass, .UNKNOWN files had it's folders with out the "." (I will attach some pictures)

Regarding to this: all filetypes that I mentioned about had a .cpp ( C++ source) file.

[https://media.moddb.com/images/members/ ... pfiles.jpg](https://media.moddb.com/images/members/5/4311/4310944/profile/cppfiles.jpg)

I come to the following conclusion:

.CUnit files are somekind of configuration files.
.CUnitWeapons are also contanins confogurationfiles.
.CBaseClass contains 3D modell files
.CGridMember: are animation files.
.Unknown files are somekind of RAW image files.

For more info (unpacked files, tipps, map editing) please visit: [https://www.moddb.com/games/the-outforc ... embersform](https://www.moddb.com/games/the-outforce/downloads#membersform)
and The Outforce game forum: [https://www.moddb.com/games/the-outforce/forum](https://www.moddb.com/games/the-outforce/forum)
## Post #35
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2020-08-30T13:40:42+00:00
- Post Title: Re: "The Outforce" .box files.

If you still interested in the game please join our:

Discord server: [https://discord.com/channels/7416477335 ... 4263775234](https://discord.com/channels/741647733500149803/741647734263775234)
Moddb site: [https://www.moddb.com/games/the-outforce](https://www.moddb.com/games/the-outforce)

Buy the full original game (digital format) at: https://www.zoom-platform.com/product/the-outforce 

My mode "Conflict in the Epsilon System" will be available soon!

Features in a nutshell?

Full map editor documentation
Full external server program documentation
Commandlsts
Fileformat documentations

-> new maps (skirmish, singleplayer)
-> singleplayer maps converted to skirmish

->Xenons "hidden race" now enabled, destruction power decreased.
-> 2 new buildable guns for Gobins (flashbat, heavy guard)
-> Obelisk turret for Crions

cut contents (units, buildable structures) will be readded.

-> gathered the tools devs used to create maps (converters) and audio tool!

and more!
## Post #36
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2023-07-09T15:41:01+00:00
- Post Title: Re: "The Outforce" .box files.

hello guys! iam a modder and i really need your help.

i want to make an external program written in c++ that allows me to open, unpack and repack files into one piece of .box file.


regarding fileformat nfo thats all i know is below:

X - File Data

// Directory
  4 - Number Of Files

  // for each file
    X - Filename
    1 - null Filename Terminator
    4 - File offset
    4 - File Size

4 - Directory Offset


iam not good at programming, but i really want to know how to start create such small unpacker-repacker program.

thank you very much for your reply in advance.
## Post #37
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-09T19:38:19+00:00
- Post Title: Re: "The Outforce" .box files.

You can try to write quickbms script. Quickbms has repack option and scripts are easier to write than standard programs.
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

If you want to learn how to write scripts, you can check out this topic [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

You can also upload sample BOX file to some hosting site like mega.nz or google drive, share a public link in this topic and then
there will be high chance that someone from the forum will write a script for you and will share it with you.

Also, what game is this file from? Which platform?
## Post #38
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2023-07-09T19:52:09+00:00
- Post Title: Re: "The Outforce" .box files.

Hello! Thx for your reply. Its for The Outforce.

Wattos Game extractor can unpack and repack any .box files... But I want to make an external program for it.

I also made a mappack for the game, next day i will release my mod for the game...

I'm also interested in how to "convert" .jpeg images to .bik format. Yes, a .bik file that only contains a .jpeg image file
## Post #39
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-09T20:06:29+00:00
- Post Title: Re: "The Outforce" .box files.

> Its for The Outforce.
Well, there was already a topic for this BOX format on the forum, so I have moved your posts.
You shouldn't create a new topic if there is already some discussion available on the forum.

> But I want to make an external program for it.
As I said - you can write it as a script, it will be easier.
Quickbms is a command-line tool so it can be run as any other external program.
But if you want to create a program on your own, nothing really stops you.
Just learn C++ and write it.

> how to "convert" .jpeg images to .bik format.
You can try to use RAD Video Tools [http://www.radgametools.com/bnkdown.htm](http://www.radgametools.com/bnkdown.htm)
If it doesn't help, you can create AVI file with any video editor, put your JPEG files there and then use RAD Tools to convert AVI to BIK
## Post #40
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2023-07-10T16:45:02+00:00
- Post Title: Re: "The Outforce" .box files.

hi again. thank you for your reply.

it is really difficult -for a beginner- to determine the file structure for an unknown data container file? i really need some help and tutorials
## Post #41
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2023-08-10T12:49:40+00:00
- Post Title: Re: "The Outforce" .box files.

*.box archive extractor is now available for download.

Here's the download link: [https://www.moddb.com/games/the-outforc ... nloadsform](https://www.moddb.com/games/the-outforce/downloads/the-outforce-box-extractor-tool#downloadsform) 

I'm also working on the GUI version of *.box extractor - builder tool (the extractor is operational, but there's a problem with the *.box builder part of my program [see below]).

I'm also working on the repacker tool, which is operational, but after creating the *.box archive, the size of the archive is different from the official *.box files... 

If I share the source code of my *.box builder can you help me fixing it?

Thank you very much in advance!
