## Post #1
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-09-10T12:35:48+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Important:

> Reply from boutoron2685 ↑Sat Aug 12, 2023 11:01 pm at Sat Aug 12, 2023 11:01 pm
>
> 
Unfortunately, this tool's project seems to have been discontinued.

If you are still interested in using this tool, you should use the DepotDownloader to get Manifest 133280937611742404. This manifest is updated to Y7S2.2.
First extraction tool made by Tushkan (requires Python to work, is glitchy):
[https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0](https://www.dropbox.com/sh/b2cuse4hp90ym0g/AADXaqKfyrCY9joUtsnlqTfja?dl=0)

Second extraction tool made by parzivail and floxay, includes a dumper and an asset viewer (requires just up to date .NET framework installation and familiarity working with Windows command prompt. AssetCatalog requires a lot of time and patience to go through all of the million different assets, refer to the UID lists below. Seems to be more stable):
[https://github.com/parzivail/RainbowForge](https://github.com/parzivail/RainbowForge)

.DDS to .png normal map exporter:
[viewtopic.php?p=177218#p177218](https://forum.xentax.com/viewtopic.php?p=177218#p177218)


UID list:
Here is a UID spreadsheet done by me with everything I have found from specific archives:
https://docs.google.com/spreadsheets/d/ ... sp=sharing

Ultra Texture Pack texture location:
datapc64_mtx_bnk_textures4

(If you have the UHD pack properly installed, the HD textures get exported with rest of the standard resolution textures)

Location for textures usually used by player characters, NPCs, their equipment and probably weapons:
datapc64_ondemand.forge

List of assets and their UIDs made by DeadmanWasTaken:
https://drive.google.com/file/d/12NTfPx ... iFkcZ/view

Another asset list by 09williamsad:
https://docs.google.com/spreadsheets/d/ ... 1372597097

Catalog of my findings for AssetCatalog (paste it to the main folder, replace if needed), mostly first and third person view models for the operators and also some gadgets:
https://www.mediafire.com/file/vn8zwihm ... og.db/file
https://www.mediafire.com/file/uf8yyep7 ... og.db/file

Texture types by assets:
Character models:
Diffuse + Translucency (light shines through cartilage -effect)
Normal
Specular
If UHD pack installed: 4k normal + cavity detail map

Note, operators' head object will dump all of the textures belonging to the spesific headgear, with the headgear included, same as when extracting the textures from a headgear with it dumping the head object's textures. No need to find both the objects if you just need the textures. Sometimes different headgear have similar looking head objects, even if they belong to different headgears, so keep that in mind if you are wondering about getting textures you're not looking for.

Translation for the DumpTool commands:

dump: When you want to export a single object or texture, use this.

dumpall: Dumps everything in a given forge file (not sure if it works on textures)

findallmeshpropsglobal: Once you have found a UID of an object (maybe a texture works too on finding objects, I'm not sure as I haven't tried), use this command to look for the corresponding package from each one of the forge files (that is if you do not know its location).

findallmeshprops: If you know where the packages are located, use this to speed up the finding process, as it will only look for them in this single archive. For example, it seems that most packages are always in the datapc64_ondemand.forge archive. UHD textures are in datapc64_mtx_bnk_textures4.forge, however the tool will automatically export them if you simply select the ondemand archive.

dumpmeshprops: Once you have run either of the findallmeshprops commands, you now have the UID of an object. You can use this to dump textures and every associated object, including the head and eye/mouth objects even if you don't have their UIDs. And best of all, you can figure out the other objects UIDs as well with this method. This also works best when exporting weapons and attachments that have small individual pieces that are for some reason separate UIDs in the game.

dumpallmeshprops: I reckon this exports every single texture and forge from a given forge archive.
## Post #2
- Username: zeyd6796
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 27, 2016 11:54 pm
- Post datetime: 2016-10-27T19:33:11+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

~~Need a update for this topic~~

We have used ninja ripper x64 dx11/9 on the cracked game to extract data to import, but mesh files (.rip) cannot be open properly.

ninja_importer v1.3, rip2obj, a blender .rip script and Noesis have been tried, but the structure of the meshes are just inappropriate.

Here is the source: [https://facepunch.com/showthread.php?t= ... p=51269755](https://facepunch.com/showthread.php?t=1538321&p=51269755)

There are some .rip and dds samples which are ripped from the game on the topic:
[https://yadi.sk/d/2EtUiNFfxhqL3](https://yadi.sk/d/2EtUiNFfxhqL3)

What can be done, any idea?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-27T19:59:11+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from zeyd6796
>
> There are some .rip and dds samples which are ripped from the game on the topic:
https://yadi.sk/d/2EtUiNFfxhqL3

What can be done, any idea?learn the 3D basics  
A quick glance into those *.rip files reveals that there's (apart from some .dds texture names)
only face indices contained - no vertices (zero bytes, 00 00 00 00...,  though).

So how should that work?
## Post #4
- Username: zeyd6796
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 27, 2016 11:54 pm
- Post datetime: 2016-10-27T20:10:34+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Thanks for the quick reply.
The samples were parepared to diagnose or to understand what happend when they were ripped. Then we can change the paremeters or methods to obtain correct data. So, the data structure or algorithm of the game is just inappropriate for ninja ripper. And there is no current archive extractor. Just Intel GPA to rip... Right?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-27T20:36:59+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I don't really care for "war games", so dunno,  but I found a rip file with vertices
so Ninja Ripper doesn't seem to be totally "off track":



Mesh_0094-rip.JPG (40.46 KiB) Viewed 2789 times
## Post #6
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-29T09:09:04+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from zeyd6796
>
> ~~Need a update for this topic~~

We have used ninja ripper x64 dx11/9 on the cracked game to extract data to import, but mesh files (.rip) cannot be open properly.

ninja_importer v1.3, rip2obj, a blender .rip script and Noesis have been tried, but the structure of the meshes are just inappropriate.

Here is the source: https://facepunch.com/showthread.php?t= ... p=51269755

There are some .rip and dds samples which are ripped from the game on the topic:
https://yadi.sk/d/2EtUiNFfxhqL3

What can be done, any idea?
Didn't realize this thread got bumped.

Well, I tried Ninjaripper and it doesn't work on the legit version. However, I'm not sure are there cracked versions of the game from the latest version with the Skull Rain items.

As for other programs, I'm not sure do they work. I tried Archive_Next and it just crashes every time I try to open a file from the R6 game folder.
## Post #7
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-11-21T21:55:45+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

So is this dead?
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-11-23T11:16:50+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

The problem is a Forge unpacker is required, if someone makes one, I'll work on the 3D models.

Cheers.
## Post #9
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-11-25T10:40:15+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from Gh0stBlade
>
> The problem is a Forge unpacker is required, if someone makes one, I'll work on the 3D models.

Cheers.
There is Archive_Next, but the developer of that tool has gone dormant so there's no R6 support for it.... :/
## Post #10
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2018-11-12T18:19:45+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I have python script that unpacks current versions of forge. They switched to zstandard to pack data, but other than that structure is not much of a difference. Another bugger is that they seem to hash all strings and store hashes instead of actual names to prevent data mining. I was hoping to inspect the game process with debugger to see how they threat those hashes, but legal exe is virtualized and has attach protection (x64dbg throws an error upon attach, on launch it hits the debug warning or BE warning). I'm still too dumb to break through such protection measures, but I have unpacked samples. So if anyone is interested, I can provide my data. They also have .depgraphbin files that hold \x02 at the beginning (magic number?) and then uint64_hash1, uint64_hash2 and some uint32 (class?, relation type?), hashes match the ones that can be found in names section, describing each file inside a given forge package. I assume this is one of ways to tie up needed resources together.
## Post #11
- Username: Jojje
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 06, 2018 10:07 pm
- Post datetime: 2018-12-23T12:38:22+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from Tushkan
>
> I have python script that unpacks current versions of forge. They switched to zstandard to pack data, but other than that structure is not much of a difference. Another bugger is that they seem to hash all strings and store hashes instead of actual names to prevent data mining. I was hoping to inspect the game process with debugger to see how they threat those hashes, but legal exe is virtualized and has attach protection (x64dbg throws an error upon attach, on launch it hits the debug warning or BE warning). I'm still too dumb to break through such protection measures, but I have unpacked samples. So if anyone is interested, I can provide my data. They also have .depgraphbin files that hold \x02 at the beginning (magic number?) and then uint64_hash1, uint64_hash2 and some uint32 (class?, relation type?), hashes match the ones that can be found in names section, describing each file inside a given forge package. I assume this is one of ways to tie up needed resources together.
Very interesting, so you can get the files, but the names are hashed?
## Post #12
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-01-07T17:42:30+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Yes, Jojje. I have the extracted data with fancy looking file names. And me and my friend have extracted a couple of game models, like Thermite's elite mesh for example. But there are some peculiar versions of a mesh file which I can't seem to fully reverse. So I'm asking for a community's help. Here is some of the extracted data [https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0](https://www.dropbox.com/sh/b2cuse4hp90ym0g/AADXaqKfyrCY9joUtsnlqTfja?dl=0) It includes a bunch of models (some are operators, their heads, weapons etc) in game's native format plus a README of currently known data plus some logs. Where I need help is with the packed vertex data (marked as Qc and Dc in the README). If anyone can help me crack how it's packed, that would be great.

Here are a couple of screenshots just to draw your attention =)
## Post #13
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-01-15T17:27:01+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Ok, nevermind, I figured it out. It turned out to be 4 int16. Three for x,y,z and last is scaler.
## Post #14
- Username: Jojje
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 06, 2018 10:07 pm
- Post datetime: 2019-05-10T22:58:29+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Checking in! Has any progress been made since last post..?
## Post #15
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-05-14T18:32:59+00:00
- Post Title: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Yep, there has been. I unpacked all types of meshes and seem to have found uv's block. There are some questionable blocks tho. And the biggest issue is there are no asset names. I have also found the files that tie an asset together (mesh or several meshes, textures) but it has no link to the skeleton which is odd. And an absence of proper names makes it impossible to pinpoint the exact asset you would want to find.
## Post #16
- Username: Guimain
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 05, 2019 4:58 pm
- Post datetime: 2019-08-05T09:16:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello everybody !

I'm new here and I was looking for a 3D file of Sledge's hammer. Do you guys have it already ? In which form ? ... And if it's an uncommon file type what should I do ?
I may try to do it with steel, could be cool.
Thx
## Post #17
- Username: 6yXJI0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 01, 2019 9:22 am
- Post datetime: 2019-09-01T01:29:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

RIP
But i sill have hope
## Post #18
- Username: fakeacc30
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 01, 2019 4:48 pm
- Post datetime: 2019-09-01T08:56:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey Tushkan,

I was wondering if your method works with image files, in particular for the user interface. If it's possible I'd like to get my hands on them. They're probably inside datapc64_ui_playgo.forge.
## Post #19
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T08:20:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks for your help
## Post #20
- Username: yyred123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 29, 2019 3:24 pm
- Post datetime: 2019-09-15T08:11:16+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed May 15, 2019 2:32 am at Wed May 15, 2019 2:32 am
>
> 
Yep, there has been. I unpacked all types of meshes and seem to have found uv's block. There are some questionable blocks tho. And the biggest issue is there are no asset names. I have also found the files that tie an asset together (mesh or several meshes, textures) but it has no link to the skeleton which is odd. And an absence of proper names makes it impossible to pinpoint the exact asset you would want to find.

Great!I finally see someone working on ripping model from the game
It used to be a person doing it.Though I can't help you,I'm here with u
## Post #21
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-09-18T18:52:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Sorry, I don't monitor this forum that often. Yes, my method works with textures. In fact, they store plain dx10 data, they just wrap it in a custom container. For some reason they move most of the valuable header data (dx10 packing type, image size etc) to the footer. So it's pretty trivial to decode those when you know the enums and offsets (which I've obviously decoded with some hints from luxox).
However I got stuck on asset data files. They hold links to all of the asset resources (textures, meshes, even shaders and some other data yet unknown to me). What annoys me the most is the absence of direct links to skeleton data and total absence of file names. All files are refered to by their uids so you can't get what's where. The only reliable way to find character's asset file is to find it's skeleton's string name. And I have found that one by parsing extra structures inside asset file. So my current focus is on reversing the asset file to the most of my ability. I think that will help to find all valuable data that is related to each asset and will help to grab all the stuff needed for each operator.
Buuuuut I have very little time to do it so the project is currently stalling abit. I hope to refine my utils to easily research and view different structures so I can parse it faster.
## Post #22
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2019-09-28T08:50:48+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I've been trying to get some models from R6 for a few days now with no luck, i'm needing Mozzie's Commando 9/super shorty and pest/launcher for 3d printing if you've found those at any point would you mind uploading them.
## Post #23
- Username: majormoron
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 06, 2019 10:18 am
- Post datetime: 2019-10-06T02:20:22+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey Tushkan,

Is there any way you can send me a texture file for the Fire skin? I am trying to make a vinyl wrap for an airsoft gun, and the best way to do it would be to try to get a direct rip of the texture as a high quality image. Idk if that is something you can do, but it would be really cool if it were something simple.

To clarify, I am looking to use this skin: [https://i.redd.it/2a1zvhorlk9z.jpg](https://i.redd.it/2a1zvhorlk9z.jpg)

Hopefully you can help, but if not I understand.
## Post #24
- Username: SilverBelle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 08, 2018 11:27 pm
- Post datetime: 2019-10-27T10:55:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Is this project still being worked towards? I'm looking to get the regular, non-elite Thermite. No ones ripped it yet and I'd really like to get my hands on it.
## Post #25
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-11-02T14:44:15+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

It's stalling. I wrote some reversing utilities to ease up the data gathering process, but I'm lacking time to actually use em and move forward with reversing the assets. Too much higher priority things to do at home these months.
## Post #26
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2019-11-26T11:10:40+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ah it's too bad, I'm a bit worried that by the time we can asset rip this game properly it'll have lost it's relevance. I've tried getting in touch with Luxox to find out any information I could about their method, so far the best I've seen for Siege, but no luck there either. I'd love to help but I'm just a 3D artist, I haven't put any skill points into programming and python and such it's completely over my head.

Tushkan, is what you've managed so far any use for a brute force approach, where you can find what you want if you have patience for digging?
## Post #27
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-12-07T01:20:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I had already contacted Luxox. He's the one who helped me to identify texture compression types. He is using Intel GPA to dump the memory and rip data from a frame render snapshot. That's too labor intensive to my liking. My approach is to reverse the actual format to know what most of the data means. I'm at the stage where I can break .forge file into distinct uncompressed files (that's not new, other people did it too), I can identify texture files and more or less their types, I can rip most types of models (there are several methods to compress and store model data) with their uv's and presumably normals. I didn't figure out yet how skinning data is stored and I can't find links to skeleton files (those are havok files, there are programs to unpack them). And also the issue is there is no way yet to identify which file is what. There are no strings with names except for rare occasions. There are some asset files that sometimes contain a havok skeleton name as well as links to a bunch of different meshes. This all is subject to reversing which i'm stalling at now. I have to finish another project so I can continue on that again.
## Post #28
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2019-12-07T01:22:35+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Oh, yeah, about your question. At this stage I can export all meshes, all textures, but there are literally tons of them. I can also sort them into folders containing the stuff that is linked into one asset. I still can't get the skeletons linked to those assets though.
## Post #29
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2019-12-09T18:51:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Where can i dowload the tool ?
## Post #30
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2019-12-13T17:54:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

So Luxox does use Intel GPA? Well, color me surprised, that's the main thing I've tried myself.. The labor of it would be okay with me if only I could get results on the level he does. I can rip some meshes; basically I've got access to all weapons and gadgets and weapon attachments. I can get their textures too, including the skins, but the problem is no UVs to go with the meshes! Luxox's rips have UVs so they must be there, but I don't know what I'm looking for. I'll probably keep looking into that some more now.

Some other bothersome things I haven't overcome with the GPA method.. Currently I get them distorted to the frame perspective and fix them afterwards with a lattice, or similar. It's usable, but not ideal. Luxox manages to get the characters in a t-pose and everything, I feel like there might be a way to reverse the object's view transforms and other transforms, or maybe he's managing to take frames with these assets in that aren't viewport based. Also, no edge data for sharp edges, many of the props probably need a lot of touch-up in order to work with smooth shading properly.




r6mesh.jpg (176.58 KiB) Viewed 762 times
## Post #31
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2019-12-31T15:40:59+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm not making any more progress with this. I spent a while researching the subject and doing tests, but even Intel themselves say that the program doesn't store UV data (albeit information a few years old). I'm going to put up the method I used here as it's been requested, maybe someone else can take it further, and sometimes just getting meshes alone could be helpful (I've seen people that want to 3d print Siege miscellania, etc).

I use the latest version of Intel GPA directly from the official source. There is very little information about using it for ripping assets out there that I've found, but the few write-ups I've come across refer to using an old version of the program, just to clear that up to begin with.

Battleye seems to complicate launching so I use the "Auto-detect launched applications" setting to attach the GPA monitor to the game. The game has never connected to the online service when I've been attaching GPA to it, again I think Battleye having a fuss and not allowing it, though it won't incur penalty my account has been fine since. Maybe that was just Ubi's servers being crap.

Take a frame in game, and go open it in the frame analyser. Along the top is a graph showing the various calls that's going on in the frame, that's where I navigate and browse for what I'm looking for. I sort it by primitive count I think (I'm writing this by memory), geometry tends to be heaviest thing so the bigger the register on the graph the more likely it's a proper detailed mesh object, but actually some things like scopes have been quite small ones. There's a lot of calls that just aren't going to be of interest, for lighting and crap I don't really know. In the lower center is the specific display, and at the top of that section you should be able to change between viewing different types of assets for the particular call that you are viewing; e.g. texture, mesh.

There seems to be a bug in the display of geometry, that prevents freely browsing all that is there in a frame without reloading it. If I go through looking at the geometry items I'll see glitchy broken stuff that seems to be mainly the same after I've clicked on a few draw calls — just a couple of disjointed planes — but the textures hint at what the asset might actually be. So I browse by looking at textures instead to find the thing I want — a scope or gun or whatnot will have a recognizable texture — then I remember what draw call number that was, close the frame, the re-open it and click on that specific draw call first and it will show the right geometry. It seems to be the act of clicking through different draw calls that breaks geometry display, the first one you click on works right. Literally a bug with the program it seems, unless I'm missing something.

Also, so far any frame I take doesn't come close to containing draw calls for all the assets that are present in the actual viewed render. Like if I stand in a map looking at walls and props, I'll never find draw calls for any of that stuff. If I try taking a frame in the menu where a character or weapon is being centrally displayed then I'll never find draw calls for most of it. If I load into the game and take a frame then nearly all the provisions of that frame will be focused something specific, which tends to be what was in the characters hands, which is how I'm able to get equipment meshes. The architecture of frame capturing is beyond me, there is probably some analog of baking occuring for static objects and physics objects that means they exist only as a reference call in the frame.. or something, just a guess.

So that's how I can get some meshes, anything I can hold in the character's hands will show up reliably in the frame capture. There's a button right there in the window to export meshes, textures can be got the same way. It will be a distorted mesh and I then attach a cube to it with a mesh deform modifier in Blender and correct the shape of the mesh using orthographic views, doesn't take much time but requires guesswork as to setting the dimensions. Look for parts of the object that are suppose to be circular (such as the end of the barrel or screws and bolts, then push and pull until those are circular and that does most of the work for you.

Better than nothing at all but yeah..
## Post #32
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2019-12-31T17:38:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Tue Dec 31, 2019 11:40 pm at Tue Dec 31, 2019 11:40 pm
>
> 
I'm not making any more progress with this. I spent a while researching the subject and doing tests, but even Intel themselves say that the program doesn't store UV data (albeit information a few years old). I'm going to put up the method I used here as it's been requested, maybe someone else can take it further, and sometimes just getting meshes alone could be helpful (I've seen people that want to 3d print Siege miscellania, etc).

I use the latest version of Intel GPA directly from the official source. There is very little information about using it for ripping assets out there that I've found, but the few write-ups I've come across refer to using an old version of the program, just to clear that up to begin with.

Battleye seems to complicate launching so I use the "Auto-detect launched applications" setting to attach the GPA monitor to the game. The game has never connected to the online service when I've been attaching GPA to it, again I think Battleye having a fuss and not allowing it, though it won't incur penalty my account has been fine since. Maybe that was just Ubi's servers being crap.

Take a frame in game, and go open it in the frame analyser. Along the top is a graph showing the various calls that's going on in the frame, that's where I navigate and browse for what I'm looking for. I sort it by primitive count I think (I'm writing this by memory), geometry tends to be heaviest thing so the bigger the register on the graph the more likely it's a proper detailed mesh object, but actually some things like scopes have been quite small ones. There's a lot of calls that just aren't going to be of interest, for lighting and crap I don't really know. In the lower center is the specific display, and at the top of that section you should be able to change between viewing different types of assets for the particular call that you are viewing; e.g. texture, mesh.

There seems to be a bug in the display of geometry, that prevents freely browsing all that is there in a frame without reloading it. If I go through looking at the geometry items I'll see glitchy broken stuff that seems to be mainly the same after I've clicked on a few draw calls — just a couple of disjointed planes — but the textures hint at what the asset might actually be. So I browse by looking at textures instead to find the thing I want — a scope or gun or whatnot will have a recognizable texture — then I remember what draw call number that was, close the frame, the re-open it and click on that specific draw call first and it will show the right geometry. It seems to be the act of clicking through different draw calls that breaks geometry display, the first one you click on works right. Literally a bug with the program it seems, unless I'm missing something.

Also, so far any frame I take doesn't come close to containing draw calls for all the assets that are present in the actual viewed render. Like if I stand in a map looking at walls and props, I'll never find draw calls for any of that stuff. If I try taking a frame in the menu where a character or weapon is being centrally displayed then I'll never find draw calls for most of it. If I load into the game and take a frame then nearly all the provisions of that frame will be focused something specific, which tends to be what was in the characters hands, which is how I'm able to get equipment meshes. The architecture of frame capturing is beyond me, there is probably some analog of baking occuring for static objects and physics objects that means they exist only as a reference call in the frame.. or something, just a guess.

So that's how I can get some meshes, anything I can hold in the character's hands will show up reliably in the frame capture. There's a button right there in the window to export meshes, textures can be got the same way. It will be a distorted mesh and I then attach a cube to it with a mesh deform modifier in Blender and correct the shape of the mesh using orthographic views, doesn't take much time but requires guesswork as to setting the dimensions. Look for parts of the object that are suppose to be circular (such as the end of the barrel or screws and bolts, then push and pull until those are circular and that does most of the work for you.

Better than nothing at all but yeah..

thank you very much for sharing it custard !
## Post #33
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-01-25T20:11:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sat Dec 07, 2019 9:22 am at Sat Dec 07, 2019 9:22 am
>
> 
Oh, yeah, about your question. At this stage I can export all meshes, all textures, but there are literally tons of them. I can also sort them into folders containing the stuff that is linked into one asset. I still can't get the skeletons linked to those assets though.

Wait, so you can get everything but skeletons and skin data? Is the tool you use quite simple to use (like id-daemon's GR: Wildlands tool) or does it require hex editing or some advanced knowledge? I really don't care about the skeletons for now because you can always make new ones.
## Post #34
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-01-28T22:54:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The tool I use is a python 3 module written to deal with forge archives. It has tools to unpack .forge, to convert textures and to encode mesh data (partially). All this stuff has a bunch of dependencies.
1. Basic .forge manipulation:
zstandard to unpack compressed data
2. textures:
RawTex do assemble proper dds from .forge (they use custom headers that I need to repack into a common dds)
texconv to convert file to png
3. meshes:
blender

3rd module is not polished and can't be used easily. I have a bunch of dirty scripts embedded into a blend file to convert mesh's generic output to a proper blender model. Plus I tendo to unpack forges directly from blender so I had to import zstandard binary into blender's libs folder.
My main goal is to get localization data and to get how assets are formed. From that I can start getting full model packages and investigate the data mode in-depth.
## Post #35
- Username: Ronininja
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 29, 2020 3:50 pm
- Post datetime: 2020-01-29T08:03:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Jan 29, 2020 6:54 am at Wed Jan 29, 2020 6:54 am
>
> 
The tool I use is a python 3 module written to deal with forge archives. It has tools to unpack .forge, to convert textures and to encode mesh data (partially). All this stuff has a bunch of dependencies.
1. Basic .forge manipulation:
zstandard to unpack compressed data
2. textures:
RawTex do assemble proper dds from .forge (they use custom headers that I need to repack into a common dds)
texconv to convert file to png
3. meshes:
blender

3rd module is not polished and can't be used easily. I have a bunch of dirty scripts embedded into a blend file to convert mesh's generic output to a proper blender model. Plus I tendo to unpack forges directly from blender so I had to import zstandard binary into blender's libs folder.
My main goal is to get localization data and to get how assets are formed. From that I can start getting full model packages and investigate the data mode in-depth.

Do you plan on uploading the tool?
## Post #36
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-01-30T00:17:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Fml... All this time I was wondering where do they keep strings to identify models. Turns out they where stored in metadata header which I was mindlessly skipping in meshes. And same goes for texture data.

Yes, Ronininja, I do plan on releasing it. However, it's not going to be a tidy and easy to use tool. I will try to provide some tutorials plus a documentation that explains all the structures and pieces of format so anyone who is versed in writing standalone apps can write a complete tool to grab any needed data. I also suspect that it might get banned by ubisoft, or my account on github\whatever will get suspended as they did with luxox or (even whorse) they will change their file format again which will render my tool mostly useless. So it should be released as a more or less complete working package at once so everyone can rip the stuff they need while they can.
Also, can anyone suggest a place to host it's code where it's unlikely to get suspended?
## Post #37
- Username: Ronininja
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 29, 2020 3:50 pm
- Post datetime: 2020-01-30T19:32:52+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Maybe you can create a torrent and upload it to a tracker?
## Post #38
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-01T06:32:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Thu Jan 30, 2020 8:17 am at Thu Jan 30, 2020 8:17 am
>
> 
Fml... All this time I was wondering where do they keep strings to identify models. Turns out they where stored in metadata header which I was mindlessly skipping in meshes. And same goes for texture data.

Sounds like a major breakthrough, will that be enough to allow indexing assets?

> Yes, Ronininja, I do plan on releasing it. However, it's not going to be a tidy and easy to use tool. I will try to provide some tutorials plus a documentation that explains all the structures and pieces of format so anyone who is versed in writing standalone apps can write a complete tool to grab any needed data. I also suspect that it might get banned by ubisoft, or my account on github\whatever will get suspended as they did with luxox or (even whorse) they will change their file format again which will render my tool mostly useless. So it should be released as a more or less complete working package at once so everyone can rip the stuff they need while they can.
>
> Also, can anyone suggest a place to host it's code where it's unlikely to get suspended?

I've noticed with some other ripping tools they only distribute privately among people that seem involved and helpful, who will make the assets available in bulk / take requests / help develop the tool. That way the game gets ripped but the tool is less likely to end up under a developer's eye, improving the chance it doesn't get bricked. Siege is riding high on the whole games-as-a-service thing right now. Even if a bulk rip gets pulled off if the methods don't last we'll miss out on juicy future content; New ops, skins, weapons, etc.

If you can make a torrent it won't get taken down but it'll be reliant on seeding, which for something this niche may likely be an issue. I've seen a lot of blatantly-illegal stuff hosted on Mega.nz. I expect that site still does takedowns, but if you make a throwaway account your files may slip through the cracks for ages there. If a complete tool gets made then p3dm.ru hosts such programs with pretty much no chance of a takedown.
## Post #39
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-02-01T09:18:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello,
I am new to this forum and feel really happy to see a breakthrough here.
You can upload your scripts to IPFS. It's distributed and thus can't be censored.
I want some zombie models from the operation Chimera, but it was ended in Apr 2018. I have got an older version game, and related forge files downloaded, but I don't know how did you make breakthrough guessing file structures. Thanks in advance.
## Post #40
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-02-02T11:41:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Thu Jan 30, 2020 8:17 am at Thu Jan 30, 2020 8:17 am
>
> 
Fml... All this time I was wondering where do they keep strings to identify models. Turns out they where stored in metadata header which I was mindlessly skipping in meshes. And same goes for texture data.

Yes, Ronininja, I do plan on releasing it. However, it's not going to be a tidy and easy to use tool. I will try to provide some tutorials plus a documentation that explains all the structures and pieces of format so anyone who is versed in writing standalone apps can write a complete tool to grab any needed data. I also suspect that it might get banned by ubisoft, or my account on github\whatever will get suspended as they did with luxox or (even whorse) they will change their file format again which will render my tool mostly useless. So it should be released as a more or less complete working package at once so everyone can rip the stuff they need while they can.
Also, can anyone suggest a place to host it's code where it's unlikely to get suspended?

The only reason Luxos really has been banned is because he was (or is) accepting paid commissions to get stuff out of the game. If I remember correctly, some Ubisoft employe stated they don't care that their models are used as long as they're not directly profited from, like reselling them on some chinese pirate site.
## Post #41
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-02T15:56:15+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[https://youtu.be/mZ383x4Br4U](https://youtu.be/mZ383x4Br4U)
## Post #42
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-03T20:44:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

zaramot, did you get .dat files from forge or did you grab them from game memory? If first, how did you locate all Ash related pieces?
## Post #43
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T10:25:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Tue Feb 04, 2020 4:44 am at Tue Feb 04, 2020 4:44 am
>
> 
zaramot, did you get .dat files from forge or did you grab them from game memory? If first, how did you locate all Ash related pieces?
I got .dat from .forge archives, with quickbms script. Just a luck, I don't know name of this character, I never played the game (just some random female) - parts were in same .forge.
## Post #44
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T14:44:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

O_o could you elaborate a bit more on your process? That seems very odd, considering the fact that you managed to get all parts of a character that should be scattered randomly among an entire .forge archive if not even a couple of them. Did you gather a list of needed pieces from ondemand.forge? What was vertex, normals and skinning weights format? (they differ from model to model, there are about 3 levels of compression plus 2 storage types: array vertex structs or bunch of buffer arrays per-pos, per-norm etc)? I'm particularly interested in skinning weights, I couldn't yet locate that data. Also, maybe you were lucky enough to find her skeleton data?
## Post #45
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T15:03:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Tue Feb 04, 2020 10:44 pm at Tue Feb 04, 2020 10:44 pm
>
> 
O_o could you elaborate a bit more on your process? That seems very odd, considering the fact that you managed to get all parts of a character that should be scattered randomly among an entire .forge archive if not even a couple of them. Did you gather a list of needed pieces from ondemand.forge? What was vertex, normals and skinning weights format? (they differ from model to model, there are about 3 levels of compression plus 2 storage types: array vertex structs or bunch of buffer arrays per-pos, per-norm etc)? I'm particularly interested in skinning weights, I couldn't yet locate that data. Also, maybe you were lucky enough to find her skeleton data?

Don't know, just a luck - there was only 8 skinned meshes (and ton of static ones) in that particular .forge, all referenced to her (as you said, I never saw this character before). My process of extraction is grouping files by type (meshes, textures etc). So, I know, that all meshes from certain .forge are in model folder, then I'm running another script (just for more faster process, it's not really necessary) which is telling me which one is skeletal and which one is static, then I just importing (checking) all skeletal and that's basically all lol. Skinning was pretty simple 4 bone weights - 4 bone indices, I haven't found skeleton - but it should't be hard, honestly. I assume they are using two sets of base skeleton for male and female like a lot of Ubisoft games. Like here for For Honor (a bit similar to Rainbow Six btw, wildlands + all of AC games are quite different)

[https://www.youtube.com/watch?v=GergFXnfy2g](https://www.youtube.com/watch?v=GergFXnfy2g)
## Post #46
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T15:50:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

There are 3 types of operators (3-speed, like the one you exported, 2- and 1-speed ops) plus 2 sexes. So there might as well be 6 skeletons. Plus some characters have their specific animations (Mozzie's reloading, Nomad's planting b'cs she lacks 1 finger). Where do ubi games generally keep their skeletons? This is the first ubi game I'm unpacking so I have no clue how they store their data in general. They have a bunch of havok files in *meshshape.forge but those seem to be colliders. I don't know if it also contains any skeletons or animations which i'm interested in.
If you manage to grab data out of those mesh files, I guess you already took care of their archiving and chunks structure. How did you distinguish between static and rigged meshes? I wasn't able to easily find skinned meshes except for ones that I know of because I play the game. One of reasons is because packaging strategies for verts differ from file to file. There are even models where 1 vert pos is packed into 4 bytes. And with other buffers it gets even harder to interpret those packings (like with normals, i'm not even sure I unpacked them correctly when I found them). The only reliable structure is tris-verts id buffer (still, even that one has a peculiar lod system with chunks and invalid vert indices at lod bounds). I guess Ash was easier because that's an operator and their models generally are not compressed like props are. Can you give any suggestion on how would you approach finding skeletons and where would you search for it?
## Post #47
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T16:15:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Well, yeah since it's using havok - there might be, that they have skeletons somewhere too. Though, from what I saw atm, they were physics/collision related files. Honestly I haven't checked much yet, I have some plans but it was more like a brief research (to get geometry and make a texture converter). Since I don't even have the game lol latest client from torrent was more than 128 gb (of course with HD textures) but still a lot of space, I downloaded only 10 gb of files, which I assumed will have a lot of models+ textures inside (and they are). As for normals they shouldn't be a big problem for skinned meshes, but could be for static ones (I honestly, almost never bugging myself about them because of 3ds max). As for skeleton - I have no idea where it might be right now xD It will have some "type", "class" I don't know how to explain this correctly, I'm a Russian-speaking user - but I basically should extract some .forge with it (identify it's bones), then just remember this "type" - since, all skeletons will be in same folder with such hash after extraction (grouping, like a said).
P.S. A little about first routine. I haven't studied any in dept structure like you might think I am, I just extracted all files by "type". so I had a bunch of folders with certain "hash", then I went into folder one by one - decompressed files, checked them - remember which "type" is model, textures. Edited extraction script, so extracted folders of interest have name models/textures. Made maxscript for geometry import and noesis plugin for textures. That's all for now  It's working, but it's definitely not the game of my interest as for models (not like For Honor, about which I'm still crying like a baby  ) Better they encrypted rainbow six, than my amazing for honor.
## Post #48
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-04T16:39:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Keep in mind that animation or mesh variety or speed of animation in itself doesn't inform on the skeleton, it's only the articulation points to use. To my eye as an animator this game shows all the signs of minimal skeleton variation. I'd say the assumption of one male and one female skeleton would be fair, with probable exceptions of some of the zombie creatures from Operation Chimera. Even when they push the body models like Gridlock or Suicide Bomber, have very different run cycle like Warden or Blitz, I still see the same articulation points on those animations. They also all use a lot of identical shared animations (e.g reinforcing wall), and they are spot-on identical. Character with visible face have facial animations, but if character has hidden face they don't need new skeleton the bones can go unused, same sort of thing with Nomad's missing finger.
## Post #49
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T17:33:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Zaramot, xD. Don't worry about russian, I'm russian speaker too. As for mapping data, I have pandas plots of specific type occurrence per each forge archive. I also have structs for texture files so I can share those if you want to save time (they use plain dds data with custom footer instead of header, plus custom dx10 enum which was a pain to map to actual dx10 types).
As of skeletons, It looks like they should be stored inside meshshape files. They all have the same type and basically store serialized havok data. It can be unpacked to an xml by tool used to unpack skyrim models (i don't remember it's name). However I'm yet to research it.
And what type of encryption does honor have?
## Post #50
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T17:38:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Custard, well that only makes my job harder ) it would be easier to spot similarities within 6 files rather than 2. Alot of data in game is linked via depgraphbin and is referred by uint64 uids, but those don't point at any havok files in particular. And asset files contain a shit ton of small structs full of uid references. Not an easy nut to crack in terms of time.
## Post #51
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T17:50:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Feb 05, 2020 1:33 am at Wed Feb 05, 2020 1:33 am
>
> 
Zaramot, xD. Don't worry about russian, I'm russian speaker too.
I kind of assumed that xD by the nickname, though kept my assumptions with myself lol Well, I have no idea what type of encryption for honor is using exactly, I guess it's AES. Though, since it's denuvo game + has anticheat system  It's almost an unbreakable thing, as for me personally it's absolutely unbreakable wall xD But, I have client with 16 characters and a ton of models for them, so I'm not left with nothing - just with a bit more, than a half of recent game assets lol Still crying though, since I wanted most characters from latest updates
## Post #52
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T18:26:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

They use AES on asset files?.. That's kinda awkward. You can try one thing though. Ubi games generally come with battle eye. When you launch a game, you get your executable (it's encrypted and gets decrypted upon launch and spawned as a new process, at least in siege) and a battle eye service. If you launch your game in offline mode and kill the battle eye service (via cmd, command can be found in the internet or I can provide it to you), you then should be able to attach a debugger or Intel GPA to the game. This way you should be able to rip some decrypted data from it.
## Post #53
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T18:37:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Don't know why but it's always run through steam, even if I'm running it from uplay. Not sure, if it's doing such thing with decrypting .exe with for honor - like with siege. Though, even if I don't have much hope, I still really want those models for myself, so I'm highly motivated and don't mind to put time and efforts into it! I'll re-download the game, and try what you said. If I"ll somehow will be able to grab aes key from decrypted .exe and decrypt .forges, I will be happy like a little puppy.
## Post #54
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T18:48:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Be aware you won't be able to get the actual unencrypted .forge archives. You should be able to halt the game and search through RAM for loaded data. There is a chance to attach and halt upon loading something heavy but I bet tat decryption code will be virtualized and very hard to read. Still, ripping data directly from memory should still be possible. If I manage to finish with R6S, I can try to help you on that one.
## Post #55
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-02-04T19:48:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Feb 05, 2020 2:48 am at Wed Feb 05, 2020 2:48 am
>
> 
Be aware you won't be able to get the actual unencrypted .forge archives. You should be able to halt the game and search through RAM for loaded data. There is a chance to attach and halt upon loading something heavy but I bet tat decryption code will be virtualized and very hard to read. Still, ripping data directly from memory should still be possible. If I manage to finish with R6S, I can try to help you on that one.
I am curious on your way of decrypting forge archives. I know the executable is heavily protected by BE, but I believe 3D related parts (model loading & rendering) can't be virtualized because of performance needs.
Where can I start analysis it without being able to run that executable?
Also, I found a tool [https://zenhax.com/viewtopic.php?t=9138](https://zenhax.com/viewtopic.php?t=9138) published in 2015 can extract forge archive, but it is not open source.
## Post #56
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-02-04T20:10:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I think there is another way to analysis it, rather than stuck on PC version. Maybe we can get details from its PS4 or XBox console version. All of these consoles share mutual instruction set(x86_64) with desktop PC. Games designed for consoles usually do no virtualize and obfuscate, thus can be disassembled and analyzed statically. In addition, the game may share engine between PC and console and have same archives structure. Maybe this could be an alternative method.
But I can't find where to download a specific console version game.
## Post #57
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T20:22:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

This tool for ubisoft games is great, but as creator said himself he can't do nothing with encrypted for honor .forges, so I have no idea how it would help you even if it was open-sourced. I checked PS4 version already xD As I said I'm very interested in For Honor. PS4 version working great - but updates requires newer firmware, no one can dump a .fpkg yet, maybe when PS5 will be released, then PS4 version will do the job even without decrypted PC (though, not 100% since maybe they encrypted .forges in new updates, but unlikely) Tushkan, you mentioned about textures from siege, here what I did for extracted textures, after I made alpha maxsciprt for models. It's plugin for Noesis, greatest tool ever - I love it so much. Not only could you preview them, but you could batch process them to ALL needed 2d formats xD

[https://www.youtube.com/watch?v=K47_f6Z ... e=youtu.be](https://www.youtube.com/watch?v=K47_f6ZchEg&feature=youtu.be)
## Post #58
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T20:39:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from comword ↑Wed Feb 05, 2020 3:48 am at Wed Feb 05, 2020 3:48 am
>
> 
I am curious on your way of decrypting forge archives. I know the executable is heavily protected by BE, but I believe 3D related parts (model loading & rendering) can't be virtualized because of performance needs.
Where can I start analysis it without being able to run that executable?
Also, I found a tool https://zenhax.com/viewtopic.php?t=9138 published in 2015 can extract forge archive, but it is not open source.

1. Plain old bytes analysis. Load a bunch of forge headers in 1-per-row manner and start noting similarities and struct hints. Then proceed with guesses and tests.
2. When I tried to reverse actual forge unpacking via exe reverse, I couldn't find any particular parts of plain unpacking code. From what I saw they virtualize at least parts of unpacking routines. Maybe that's why siege takes so long to load ) The other issue is that i'm not that versed with asm reversing. I only use x64dbg, with minimal amount of analysis tools. Hell, I can't even use Scylla properly xD. And game gets an update each month and a half so I'm simply lacking in speed to crack it via reversing. I'd gladly read some literature on that matter or attend a webinar to get on par with the "industry"
 )
3. If you want to analyze without an executable, than you should analyze actual binaries, like I did. Or ask someone to decypher and dump an exe for you. But given the fact it's heavily virtualized... I doubt it's worth something.
4. Last time I checked it on actual data, that unpacking tool was out of date. Ubi changed parts of .forge archives and switched to zstandard compressor, so that tool no longer applies. There is a newer one, but it only dumps out files, no text data, no nothing. Plain unpacked binaries. But still it's better than nothing. Or maybe that tool got an update. dunno, never bothered to check.

> Reply from zaramot ↑Wed Feb 05, 2020 4:22 am at Wed Feb 05, 2020 4:22 am
>
> 
Tushkan, you mentioned about textures from siege, here what I did for extracted textures, after I made alpha maxsciprt for models. It's plugin for Noesis
O_o holy crap you work fast xD
## Post #59
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-02-04T21:19:15+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Feb 05, 2020 4:39 am at Wed Feb 05, 2020 4:39 am
>
> 
1. Plain old bytes analysis. Load a bunch of forge headers in 1-per-row manner and start noting similarities and struct hints. Then proceed with guesses and tests.
I have seen files in your Dropbox. They are not clear for understanding, and I didn't find forge archive structure analyzed.

Did you remember when Ubi changed .forge archives? Because I'm working on a season operation in old version game (about Mar - April in 2018). 

> Reply from zaramot ↑Wed Feb 05, 2020 4:22 am at Wed Feb 05, 2020 4:22 am
>
> 
Tushkan, you mentioned about textures from siege, here what I did for extracted textures, after I made alpha maxsciprt for models. It's plugin for Noesis
Really amazing, do you plan to share some of your work?
## Post #60
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-04T21:49:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from comword ↑Wed Feb 05, 2020 4:10 am at Wed Feb 05, 2020 4:10 am
>
> 
Really amazing, do you plan to share some of your work?

Sure, I'm mostly sharing stuff which I did or doing, with rare examples when it's just for my personal use only or not finished for end-user, not user friendly xD So, of course with siege I could post everything I did later on, so anyone could take a look and continue the process or just take it as it is.
## Post #61
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-04T21:54:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from comword ↑Wed Feb 05, 2020 5:19 am at Wed Feb 05, 2020 5:19 am
>
> 
I have seen files in your Dropbox. They are not clear for understanding, and I didn't find forge archive structure analyzed.

Did you remember when Ubi changed .forge archives? Because I'm working on a season operation in old version game (about Mar - April in 2018).

Afair they changed compressor somewhere between operation health and outbreak event. So you should be good. Of the most recent changes they modified depgraphbin structures, but it's not a very serious change (they seem to have split uint64 into [int32, int16, uint8, uint8]) and does not affect any actual data parsing. The other one is now I find string IDs for many basic structs like textures, meshes and havoks. I'm not sure wether those are reanny new, but I don't remember seeing them before. If your forge chunks are compressed with zstandard, then you're 'up to date'. You can actually send me some small forge file to test out if it unpacks.

And my dropbox is basically out of date. It's about year old, when lots of things were undiscovered and sources where messy. It's actually messy even now because it's a mix of jyputer notebooks, .md notes, test py files and actual core code. But at least core is more consistent and documented now.

I guess I should release this stuff on github in it's current state so people at least can get some info on structures and types... But zaramot's Noesis plugin looks alot more promising and comfortable. ) My stuff is designed to work from cmd or scripts and it's intended do gather extensive amount of data in one go. Say if you want a character, you should be able to run a search for some string like "Caveira" and grab it's mesh and from mesh grab it's asset struct and dump all that is needed at once in one folder (all meshes, textures etc.). I even found shaders per model, like if it would interest anyone xD...
## Post #62
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-05T10:48:24+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Feb 05, 2020 5:54 am at Wed Feb 05, 2020 5:54 am
>
> 
Of the most recent changes they modified depgraphbin structures, but it's not a very serious change (they seem to have split uint64 into [int32, int16, uint8, uint8]) and does not affect any actual data parsing. The other one is now I find string IDs for many basic structs like textures, meshes and havoks. I'm not sure wether those are reanny new, but I don't remember seeing them before.

Maybe some changes are happen with the game currently undergoing Vulkan API implementation? Which may forebode more changes as well.

> Reply from zaramot ↑Wed Feb 05, 2020 5:49 am at Wed Feb 05, 2020 5:49 am
>
> 
Sure, I'm mostly sharing stuff which I did or doing, with rare examples when it's just for my personal use only or not finished for end-user, not user friendly xD So, of course with siege I could post everything I did later on, so anyone could take a look and continue the process or just take it as it is.

I'm sure we all really appreciate your work on this zaramot, and for a game you're not highly motivated for. So you are able to extract meshes with UVs and weights, and textures so far. Did you plan to do further development for Siege? It sound like if this is combined with asset identification it'd serve many purposes already.
## Post #63
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-02-05T15:09:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Feb 05, 2020 5:54 am at Wed Feb 05, 2020 5:54 am
>
> 
If your forge chunks are compressed with zstandard, then you're 'up to date'. You can actually send me some small forge file to test out if it unpacks.

Here is the link, have a try. [https://www.dropbox.com/sh/sii6e34kymrk ... DBY3Qv2TUa](https://www.dropbox.com/sh/sii6e34kymrkgzl/AACb1BYKQODv47NDBY3Qv2TUa)
I believe these files are main parts of Outbreak, Operation Chimera as I viewed change log on SteamDB.
I found all my forge files start with a magic string "scimitar", and I found a BMS script can extract it to files. Files name are hashed.
Some extracted file started with 34 AA FB 57 99 FA 14 10 02 00 03 00 ... Have you seen this pattern before?
## Post #64
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-05T19:31:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from comword ↑Wed Feb 05, 2020 11:09 pm at Wed Feb 05, 2020 11:09 pm
>
> 
Some extracted file started with 34 AA FB 57 99 FA 14 10 02 00 03 00 ... Have you seen this pattern before?

Yes. [34 AA FB 57 99 FA 14 10] is a Container_ID. It denotes file It can hold uncompressed data (meta) and compressed (actual file split into compressed chunks). you can see those all over forges. They generally go in groups: one container for uncompressed metadata and emmideatly after that goes another with compressed file. It should go as:

```
uint16 = 2 // unknown
uint16 = 3 // unknown
uint8 = 0 // unknown
uint16 varying // unknown
uint32 num_chunks // how many data chunks are in this container
[chunk_size, chunk_size, ...]
[chunk, chunk, ...]
```

each chunk_size is a struct of:

```
uint32 compressed_size (actual chunk size that you need to read)
```

each chunk is:

```
bytes [compressed_size] //actual compressed data
```


The files that start emmideately with this header, are most likely depgraphbins. Those hold data about links between different entities. When you unzompress and concatenate all chunks (with zstandard), you will get a binary file, that starts with uint8 = 2 and then its a buncho if structs of type:

```
uint64 child_uid
uint64 child_type
```

In newer versions child_type now seems to be split into [int32, uint16, uint8, uint8]
## Post #65
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-06T01:18:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

well. Good news is your assets are inline with my tools. But there are no string hints so I'll have to continue at least some work on locating asset packs. Plus some types of meshes are still badly parsed. This is only a fraction of assets, there are lot more, but they are compressed with 0d24 bytes per vertex and they get teared apart on import.
[meshes.jpg](https://xentaxbackup.github.io/file/17465_meshes.jpg)
## Post #66
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-06T02:55:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tushkan, could so send me in PM of somewhere those compressed meshes? I haven't encountered this mesh type, since I have only few siege .forges, it's interesting.
## Post #67
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-06T08:40:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0](https://www.dropbox.com/sh/b2cuse4hp90ym0g/AADXaqKfyrCY9joUtsnlqTfja?dl=0)

There are the 7z archive (an old one) and the fury*.zip, (from outbreak). They contain unpacked mesh files. Site-packages folder contains the code to parse them. It's just a fraction of r6s module, but it should be enough to parse unpacked files. Just add an empty __init__.py into r6s folder, I forgot to do it myself. Usage:

```
mesh = Mesh.parse('path\\to.file')  # parses header data
data = mesh.getmesh()  # simple struct with 3 buffers: vetrs, tris, uvs
```


Bad_samples.txt contains names of files from fury archive, that are parsed badly. Those aren't all, just a fraction I've seen so far.

There are also folders with x## names, those should also contain samples of meshes with different compression, but I'm not sure, I saved those a year ago.
## Post #68
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-06T17:53:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tushkan, could you please make a screenshot of your version of imported 12538.mesh? I imported 12538.mesh from datapc64_merged_fury_bnk_mesh archive, that's how it looks like for me. I tried others from list of bad files, they are basically the same - some boxes and one I guess small floor piece. Or any other mesh, maybe bigger which looks not correct for you? I want to compare the outputs.
## Post #69
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-06T19:04:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

This is how 12528 looks in my case. There is a 1x1x1 cube for reference on the left. Strangely enough most objects of same compression type look just fine. But some get imported like that. Also I have hard time detecting lod bounds some times for some models everything looks fine, but for others two lods get imported simultaneously and, because they use same vertices, second lod messes up the first one. Also sometimes isnands count (number of separate shells per one lod) doesn't seem to reflect actual number of shells. They can differ +\-1 and that is causing that type of lod merging as far as I see. Can you show your algo on parsing those meshes? Or describe your working process on how you interpret data and search for buffers bounds?
[12528.jpg](https://xentaxbackup.github.io/file/17467_12528.jpg)
## Post #70
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-06T20:17:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey waaaaait a minute! There are ascii strings in it! I've never seen those before. My code wasn't suited to deal with them. So it reads data in all the wrong ways.

Edit:
Daaaamn, I'm an idiot. I checked the binary that actually was a python's pickle file. That's why it had strings. I'll go revisit the binaries. My question still applies then. How did you unpack the data for vertices? That's the most frustrating thing for me now. My algo works on most objects except for such rare exceptions.
## Post #71
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-07T01:46:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Finally...
I was expecting a struct of type

```
	[pos, pos, pos,...],
	[uv,uv,uv,...],
	[norm,norm,norm,...],
]

```

But it turned out to be

```
	[pos, uv, norm,..],
	[pos, uv, norm,..],
	[pos, uv, norm,..],
]

```

I was expecting that uint32 @ 0x2c controls those two types, but I guess I was wrong. I'll have to find another parameter, that is correlating with data ordering.
Our proportions seem to differ though, that's strange...
[12528_fixed.jpg](https://xentaxbackup.github.io/file/17468_12528_fixed.jpg)
## Post #72
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-07T02:32:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Looks pretty good already, I'm doing it a bit in a different way, I guess, since I have an experience with similar example before, not only with ubisoft games but with lost via domus (not exact but still) and with ghost recon: phantoms. It's hard, for me personally to decide which version is more correct - because of this simple box mesh, if it was some sort of vehicle, building - it would be easier to see which variant is correct!
## Post #73
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-07T07:59:22+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Well, I use

```
norm = 0x7f ff
s = s/norm
return x*s, y*s, z*s
```

This works well on other models and yields humanoid models to be ~1.7-1.8 units tall, which is an average human height.
But now I need to find how format regulates between buffers and struct sequences for vertex data...
## Post #74
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-02-08T01:03:25+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

It seems you people are getting results, but is there a chance the tools can be made public at some point? Also, is that Noesis texture script ready?
## Post #75
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-08T02:35:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

As I said previously, I am planning to share my tools. Only problem is they are going to require some skills from a person using it. It's python based and it's tailored towards scripted execution i.e. there is no gui.
## Post #76
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-08T19:11:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[https://youtu.be/tSNCstwSzq8](https://youtu.be/tSNCstwSzq8)
## Post #77
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-02-09T18:22:40+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sat Feb 08, 2020 10:35 am at Sat Feb 08, 2020 10:35 am
>
> 
As I said previously, I am planning to share my tools. Only problem is they are going to require some skills from a person using it. It's python based and it's tailored towards scripted execution i.e. there is no gui.Alright, well, have to see how complicated they are to use once they're public.
## Post #78
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-09T22:27:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm trying to document everything I do there. But you will still most likely need to write a script to grab the actual thing you want. Right npw the process looks like this:

```

with r6s.forge.parse('path\\to\\forge.file') as f:
	for i, e, n, c in f.files():  # loop through all files in forge archive
	# i - file index
	# e - file entry, has info about it's uid and offset
	# n - name entry, has info about its type and lots of less relevant data
	# c - file container (may also be hash or meta dict)
	meta_stream = c.meta.getstream()  # yields stream with unpacked meta data
	file_stream = c.file.getstream()  # yields stream with actual unpacked file
	# right now module doesn't select specific parser on the fly, so you have to make it manually
	with r6s.mesh.Mesh(file_stream) as mesh_handler:
		# mesh_handler holds parameters from model file. It includes vertex buffer length,
		# number of islands, all vertices and all lods
		actual_mesh = mesh.getmesh()  # this one yields 1 specific lod. This is what I import in blender

```


there are more comfy modules planned designed to ease up asset search and load to avoid fiddling with all that manual work. But that is not going to happen before I crack asset files and strings linking to make search by models names an option.
## Post #79
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-10T16:54:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from zaramot ↑Sun Feb 09, 2020 3:11 am at Sun Feb 09, 2020 3:11 am
>
> 
https://youtu.be/tSNCstwSzq8

Interesting, they must have separate sub-rig for head and for equipment points, maybe apart or together.


> Reply from Tushkan ↑Mon Feb 10, 2020 6:27 am at Mon Feb 10, 2020 6:27 am
>
> 
I'm trying to document everything I do there. But you will still most likely need to write a script to grab the actual thing you want. Right npw the process looks like this:
Code: Select allimport r6s

with r6s.forge.parse('path\\to\\forge.file') as f:
	for i, e, n, c in f.files():  # loop through all files in forge archive
	# i - file index
	# e - file entry, has info about it's uid and offset
	# n - name entry, has info about its type and lots of less relevant data
	# c - file container (may also be hash or meta dict)
	meta_stream = c.meta.getstream()  # yields stream with unpacked meta data
	file_stream = c.file.getstream()  # yields stream with actual unpacked file
	# right now module doesn't select specific parser on the fly, so you have to make it manually
	with r6s.mesh.Mesh(file_stream) as mesh_handler:
		# mesh_handler holds parameters from model file. It includes vertex buffer length,
		# number of islands, all vertices and all lods
		actual_mesh = mesh.getmesh()  # this one yields 1 specific lod. This is what I import in blender


there are more comfy modules planned designed to ease up asset search and load to avoid fiddling with all that manual work. But that is not going to happen before I crack asset files and strings linking to make search by models names an option.

What does making the parser manually entail? If scouring and cataloging some file data will help you out I'd be happy to give it some time.
## Post #80
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-10T22:42:15+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Right now it's based around manual parsing for 2 reasons: 1) it gives more flexibility. I can collect specific files and work on their raw data 2) it simply isn't finished to be as straightforward as possible =) . My main goal is to build complete models parser, complete skeletons parser  (thanks to zaramot for hints on skeleton data) and provide at least rudimental means of identifying specific assets by their names. After that I intend to release it as a module so anyone willing to make a neat gui can use my work as a basis. Or even translate it to other programming languages and build more refined tools.
As for manual data tagging, It might come in handy in reversing some of the unknown tags inside mesh files. I'll think about your proposal. The only problem is it might also involve some manual fiddling with data import in blender. If you're an animator, I suppose you work with some kind of DCC (maya?). Are you familiar with blender and some rudimental understanding of python syntax?
## Post #81
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-11T22:11:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I am familiar with Blender, and my idea of Python might pass for rudimentary. I've use a line or two of it making drivers, but it's not like I can differentiate api functions from vars 90% of the time in another person code. If this manual fiddling you speak of is such task of replacing a directory path, or swapping one var for another that's been notated then I manage.   

I was thinking that finding a few sets of meshes that we know belongs to the same asset could help uncover something through the data comparison, though how far you gotten with this is unknown to me, no reason to indulge me if I can't be put on a useful track.
## Post #82
- Username: KnownAzEpic
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 23, 2019 8:08 pm
- Post datetime: 2020-02-14T20:12:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Is it possible to extract the menu background images?
## Post #83
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-14T23:38:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yes. Those are just textures like everything else. Problem is identifying them.
## Post #84
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-17T21:55:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from comword ↑Wed Feb 05, 2020 11:09 pm at Wed Feb 05, 2020 11:09 pm
>
> 
Here is the link, have a try. https://www.dropbox.com/sh/sii6e34kymrk ... DBY3Qv2TUa
Small node about your archives. I couldn't find any pointers from beast mesh to it's asset file. What this means is there are 2 options:
1. Mobs aren't stored as an operator asset
2. You missed some .depgraphbin file when you were backing up outbreak assets, so now I'm lacking linking data between assets.
I think it's the second one (can be proved on current full game build but I hadn't had enough time to check). What does it mean: either I will scan through all asset files and will find links there or you will be bound to manually skim through all meshes and textures to assemble the model back. Or you will be able to find another enthusiast that managed to store all necessary depgraphbins.

On the bright side, I almost ended unpacking data for meshes (normals done, vert colors done, uvs done thanks to zamarot, skinning is next in queue). Next up will be asset's skeletons (again, thanks to zamarot for data section hints).
## Post #85
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-17T22:18:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

NNNNNOOOOOOOO!!!! I just found out from their update notes that they are going to restructure game data. Why?! WHY?!?!?!

Edit: checked the TTS game version. They have indeed changed file format. But it's not that severe. They seem to pack meta and file data into one block now, so file headers have changed. But overall forge structure is the same (except for file type link but it will be easy to fix), compressor is the same, models are the same. Will have to see how they handle assets. I guess I will catch up fast enough. Only problem is I will shift onto new format and stop working with older forge archives. I still can decompress them, but at some point api might diverge and not all tools will longer apply to both newer and older forge versions.
## Post #86
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-18T03:07:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yikes   

Btw we can guess that those Operation Chimera creatures and more is going to be in the Rainbow Six Quarantine, so that might providing a better source for that stuff. With a bit of luck it could end up being very relatable in the files to Siege.
## Post #87
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-18T07:44:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Well as long as they don't decide to encrypt it like in for honor. And someone provides game resources. Because I don't think I'm going to buy it )
## Post #88
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-02-19T16:41:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Tue Feb 18, 2020 5:55 am at Tue Feb 18, 2020 5:55 am
>
> 
2. You missed some .depgraphbin file when you were backing up outbreak assets, so now I'm lacking linking data between assets.
I think it's the second one (can be proved on current full game build but I hadn't had enough time to check). What does it mean: either I will scan through all asset files and will find links there or you will be bound to manually skim through all meshes and textures to assemble the model back. Or you will be able to find another enthusiast that managed to store all necessary depgraphbins.
Hi, I am really busy these days and very glad to see your progress. I found that my dropbox was full, and may result in missed depgraphbin.
This is all depgraphbins:

```
./datapc64_fury_d01_resort.depgraphbin
./datapc64_fury_d01_resort_p2.depgraphbin
./datapc64_fury_d02_hospital.depgraphbin
./datapc64_fury_d02_hospital_p2.depgraphbin
./datapc64_fury_d03_junkyard.depgraphbin
./datapc64_fury_d03_junkyard_p2.depgraphbin
./datapc64_pvp10_chalet_set02.depgraphbin
./datapc64_pvp11_university.depgraphbin
./datapc64_pvp12_russiancafe_set02.depgraphbin
./datapc64_pvp13_border.depgraphbin
./datapc64_pvp14_favela.depgraphbin
./datapc64_pvp15_temple.depgraphbin
./datapc64_pvp16_ibiza.depgraphbin
./datapc64_pvp17_themepark.depgraphbin
./datapc64_pvp19_tower.depgraphbin
./datapc64_r6_menuworld_playgo.depgraphbin
./datapc64_ui_playgo.depgraphbin
./datapc64_ondemand.depgraphbin
./datapc64_ondemand_fury.depgraphbin
./datapc64_ondemand_playgo.depgraphbin
./datapc64_ondemand_set01.depgraphbin
./datapc64_ondemand_set02.depgraphbin
./datapc64_pvp01_house_v2_set01.depgraphbin
./datapc64_pvp02_oregon_set02.depgraphbin
./datapc64_pvp03_hereford_playgo.depgraphbin
./datapc64_pvp04_clubhouse_set02.depgraphbin
./datapc64_pvp05_plane_set01.depgraphbin
./datapc64_pvp06_yacht.depgraphbin
./datapc64_pvp07_consulate_set01.depgraphbin
./datapc64_pvp08_bank.depgraphbin
./datapc64_pvp09_kanal_set02.depgraphbin
```

[https://drive.google.com/file/d/1EGeIBr ... sp=sharing](https://drive.google.com/file/d/1EGeIBrFnOWcii9pPyVwW6QwFqCUJmjM_/view?usp=sharing)

> Reply from Tushkan ↑Tue Feb 18, 2020 6:18 am at Tue Feb 18, 2020 6:18 am
>
> 
NNNNNOOOOOOOO!!!! I just found out from their update notes that they are going to restructure game data. Why?! WHY?!?!?!

Edit: checked the TTS game version. They have indeed changed file format. But it's not that severe. They seem to pack meta and file data into one block now, so file headers have changed. But overall forge structure is the same (except for file type link but it will be easy to fix), compressor is the same, models are the same. Will have to see how they handle assets. I guess I will catch up fast enough. Only problem is I will shift onto new format and stop working with older forge archives. I still can decompress them, but at some point api might diverge and not all tools will longer apply to both newer and older forge versions.
You can try to use different parts of unpacking code based on conditions and try to support different game versions. If this is too complex, try to use version control like git to snapshot your code for older forge versions.
## Post #89
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-19T18:44:15+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Fury_ondemand seems to be the vital one that is missing.
I stashed the old parser for now to keep the code. I don't want to introduce versioning inside existing repo right now because I want to focus on actual data parsers. I might introduce version recognition later. Or simply unpack the data and sent it back to you so you can work with it.
## Post #90
- Username: benchmark7770
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 24, 2019 9:56 pm
- Post datetime: 2020-02-20T05:24:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey  Tushkan,
First of all thank you for your time and effort you are putting into this, i have a question do i have to keep the mesh.rip data that i extracted via ninja ripper or is it all ruined already and of no use, bcs of how the mesh is broken, when it is imported into noesis?
## Post #91
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-20T21:21:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I haven't used the ninja ripper so I don't know what type of data you have. I'm pretty sure if it's actual model data than it can be interpreted and parsed. The other question is whether there is any sense in trying to convert it when there is some decent progress on unpacking tool.
## Post #92
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-21T17:12:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I followed along with process of ripping Mass Effect Andromeda, which was mainly one guy who was passionate and skilled. Took him ages, then he finished and suddenly those big tools had the ability to rip Andromeda, they had taken his work wholesale and used it line-for-line in the code. Just saying those big tools don't run on magic that can access all kinds of data that it hasn't solved before, may be Ninja Ripper will suddenly be able to work on Siege if Tushkan gets the result. It really put that guy off helping any more too, bad lack of respect and community spirit than he had expected.
## Post #93
- Username: ImEnFuego
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 24, 2020 12:14 pm
- Post datetime: 2020-02-24T04:20:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey guys! I'm so glad to see you working on this, as a 3d artist I'm really interested in this and if you need any help I'd love to, my coding skills are pretty much none but I can provide game files, create shaders for the models or whatever. Keep it up legends
## Post #94
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-24T21:58:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

God samples of new metas. Doesn't seem to be zstandard as for general .forge chunk packing. Maybe enyone by chance can identify the compressor?

```
          datapc64_merged_set02_bnk_meshshape.forge   2231   FF 60 FA 6B 30 80 D1 5F 68 A7 7A DC 9D C1 24 53 37 19 11 66 9C 2C C3 42 C4 80 92 2C 8A 70 45 87 99 E0 0F FB AC 92 FA 99 1A
                datapc64_ondemand_cn_bnk_mesh.forge    249   7C 16 35 03 90 6C 21 0B 27 B2 B2 A0 80 BB 8F 58 BA 1F 27 63 BD D2 1A 65 11 59 F0 3C
               datapc64_merged_set02_bnk_mesh.forge    993   73 4B A6 5C 98 6D 13 17 EC B0 4C EB 80 BD 8F 7D AE 38 D3 B8 83 EC 3C 52 72 A9 5F 71 96 1D 85 4B 30 3B 5A D3 91 53
               datapc64_merged_set02_bnk_mesh.forge   2417   E2 30 EA 73 30 40 0F 3B 6A 88 57 E9 8F BD A4 53 39 E1 CE 9D 9C EA 34 48 C6 46 85 16 DB 6C 85 4B B5 F3 50 FE A0 53
                     datapc64_merged_bnk_mesh.forge  16501   D3 C3 A3 C4 10 40 05 1A 81 76 1B 18 4C 80 92 5F 43 CC A9 CB 7B DC 20 51 1B 3D 51 8E 6A 00 9B 58 8A B9 CB 11 41 6D 3E 89 42 3A 32 9D A0 92 AC 90 5F 50 2E 4F
                     datapc64_merged_bnk_mesh.forge  36563   DD 2D F0 FE 20 40 05 1A 8B 50 4E 67 40 80 93 5B 43 E6 01 1A 6A FB 3C 4F E4 67 93 8D B2 11 99 48 99 93 0A 65 B1 2E 00 AD 6A
                     datapc64_merged_bnk_mesh.forge   5087   CB 86 7A 3E A0 6C 23 37 BE 08 D6 CD 8C EF E5 02 07 AF 48 5D
                datapc64_merged_bnk_meshshape.forge  12956   D8 06 A2 8D 37 80 DB 74 8E BB 1D 41 55 C0 55 40 5E 3A A4 09 96 30 F9 73 21 59 60 93 A8 5F 7E A6 B9 F3 FD 69 B3 B1 C9 8B 6F 65
          datapc64_merged_set02_bnk_meshshape.forge   6611   5D BE 3F E8 64 91 C6 65 25 C1 9F 51 76 F6 67 44 8F 13 26 0B 41 1E C3 35 7D E7 EF E2 5E 76 73 8B 11 0F 77 79 50 92 F6
                     datapc64_merged_bnk_mesh.forge  23151   79 8C 0E 87 C7 41 05 1A 2F 31 8D 41 B2 81 A4 5B AF 6E 57 11 B0 DF 0A 73 5D D1 E9 DD 80 01 9B 32 2E 67 4A 50 D0 41 1C A3
                     datapc64_merged_bnk_mesh.forge  33985   B3 06 5C 8A C6 7D 5C BE 16 BB DE 5C F7 BD EC FF D6
                     datapc64_merged_bnk_mesh.forge   6526   E6 DB 37 2B A8 4B 1E 0B 43 4B BF A4 97 AB B5 7E 36 CD 5D 7C 9E C1 07 63 E3 20 C1 1D 88 1F EE 58 BB A9 4D E2 90 5D 12
               datapc64_merged_set02_bnk_mesh.forge  13194   05 3F F4 C2 B7 50 18 0B DC 41 71 AA A1 BF A4 5F 94 E8 F8 2B B0 DF 0A 73 7A 71 85 C2 80 01 9B 32 D5 87 2F BF EF 41 1C A3
          datapc64_merged_set02_bnk_meshshape.forge   7218   52 54 37 DE 31 80 D1 4F 27 E2 BF 2B A5 C9 76 4D CA 75 75 EB 86 2D F5 63 9D E1 E1 C4 B5 56 48 BC 2F 20 4E 22 8F 81 E8 87
               datapc64_merged_set02_bnk_mesh.forge   8130   BC 06 9C DE A4 27 64 BE 15 AF 13 AB 94 61 E8 C9 EE F5 8E 73 97
                     datapc64_merged_bnk_mesh.forge  40050   BF 06 2C F3 17 C5 31 BF 12 BF D8 71 36 3F 84 F0
                datapc64_merged_bnk_meshshape.forge  23741   0A D9 67 F8 06 80 DB 74 F8 7C F2 74 78 C0 25 67 A1 FB 45 2B 64 33 F3 68 22 1F 00 BA 7E 40 62 81 C4 86 B8 43 50 B0 D7 A6 9D 10 28 0C 47 D0 79 E4 07 56 F9 BC 51 3A DC E2 F7 F1 45 60 AF
                     datapc64_merged_bnk_mesh.forge  33934   10 54 7E BD 36 40 09 0C C6 C9 D3 A3 BC 81 83 52 8B 45 75 57 96 F9 07 40 58 D8 0F CA A7 31 B5 63 CA 36 B5 81 B7 52 10 AA EA B8 7E 09
          datapc64_merged_set02_bnk_meshshape.forge   1298   77 69 09 00 18 80 C6 48 18 BA AC C5 57 EC 72 54 A6 38 60 AF 49 19 F0 68 72 8E C6 43 66 7B 7E AF 30 D8 96 DC 6E AC E6 BB AD 7B 24 B5
              datapc64_merged_playgo_bnk_mesh.forge   2208   DF 92 6A 4D A2 57 00 0B BB 31 C7 0D A4 B1 A6 5F 4C AC 50 9E 8D DC 13 53 F1 E0 24 5B EA 01 96 48 A6 2B BA 2C 9D
                datapc64_merged_bnk_meshshape.forge  15900   B1 A8 D8 EB 2B 80 D7 42 47 CC A1 58 71 F3 7B 7E D7 48 33 EE 53 12 FD 6E B9 E4 87 80 4C 76 73 8B 5A 13 40 5B A2 93 F6
                     datapc64_merged_bnk_mesh.forge  12267   FF 61 BB 0E C5 41 09 0C 55 93 02 D2 A1 81 93 5B 21 33 DB 8A 80 F0 0A 67 D7 95 4A 23 85 1F 85 4B B8 CC A1 C2 91 53
               datapc64_merged_set02_bnk_mesh.forge  14013   02 7B 28 66 4F 49 1C 64 99 99 AE F1 79 BE BC 65 A1 39 3D 8D 6A F1 0A 64 29 86 CB 4C 61 29 BF 58 D7 DC 6C D8 43 50 13 B1 BA 55 CA 9C 99 B9 BC 96 08 95 AA 09 BE DA 58 E4 CF 0D
               datapc64_merged_set02_bnk_mesh.forge  14256   AB 19 40 72 6F 51 18 0B 77 BF 33 DB 48 BA BE 4E F9 E9 80 AF 7F F0 3B 7E A3 46 07 7C 4B 6F 85 44 79
              datapc64_merged_playgo_bnk_mesh.forge   1330   4C 64 67 F7 DE 41 03 07 31 F5 D3 5B B9 8A A2 5F A5 49 B5 39 91 DA 65 7E 51 82
                     datapc64_merged_bnk_mesh.forge  29987   7D DF DC C1 59 51 18 0B CA 7B AE AA 5A B0 A5 54 BA 96 04 2F 6D FA 06 4C 51 3B A3 FB B8 01 88 45 C4 99 59 9B AE 5F 69 B1 98 30 E6 63 B5 9D AE
               datapc64_merged_set01_bnk_mesh.forge   3725   DF 62 D0 A6 5C 51 18 0B AE FE 44 0E 5E B0 A4 65 7D 0F 23 EA 40 ED 34 46 D1 A5 E9 A0 B2 11 9E 37 BF 3B 09
                     datapc64_merged_bnk_mesh.forge  30305   7D DD 2C 04 42 51 18 0B CA 79 9E ED 42 AD BD 79 B6 A1 5C 78 A3 DF 0A 73 72 13 ED 00 93 01 9B 36 B4 B6 44 F6 A8 2E 00 AD 99
                     datapc64_merged_bnk_mesh.forge  34200   BF 06 8C 67 E1 93 40 BE 12 BF 38 E2 C1 E9 FB F1
                     datapc64_merged_bnk_mesh.forge  22783   8E D2 2D A6 1C 40 05 1A 64 46 A3 AB 5E 80 9F 48 EB CA 31 2B 7F DD 3C 53 B0 32 E5 DC 51 11 95 44 69 9A 7C A7 44 59 2D 8F 1F 35 CF 78 A0 92 AC 90 FA A1 B5 EE
                     datapc64_merged_bnk_mesh.forge  14716   B4 99 9C 35 30 40 05 1A 62 3B 70 09 AF 81 83 4E E9 96 FB EC B4 C1 07 63 9C FE 68 6C B1 1F ED 58 60 6E 37 52 B9 5D 12
                     datapc64_merged_bnk_mesh.forge   5850   9B E7 91 06 C4 41 05 1A 49 19 6D DB B8 81 92 5B 1D 8E F5 87 8E FB 0A 62 9E 3C BC 7A A9 3F BD 58 52 32 5E CB 9F 51 1B DE 3A D4 9C
               datapc64_merged_set01_bnk_mesh.forge   4332   02 74 7E D5 47 50 19 0B CE BB FA 95 44 BE A3 5F B0 23 A2 6A 42 D9 27 40 26 A8 27 A1 C0 01 96 48 D7 BB 8F A4 BD
              datapc64_merged_playgo_bnk_mesh.forge   2954   64 A4 C6 C4 6F 78 29 20 DA D8 8A 90 6F 80 82 5F BE 4D 33 3B 8E FD 30 7E 6D DD CE C7 9B 27 BF 63 24 7D 1C 33 B2 4C 1D A8 BF 81 F6 05 A4 EC D1 8B 53 3A BF 81 82 DD 25
               datapc64_merged_set02_bnk_mesh.forge  10654   B5 57 AC 36 30 40 05 1A 63 C9 21 1A 42 80 80 56 E8 44 BB D3 8B D6 34 4F BC D7 56 69 AD 1F 85 55 6F 15 D0 04 8D 41 1E DF 4F B8 47 F2 A6 EE BC 97 9C
datapc64_merged_set02_bnk_014061302_meshshape.forge    104   AF 52 77 3E E0 89 74 D6 62 8F 07 C8 D6 C9 D3 E7 C0 10 B7 42 CD
                     datapc64_merged_bnk_mesh.forge  30770   F6 C7 2F 25 6B 6D 21 0B AA 1F 85 97 5D 9C B8 53 27 A8 60 BA 88 F1 26 55 D2 39 C0 27 96 01 96 48 AD D9 4D E8 A6
               datapc64_merged_set02_bnk_mesh.forge   6350   21 BE 78 38 AB 52 09 0B E8 E5 F2 D7 89 8D A4 5B 78 70 6F 78 80 DD 0A 73 1C EB 1B 0C B0 01 9B 36 EF 0D 9C 80 FF 41 1C A3
                datapc64_merged_bnk_meshshape.forge   2619   25 F9 6D 07 5B 8C E6 5B AE 31 B4 D7 B8 DB 44 75 46 9A 6F B2 B6 18 EE 66 0C 33 DB 0F B2 52 6E AA 8D 5F 47 E0 89 81 E8 87
                datapc64_merged_bnk_meshshape.forge   6371   35 B8 EF F3 55 AD FD 59 9C DE 63 71 9A A7 23 17 4A 61 EE 37 A9 13 CF
```
## Post #95
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-25T18:36:22+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

oryx_mom.jpg (75.39 KiB) Viewed 294 times


Well, something went wrong xD At least now I do have links per each npc. Strangely enough they have different magic from operator's assets (this one has 0x971a842e while assets have 0x22ecbe63). I hope inner structures will be the same. I'm planning to polish out mesh parser on older models before migrating onto newer assets and modifying the core code. Maybe someone will manage to identify meta compression by that time. I also checked tts exe with x64dbg, it still seems to import mainly zlib for compression but it won't unpack those metas.
## Post #96
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-26T13:21:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

This guy was working on a handler for Anvil engine files: [https://zenhax.com/viewtopic.php?f=9&t=9138](https://zenhax.com/viewtopic.php?f=9&t=9138)
His data tool includes lzo2 library in addition to zstandard. I can't verify if his tool decompresses those metas so far, I might be able to do so later.
## Post #97
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-26T17:58:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Afaik lzo was used as main compressor in siege in first years. Then they switched to zstd. It's still worth a try though.
Right now Im having troubles with that mesh I posted earlier. Siege's triangle indices come in 0x180 long blocks. If block ends with valid triangle (3 unique indices) then you can proceed. If there is an invalid triangle (say, [5, 5, 5], ie all 3 angles point to the same vertex) then it means this is an end of a triangle island. These are used for separate objects (pouches, armor, helmet) as well as for separating lods. And generally, for pouches and stuff, you have a chain of triangles, then a boundary (via invalid triange, it gets duplicated till the end of 0x180 block) then it continues from some arbitrary vertex id for the next element. In case of a lod it drops back to 0, 1, 2 and other lower vertices. But in case of that beast, it something fishy is going on. It has 5 body parts and 6 lods. So it's 5*6=30 separate triangle islands. And you would expect first 5 islands to travel all range of vertices than drop to 0 for next lod. But here EACH island drops to 0. So all parts except for first one or it's lods end up messed. It looks like it expects me to cut my 70k vertex buffer into 5 parts and use each one per body part. Each separate vertex buffer would start again from 0 so triangle islands would fit. But I have no clue on where to cut those buffers and if my guess is right at all...
Did anyone encounter similar problems in ubi models?
## Post #98
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-02-27T22:53:01+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

6 LODs seem high, considering how tight those levels were. Is that typical on Siege character? And five body part seems low. For this creature in particular, he kinda looks like he's made of separated armor pieces? Just a passing observation of no particular validity.



By the way, can I ask what do you use to examine extracted files in their raw form, is it just the python console?
## Post #99
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-02-28T07:55:35+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Part separation is nominal. It isn't an island per limb. It goes in groups. On my screenshot you can see legs' and shoulders' armor pads. That all is the first 'island' in that model. Uslands most likely separated by material id, not by triangle connectivity.
And yes, they have up to 5-6 lods, that's 100% positive. There are even youtube vids with fails where menu would load with the lowest lod and Clash would look like a minecraft character.
My research process is this: I unpack a mesh.forge, I build a script inside blender that utilizes my parser. I build meshes and print stats directly in blender. On each execution blender updates imported modules to account for changes in my module. All this is accessible in my dropbox which I posted previously for zaramot. You can download it and play with it. You'll need a blender 2.82 for that and you will also need to fix sys.path.append part of the sctipt to your local path to the modules.
## Post #100
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-04T00:05:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

beast_parts.jpg (132.56 KiB) Viewed 199 times


Finally found where block headers are stored and how offsets are organized. These are all the pieces from this mesh file (head is stored separately). Strangely enough I still don't see any value describing the amount of LODs in mesh which is odd. But I guess I should just fig a bit more.
## Post #101
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-05T08:45:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I was having a play with some stuff from your Dropbox. None of the scripts there include any call to sys that I could find. At this point I'm not sure that other dude's extraction tool is working properly for any of the mesh.forges, which complicates my tests. I tried to get some of your unpacked files for cross-examination, and rather unhelpfully Dropbox gives me a generic download error for all those ones, not sure why. This is a bit of a silly round-about way to try and check the unknown compression type, easier done in your own decompression script I expect.
## Post #102
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-03-05T09:42:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello guys, I'm new on this forum and also to this kind if stuff in general.

Looking through this thread I wasn't able to find any information on Operator hitboxes, so are those exportable and if yes how? Any help/information would be useful and much appreciated.
## Post #103
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-05T13:52:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Thu Mar 05, 2020 4:45 pm at Thu Mar 05, 2020 4:45 pm
>
> 
I was having a play with some stuff from your Dropbox. None of the scripts there include any call to sys that I could find.

sys module is referenced inside blend file. If you open the blend scene and navigate into Text window, you will see a script that actually imports the meshes. It relies on my module so it gets hooked up via sys.paths hack. I just tried to download a random mesh from exports folder and it seems to work. Permissions also seem to be fine. Let me know if the problem persists. Also keep in mind that dropbox scripts are a bit out of date. I update them manually each time I reach a milestone in mesh extraction.
If you don't want to use blender for some reason, let me know, I'll show you an example script on how to extract data into some readable form. You can also PM me your discord id in case you need some immediate help.

> Reply from floxay ↑Thu Mar 05, 2020 5:42 pm at Thu Mar 05, 2020 5:42 pm
>
> 
Looking through this thread I wasn't able to find any information on Operator hitboxes, so are those exportable and if yes how?

Those seem to be stored in meshshape files. each meshsape.forge is basically a heap of havok binaries. So you can unpack it with a forge extractor and then convert to xml with tool from Skyrim modding community. However, there are no clear indentifiers for those binaries, so good luck eyeballing 10000's of files. )
Also, I can be wrong on that one actually. I see some strange extra data in 1830 mesh that really resembles another vert\tri buffer. That might turn out to be an actual hitbox mesh.
## Post #104
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-06T08:03:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Aha, it did not cross my mind the .blend file was part of it, thanks for the help! It's making a lot more sense now. I got some results pretty fast but I seem to have a user error. Testing on the helicoper object (9120.mesh); The properly parsed one is already exist in the .blend file, the one below it is my result. I draw pink arrows to my changes, the 9120.mesh file was put in the Meshes folder, and I just hit "Run Script" for this script. So it seems to find it okay, and do something to turn it into an object, but I'm missing something. No complaints or errors in the system console window to give a hint. I'm not sure how that "Usage" code you posted is to be used, it didn't like being run in the console when I tried that. 




blenderprscr1.jpg (169.13 KiB) Viewed 137 times



Btw Dropbox seemed to disagree with my VPN, turning that off solved the download errors. Not a usual problem so I didn't think of it at first.
## Post #105
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-06T09:10:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Your edits are completely valid. The mesh is broken for another reason. I can't see the actual blend code, but chances are there is a mesh.getmesh(1) or mesh.getmeshraw(1) in there. It tries to import the second submesh from the binary. Problem is, this functionality was reversed by me on the smasher 2 days ago and is not yet implemented in your version or parser. You can change the code to mesh.getmesh(0) to parse the shell that is alreaty present in blend file. In your case it will also have extra data (normals). I will try to implement shells parsing by monday.

> Reply from Custard ↑Fri Mar 06, 2020 4:03 pm at Fri Mar 06, 2020 4:03 pm
>
> 
I'm not sure how that "Usage" code you posted is to be used, it didn't like being run in the console when I tried that.

What console do you mean? if OS' cmd interface, then it won't run there because import script relies on bpy module which is strictly blender-specific. If in blender's python console, then it should run if all script is copy-pasted there, including imports etc (IIRC "Run Script" button and blender console run in different scopes, i.e. they don't share imports or variables). Hitting "Run Script" is actually the way to go.

Also, here is a little rundown on how things are built in r6s module:

r6s.mesh has 2 main classes and a couple utilitary functions. Classes are:
1. Mesh - this is a wrapper for mesh binary. It parses header, stores "pointers" to where vertex\tri data starts.
2. MeshData - actual geometry data container. It's basically a struct with a bunch or arrays (for verts, norms and tris). I should have used a simple dict probably to make it more portable but oh well, that is a subject for future changes.

To get MeshData, you spawn a Mesh and then run Mesh.getmesh(submesh_number) (submesh is what I occasionally call an island, can't settle my naming habits XD )
This extra step is necessary for 2 reasons: importing different LODs and researching the mesh. I might remove it in future.

Now, how do we build an actual mesh from MeshData in blender? This is where r6s.blnd comes into play. It's basically a set of helper functions to make code inside blender less bloated. Main functions that get used are build_mesh(MeshData) which builds and returns actual blender mesh (bpy.types.Mesh) and link(bpy.types.Mesh, collection) which links a given mesh object to the scene so you can see it on screen. There are also some minor helper functions like purge (which doesn't actually purge because it's poorly written xD), render_as(image_path) which saves a viewport snapshot to given location etc. You can read source code to get an understanding of what they do.
## Post #106
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-07T10:53:00+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yup, setting submesh number to zero solved it right away, it's putting out proper meshes.   


> What console do you mean? if OS' cmd interface, then it won't run there because import script relies on bpy module which is strictly blender-specific. If in blender's python console, then it should run if all script is copy-pasted there, including imports etc (IIRC "Run Script" button and blender console run in different scopes, i.e. they don't share imports or variables). Hitting "Run Script" is actually the way to go.

I meant Blender's internal python console, sorry wasn't clear. It seemed like an import issue since it was failing due to functions "not existing", but if I'm understanding you right that code doesn't need to be used anyway, when running test_mesh_parms does the job instead.

Examining Mesh class I can see a fair bit of WIP in there. If I wanted to print out a mesh header to view, is that accommodated for?

Attempting to parse files unpacked by the Delutto unpacker throws a decode error:
File "S:\Tools\Blender\2.82\python\lib\site-packages\r6s\common.py", line 8, in __init__
    self.name = r.read(name_len).decode('utf8')
UnicodeDecodeError: 'utf-8' codec can't decode byte 0x95 in position 8: invalid start byte
I got the same outbreak .forge from comword's dropbox and extracted and processed a mesh file that was the same as one I already had from your dropbox, all I could tell was the contents of the two were not the same. Guessing it's either output bad data, or ins't compatible in some other way. Not much incentive to continue with that path as you've solved unpacking separately, unless you got some simple idea that fixes it.
## Post #107
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-07T11:10:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

My tool expects a raw uncompressed file data from forge. These files always have a container wrapper around them that has their magic, size and optional string and then uid. The failing code from Common parses that data. Now there are the following options:
1) denutto's unpacker unpacks data and rips away that header. So common tries to read actual mesh data as utf-8 string and fails.
2) denutto's unpacker is up to date with recent file structure change (where they now store packed metadata in that wrapper instead of string) so my wrapper reader tries to interpret packed meta as a utf8 string and fails. I need a file sample in order to get to the bottom of the problem. You can share it somehow or again PM me the discord id, that will make turnarounds faster.
## Post #108
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-08T07:54:12+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The version of the tool I got is from late 2018, I'm not aware of a later version and it's not being developed anymore (and was never really considered finished at the time). Now that you mention it, neither this version of your parser or this unpacker tool are going to work right with my current version of the game, which is what I was planning on investigating those compression types on. Or are those structure changes only in the TTS right now? I might have a few days to save a copy.

I put two Delutto unpacked files in dropbox.
9120 is that helicopter mesh from that outbreak forge, I just picked something that could be compared.
2231 is from current live version of the game — datapc64_merged_set02_bnk_meshshape.forge from which you indicated compression issue. If you can tell if this has been properly decompressed it means it's probably using lzo then. His tool also uses Oodle library, bit of a questionmark for me there trying to find out about it but I think it's used for image compression.

[https://www.dropbox.com/sh/gusxvns2h6j2 ... pdQGa?dl=0](https://www.dropbox.com/sh/gusxvns2h6j26b0/AAANCAKjUm03zK2O7sVLpdQGa?dl=0)

And yeah it outputs a weird file extension that makes it look like a script error..

Thanks for the Discord offer. Slow pace is suiting me at the moment, I hope not to be inconvenient to you.
## Post #109
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-08T09:17:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tts has the updated storage format. Current official build (that has wamai an kali introduced) still has the old format that I reverse. So yes, you can grab a copy of it. My parser should be easily adjusted for new forges except for metadada. I still don't know how they pack it but I can simply skip it.
I'll take a look at your sample soon, thanks.
Discord is alot more handy to my liking because I always have it online and it supports small file and image sharing. But forum is more transparent for people in terms of following the progress so I won't insist )

Edit: Oh, it's easy ) Denutto's unpacker works. You just unpack the wrong forge ) meshshape.forges store havok data. r6s.mesh expects data from mesh.forges so you have to unpack datapc64_merged_set02_bnk_mesh.forge And ignore the file formats. he uses magic as a file format, he just seems to parse it as int instead of uint so you get the minus. If you convert -1842221553 back to bytes, you will get 0F EE 31 92 which is the magic number for havok files. This also means last version of Denutto uses zstd, not lzo. Otherwize it wouldn't be able to unpack the data.

Grab a sample from mesh.forge and put it onto dropbox. I still have suspicion that he trims the header of a binary. If that's the case, you'll have to make a slight modification in r6s.mesh to make it work.
## Post #110
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-08T17:47:02+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Updated site-packages and .blend scene. In theory it should import more stuff correctly. But right now I only tested it on a Smasher (1830.mesh). Imports all islands for given lod, assigns materials slots per island, assigns uv. Any unknown data is mapped onto vertex colors. Right now there are 4 or 5 channels for smasher, I guess those are skin weights but I can't seem to grasp how they are packed. mesh object now also contains additional metadata per island. I can parse it but I can't understand what it's meant for in some cases (for example Mesh.island_bboxes is a bad name, it's not a bbox). I have found some other extra data which I will post later, maybe someone here will be able to solve it.

EDIT:
Fixed a bug with zero length islands that would lead to an exception. If anyone has downloaded new script, redownload mesh\__init__.py. Be aware, there might still be plenty of bugs.



full_mesh_import.jpg (89.38 KiB) Viewed 202 times
## Post #111
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2020-03-09T16:18:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Mon Mar 09, 2020 1:47 am at Mon Mar 09, 2020 1:47 am
>
> 
Updated site-packages and .blend scene. In theory it should import more stuff correctly. But right now I only tested it on a Smasher (1830.mesh). Imports all islands for given lod, assigns materials slots per island, assigns uv. Any unknown data is mapped onto vertex colors. Right now there are 4 or 5 channels for smasher, I guess those are skin weights but I can't seem to grasp how they are packed. mesh object now also contains additional metadata per island. I can parse it but I can't understand what it's meant for in some cases (for example Mesh.island_bboxes is a bad name, it's not a bbox). I have found some other extra data which I will post later, maybe someone here will be able to solve it.

EDIT:
Fixed a bug with zero length islands that would lead to an exception. If anyone has downloaded new script, redownload mesh\__init__.py. Be aware, there might still be plenty of bugs.
full_mesh_import.jpg
I didn't see same result in .blend as the photo, which is much more smooth and complete than export/outbreak_models.blend, also this monster is called Apex. I guess some of unknown data is reflection or diffuse or light emission. You can see some parts of their body are red glowing. In addition, have you tried to unpack textures?
## Post #112
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-09T17:39:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I know that's apex ) I used him to test for a bug and I added him after I edited the original message.
If you use latest scripts, your imports must also contain multiple isnands per char and smooth normals.
Glow is most likely stored in textures, not vertex color. Judging by Apex' fingers those are most likely skin weights. I just need to figure out the packing.
Yes, I can unpack textures. Main issue is tracking the ones that belong to an asset. For that I need to turn back to reversing asset structures.
## Post #113
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-10T06:43:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sun Mar 08, 2020 5:17 pm at Sun Mar 08, 2020 5:17 pm
>
> 
Edit: Oh, it's easy ) Denutto's unpacker works. You just unpack the wrong forge ) meshshape.forges store havok data. r6s.mesh expects data from mesh.forges so you have to unpack datapc64_merged_set02_bnk_mesh.forge And ignore the file formats. he uses magic as a file format, he just seems to parse it as int instead of uint so you get the minus. If you convert -1842221553 back to bytes, you will get 0F EE 31 92 which is the magic number for havok files. This also means last version of Denutto uses zstd, not lzo. Otherwize it wouldn't be able to unpack the data.

Grab a sample from mesh.forge and put it onto dropbox. I still have suspicion that he trims the header of a binary. If that's the case, you'll have to make a slight modification in r6s.mesh to make it work.

Oh, I seem to have misunderstood something. When you posted that list prior.. uh, [this one](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=90#p160305), I thought that was pointing to the location of some files that you weren't able to decompress with zstd. I didn't actually try to put the meshshape file through the parser, I included that one because it was on that list of yours. I thought that file had the unknown compression type. The other file (9120) was proper mesh file and was the one I got the error on when attempting to parse. Delutto's tool does use zstd, but lzo and oo2core as well. Where it's using those libraries is another matter.




blenderprscr2.jpg (251.68 KiB) Viewed 160 times



Just because it was in the view, this monster seems to have suffered localized black hole to the groin. I expect you already noticed that. But on the topic of UVs, this game is using UDIMS? I see a lot to suggest that it uses multiple UV maps per mesh for certain objects, whether that's actual separated UV maps or they are suppose to all be on UDIMs I dunno. But for example when zaramot got Ash he seemed to export all of Ash body from one mesh file, and all of Ash head from another. However, from the operators I have from Luxox I can see that operators have far more texture sets which do not co-exist on the same UV tile:

Ash

Eyelashes
Hair
Head
Hands
Torso
Arms
Pants
Boots
Badges

IQ

Eyelashes
Eyes
Hair
Head
Head_det (some blank texture)
Helmetvisor
Holster
Gear
Torso
Arms
Arms_det (a tileable)
Arms_det2 (a tileable)
Legs


I see overlapping UVs for the monster too, could it be what you've been calling sub-meshes is where UVs are separated by?
## Post #114
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-10T08:40:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The lack of groin seems to be intentional, not a parser error. Maybe that's why he's so angry ))
New script supports exporting separate islands, you can add islands=%island number% to mesh.build_meshdata, it will only build the specified island (smasher has 5 of them). If you build only the first island, you will notice there are no uv overlaps and the part that goes beyuond u=1 is actually almost identical to the left one. They unwrapped left and right parts of body identically and placed them in different uv quads for ease of management. But the texture wraps around the edge and tiles so you basically have them uv-ed identically, like if they where stacked, no udims involved.
In fact they use 1 material per island, that's why they consume uv space completely per each island. If you look into material tab in blender for that mesh, you will notice it creates meshslots per each usland so you can apply different materials on them like they do it in the game itself.
Smasher's head is also in different file. It uses only 2 uslands (actual head and a neck hole filler). On characters you will have more islands because hair, eyes, eyelashes - all those require different shaders (I can bet each island even gets rendered in a sepatare render call).
## Post #115
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-10T09:01:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[These metas](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=90#p160305) where sampled from TTS files. It's not just those that are unknown. It's ALL metas are packed like that in TTS. I just randomly sampled about a 100 of them from different files to get some diversity in data. Those need to get piped through different decompressors in order to try to identify the right one. I just can't find time for that so I rely on community's help on that one.
## Post #116
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-10T14:30:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

You're making a large amount of sense, thank you senpai.   

They were NOT kidding about those permeating data changes huh, new season patch has gone live and it's 105 GB for me. That's pretty much the entire game. Actually, I think it's more than the entire game and includes the optional high-def texture pack which I have installed as well, which I assume lives among the .forges.

I encountered an error when playing around with new script, a file which was parsed before now fails. This is the number 12723.mesh, containing the pretty awesome tilt rotor craft if I do say so. I iterated through the islands using the parameter you suggested — mesh.build_meshdata(islands=%island number%) — The mesh has 15 islands and all of them parse corrected except number 8, which judging by the other islands I seen number 8 must be the main body of the aircraft. Here is the log of my iterations and the error:

```
remaining 0
built data
1
^^^^^
12723
=================
remaining 0
built data
2
^^^^^
12723
=================
remaining 0
built data
6
^^^^^
12723
=================
remaining 0
built data
7
^^^^^
12723
=================
remaining 0
built data
8
^^^^^
12723
=================
remaining 0
built data
11
^^^^^
12723
=================
remaining 0
built data
13
^^^^^
12723
=================
remaining 0
built data
Rebuilt loops from 4764 to 4755.
Array iterator out of range: (index 1585)
Traceback (most recent call last):
  File "S:\R6SRip\Scripthead2.blend\test_mesh_parms", line 68, in <module>
  File "S:\R6SRip\site-packages\r6s\blnd.py", line 106, in build_dict_mesh
    mesh.polygons[poly_id].material_index = mat_id
IndexError: bpy_prop_collection[index]: index 1585 out of range, size 1585
Error: Python script failed, check the message in the system console

=================
remaining 0
built data
5
^^^^^
12723
=================
remaining 0
built data
14
^^^^^
12723
=================
remaining 0
built data
9
^^^^^
12723
=================
remaining 0
built data
12
^^^^^
12723
=================
remaining 0
built data
10
^^^^^
12723
=================
remaining 0
built data
3
^^^^^
12723
=================
remaining 0
built data
15
^^^^^
12723
=================
```
## Post #117
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-10T14:59:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Tue Mar 10, 2020 4:40 pm at Tue Mar 10, 2020 4:40 pm
>
> 
The lack of groin seems to be intentional, not a parser error. Maybe that's why he's so angry ))

Haha yes I remember he was very angry. Though, in the interest of avoiding misunderstanding due to my off-hand comment, in the image on the right-hand leg I am referring to mesh deformity, badly stretch faces causing a ugly shading there. I can believe it if the error was part of the mesh and not your parser, but sometimes I'm not very clear, just ignore this if that's what you meant all along.
## Post #118
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-10T16:13:49+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yes, you got 100Gb update because of extra textures. My friend had just reported that it's 63Gb for him. They have essentially reuploaded all forges. Be aware that Denutto's tool in theory should be able to unpack new forges (mine does, it only messes up some indexing meta), but my scripts won't be able to parse these meshes yet (pesky new metadata format).
Now for your error message. There is a message "Rebuilt loops from 4764 to 4755." This happens because I invoke blender's internal validation. For some reason it crops off some of the triangles, causing the vertex count to shrink. That's why you get IndexError. If you want to bypass it, set validation=0 in build_mesh, it will skip the pass and should load normally then. I'll try to fix it later.
## Post #119
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2020-03-11T11:33:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I just found this thread via google and was pleasantly surprised that someone was already working on this game.
Is it possible to extract operator models with their skeletons for simple posing? All the operator models I could find online are boneless, which makes them useless for anything beyond simple renders.
## Post #120
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-11T13:46:01+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from GordenF ↑Wed Mar 11, 2020 7:33 pm at Wed Mar 11, 2020 7:33 pm
>
> 
Is it possible to extract operator models with their skeletons for simple posing?

This is basically my goal for this project. I'm yet to extract skeletons. Zamarot was able to pinpoint where this data is stored, but he is not that interested in siege, so he handed me the hints on what to search. Right now my plans are to ease up dds extraction and then I will proceed with skeleton data reversing.
## Post #121
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-12T06:35:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Mar 11, 2020 12:13 am at Wed Mar 11, 2020 12:13 am
>
> 
Yes, you got 100Gb update because of extra textures. My friend had just reported that it's 63Gb for him. They have essentially reuploaded all forges. Be aware that Denutto's tool in theory should be able to unpack new forges (mine does, it only messes up some indexing meta), but my scripts won't be able to parse these meshes yet (pesky new metadata format).
Now for your error message. There is a message "Rebuilt loops from 4764 to 4755." This happens because I invoke blender's internal validation. For some reason it crops off some of the triangles, causing the vertex count to shrink. That's why you get IndexError. If you want to bypass it, set validation=0 in build_mesh, it will skip the pass and should load normally then. I'll try to fix it later.

Yup these meshes have all their pieces now, good work. I was wrong about island 8 btw, it wasn't the main part of the craft it was all those little white bits, so a large amount of tiny disconnected faces.




blenderprscr5.jpg (101.17 KiB) Viewed 391 times
## Post #122
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-03-24T19:18:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tushkan u said "Be aware that Denutto's tool in theory should be able to unpack new forges" do you mean the current r6s version ? i tried and it wasnt able to unpack
btw where did u get the old r6s version id like to download that if possible
## Post #123
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-24T23:27:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yes, I meant the current version with updated forges. Well then it shows that I was wrong if it's not able to unpack em. Mine unpacks them fine but messes up some header info that I use to filter out file types.
As for Y4S4 forges I backed up my own files before they got updated. And all those outbreak files where provided by another guy on this forum.
## Post #124
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-03-25T09:29:49+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

i figured out how to downgrade r6s version 
do you know which version of r6 Archive_NeXt can unpack ?
## Post #125
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-25T12:12:34+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

No, I never used it. Custard might know though, he seems to have used it before.
## Post #126
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-26T02:08:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Archive_Next? No I didn't use that one, it seemed like it had been discontinued for quite a while and hadn't really claimed R6S support. I had a quick search just now to try and discover if that was true, one of the very last posts made by that tool's developer says this:

> Reply from MichaelDarkAngel ↑Fri Mar 31, 2017 10:54 pm at Fri Mar 31, 2017 10:54 pm
>
> 
Rainbow Six is not going to work if you have any version other than the Beta.  Even the Beta doesn't work properly because of missing files.  I have the full version of the game now and I'm currently working on rebuilding the search index.  However, I have run into an issue with some of the forge files, so even that is taking longer than I would have hoped.

The Beta has 53 forge files, the full version has 213.  This renders the current search index useless as positions of some of the files have changed.

Well, he was up to working on search functions so that's cool, but I think a lot has changed in the files since the Beta..

> Reply from Flyynn ↑Wed Mar 25, 2020 3:18 am at Wed Mar 25, 2020 3:18 am
>
> 
Tushkan u said "Be aware that Denutto's tool in theory should be able to unpack new forges" do you mean the current r6s version ? i tried and it wasnt able to unpack
btw where did u get the old r6s version id like to download that if possible

When you say it wasn't able to un-pack, how did you test that? Or was it just an error it gave you?
## Post #127
- Username: UnknownLuck
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 27, 2020 9:24 am
- Post datetime: 2020-03-27T01:28:58+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

So I don't really know a whole lot about 3D modelling, (I do CAD work for 3D printing, that's as far as I go), and I was wanting to try and get a 3D model of one of the charms. Anyone know how I might go about grabbing one?
## Post #128
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-03-29T06:16:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from UnknownLuck ↑Fri Mar 27, 2020 9:28 am at Fri Mar 27, 2020 9:28 am
>
> 
So I don't really know a whole lot about 3D modelling, (I do CAD work for 3D printing, that's as far as I go), and I was wanting to try and get a 3D model of one of the charms. Anyone know how I might go about grabbing one?

The Intel GPA method would be your best bet right now. 3d printing is one of the few things it's results are not super undercooked for, and weapon charms are one of the few things that I can say you'd certainly be able to get. I wrote up roughly how to go about using it here: 

[viewtopic.php?f=16&t=15031&start=30#p158679](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=30#p158679)

It's still not exactly easy, or for the faint of heart, but since the game files aren't properly cracked at the moment that's rather inevitable.
## Post #129
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-03-30T21:35:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Thu Mar 26, 2020 10:08 am at Thu Mar 26, 2020 10:08 am
>
> 
Archive_Next? No I didn't use that one, it seemed like it had been discontinued for quite a while and hadn't really claimed R6S support. I had a quick search just now to try and discover if that was true, one of the very last posts made by that tool's developer says this:
MichaelDarkAngel wrote: ↑Fri Mar 31, 2017 10:54 pm
Rainbow Six is not going to work if you have any version other than the Beta.  Even the Beta doesn't work properly because of missing files.  I have the full version of the game now and I'm currently working on rebuilding the search index.  However, I have run into an issue with some of the forge files, so even that is taking longer than I would have hoped.

The Beta has 53 forge files, the full version has 213.  This renders the current search index useless as positions of some of the files have changed.


Well, he was up to working on search functions so that's cool, but I think a lot has changed in the files since the Beta..
Flyynn wrote: ↑Wed Mar 25, 2020 3:18 am
Tushkan u said "Be aware that Denutto's tool in theory should be able to unpack new forges" do you mean the current r6s version ? i tried and it wasnt able to unpack
btw where did u get the old r6s version id like to download that if possible


When you say it wasn't able to un-pack, how did you test that? Or was it just an error it gave you?

sry tushkan was right i probably clicked on the textures file
but even when i (unpack/decompress{i rly dont know the terms}) it i get .data file which i then use the DATA_TOOL and then i get a .dat file which i used noesis to open but i got an error "This file cannot be previewed"

btw tushkan whats the progress on your tool in %

and ty you for the hardwork and to every one that helped with the tool
## Post #130
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-03-30T21:41:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Btw idk what im doing
## Post #131
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-30T22:50:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Noesis won't read these textures by themselves. They are a classic dx10 dds but with custom headers so noesis doesn't know where to read data about packing type and image size and mipmaps. IIRC, these data files have 0x58 bytes long header (might be longer if there is a string name encoded, also headers are different since 2020 update because of new metadata packing), then goes actual dds block, then goes footer that actually holds enum of dx10 type (rgb8 \ monochrome8 \ rgb16 bit etc.) and height\width (multiplied by number of channels or smth like that ,generally it's multiplied by 4, don't ask me why...). You can actually get the textures by reading them in Rawtex. This program allows you to specify data offset (around x58 for previous format) and guess pixel format and size.
mainly used types are:

```
---------------------------------------------------------------
0x0 : 87, # b8g8r8a8_unorm
0x2 : 71, # BC1
0x3 : 71, # BC1
0x4 : 74, # BC2
0x5 : 77, # BC3
0x6 : 83, # BC5U
0x7 : 61, # r8_unorm
0x8 : 61, # r8_unorm
0x9 : 56, # r16_unorm
0xb : 42, # r32_uint
0xc : 3, # r32g32b32a32_uint???
0xe : 80, # bc4???
0xf : 95, # BC6
0x10 : 98, # BC7
0x11 : 87, # b8g8r8a8_unorm

```


Current progress is hard to describe in %. It's like mining gold. You know you have found it when you have found it )
Current state is:
1. unpacker for pre-2020 forges works. It also works for 2020 forges but messes some meta a bit. But should be easy to fix.
2. models parser: parses most of mesh types, parses most of data except for skinning. I haven't figured out how it's packed yet.
3. textures parser: was working when I last tested it about a year ago. Involves RawTex and texconv to function. I want to make it depend only on texconv.
4. assets parser - currently in progress. There is a lot to be done. I'm struggling with how they pack data because it's a bunch of varying-size structs with optional tail information. So it's hard to identify bounds and separate generic tailed structures from actual encoded types. It's needed because it holds all related data such as what parts are glued together, skeletons (I think I even found animations), texture links, shaders etc.
5. strings parser: 0% progress. I've found where strings are stored. They are needed to retrieve specific assets from game, otherwise one would have no clue on which asset is which and would have to unpack all of them to find the needed one. I also can't seem to find localization data, only eng strings.
6. dependency graph parser: works with pre-2020 depgraphbins. Needed to easily find relations between files. For example it lists all textures and meshes that are tied to given asset.
## Post #132
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-03-31T09:25:58+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

alright ty for the update

you have contacted luxos in the past 
how did u get in contact with him almost every acc is banned and i cant find him
i would like to ask him how he got the uvs from GPA
## Post #133
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-03-31T10:33:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I bombarded him through all available accounts. Eventually I managed to contact him through his now suspended DeviantArt acc. He's not that easy to get in touch with )
## Post #134
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-03-31T11:31:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[https://p3dm.ru/xfsearch/avtor_rip/Luxox005/](https://p3dm.ru/xfsearch/avtor_rip/Luxox005/)

this is his new account if u want to get in touch
## Post #135
- Username: Flyynn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 05, 2020 6:26 pm
- Post datetime: 2020-04-25T10:51:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

whats wrong,
no one is posting here any more ?
## Post #136
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-04-26T22:07:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm a bit overwhelmed with other stuff at the moment so I can't find time to work on asset reversing. Plus there isn't much interesting going on to post about. I scanned the whole repo to identify some of uids (took a week on 12 cores) and I'm writing some minimal hint framework to be able to highlight some data in html tables so I can easily identify potentially important stuff (uids, magic mentions etc).
## Post #137
- Username: jaxx21
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 11, 2020 12:00 am
- Post datetime: 2020-04-27T09:10:24+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

hi, thank for the work you are making for extract model. I hope you will find soon. Thank you.
## Post #138
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-04-27T18:36:35+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Samples where used to test and debug mesh reader code. Siege uses several compression methods so one has to account for all possible types of mesh packing. So I used samples to check if I broke something in code or missed some details. I'm actually yet to figure out how they encode skin weights. Right now those are exported as colors in blender.
## Post #139
- Username: jaxx21
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 11, 2020 12:00 am
- Post datetime: 2020-05-04T01:58:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

are they some progress? will we see 3D model from this game again? thank you for your work.Just a question.
## Post #140
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-05-05T10:53:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Only minor technical progress. I have to build my own tools to assist reversing. No new models atm. But there is no need to publish models because they are easily exportable at this stage. Main focus is on extracting skeletons and skinning and finding ways to identify assets by names.
## Post #141
- Username: jaxx21
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 11, 2020 12:00 am
- Post datetime: 2020-05-05T14:48:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

ok, thanks because i dont see any new model (weapon, or character without skeleton).skeleton can be rig a little bit with mixamo. Thank.
if you have a tutorial how to extract forge file or extract model. Thank you very much for your work.
## Post #142
- Username: SheetMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 26, 2020 4:07 pm
- Post datetime: 2020-05-08T17:17:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Tue May 05, 2020 6:53 pm at Tue May 05, 2020 6:53 pm
>
> 
they are easily exportable at this stage
Can you clarify one question for me please? Following this thread I can extract meshes and textures from the newest version of r6? It's just a ton of information, I want to know if is that I am looking for.
## Post #143
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-05-11T11:07:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Weeell, I can, you can't ) I did not publish any of these tools except for a mesh converter in my dropbox. And it expects unpacked forge data. I can unpack it, but I have to fix metadata encoding. I guess it's about time to write a small faq with project status to not answer same questions over and over.
## Post #144
- Username: Tervel1337
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 06, 2020 7:34 am
- Post datetime: 2020-06-05T23:52:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Has anyone managed to extract the police car model from before the models update?
## Post #145
- Username: Midnight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 19, 2020 4:48 pm
- Post datetime: 2020-07-19T08:55:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I’m new to this whole 3D models thing but I want to make a game and was wondering if anybody could extract some weapons for my game pls
## Post #146
- Username: Sciong
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 29, 2019 8:38 pm
- Post datetime: 2020-07-28T14:10:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Would anyone have any progress on this so far?
## Post #147
- Username: Cris23ST
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 16, 2020 1:20 pm
- Post datetime: 2020-08-16T05:22:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

A few years latter, I just wanted to know if any other substantial advances have been made
## Post #148
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2020-08-19T15:38:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I just tried with Intel GPA but the launcher that appears a few seconds before the game ruins everything, i guess it's simpler with a cracked game.
Btw can someone provide the 2015 version of Intel GPA ? The 2020 version doesn't allow to export meshes & the 2014 version doesn't work in w10.
## Post #149
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-08-19T15:50:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Damoclès ↑Wed Aug 19, 2020 11:38 pm at Wed Aug 19, 2020 11:38 pm
>
> 
I just tried with Intel GPA but the launcher that appears a few seconds before the game ruins everything, i guess it's simpler with a cracked game.
Btw can someone provide the 2015 version of Intel GPA ? The 2020 version doesn't allow to export meshes & the 2014 version doesn't work in w10.

2015 does not work, just like 14

if anyone has any idea why does this happen and how can I fix it we will have Kali's sniper textured and basically any other weapon with little to no manual work involved, i suspect it's the script's fault but weird how the UV shows up correctly on the texture but distorts on the mesh...

[https://twitter.com/floxayyy/status/1296080380257341441](https://twitter.com/floxayyy/status/1296080380257341441)

(sry for link, im on my phone atm)
## Post #150
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-08-20T00:23:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Kali's sniper in Blender; 46.080 verts and 15.360 faces/tris... I have multiple verts in the same place... am I fucked?
## Post #151
- Username: Nyfoxel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 30, 2020 6:28 pm
- Post datetime: 2020-08-21T07:06:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

This is the best attempt i have seen so far. Did you try Edit Mode - Vertex Select - Select > all - Vertex > Merge Verticles > by Distance ?
## Post #152
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-08-21T07:28:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Nyfoxel ↑Fri Aug 21, 2020 3:06 pm at Fri Aug 21, 2020 3:06 pm
>
> 
This is the best attempt i have seen so far. Did you try Edit Mode - Vertex Select - Select > all - Vertex > Merge Verticles > by Distance ?

Unfortunately I'm not experienced in 3D stuff so I don't really know if I'm doing something wrong, I google a lot of stuff :d

Yes, after shading smooth, does not look good lol:
## Post #153
- Username: Nyfoxel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 30, 2020 6:28 pm
- Post datetime: 2020-08-21T11:28:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Can you give me a test blend file?
## Post #154
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-08-21T16:35:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

with a little help from @Nyfoxel it looks good now  

hopefully we will figure out how to get the missing meshes for OPs and the other parts that are missing before the game dies :d
## Post #155
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-09-04T16:02:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'll try to answer latest questions raised here.
Do debug the game with x64dbg one needs to start the game, wait for virtualization to unpack, kill BE process (there is a bat that does that, seen in on unknowncheats if my memory serves me) then attach to running process. It did work in 2018, did fail occasionally at the end 2019, don't know if it will work now.
Depgraphbin's x02 seems to be an ultra short magic number. Didn't change in last 4 years while actual data was changing.
Kali's rifle has overlapping verts because of how lods are stored. It's a unified vertex buffer for all submeshes which is shared by all lods. So lower lod has same amount of verts in memory, some of em are simply not connected to tris. There is a link to my dropbox that has all code to unpack mesh files. You can check it to get some idea how meshes are stored.
About my personal progress: can't find time and motivation to finish it. Bash me collectively if you want me to publish what is available atm and continue yourself.
## Post #156
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-09-04T16:10:48+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Oh, btw, if gou intend to debug the game, make sure you do it in offline mode. If you dont' have a spare acc ) I'd occasionally even shut down the internet to avoid any fuckups. Also, unpacked exe is protected heavily with vm. And doesnlt seem to have string. Those are packed partially in ui files and i suspect the are in the fattest file that seems to describe the whole data tree. Didn't examine it though yet.
## Post #157
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-09-04T16:56:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sat Sep 05, 2020 12:02 am at Sat Sep 05, 2020 12:02 am
>
> 
I'll try to answer latest questions raised here.
Do debug the game with x64dbg one needs to start the game, wait for virtualization to unpack, kill BE process (there is a bat that does that, seen in on unknowncheats if my memory serves me) then attach to running process. It did work in 2018, did fail occasionally at the end 2019, don't know if it will work now.
Depgraphbin's x02 seems to be an ultra short magic number. Didn't change in last 4 years while actual data was changing.
Kali's rifle has overlapping verts because of how lods are stored. It's a unified vertex buffer for all submeshes which is shared by all lods. So lower lod has same amount of verts in memory, some of em are simply not connected to tris. There is a link to my dropbox that has all code to unpack mesh files. You can check it to get some idea how meshes are stored.
About my personal progress: can't find time and motivation to finish it. Bash me collectively if you want me to publish what is available atm and continue yourself.

Can your current progress get character (static non-weighted) models and textures?
## Post #158
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-09-05T12:42:12+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yes, but it's not straightforward. And I need to update my code so it correctly reads 2020 version of forge files.
## Post #159
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-09-05T14:02:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sat Sep 05, 2020 8:42 pm at Sat Sep 05, 2020 8:42 pm
>
> 
Yes, but it's not straightforward. And I need to update my code so it correctly reads 2020 version of forge files.

Cool, that's sounds great
## Post #160
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-09-11T22:23:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I don't suppose anyone how I guide on how to get started porting via the Intel GPA method? Or if not, I saw someone say they got Iana ported via a commission, but it was a private model.

I don't suppose anyone knows who to ask about commissions?
## Post #161
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-09-12T08:21:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from gep55 ↑Sat Sep 12, 2020 6:23 am at Sat Sep 12, 2020 6:23 am
>
> 
I don't suppose anyone how I guide on how to get started porting via the Intel GPA method? Or if not, I saw someone say they got Iana ported via a commission, but it was a private model.

I don't suppose anyone knows who to ask about commissions?

Luxos has ripped so far every single public R6 model out of the game via Intel GPA and hex editing, you should ask him. Dunno where you can contact him as he constantly gets banned for copyright infrigements.
## Post #162
- Username: SheetMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 26, 2020 4:07 pm
- Post datetime: 2020-09-12T08:44:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sat Sep 12, 2020 4:21 pm at Sat Sep 12, 2020 4:21 pm
>
> 
Luxos has ripped so far every single public R6 model out of the game via Intel GPA and hex editing, you should ask him. Dunno where you can contact him as he constantly gets banned for copyright infrigements.

That's interesting. I tried to use Intel GPA without any hex editing, but all meshes was broken. 
Also, luxox now here: [https://p3dm.ru/user/Luxox/](https://p3dm.ru/user/Luxox/) and he is still active.
## Post #163
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-09-12T14:11:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from SheetMan ↑Sat Sep 12, 2020 4:44 pm at Sat Sep 12, 2020 4:44 pm
>
> 
MaZTeR wrote: ↑Sat Sep 12, 2020 4:21 pm
Luxos has ripped so far every single public R6 model out of the game via Intel GPA and hex editing, you should ask him. Dunno where you can contact him as he constantly gets banned for copyright infrigements.


That's interesting. I tried to use Intel GPA without any hex editing, but all meshes was broken. 
Also, luxox now here: https://p3dm.ru/user/Luxox/ and he is still active.
Yeah he gets the model data somehow with Intel GPA and hex edits them to .obj format.
## Post #164
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2020-09-16T10:38:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sat Aug 22, 2020 12:35 am at Sat Aug 22, 2020 12:35 am
>
> 
with a little help from @Nyfoxel it looks good now  

hopefully we will figure out how to get the missing meshes for OPs and the other parts that are missing before the game dies :d

Amazing work ! first time to see someone doing that after Lux !
pls keep us updated bcs i'm a 3d artist i want to get my hands on Siege Models 

Keep up the good work guys
## Post #165
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-10-18T19:00:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

If anyone is still working on this, please know that we eagerly await news
## Post #166
- Username: Coverop
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 17, 2014 5:41 pm
- Post datetime: 2020-10-27T07:25:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Fresh bump.

Is someone still working on it?
## Post #167
- Username: WolfAndRaven
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 02, 2020 6:32 pm
- Post datetime: 2020-12-02T13:08:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I tried playing with Intel GPA. It's possible to extract most of the things needed to make a character, however, with this method, you'll need A LOT of time and work if you want to have an actual good model, as in, posable, textured, model. In other words, you could get the 1.000.000 pieces needed to solve the puzzle, but the hard part is actually solving it.

My conclusion is that through this method you can get textures 100% and meshes 80% (they are posed) using Intel GPA, but other things, such as UV maps and rigs are not obtainable as far as I've seen, which means you'd have to solve those things yourself. In other words, though this method, you could extract everything, although, it would take you a lot of time to clean things up and you'd need to provide for the missing things.

I'll proceed to explain what my observations where in a detailed way:

> I've "succesfully" "extracted" models and textures from the game with the last version of Intel GPA. This should serve as a disclaimer, as I've only tried this with said program with relative success. It should also be noted that this is not my area of expertise. I'm not really knowledged when it comes to ripping and extracting models from games, nor am I good with programming or coding. If anything, my whole area of expertise is in 3D Modeling, texturing, rigging, etc... This means that I can edit meshes with no problem, which surprisingly comes useful when it comes to extracting these models. Anyway.
>
> 
>
> 1) When it comes to meshes, it's indeed kind of a pain: It's not necessarily hard, but it requires patience, since the characters are relatively well segmented, for example, there's a general mesh for the head, for the hair, the arms, the top of the body, some belts, etc. This means you need to be ready to export (and explore) many different sectors of the frame in order to get the full model out. Once you accept this reality, you could, theoretically export all of the meshes, including characters and weapons. I haven't tried to export maps, however, I believe it is possible. Meshes are exported as .obj files which are easily importable to any 3D software.
>
> 
>
> There's a problem though, at least for me. All the meshes I've found seem to be... distorted? More specifically, they seem to be kind of flattened, not all the way through though, which is good since it means they can be fixed simply by scaling the mesh in the affected axis. I suppose this makes sense since you are getting a frame after all. It's a problem indeed but easily solved, however, it's worth noting since it adds to the time it takes to "succesfully" export a model. I've noted however that all the meshes in one frame seem to be squashed in the same axis, the same ammount, which would theoretically mean that you could export many meshes (head, hair, arms, etc) and then scale them all together, fixing all meshes simultaneously. 
>
> 
>
> Another solvable problem is that meshes get a lot of overlapping vertices, almost as if all faces were not joined, this can be solved by merging all overlapping faces, deleting the duplicated vertices.
>
> 
>
> An unsolvable problem, on my end at least, is that meshes seem to be posed, which also kind of makes sense since you are getting a frame l, so, you don't get them in a easily editable pose (T-Pose or A-Pose). This, added to that it doesn't seem possible to get the models rigged (it's a .obj after all...), means manually rigging them will be harder.
>
> 
>
> 
>
> 2) When it comes to textures, it's easier. Textures seem to be in the same location as meshes, which means that once you find a mesh, you should also see all the textures used by said mesh, so, you don't need to look for them all over the program. I found diffuse maps, normal maps (inverted (green), but found them nonetheless), and some other maps I don't remember (specular, or roughness I suppose). Once you export them, you get them in .dds or .png files, your choice.
>
> 
>
> Here's the final problem however. You don't get the UV maps. This means that your textures won't be useable unless you unwrap the meshes. This is no easy work, since there's no easy way of knowing where the original seams were as far as I know.

So... Extracting the meshes and the textures is possible. With a bit of tweaking, you can get to fix the model scale, making it look good. However, you'd then need to rig the model, turning it into a regular T-posed one, which is doable if you take your time and know what you are doing (I know I could do a decent enough job, should I find it necessary and get motivated), but the UV Map is where I can't do much. It would simply take way too much work and time to reverse engineer the textures. I don't know if there's a way to get that information out of a model, but unless I find a way, this is all I can do. Sorry to disappoint.

At the point I am, the only 100% functional stuff I can do with this tool is extract better resolution textures for already existing, UV mapped models, extract meshes to mod an existing model (some hair, hats, uniforms and other easy to UV Map things), but that's it. It seems our only viable hope is to wait for a .FORGE unpacker.

As a side note, interestingly enough, with this tool I can't extract stuff I can't see. So, for example, I can't extract Dokkaebi's "Shutter Shade" Legendary Headgear, unless I find a Dokkaebi in game with that skin or I get it on an Alpha Pack. Which is a boomer, since I got into this in order to get that headgear alone.

Also. I downloaded the UHD pack for the textures, to see if I could get some 4K textures, but the only ones I could find were weapons and some normal maps (heads, specifically, which seem to be different from the regular head normal maps), apart from those, as far as I could see, character textures where at 2048 max.

Anyway. Enjoy an untextured, unrigged Aruni.

[https://imgur.com/a/BlnGGVP](https://imgur.com/a/BlnGGVP)
[AruniP.jpg](https://xentaxbackup.github.io/file/19117_AruniP.jpg)
## Post #168
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2020-12-06T18:10:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I tried ripping them as well. Maybe we could help each other with this. I tried it with renderdoc, it didn't work for me. I don't know much about 3d. I started learning it recently. I also tried to contact Luxox and floxay who were able to rip some models. None of them answered me. I really want to get those models but everyone who knows something or who has them is less than uncooperative. I hoped we could help each other with this.
## Post #169
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2020-12-06T23:14:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from aajax ↑Mon Dec 07, 2020 2:10 am at Mon Dec 07, 2020 2:10 am
>
> 
I tried ripping them as well. Maybe we could help each other with this. I tried it with renderdoc, it didn't work for me. I don't know much about 3d. I started learning it recently. I also tried to contact Luxox and floxay who were able to rip some models. None of them answered me. I really want to get those models but everyone who knows something or who has them is less than uncooperative. I hoped we could help each other with this.
Luxox is so busy (full time) and he's a cool guy he can help when he's free, but Floxay surprised us in [https://p3dm.ru/user/floxay/](https://p3dm.ru/user/floxay/) but i send him like a chain of messages, he responded just for one message, anyway, i hope someone can make a miracle...5 years
## Post #170
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2020-12-07T18:31:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

He is the only one having the models. Why should he help me to rip them. I know that he sold some models to a guy. I hope you're right. I try to get them for so long now. I hope to get the custom skins and battle pass rewards as well. Thank you for your answer on this. I really appreciate it.
## Post #171
- Username: killahtree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 13, 2020 12:00 am
- Post datetime: 2020-12-09T04:07:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Anyone here have any clue as to how the hell textures files are stored? I know they are BC1, but with some random data scrambled between texels, of which I have found no way to filter out. I've been stuck on this for a couple months now and I've pulled every hair follicle off of my scalp.

You can see actual normal crap show up, but then it ends because the parsing continues through the shitty bytes. The dumps are correct, I'm 100% positive about that, but I can't parse the textures.
[https://i.imgur.com/SxfRCYT.jpeg](https://i.imgur.com/SxfRCYT.jpeg)

Tushkan is gone and I don't know whom else to ask about this.

Attached are some examples, hoping someone can tell me what I'm missing. Thanks.
[test.zip](https://xentaxbackup.github.io/file/19156_test.zip)
## Post #172
- Username: dovahkiinbro47
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 03, 2020 2:58 pm
- Post datetime: 2020-12-09T06:54:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from killahtree ↑Wed Dec 09, 2020 12:07 pm at Wed Dec 09, 2020 12:07 pm
>
> 
Anyone here have any clue as to how the hell textures files are stored? I know they are BC1, but with some random data scrambled between texels, of which I have found no way to filter out. I've been stuck on this for a couple months now and I've pulled every hair follicle off of my scalp.

You can see actual normal crap show up, but then it ends because the parsing continues through the shitty bytes. The dumps are correct, I'm 100% positive about that, but I can't parse the textures.
https://i.imgur.com/SxfRCYT.jpeg

Tushkan is gone and I don't know whom else to ask about this.

Attached are some examples, hoping someone can tell me what I'm missing. Thanks.

You can decently rip textures from the game using NinjaRipper. While meshes don't come out properly, textures are all there.
## Post #173
- Username: killahtree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 13, 2020 12:00 am
- Post datetime: 2020-12-09T21:19:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from dovahkiinbro47 ↑Wed Dec 09, 2020 2:54 pm at Wed Dec 09, 2020 2:54 pm
>
> 
killahtree wrote: ↑Wed Dec 09, 2020 12:07 pm
Anyone here have any clue as to how the hell textures files are stored? I know they are BC1, but with some random data scrambled between texels, of which I have found no way to filter out. I've been stuck on this for a couple months now and I've pulled every hair follicle off of my scalp.

You can see actual normal crap show up, but then it ends because the parsing continues through the shitty bytes. The dumps are correct, I'm 100% positive about that, but I can't parse the textures.
https://i.imgur.com/SxfRCYT.jpeg

Tushkan is gone and I don't know whom else to ask about this.

Attached are some examples, hoping someone can tell me what I'm missing. Thanks.


You can decently rip textures from the game using NinjaRipper. While meshes don't come out properly, textures are all there.

With all due respect, that has literally nothing to do with what I'm talking about. I am extracting the forges...
## Post #174
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-12-10T16:21:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I remember I made texture plugin for textures, and they were different. Could you attach model sample? I have my old models but don't have textures, so models I could compare.
## Post #175
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2020-12-10T17:03:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from killahtree ↑Thu Dec 10, 2020 5:19 am at Thu Dec 10, 2020 5:19 am
>
> 
dovahkiinbro47 wrote: ↑Wed Dec 09, 2020 2:54 pm
killahtree wrote: ↑Wed Dec 09, 2020 12:07 pm
Anyone here have any clue as to how the hell textures files are stored? I know they are BC1, but with some random data scrambled between texels, of which I have found no way to filter out. I've been stuck on this for a couple months now and I've pulled every hair follicle off of my scalp.

You can see actual normal crap show up, but then it ends because the parsing continues through the shitty bytes. The dumps are correct, I'm 100% positive about that, but I can't parse the textures.
https://i.imgur.com/SxfRCYT.jpeg

Tushkan is gone and I don't know whom else to ask about this.

Attached are some examples, hoping someone can tell me what I'm missing. Thanks.


You can decently rip textures from the game using NinjaRipper. While meshes don't come out properly, textures are all there.


With all due respect, that has literally nothing to do with what I'm talking about. I am extracting the forges...

Is there already a forge unpacker for R6 or are you working on it? I'm just curious.
## Post #176
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-12-10T17:11:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

No I'm not, I made something for it like a year ago, we talked with Tushkan and I gave him few tips. Though, personally I wasn't inetrested in the game, so I left everything to Tushkan!
Here's example of model import
[https://www.youtube.com/watch?v=tSNCstw ... montDeSire](https://www.youtube.com/watch?v=tSNCstwSzq8&ab_channel=DismontDeSire)
texture plugin
[https://www.youtube.com/watch?v=K47_f6Z ... montDeSire](https://www.youtube.com/watch?v=K47_f6ZchEg&ab_channel=DismontDeSire)
## Post #177
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2020-12-10T18:52:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ok I see. I hope to get a way to extract the models or at least to get them from someone. I didn't manage to rip them with known tools.
## Post #178
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-12-11T20:15:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I checked only older client, from torrents I think it's year old. I'm almost 100% sure they changed quite a bit since then, I remember Tushkan said they are changing stuff there and there quite often.
## Post #179
- Username: killahtree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 13, 2020 12:00 am
- Post datetime: 2020-12-11T21:04:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from zaramot ↑Fri Dec 11, 2020 12:21 am at Fri Dec 11, 2020 12:21 am
>
> 
I remember I made texture plugin for textures, and they were different. Could you attach model sample? I have my old models but don't have textures, so models I could compare.

I haven’t looked into them much, do you know if they’re the mesh or meshshape forges?

EDIT: Here's a mesh forge.
[mesh.zip](https://xentaxbackup.github.io/file/19170_mesh.zip)
## Post #180
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-12-12T13:04:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The meshshape.forges are Havok data from what I remember, mesh.forge has the models.

All the forges got a reformat in March 2020, file headers changed. Compression and meshes should be the same though going back to when zaramot last poked his head in here.

Tushkan explained about the texture structures here: [viewtopic.php?f=16&t=15031&start=120#p161589](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=120#p161589)
He had a working texture parser that he didn't share, but it used RawTex and texconv.

He had a working model parser that he did share. No UI or executable, it was just a Python script you had to run manually but it did the job, full models with LODS and UVs, you can dig that up on his Dropbox if you're really interested. Not sure if it worked on post-March 2020 files out of the box, I haven't had the means to extract recent forges myself or I'd like to try that out.

His Dropbox: [https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0](https://www.dropbox.com/sh/b2cuse4hp90ym0g/AADXaqKfyrCY9joUtsnlqTfja?dl=0)

You'll want "export > outbreak_models.blend" because that includes the script head, but you'll also need to set up the "site-packages" in your Blender Python environment. Some extracted mesh files are also in the Dropbox to test on. You need to edit parts of the script to define the target to parse. Btw if you're a bit clueless and you're just looking for a tool where you can click some buttons and get the models you want this isn't it. No such tool exists so far.

Tushkan also had a working forge extractor, but did not share it and I'm not sure if he ever updated that one to work post March 2020. He said it wasn't hard to make that adjustment, but those format changes had interfered with it. The lack of a publicized forge extractor that worked properly with the current .forge file format in Siege was a barrier for us to be able to attempt the brute force approach with his model parser, but make no mistake, the brute force approach is rubbish. Having a tool that can extract a working model with good UVs isn't actually good enough, because what comes out of the forges is not ordered and has no useful names, so you'd be individually and laboriously processing files for hours, days, weeks to try and find the one mesh you wanted. It's not like there's just a .forge for the characters, and one for the guns. Instead consider it like there's like a hundred thousand assets thrown randomly into the forges, then you realize, it's no more reasonable than getting meshes off Intel GPA and painstakingly reconstructing the UVs and de-posing it. Without a way to search, it's a massive time investment to get anything you want. This is why Tushkan was also trying to solve the strings and dependency graphs, to be able to identify and target specific ones. That's one of the most important things we need to move forward on this. Tushkan was also trying to solve skeletons, weights, and so on, which can be nice but didn't help in him burn out on this project I guess..
## Post #181
- Username: killahtree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 13, 2020 12:00 am
- Post datetime: 2020-12-12T14:47:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sat Dec 12, 2020 9:04 pm at Sat Dec 12, 2020 9:04 pm
>
> 
The meshshape.forges are Havok data from what I remember, mesh.forge has the models.

All the forges got a reformat in March 2020, file headers changed. Compression and meshes should be the same though going back to when zaramot last poked his head in here.

Tushkan explained about the texture structures here: viewtopic.php?f=16&t=15031&start=120#p161589
He had a working texture parser that he didn't share, but it used RawTex and texconv.

He had a working model parser that he did share. No UI or executable, it was just a Python script you had to run manually but it did the job, full models with LODS and UVs, you can dig that up on his Dropbox if you're really interested. Not sure if it worked on post-March 2020 files out of the box, I haven't had the means to extract recent forges myself or I'd like to try that out.

His Dropbox: https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0

You'll want "export > outbreak_models.blend" because that includes the script head, but you'll also need to set up the "site-packages" in your Blender Python environment. Some extracted mesh files are also in the Dropbox to test on. You need to edit parts of the script to define the target to parse. Btw if you're a bit clueless and you're just looking for a tool where you can click some buttons and get the models you want this isn't it. No such tool exists so far.

Tushkan also had a working forge extractor, but did not share it and I'm not sure if he ever updated that one to work post March 2020. He said it wasn't hard to make that adjustment, but those format changes had interfered with it. The lack of a publicized forge extractor that worked properly with the current .forge file format in Siege was a barrier for us to be able to attempt the brute force approach with his model parser, but make no mistake, the brute force approach is rubbish. Having a tool that can extract a working model with good UVs isn't actually good enough, because what comes out of the forges is not ordered and has no useful names, so you'd be individually and laboriously processing files for hours, days, weeks to try and find the one mesh you wanted. It's not like there's just a .forge for the characters, and one for the guns. Instead consider it like there's like a hundred thousand assets thrown randomly into the forges, then you realize, it's no more reasonable than getting meshes off Intel GPA and painstakingly reconstructing the UVs and de-posing it. Without a way to search, it's a massive time investment to get anything you want. This is why Tushkan was also trying to solve the strings and dependency graphs, to be able to identify and target specific ones. That's one of the most important things we need to move forward on this. Tushkan was also trying to solve skeletons, weights, and so on, which can be nice but didn't help in him burn out on this project I guess..

The file name strings aren’t even used by the game, there is a good chance that they’re randomized or just a hash of the real file name.
## Post #182
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2020-12-12T18:09:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sat Dec 12, 2020 9:04 pm at Sat Dec 12, 2020 9:04 pm
>
> 
The meshshape.forges are Havok data from what I remember, mesh.forge has the models.

All the forges got a reformat in March 2020, file headers changed. Compression and meshes should be the same though going back to when zaramot last poked his head in here.

Tushkan explained about the texture structures here: viewtopic.php?f=16&t=15031&start=120#p161589
He had a working texture parser that he didn't share, but it used RawTex and texconv.

He had a working model parser that he did share. No UI or executable, it was just a Python script you had to run manually but it did the job, full models with LODS and UVs, you can dig that up on his Dropbox if you're really interested. Not sure if it worked on post-March 2020 files out of the box, I haven't had the means to extract recent forges myself or I'd like to try that out.

His Dropbox: https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0

You'll want "export > outbreak_models.blend" because that includes the script head, but you'll also need to set up the "site-packages" in your Blender Python environment. Some extracted mesh files are also in the Dropbox to test on. You need to edit parts of the script to define the target to parse. Btw if you're a bit clueless and you're just looking for a tool where you can click some buttons and get the models you want this isn't it. No such tool exists so far.

Tushkan also had a working forge extractor, but did not share it and I'm not sure if he ever updated that one to work post March 2020. He said it wasn't hard to make that adjustment, but those format changes had interfered with it. The lack of a publicized forge extractor that worked properly with the current .forge file format in Siege was a barrier for us to be able to attempt the brute force approach with his model parser, but make no mistake, the brute force approach is rubbish. Having a tool that can extract a working model with good UVs isn't actually good enough, because what comes out of the forges is not ordered and has no useful names, so you'd be individually and laboriously processing files for hours, days, weeks to try and find the one mesh you wanted. It's not like there's just a .forge for the characters, and one for the guns. Instead consider it like there's like a hundred thousand assets thrown randomly into the forges, then you realize, it's no more reasonable than getting meshes off Intel GPA and painstakingly reconstructing the UVs and de-posing it. Without a way to search, it's a massive time investment to get anything you want. This is why Tushkan was also trying to solve the strings and dependency graphs, to be able to identify and target specific ones. That's one of the most important things we need to move forward on this. Tushkan was also trying to solve skeletons, weights, and so on, which can be nice but didn't help in him burn out on this project I guess..

I wasn't expecting a UI tool to just click buttons. I thought about a script or something like that. I study computer Science and hoped my knowledge could help me to get the models, but in the university you get trained to be a theorist. You have to learn the practics on your own. But everytime I try to research on the forge files or any I get some information that is not very useful or understandable for me. It's like everyone who knows something about it just gives small hints and then remains silent or just works on his own just to never share it to anyone. I hate to dependent in a to others in a way like that. But thanks for the information about that. I really appreciate it.
## Post #183
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2020-12-21T06:08:52+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Sorry for my long absence, can't still find time to get back on track with this stuff. killahtree if you want to get hands on my code, you can ping me over at discord (Ulibos#3846) I'll share my sources and guide you through it. It's divided in 3 parts and needs some explanations to not get lost. I need someone to glance over it with extra pair of eyes to tidy some of it up and publish what I have so others can move on from where I left it.

As for your textures extractions: there are not only BC1 textures. Siege uses about 4 different types of dds encoding depending on texture type. Their forge versions are basically a shuffled vanilla dds with some strange decisions (like porting header to the end of file, storing dimensions not as pure w:h, but as w*num_channles:h*num_channels or smth like that). It would be easier for you to just grab my code and move on with it rather than rewriting that from scratch and losing all your steam in the process.

P.S.: you publish your discord id but your profile is locked for invitations, couldn't send a request to you xD
## Post #184
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-08T00:44:16+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ok boys and girls. It's 2021 and I think it's time to drop some news. I updated my code to work (more or less) with Y5 forges, made a couple scripts to ease the process and now I'm releasing it for you all to use. You can download it here [https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0](https://www.dropbox.com/sh/b2cuse4hp90ym0g/AADXaqKfyrCY9joUtsnlqTfja?dl=0)
There are readmes for you to be able to set it all up. I might have missed a thing or two while packing so if it breaks - don't panic, just post your problem here.
Also, I have no clue whether Ubi will break their forges again in Y6, so I'd HIGHLY suggest you to backup your current game distro. Would be a shame if next update would render my tool useless and you'd have to wait another 6 months for my patch, eh? )
## Post #185
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-11T03:51:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hooray! This looks very interesting 

I wasn't able to find a module called binstream.py on the Dropbox.  
Did found binstream as a pypi project, did pip install binstream, but it still fails the script on the first request made to it that doesn't seem like what you meant.
## Post #186
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-11T11:42:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Oops, my bad. I dropped binutils instead of binstream. Updated dropbox now. Official binstream wouldn't work because mine is a custom wrapper that I use to write less code when deserializing. The only thing they have in common is their names ) Redownload the zip and you should be good to go.
## Post #187
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-11T15:33:34+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Very stupid question, are 4K Textures pack will be do diffirence and may use with unpacker?
## Post #188
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-11T15:51:35+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I honestly never bothered to test. It looks like their uids are stored in asset files so they should be accessible via scripts. The only caveat is each texture package type (texture0,texture1,texture2,texture3) has it's own magic number which is used in r6s.tex.is_texture() to detect whether this file is to be parsed as texture. I suppose 4k textures should have their own file postfix like texture4.forge and have their own magic number for container. You need to add that magic into is_texture function for script to recognize those files correctly. You either can find it yourself and post it here, or I will need a sample file to find it myself. In readme there is a code to dump files from archive. You can dump just 1 file (replacing `for i,e,n,c in forge.files():` with `for i,e,n,c in forge[10]:`, it will only dump 10th entry from that forge archive) and send it to me so I can find and add that magic into the package.
## Post #189
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-11T16:06:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks for reply, i'll try when can.
## Post #190
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-11T17:34:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Can you help me with some understand how to use it properly.
What i did:

I have installed Pytnon 3.7 (3.7.9)
install addon zstandard by this command:
```
 pip install zstandard
```

create file in C:\Users\%username%\AppData\Local\Programs\Python\Python37\Lib\site-packages\siege.pth with this line:

```
E:\SiegeUnpack\Tools
```

In this folder i have this:

```
rawtex\
scripts\
binstream.py
binutils.py
```


And i create folder E:\SiegeUnpack\Data for dumped files i think.
Then i edited E:\SiegeUnpack\Tools\r6s\settings.py
with this:

```
    r"E:\Backup[G][Games]\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege[upoff]"
)
#: path to dump uncompressed data to
EXPORT = r"E:\SiegeUnpack\Data"
#: binaries used for texture conversion
tex_bin = r"E:\SiegeUnpack\Tools\rawtex"
```


Okay then i will start simple check:

Step one:

Run(just double mouse click) E:\SiegeUnpack\Tools\scripts\roam_meshes.py
I will see UID and some numbers, okay, it will create folder "meshes\datapc64_merged_bnk_mesh\" with amount *.meshjson files.

Step two:
Run(just double mouse click) E:\SiegeUnpack\Tools\scripts\roam_textures.py
I will see something same, numbers UID etc. and it will create folder too. "textures\datapc64_merged_bnk_textures3\" with amount *.png files.

Well like all good? Yes i think.

Step three:

Run again double clicked  E:\SiegeUnpack\Tools\scripts\dump_asset.py 
And folder assets didn't create and nothing happend window just closed, on this step i think a do something wrong.

I missing some instructions in readme file? i've glad if you help me what i do wrong.

P.S. Game install without 4K textures pack, just standart install.
## Post #191
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-11T19:42:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

And in readme said about cache, i don't have it, how can i create him and how i need it, for easely asset export?
I notice roam_meshes.py export only guns, when i comment this line:

```
                # if (
                #  mesh.x2C not in (9,10)
                # ): continue
```

it start dump every mesh, how can be possible to know type of meshes, like, guns, character and etc. i'll be happy to dump some character if it possible.
If i understand right it possible only by asset file, wich i can't get.
## Post #192
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-11T21:03:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Cache is created automatically by the scripts that need it. You should see a folder named cache inside scripts dir. I can't tel what went wrong without seeing dump_asset's console output. DOn't run it via double-click. Run cmd.exe, navigate to the scripts folder, then run the script in that cmd. It won't close after executing script and you will be able to see error report. I need that report to diagnose what went wrong.

If you want to search for specific types of objects, you will have to read r6s source. I comment all parameters that I reverse. So you need to open r6s/mesh/__init__.py and read class Mesh definition. There are different parameters that allow to partially filter needed data.
## Post #193
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-11T21:08:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Here the error msg:

```

E:\>Cd E:\SiegeUnpack\Tools\scripts

E:\SiegeUnpack\Tools\scripts>dump_asset.py
loading E:\SiegeUnpack\Tools\scripts\cache
generating None
Traceback (most recent call last):
  File "E:\SiegeUnpack\Tools\scripts\dump_asset.py", line 43, in <module>
    asset_links = data.asset_children.child_in_links(UID)
AttributeError: 'NoneType' object has no attribute 'child_in_links'
```
## Post #194
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-11T22:03:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

It didn't find any asset that would have given UID as a child. So it returned None instead of list. Loop couldn't iterate through None object and failed. In short, no asset found that has that id as a child. How do you insert a UID you're truing to search?
## Post #195
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-11T22:18:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Its default UID from dump_asset.py UID = 22439848753, or you mean in need place files to folder wich i self create for this asset number?
## Post #196
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-11T23:27:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

IF you use my uid then it should work fine. When you first ran dump_asset, it should have created a 'cache' folder next to it. DO you have it? My only guess is cache didn't initialize properly so it can't find links.

Also I have updated tool to be a little bit more verbose and fixed a couple issues other people found out plus added textures from example. Update is available by the same link.
## Post #197
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-12T00:04:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yes I had the same error, two lines near the start of dump_asset.py seemed like the solution:

```
import os
import sys
import pathlib as pth
import r6s.collector
import json


DUMP_PATH = (pth.Path.cwd() / './assets').resolve()
idir = pth.Path(r6s.settings.IMPORT)
data = r6s.collector.SiegeLinksData()
# data = r6s.collector.SiegeLinksData(load=False); data.generate()

#UID = 220652921502  # caveira head FaZe diffuse texture uid
UID = 220652921502
```


I made it like this instead (swapped which one was commented out):

```
data = r6s.collector.SiegeLinksData(load=False); data.generate()
```


It's been scanning for a while now, which seems closer to expectation.

I have the texture4.forges on account of having downloaded the ultra texture pack, I'll see about sharing the magic number for those when I can.

Btw is the binutils.py a dependancy? I threw it in there to begin with, thinking you might have meant that instead of binstream.py, however the script wasn't happy when I then removed it after the correction, so I'm still using it, as is Jake. However it's gone off the Dropbox.
## Post #198
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-12T00:15:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

You need to generate cache once. Then revert code back so you don't have to wait so long each time you fire a script. binutils is a redundant dependency. I've updated the tool again, you can redownload it. Of just go to r6s/forge.py and comment out the `from binutils import phex` line. It's never used, just a leftover garbage.
## Post #199
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-12T03:31:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Would you say it's normal if this cache generation were to take, say, days to complete?

Mine seems to be running through alphabetically, same order I see the forges in the game directory, it ran through datapc64 in seconds, the next ones a bit longer, then it's doing the first meshshape.forge for nearly 4 hours now, getting slower and slower.

Edit: A restart seems to have affected it, it's gone past that file within a few minutes now.
## Post #200
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-12T09:48:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

On my machine cache is generated within 1-2 minutes. If it goes longer - something went wrong. But I need statistics to find what exactly went wrong. If restart solved your problem then fine. I had links compile exponentially longer over tine but I since modified code to make it faster. So if it goes for an hour or longer - let me know, I might include my prebaked cache in next release.
## Post #201
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-12T15:41:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks Custard! Swap code start generating cache, now when i execute dump asset it create folder asset  
@Custard how about 4K textures do you get result?
## Post #202
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-12T16:33:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I've check r6s\mesh\__init__.py and in line 201

```
        # 2(map props?), 8(some bosses, some hands), 9, 10(some weapons)
```

in roam_meshes.py i did this:

```
                   # mesh.num_verts < 100
```

When i edit it like this:

```
mesh.x2C not in (1)  # see r6s.mesh.Mesh.x2C
```

it gives me a error:

```
TypeError: argument of type 'int' is not iterable
```

If i unredstand, i can't point of type of mesh like that, this need do in different code.
P.S. That becouse i think if i set high poly count and serch mesh by poly (maybe 2000) I may skip some low poly meshes like eyes etc.
P.P.S. Or you may give a sample how to search characters right, please  .
P.P.P.S. One question: Do you plan map export or just get coord of meshes on map without brushes (ingame geometry created by engine editor, like floor, walls etc.)?
## Post #203
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-12T17:30:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

In python brackets mean either tuple (an iterable non mutable list) or execution grouping. (1,2) is a tuple, while (1+5) or (a==b) or simply (1) is a group. To nake it a tuple, add a comma like this (1,). Or even better, simply do x2C == 1
## Post #204
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-12T17:50:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks for tip i'll try it, not have knowbledge in python
## Post #205
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-12T17:58:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Well then you should definitely read some tuts about it ) It's not that hard though sometimes it has it's peculiarities that aren't immediately apparent. 
On map export: I don't plan to invest much time in maps. My personal goal is to rip characters with skeletons and skinning. Everything else is of less priority. If anyone is willing to reverse it himself he can ping me for some guidance.
## Post #206
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-12T22:58:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

If i can call it bug report, what a get: 
```
    3812: 299062604030
    3817: 299062606425
    3824: 299062693146
    3839: 309301408753
    3844: 309301409215
    3852: 309301491241
    4016: 22439860332
Traceback (most recent call last):
  File "E:\SiegeUnpack\Tools\scripts\roam_meshes_chara.py", line 37, in <module>
    with r6s.mesh.Mesh(c.file.getstream(), readmesh=False) as mesh:
  File "E:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in __init__
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "E:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in <listcomp>
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "E:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 134, in parse
    self.x108 = ruint32(r)
  File "E:\SiegeUnpack\Tools\binstream.py", line 34, in ruint32
    return upk('I', r.read(4))[0]
struct.error: unpack requires a buffer of 4 bytes

E:\SiegeUnpack\Tools\scripts>
```


Edited Roam_Meshes.py:

```
mesh.num_verts < 20000

```


Nothing more changes, just a bug report.

Can it be a error because nothing found or end of loop, forge file etc.?
## Post #207
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-12T23:30:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Your script is perfectly fine. It's an issue with my code. Some meshes aren't deserialized properly and lead to an exception. Can be avoided by using try-catch block.
I've updated the script with such block. It will spit out the error message and continue running.
## Post #208
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-13T00:24:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks for this, it's really cool 

I've really been wanting to port some characters from this game for a while, so I have a few questions.

Firstly, what is the best place to buy the game?

Secondly, If I buy the game, where can I buy the operator skins (e.g. hibana's elite skin, iana..), or are they already included in the game files, and buying them just unlocks them for gameplay. Are any of the skins not available anymore since they were limited releases?

Cheers
## Post #209
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-13T01:06:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

You can buy where ever suits you. I'd suggest to wait for sales, siege often goes for sale with up to 75% discount on some versions. I'd also suggest you to buy not the cheapest one so you don't have to grind to open all operators. And yes, operators are only locked in-game, yet all resources are available right away (otherwise how would you see an opponent playing an operator you don't own yet). In short, if you only want to rip characters then buy cheapest release or even ask someone to share archives with you. If you want to play it then buy at least a release with all basic operators unlocked.
## Post #210
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-13T06:33:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Failing to generate cache properly was caused by me running the script in IDLE Shell, running in elevated Command Prompt solved it.

Made some attempts to find what magic was for textures4, I printed out the contents of two things, that being "n" as mentioned here..

        # e - Entry object, contains offset, size and uid of a file
        # n - NameEntry object (old class name, not relevant anymore)
        #     contains compressed metadata (haven't cracked it yet),
        #     magic number and other less interesting stuff. Can be
        #     used for fast specific filetype search
        # c - Container. 99% of time it's a compressed file (if
        #     n.file_type != 0). It has `meta` and `file` attributes.
        #     meta is deprecated since Y5 when it was compressed and
        #     moved inside each entry's blob, just ignore it.

And also all the contents of tex.header..

```

NameEntry object dump: 

x00: 0, x04: 4, x08: 0, x10: 4, meta: b"\x1e'\xf7u\x92\xee\x94\xa1\xa9^\xed\xc2\xdal\x19]\xe4\xfb\xf2P5\xe3\xd8\n10\xe5\x1eD\x9dZ\xefx\x9d\xc3\xb8\xb9,\xc4\xd5\xb6\xfd\xc1%\xff\xa5c\xb3%s\xc3\x841~\xd2l\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00", x113: 56, timestamp: 2020-10-31 06:59:21, x118: 0, prev_entry_idx: 109, next_entry_idx: 111, x124: 0, file_type: 947309791, x130: 0, x134: b'\x11\xce\xb6\xd5\xd6rc~x\xb7\x10\x00'

tex.header dump:

encoded_meta: b"\x1e'ns\x92\xee\x94\xa1\xc9D\xc6-\x8b4\x0f\x8c\xa4\xee]\x87\xd4S\x85\xecQQ N\xd1\x95\x11\xfa\xf8\xa7\xb2!\xfd\xcd\x8f\x19\x961^\xa4\xeb\x1c\x1f>e\xb1\xf7n\xd7o\xa0\n", var1: 2097269, magic: 947309791, uid: 4471484783, var2: 0, var3: 0
```


Both those seem to suggest a magic number of 947309791, which wasn't the form I expected that number to take. I don't know if that helps at all.

Anyway congrats Tushkan, you've gotten us to a point where there will be a wave of new assets from this game, pulled right out of the forges! I doubted to even see this day but you did it.
## Post #211
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-13T07:31:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Python by default prints integers as decimals. If you convert 947309791 to hex, you will get 0x3876ccdf. Add this value to r6s/tex.py into a list in is_texture() function (you can actually add even a decimal, it will work exactly the same) and try dumping some character or gun asset. It should dump 4k textures as well.
## Post #212
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-13T13:02:24+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

That magic has worked for textures4, but level 4 diffuse textures don't want to come out and play. 

When doing a asset_dump I now get higher res norms and whatever the other ones are. A roam_textures catches nothing in textures4 unless the conditions are modified to not demand tex.tex_type 0. I demanded no specific tex.tex_type at all but diffuse textures were not among results.

I used this advanced script to scan several texture4.forges for any different magic number at all, there were no hits..

```
    for i,e,n,c in forge.files():
        data = r6s.forge.getdatastream(c.file, forge.reader)
        with r6s.tex.Tex(data) as tex:
            if n.file_type==947309791: print("Daka daka dakka")
            else: input(n.file_type)
```


It'd be weird if there was no diffuse textures in all those textures4 packs, however I have seen 4K sizes produced from textures3 (e.g Tachanka's LMG which I found). Technically possible that they mostly used the ultra texture pack for secondary texture improvements? Many of the norm maps I seen aren't even 1K without it.
## Post #213
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-13T14:17:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Try not to check for that specific magic, but rather collect all possible magics. Create a set() and add to it all magics you find. Pdeudocode:

```
with r6s.forge.parse(your_forge) as f:
    magics = magics | set(x.file_type for x in f.names)
print(magics)
```


Chances are they have another container that we've missed.
## Post #214
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-13T14:42:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Jan 13, 2021 9:06 am at Wed Jan 13, 2021 9:06 am
>
> 
You can buy where ever suits you. I'd suggest to wait for sales, siege often goes for sale with up to 75% discount on some versions. I'd also suggest you to buy not the cheapest one so you don't have to grind to open all operators. And yes, operators are only locked in-game, yet all resources are available right away (otherwise how would you see an opponent playing an operator you don't own yet). In short, if you only want to rip characters then buy cheapest release or even ask someone to share archives with you. If you want to play it then buy at least a release with all basic operators unlocked.

Thanks, good to know. I'm trying to buy the cheap version of the game on Steam at the moment, but the payment system doesn't seem to be working. Since I only want to rip assets, I'd love to just get the .forge archives if I could.

Edit - Nevermind, bought the game and downloading it now.
## Post #215
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-13T14:52:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Trying to find head from Elite skin, now don't have result, will try scan other forges.   


I know skin and weight not coded, how about skeletal, maybe in future search by skeletal match and rip asset full (i mean all parts with come this skel, like head, hair, etc)?

Can possible to know some sets address or name by hex viewving forge or cache files, sample, i know name of Elite skin or part of it (UID), and with this get some info where find others parts from this skin, head etc. Or maybe by numbers like head start with one numbers other parts with different. Or it absolutely random and need to know all real addresses?

P.S. Here a samples how CAV skin must looks, [https://r6skin.com/2019/11/12/caveira-elite-skin/](https://r6skin.com/2019/11/12/caveira-elite-skin/)
Where i can get full parts i ask about textures or google it self, i think PBR pipeline in siege same as most cases, and read about it, now i don't understand much what are red, green textures, and others blue, i've know where diffuse and normal, but wich is roughness or others texures and wich chanel it take i didn't know currently
## Post #216
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-13T15:08:58+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Skeleton is stored inside an asset file (turns out it's actually called a BuildTable). The folder you have created by dump_asset has it's name as a long number. That's actually an asset's UID. You can dump it using that uid (you'll have to write your script, I did not include one for that). I'm still reversing those and it's going to take long time. So no skeletons for now. In case you want to rip it manually, skeleton's magic is 0x24AECB7C (7C CB AE 24). You can find such value inside an asset file and manually extract bones matrices. But judging by your current python skills it won't be easy for you )

Missed your question about how to find head based on body. Short answer is: I have no clue. I have to yet find structures that describe such assemblies. I would rather find localization links so we can search items by their names. But that's not even remotely implemented atm.
## Post #217
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-14T14:44:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hi again,

I just installed the game from Steam, but I'm a bit confused as to what the 'test server' is?  There are .forge files with it, but do I need them, or just the ones located with the game?

Cheers
## Post #218
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-14T15:00:34+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Test server is basically what the name says. It's a WIP snapshot that is used to test new features before release. It has newest assets if those are intended. You can dig it but while we don't have any means of identifying assets it won't be of much use unless you're ready to check all 100gb worth of items.
## Post #219
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-14T17:05:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Okay I've found head! Just grab all meshes from dump_asset.py, and spend more time by blender load up it (i split meshes to different folder like part1, part2 etc. becouse i didn't want try load 4000+ meshes be one time) for separate and filter by hand   

If someone interested here a meshes UID:

```
Body: 233351024927
Head: 233351024906

```


When i've dumped it asset folder have this numbers:

```
235493428027
```


But again a have some bugs   

Ok, number one:





Lets explain, 91271895122.001 this load from asset, wich i dump, Eyes and Mouth look like mistatch, but eyes and mouth which you provide from faze head looks good, but it like same asset number and which come from dump asset look screwed.

number two not your bug just show:




This is subsurface wich a don't set right, ive just copy material presset from your faze head, yeah i know this is misstake, i bit later i try setup it right like in game look as i can. But this is hard asset come with more textrures wich is blend with masks, need looks better what texture is it.

And last number three:




Some texture black in preview (blender\windows) but when i apply in blender it looks normal (this is color texure like deffuse), i think they have multi channel or swaped it, and preview buggy.
If someone know about textures help me explain this:



Okay
1: is Diffuse 
2: is Normal? (or normal from previous image, few first images in preview?)
3: Roughness Specular?
4: Some Mask or PBR material too? like glossy maybe i've not correct and this is specular idk.

Eye shadar i didn't try now, but i don't think it hard, becouse ingame eye don't look non standart
## Post #220
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-14T19:41:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'll start from texture mapping.
1. Diffuse. That one is obvious.
2. normal This normal contains only x and y values for normal. I suppose they drip z value to save space. My example shader restores it back, use it.
3. Masks. Those look like material masks. Basically control sgader mixing.
4. Pbr These are actual pbr channels. Use my shaders as base.

Mismatching teeth: I had same issue. They either have cusom positioning ans scale or are modified by bones. Can't tell for sure unless I completely reverse asset files.

And thanks for ids, those mught help in analysis.
## Post #221
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-14T20:49:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Big thanks about material explain, i will be use your samples! If i found something else interesting message here)
## Post #222
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-15T05:15:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Jan 13, 2021 10:17 pm at Wed Jan 13, 2021 10:17 pm
>
> 
Try not to check for that specific magic, but rather collect all possible magics. Create a set() and add to it all magics you find. Pdeudocode:
Code: Select allmagics = set()
with r6s.forge.parse(your_forge) as f:
    magics = magics | set(x.file_type for x in f.names)
print(magics)

Chances are they have another container that we've missed.

Setup and ran this method now on half dozen forges, it only reports back the single UID. I'm out of ideas for that.   

I have been putting together Aruni, since I found her whole on basically the first time I searched (I've been saving a list of UIDs to share, but it's just two things right now). I've been pondering on the textures, I got the impression the blue channel is an AO texture and came up with what you can see below, using it in sRGB color space on purpose. That's before I thought to looked at Tushkan's shader. My confidence is not 100% on this. However in defense of it, I was comparing to the in-game character to see if I was getting similar reflectivity, and that brushed metal around Aruni's knee is very shiny and metallic in-game, and this is one of the few uses that preserves that. Using the blue channel as some sort of roughness seems to conflict with that, using it as a glossiness seems to make everything too shiny.




Edit: Btw Jake, about the diffuse textures, they can have slight areas of transparency which can can cause discoloration. If you aren't expecting that it can cause you headaches when it happens, making us thinking the shader is wrong or the lighting is wrong instead. It seems to be related to their subsurf, I haven't worked out that yet.
## Post #223
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-01-15T19:12:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Anyone could extract and publish default and elite sets of Caveira, Valkyrie and Hibana? No need for bones, just textures and the meshes.
## Post #224
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-16T10:09:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

There is no way rn to easily locate specific assets. You either have to wait till people find those uids or search for them yourself.
## Post #225
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2021-01-16T14:46:15+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Does anyone else have a syntax error in line 55 of roam_meshes.py?
## Post #226
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-01-16T16:26:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from aajax ↑Sat Jan 16, 2021 10:46 pm at Sat Jan 16, 2021 10:46 pm
>
> 
Does anyone else have a syntax error in line 55 of roam_meshes.py?

remove the colon at the end of the line
## Post #227
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-16T17:07:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

And i bored about find interested meshes and edit blender import script:
USE THIS IF YOU LOAD ALOT of Meshes, not for Asset!
In def build_dict_mesh(), after this line obj = bpy.data.objects.new(name, mesh) add this line:

```
obj.location = (newXPos, newYPos, 0.0)
```

next add after fdir = r'D:\folder\with\meshjson\files'  this lines:

```
newYPos = 0.0
```

and a bit below add this after meshdata = load_json(fpath)

```
        newXPos += 2.0
    if newXPos >= 50.0:
        newYPos += 2.0
        newXPos = 0.0
```

Here a result if load many meshes:



Thanks a lot Custard! Can you may provide your eye's shader, i've do fast self few days ago, this is not look good but this is like "fast as can as is":

Without rotate:

Linear

My bad forgot disconect node with invalid image   

My shader


@MaZTeR If i can search UID for this meshes i've post UID here.

Here some UID but this is may not correctly:

```
*IQ body 22439853703 42145286857 103017200953 103017200891 137109688208 134899778449 138069196434 167065136839

*Cav heads 23604782352 35440557402 42145172043 105430467046
*Cav body 32505461026, 42145226580, 8670922697

*Hibana heads 42145179185 42145159299 53135534821 95215580895 48086912442 105997733667 151373279631 148749981863  210322437173 167029277499
*Hibana body 42145166235 42145166284 64744913125 210322437668 167029275706 167029285820 167029285847

*Valk heads 42145291720 42145291323 42145291738 46560158188 66793212533 106277448919 105997728084
*Valk body  64744923166 61972413351 98997255553 105997795343 98997346399
```


This is hard found by old method, i've try with edited script a bit easy may search meshes, i wish it is
## Post #228
- Username: aajax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 07, 2020 1:40 am
- Post datetime: 2021-01-16T17:07:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Jan 17, 2021 12:26 am at Sun Jan 17, 2021 12:26 am
>
> 
aajax wrote: ↑Sat Jan 16, 2021 10:46 pm
Does anyone else have a syntax error in line 55 of roam_meshes.py?


remove the unneeded colon at the end of the line

yeah I already did thanks.
## Post #229
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-16T19:20:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

JakeMiles there is no complete shader for eyes. I could actually try to dump shaders code and reverse from there. Will give it a try later. But most importantly, I want to point out that you should no use 63295959345.png in your eye shader (the one that looks like a black-reddish-white radial gradient). This one is most likely a "bsdf" for skin's subsurface scattering tint.

floxay "colors" is a bunch of unresearched parameters that actually appear to be skinnig data, so right now you basically filter out everything that is not skinned (all static items). There is an easier way to do it without fully reading mesh data. Mesh contains a parameter called Mesh.vert_len. It encodes how many bytes are needed to encode all data for one vertex. Skinned models seem to require at least 0x1C bytes to store all it's attributes plus skinning. So by filtering out everything that is <0x1C you will output only skinned meshes. YOu can play with this one to find the sweet spot. Also take a look at Mesh.revision, it also might help to see some pattern of some revisions being used for specific types of assets.
## Post #230
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-18T17:19:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Some bug report or im noob, but i think it's bug   

I can't find color texture on top, and i think it don't extract right or have shader for this wich is not simple, like others.


This part have same texture, but need have different like here 

Explain, rose part have green color from top green material.

And backbag have different texture


But it have same color like top (Green)

Belt one material control this sections



But again it need to be different colors not same.



This have same problem.

For example here a Dokkaebi Elite skin


Few simple tricks and textures blend good as can without any problems
P.S. Decal on Pants as example, this is from different material slot, on image blend bag.
I mean all materials have your place and i didn't feals i don't have materials slots or something not right. 

Here Meshes UIDs:

```
IQ Elite Head 103017200919 103017200935
IQ Elite Body 103017200891
IQ Elite Body Parts Arms 103017200976, Leags 103017200997, Top 103017200953 maybe it LOD or for some trick like for first person view in-game models
```


```
Dokk Elite Head 264139768986
Dokk Elite Body 264139769111
```


P.P.S. IQ without cassete player on hand and Dokka without boombox from MVP scene, it place in others forges or i didn't find it, maybe skip.
## Post #231
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-19T09:50:40+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The only color issues I ran into yet is because of transparencies in the diffuse texture. I don't properly understand the explanation of your problem. It looks like with IQ that texture is being made all green because a Multiply node has green color in Color1, but you might be doing that on purpose to demonstrate something else. The last picture there is three different Multiply nodes, maybe three different textures, being put into the base color, and it crossed over at the end. This is not easy to understand, I think Multiply node is unimportant for achieving the proper diffuse colors.

That is a good idea for mesh searching. So far I have done texture search, I did a big AFK texture extract to look through the thumbnails, and then some asset pulls on curious items, here's my list so far:


# Dumped & Confirmed — Characters


227263212971: Kali body, default skin, mesh

235493608765: Kali body, default skin, mesh

208674001465: Amaru body, default skin, mesh

208674001442: Amaru head, default skin, mesh

241085404837: Iana body, default skin, mesh

241085404846: Iana head, default skin, mesh

242279067640: Oryx body, default skin, mesh

242279067666: Oryx head, default skin, mesh

263931134676: Aruni head, default skin, texture

67256658867: Dokkaebi face, default skin, texture

127545825670: Dokkaebi torso, default skin, texture

107655346912: Alibi face, default skin, texture

123072720648: Frost face, default skin, texture

189892751785: Warden face, default skin, texture

66793242130: Caveira face, Death skin, texture

95215538602: Sledge face, Midnight Owl skin, texture

14393234550: Terrorist Bomber torso, PvE character, texture

5397612784: Recruit torso, , texture

89636317764: Doc face, unknown skin, texture




# Dumped & Confirmed — Weapons


217057174575: CSRX 300 | Kali Sniper Rifle, weapon body without mag, mesh

243468289335: DP-27 | Tachanka LMG, weapon body without mag, mesh

266171643779: Shumikha Launcher | Tachanka grenade launcher, includes a grenade, texture




# Dumped & Confirmed — Misc


14393161030: Barb Wire, undeployed version, texture

73289262094: Dokkaebi Tablet, , texture




# Not Confirmed; Educated Guess


167466514460: Bandit torso, Elite skin, texture

147616585377: Frost face, Elite skin, texture

167029278598: Hibana face, Elite skin, texture

86825880309: Hibana face, Clan skin, texture

167029284514: Hibana face, default skin, texture

266250227599: Ace torso, default skin, texture

241085434855: Iana torso, default skin, texture

241085436110: Iana face, default skin, texture

208674191421: Wamai face, default skin, texture

208674192919: Wamai legs, default skin, texture

58156742479: Finka face, default skin, texture

58156841305: Finka face, unknown skin without the mask, texture

239222025064: Finka legs, default skin, texture

38223137788: Mira face, default skin, texture

91316034130: Twitch face, Incognito skin, texture

95215482648: Valkyrie face, American Anarchy skin, texture

73522700437: Valkyrie face, Pop Art skin, texture

95215485269: Valkyrie face, default skin, texture

47440353469: Ying face, default skin, texture 

67256453520: Ela face, default skin, texture

105430463739: Lesion face, maybe default skin, texture

195285680207: Goyo face, default skin, texture

198545096973: Maestro face, default skin, texture

14393182590: Target dummy man, , texture

266171643779: Impact grenade, , texture

26204488543: Sledge hammer, , texture

14393160241: Defuser, , texture




# Weapon sights, did not pull corresponding models or textures when asset dumped or behaved strangely.


14393157131: Russian holographic, , texture

14393158146: Russian red dot, , texture

14393157388: Holographic Sight, original version with tan color, texture

23143014245: Red Dot Sight, taller version, mesh

14393158003: Red Dot Sight, for taller version but seems partial, texture

14393158051: Red Dot Sight, short version, texture

22439848903: Reflex Sight, original small optic with the triangular reticule, mesh

22439848935: Laser Attachement, large size for bigger guns, mesh



> Reply from MaZTeR ↑Sat Jan 16, 2021 3:12 am at Sat Jan 16, 2021 3:12 am
>
> 
Anyone could extract and publish default and elite sets of Caveira, Valkyrie and Hibana? No need for bones, just textures and the meshes.

After Aruni I might look to Elite Hibana, since I got a lead for that. I'm happy to help get these assets into other people's hands, but I want to understand it properly as much as I can.
## Post #232
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-01-19T14:19:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I've not seen anybody talking about normal data but that doesnt look correct to me, or you guys just 'fixed' them somehow in blender/maya etc after importing?

what I'm doing rn is merge double verts and use weighted normal data modifier but its far from perfect, but looks "more correct"
## Post #233
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T14:37:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm currently having trouble extracting models due to install issues, so I'm just going to leave these requests here. If someone can share these with me great, if not great as well.

Hibana elite
Frost elite
Iana
Melusi
Ella elite
Mira elite
## Post #234
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T16:30:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ok, I ran this from windows cmd, but I'm not sure what I'm doing wrong. Any pointers would be greatly appreciated 

Microsoft Windows [Version 10.0.19042.746]
(c) 2020 Microsoft Corporation. All rights reserved.

C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts>py dump_asset.py
'py' is not recognized as an internal or external command,
operable program or batch file.

C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts>python.exe dump_asset.py
Traceback (most recent call last):
  File "C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts\dump_asset.py", line 1, in <module>
    import r6s
ModuleNotFoundError: No module named 'r6s'
## Post #235
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-19T16:45:35+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Custard, sure, sorry for mistalking, i mean "green" color, becouse for default method bind texture in material it looks not right, like you said becouse of alpha i mean? Here a example how it looks. Thanks for UIDs.



gep55, Do you run windows command line not python cmd? It looks like you run python cmd not a windows. I didn't install it from windows store, maybe it have some tricks or setup. I install it from site [https://www.python.org/downloads/](https://www.python.org/downloads/)
You can update pip, but if you have newer version of python than me, you don't need it. Command for update pip:

```

```
## Post #236
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-19T16:58:22+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

gep55

You need setup your paths. Need do this.
Go your .\Tools\r6s
Edit file settings.py

```
    r"E:\Backup[G][Games]\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege[upoff]"
)
#: path to dump uncompressed data to
EXPORT = r"E:\SiegeUnpack\Data"
#: binaries used for texture conversion
tex_bin = r"E:\SiegeUnpack\Tools\rawtex"
```


Edit it with your game path for IMPORT = (where game folder)
tex_bin = where your \Tools\rawtex folder
and EXPORT = where you dump folder
then save file.

Next go to your C:\Users\%username%\AppData\Local\Programs\Python\Python37\Lib\site-packages
Your may looks like Python39 or what you version.
and create file with name siege.pth:
Inside write your tools path, example:

```
E:\SiegeUnpack\Tools
```


And execute scripts from windows cmd not from python cmd.
Example, just run windows cmd, with admin rights, becouse you use your scripts from system folder and programm files, and type:

```
C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts\dump_asset.py
```
 then press enter, that all, no need write Python.exe or py, just execute script file.
## Post #237
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T17:53:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from JakeMiles ↑Wed Jan 20, 2021 12:58 am at Wed Jan 20, 2021 12:58 am
>
> 
gep55

You need setup your paths. Need do this.
Go your .\Tools\r6s
Edit file settings.py
Code: Select allIMPORT = (
    r"E:\Backup[G][Games]\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege[upoff]"
)
#: path to dump uncompressed data to
EXPORT = r"E:\SiegeUnpack\Data"
#: binaries used for texture conversion
tex_bin = r"E:\SiegeUnpack\Tools\rawtex"

Edit it with your game path for IMPORT = (where game folder)
tex_bin = where your \Tools\rawtex folder
and EXPORT = where you dump folder
then save file.

Next go to your C:\Users\%username%\AppData\Local\Programs\Python\Python37\Lib\site-packages
Your may looks like Python39 or what you version.
and create file with name siege.pth:
Inside write your tools path, example:
Code: Select allE:\SiegeUnpack\Tools

And execute scripts from windows cmd not from python cmd.
Example, just run windows cmd, with admin rights, becouse you use your scripts from system folder and programm files, and type:
Code: Select allC:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts\dump_asset.py then press enter, that all, no need write Python.exe or py, just execute script file.

Thanks for the help, that get the script running I think  Now though I'm getting this error message instead.

C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts>dump_asset.py
loading C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts\cache
generating None
Traceback (most recent call last):
  File "C:\Program Files (x86)\Steam\steamapps\common\BAK\Unpacker\scripts\dump_asset.py", line 52, in <module>
    asset_links = data.asset_children.child_in_links(UID)
AttributeError: 'NoneType' object has no attribute 'child_in_links'
## Post #238
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-19T18:13:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

gep55
You need do one thing. Open your dump_asset.py, find this lines:

```
#data = r6s.collector.SiegeLinksData(load=False); data.generate()
```


Change it like that:

```
data = r6s.collector.SiegeLinksData(load=False); data.generate()
```


Save file and execute it from cmd, it create cache folder, when it finish, open file again and rewert back lines, like it was be:

```
#data = r6s.collector.SiegeLinksData(load=False); data.generate()
```


Save file, now it must works good.
## Post #239
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-19T18:50:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

floxray my normals reconstruction is a guestimate. I'm not sure whether it's correct, suffice to say it more or less works on stuff. My import script does the following:
1. build triangles.
2. make them smooth shaded
3. apply custom normals
It does not merge vertices. It's a bad idea because game engine doesn't merge them for sure. When you merge them, previously sharp edges become smooth and drag custom normals in same directions producing artifacts.
Upon close inspection meshes in blender seem to show minor artifacts, but that might be due to the fact those normals are heavily compressed. I'm thinking of poking ACV and Blacksmith guys for some insight bat not now. Now I'm migrating my tools to continue work on BuildTables.

JakeMiles just pack your model and shaders into a zip and share it. Would make things alot easier. I guess Custard could help you with that stuff, he seems to be one of 'pro users' of this tool )

gep55 for some non apparent reason cache generator does not work for anyone but me. Do what JakeMiles suggests, it will force the script to build cache file. Do it once for every game update though. I wonder why it fails to autogenerate though...
## Post #240
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-19T19:17:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tushkan

Here archive with a blend file and asset files : [https://dropmefiles.com/JTBtG](https://dropmefiles.com/JTBtG)
## Post #241
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T19:31:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Just tried to Unpack Iana using this (241085404837) ID and got this error message.

Traceback (most recent call last):
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 89, in <module>
    result = processor(asset_dir, forge, child_uid, index)
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 39, in process_mesh
    mesh = r6s.mesh.Mesh(r)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in __init__
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in <listcomp>
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 134, in parse
    self.x108 = ruint32(r)
  File "C:\SiegeUnpack\Tools\binstream.py", line 34, in ruint32
    return upk('I', r.read(4))[0]
struct.error: unpack requires a buffer of 4 bytes



Also, many items were 'unresolved' during extraction.
## Post #242
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-19T19:42:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Tue Jan 19, 2021 10:19 pm at Tue Jan 19, 2021 10:19 pm
>
> 
I've not seen anybody talking about normal data but that doesnt look correct to me, or you guys just 'fixed' them somehow in blender/maya etc after importing?

what I'm doing rn is merge double verts and use weighted normal data modifier but its far from perfect, but looks "more correct"

I have noticed that some incorrect split edges seem to occur. Some spots are broken out separately in places that don't make sense to have a sharp edge. The normals seemed mostly okay once the normal map texture is applied, but in some lighting can still be noticed. If merging doubles is not correct to use, then it needs a more manual fix of the mesh, and it promises a headache for any rigging and weighting (as you can see this happening right on a shoulder).




> Reply from JakeMiles ↑Wed Jan 20, 2021 3:17 am at Wed Jan 20, 2021 3:17 am
>
> 
Tushkan

Here archive with a blend file and asset files : https://dropmefiles.com/JTBtG

To be honest, I think you just didn't receive diffuse texture for that shirt. This may be related to the case of missing texture4 textures, some things may be hiding from us mysteriously.

Also I extracted large amounts of textures, and outfits actually tend to be together numerically. If I scroll through there are chunks of textures that have come out as simply black images. I can see where the pants and the arms for IQ elite outfit are, and they have two black images next to it, 44947786929 and 44947786970. I don't know if that is meaningful, maybe failing to interpret those textures.


> Reply from gep55 ↑Wed Jan 20, 2021 3:31 am at Wed Jan 20, 2021 3:31 am
>
> 
Just tried to Unpack Iana using this (241085404837) ID and got this error message.

Traceback (most recent call last):
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 89, in <module>
    result = processor(asset_dir, forge, child_uid, index)
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 39, in process_mesh
    mesh = r6s.mesh.Mesh(r)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in __init__
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in <listcomp>
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 134, in parse
    self.x108 = ruint32(r)
  File "C:\SiegeUnpack\Tools\binstream.py", line 34, in ruint32
    return upk('I', r.read(4))[0]
struct.error: unpack requires a buffer of 4 bytes



Also, many items were 'unresolved' during extraction.

I have gotten that error and just ran the same script again and didn't get it.    Bunch of things being unresolved is usual.

Edit: Also a little thing about Iana that I remembered, the diffuse textured seemed broken, like greyed out. If you look under unconfirmed on my list you'll see textures listed for Iana and those ones actually had good colors, I left it under unconfirmed because it was just a thumbnail I seen, hopfully it helps.
## Post #243
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-01-19T20:14:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Custard

Ok, thanks for the reply, and i don't have textures4 i don't install ultra pack currently, just standart game with textures3.  
4K pack worth it, i just beware installing it of it, may cause bugs with export, or you investingate it and nothing sirious to beware?
## Post #244
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T21:07:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

ID List. I'll update this as I find more.

Mira elite Head Mesh - 202726047383

Melusi Head Mesh +Ace whole body mesh - 264139704669



216597865597: Ela Elite head, Asset.

97886035065:Ela Elite Body, mesh. Has two body mesh variations.


167029285117:Hibana Elite Body, Asset.
167029285896:Hibana Elite Body, Asset, less gear, maybe lower poly?

for Hibana Elite Head I used Custard's recommendation. Many thanks to them 
167029278598: Hibana face, Elite skin, texture
## Post #245
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T21:12:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Also, for anyone wondering, the black textures are not corrupted, they just show up as black in the windows pic preview due to having a completely transparent alpha channel.

Go into Gimp/Photoshop to remove it.
## Post #246
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T21:15:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Just tried dumping the HD archive and didn't get any exported textures using the default filters. Maybe there are no HD character textures?
## Post #247
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-01-19T21:56:48+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from gep55 ↑Wed Jan 20, 2021 5:12 am at Wed Jan 20, 2021 5:12 am
>
> 
Also, for anyone wondering, the black textures are not corrupted, they just show up as black in the windows pic preview due to having a completely transparent alpha channel.

Go into Gimp/Photoshop to remove it.

alpha is a texture map in some diffuse textures, don't remove it?

Also, thanks Tushkan for the reply
## Post #248
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-19T22:33:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Wed Jan 20, 2021 5:56 am at Wed Jan 20, 2021 5:56 am
>
> 
gep55 wrote: ↑Wed Jan 20, 2021 5:12 am
Also, for anyone wondering, the black textures are not corrupted, they just show up as black in the windows pic preview due to having a completely transparent alpha channel.

Go into Gimp/Photoshop to remove it.


alpha is a texture map in some diffuse textures, don't remove it?

Also, thanks Tushkan for the reply

Good point, thanks.

BTW, if anyone has created a decent eye shader, would they mind sharing the nodes setup as a .blend file? I've very little experience with nodes.
## Post #249
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-19T23:49:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

gap55 I'm pretty sure you downloaded ultra textures pack and didn't force the cache to generate again ) This cache is built by scanning all forges and getting basic data about files from them. You generated it before downloading ultra textures so script doesn't have any info about new files. Rebuild that cache and it should find new textures next time you dump.

floxray yes, alpha is used depending on shader. For heads it seems to store subsurface scattering mask.

Custard broken patches are actually a common thing for game models. Blender or maya can store split normals per one vertex while games can't. Game engines store basically 1 vert with it's position, normal, tangent and uv(s). If you have a cut on uv or a split normal, there is no way to fit both values per vertex so those vertices get duplicated and split. If you want to merge those holes and keep the look identical, you should:
1. copy a backup of that mesh
2. merge and smooth original mesh
3. transfer normals from original mesh
I don't personally think it's of much importance personally.

Edit: And please, follow the guidelines from scripts/README.md on how to post found uids. It will eat up my time trying to figure out what uids I'm dealing with if they aren't properly marked.
## Post #250
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-20T02:19:01+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Wed Jan 20, 2021 7:49 am at Wed Jan 20, 2021 7:49 am
>
> 
gap55 I'm pretty sure you downloaded ultra textures pack and didn't force the cache to generate again ) This cache is built by scanning all forges and getting basic data about files from them. You generated it before downloading ultra textures so script doesn't have any info about new files. Rebuild that cache and it should find new textures next time you dump.

floxray yes, alpha is used depending on shader. For heads it seems to store subsurface scattering mask.

Custard broken patches are actually a common thing for game models. Blender or maya can store split normals per one vertex while games can't. Game engines store basically 1 vert with it's position, normal, tangent and uv(s). If you have a cut on uv or a split normal, there is no way to fit both values per vertex so those vertices get duplicated and split. If you want to merge those holes and keep the look identical, you should:
1. copy a backup of that mesh
2. merge and smooth original mesh
3. transfer normals from original mesh
I don't personally think it's of much importance personally.

Edit: And please, follow the guidelines from scripts/README.md on how to post found uids. It will eat up my time trying to figure out what uids I'm dealing with if they aren't properly marked.

Thanks  I'll try re-generating the cache, but I'm 99% sure that I already had the HD pack installed when I first generated it. By the way, do you want new UIDs post in new posts, or keep all the ones found in a single post that gets updated?
## Post #251
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-20T02:50:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Better go with new posts so I don't have to crawl across the whole thread. Just try to dump those in batches and not 1-by-1.
## Post #252
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-20T02:58:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

216597865597: Ela Elite head, Asset.
97886035065:Ela Elite Body, mesh. Has two body mesh variations.


167029275547:Hibana Elite Body, Asset.

for Hibana Elite Head I used Custard's recommendation. Many thanks to them 
167029278598: Hibana face, Elite skin, texture
## Post #253
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-20T19:48:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from JakeMiles ↑Wed Jan 20, 2021 4:14 am at Wed Jan 20, 2021 4:14 am
>
> 
Custard

Ok, thanks for the reply, and i don't have textures4 i don't install ultra pack currently, just standart game with textures3.  
4K pack worth it, i just beware installing it of it, may cause bugs with export, or you investingate it and nothing sirious to beware?

Using the textures4 doesn't cause any problems, and will give the higher resolution normal and tertiary textures. However, despite expectations, I haven't gotten a single higher res diffuse textures from it. I know your problem is not related to textures4 forges, but I note it has the same symptoms; You got the normals and channel packed textures for the shirt, but diffuse missing for no good reason.

By default the texture search filters only pick out diffuse textures so this sounds like the problem gep is having. If you can't get any diffuse textures from textures4 gep, that is the same as my experience.

The black images I spoke of do seem to be empty of data, not just thumbnail issue. I took some in Photoshop and split the channels, inspected them closely, could not find anything but 100% transparency. There is probably hundreds of these textures in my dump of 2K by 2K size, here is what some patches look like:



For the eye shader, I did not solve it. I added in some other eyes and considered it an upgrade, Siege eyes do not impress with good looks.   
If there is demand for eye asset I could share them, but they are only really made for Cycles rendering (Shader is old and involved).



Tushkan, thanks for clarifying that, and if you want to say how you like this format I will be receptive. I based mine on your readme, and a bit of my own idea, as follows:

# Commented everything among the list that's not a UID
UID: Title, extra description, data type

Include two commas even if I didn't have an extra description to put, for delimiting purpose.
Use | as a seperator if wanted
Avoid use character like '

So...   243468289335: DP-27 | Tachanka LMG, weapon body without mag, mesh
Opposed to...   243468289335: DP-27, Tachanka's LMG, weapon body without mag, mesh

Some consideration for human reading, some for script reading.

Also I haven't been recording any UID of asset folder, because I haven't found any one that works. They don't return me anything when used with dump_asset. Just tried one again as gep listed (167029285117:Hibana Elite Body, Asset), no result is extracted. Anyone can report otherwise?
## Post #254
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-20T22:00:16+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yeah, I did get Hibana's elite body extracted, but it seems the number got mixed up. I'll post the real one here when I find it again.

As for textures4, I haven't been able to get anything at all from it so far.
## Post #255
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-21T00:05:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hibana Elite Body Correct UID - 167029275547
## Post #256
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-21T03:08:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

147616585377: Asset, Nomad Head, all skins (or at least lots of skins).
147616584788: Asset, Nomad Body, all skins (or at least lots of skins).

263544687231: Asset, Kali head, defaut elite and prototype skins.
263544686267: Asset, Kali body, elite skin.
239222036593: Asset, Kali body, prototype skin (Is missing attachments).
## Post #257
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-22T15:20:48+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Done some more testing. I am now able to dump textures from the textures4 .forge, but like Custard, I can't get any diffuse textures out of it.
## Post #258
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-01-22T16:11:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from gep55 ↑Fri Jan 22, 2021 11:20 pm at Fri Jan 22, 2021 11:20 pm
>
> 
Done some more testing. I am now able to dump textures from the textures4 .forge, but like Custard, I can't get any diffuse textures out of it.

i dont think it holds diffuses..
## Post #259
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-01-22T16:17:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sat Jan 23, 2021 12:11 am at Sat Jan 23, 2021 12:11 am
>
> 
gep55 wrote: ↑Fri Jan 22, 2021 11:20 pm
Done some more testing. I am now able to dump textures from the textures4 .forge, but like Custard, I can't get any diffuse textures out of it.


i dont think it holds diffuses..

Cheers  Do you think HD diffuses even exist? If they do, where would they be located?

I don't actually play the game, I'm just ripping stuff.
## Post #260
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2021-01-25T15:05:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks for this amazing work, but i noticed that the mesh normals are impossible to fix !
## Post #261
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-01-25T16:04:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from ravenov ↑Mon Jan 25, 2021 11:05 pm at Mon Jan 25, 2021 11:05 pm
>
> 
Thanks for this amazing work, but i noticed that the mesh normals are impossible to fix !
The 'seriously broken' ones are actually unconnected faces
## Post #262
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-25T16:58:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

ravenov welp, [https://www.youtube.com/watch?v=dvUvC_5dnZ4](https://www.youtube.com/watch?v=dvUvC_5dnZ4) for now. I'm trying to dig up stuff to completely deserialize buildTables (assets). I don't know when I'm going to fix those normals. I'm pretty sure anyone could poke some more experienced rippers to take a look at how my algo unpacks them, maybe (actyally, most likely) I'm doing something wrong. If they will provide an insight on how to fix it, I'll update the code.
## Post #263
- Username: yyred123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 29, 2019 3:24 pm
- Post datetime: 2021-01-28T13:58:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Any help will be appreciated!!   

I really appreciated for those making contribution to this community.

So I ran the asset.dump.py by cmd it seems work perfectly fine at the start



but at the end of the script it showed that there's some error and I couldn't find any asset file either
## Post #264
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-28T15:23:22+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

buildDDS fails to find it's executables for texture conversion. Make sure you've downloaded those (links in README.md) and set their path in r6s/settings.py
## Post #265
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-01-31T10:21:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I've been building a new PC and installing things on it, it was an easy opportunity to check some differences between Ultra texture pack and not.

There is a 13 file difference between the two installations, there are 13 texture4.forges, so this is fully accounted for by those. The client indicated a 23.49 GB download for the ultra pack, the texture4.forges total 21.9 GB in size. So, a gig and a half unaccounted for, idk could be many things; replacing some depgraphs, the download container, etc..

Took a few menu screenshots for side-by-side looks. The higher quality was obvious enough in all cases, but I couldn't spy any obvious clues about diffuses in specific. Most or all of the improvements could be the normal maps to my eye. I'll include the most potential diffuse difference I seen, with this deagle skin below. The pattern on the barrel has banding, the intricate pattern on the grip appears to have slightly sharper definitions of minuscule detail.



Still not enough to fully convince me a higher level diffuse exists, and this was by far the best case I seen to suggest it out of a dozen examples.

On another subject, anyone has worked out a correct hair shader? Diffuse with alpha and normal texture seem straightforward, it's the black and white map I'm not sure about. It didn't look correct as anything I tried so far; spec, roughness, glossiness, both, and as many combinations of those as I thought of.
## Post #266
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-01-31T10:57:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Each buildTable (asset) file has shaders stored in it. Like, plain hlsl text. I could make script dump those so we don't have to guess how they work.
## Post #267
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-01-31T11:37:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sun Jan 31, 2021 6:21 pm at Sun Jan 31, 2021 6:21 pm
>
> 
Took a few menu screenshots for side-by-side looks. The higher quality was obvious enough in all cases, but I couldn't spy any obvious clues about diffuses in specific. Most or all of the improvements could be the normal maps to my eye. I'll include the most potential diffuse difference I seen, with this deagle skin below. The pattern on the barrel has banding, the intricate pattern on the grip appears to have slightly sharper definitions of minuscule detail.

Why don't just use GPA and check the texture resolution?
## Post #268
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-02-03T10:05:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sun Jan 31, 2021 6:57 pm at Sun Jan 31, 2021 6:57 pm
>
> 
Each buildTable (asset) file has shaders stored in it. Like, plain hlsl text. I could make script dump those so we don't have to guess how they work.

If you could make that happen I'd be interested, though I don't yet know how readable hlsl is.

> Reply from floxay ↑Sun Jan 31, 2021 7:37 pm at Sun Jan 31, 2021 7:37 pm
>
> 
Why don't just use GPA and check the texture resolution?

Weell.. It's a good idea. I have PTSD of using that program and it's not installed anymore.    I checked it as above only because it was easy, since I'm questioning the value of exploring more the possibility of tier 4 diffuse. The complete lack of finding any other magic types in those forges leave little wind in those sails.
## Post #269
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-02-08T21:30:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

@Floxay, when you upload models you tag also Roughness map. Which one are you plugging into roughness? For example in the DP27. Unfortunately if there are shaders made up in the .fbx it doesn't perserve it into Blender.
## Post #270
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-02-08T23:30:34+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Tue Feb 09, 2021 5:30 am at Tue Feb 09, 2021 5:30 am
>
> 
@Floxay, when you upload models you tag also Roughness map. Which one are you plugging into roughness? For example in the DP27. Unfortunately if there are shaders made up in the .fbx it doesn't perserve it into Blender.

Inverted G, i'm not sure if it's correct 
actually i know my nodes are not correct but looks okayish  :d
## Post #271
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-02-11T02:06:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Tue Feb 09, 2021 7:30 am at Tue Feb 09, 2021 7:30 am
>
> 
Inverted G, i'm not sure if it's correct 
actually i know my nodes are not correct but looks okayish  :d

Thanks, it's interesting to consider. I like the effects it has on several materials, but found one that it doesn't agree with; there is an important pattern on Aruni's shirt that's defined entirely by the specular, which gets cancelled out. Hmm, I'll continue to be uncertain as well.
## Post #272
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-02-16T23:37:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Thu Feb 11, 2021 10:06 am at Thu Feb 11, 2021 10:06 am
>
> 
Thanks, it's interesting to consider. I like the effects it has on several materials, but found one that it doesn't agree with; there is an important pattern on Aruni's shirt that's defined entirely by the specular, which gets cancelled out. Hmm, I'll continue to be uncertain as well.

I don't think those are visible in-game at all, at least I don't recall seeing those on Aruni's model anywhere else but her artwork, I wouldn't be surprised if even the guys at Ubi don't know how their materials work, a few models are using outdated textures, those are COMPLETELY broken in-game..
## Post #273
- Username: SChopper
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 17, 2021 10:05 pm
- Post datetime: 2021-02-17T19:26:00+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

hello guys, I'm new here and i would like to help.. 

what software you using to rip? i have been ripping models from other games on unreal engine 4
## Post #274
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-02-18T04:33:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Wed Feb 17, 2021 7:37 am at Wed Feb 17, 2021 7:37 am
>
> 
I don't think those are visible in-game at all, at least I don't recall seeing those on Aruni's model anywhere else but her artwork, I wouldn't be surprised if even the guys at Ubi don't know how their materials work, a few models are using outdated textures, those are COMPLETELY broken in-game..

Ah, you're right. I checked the appearance in the game menu, and the right example with G as glossiness looks more correct to that, the pattern is nearly invisible. Maybe we are putting more thought into their materials than they do.  

Though Tushkan, if you're doing the shader dumping thing I'm still more interested than ever. In looking at some non-default skins I noticed one of the tactics they tend to use is to make the diffuse texture grey-scale, and re-color it via the shader itself (using the masks for color separation). Either partially with the aid of tileables (I.e seasonals like neon dawn), or fully with flat colors, and use the greyscale diffuse in an overlay configuration to bring detail back in. It's like lazy mode for low effort skins, but I've seen this in a higher-effort skin too, the ornamental one, which has a bunch of bespoke diffuses but just for some of the harness straps it's greyscale to be colored by shader. Without actual information from their shader we can only eyeball the colors in those cases.

> Reply from SChopper ↑Thu Feb 18, 2021 3:26 am at Thu Feb 18, 2021 3:26 am
>
> 
hello guys, I'm new here and i would like to help.. 

what software you using to rip? i have been ripping models from other games on unreal engine 4

We are using some loose python code and some supporting applications to do it, the link is in Tushkan's signature with instructions.
## Post #275
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-02-18T07:28:08+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Fri Jan 15, 2021 1:15 pm at Fri Jan 15, 2021 1:15 pm
>
> 
Tushkan wrote: ↑Wed Jan 13, 2021 10:17 pm
Try not to check for that specific magic, but rather collect all possible magics. Create a set() and add to it all magics you find. Pdeudocode:
Code: Select allmagics = set()
with r6s.forge.parse(your_forge) as f:
    magics = magics | set(x.file_type for x in f.names)
print(magics)

Chances are they have another container that we've missed.


Setup and ran this method now on half dozen forges, it only reports back the single UID. I'm out of ideas for that.   

I have been putting together Aruni, since I found her whole on basically the first time I searched (I've been saving a list of UIDs to share, but it's just two things right now). I've been pondering on the textures, I got the impression the blue channel is an AO texture and came up with what you can see below, using it in sRGB color space on purpose. That's before I thought to looked at Tushkan's shader. My confidence is not 100% on this. However in defense of it, I was comparing to the in-game character to see if I was getting similar reflectivity, and that brushed metal around Aruni's knee is very shiny and metallic in-game, and this is one of the few uses that preserves that. Using the blue channel as some sort of roughness seems to conflict with that, using it as a glossiness seems to make everything too shiny.




Edit: Btw Jake, about the diffuse textures, they can have slight areas of transparency which can can cause discoloration. If you aren't expecting that it can cause you headaches when it happens, making us thinking the shader is wrong or the lighting is wrong instead. It seems to be related to their subsurf, I haven't worked out that yet.
What's aruni's uuid?
## Post #276
- Username: seraphiel71
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 11, 2021 6:38 am
- Post datetime: 2021-02-18T18:07:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello, any advice on exporting textures. I managed to get the meshes for the dokkaebi elite skin except the eyes. How do i go on about making it search in different forges? I tried to change the name of 
forge_name = 'datapc64_merged_bnk_textures3.forge' 

to like  

forge_name = 'datapc64_merged_bnk_textures2.forge'

didn't really work. I also increased the stop to stop=10000 to get more textures.

Also tried changing the value of  tex.tex_type != 0. still doesn't seem to work. Have read the notepad of the .pys multiple times and can't seem to crack a way to get her textures. I was only able to get 1 basic diffuse by just running the default roam_textures.py.
## Post #277
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-02-18T23:52:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from seraphiel71 ↑Fri Feb 19, 2021 2:07 am at Fri Feb 19, 2021 2:07 am
>
> 
Hello, any advice on exporting textures. I managed to get the meshes for the dokkaebi elite skin except the eyes. How do i go on about making it search in different forges? I tried to change the name of 
forge_name = 'datapc64_merged_bnk_textures3.forge' 

to like  

forge_name = 'datapc64_merged_bnk_textures2.forge'

didn't really work. I also increased the stop to stop=10000 to get more textures.

Also tried changing the value of  tex.tex_type != 0. still doesn't seem to work. Have read the notepad of the .pys multiple times and can't seem to crack a way to get her textures. I was only able to get 1 basic diffuse by just running the default roam_textures.py.

I'm pretty sure it checks the other forges. The workflow seems to be
Find Assets -> Using the uuid of your chosen assets use dump_asset.py to download relevant  textures. 
My understanding is that it automatically searches through linked dependecy textures.
"Now, copy it's filename (it's UID). Open dump_asset.py and paste UID into a UID variable. Run script.

What it will do is it will search for any assets that have this item as a dependency. It will create a folder assets/*asset_uid*, and dump all it's texture and mesh dependencies there."
## Post #278
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-02-19T00:07:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

AYYYY I finished the Dokkabi Elite! (264139768986 Head, 264139769111 Body)



[https://drive.google.com/file/d/1gut3fh ... sp=sharing](https://drive.google.com/file/d/1gut3fhicwB0hs8MbtgAycgkBhw8rMg2-/view?usp=sharing)
## Post #279
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-02-19T00:11:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from gep55 ↑Wed Jan 20, 2021 3:31 am at Wed Jan 20, 2021 3:31 am
>
> 
Just tried to Unpack Iana using this (241085404837) ID and got this error message.

Traceback (most recent call last):
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 89, in <module>
    result = processor(asset_dir, forge, child_uid, index)
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 39, in process_mesh
    mesh = r6s.mesh.Mesh(r)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in __init__
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 238, in <listcomp>
    IslandSkinMapping.parse(r) for _ in range(self.num_islands)
  File "C:\SiegeUnpack\Tools\r6s\mesh\__init__.py", line 134, in parse
    self.x108 = ruint32(r)
  File "C:\SiegeUnpack\Tools\binstream.py", line 34, in ruint32
    return upk('I', r.read(4))[0]
struct.error: unpack requires a buffer of 4 bytes



Also, many items were 'unresolved' during extraction.

Happened to me too, It also took an unusually long time to run, compared to other models. I think it might have been trying to export just too much data and it ran out of memory in the buffer or something
## Post #280
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-02-19T00:23:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from darthme ↑Fri Feb 19, 2021 8:11 am at Fri Feb 19, 2021 8:11 am
>
> 
Happened to me too, It also took an unusually long time to run, compared to other models. I think it might have been trying to export just too much data and it ran out of memory in the buffer or something

It exports a lot of headgears and other skins for Iana as well not just the default ones that's why it takes so long.
## Post #281
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-02-19T00:27:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yea it looks like it exported The Stadium Maps and Skins (uuid: 290915039218)

I wish there was a way to arrange blender files so that everything gets its unique place

Also has someone made a script that automatically textures everything, this is seriously tedious
## Post #282
- Username: seraphiel71
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 11, 2021 6:38 am
- Post datetime: 2021-02-19T08:01:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Seems to work now, I guess i was using the wrong UID for dokkaebi   thank you for the reply, means a lot
## Post #283
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-02-21T22:37:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

An important announcement!
In recent reveal trailer Ubi mentions they are reworking textures storage to a more efficent one. I'm pretty sure it's going to break my scripts. So BACKUP an existing forges archive to be able to rip at least Y5S4 models. I honestly don't know when I'm going to be able to rewrite those to support new stuff.
## Post #284
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-22T15:03:35+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tushkan Thanks that are good info, for people who want use your scripts!
## Post #285
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-02-22T23:25:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

If someone has time and enthusiasm for it, he\she could grab R6S test server client and try ripping something from it using same scripts. If it works then chances are they are going to rewrite textures later this year. If scripts fail, that means reversing is to be done from scratch on those types of data.
## Post #286
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-02-24T13:19:49+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Tue Feb 23, 2021 7:25 am at Tue Feb 23, 2021 7:25 am
>
> 
If someone has time and enthusiasm for it, he\she could grab R6S test server client and try ripping something from it using same scripts. If it works then chances are they are going to rewrite textures later this year. If scripts fail, that means reversing is to be done from scratch on those types of data.

so far everything seems to be working with Y6S1 test server day 2 files just like it did on live servers (Y5S4)

Flores UIDs (please note that high resolution normal and pbr textures are not yet available because the test server doesn't have a UHD texture pack DLC):
314015829770 - hat, facial hair, glasses model etc.
314015829782 - head model
317523773718 - body model
315244481482 - his drone controller model
318852118757 - RCE ratero drone model
## Post #287
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-26T19:33:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Kali Elite: (Helmet UID also contain face with eyes)
MASTERFRAME PROTOTYPE I:

```
Helmet: 282404946849

```

First-Person in-game parts i think, DON'T NEED if you want only HIGH poly model:

```
kali legs 282404947170
kali upper 282404947185

```
## Post #288
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-02-26T19:45:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from JakeMiles ↑Sat Feb 27, 2021 3:33 am at Sat Feb 27, 2021 3:33 am
>
> 
Helmet UID also contain face with eyes

you still have to manually position eyes&mouth, right?
## Post #289
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-26T20:15:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

floxay Yes, need scale and pos. it manualy.
## Post #290
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-02-27T15:41:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from JakeMiles ↑Sat Feb 27, 2021 3:33 am at Sat Feb 27, 2021 3:33 am
>
> 
LOD parts i think, DON'T NEED if you want only HIGH poly model:
Code: Select allkali hands 282404947161
kali legs 282404947170
kali upper 282404947185

I vaguely remember something about LODs being all included in the same mesh file, there's probably a part in Tushkan's script that assumes the highest and sorts it out. I found some different body mesh parts also for Aruni and didn't know what to make of it, but now I'm thinking those sound like the parts needed for first-person view.
## Post #291
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-27T15:58:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Custard
Yeah, i think it for first person presentation hand, body and arms when get something special pose, lie down, sit etc. And it look bad sometime, in-game legs and arms are less than your teammate legs, arms who are lie down too.
## Post #292
- Username: yyred123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 29, 2019 3:24 pm
- Post datetime: 2021-02-28T14:45:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Is it possible to dump the whole map out?
## Post #293
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-03-01T18:13:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Tushkan can we/I post the code to github, I would like to fix some of the code and make the readme easier to understand.
## Post #294
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-03-01T18:18:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from JakeMiles ↑Wed Jan 20, 2021 3:17 am at Wed Jan 20, 2021 3:17 am
>
> 
Tushkan

Here archive with a blend file and asset files : https://dropmefiles.com/JTBtG

The thing expired
## Post #295
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-03T15:44:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from darthme ↑Tue Mar 02, 2021 2:18 am at Tue Mar 02, 2021 2:18 am
>
> 
The thing expired
It not need anymore, i upload it for investigate for material error, wich (texture) are just don't dump right and give problem.
## Post #296
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-03-03T17:40:58+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

darthme yes, I'll be glad if you help me setting up a github repo. I have some experience with git itself, but never tried to publish any repos. You can ping me in discord (Ulibos#3846) so we can make it in realtime.

yyred123 no, not yet. I'm reversing the file in an inefficent way. To do it well I have to dig up the actual game code and reverse that one to retrieve all the structures. For that I have to find a way to break in the middle of a serializer execution and dig my way up the stack. The fact that code is vm protected complicates things. If someone could help me with that, things would go faster. But I haven't found anyone ho has knowledge and time to guide me through an optimal workflow (although there are people who gave valuable hints). Until I get my hands on actual serializer, I doubt maps data will be available.

Custard, sorry for not dropping shaders dump, can't find time, but I do remember about it. And yes, LODs are embedded in same mesh file. It has 1 array of verts and 3 to 5 poly arrays that all point to those verts. Each such poly array is a LOD. This way they don't have to save exclusive set of verts along with UVs and skin weights per LOD.
## Post #297
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-03-03T23:44:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Custard, I've updated the archive. dump_assets.py now also creates a 'shaders' folder and dumps shaders there. Each shader entry has vertex shader, fragment shader and a linkage table. I dump shaders code in separate txt files and I aslo dump linkage table as a raw data. I don't want to waste time guestimating it's tructures. In case you want to dig through it for more data (it has mask linkages at least), then search for:

```
uint32 magic  // local structure magic
uint32 name_length
char[name_length] name
char[] tail  // this one is different depending on magic (both length and data types)

```

There is currently no way to automatically identify which models rely on each shader so you'll have to guestimate. I also named vert and frag shader based on an educated guess. I might have chosen a wrong order, keep that in mind.
## Post #298
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-03-11T09:46:09+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Excellent! I am returning from a trip and will explore that soon. 

Do you think there is a next step to take regarding the normals malformation issue? I was dismissive of it earlier in error, as it turns out some situations hide it's presence effectively. In particular, lighting the scene with only a relatively uniform HDRI with no harshness masks it (All I was used early on). Eevee also hides it better than Cycles. Adding contrast — attempting lighting in depth — makes the problem leap out.




Untitled-1.jpg (81.75 KiB) Viewed 370 times
## Post #299
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-03-11T20:21:22+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Thu Mar 11, 2021 5:46 pm at Thu Mar 11, 2021 5:46 pm
>
> 
 lighting the scene with only a relatively uniform HDRI with no harshness masks it (All I was used early on). Eevee also hides it better than Cycles. Adding contrast — attempting lighting in depth — makes the problem leap out.

Tachanka's elite headgear is completely broken tho no matter what
## Post #300
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-03-15T11:00:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Custard, unless someone provides an info on how game normals are packed in general (or, better yet, for Anvil Next in particular) I see now way of fixing it. All I can do right now is guesstimate which isn't very efficent.

About that shadow bug - what you see is also known as a shadow terminator issue that is pretty pronounced in Cycles ( [https://developer.blender.org/T68920](https://developer.blender.org/T68920) ). Make a perfectly round sphere with not much poly loops, cast a backlight - and you will see same effect. There is a setting (in object tab iirc) that allows to adjust it. I'd rather play with that than try to finesse those normals =)
## Post #301
- Username: Skyborik
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 18, 2021 4:57 am
- Post datetime: 2021-03-16T21:14:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Is there a database for UIDs? I am interested in props from several maps
## Post #302
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-03-18T13:49:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Right now there are only character UIDs published here. So you'll have to dig those yourself. But you can share them when you find em )
## Post #303
- Username: Skyborik
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 18, 2021 4:57 am
- Post datetime: 2021-03-19T19:20:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

By roaming meshes I found some of the props from the maps. I've tried dumping these assets to get the textures but the script has dumped the whole map with all of its meshes and textures. It's a lot of data. I got folders with like 10k files. Is there a way to dump the prop without dumping the whole map?
## Post #304
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-03-20T04:26:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Figured someone might wanna do this as well for shop images and other icons:

changing line 233 in tex.py to this

```
f"{exe} {rewrite}{vflip}-ft png -srgbi -l -f R8G8B8A8_UNORM_SRGB -o {fdir} {fpath}"
```

will output files with lowercase '.png' extension and gamma will be correct in Windows Photos, it is possible that this might require you to change color space in for example Blender

the -l switch (for lowercase extension) requires a newer version of texconv.exe LINK
## Post #305
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-03-20T08:58:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Mon Mar 15, 2021 7:00 pm at Mon Mar 15, 2021 7:00 pm
>
> 
Custard, unless someone provides an info on how game normals are packed in general (or, better yet, for Anvil Next in particular) I see now way of fixing it. All I can do right now is guesstimate which isn't very efficent.

About that shadow bug - what you see is also known as a shadow terminator issue that is pretty pronounced in Cycles ( https://developer.blender.org/T68920 ). Make a perfectly round sphere with not much poly loops, cast a backlight - and you will see same effect. There is a setting (in object tab iirc) that allows to adjust it. I'd rather play with that than try to finesse those normals =)

Hm I see, oh well we'll do what we can. I see that terminator adjustment as well, it's proven useful.

Been looking at the shader data, bit over my head alot of it. Though it confirms the gloss usage floxay told about. It also seems to imply the entire packed texture is plugged in as Specular, not just the green channel as I've been doing. I need to read an article or two on HSLS..   

Btw, don't known if it's still the same now, but the dump_asset.py iteration I got after you updated it for shaders had some returns in it which stopped it dumping anything but shaders. They were handily commented for removal.

Well it's been a while coming but I'm calling Aruni done, she's available now. It should now take me a small fraction of the effort to do any other character from the game to the same standard of completion. I'll try Elite Hibana next and see how true that is.
## Post #306
- Username: CAXX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 06, 2019 7:44 pm
- Post datetime: 2021-03-22T07:29:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Btw, don't known if it's still the same now, but the dump_asset.py iteration I got after you updated it for shaders had some returns in it which stopped it dumping anything but shaders. They were handily commented for removal.

I was thinking it had something to do with the new file structure update, but it was confirmed that there are no problems with that. After looking a bit more carefully at the dump_asset.py code I noticed 2 comments right at the start of both texture and mesh export scripts:

```
    return  # REMOVE THIS!
```


```
    return  # REMOVE THIS!
```


Basically you need to either comment out the early returns or delete them and then the script will dump textures, meshes and shaders as usual.
## Post #307
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-03-24T08:52:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

UID master list up to this point (Includes UIDs contributed previously in this thread by others). I added a bunch of weapons recently, ironically didn't find the one I wanted. I'm guessing about a fifth or so of the guns aren't found in type 9 or 10 AND/OR are in some other .forges, I searched a bit to both of those points and found a few more. Anyway..

```

UID: Title, extra description, data type



# Dumped & Confirmed — Characters


167029278598: Hibana face, Onkochishin Elite skin, texture

167029275631: Hibana body, Onkochishin Elite skin, texture

233351024927: Caveira body, Mata-Leao Elite skin, mesh

233351024906: Caviera head, Mata-Leao Elite skin, mesh

264139768986: Dokkaebi head, Electro Beat Elite skin, mesh

264139769111: Dokkaebi body, Electro Beat Elite skin, mesh

103017200919: IQ head, Reunification Elite skin, mesh

103017200891: IQ body, Reunification Elite skin, mesh

216597865597: Ela head, Huk Sztuki Elite skin, asset

97886035065: Ela body, Huk Sztuki Elite skin, mesh

282404946849: Kali head, Masterframe Prototype I Elite skin, mesh

282404947130: Kali body, Masterframe Prototype I Elite skin, mesh

202726047383: Mira head, Inspiracion Elite skin, mesh

263544687231: Kali head, Glorious Undercut | Kali DJ skin, texture

263544686267: Kali body, Glitter And Ink | Kali DJ skin, texture

66793242130: Caveira face, Death skin, texture

95215538602: Sledge face, Midnight Owl skin, texture

314015829782: Flores head, default skin, mesh

317523773718: Flores body, default skin, mesh

266250227947: Ace body, default skin, mesh

266250227970: Ace head, default skin, mesh

241085404837: Iana torso, default skin, mesh

241085404846: Iana head, default skin, mesh

264139704430: Melusi head, default skin, mesh

264139704396: Melusi body, default skin, mesh

147616585377: Nomad head, default skin, texture

147616584788: Nomad body, default skin, texture

227263212971: Kali body, default skin, mesh

235493608765: Kali head, default skin, mesh

208674001465: Amaru body, default skin, mesh

208674001442: Amaru head, default skin, mesh

242279067640: Oryx body, default skin, mesh

242279067666: Oryx head, default skin, mesh

263931134676: Aruni head, default skin, texture

67256658867: Dokkaebi face, default skin, texture

127545825670: Dokkaebi body, default skin, texture

107655346912: Alibi face, default skin, texture

123072720648: Frost face, default skin, texture

189892751785: Warden face, default skin, texture

66793242130: Caveira face, Death skin, texture

5397612784: Recruit body, default skin, texture




# Dumped & Confirmed — Weapons


217057174575: CSRX 300 Sniper Rifle | Kali, weapon body, mesh

243468289335: DP-27 LMG | Tachanka, weapon body, mesh

266171643779: Shumikha Grenade Launcher | Tachanka, includes a grenade, texture

59618041989: Scorpion EVO3 A1 SMG | Ela, weapon body, mesh

76215890797: SMG-12 Machine Pistol | Dokkaebi Vigil Warden Kali, weapon body, mesh

22439848744: G8A1 LMG | IQ Amaru, weapon body, mesh

59618043111: M762 Assault Rifle | Zofia, weapon body, mesh

76215901416: C75 Auto Machine Pistol | Dokkaebi Vigil, weapon body, mesh

103017210167: ALDA 5.56 LMG | Maestro, weapon body, mesh

22439848746: UMP45 SMG | Castle Pulse, weapon body, mesh

59618054330: FO-12 Shotgun | Ela, weapon body, mesh

90639098098: AUG A3 SMG | Kaid, weapon body, mesh

22439848748: MP5 SMG | Doc Rook Melusi, weapon body, mesh

108454269445: AR-15.50 Assault Rifle | Maverick, weapon body, mesh

125299726592: M4 Assault Rifle | Maverick, weapon body, mesh

22439848753: MP5K SMG | Mute, weapon body, mesh

261495785438: SC3000K Assault Rifle | Zero, weapon body, mesh

61235544839: LMG-E LMG | Zofia, weapon body, mesh

94273697479: Mx4 Storm SMG | Alibi, weapon body, mesh

22439848754: 9mm C1 SMG | Frost, weapon body, mesh

22439848756: P90 SMG | Doc Rook, weapon body, mesh

22439848757: MP7 SMG | Bandit Zero, weapon body, mesh

121497159655: ARX200 Assault Rifle | Nomad Iana, weapon body, mesh 

22439848768: Super 90 Shotgun | Frost Melusi, weapon body, mesh

33059117957: SPAS-15 Shotgun | Caviera, weapon body, mesh

33172963055: M12 SMG | Caviera, weapon body, mesh

96435562483: Baliff410 Handgun | Alibi Maestro, weapon body, mesh

22439848770: M1014 Shotgun | Castle Pulse Thermite, weapon body, mesh

125299752570: SPSMG9 SMG | Clash Kali, weapon body, mesh

22439848771: SPAS-12 Shotgun | Valkyrie Oryx, weapon body, mesh

39244980153: Type-89 Assault Rifle | Hibana, weapon body, mesh

125299797966: 1911 TACOPS Handgun | Maverick, weapon body, mesh

22439848773: M870 Shotgun | Bandit Jager, weapon body, mesh

41317070366: MP5SD SMG | Echo, weapon body, mesh

98615055063: P10 Roni SMG | Mozzie Aruni, weapon body, mesh

134022674869: Super Shorty Shotgun | Gridlock Mozzie Castle, weapon body, mesh

22439848792: MMK1 9mm Handgun | Buck Frost Iana, weapon body, mesh

41317103133: Supernova Shotgun | Echo Hibana Amaru, weapon body, mesh

134022675487: P-10C Handgun | Clash Warden, weapon body, mesh

22439848795: LFP586 Revolver | Doc Lion Montagne Rook Twitch, weapon body, mesh

22439848799: SR-25 Marksman Rifle | Blackbeard Flores, weapon body, mesh

22439848808: F2 FAMAS Assault Rifle | Twitch, weapon body, mesh

42660571740: Commando 9 Assault Rifle | Mozzie, weapon body, mesh

144475058125: AK-74M Asssault Rifle | Nomad, weapon body, mesh

22439848811: C8-SFW Assault Rifle | Buck, weapon body, mesh

42812322408: PDW9 SMG | Jackal, weapon body, mesh

38221878149: C7E Assault Rifle | Jackal, weapon body, mesh

147124412620: .44 Mag Semi-Auto Handgun | Kaid Nomad, weapon body, mesh

22439848812: 416-C Carbine Assault Rifle | Jager, weapon body, mesh

42812471134: SIX12 Shotgun | Ying, weapon body, mesh

42812481247: SIX12 SD Shotgun | Lesion Nokk, weapon body, mesh

71179943556: KERATOS.357 Handgun | Alibi Maestro, weapon body, mesh

22439848817: MK17 CQB Assault Rifle | Blackbeard, weapon body, mesh

148705142142: TCSG12 Shotgun | Kaid Goyo, weapon body, mesh

157897068235: F90 Assault Rifle | Gridlock, weapon body, mesh

22439848825: 417 Marksman Rifle | Lion Twitch, weapon body, mesh

47418176640: Spear .308 Assault Rifle | Finka, weapon body, mesh

159680763236: SDP 9mm Handgun | Gridlock Mozzie, weapon body, mesh

22439848828: CAMRS Marksman Rifle | Buck, weapon body, mesh

48862077931: Q-929 Handgun | Lesion Ying, weapon body, mesh

71269334823: BOSG.12.2 Shotgun | Dokkaebi Vigil, weapon body, mesh

177654242790: M249 SAW LMG | Gridlock, weapon body, mesh

34384197876: M249 LMG | Capitao, weapon body, mesh

48862102629: T-95 LSW LMG | Ying, weapon body, mesh

71269337917: Mk 14 EBR Marksman Rifle | Dokkaebi Aruni, weapon body, mesh

48862224359: T-5 SMG | Lesion Oryx, weapon body, mesh

49109384247: ACS12 Shotgun | Alibi Maestro, weapon body, mesh

21759466570: D-50 Handgun | Blackbeard Nokk Valkyrie, weapon body, mesh

76215837142: K1A SMG | Vigil, weapon body, mesh

42491313886: Vector .45 ACP | Mira Goyo, weapon body, mesh

4487355455: 552 Commando Assault Rifle | IQ, weapon body, mesh

35440479729: Para-308 Assault Rifle | Capitao, 35440479743 mag, mesh

22439848826: R4-C Assault Rifle | Ash, weapon body, mesh

22439848810: G36C Assault Rifle | Ash Iana, weapon body, mesh

22439848791: P12 Handgun | IQ Bandit Jager Blitz, weapon body, mesh

22439848787: 5.7 USG Handgun | Ash Castle Pulse Thermite Nokk Zero, weapon body, mesh

21759285478: M45 MEUSOC Handgun | Ash Castle Pulse Thermite, weapon body, mesh

42812318744: ITA12S Shotgun | Jackal Mira Frost, weapon body, mesh

42812316302: ITA12L Shotgun | Jackal Mira, weapon body, mesh

41317061506: BEARING 9 Machine Pistol | Echo Hibana, weapon body, mesh

22439848829: AR33 Assault Rifle | Thatcher Flores, weapon body, mesh

22439848822: 556xi Assault Rifle | Thermite, weapon body, mesh

22439848813: AK-12 Assault Rifle | Fuze Ace, weapon body, mesh

22439848786: GSH-18 Handgun | Finka Fuze Glaz Kapkan Tachanka, weapon body, mesh

13021213114: PMM Handgun | Finka Fuze Glaz Kapkan Tachanka, weapon body, mesh

21759293095: 9x19VSN SMG | Kapkan Tachanka, weapon body, mesh

42812312330: USP40 Handgun | Jackal Mira Oryx, weapon body, mesh

254397036906: SMG-11 Machine Pistol | Mute Smoke Sledge Amaru, 22439848762 handle folded version, mesh

61235532328: RG15 Handgun | Ela Zofia Melusi, slide pulled back by default, mesh

22439844342: PRB92 Handgun | Capitao Aruni, weapon body, mesh

22439848742: 6P41 LMG | Finka Fuze, weapon body, mesh

22439848750: FMG-9 SMG | Smoke Nokk, weapon body, mesh

22439848777: SG-CQB Shotgun | Doc Lion Rook Twitch, weapon body, mesh

22439848778: M590A1 Shotgun | Mute Smoke Sledge Thatcher Warden, weapon body, mesh

22439848780: P226 MK 25 Handgun | Mute Smoke Thatcher Sledge, weapon body, mesh

22439848789: P9 Handgun | Doc Lion Montagne Rook Twitch, weapon body, mesh

22439848803: AUG A2 Assault Rifle | IQ Wamai, weapon body, mesh

22439848816: L85A2 Assault Rifle | Sledge Thatcher, weapon body, mesh




# Dumped & Confirmed — Gadgets / Misc


315244481482: Flores Drone Controller, , mesh

318852118757: Flores RCE Ratero Drone, , mesh

14393161030: Barb Wire, undeployed version, texture

73289262094: Dokkaebi Tablet, , texture

22060873006: Doc MPD-0 Stim Pistol, , mesh

22060873007: Doc Stim Pistol Syringe, , mesh

4728020462: Smoke Grenade, , mesh

22439849202: Rook Armor Bag, , mesh

44921888897: Mira Black Mirror Frame, , mesh

44593049192: Mira Black Mirror Glass, 46458744628 49408981035, mesh

45755269559: Mira Black Mirror Canister, 45755285152 opened version, mesh

84504787098: Alibi Hologram Character, , mesh

76215954420: Alibi Hologram Base, , mesh

35440397145: Capitao TAC Mk0 Tactical Crossbow, , mesh

41442458334: Echo Yokai Drone, default version, mesh

39085185219: Echo Yokai Drone, elite version, mesh

33059228398: Ela Grzmot Mine, , mesh

39085183651: Hibana X-Kairos Launcher, 40159792505 projectile, mesh

22439849208: Ash Breaching Round Launcher, 22439849020 projectile, mesh

22680798623: Bomb, big objective thing from bomb mode, mesh




# Not Confirmed; Educated Guess


167466514460: Bandit torso, Elite skin, texture

147616585377: Frost face, Elite skin, texture

86825880309: Hibana face, Clan skin, texture

167029284514: Hibana face, default skin, texture

266250238750: Tachanka helmet, Elite skin, texture

266250239016: Tachanka torso, Elite skin, texture

266250238890: Tachhanka legs, Elite skin, texture

266250238848: Tachanka arms, Elite skin, texture

41159237028: Caveira body, Black Leopard skin, texture

208674191421: Wamai face, default skin, texture

208674192919: Wamai legs, default skin, texture

58156742479: Finka face, default skin, texture

58156841305: Finka face, unknown skin without the mask, texture

239222025064: Finka legs, default skin, texture

38223137788: Mira face, default skin, texture

91316034130: Twitch face, Incognito skin, texture

95215482648: Valkyrie face, American Anarchy skin, texture

73522700437: Valkyrie face, Pop Art skin, texture

95215485269: Valkyrie face, default skin, texture

98997255553: Valkyrie body, default skin, mesh

47440353469: Ying face, default skin, texture 

291944602781: Dokkaebi torso, Seoul Active skin, texture

291944602665: Dokkaebi legs, Seoul Active skin, texture

67256453520: Ela face, default skin, texture

105430463739: Lesion face, default skin, texture

195285680207: Goyo face, default skin, texture

198545096973: Maestro face, default skin, texture

291944707168: Maverick torso, Elite skin, texture

291944707292: Maverick head, Elite skin, texture

291944707000: Maverick legs, Elite skin, texture

23140180761: Female Hostage body, , mesh

22439854180: Female Hostage head, , mesh

22439854165: Female Hostage arms, 22439854173 bound version, mesh

14393182590: Target dummy man, , texture

266171643779: Impact grenade, , texture

26204488543: Sledge hammer, , texture

14393160241: Defuser, , texture




# Weapon sights, did not pull corresponding models or textures when asset dumped or behaved strangely.


14393157131: Russian holographic, , texture

14393158146: Russian red dot, , texture

14393157388: Holographic Sight, original version with tan color, texture

23143014245: Red Dot Sight, taller version, mesh

14393158003: Red Dot Sight, for taller version but seems partial, texture

14393158051: Red Dot Sight, short version, texture

22439848903: Reflex Sight, original small optic with the triangular reticule, mesh

22439848935: Laser Attachement, large size for bigger guns, mesh




```


If this project goes on Github maybe this list can have a home and get added to on there a bit easier.
## Post #308
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-03-24T12:09:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Sorry, that's my monkey patching that I forgot to remove. I used it to skip data redumping while I was debugging shader dump. Just cut those returns out and function should proceed as intended. I probably should fix it in my "release" archive too.

As on UID list, I think it's worth integrating it into a lib itself along with a search function. So you can search needed parts by their names. But I'm not the one who's going to implement it in near future. There was a guy who volunteered to help with github release, but he never contacted me again for some reason...
## Post #309
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-03-27T09:15:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm tempted to try a thing or two myself with the code, though considering how useless I am at it I won't seek it on Github for my sake so far.

Searching for 9,10 in datapc64_merged_playgo_bnk_mesh yields what looks like most or all of weapon attachments. Unfortunately trying to dump them has issues. They seem to have lots of associations and it's not long before it throws a "struct.error: unpack requires a buffer of 4 bytes". I guess it would eventually dump a folder containing the appropriate textures if not for that.

If I'm remembering right that error is the script meeting something that hasn't been de-serialized properly, and there was mention of a try-catch block or something to allow the script to continue. I don't remember if that was said to be added or not though?
## Post #310
- Username: Kaitou97
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 04, 2021 3:30 am
- Post datetime: 2021-04-03T19:35:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Fri Jan 08, 2021 8:44 am at Fri Jan 08, 2021 8:44 am
>
> 
Ok boys and girls. It's 2021 and I think it's time to drop some news. I updated my code to work (more or less) with Y5 forges, made a couple scripts to ease the process and now I'm releasing it for you all to use. You can download it here https://www.dropbox.com/sh/b2cuse4hp90y ... qTfja?dl=0
There are readmes for you to be able to set it all up. I might have missed a thing or two while packing so if it breaks - don't panic, just post your problem here.
Also, I have no clue whether Ubi will break their forges again in Y6, so I'd HIGHLY suggest you to backup your current game distro. Would be a shame if next update would render my tool useless and you'd have to wait another 6 months for my patch, eh? )

Hey, i am totally new in python here. i just want to learn and contribute to community for siege files.
i try to read all the thread but didnt found any correct steps to use this . i already installed python 3.6 and also your files R6S. just want to know the next step beside do the directory (D:\my_packages).

Thanks in advance!
## Post #311
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-04-05T11:50:40+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hi, I'm trying to get into dumping from the game again.

I'm running dump_asset.py from the command line, but I get this error message when I do. Does anyone have any insight into this? Thanks 

C:\SiegeUnpack\Tools\scripts>
C:\SiegeUnpack\Tools\scripts>dump_asset.py
  File "C:\SiegeUnpack\Tools\scripts\dump_asset.py", line 41
    out_file = dump_dir / f'{uid}.meshjson'
                                          ^
SyntaxError: invalid syntax
## Post #312
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-04-05T14:06:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

gep55,
Line looks the same as mine except that line is on line 49 instead for me. Perhaps the first thing to try is simply re-download and replace the scripts to make sure they're on the latest and same iteration as each other, and eliminate the possibility of an accidental edit creating the syntax error.
## Post #313
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-04-05T18:19:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thanks, no luck though
## Post #314
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-04-05T18:53:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

what version of python are you using? try to update it?
## Post #315
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-04-05T23:09:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Also consider what the directory is that you are dumping into, as seems to be input into the script at that time. Actually Windows allows some special characters into directories name, when I started with ripping Siege I was working with a directory that included "Tom Clancy's" and the script was not happy about that.
## Post #316
- Username: eiddyJack
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 27, 2020 11:25 am
- Post datetime: 2021-04-10T15:00:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thx for the tools btw
    So i was try to dump the assets i wanted,which Uid is 95215482646(head texture for valkyrie's punk bundle).but it shows error code as followed

```
generating None
Traceback (most recent call last):
  File "F:\exrtR6s\dump_asset.py", line 83, in <module>
    asset_links = data.asset_children.child_in_links(uid)
AttributeError: 'NoneType' object has no attribute 'child_in_links'
```

Any hint on whats going on?
## Post #317
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-04-10T15:49:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

eiddyJack,

That problem is caused by there being no cache generated. I'll simply link you back to the part of the topic where we addressed this:

[viewtopic.php?f=16&t=15031&start=195#p170313](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=195#p170313)

So it's a matter of editing the script to prompt cache generation; it will assess all the siege files and try to record the links between UIDs and save a cache of that for it's reference. You'll want to edit it back to how it was after that's done though, otherwise it'll re-assess all files every time you try to dump something, which is unnecessary. You only need to re-generate cache after a game update.
## Post #318
- Username: eiddyJack
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 27, 2020 11:25 am
- Post datetime: 2021-04-11T12:46:52+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sat Apr 10, 2021 11:49 pm at Sat Apr 10, 2021 11:49 pm
>
> 
eiddyJack,

That problem is caused by there being no cache generated. I'll simply link you back to the part of the topic where we addressed this:

viewtopic.php?f=16&t=15031&start=195#p170313

So it's a matter of editing the script to prompt cache generation; it will assess all the siege files and try to record the links between UIDs and save a cache of that for it's reference. You'll want to edit it back to how it was after that's done though, otherwise it'll re-assess all files every time you try to dump something, which is unnecessary. You only need to re-generate cache after a game update.
Thx for the help,everything works normal now
## Post #319
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-12T15:24:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm a little new to this but I'm looking to get Ela's Huk Sztuk outfit. Where can I find a tutorial here or anywhere else to rip characters from R6S?
## Post #320
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-04-12T23:16:34+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Assasinge ↑Mon Apr 12, 2021 11:24 pm at Mon Apr 12, 2021 11:24 pm
>
> 
I'm a little new to this but I'm looking to get Ela's Huk Sztuk outfit. Where can I find a tutorial here or anywhere else to rip characters from R6S?

There is a read-me along with the needed files, the link to it is in Tushkan's signature.
## Post #321
- Username: eiddyJack
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 27, 2020 11:25 am
- Post datetime: 2021-04-21T10:03:25+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

sit rap.
after diggin though some of those files i got some of my interested mesh dumped

stars zofia  head 328838174598 stars zofia body 328838174569
mira elite head 202017321543 mira elite body 202017320524
elite zofia  head 61972403547  elite zofia body 97886125309 
ash lara head 222130940700 ash lara body 222130940742
Most of those meshes i was founded on datapc64_merged_bnk_mesh.forge
startin from 11000KB to 1000KB roughly is body mesh,head gears and guns.rest of it just manual labor.
## Post #322
- Username: eiddyJack
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 27, 2020 11:25 am
- Post datetime: 2021-04-21T10:09:00+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

btw,how can one distribute more RAM to the script?when i try to dump a weapon such as GIGN revolver (22439848795),it always shows an error message
 as follow:
Traceback (most recent call last):
  File "F:\exrtr6s\scripts\dump_asset.py", line 126, in <module>
    result = processor(asset_dir, forge, child_uid, index)
  File "F:\exrtr6s\scripts\dump_asset.py", line 67, in process_asset
    vert, frag, tail = r6s.asset.parse_shader(data)
  File "F:\Python\lib\site-packages\r6s\asset.py", line 30, in parse_shader
    num_entries = ruint32(r)
  File "F:\Python\lib\site-packages\binstream.py", line 34, in ruint32
    return upk('I', r.read(4))[0]
struct.error: unpack requires a buffer of 4 bytes
## Post #323
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-04-22T10:14:32+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ah, that's not a reference to RAM, the buffer of four bytes it's expecting is part of the file structure it's currently attempting to parse I believe (four bytes is such a minuscule amount of memory). Currently there are a few ways to work around that. In your case you can see from the error that it's failing when trying to parse some shader data. Getting the shader data is more of a research thing, and you can simply disable it to avoid error in that case. Go into the dump_asset script and find the part that looks like this (roughly half way down):

```
def process_asset(dump_dir, forge, uid, entry_index):
```


Right under that line add a return, or you can just copy/past this bit of code (I include a little bit below it to make it clearer, that area should look like this afterwards):

```
    return
    shaders_dir = dump_dir / 'shaders'
    if not shaders_dir.is_dir():
        shaders_dir.mkdir()
    SHADER_MAGIC = 0x1C9A0555
```


There are some other workarounds too but that should fix that one for you.
## Post #324
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-04-23T00:21:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Damn, looks like I really have to fix some of those, too many people are stumbling on same issues way too often...
## Post #325
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-23T11:52:01+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I was going to attempt to try this game but i got to the .forge files and yeah.. too confusing on this extraction.
## Post #326
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-04-23T13:28:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Sharppy ↑Fri Apr 23, 2021 7:52 pm at Fri Apr 23, 2021 7:52 pm
>
> 
I was going to attempt to try this game but i got to the .forge files and yeah.. too confusing on this extraction.

Welp, [https://www.youtube.com/watch?v=FBWeAkB63V4](https://www.youtube.com/watch?v=FBWeAkB63V4)
## Post #327
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-23T21:45:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

22 pages later and i still dont get it. So I agree.
## Post #328
- Username: TarpGuy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 26, 2021 2:52 pm
- Post datetime: 2021-04-26T06:54:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Sharppy ↑Sat Apr 24, 2021 5:45 am at Sat Apr 24, 2021 5:45 am
>
> 
 22 pages later and i still dont get it. So I agree.
Same man... I just wanted to know if someone had extracted the textures from Rainbow Is Magic ^^ ''
## Post #329
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2021-05-12T02:21:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Has anyone managed to find the default Drone model? been going though and have so far only found Twitch's (22439849214) and Echo's (60528523109) drones. 
also looking for Mozzie's spider.
I've found Mozzie's Body (183055478230) Head (183055478269) Spider (the closed one) (155305576993) and the Spider launcher (169914260426)
## Post #330
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-12T08:12:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from YourlordAdam ↑Wed May 12, 2021 10:21 am at Wed May 12, 2021 10:21 am
>
> 
Has anyone managed to find the default Drone model? been going though and have so far only found Twitch's (22439849214) and Echo's (60528523109) drones. 
also looking for Mozzie's spider.
I've found Mozzie's Body (183055478230) Head (183055478269) Spider (the closed one) (155305576993) and the Spider launcher (169914260426)

Yeah it is UID 22439849174, however Floxay already upload it over at p3dm.ru so that's the easiest way to get it.
## Post #331
- Username: EmreCan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 23, 2017 5:06 am
- Post datetime: 2021-05-17T21:45:00+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello Custard,thank you for the models,i wonder can you rip Buck and Buck Elite if its possbile,nobody ripped it yet even his base model.Also his rifle C8-SFW is very unique thanks in advance.
## Post #332
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-17T22:57:52+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from EmreCan ↑Tue May 18, 2021 5:45 am at Tue May 18, 2021 5:45 am
>
> 
Hello Custard,thank you for the models,i wonder can you rip Buck and Buck Elite if its possbile,nobody ripped it yet even his base model.Also his rifle C8-SFW is very unique thanks in advance.

I'm pretty sure Custard reads comments on p3dm, there is no need to spam this xentax thread as well with requests...
/maybe try getting them yourself?/
## Post #333
- Username: EmreCan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 23, 2017 5:06 am
- Post datetime: 2021-05-18T10:57:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Tue May 18, 2021 6:57 am at Tue May 18, 2021 6:57 am
>
> 
EmreCan wrote: ↑Tue May 18, 2021 5:45 am
Hello Custard,thank you for the models,i wonder can you rip Buck and Buck Elite if its possbile,nobody ripped it yet even his base model.Also his rifle C8-SFW is very unique thanks in advance.


I'm pretty sure Custard reads comments on p3dm, there is no need to spam this xentax thread as well with requests...
/maybe try getting them yourself?/

I have tried many times before asking,unfortunately the tool is so complex for me i couldn't even understand the guide.If you can help me and lead me about how to use i would love to extract assets myself without bothering you guys.Thanks in advance.
## Post #334
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-20T04:29:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from EmreCan ↑Tue May 18, 2021 6:57 pm at Tue May 18, 2021 6:57 pm
>
> 
I have tried many times before asking,unfortunately the tool is so complex for me i couldn't even understand the guide.If you can help me and lead me about how to use i would love to extract assets myself without bothering you guys.Thanks in advance.

Yeah it's a bit of a mission to use the scripts, yet it's kinda of for that reason that it's good to see some own initiative from people before embarking to help them. That way, it seems more possible to help them achieve any results. When Tushkan started writing script for this I was literally web searching things like "how do I run a python script". I started this at zero myself, so I'm confident there is enough information between here and other parts of the web to get the results. The Read Me could do with a re-write if we are beleiving it's role is to also teach the basics of things like running Python script at all, but that can be learned from many other places.

See how many point of failure you can surpass with knowledge you can find already, then let us know where you get stuck.
## Post #335
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-05-22T16:39:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey, how can I filter only 1:1 2048x2048 textures in the roam_textures.py?

I tried but I keep getting the 1:2 face textures and I only want gun textures.
## Post #336
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2021-05-22T16:49:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Find

w < 512  # only images that are wider than 512px
or h <512  # only images that are taller than 512px

and change the 512s with 2048 and it *should* only export the 2048 textures
## Post #337
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-05-22T16:53:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I did that but it gives me all the textures.
## Post #338
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-22T17:03:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from YourlordAdam ↑Sun May 23, 2021 12:49 am at Sun May 23, 2021 12:49 am
>
> 
Find

w < 512  # only images that are wider than 512px
or h <512  # only images that are taller than 512px

and change the 512s with 2048 and it *should* only export the 2048 textures
> Reply from dekiroz ↑Sun May 23, 2021 12:39 am at Sun May 23, 2021 12:39 am
>
> 
Hey, how can I filter only 1:1 2048x2048 textures in the roam_textures.py?

I tried but I keep getting the 1:2 face textures and I only want gun textures.
in the if(): continue block:

```
(w, h) != (2048, 2048)
```
## Post #339
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-23T00:16:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

You are better off roaming a lower res texture, takes less time to extract them but more importantly the thumbnails load faster in windows explorer. Even though the weapon itself won't pull skins the skin will have associations with itself, i.e. if you find the 512x512 version you can then dump_asset it's UID to get the max resolution version. Though if it's weapon skins you're after Intel GPA is the best way.
## Post #340
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-05-23T00:34:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

How do I use Intel GPA for that? Do I need an Intel CPU for it to work?
## Post #341
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-23T01:36:24+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from dekiroz ↑Sun May 23, 2021 8:34 am at Sun May 23, 2021 8:34 am
>
> 
How do I use Intel GPA for that? Do I need an Intel CPU for it to work?
Nah I have an AMD CPU myself. I wrote up something about using this program years ago, I think it's mostly still relevant:
[viewtopic.php?f=16&t=15031&start=30#p158679](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=30#p158679)

It's changed a little bit since then, the bug I mention is gone and the interface is a bit different. It's just a program you can download from Intel. Once you have it attached to the running game hit Ctrl+F1 a few times till it shows you the hotkeys, and that will tell you how to take a 'frame'. To open that frame in the analyzer you can find where it was saved and double click on it. Take a frame in-game while holding the item you want the textures from, or maybe it works from the menu in the past I wasn't able to make ti work in the menu.

Textures coming out of that can have wrong orientation, so far it's been flip vertical for me. Check the UVs of the mesh to rationalize it. And normal maps coming out of the game in general are color inverted (obviously) but also in weird format. It should abide by one of these two uses depending on where you intend to use it (Blender is OpenGL, therefore the red channel needs flipping):
## Post #342
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-23T03:14:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sun May 23, 2021 9:36 am at Sun May 23, 2021 9:36 am
>
> 
Textures coming out of that can have wrong orientation, so far it's been flip vertical for me. Check the UVs of the mesh to rationalize it. And normal maps coming out of the game in general are color inverted (obviously) but also in weird format. It should abide by one of these two uses depending on where you intend to use it (Blender is OpenGL, therefore the red channel needs flipping):
I'm pretty sure it's the Y (green) that needs to be flipped when converting between opengl and dx
also blue is completely lost so you either need to recalculate it, flip it or fill it with white/1
## Post #343
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-23T05:09:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun May 23, 2021 11:14 am at Sun May 23, 2021 11:14 am
>
> 
I'm pretty sure it's the Y (green) that needs to be flipped when converting between opengl and dx
also blue is completely lost so you either need to recalculate it, flip it or fill it with white/1
Oh, yeah from a technical perspective I'm thinking of this weirdly. I assumption that people would fill the blue channel with a Ctrl + I basically, which leaves an upside down and mirrored DirectX (or something like that), from which inverting the red gives the OpenGL.
## Post #344
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-05-25T15:50:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

got thunderbird

head 355091298469
body 355091301418
## Post #345
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-25T16:30:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from dekiroz ↑Tue May 25, 2021 11:50 pm at Tue May 25, 2021 11:50 pm
>
> 
got thunderbird

head 355091298469
body 355091301418

full list for thunderbird;
33154480716 - holster - mesh
91271895122 - eye and mouth - mesh
222131100149 - thunderbird body - mesh
326388231464 - thunderbird head - mesh
326388231503 - thunderbird helmet - mesh
357365985691 - thunderbird headgear v2 (no helmet+hair) - mesh
357483124940 - kona station base - mesh
365163784835 - kona station ammo/pill holder - mesh

UHD textures will be available when the patch drops on live
## Post #346
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-05-25T16:37:48+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Wed May 26, 2021 12:30 am at Wed May 26, 2021 12:30 am
>
> 
dekiroz wrote: ↑Tue May 25, 2021 11:50 pm
got thunderbird

head 355091298469
body 355091301418


full list for thunderbird;
33154480716 - holster - mesh
91271895122 - eye and mouth - mesh
222131100149 - thunderbird body - mesh
326388231464 - thunderbird head - mesh
326388231503 - thunderbird helmet - mesh
357483124940 - kona station base - mesh
365163784835 - kona station ammo/pill holder - mesh

UHD textures will be available when the patch drops on live

fastest man alive
## Post #347
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-05-26T02:15:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

mozzie elite eyes and mouth 91271895122
mozzie elite head 183055478256
mozzie elite hat 337222633581
mozzie elite body 337222584245
mozzie elite holster 33154480716

iq cragswoman eyes and mouth 91271895122
iq cragswoman head 259207030492
iq cragswoman hair 355125587113
iq cragswoman body 64744913349
iq cragswoman holster 33154480716

lion elite eyes and mouth 91271895122
lion elite head 337222636151
lion elite hair 337222639053
lion elite body 337222639235
lion elite holster 33154480716

nomad subsister eyes and mouth 91271895122
nomad subsister head 147616584438
nomad subsister hair 338395670709
nomad subsister body 338395670817
## Post #348
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-26T09:58:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey Custard would you mind helping cleaning up the nodes for this or do you have a proper nodegroup for it? The nodes are   
Also I wanna combine the normals into one texture (so no need for the mask and nodes again at a later time) but no idea how to :c
## Post #349
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-05-26T23:47:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun May 23, 2021 11:14 am at Sun May 23, 2021 11:14 am
>
> 
I'm pretty sure it's the Y (green) that needs to be flipped when converting between opengl and dx
also blue is completely lost so you either need to recalculate it, flip it or fill it with white/1

Your assumption about Y axis is correct. DX has it's upper left corner as zero, while GL has it's lower left corner. So their Y axis normal coordinates point in opposite directions.
Your idea to fill z coord with 1 is not particularly good. This will lead to normal's flattening. x,y and z should produce a vector that is exactly 1.0 in length. so you can express it as 1.0 = sqrt(x^2+y^2+z^2) To reconstruct z from x and y you simply have to do z=sqrt(1-x^2-y^2). This stuff is present in my example file along with scripts. Ubi seems to do this a bit trickier but ovarell the result should be the same. BTW, here are a couple of vert shader functions I have stumbled upon:

```

half3 DecompressRawDetail( half3 vNormal )
{
    // Assume that all normals are in DXN (ignore the Z)
    vNormal.xy = -vNormal.xy * 2 + 1;
    vNormal.z = sqrt( 1.0f - saturate(dot( vNormal.xy, vNormal.xy )) );

    // The output normal is signed, but may not be normalized depending on texture values and BumpScale
    return vNormal;
}

half3 BlendDetailMap(half3 _baseNormal, half4 rawDetail)
{ 
    _baseNormal.z += 1;
    half3 detail = DecompressRawDetail(rawDetail.rgb);
    half3 r = _baseNormal * dot(_baseNormal, detail) - detail * _baseNormal.z;
    return normalize(r);

}

float2x2 RotationMatrix(float rotation)  
{  
    float c = cos(rotation);  
    float s = sin(rotation);  
 
    return float2x2(float2(c, -s), float2(s ,c));  
}

```
## Post #350
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-27T00:21:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Thu May 27, 2021 7:47 am at Thu May 27, 2021 7:47 am
>
> 
Your assumption about Y axis is correct. DX has it's upper left corner as zero, while GL has it's lower left corner. So their Y axis normal coordinates point in opposite directions.
Your idea to fill z coord with 1 is not particularly good. This will lead to normal's flattening.

I understand that but the 'flattened' looks 'more correct' most of the time with the original mesh normal data is missing, also thank you for the funcs =)
## Post #351
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-27T04:38:00+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Wed May 26, 2021 5:58 pm at Wed May 26, 2021 5:58 pm
>
> 
Hey Custard would you mind helping cleaning up the nodes for this or do you have a proper nodegroup for it? The nodes are   
Also I wanna combine the normals into one texture (so no need for the mask and nodes again at a later time) but no idea how to :c

Huh, well I'm happy to have a look but I don't think there's a lot I can help you with Floxay. You seems as good or better than me about the materials. For consolidating normal map texture the Cycles baker should make this very easy, it's a method I've used often in my own assets creation at the end to make it a bit of cleaner package.

Not sure if you've done bakiung in Blender before but here's the process. You can ask the baker to take the final state of the normal map as applied to the mesh and put that on a texture for you.

- Go into the shader you want to get processed normal map of.
- Add a new image texture node. This isn't going to be plugged into anything it's going to serve as the target image to bake to, as such it is important that this one be in a 'selected' state when you hit bake. That means it's the node with a highlight around it that you've clicked on last.
- Make a new texture there by pressing new, make the resolution correct and for normal you'd probably want no alpha and 32 bit float.
- Set the color space of that image node to non-color. The color space setting on the node affects the bake result.
- Go Render Properties tab, with it set to Cycles. Change render sampling to 1 sample. In the case where the baker isn't actually taking input from lighting then 1 sample is as good as 1 million sample, but it still wastes time generating as many samples as you set there.
- Down in the same Render Property tab can be found the Bake section. Set bake type to "Normal" and chose margin. Setting a very high margin counts as infinite dilation basically, and low margin + clear image will fill flat normal color between islands.
- Then, with your target image node selected and the object itself still selected hit bake and it should give you out the perfect consolidated normal map.

If the object has multiple shaders on it there will be a message saying no selected image in those other shaders, which is ignorable, OR you may accidentally had an image still selected in one of those other shaders, in which case it probably give a circular dependency error as it tries to bake onto a texture that's already being used by the shader.

Then in image editor section in Blender visual confirm the results and save the image out. If you start adding stuff like modifiers or mesh edit it can end up adding artifacts to the output, but otherwise the results always seem perfect to me. Not like the baking pains you might get when doing high-to-low poly and worrying about cages and rays and all that.
## Post #352
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-27T14:37:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Thu May 27, 2021 12:38 pm at Thu May 27, 2021 12:38 pm
>
> For consolidating normal map texture the Cycles baker should make this very easy, it's a method I've used often in my own assets creation at the end to make it a bit of cleaner package.

I feel like I'm missing something here, the baked normal has no details at all, prolly my nodes, imma watch some blender tutorials, anyway thx for the help Custard
(as for the nodes, i cleaned them up so ig it's OK now)

EDIT: not sure what happened, made a new blend file and it just worked..   now I have a detail normal map for thunderbird's helmet which plugged into your shader's detail normal input works perfectly, I still need to clean it up and add a few things but it's looking good (for portability)
## Post #353
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-28T02:04:40+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Thu May 27, 2021 10:37 pm at Thu May 27, 2021 10:37 pm
>
> 
Custard wrote: ↑Thu May 27, 2021 12:38 pmFor consolidating normal map texture the Cycles baker should make this very easy, it's a method I've used often in my own assets creation at the end to make it a bit of cleaner package.


I feel like I'm missing something here, the baked normal has no details at all, prolly my nodes, imma watch some blender tutorials, anyway thx for the help Custard
(as for the nodes, i cleaned them up so ig it's OK now)

EDIT: not sure what happened, made a new blend file and it just worked..   now I have a detail normal map for thunderbird's helmet which plugged into your shader's detail normal input works perfectly, I still need to clean it up and add a few things but it's looking good (for portability)
The Blender baker use advanced algorithms to determine when to output blank result. The square root of the wind direction and temperature at Schiphol Airport in Amsterdam divided by your Blender version number was probably odd in the last decimal place and Luna was passing it's aphelion point so I don't know why you would have expected it to work at that time.
## Post #354
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-28T02:41:34+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Fri May 28, 2021 10:04 am at Fri May 28, 2021 10:04 am
>
> 
The Blender baker ...

... crashes most of the time when I try to bake normals using nodegroups  , if it's not in a group everything is fine.. anyways here's the helmet in Cycles after all this... worth it i guess
## Post #355
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-28T07:30:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Looks good I'd wear it. I see this time around Ubi has gone with the old faithful 'don't bother' method of making a visor appear capable of being seen through. Not that the metalness 1 of the SSG headgears or alpha transparency of those football number masks were particularly better looking. Game engine showing it's limits I suppose.

By the way that eye in your render looks like the official eye, did you actual manage to assemble a shader for it?
## Post #356
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-05-28T07:58:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Thu May 27, 2021 12:38 pm at Thu May 27, 2021 12:38 pm
>
> 
floxay wrote: ↑Wed May 26, 2021 5:58 pm
Hey Custard would you mind helping cleaning up the nodes for this or do you have a proper nodegroup for it? The nodes are   
Also I wanna combine the normals into one texture (so no need for the mask and nodes again at a later time) but no idea how to :c




Huh, well I'm happy to have a look but I don't think there's a lot I can help you with Floxay. You seems as good or better than me about the materials. For consolidating normal map texture the Cycles baker should make this very easy, it's a method I've used often in my own assets creation at the end to make it a bit of cleaner package.

Not sure if you've done bakiung in Blender before but here's the process. You can ask the baker to take the final state of the normal map as applied to the mesh and put that on a texture for you.

- Go into the shader you want to get processed normal map of.
- Add a new image texture node. This isn't going to be plugged into anything it's going to serve as the target image to bake to, as such it is important that this one be in a 'selected' state when you hit bake. That means it's the node with a highlight around it that you've clicked on last.
- Make a new texture there by pressing new, make the resolution correct and for normal you'd probably want no alpha and 32 bit float.
- Set the color space of that image node to non-color. The color space setting on the node affects the bake result.
- Go Render Properties tab, with it set to Cycles. Change render sampling to 1 sample. In the case where the baker isn't actually taking input from lighting then 1 sample is as good as 1 million sample, but it still wastes time generating as many samples as you set there.
- Down in the same Render Property tab can be found the Bake section. Set bake type to "Normal" and chose margin. Setting a very high margin counts as infinite dilation basically, and low margin + clear image will fill flat normal color between islands.
- Then, with your target image node selected and the object itself still selected hit bake and it should give you out the perfect consolidated normal map.

If the object has multiple shaders on it there will be a message saying no selected image in those other shaders, which is ignorable, OR you may accidentally had an image still selected in one of those other shaders, in which case it probably give a circular dependency error as it tries to bake onto a texture that's already being used by the shader.

Then in image editor section in Blender visual confirm the results and save the image out. If you start adding stuff like modifiers or mesh edit it can end up adding artifacts to the output, but otherwise the results always seem perfect to me. Not like the baking pains you might get when doing high-to-low poly and worrying about cages and rays and all that.
I have found combining two normal maps and then baking those on Blender gives bad results, as seen in my old Shadow of the Tomb Raider models on DeviantArt, for example, the lack of sub-surface scattering on lips. I'd rather use something like Photoshop and CrazyBump to combine multiple normal maps.

I followed this guide and it instantly gave me better results (Photoshop only):
[https://www.youtube.com/watch?v=t8jvroWSCBU](https://www.youtube.com/watch?v=t8jvroWSCBU)
## Post #357
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-28T08:23:17+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Fri May 28, 2021 3:30 pm at Fri May 28, 2021 3:30 pm
>
> 
By the way that eye in your render looks like the official eye, did you actual manage to assemble a shader for it?

It is the official eye with the mouth yes, I just played around with an older eye diffuse Luxox left us 


> Reply from MaZTeR ↑Fri May 28, 2021 3:58 pm at Fri May 28, 2021 3:58 pm
>
> 
I have found combining two normal maps and then baking those on Blender gives bad results

I'm pretty sure that is fixable and just a matter of figuring out the correct node and bake workflow for it. I, personally, will definitely never go with the PS method, it looks like a pain in the ass sadly, I'd rather just fix the normals in blender (if they are actually broken which doesn't seem to be the case for me, rn just doing the mixrgb 0.5 mix and normal strength on 2, it seems to work i guess?)
## Post #358
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-28T11:25:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Fri May 28, 2021 3:58 pm at Fri May 28, 2021 3:58 pm
>
> 
I have found combining two normal maps and then baking those on Blender gives bad results, as seen in my old Shadow of the Tomb Raider models on DeviantArt, for example, the lack of sub-surface scattering on lips. I'd rather use something like Photoshop and CrazyBump to combine multiple normal maps.

I followed this guide and it instantly gave me better results (Photoshop only):
https://www.youtube.com/watch?v=t8jvroWSCBU

We can consider that combining normals map in Blender is an ambiguous action. Baking is by-the-by, cashing in of whatever work you've already done with the nodes. That work can be mixing normals with a MixRGB node in 3 seconds, or running them through a series of math nodes based on a presumably 'correct' method.

It was no long since I took the time to research the subject and get myself such a node group. I read a few papers and threads of the subject, and tried about 5 different node groups. They all either made mistakes that made the situation worse due to too little field testing or were imperceptible from a simple overlay mix, until the last one. As soon as I plugged in the last one I could see how overlay was inferior, the advanced method made the overlay look slightly blurry or flattened.

I will link it here so that you can use it if you want to and see if you like it. An empty .blend file with the node group for appending from. Of course using it without bothering to bake or combine any textures is the most convenience method of all.

[https://mega.nz/file/SpgUhCIL#peMAl4OOj ... PaRIEXif6Q](https://mega.nz/file/SpgUhCIL#peMAl4OOjSOi-R4YcBLNg943-wQhmbi1gPaRIEXif6Q)
## Post #359
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-05-28T12:00:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Fri May 28, 2021 4:23 pm at Fri May 28, 2021 4:23 pm
>
> 
Custard wrote: ↑Fri May 28, 2021 3:30 pm
By the way that eye in your render looks like the official eye, did you actual manage to assemble a shader for it?


It is the official eye with the mouth yes, I just played around with an older eye diffuse Luxox left us 

MaZTeR wrote: ↑Fri May 28, 2021 3:58 pm
I have found combining two normal maps and then baking those on Blender gives bad results


I'm pretty sure that is fixable and just a matter of figuring out the correct node and bake workflow for it. I, personally, will definitely never go with the PS method, it looks like a pain in the ass sadly, I'd rather just fix the normals in blender (if they are actually broken which doesn't seem to be the case for me, rn just doing the mixrgb 0.5 mix and normal strength on 2, it seems to work i guess?)
You can make a macro that does all of that in an instant.

Plus, it makes the texture work outside Blender.
## Post #360
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-05-28T12:04:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Fri May 28, 2021 7:25 pm at Fri May 28, 2021 7:25 pm
>
> 
MaZTeR wrote: ↑Fri May 28, 2021 3:58 pm
I have found combining two normal maps and then baking those on Blender gives bad results, as seen in my old Shadow of the Tomb Raider models on DeviantArt, for example, the lack of sub-surface scattering on lips. I'd rather use something like Photoshop and CrazyBump to combine multiple normal maps.

I followed this guide and it instantly gave me better results (Photoshop only):
https://www.youtube.com/watch?v=t8jvroWSCBU


We can consider that combining normals map in Blender is an ambiguous action. Baking is by-the-by, cashing in of whatever work you've already done with the nodes. That work can be mixing normals with a MixRGB node in 3 seconds, or running them through a series of math nodes based on a presumably 'correct' method.

It was no long since I took the time to research the subject and get myself such a node group. I read a few papers and threads of the subject, and tried about 5 different node groups. They all either made mistakes that made the situation worse due to too little field testing or were imperceptible from a simple overlay mix, until the last one. As soon as I plugged in the last one I could see how overlay was inferior, the advanced method made the overlay look slightly blurry or flattened.

I will link it here so that you can use it if you want to and see if you like it. An empty .blend file with the node group for appending from. Of course using it without bothering to bake or combine any textures is the most convenience method of all.

https://mega.nz/file/SpgUhCIL#peMAl4OOj ... PaRIEXif6Q

A complex math node is really the only way to get the normal maps look correct if you know what you are doing. However, it's way out of my league.

Mix RGB adds too much noise and blur to the texture in my opinion.
## Post #361
- Username: bumba
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 28, 2021 11:00 pm
- Post datetime: 2021-05-28T15:22:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello guys! I wonder if somebody are interested in weapon skins. Could anyone tell me C8 sfw glacier's UID or any other glacier skin uid? it's so beautiful. 

Cheers
## Post #362
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-05-29T00:28:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Mix RGB should not alter textures in any particular way. However, there are things to account for, for example, many render passes get treated as if they are a beauty channel that needs color management. So blender might apply filmic profile to normal map, basically squishing it's vectors and possibly even tilting them. Not that I tested that particular setup but it's worth checking. If anyone wants, he can drop a ling to some assembled ready-for-baking file and I will take a look at what goes wrong (no promises on results though).
## Post #363
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-05-29T05:12:24+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Sat May 29, 2021 8:28 am at Sat May 29, 2021 8:28 am
>
> 
Mix RGB should not alter textures in any particular way. However, there are things to account for, for example, many render passes get treated as if they are a beauty channel that needs color management. So blender might apply filmic profile to normal map, basically squishing it's vectors and possibly even tilting them. Not that I tested that particular setup but it's worth checking. If anyone wants, he can drop a ling to some assembled ready-for-baking file and I will take a look at what goes wrong (no promises on results though).

Hmm, when I've baked normals before using previous mentioned process I checked the flat color between the margins after and it was 128,128,255 as expected. For color management of baking or simply using any texture in Blender I thought that setting the node color space to non-color will make it immune to color management.

Here is a little Blender file set up as a comparison between my current nodegroup method and a lazy mixRGB method to examine it's effects. It clearly helps prevent flattening of details:
[https://mega.nz/file/y9IgBbYT#POpFGrYUm ... p-vFWJI9SI](https://mega.nz/file/y9IgBbYT#POpFGrYUmqPk7znf2JzhKCY9igTDjzNw1p-vFWJI9SI)

This is an Overlay use, the 50% Mix with normal strength to 2 that Floxay mentioned is a much closer result. It's interesting to play with anway.




Untitled-1.jpg (52.63 KiB) Viewed 372 times



This node group was based mainly on the Reoriented Normal Mapping method as detailed in this article:
[https://blog.selfshadow.com/publication ... in-detail/](https://blog.selfshadow.com/publications/blending-in-detail/)
Extra comparisons between some other popular methods and this one:
[https://blog.selfshadow.com/sandbox/normals.html](https://blog.selfshadow.com/sandbox/normals.html)

> Reply from bumba ↑Fri May 28, 2021 11:22 pm at Fri May 28, 2021 11:22 pm
>
> 
Hello guys! I wonder if somebody are interested in weapon skins. Could anyone tell me C8 sfw glacier's UID or any other glacier skin uid? it's so beautiful. 

Cheers
I don't think anyone has bothere recording any weapon skin UIDs, since they are more annoying to search for. If you're really interested I suggest the Intel GPA method for weapon skin as I mention about on the previous page.
## Post #364
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-05-29T16:48:18+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

ubi brain , can't wait for UHD texture pack lol, just gotta figure out how to get the original scale (and rotation maybe?) for these normal maps instead of just eyeballing the values
## Post #365
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-05-30T12:14:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Texture scale and rotation are nested inside asset file. I honestly doubt I'm ever going to reverse those because there is no fixed-size structure to it with branching node trees. It's too tedious to reverse manually, best way is to attach to game process, halt it mid forge read, detect code that is responsible for unpacking the data, unvirtualize it and reverse. All of this is still too hard for me. I can't even halt ip properly. x64dbg fails to keep game alive (game almost always crashes on 1st or 2nd halt with some exception). CheatEngine can halt the game but I can't find a way to make it halt the game mid-run. It only accepts placing breakpoints. But I can't place it because I don't know which part of code is responsible for forge unpacking. And searching for it manually yields no results because this code is virtualized. So for now no proper skeleton extraction (what I was actually after to begin with) and no extra textures data.
## Post #366
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-02T19:00:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Mon Mar 15, 2021 7:00 pm at Mon Mar 15, 2021 7:00 pm
>
> 
Custard, unless someone provides an info on how game normals are packed in general (or, better yet, for Anvil Next in particular) I see now way of fixing it. All I can do right now is guesstimate which isn't very efficent.

This is hardly any help, I know, but recently take a closer look on ripped models and the (presumably) TBN matrix it gave, interestingly the normals seem to be incorrect (just like with the script) on character meshes, guns look correct with these, here's a quick comparison;


and another one: 
the ripped is the one in the back, circled the most obvious stuff
## Post #367
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-06-05T08:40:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Umm what is difference of "script" and "ripped" in the method? My confusion is from thinking that script = ripped, since I run the script and it gives me a ripped thing and I don't know of another way (Discounting IGPA).
## Post #368
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-05T10:40:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sat Jun 05, 2021 4:40 pm at Sat Jun 05, 2021 4:40 pm
>
> 
Umm what is difference of "script" and "ripped" in the method?

Ripped = ripped from memory (example: GPA), not extracted from forge files
## Post #369
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-06-06T01:34:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Oh so I'm guessing you did some mesh data transfer to put the ripped normal data and UVs together on the same mesh? Interesting idea.
## Post #370
- Username: Dan00ile
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 06, 2021 6:45 pm
- Post datetime: 2021-06-06T10:47:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hi, what program can I use to extract 3d models from rainbow six?
## Post #371
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-07T00:56:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sun Jun 06, 2021 9:34 am at Sun Jun 06, 2021 9:34 am
>
> 
Oh so I'm guessing you did some mesh data transfer to put the ripped normal data and UVs together on the same mesh? Interesting idea.

No, one of those is entirely from ripped data and the other one is from extracted data (using same material), if you look closely you can see how the bipods or whatever those are differ in position as in the game the DP27 has a base 'animation' pose for it which is different from the model space.
## Post #372
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-24T01:39:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey, guys im new and ive looked through the forum and see mentions of a 'guide' but can't see a link to it, does it exist and if so does someone have a link to it?
## Post #373
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-06-24T02:34:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I was thinking about making one the process is quite complex. If you read page 1-3. It lays it out pretty much. I was able to get the models finally from this post. You just have to read carefully. There are Readme files in the tools. Read them and you will be able to figure it out. 
[](https://ibb.co/m0n2SmF)
## Post #374
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2021-06-24T15:46:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

is there any way to extract audio? specifically voice lines.
## Post #375
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-24T19:32:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from YourlordAdam ↑Thu Jun 24, 2021 11:46 pm at Thu Jun 24, 2021 11:46 pm
>
> 
is there any way to extract audio? specifically voice lines.

audio seems to be just wwise wems inside soundmedia forges, you could just use ravioli game tools to get most of them, obviously no filenames or even the IDs tho
## Post #376
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-24T21:46:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Im just trying to clear the air on the current method, not just for me but potential helpers. Tushkan has his unpacking tool, Archive_Next has one that i cant get my hands on, Lux uses Intel GPA and hex to OBJ from another forum, and finally Delutto's tool. All of these seemed to work at one point or another, yet I cant get any to work for myself (and I assume others), which sucks because the more people helping would speed up the project exponentially. If anyone Custard, Floxay, or Tushkan, can lend me a hand id appreciate it.
## Post #377
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-24T21:58:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Fri Jun 25, 2021 5:46 am at Fri Jun 25, 2021 5:46 am
>
> 
Im just trying to clear the air on the current method, not just for me but potential helpers. Tushkan has his unpacking tool, Archive_Next has one that i cant get my hands on, Lux uses Intel GPA and hex to OBJ from another forum, and finally Delutto's tool. All of these seemed to work at one point or another, yet I cant get any to work for myself (and I assume others), which sucks because the more people helping would speed up the project exponentially. If anyone Custard, Floxay, or Tushkan, can lend me a hand id appreciate it.

Delutto's tool is archive_next iirc, here's the link: [http://www.tbotr.net/Downloads/ARchive_neXt.msi](http://www.tbotr.net/Downloads/ARchive_neXt.msi)
this PARTIALLY worked around velvet shell (2017 feb)

Yes, Luxox used GPA in the beginning, then switched to archive_next then back to GPA AFAIK

If you follow Tushkan's README's you should be able to get his tool working, it's really not that hard, I believe you need to fix 2 lines of "input()", just replace the comma with + (plus sign) and remove the returns in the first line of the functions of dump_asset.py

I personally just rip the weapon models so I have correct original normals for those now, can't seem to find an easy way to do the same for characters tho :c
## Post #378
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-26T22:56:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Anyone knows why UVs break upon exporting from Blender?
## Post #379
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-26T23:24:58+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from dimis9138 ↑Sun Jun 27, 2021 6:56 am at Sun Jun 27, 2021 6:56 am
>
> 
Anyone knows why UVs break upon exporting from Blender?

They don't, if they do then that's an issue with your Blender installation or the export settings/format/plugin you are using.
## Post #380
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-27T01:07:01+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Jun 27, 2021 7:24 am at Sun Jun 27, 2021 7:24 am
>
> 
dimis9138 wrote: ↑Sun Jun 27, 2021 6:56 am
Anyone knows why UVs break upon exporting from Blender?


They don't, if they do then that's an issue with your Blender installation or the export settings/format/plugin you are using.

UVs are fine in Blender, exporting it breaks it. I tried with 2.83, 2.93 and 2.49

EDIT: Tried with 2.91 also and tried exporting as .obj, .fbx and .dae.

EDIT 2: Talked with floxay over disc, only way for me to get it to work in versions under Max 2021 was to separate mesh by materials in Blender and then export as obj and then import that into 2021 and export as 2013 ver fbx and import to 19/16.
## Post #381
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2021-06-27T07:49:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

So does anyone have a good shader for the Eyes? im trying to set mozzie up but only found that weird eye texture that dumps with every head. (blender ofc)
## Post #382
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T05:23:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey sorry to bother the thread again but im getting this error within pycharm when trying to run the texture unpacker. Any ideas?
[Capture2.PNG](https://xentaxbackup.github.io/file/20376_Capture2.PNG)
## Post #383
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-29T05:28:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Oh that is rather easy to fix, have you tried [googling](https://www.google.com/search?q=modulenotfounderror) it yet?
## Post #384
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T06:10:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Tue Jun 29, 2021 1:28 pm at Tue Jun 29, 2021 1:28 pm
>
> 
Oh that is rather easy to fix, have you tried googling it yet?

Cause now I get this which seemed to have worked up until the end
[Capture3.PNG](https://xentaxbackup.github.io/file/20377_Capture3.PNG)
## Post #385
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-29T06:47:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Tue Jun 29, 2021 2:10 pm at Tue Jun 29, 2021 2:10 pm
>
> 
floxay wrote: ↑Tue Jun 29, 2021 1:28 pm
Oh that is rather easy to fix, have you tried googling it yet?


Cause now I get this which seemed to have worked up until the end

See [#175787](https://forum.xentax.com/viewtopic.php?f=16&t=15031&p=175787#p175787#:~:text=I%20believe%20you%20need%20to%20fix%202%20lines%20of%20%22input%28%29%22,%20just%20replace%20the%20comma%20with%20+%20%28plus%20sign%29%20and%20remove%20the%20returns%20in%20the%20first%20line%20of%20the%20functions%20of%20dump_asset.py)
## Post #386
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T07:06:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Tue Jun 29, 2021 2:47 pm at Tue Jun 29, 2021 2:47 pm
>
> 
Kluhez wrote: ↑Tue Jun 29, 2021 2:10 pm
floxay wrote: ↑Tue Jun 29, 2021 1:28 pm
Oh that is rather easy to fix, have you tried googling it yet?


Cause now I get this which seemed to have worked up until the end


See #175787

alright i fixed that got another error then fixed that, then ran it and it exported nothing does this seem proper (im also using a cracked year 1 for the forge files, does this affect it also?)
## Post #387
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-29T07:15:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Tue Jun 29, 2021 3:06 pm at Tue Jun 29, 2021 3:06 pm
>
> 
im also using a cracked year 1 for the forge files, does this affect it also?
 

most likely
## Post #388
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T07:21:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

yeah i woulldve guessed ill try both a newer cracked versions and a regular steam distro. and compare tommorow. Thank you  a lot for the help btw.
## Post #389
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T17:41:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The roam_textures runs fine and says it exported the files yet the folder ive set the export to, doesnt contain any files. Any idea whats making this happen?
[Capture5.PNG](https://xentaxbackup.github.io/file/20384_Capture5.PNG)
## Post #390
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-29T18:00:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

did you look at the script folder as well?
## Post #391
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T18:03:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Wed Jun 30, 2021 2:00 am at Wed Jun 30, 2021 2:00 am
>
> 
did you look at the script folder as well?
Thats where it is thanks! Is there a reason the set destination doesnt work?
## Post #392
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-29T18:04:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Wed Jun 30, 2021 2:03 am at Wed Jun 30, 2021 2:03 am
>
> 
Thats where it is thanks! Is there a reason the set destination doesnt work?

plain uncompressed data is not exactly what you are looking for
## Post #393
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T20:16:45+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Alright back again, and finally was able to import the meshjson files from 'datapc64_merged_bnk_000000021_mesh' and it looked like assets from the map Bank but also had 2 guns and 2 bodies + 1 head. attached below. Now the mp5K was imported fully textured, but nothing else. Should I upload that to p3dm as is or is there more beauty work i need to do? 
edit: link [https://imgur.com/a/LmwcU6E](https://imgur.com/a/LmwcU6E)
## Post #394
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-29T21:03:02+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Wed Jun 30, 2021 4:16 am at Wed Jun 30, 2021 4:16 am
>
> 
the mp5K was imported fully textured, but nothing else

That mp5 is only textured because Tushkan textured it, it was already in the included blend along with a skin of Caveira IIRC.

The script won't import you models with set-up, ready to use materials, it's all manual work to set those up.
## Post #395
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T21:10:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ah i dont know how that slipped my mind.
## Post #396
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-29T22:07:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Quick question are the UIDs the number names of the blender models, cause if so I have Frost elite body, comp mozzie 20' body, Bain bucket mozzie headgear, valk elite headgear, and a few other bodies and heads that i know the op of but not the specific skin. Also how would I go about importing legs, hands etc, and texturing the character?
## Post #397
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-06-30T10:59:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

settings.EXPORT is a remnant of my initial research. It was used to initially dump raw data while I was reversing forges. It is not used in dump scripts. Scripts dump stuff next to themselves to keep it more or less in one place.

You can't unpack forges that are pre Breakout event because this is roughly where they [again] changed internal forge's structure. I have code that can unpack older forges (but not years 1-2, those didn't use zstd, my code only works with zstd versions) but it's not integrated in the published tool.

Yes, file names are original UIDS from forge data. I asked everyone to gather those because I was planning to build a small database containing all known parts. However, I never came to implementing it actually.

There is no way to automatically build an asset. This would require to parse an asset file which is too complex to reverse engineer by hand. Script only provides you with more or less relevant pieces of an asset. Everything else is up to one to rebuild manually. You can use my example models to get an idea of how those are formed. But asking floxray or Custard for their shaders would be better because they managed to figure out how texture details are used.
## Post #398
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-30T15:28:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thank you now I think i have a better grasp on what the parts are doing but Ive hit another snag. Im trying to texture this Frost Elite, yet when I apply an image texture to the body only the straps get textured and the rest stay white. (I have the same issue with the legs but the reverse). Ive only worked with meshes that have a single image texture per mesh so this confuses me.

[https://imgur.com/a/1rRTjeM](https://imgur.com/a/1rRTjeM)
## Post #399
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-30T16:02:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Wed Jun 30, 2021 11:28 pm at Wed Jun 30, 2021 11:28 pm
>
> 
when I apply an image texture to the body only the straps get textured and the rest stay white

change slot
## Post #400
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-30T16:29:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ive never seen that but thats for my lack of 3d experience. Also with the addition of now skins are they packed into a random forge or will they be put into the last forge? (Wondering because of the new mozzie skin added recently)
## Post #401
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-06-30T18:33:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

everything persistent gets merged into the base forges sooner or later but you can't really count on that

what is already released is definitely in the base forges unless it gets an update, in that case it gets put into another forge and merged to base forges later

mozzie elite is in the base forge (pretty much the biggest one with merged in its name, cant recall the name of it rn) I can give you the elite mozzie UIDs (forges IDs) later but i believe it was posted here before by @dekiroz

also the mozzie elite head and hair meshes dont seem to be placed correctly in modelspace, you have to manually position those after importing as we don't have bindpose or anything like that with this script exported (yet, hopefully)

EDIT: yes, dekiroz posted it [#174799](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=345#p174799) (don't dump the head mesh as that is the base one and you'd get all mozzie headgear skins too, only dump the 'hat' and 'body', if you want the props used in his MVP animation: 346925989708)
Also datapc64_merged_bnk_000000021_mesh.forge is the name of the merged forge holding most of the interesting meshes

EDIT 2: Here's an eye diffuse for mozzie [https://i.ibb.co/LQD0yZ8/CHR-SASR-Mozzi ... iffuse.png](https://i.ibb.co/LQD0yZ8/CHR-SASR-Mozzie-Eye-Diffuse.png)
## Post #402
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-06-30T23:07:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

This is my first time using Mega so let me know if the link isnt working, but i sorted through 300 or so charms but have yet to texture them, the majority of them being chibis and ranked charms.
<link with game assets has been deleted by moderator>
## Post #403
- Username: DeadmanWasTaken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 01, 2021 3:53 pm
- Post datetime: 2021-07-01T08:02:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey, this looks really good and I was wondering if you could extract all of the weapon models/textures for me. If you want I found a list of each UID for some people on this thread. [https://drive.google.com/file/d/12NTfPx ... sp=sharing](https://drive.google.com/file/d/12NTfPxCBzbUR6CPoLQPqLzp6EyLiFkcZ/view?usp=sharing) Thank you!
## Post #404
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-01T21:11:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Floxxay how do you sort through these models, What im doing is sorting by the 3rd to last number in the uid, and that gets some full models like rook and twitch elites but others only i only find their hands, is this because i split the forges export? (I split them by 1000s)

[https://imgur.com/gallery/Tx9xfr4](https://imgur.com/gallery/Tx9xfr4)
## Post #405
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-02T19:53:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from DeadmanWasTaken ↑Thu Jul 01, 2021 4:02 pm at Thu Jul 01, 2021 4:02 pm
>
> 
Hey, this looks really good and I was wondering if you could extract all of the weapon models/textures for me. If you want I found a list of each UID for some people on this thread. https://drive.google.com/file/d/12NTfPx ... sp=sharing Thank you!

Hey Floxy, uploaded a bunch already to p3dm but i made a list with the ones already uploaded (Green), and ones I currently have and are working on in blender (untextured and no mags (Orange)). Im dumping Bandit's MP7, and will work on the others, if you have something specific?
[https://docs.google.com/spreadsheets/d/ ... sp=sharing](https://docs.google.com/spreadsheets/d/1F21f6YyjtKe5RhzElli85jutXNew6TMMTz38c-7jrYE/edit?usp=sharing)
## Post #406
- Username: DeadmanWasTaken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 01, 2021 3:53 pm
- Post datetime: 2021-07-03T05:01:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

The spreadsheet is locked by the way so I can't view it, but no I don't really have any weapon in mind. It's just nice knowing that I could have every weapon available to me as I want to add them to Boneworks. Does anybody know and method of extract sounds as well? Right now I have to record them in-game and there is a lot of background nice, as well as the fact that when your in a different room there is more or less reverb applied over the firing sound.
## Post #407
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-03T06:32:19+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from DeadmanWasTaken ↑Sat Jul 03, 2021 1:01 pm at Sat Jul 03, 2021 1:01 pm
>
> 
Does anybody know and method of extract sounds as well?

Wwise Unpacker worked on the first season of the game but havent tested it on the newest version. Youd have to sift through the files as a lot of them are groans and short music notes.
## Post #408
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-03T10:34:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I also struggled for a long time with combining normal maps in Blender. 

The normal map is vectors, so we can convert the color to a vector, we do this for both maps.

rotate the primary vector by adding rotation of secondary vector.

Then convert it all back to colorspace.
I made a node group that will mathematically combine 2 vectors. it has MASK inputs, and can easily be nested.
Stert with base normal map, and add the detail maps.

[https://drive.google.com/file/d/1ydaj5L ... sp=sharing](https://drive.google.com/file/d/1ydaj5L0TNGtWXhQZIgGXUQgzFEwQBISn/view?usp=sharing)
## Post #409
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-07-03T13:03:30+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Sat Jul 03, 2021 6:34 pm at Sat Jul 03, 2021 6:34 pm
>
> 
I also struggled for a long time with combining normal maps in Blender. 

The normal map is vectors, so we can convert the color to a vector, we do this for both maps.

rotate the primary vector by adding rotation of secondary vector.

Then convert it all back to colorspace.
I made a node group that will mathematically combine 2 vectors. it has MASK inputs, and can easily be nested.
Stert with base normal map, and add the detail maps.

https://drive.google.com/file/d/1ydaj5L ... sp=sharing

Interesting, but I confused on the usage. Sockets color seem to imply like this with tangent space conversion first, straight to shader after?




Untitled-1.jpg (71.44 KiB) Viewed 163 times
## Post #410
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-03T15:34:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sat Jul 03, 2021 9:03 pm at Sat Jul 03, 2021 9:03 pm
>
> 
Interesting, but I confused on the usage. Sockets color seem to imply like this with tangent space conversion first, straight to shader after?

looks like it's from this video; [https://www.youtube.com/watch?v=keCu8mfoKEA](https://www.youtube.com/watch?v=keCu8mfoKEA) with the option to add a mask, so just connect the image texture node to the vector input
## Post #411
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-03T16:46:39+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sat Jul 03, 2021 11:34 pm at Sat Jul 03, 2021 11:34 pm
>
> 
Custard wrote: ↑Sat Jul 03, 2021 9:03 pm
Interesting, but I confused on the usage. Sockets color seem to imply like this with tangent space conversion first, straight to shader after?


looks like it's from this video; https://www.youtube.com/watch?v=keCu8mfoKEA with the option to add a mask, so just connect the image texture node to the vector input

Indeed, I knew there was a mathematical solution to this. Normal maps are vectors. I was struggling with this for a a very long time. And this video fixed the mistakes I made.

My original concept was to Vres=V1+V2, getting the new reflection angle by adding the vectors, and normalize the result. That does not work, that will give you an average of the 2 vectors.
## Post #412
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-03T16:50:03+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Sat Jul 03, 2021 9:03 pm at Sat Jul 03, 2021 9:03 pm
>
> 
Ankhati wrote: ↑Sat Jul 03, 2021 6:34 pm
I also struggled for a long time with combining normal maps in Blender. 

The normal map is vectors, so we can convert the color to a vector, we do this for both maps.

rotate the primary vector by adding rotation of secondary vector.

Then convert it all back to colorspace.
I made a node group that will mathematically combine 2 vectors. it has MASK inputs, and can easily be nested.
Stert with base normal map, and add the detail maps.

https://drive.google.com/file/d/1ydaj5L ... sp=sharing


Interesting, but I confused on the usage. Sockets color seem to imply like this with tangent space conversion first, straight to shader after?


Untitled-1.jpg

The node only calculate a new normal map. I refuse to say "mixing" because this isn't what is happening. A new map is calculated.
[Capture.PNG](https://xentaxbackup.github.io/file/20408_Capture.PNG)
## Post #413
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-07-04T01:12:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Sun Jul 04, 2021 12:50 am at Sun Jul 04, 2021 12:50 am
>
> 
Custard wrote: ↑Sat Jul 03, 2021 9:03 pm
Ankhati wrote: ↑Sat Jul 03, 2021 6:34 pm
I also struggled for a long time with combining normal maps in Blender. 

The normal map is vectors, so we can convert the color to a vector, we do this for both maps.

rotate the primary vector by adding rotation of secondary vector.

Then convert it all back to colorspace.
I made a node group that will mathematically combine 2 vectors. it has MASK inputs, and can easily be nested.
Stert with base normal map, and add the detail maps.

https://drive.google.com/file/d/1ydaj5L ... sp=sharing


Interesting, but I confused on the usage. Sockets color seem to imply like this with tangent space conversion first, straight to shader after?


Untitled-1.jpg


The node only calculate a new normal map. I refuse to say "mixing" because this isn't what is happening. A new map is calculated.

If it's not a mixture then it'd be able to do something without plugging in two normal maps.   Mixin g something doesn't preclude a new thing being created, just the opposite.

I like it. It's based on the exact same principle that I read in the re-oriented normal map paper and that my current node is based on, except it's a more elegant implementation of that into Blender nodes with the vector functions. My assessment is that — with most differences being very small — your node is slightly less prone to blow out on flat geometry with extreme examples, slightly more prone (to a lesser degree) to blown out on curvy geometry with extreme examples, and retains a little more sharpness at low combine factors giving a better feeling to the factor use.

Here my little test setup if you care to look, results are the most honest. Best to open with UI setting retained.
[https://mega.nz/file/jppwACpY#Yill0WKJw ... QrF1kVoOCY](https://mega.nz/file/jppwACpY#Yill0WKJw7M4o6sr1HiT3h4PVGCrk7ClKQrF1kVoOCY)
## Post #414
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-04T06:31:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I like your setup, it is a different approach than to rotate the vector on an axis.
Originally, I am trying to make a node for DAZ3D, it has math blocks, but no rotate vector. I will try your setup iun DAZ3d, and hopefully it will work.


> Reply from Custard ↑Sun Jul 04, 2021 9:12 am at Sun Jul 04, 2021 9:12 am
>
> 
Ankhati wrote: ↑Sun Jul 04, 2021 12:50 am
Custard wrote: ↑Sat Jul 03, 2021 9:03 pm


Interesting, but I confused on the usage. Sockets color seem to imply like this with tangent space conversion first, straight to shader after?


Untitled-1.jpg


The node only calculate a new normal map. I refuse to say "mixing" because this isn't what is happening. A new map is calculated.


If it's not a mixture then it'd be able to do something without plugging in two normal maps.   Mixin g something doesn't preclude a new thing being created, just the opposite.

I like it. It's based on the exact same principle that I read in the re-oriented normal map paper and that my current node is based on, except it's a more elegant implementation of that into Blender nodes with the vector functions. My assessment is that — with most differences being very small — your node is slightly less prone to blow out on flat geometry with extreme examples, slightly more prone (to a lesser degree) to blown out on curvy geometry with extreme examples, and retains a little more sharpness at low combine factors giving a better feeling to the factor use.

Here my little test setup if you care to look, results are the most honest. Best to open with UI setting retained.
https://mega.nz/file/jppwACpY#Yill0WKJw ... QrF1kVoOCY
## Post #415
- Username: DeadmanWasTaken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 01, 2021 3:53 pm
- Post datetime: 2021-07-05T09:48:49+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I've installed the 4K textures DLC for R6, now how do I extract them. When I set the python script to the 16GB .forge file it doesn't extract anything.
## Post #416
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-07-05T13:33:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from DeadmanWasTaken ↑Mon Jul 05, 2021 5:48 pm at Mon Jul 05, 2021 5:48 pm
>
> 
I've installed the 4K textures DLC for R6, now how do I extract them. When I set the python script to the 16GB .forge file it doesn't extract anything.

That's probably because the texture roaming script by default filters out only diffuse textures, and the textures4 forges contain no diffuse textures. The ultra DLC seems to be used just for upgrading the normals and PBRs (sometimes if we're lucky all the way to 2K).

Ubi is really inconsistent with sizes and more or less stopped giving guns 4k textures at a certain point but sometimes do, such as the Tachanka LMG rework, probably because it was such a big gun. Perceived resolution is more relevant than tagline resolutions, i.e. a pistol at 1k could be just as high detail as a LMG at 4k because it's 4 times less surface. Either way you'll get those max size diffuse from a textures3.

Their inconsistency is likely no accident, that sort of thing is a hallmark of doing a stepping down process after texturing with size and compression iterations to find the perceptual breaking point of fine details. As mentioned before that can vary quite widely per model, even just on how much heavy lifting the normal map has been given or the UVs being done well. As they grew more concerned with game size limits they've lower the bar on what they  considered a good maximum and so we see less 4k.

Or else maybe you are using the dump asset script and didn't generate a cache yet. 
[viewtopic.php?f=16&t=15031&start=195#p170313](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=195#p170313)
## Post #417
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-05T14:54:40+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Mon Jul 05, 2021 9:33 pm at Mon Jul 05, 2021 9:33 pm
>
> 
stopped giving guns 4k textures at a certain point
Y5S3 definitely had 4k diffuse textures for guns (and pretty much almost all diffuse textures were 'double' the resolution in width and height [so essentially 4 times bigger])
they got rid of those diffuse textures with either the release of aruni (Y5S4) or what is much more likely, Y6S1

so DeadmanWasTaken, if you are looking for 4k diffuse textures then Y5S4 would most likely be it, tho (much) older builds had 4k ones for pbr and normal maps as well
## Post #418
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-05T23:53:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Does someone have a fix when, I type in the UID for smaller models (Guns, Smoke cans, and other utility) into the Dump.py it has an exit code of 0 yet nothing is dumped. Is there something I need to change that I havent seen?
## Post #419
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-07-06T11:41:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Mon Jul 05, 2021 10:54 pm at Mon Jul 05, 2021 10:54 pm
>
> 
Custard wrote: ↑Mon Jul 05, 2021 9:33 pm
stopped giving guns 4k textures at a certain point
Y5S3 definitely had 4k diffuse textures for guns (and pretty much almost all diffuse textures were 'double' the resolution in width and height [so essentially 4 times bigger])
they got rid of those diffuse textures with either the release of aruni (Y5S4) or what is much more likely, Y6S1

so DeadmanWasTaken, if you are looking for 4k diffuse textures then Y5S4 would most likely be it, tho (much) older builds had 4k ones for pbr and normal maps as well

Now thhat you mention it, maybe I've attributing variance unduely to per-asset and not to patch cycles since we've been doing this over quite a few now. I'm certain there's assets that just don't abide by the same sizes as others even back then, but it's a good thought, especially since I do still have Y5S4 sitting in backup if anyone wants forges from it.

> Reply from Kluhez ↑Tue Jul 06, 2021 7:53 am at Tue Jul 06, 2021 7:53 am
>
> 
Does someone have a fix when, I type in the UID for smaller models (Guns, Smoke cans, and other utility) into the Dump.py it has an exit code of 0 yet nothing is dumped. Is there something I need to change that I havent seen?

Doesn't sound familiar, maybe post a UID that's failing for you, runtime log, anything that seems relevant like that.
## Post #420
- Username: DeadmanWasTaken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 01, 2021 3:53 pm
- Post datetime: 2021-07-06T14:43:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Custard ↑Tue Jul 06, 2021 7:41 pm at Tue Jul 06, 2021 7:41 pm
>
> 
floxay wrote: ↑Mon Jul 05, 2021 10:54 pm
Custard wrote: ↑Mon Jul 05, 2021 9:33 pm
stopped giving guns 4k textures at a certain point
Y5S3 definitely had 4k diffuse textures for guns (and pretty much almost all diffuse textures were 'double' the resolution in width and height [so essentially 4 times bigger])
they got rid of those diffuse textures with either the release of aruni (Y5S4) or what is much more likely, Y6S1

so DeadmanWasTaken, if you are looking for 4k diffuse textures then Y5S4 would most likely be it, tho (much) older builds had 4k ones for pbr and normal maps as well


Now thhat you mention it, maybe I've attributing variance unduely to per-asset and not to patch cycles since we've been doing this over quite a few now. I'm certain there's assets that just don't abide by the same sizes as others even back then, but it's a good thought, especially since I do still have Y5S4 sitting in backup if anyone wants forges from it.

If you don't mind uploading them, I'll definitely download them
## Post #421
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-06T15:00:11+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Why not just use [Steam depot downloader](https://github.com/SteamRE/DepotDownloader)?
## Post #422
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-07T05:07:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[/quote]
Doesn't sound familiar, maybe post a UID that's failing for you, runtime log, anything that seems relevant like that.
[/quote]

ill attach screenshots, but everything exits the same within pycharm as it does with any body or head dump, but even the mp5 that Tushkan has added doesnt even dump properly either. Is there something I need to change in the code to search specifically for weapons models instead of bodys/heads?

This is my attempt at dumping the SMG-12
[https://imgur.com/gallery/FF6ygUU](https://imgur.com/gallery/FF6ygUU)
## Post #423
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2021-07-07T06:23:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from DeadmanWasTaken ↑Tue Jul 06, 2021 10:43 pm at Tue Jul 06, 2021 10:43 pm
>
> 
If you don't mind uploading them, I'll definitely download them

Neither my Google drive or Mega allows a 70GB size anyway so that thing floxay linked sound like the one.

> Reply from Kluhez ↑Wed Jul 07, 2021 1:07 pm at Wed Jul 07, 2021 1:07 pm
>
> 
ill attach screenshots, but everything exits the same within pycharm as it does with any body or head dump, but even the mp5 that Tushkan has added doesnt even dump properly either. Is there something I need to change in the code to search specifically for weapons models instead of bodys/heads?

This is my attempt at dumping the SMG-12
https://imgur.com/gallery/FF6ygUU

Looks like you've left the cache generation line in instead of swapping the hash back after running it once, that would cause your issue.
## Post #424
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-07T11:31:01+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Are the some people who share some models with MASK and detail maps?
So far i've seen very few.

> Reply from Custard ↑Wed Jul 07, 2021 2:23 pm at Wed Jul 07, 2021 2:23 pm
>
> 
DeadmanWasTaken wrote: ↑Tue Jul 06, 2021 10:43 pm
If you don't mind uploading them, I'll definitely download them


Neither my Google drive or Mega allows a 70GB size anyway so that thing floxay linked sound like the one.
Kluhez wrote: ↑Wed Jul 07, 2021 1:07 pm
ill attach screenshots, but everything exits the same within pycharm as it does with any body or head dump, but even the mp5 that Tushkan has added doesnt even dump properly either. Is there something I need to change in the code to search specifically for weapons models instead of bodys/heads?

This is my attempt at dumping the SMG-12
https://imgur.com/gallery/FF6ygUU


Looks like you've left the cache generation line in instead of swapping the hash back after running it once, that would cause your issue.
## Post #425
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-07T13:03:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Wed Jul 07, 2021 7:31 pm at Wed Jul 07, 2021 7:31 pm
>
> 
Are the some people who share some models with MASK and detail maps?
So far i've seen very few.

I'm not sure if I understand, MASK maps are mostly used by uniforms and headgears to add additional detail, for guns there is usually just a single detail normal for the whole material (the base metal det one which looks terrible imo lol)
## Post #426
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-07-08T02:09:44+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Do you think we could also extract audio files (i know a little off topic but still)
## Post #427
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-07-08T02:15:20+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Thu Mar 04, 2021 1:40 am at Thu Mar 04, 2021 1:40 am
>
> 
darthme yes, I'll be glad if you help me setting up a github repo. I have some experience with git itself, but never tried to publish any repos. You can ping me in discord (Ulibos#3846) so we can make it in realtime.

yyred123 no, not yet. I'm reversing the file in an inefficent way. To do it well I have to dig up the actual game code and reverse that one to retrieve all the structures. For that I have to find a way to break in the middle of a serializer execution and dig my way up the stack. The fact that code is vm protected complicates things. If someone could help me with that, things would go faster. But I haven't found anyone ho has knowledge and time to guide me through an optimal workflow (although there are people who gave valuable hints). Until I get my hands on actual serializer, I doubt maps data will be available.

Custard, sorry for not dropping shaders dump, can't find time, but I do remember about it. And yes, LODs are embedded in same mesh file. It has 1 array of verts and 3 to 5 poly arrays that all point to those verts. Each such poly array is a LOD. This way they don't have to save exclusive set of verts along with UVs and skin weights per LOD.

I know its been months (sorry), lemme know If there is aldready one, but I made a github repository. If anyone has found any bugs or wants to improve the code that was originally on dropbox please Pull Requst
[https://github.com/darthnithin/R6-Unpacker](https://github.com/darthnithin/R6-Unpacker)
## Post #428
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-08T04:50:14+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Those detail maps really adds a lot when rendering in Blender and using a good node for nesting the normal maps.

> Reply from floxay ↑Wed Jul 07, 2021 9:03 pm at Wed Jul 07, 2021 9:03 pm
>
> 
Ankhati wrote: ↑Wed Jul 07, 2021 7:31 pm
Are the some people who share some models with MASK and detail maps?
So far i've seen very few.


I'm not sure if I understand, MASK maps are mostly used by uniforms and headgears to add additional detail, for guns there is usually just a single detail normal for the whole material (the base metal det one which looks terrible imo lol)
## Post #429
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-08T05:05:06+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Thu Jul 08, 2021 12:50 pm at Thu Jul 08, 2021 12:50 pm
>
> 
Those detail maps really adds a lot when rendering in Blender and using a good node for nesting the normal maps.

yeah, those looks great on uniforms and headgears but the weapons tend to use only one (or none) for metal which looks terrible imo
## Post #430
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-08T06:41:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

My next challenge is to create a node in DAZ3D that will handle the masked normal maps. I am quite proficient with blender nodes, but the Nvidia MDL are something very different.


> Reply from floxay ↑Thu Jul 08, 2021 1:05 pm at Thu Jul 08, 2021 1:05 pm
>
> 
Ankhati wrote: ↑Thu Jul 08, 2021 12:50 pm
Those detail maps really adds a lot when rendering in Blender and using a good node for nesting the normal maps.


yeah, those looks great on uniforms and headgears but the weapons tend to use only one (or none) for metal which looks terrible imo
## Post #431
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-08T07:52:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

In the XNAlara import script I found this rather simple normal map mixer. How does it compare?

That one I can port to DAZ3D quite easily.

> Reply from Custard ↑Wed Jul 07, 2021 2:23 pm at Wed Jul 07, 2021 2:23 pm
>
> 
DeadmanWasTaken wrote: ↑Tue Jul 06, 2021 10:43 pm
If you don't mind uploading them, I'll definitely download them


Neither my Google drive or Mega allows a 70GB size anyway so that thing floxay linked sound like the one.
Kluhez wrote: ↑Wed Jul 07, 2021 1:07 pm
ill attach screenshots, but everything exits the same within pycharm as it does with any body or head dump, but even the mp5 that Tushkan has added doesnt even dump properly either. Is there something I need to change in the code to search specifically for weapons models instead of bodys/heads?

This is my attempt at dumping the SMG-12
https://imgur.com/gallery/FF6ygUU


Looks like you've left the cache generation line in instead of swapping the hash back after running it once, that would cause your issue.
[normal mix.PNG](https://xentaxbackup.github.io/file/20432_normal mix.PNG)
## Post #432
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-07-08T09:35:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from darthme ↑Thu Jul 08, 2021 10:15 am at Thu Jul 08, 2021 10:15 am
>
> 
I know its been months (sorry), lemme know If there is aldready one, but I made a github repository. If anyone has found any bugs or wants to improve the code that was originally on dropbox please Pull Requst
https://github.com/darthnithin/R6-Unpacker

Lol, I just made my own repo a month ago ))). It's ok though, I only made it local and didn't yet publish it so I will use yours as the "official" one. I also made some fixes in mesh parsing code and moved stuff here and there. So I will push my patches to your repo later on (I'm hoping to fix normals based on floxray's recent hint).
## Post #433
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-08T17:09:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Has anyone had an issue with missing/transparent albeto textures. Ive hit this issue with a few models currently Cav Elite Head. the preview is pure black instead of the human colored skin.
## Post #434
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-07-08T17:44:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Which preview? Windows preview? If sow than it's most likely because of black alpha channel (it is used for things other than transparency in game because heads are not transparent). RGB channels still contain data you expect.
## Post #435
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-08T17:57:02+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Fri Jul 09, 2021 1:09 am at Fri Jul 09, 2021 1:09 am
>
> 
Has anyone had an issue with missing/transparent albeto textures. Ive hit this issue with a few models currently Cav Elite Head. the preview is pure black instead of the human colored skin.

As tushkan said that's a correct texture, in blender make sure to set those to 'channel packed'
## Post #436
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-08T18:58:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Tushkan ↑Fri Jul 09, 2021 1:44 am at Fri Jul 09, 2021 1:44 am
>
> 
Which preview? Windows preview? If sow than it's most likely because of black alpha channel (it is used for things other than transparency in game because heads are not transparent). RGB channels still contain data you expect.

Thats what i was thinking but im also confused on the nodes to use to unpack the channels or if I should do this in a photo editor then put them back into blender?

Edit- Here are the textures I have - [https://imgur.com/gallery/2pFppgf](https://imgur.com/gallery/2pFppgf)
## Post #437
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-08T23:28:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Fri Jul 09, 2021 2:58 am at Fri Jul 09, 2021 2:58 am
>
> 
Thats what i was thinking but im also confused on the nodes to use to unpack the channels or if I should do this in a photo editor then put them back into blender?

Edit- Here are the textures I have - https://imgur.com/gallery/2pFppgf

from here you can just plug R, G, B and A accordingly, for heads A (alpha) is usually subsurface mask, also depending on the types of texture you'd need to set color space to non-color from sRGB
## Post #438
- Username: sebasz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 13, 2021 2:13 am
- Post datetime: 2021-07-12T18:15:10+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hey, is there a way to dump a single prop without dumping thousands of other assets?
## Post #439
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2021-07-12T18:20:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from sebasz ↑Tue Jul 13, 2021 2:15 am at Tue Jul 13, 2021 2:15 am
>
> 
Hey, is there a way to dump a single prop without dumping thousands of other assets?

If you know the UID of the prop Yes. if not then you gotta dump and start looking. there should be a list of characters/weapons id list somewhere in this thread its not finished tho
## Post #440
- Username: sebasz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 13, 2021 2:13 am
- Post datetime: 2021-07-12T18:46:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I got the uid of a texture from a map prop but when I dump it, it extracts thousands of other props.
## Post #441
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-14T18:08:54+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Id assume since its a map prop that texture has a dependence on all the other props within that map. What item are you dumping?
## Post #442
- Username: PeteBroccoli
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 27, 2020 6:15 am
- Post datetime: 2021-07-15T02:17:36+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Apologies if this is the incorrect place to ask but, does anyone know if animations are also going to be able to be/are already extracted?
## Post #443
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-15T03:30:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from PeteBroccoli ↑Thu Jul 15, 2021 10:17 am at Thu Jul 15, 2021 10:17 am
>
> 
Apologies if this is the incorrect place to ask but, does anyone know if animations are also going to be able to be/are already extracted?

Highly unlikely, we can't even extract the rigs the game uses for currently
## Post #444
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-17T06:48:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Greetings all. 
Have some Shared the Kali elite model with all the textures? including the microbumps and mask texture?
Thank you.
## Post #445
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-17T07:03:33+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Sat Jul 17, 2021 2:48 pm at Sat Jul 17, 2021 2:48 pm
>
> 
Greetings all. 
Have some Shared the Kali elite model with all the textures? including the microbumps and mask texture?
Thank you.

Feel free to dump the assets yourself, you can find the UIDs you need in this post: [#p175978](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=390#p175978)
## Post #446
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-17T12:08:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I have the steam version. I hope someone can answer my noob questions when I start.

one thing I wondered. on p3dm there is model named "Hibana (Decontamination)", I cant find this model in the game client?
All the skins seems to be the same mesh with a re color texture.

And this is python.
Just installing python is:
a 20 minutes pointles youtube tutorial
2 bottles of prozac.
5 calls to the suicide hotline.


> Reply from floxay ↑Sat Jul 17, 2021 3:03 pm at Sat Jul 17, 2021 3:03 pm
>
> 
Ankhati wrote: ↑Sat Jul 17, 2021 2:48 pm
Greetings all. 
Have some Shared the Kali elite model with all the textures? including the microbumps and mask texture?
Thank you.


Feel free to dump the assets yourself, you can find the UIDs you need in this post: #p175978
## Post #447
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-17T13:36:26+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Sat Jul 17, 2021 8:08 pm at Sat Jul 17, 2021 8:08 pm
>
> 
I have the steam version. I hope someone can answer my noob questions when I start.

one thing I wondered. on p3dm there is model named "Hibana (Decontamination)", I cant find this model in the game client?
All the skins seems to be the same mesh with a re color texture.
floxay wrote: ↑Sat Jul 17, 2021 3:03 pm
Ankhati wrote: ↑Sat Jul 17, 2021 2:48 pm
Greetings all. 
Have some Shared the Kali elite model with all the textures? including the microbumps and mask texture?
Thank you.


Feel free to dump the assets yourself, you can find the UIDs you need in this post: #p175978

Ubisoft recently rereleased the old outbreak event packs for a limited time. These skins likely use they same body template as the Default, which have been transcribed somewhere in this forum, making it easy to dump all textures/recolorations related to the default body mesh. Dekiroz probably already had theses if he had dumped Hibana's UID near to when the event released. 
I have like 15+ different textures from a single UID dump, which tells me its the default skin of that operator. 
I also use [https://www.r6loot.com/uniforms](https://www.r6loot.com/uniforms) to identify skins and headgears I want to pull, as almost all operators have something unique about them.
## Post #448
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-17T15:01:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Sat Jul 17, 2021 8:08 pm at Sat Jul 17, 2021 8:08 pm
>
> 
And this is python.
Just installing python is:
a 20 minutes pointles youtube tutorial
2 bottles of prozac.
5 calls to the suicide hotline.

it certainly doesn't take 20 minutes to install python, the installer even has a nice GUI you can just click 'next' on almost all pages, sharing game assets on this forum is prohibited.

> Reply from Tushkan
>
> 
.
sorry random quote so you (hopefully) get a notif
a few UV maps seem to be incorrect in places, noticed it on a submesh of Thunderbird and Thermite so far

Thermite:
Blender:



In game:


Any idea what could cause this?
## Post #449
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-17T15:10:43+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[https://www.youtube.com/watch?v=28eLP22SMTA](https://www.youtube.com/watch?v=28eLP22SMTA)
Me: watching how to install python
Python Programmer: let's play the ukulele

This guy literally starts to play the ukulele!!!

Python is a mess. you need to rumage around in the hidden AppData folder.

I installed Zstandard
C:\my_packages\scripts>pip install zstandard
Requirement already satisfied:

I did this siege.pth file and had it point to a folder with R6S, that didn't work so had to dump R6S in the `site-packages` directory

But still.
 import zstandard as zstd
ModuleNotFoundError: No module named 'zstandard'


> Reply from floxay ↑Sat Jul 17, 2021 11:01 pm at Sat Jul 17, 2021 11:01 pm
>
> 
Ankhati wrote: ↑Sat Jul 17, 2021 8:08 pm
And this is python.
Just installing python is:
a 20 minutes pointles youtube tutorial
2 bottles of prozac.
5 calls to the suicide hotline.


it certainly doesn't take 20 minutes to install python, the installer even has a nice GUI you can just click 'next' on almost all pages, sharing game assets on this forum is prohibited.
Tushkan wrote:
.

sorry random quote so you (hopefully) get a notif
a few UV maps seem to be incorrect in places, noticed it on a submesh of Thunderbird and Thermite so far

Thermite:
Blender:



In game:


Any idea what could cause this?
## Post #450
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-18T12:34:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I finally got this to work.

so I enter UID 42145285013

And get what I believe to be all of Blitz heads. Is that a correct assumption? and from there I can add that to my list of known UID's?
## Post #451
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-18T23:39:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Sun Jul 18, 2021 8:34 pm at Sun Jul 18, 2021 8:34 pm
>
> 
I finally got this to work.

so I enter UID 42145285013

And get what I believe to be all of Blitz heads. Is that a correct assumption? and from there I can add that to my list of known UID's?

Yeah if thats the base blitz head itll dump every skin associated with it. I dont see a concrete location aside from Custard's list but thats not editable. Maybe once you have a bunch try dumping a list?
## Post #452
- Username: sebasz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 13, 2021 2:13 am
- Post datetime: 2021-07-19T00:34:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

A discord would be great
## Post #453
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2021-07-19T00:50:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from sebasz ↑Mon Jul 19, 2021 8:34 am at Mon Jul 19, 2021 8:34 am
>
> 
A discord would be great

Would be great for keeping track of info and so people could talk with less of a delay.
## Post #454
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-19T16:57:12+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

There are some little tricks I believe.
119250456051 This is the patches on zofia's arms, I assume that dumping that will get me all her uniforms.

> Reply from Kluhez ↑Mon Jul 19, 2021 7:39 am at Mon Jul 19, 2021 7:39 am
>
> 
Ankhati wrote: ↑Sun Jul 18, 2021 8:34 pm
I finally got this to work.

so I enter UID 42145285013

And get what I believe to be all of Blitz heads. Is that a correct assumption? and from there I can add that to my list of known UID's?


Yeah if thats the base blitz head itll dump every skin associated with it. I dont see a concrete location aside from Custard's list but thats not editable. Maybe once you have a bunch try dumping a list?
## Post #455
- Username: Kluhez
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jun 24, 2021 9:35 am
- Post datetime: 2021-07-19T17:26:53+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Ankhati ↑Tue Jul 20, 2021 12:57 am at Tue Jul 20, 2021 12:57 am
>
> 
There are some little tricks I believe.
119250456051 This is the patches on zofia's arms, I assume that dumping that will get me all her uniforms.
Kluhez wrote: ↑Mon Jul 19, 2021 7:39 am
Ankhati wrote: ↑Sun Jul 18, 2021 8:34 pm
I finally got this to work.

so I enter UID 42145285013

And get what I believe to be all of Blitz heads. Is that a correct assumption? and from there I can add that to my list of known UID's?


Yeah if thats the base blitz head itll dump every skin associated with it. I dont see a concrete location aside from Custard's list but thats not editable. Maybe once you have a bunch try dumping a list?

But some skins change the hands like her elite i believe.
## Post #456
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-07-20T05:16:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I made a discord server if someone wants to join
[https://discord.gg/SJre7WV2UW](https://discord.gg/SJre7WV2UW)
## Post #457
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-07-20T05:54:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

excellent. I am in.

> Reply from dekiroz ↑Tue Jul 20, 2021 1:16 pm at Tue Jul 20, 2021 1:16 pm
>
> 
I made a discord server if someone wants to join
https://discord.gg/SJre7WV2UW
## Post #458
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-07-28T19:51:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sat Jul 17, 2021 11:01 pm at Sat Jul 17, 2021 11:01 pm
>
> 
sorry random quote so you (hopefully) get a notif
a few UV maps seem to be incorrect in places, noticed it on a submesh of Thunderbird and Thermite so far

Script has a vertices reordering routine plus there is a verification step in blender that removes stray vertices (there are strange verts in some assets, I don't know how and why they got there). Either one of them can cause the issue by breaking the indexing. That's my guess. To debug this issue, IDs of broken elements are needed. And time.
## Post #459
- Username: caveira
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 31, 2021 12:52 pm
- Post datetime: 2021-07-31T04:57:29+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hi, do you know if I can use your methods described in this thread to get this image of caveira from the game? Any pointers on where to start? I'd like to have the image isolated not the composite image with all the gui and background. Not sure if this image is built in-game or some kind of static prefab background. Thanks!
[cavmenu.jpg](https://xentaxbackup.github.io/file/20553_cavmenu.jpg)
## Post #460
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2021-07-31T05:00:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Thought I'd drop this in here, worked on this for a while and made some great progress working out some of the forge container formats, and worked out some ways to inspect containers from the top-down instead of guessing and checking IDs, as well as fix a lot of the format assumptions made by some of the python scripts that turned out to break on some of the other container formats. Most meshes and textures dump, and I did a lot of work sorting out how model and material metadata definitions are stored so it's pretty simple to pick a model and find all the textures that go with it. Got a fair bit of the sound working as well (although there are some new developments in Y6S1/2 that I've yet to sort out).

If you have any improvements or fixes please let me know or submit a PR! Always looking for improvements, but I don't have as much time to spend on it right now.

[https://github.com/parzivail/RainbowForge](https://github.com/parzivail/RainbowForge)
## Post #461
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-07-31T07:17:21+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from caveira ↑Sat Jul 31, 2021 12:57 pm at Sat Jul 31, 2021 12:57 pm
>
> 
Hi, do you know if I can use your methods described in this thread to get this image of caveira from the game? Any pointers on where to start? I'd like to have the image isolated not the composite image with all the gui and background. Not sure if this image is built in-game or some kind of static prefab background. Thanks!

easiest way would be to just use intel GPA
## Post #462
- Username: caveira
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 31, 2021 12:52 pm
- Post datetime: 2021-07-31T15:25:52+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sat Jul 31, 2021 3:17 pm at Sat Jul 31, 2021 3:17 pm
>
> 
caveira wrote: ↑Sat Jul 31, 2021 12:57 pm
Hi, do you know if I can use your methods described in this thread to get this image of caveira from the game? Any pointers on where to start? I'd like to have the image isolated not the composite image with all the gui and background. Not sure if this image is built in-game or some kind of static prefab background. Thanks!


easiest way would be to just use intel GPA
lol, anyone wanna extract this for me along with the whatever other game artifacts are in there for that Cav elite skin/model. DM me. Compen$ation
## Post #463
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-08-03T17:06:49+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from parzivail ↑Sat Jul 31, 2021 1:00 pm at Sat Jul 31, 2021 1:00 pm
>
> 
Thought I'd drop this in here

Finally someone got to clean up my mess ))
## Post #464
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2021-08-04T14:40:47+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from parzivail ↑Sat Jul 31, 2021 1:00 pm at Sat Jul 31, 2021 1:00 pm
>
> 
https://github.com/parzivail/RainbowForge

Just released a new tool in addition to DumpTool called AssetCatalog, it should make browsing forge files for assets (currently just meshes) and cataloging them a lot easier. It saves all of the information you add to meshes (names, categories, etc) to a local database. I've attached a screenshot of AssetCatalog's interface. It's on the releases page of the GitHub.

I have updates coming to DumpTool soon as well that should automatically correlate meshes and textures when they're dumped with 
```
dumpmeshprops
```
 which should eliminate some of the guess and check.



ab4sJDm.png (63 KiB) Viewed 126 times
## Post #465
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-13T08:10:27+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Does Intel GPA work on the ultra HD textures?
## Post #466
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-13T08:13:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Fri Aug 13, 2021 4:10 pm at Fri Aug 13, 2021 4:10 pm
>
> 
Does Intel GPA work on the ultra HD textures?

Yes
## Post #467
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-13T09:55:37+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Fri Aug 13, 2021 4:13 pm at Fri Aug 13, 2021 4:13 pm
>
> 
MaZTeR wrote: ↑Fri Aug 13, 2021 4:10 pm
Does Intel GPA work on the ultra HD textures?


Yes
Excellent
## Post #468
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T17:35:51+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'm not able to get R6 launched with intel GPA, it just closes moments after I launch it. I tried hooking GPA to Ubisoft Connect and after that, launching R6 through the launcher but it still crashes.
## Post #469
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-14T17:38:07+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 1:35 am at Sun Aug 15, 2021 1:35 am
>
> 
I'm not able to get R6 launched with intel GPA, it just closes moments after I launch it. I tried hooking GPA to Ubisoft Connect and after that, launching R6 through the launcher but it still crashes.

that's because battleye started blocking GPA, launch the game with -belaunch launch parameter
## Post #470
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T18:05:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Aug 15, 2021 1:38 am at Sun Aug 15, 2021 1:38 am
>
> 
MaZTeR wrote: ↑Sun Aug 15, 2021 1:35 am
I'm not able to get R6 launched with intel GPA, it just closes moments after I launch it. I tried hooking GPA to Ubisoft Connect and after that, launching R6 through the launcher but it still crashes.


that's because battleye started blocking GPA, launch the game with -belaunch launch parameter
I did add "/belaunch -be" and it still won't launch
## Post #471
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-14T18:09:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

it's only belaunch btw and just enable auto-detect launched applications
## Post #472
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T18:11:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Aug 15, 2021 2:09 am at Sun Aug 15, 2021 2:09 am
>
> 
it's only belaunch btw and just enable auto-detect launched applications

Every site said you gotta add / and - to it. Well, I'll try that.
## Post #473
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T18:12:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ah, that seemed to have worked
## Post #474
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T18:52:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Is there a tutorial for getting the textures of models out of captured frames? I wished it was something like in Ninjaripper

Edit: Ah, I got, but it seems that there's no way to save all the textures at once. Shame.
## Post #475
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-14T19:23:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 2:52 am at Sun Aug 15, 2021 2:52 am
>
> 
Is there a tutorial for getting the textures of models out of captured frames? I wished it was something like in Ninjaripper

Edit: Ah, I got, but it seems that there's no way to save all the textures at once. Shame.

I mean this has its advantages too, you know which material has which textures (specially useful for detail normals)
## Post #476
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T19:47:50+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Also, sadly Ubisoft has removed some old skins from the store so the only way to view them is to find someone in the game who has the skin on, which isn't possible with BattlEye disabled. What a shame. I read some time ago that the extraction tools do not support Ultra HD textures.
## Post #477
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-08-14T20:44:58+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

You can use an unlock all
## Post #478
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-14T21:52:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 3:47 am at Sun Aug 15, 2021 3:47 am
>
> 
I read some time ago that the extraction tools do not support Ultra HD textures.

it does if the magic for it is added, if you use rainbowforge/assetcatalog/dumptool then that has it by default, for tushkan's you have add it yourself once
## Post #479
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T22:20:46+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Aug 15, 2021 5:52 am at Sun Aug 15, 2021 5:52 am
>
> 
MaZTeR wrote: ↑Sun Aug 15, 2021 3:47 am
I read some time ago that the extraction tools do not support Ultra HD textures.


it does if the magic for it is added, if you use rainbowforge/assetcatalog/dumptool then that has it by default, for tushkan's you have add it yourself once
Riight. I just installed R6 for the first time in 1,5 years so I don't have any experience with these tools. Gonna try to set up the new tool posted in the last page.
## Post #480
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T22:35:13+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Do I need Python to run that new tool? I'm really confused
## Post #481
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-14T23:09:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 6:35 am at Sun Aug 15, 2021 6:35 am
>
> 
Do I need Python to run that new tool? I'm really confused

no, it's an executable, read the readme, also if you only want (all) the texture you could use ninjaripper for that
## Post #482
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-14T23:38:48+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Aug 15, 2021 7:09 am at Sun Aug 15, 2021 7:09 am
>
> 
MaZTeR wrote: ↑Sun Aug 15, 2021 6:35 am
Do I need Python to run that new tool? I'm really confused


no, it's an executable, read the readme, also if you only want (all) the texture you could use ninjaripper for that

The newer asset viewer works, but the Dumper exe file only flashes cmd for a moment and closes every time I run it
## Post #483
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-15T09:05:23+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Yes, AssetCatalog works, but DumpTool doesn't, or I'm doing something wrong.
## Post #484
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-15T10:05:41+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 5:05 pm at Sun Aug 15, 2021 5:05 pm
>
> 
Yes, AssetCatalog works, but DumpTool doesn't, or I'm doing something wrong.

you are doing something wrong
## Post #485
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-15T10:49:31+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Ah I finally got it, but too bad the textures export as  dds, since the normal maps turn white when exported with Noesis.
## Post #486
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-15T11:12:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 6:49 pm at Sun Aug 15, 2021 6:49 pm
>
> 
Ah I finally got it, but too bad the textures export as  dds, since the normal maps turn white when exported with Noesis.

just use texconv to batch convert them for now, place the 2 files in the attached zip next to the dds files and run the .bat, it will convert and vertically flip them (so it matches UVs)

EDIT: Seems like I forgot the lowercase flag in it, if you wish to keep the original filenames remove the -l flag from the .bat file.


 convertDDS2PNG.zip
(249.67 KiB) Downloaded 73 times
## Post #487
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-15T11:18:05+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Sun Aug 15, 2021 7:12 pm at Sun Aug 15, 2021 7:12 pm
>
> 
MaZTeR wrote: ↑Sun Aug 15, 2021 6:49 pm
Ah I finally got it, but too bad the textures export as  dds, since the normal maps turn white when exported with Noesis.


just use texconv to batch convert them for now, place the 2 files in the attached zip next to the dds files and run the .bat, it will convert and vertically flip them (so it matches UVs)

convertDDS2PNG.zip

Ah, thank you very much. As a matter of fact, I should link all of these tools to the first page.
## Post #488
- Username: janikovka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 15, 2021 7:00 pm
- Post datetime: 2021-08-15T11:31:55+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

Hello, someone already extracted Bearing 9 SMG - Hibana/Echo (with or without textures)?
## Post #489
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-15T14:16:38+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I've got a few suggestions for the asset cataloger:

A list of recently used forge archives should be visible when pressing the "File" button, with the most recent being on top of the stack and also the cataloger should return you to the same section of the asset list where you last left off. Also, the list should display the numbers of each asset.

Finally, you should be able to set an option to automatically clear out the assets out of the list which give you an error.

And for the 3D viewer, you should be able to set the pivot point of the camera to a custom location.

Any way you could also fix up the  way it seems that the faces are seperated in a lot of places and there's only one material?
## Post #490
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-15T20:32:28+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Sun Aug 15, 2021 10:16 pm at Sun Aug 15, 2021 10:16 pm
>
> 
Any way you could also fix up the way it seems that the faces are separated in a lot of places and there's only one material?

What exactly do you mean by this?
## Post #491
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-15T20:37:04+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

I'll send images soon
## Post #492
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-15T22:01:56+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

[https://www.mediafire.com/view/qvrt1s88 ... 7.png/file](https://www.mediafire.com/view/qvrt1s88yildonu/screenshot_2021-08-16_005837.png/file)
Elements are messed up

[https://www.mediafire.com/view/i5gvyky1 ... 7.png/file](https://www.mediafire.com/view/i5gvyky13vfgzqm/screenshot_2021-08-16_005647.png/file)
One material

I haven't tried Tushkan's tool, but I'm pretty sure it imports the materials properly.
## Post #493
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-15T22:15:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from MaZTeR ↑Mon Aug 16, 2021 6:01 am at Mon Aug 16, 2021 6:01 am
>
> 
https://www.mediafire.com/view/qvrt1s88 ... 7.png/file
Elements are messed up

https://www.mediafire.com/view/i5gvyky1 ... 7.png/file
One material

I haven't tried Tushkan's tool, but I'm pretty sure it imports the materials properly.
all fine here, make sure you split by object when importing the obj (iirc that should be on by default)
## Post #494
- Username: Noxdesu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 16, 2021 1:44 pm
- Post datetime: 2021-08-16T05:49:57+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from Kluhez ↑Thu Jul 01, 2021 7:07 am at Thu Jul 01, 2021 7:07 am
>
> 
This is my first time using Mega so let me know if the link isnt working, but i sorted through 300 or so charms but have yet to texture them, the majority of them being chibis and ranked charms.
<link with game assets has been deleted by moderator>

Hi, can you send me that link via pm?
## Post #495
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-16T07:42:42+00:00
- Post Title: Re: Rainbow Six: Siege Models Thread

> Reply from floxay ↑Mon Aug 16, 2021 6:15 am at Mon Aug 16, 2021 6:15 am
>
> 
MaZTeR wrote: ↑Mon Aug 16, 2021 6:01 am
https://www.mediafire.com/view/qvrt1s88 ... 7.png/file
Elements are messed up

https://www.mediafire.com/view/i5gvyky1 ... 7.png/file
One material

I haven't tried Tushkan's tool, but I'm pretty sure it imports the materials properly.

all fine here, make sure you split by object when importing the obj (iirc that should be on by default)
Bollocks, didn't know this. Does this fix the broken elements as well?
## Post #496
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-16T14:24:41+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Here's an issue with the Valkyrie body:

> 

UID is 42145291264 in datapc64_merged_bnk_000000021_mesh.forge. I can't use the old model from Luxos because it's got a different vertex count (probably because they optimized the models some years ago after he extracted that model) and the smoothing groups seem to be messed up.

Edit: Actually, that's on Ubisoft. The meshes' backside is messed up because you won't see it ever. The model has other vertex issues that's on Ubisoft as well.
## Post #497
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-16T16:55:51+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Mon Aug 16, 2021 10:24 pm at Mon Aug 16, 2021 10:24 pm
>
> 
Edit: Actually, that's on Ubisoft. The meshes' backside is messed up because you won't see it ever. The model has other vertex issues that's on Ubisoft as well.

on that note, there are some meshes where the UVs break a little, I remember Thunderbird had it and Thermite ([#p176471](https://forum.xentax.com/viewtopic.php?f=16&t=15031&start=435#p176471))
## Post #498
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-17T10:51:41+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I added a list of UIDs with the names where each belong to in the first page of ones I found (I've got a bunch of more not included, but it takes so long to go through all of it). If anybody has more, feel free to comment so that I'll add any missing ones.
## Post #499
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-18T12:15:32+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I've categorized now all headgear and body meshes from datapc64_merged_bnk_000000021_mesh.forge.
I ignored maybe 20 or so operator related meshes but I'll probably categorize them at some point. Also, vast majority don't have names attached.

I might've missed or not categorized some on accident, but most should be.

Not sure if I'm going to post the UIDs of them all though.
## Post #500
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-19T16:27:49+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Is there a way to make the dump tool to extract the highest available map for the heads? It extracts the diffuse maps in 1024x2048, but normal and specular maps extract as 512x1024.
## Post #501
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-20T00:08:24+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Fri Aug 20, 2021 12:27 am at Fri Aug 20, 2021 12:27 am
>
> 
Is there a way to make the dump tool to extract the highest available map for the heads? It extracts the diffuse maps in 1024x2048, but normal and specular maps extract as 512x1024.

that's the highest
## Post #502
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-20T06:44:46+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Fri Aug 20, 2021 8:08 am at Fri Aug 20, 2021 8:08 am
>
> 
MaZTeR wrote: ↑Fri Aug 20, 2021 12:27 am
Is there a way to make the dump tool to extract the highest available map for the heads? It extracts the diffuse maps in 1024x2048, but normal and specular maps extract as 512x1024.


that's the highest
Sorry, I meant specular and normal maps extract in 256x512, meanwhile they get ripped in 512x1024
## Post #503
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-20T07:45:03+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Does anyone have a clue what the UID of the Ash Tomb Raider head mesh is?

Edit: I think I found it, but it's pretty broken. The head doesn't fit the lower body and it's rotated to the side.

UID is 222130940722.

Edit 2: Well, to be honest, modifying the default head also works because the seams weren't exactly adjusted in the modified head for the Tomb Raider body.
## Post #504
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-20T09:44:49+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Fri Aug 20, 2021 2:44 pm at Fri Aug 20, 2021 2:44 pm
>
> 
floxay wrote: ↑Fri Aug 20, 2021 8:08 am
MaZTeR wrote: ↑Fri Aug 20, 2021 12:27 am
Is there a way to make the dump tool to extract the highest available map for the heads? It extracts the diffuse maps in 1024x2048, but normal and specular maps extract as 512x1024.


that's the highest

Sorry, I meant specular and normal maps extract in 256x512, meanwhile they get ripped in 512x1024

maybe you generated index.db before installing the uhd dlc?
## Post #505
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-20T18:36:27+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Fri Aug 20, 2021 5:44 pm at Fri Aug 20, 2021 5:44 pm
>
> 
MaZTeR wrote: ↑Fri Aug 20, 2021 2:44 pm
floxay wrote: ↑Fri Aug 20, 2021 8:08 am


that's the highest

Sorry, I meant specular and normal maps extract in 256x512, meanwhile they get ripped in 512x1024


maybe you generated index.db before installing the uhd dlc?
I had ran it before, but I ran it again and seem to be getting now UHD textures.
## Post #506
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-23T16:44:56+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Is there a fix to how the 3D previewer disappears if you leave the software unattended for some time? It's pretty annoying since you gotta restart the whole app and there's really no proper way to track where you were the last time.


Also,does anyone have a clue what the UIDs of the default IQ meshes are?
## Post #507
- Username: dekiroz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 04, 2020 2:17 pm
- Post datetime: 2021-08-23T20:07:55+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Tue Aug 24, 2021 12:44 am at Tue Aug 24, 2021 12:44 am
>
> 
Is there a fix to how the 3D previewer disappears if you leave the software unattended for some time? It's pretty annoying since you gotta restart the whole app and there's really no proper way to track where you were the last time.


Also,does anyone have a clue what the UIDs of the default IQ meshes are?

head: 42145290011 
body: 64744913349
## Post #508
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-23T21:09:18+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from dekiroz ↑Tue Aug 24, 2021 4:07 am at Tue Aug 24, 2021 4:07 am
>
> 
MaZTeR wrote: ↑Tue Aug 24, 2021 12:44 am
Is there a fix to how the 3D previewer disappears if you leave the software unattended for some time? It's pretty annoying since you gotta restart the whole app and there's really no proper way to track where you were the last time.


Also,does anyone have a clue what the UIDs of the default IQ meshes are?


head: 42145290011 
body: 64744913349

Thanks, they were in a pretty strange location
## Post #509
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-25T11:57:34+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Any clue why the default IQ headgear (42145290011) is rotated off 90 degrees?
## Post #510
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-25T12:12:37+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Wed Aug 25, 2021 7:57 pm at Wed Aug 25, 2021 7:57 pm
>
> 
Any clue why the default IQ headgear (42145290011) is rotated off 90 degrees?

because ubisoft, they even have models rotated by like 10 degrees and models moved from their original origin (sometimes just a few centimeters..)
## Post #511
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-25T13:30:27+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Wed Aug 25, 2021 8:12 pm at Wed Aug 25, 2021 8:12 pm
>
> 
MaZTeR wrote: ↑Wed Aug 25, 2021 7:57 pm
Any clue why the default IQ headgear (42145290011) is rotated off 90 degrees?


because ubisoft, they even have models rotated by like 10 degrees and models moved from their original origin (sometimes just a few centimeters..)

Damn :/
## Post #512
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-27T10:33:32+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Is there a way to make the new tool search for textures of a mesh in just a spesific archive? For example, it seems that majority of the textures are in datapc64_ondemand.forge, so there's no need for the tool to search all of the archives in the index list if I know that  the textures are in that forge file.
## Post #513
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-08-27T15:19:27+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Fri Aug 27, 2021 6:33 pm at Fri Aug 27, 2021 6:33 pm
>
> 
Is there a way to make the new tool search for textures of a mesh in just a spesific archive? For example, it seems that majority of the textures are in datapc64_ondemand.forge, so there's no need for the tool to search all of the archives in the index list if I know that  the textures are in that forge file.

_ondemand forges do not store textures or meshes, it only has the links between those, meshes and textures are stored in _texturesX and _mesh forges, you can search for 'meshprops' in a specific forge file
## Post #514
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-27T18:06:25+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Fri Aug 27, 2021 11:19 pm at Fri Aug 27, 2021 11:19 pm
>
> 
MaZTeR wrote: ↑Fri Aug 27, 2021 6:33 pm
Is there a way to make the new tool search for textures of a mesh in just a spesific archive? For example, it seems that majority of the textures are in datapc64_ondemand.forge, so there's no need for the tool to search all of the archives in the index list if I know that  the textures are in that forge file.


_ondemand forges do not store textures or meshes, it only has the links between those, meshes and textures are stored in _texturesX and _mesh forges, you can search for 'meshprops' in a specific forge file

You had actually included findallmeshprops in the tutorial, I missed it.
## Post #515
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-27T18:08:52+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

By the way, is it possible to make the bat command file to basically extract everything in given sub-folders? Say, I have 6 different sub folders with textures from individual uniforms or headgear and I need to convert all of the dds files in all of them at once to png.
## Post #516
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2021-08-27T23:49:20+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hi, I tried the parzivail/RainbowForge tool v1.3.1, but the list commend gives me results that every UID are Unknown. Did anyone encounter this issue?

DumpTool.exe list datapc64_merged_fury_bnk_textures0.forge
16: Unknown
3040: Unknown
14393231457: Unknown
14393258946: Unknown
14393239185: Unknown
14393239205: Unknown
14393231309: Unknown
14393231256: Unknown
14393231449: Unknown
14393231301: Unknown
27735325785: Unknown
14393231293: Unknown
4489859213: Unknown
14393154884: Unknown

DumpTool.exe inspect datapc64_merged_fury_bnk_textures0.forge 4459933919
UID: 4459933919
Offset: 0x263C000
End: 0x26677D7
Size: 0x2B7D7
Name Table:
        File Magic: Unknown
        Timestamp: 1/1/1970 12:00:00 AM (epoch: 0)
Container: Forge Asset
Has Metadata Block: True

The dump commend gives me files like:
id4459933919_filetype4.bin

The content of this file looks: 78 C4 B5 D7 E5 55 05 00 00 00 00 00 DF 30 D5 09
## Post #517
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-28T09:10:37+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from comword ↑Sat Aug 28, 2021 7:49 am at Sat Aug 28, 2021 7:49 am
>
> 
Hi, I tried the parzivail/RainbowForge tool v1.3.1, but the list commend gives me results that every UID are Unknown. Did anyone encounter this issue?

DumpTool.exe list datapc64_merged_fury_bnk_textures0.forge
16: Unknown
3040: Unknown
14393231457: Unknown
14393258946: Unknown
14393239185: Unknown
14393239205: Unknown
14393231309: Unknown
14393231256: Unknown
14393231449: Unknown
14393231301: Unknown
27735325785: Unknown
14393231293: Unknown
4489859213: Unknown
14393154884: Unknown

DumpTool.exe inspect datapc64_merged_fury_bnk_textures0.forge 4459933919
UID: 4459933919
Offset: 0x263C000
End: 0x26677D7
Size: 0x2B7D7
Name Table:
        File Magic: Unknown
        Timestamp: 1/1/1970 12:00:00 AM (epoch: 0)
Container: Forge Asset
Has Metadata Block: True

The dump commend gives me files like:
id4459933919_filetype4.bin

The content of this file looks: 78 C4 B5 D7 E5 55 05 00 00 00 00 00 DF 30 D5 09
Those are not even Rainbow Six: Siege archives or you have some really old version of the game as I can't even find what you mentioned.
## Post #518
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2021-08-28T09:31:52+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sat Aug 28, 2021 5:10 pm at Sat Aug 28, 2021 5:10 pm
>
> 
comword wrote: ↑Sat Aug 28, 2021 7:49 am
Hi, I tried the parzivail/RainbowForge tool v1.3.1, but the list commend gives me results that every UID are Unknown. Did anyone encounter this issue?

DumpTool.exe list datapc64_merged_fury_bnk_textures0.forge
16: Unknown
3040: Unknown
14393231457: Unknown
14393258946: Unknown
14393239185: Unknown
14393239205: Unknown
14393231309: Unknown
14393231256: Unknown
14393231449: Unknown
14393231301: Unknown
27735325785: Unknown
14393231293: Unknown
4489859213: Unknown
14393154884: Unknown

DumpTool.exe inspect datapc64_merged_fury_bnk_textures0.forge 4459933919
UID: 4459933919
Offset: 0x263C000
End: 0x26677D7
Size: 0x2B7D7
Name Table:
        File Magic: Unknown
        Timestamp: 1/1/1970 12:00:00 AM (epoch: 0)
Container: Forge Asset
Has Metadata Block: True

The dump commend gives me files like:
id4459933919_filetype4.bin

The content of this file looks: 78 C4 B5 D7 E5 55 05 00 00 00 00 00 DF 30 D5 09

Those are not even Rainbow Six: Siege archives or you have some really old version of the game as I can't even find what you mentioned.

They are archives from Apr 2018 Operation Chimera. Do you know what has changed from the old versions to the newer ones supported by the RainbowForge tool?
## Post #519
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-28T10:03:00+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from comword ↑Sat Aug 28, 2021 5:31 pm at Sat Aug 28, 2021 5:31 pm
>
> 
MaZTeR wrote: ↑Sat Aug 28, 2021 5:10 pm
comword wrote: ↑Sat Aug 28, 2021 7:49 am
Hi, I tried the parzivail/RainbowForge tool v1.3.1, but the list commend gives me results that every UID are Unknown. Did anyone encounter this issue?

DumpTool.exe list datapc64_merged_fury_bnk_textures0.forge
16: Unknown
3040: Unknown
14393231457: Unknown
14393258946: Unknown
14393239185: Unknown
14393239205: Unknown
14393231309: Unknown
14393231256: Unknown
14393231449: Unknown
14393231301: Unknown
27735325785: Unknown
14393231293: Unknown
4489859213: Unknown
14393154884: Unknown

DumpTool.exe inspect datapc64_merged_fury_bnk_textures0.forge 4459933919
UID: 4459933919
Offset: 0x263C000
End: 0x26677D7
Size: 0x2B7D7
Name Table:
        File Magic: Unknown
        Timestamp: 1/1/1970 12:00:00 AM (epoch: 0)
Container: Forge Asset
Has Metadata Block: True

The dump commend gives me files like:
id4459933919_filetype4.bin

The content of this file looks: 78 C4 B5 D7 E5 55 05 00 00 00 00 00 DF 30 D5 09

Those are not even Rainbow Six: Siege archives or you have some really old version of the game as I can't even find what you mentioned.


They are archives from Apr 2018 Operation Chimera. Do you know what has changed from the old versions to the newer ones supported by the RainbowForge tool?

You need the latest version of the game, anything else will not work with this tool. Ubisoft has changed the code numerous times with the assets in the last almost 6 years.
## Post #520
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2021-08-28T10:11:10+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sat Aug 28, 2021 6:03 pm at Sat Aug 28, 2021 6:03 pm
>
> 
comword wrote: ↑Sat Aug 28, 2021 5:31 pm
MaZTeR wrote: ↑Sat Aug 28, 2021 5:10 pm

Those are not even Rainbow Six: Siege archives or you have some really old version of the game as I can't even find what you mentioned.


They are archives from Apr 2018 Operation Chimera. Do you know what has changed from the old versions to the newer ones supported by the RainbowForge tool?


You need the latest version of the game, anything else will not work with this tool. Ubisoft has changed the code numerous times with the assets in the last almost 6 years.

But the resources I need does not exist in the latest version of the game. I remember that Tushkan once successfully dump resources in this old version, before the Python tools version published.
## Post #521
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-28T10:18:38+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from comword ↑Sat Aug 28, 2021 6:11 pm at Sat Aug 28, 2021 6:11 pm
>
> 
MaZTeR wrote: ↑Sat Aug 28, 2021 6:03 pm
comword wrote: ↑Sat Aug 28, 2021 5:31 pm


They are archives from Apr 2018 Operation Chimera. Do you know what has changed from the old versions to the newer ones supported by the RainbowForge tool?


You need the latest version of the game, anything else will not work with this tool. Ubisoft has changed the code numerous times with the assets in the last almost 6 years.


But the resources I need does not exist in the latest version of the game. I remember that Tushkan once successfully dump resources in this old version, before the Python tools version published.
You mean the unique models from the Outbreak event? You need someone to make a tool for that version of the game, but not sure who's going to work on an old version of the game that's already hard to work with the current versions.
## Post #522
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2021-08-28T10:24:37+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sat Aug 28, 2021 6:18 pm at Sat Aug 28, 2021 6:18 pm
>
> 
comword wrote: ↑Sat Aug 28, 2021 6:11 pm
MaZTeR wrote: ↑Sat Aug 28, 2021 6:03 pm


You need the latest version of the game, anything else will not work with this tool. Ubisoft has changed the code numerous times with the assets in the last almost 6 years.


But the resources I need does not exist in the latest version of the game. I remember that Tushkan once successfully dump resources in this old version, before the Python tools version published.

You mean the unique models from the Outbreak event? You need someone to make a tool for that version of the game, but not sure who's going to work on an old version of the game that's already hard to work with the current versions.

Yes, I want unique models from that event. I would like to work on tools for this version, but I have little experience of reverse engineering. So I need a clue to start, such as file type for 78 C4 B5 D7 E5
## Post #523
- Username: comword
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Nov 22, 2018 5:38 pm
- Post datetime: 2021-08-28T10:52:24+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from Tushkan ↑Thu Feb 06, 2020 3:31 am at Thu Feb 06, 2020 3:31 am
>
> 
comword wrote: ↑Wed Feb 05, 2020 11:09 pm
Some extracted file started with 34 AA FB 57 99 FA 14 10 02 00 03 00 ... Have you seen this pattern before?


Yes. [34 AA FB 57 99 FA 14 10] is a Container_ID. It denotes file It can hold uncompressed data (meta) and compressed (actual file split into compressed chunks). you can see those all over forges. They generally go in groups: one container for uncompressed metadata and emmideatly after that goes another with compressed file. It should go as:
Code: Select alluint64 Container_ID
uint16 = 2 // unknown
uint16 = 3 // unknown
uint8 = 0 // unknown
uint16 varying // unknown
uint32 num_chunks // how many data chunks are in this container
[chunk_size, chunk_size, ...]
[chunk, chunk, ...]
each chunk_size is a struct of:
Code: Select alluint32 uncompressed_size
uint32 compressed_size (actual chunk size that you need to read)
each chunk is:
Code: Select alluint32 hash // at least it looks like some hash
bytes [compressed_size] //actual compressed data

The files that start emmideately with this header, are most likely depgraphbins. Those hold data about links between different entities. When you unzompress and concatenate all chunks (with zstandard), you will get a binary file, that starts with uint8 = 2 and then its a buncho if structs of type:
Code: Select alluint64 parent_uid
uint64 child_uid
uint64 child_type
In newer versions child_type now seems to be split into [int32, uint16, uint8, uint8]

Hi Tushkan, do you remember asset packaging differences between files in this event and files in newer versions?
## Post #524
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-08-28T15:28:17+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

The AssetCataloger could use a sort function for say by a name. For example, having objects cataloged by a spesific operator name will be listed in a row instead of scattered somewhere.

Where are also the catalog names stored? I think I've cataloged at least 90% of the operator related objects, so it'd be nice if I could post the whole list to the first page.
## Post #525
- Username: DudeKiller
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 09, 2021 5:00 pm
- Post datetime: 2021-09-09T09:05:15+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hello, I'm the dev of the site r6call.com

To make this site I use pictures from [https://www.ubisoft.com/en-gb/game/rain ... -info/maps](https://www.ubisoft.com/en-gb/game/rainbow-six/siege/game-info/maps)

The quality of those pictures are really crap compared to to the one you see in-game when you choose a site.

Is it possible to get the images from the game ?
## Post #526
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-09-09T19:06:16+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from DudeKiller ↑Thu Sep 09, 2021 5:05 pm at Thu Sep 09, 2021 5:05 pm
>
> 
Hello, I'm the dev of the site r6call.com

To make this site I use pictures from https://www.ubisoft.com/en-gb/game/rain ... -info/maps

The quality of those pictures are really crap compared to to the one you see in-game when you choose a site.

Is it possible to get the images from the game ?

You can use ninjaripper to get the images.
## Post #527
- Username: DudeKiller
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 09, 2021 5:00 pm
- Post datetime: 2021-09-10T07:36:29+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hello MaZTeR,

Cool, is it complicated to do ?
Do you have a tutorial link to suggest ?
Has it something specific to do for Siege in particular ?
Will BattlEye detect the tool and could I get ban for that ?
## Post #528
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-09-10T07:39:40+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from DudeKiller ↑Fri Sep 10, 2021 3:36 pm at Fri Sep 10, 2021 3:36 pm
>
> 
Cool, is it complicated to do ?
Do you have a tutorial link to suggest ?
Has it something specific to do for Siege in particular ?
Will BattlEye detect the tool and could I get ban for that ?

no
search on yt
no
yes, disable battleye with the belaunch launch parameter
## Post #529
- Username: DudeKiller
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 09, 2021 5:00 pm
- Post datetime: 2021-09-10T08:09:12+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

ok thank you for the info
## Post #530
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-09-10T14:46:29+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Do the newer tools work with the latest version of the game? Also, if I run the indexer, will I lose all of my previously cataloged UIDs?
## Post #531
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-09-13T17:47:24+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Fri Sep 10, 2021 10:46 pm at Fri Sep 10, 2021 10:46 pm
>
> 
Do the newer tools work with the latest version of the game? Also, if I run the indexer, will I lose all of my previously cataloged UIDs?

RainbowForge works with the 2021-09-12 version of R6S.
I unpacked the uploaded models and converted textures (texconv then noesis) and have uploaded them here <link deleted by moderator>
UIDs from this forumn along with a list of models and textures from my upload here [https://docs.google.com/spreadsheets/d/ ... sp=sharing](https://docs.google.com/spreadsheets/d/1Ik0LOTpO5qNIwWUGmqdXBvGCWo0msPsnBV15IoIwBjk/edit?usp=sharing)
## Post #532
- Username: Neku
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 04, 2021 2:46 am
- Post datetime: 2021-10-03T21:51:09+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hi I'm new to this forum, I have already downloaded this tool but I don't know how to run it, anyone having the same problem when it just doesn't open?
## Post #533
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-10-04T15:00:02+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from Neku ↑Mon Oct 04, 2021 5:51 am at Mon Oct 04, 2021 5:51 am
>
> 
Hi I'm new to this forum, I have already downloaded this tool but I don't know how to run it, anyone having the same problem when it just doesn't open?

You need to use CMD to run the tool, it doesn't work like a typical UI extractor
## Post #534
- Username: Tushkan
- Rank: veteran
- Number of posts: 106
- Joined date: Mon Dec 18, 2017 8:47 pm
- Post datetime: 2021-10-06T13:06:05+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from comword ↑Sat Aug 28, 2021 6:52 pm at Sat Aug 28, 2021 6:52 pm
>
> 
Hi Tushkan, do you remember asset packaging differences between files in this event and files in newer versions?

Yes. They changed meta header. Everything else is identical AFAIR. Metadata header needs to be parsed the old way for current parser to be able to parse Chimera files. I do have old code stashed but it wasn't integrated in script because there was no demand for it last I was publishing.
## Post #535
- Username: Toshii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 07, 2021 11:49 pm
- Post datetime: 2021-11-07T15:51:02+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

can someone explain what all is needed to data mine siege? i want to start leaking stuff to my friends
## Post #536
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2021-11-20T10:21:29+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Is there a possibility to find/extract filenames in forge?
## Post #537
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2021-11-21T02:24:41+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from John76 ↑Sat Nov 20, 2021 6:21 pm at Sat Nov 20, 2021 6:21 pm
>
> 
Is there a possibility to find/extract filenames in forge?

That's an implemented feature in Prism, which is a project within RainbowForge. The git (currently) doesn't have any of the binaries but you can build it from source.
## Post #538
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2021-11-21T03:37:55+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I tried but it always returns an empty string ... 
Wouldn't he find at least one name in the archive?
I use DecodeName func
[https://github.com/parzivail/RainbowFor ... ncoding.cs](https://github.com/parzivail/RainbowForge/blob/master/RainbowForge/Core/NameEncoding.cs)

Or I'm doing something wrong!



Untitled.jpg (209.67 KiB) Viewed 94 times
## Post #539
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2021-11-21T18:24:51+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from John76 ↑Sun Nov 21, 2021 11:37 am at Sun Nov 21, 2021 11:37 am
>
> 
I tried but it always returns an empty string ... 
Wouldn't he find at least one name in the archive?
I use DecodeName func
https://github.com/parzivail/RainbowFor ... ncoding.cs

Or I'm doing something wrong!

Untitled.jpg

It only works on roughly-Chimera or newer forges. Which version of Siege are you trying to browse?
## Post #540
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2021-11-21T19:01:00+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Tom Clancy's Rainbow Six - Siege 
Forge Version 29
## Post #541
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2021-11-21T19:14:37+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from John76 ↑Mon Nov 22, 2021 3:01 am at Mon Nov 22, 2021 3:01 am
>
> 
Tom Clancy's Rainbow Six - Siege 
Forge Version 29

Buy the game
## Post #542
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2021-11-21T19:20:57+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from John76 ↑Mon Nov 22, 2021 3:01 am at Mon Nov 22, 2021 3:01 am
>
> 
Tom Clancy's Rainbow Six - Siege 
Forge Version 29

Ah, filename decoding currently only works on Forge versions 30 and above. I assume the data is still there for 29 and below but the format is different and I haven't checked how it's encoded on any older version.
## Post #543
- Username: MisterOwlMaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 03, 2021 1:07 pm
- Post datetime: 2021-12-03T05:11:39+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Whenever I extract meshes using RainbowForge, the uvs result being broken. How do I fix it?
## Post #544
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-01-25T00:46:16+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Why am I getting this after running dumpmeshprops?

```
File name: 'H:\Ubisoft Game Launcher\Tom Clancy's Rainbow Six Siege\datapc64_merged_bnk_000000020_soundmedia.forge'
   at System.IO.FileStream.ValidateFileHandle(SafeFileHandle fileHandle)
   at System.IO.FileStream.CreateFileOpenHandle(FileMode mode, FileShare share, FileOptions options)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options)
   at DumpTool.DumpMeshPropsCommand.ProcessFlatArchive(ILiteDatabase db, Forge forge, Entry entry, String rootOutputDir, String rootForgeDir) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\DumpMeshPropsCommand.cs:line 101
   at DumpTool.DumpMeshPropsCommand.Run(DumpMeshPropsCommand args) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\DumpMeshPropsCommand.cs:line 38
```


It didn't happen months ago when I was extracting models.

I ran the index command again and let it run all the way through. When I try the older one from months ago, I get a similar error message, but this time it's

```
File name: 'H:\Ubisoft Game Launcher\Tom Clancy's Rainbow Six Siege\datapc64_merged_events_bnk_015722044_textures0.forge'
   at System.IO.FileStream.ValidateFileHandle(SafeFileHandle fileHandle)
   at System.IO.FileStream.CreateFileOpenHandle(FileMode mode, FileShare share, FileOptions options)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options)
   at DumpTool.DumpMeshPropsCommand.ProcessFlatArchive(ILiteDatabase db, Forge forge, Entry entry, String rootOutputDir, String rootForgeDir) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\DumpMeshPropsCommand.cs:line 101
   at DumpTool.DumpMeshPropsCommand.Run(DumpMeshPropsCommand args) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\DumpMeshPropsCommand.cs:line 38
```


but it does dump one texture and also the model (though it should extract everything related). The new index file doesn't dump anything.
## Post #545
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2022-01-25T01:10:37+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Tue Jan 25, 2022 8:46 am at Tue Jan 25, 2022 8:46 am
>
> 
Why am I getting this after running dumpmeshprops?

try deleting the db file and re-indexing
## Post #546
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-01-25T01:17:28+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Tue Jan 25, 2022 9:10 am at Tue Jan 25, 2022 9:10 am
>
> 
MaZTeR wrote: ↑Tue Jan 25, 2022 8:46 am
Why am I getting this after running dumpmeshprops?


try deleting the db file and re-indexing

But it's happening with the older index file too I was running this tool the last time I posted comments here as well and I haven't touched the tool in any way since then. I've only updated the game today.
## Post #547
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2022-01-25T01:19:58+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Tue Jan 25, 2022 9:17 am at Tue Jan 25, 2022 9:17 am
>
> 
But it's happening with the older index file too I was running this tool the last time I posted comments here as well and I haven't touched the tool in any way since then. I've only updated the game today.

The old db obviously will not work as forges get modified with game patches and the database still holds links to now non-existing forges, hence the FileNotFoundException error.

Does the new db work?
## Post #548
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-01-25T09:42:26+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

New one doesn't work at all. The old one at least gives me something. Should I just reinstall the whole dump tool?
## Post #549
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-03-25T19:48:29+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Anyone have a clue what the alpha map in the diffuse textures with operators' faces is supposed to represent?
## Post #550
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2022-03-26T20:45:30+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sat Mar 26, 2022 3:48 am at Sat Mar 26, 2022 3:48 am
>
> 
Anyone have a clue what the alpha map in the diffuse textures with operators' faces is supposed to represent?

Translucency maybe (they added new things), can you post it here ?!
## Post #551
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2022-03-26T21:07:21+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Diffuse map alpha depends on what kind of material its being used on. Faces im pretty sure is SSS as for guns and such i have no clue.
## Post #552
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-03-27T20:05:40+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

This is the alpha map on the diffuse map for Valkyrie


and this is the alpha map on the 4k detail normal map when you have the Ultra HD pack installed
## Post #553
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2022-03-28T11:01:41+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from YourlordAdam ↑Sun Mar 27, 2022 5:07 am at Sun Mar 27, 2022 5:07 am
>
> 
Diffuse map alpha depends on what kind of material its being used on. Faces im pretty sure is SSS as for guns and such i have no clue.

For guns it's most likely the mask for universal weapon skins (tiling ones)
## Post #554
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2022-03-28T22:34:58+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Mon Mar 28, 2022 4:05 am at Mon Mar 28, 2022 4:05 am
>
> 
This is the alpha map on the diffuse map for Valkyrie


and this is the alpha map on the 4k detail normal map when you have the Ultra HD pack installed

The first map inverted gives you Translucency and the second one is for face cavity.
## Post #555
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-02T16:20:51+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from W0lfy ↑Tue Mar 29, 2022 6:34 am at Tue Mar 29, 2022 6:34 am
>
> 
MaZTeR wrote: ↑Mon Mar 28, 2022 4:05 am
This is the alpha map on the diffuse map for Valkyrie


and this is the alpha map on the 4k detail normal map when you have the Ultra HD pack installed


The first map inverted gives you Translucency and the second one is for face cavity.
Ah thanks
## Post #556
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2022-04-02T19:54:17+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

For the cavity map, it looks like you took it from a Normal map channel or "Detail Normal map" like this one here...you can use the main 
• Normal map + Detail normal map for more details + "B" or "Alpha" channel as Cavity (black and white) (my method)
## Post #557
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-09T14:22:40+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Is possible to extract textures with the ultra HD pack? I'm looking for the Ash Rodeo Dahlia textures and the specular and normal maps export in 512x512, though in the game with the pack they're 1024x1024. And as far as I'm aware, the headgear isn't viewable in the game anymore and it's just in the game files so I can't use Ninja Ripper to get them (as far as I know, I'm not 100% sure).

By the way, does anyone have an old version of the game dating back to from release to late 2016? I need the Ash hair specular texture from the old model before they changed it in Chimera in 2017. The model is available publicly, but it's missing the specular map and I'd like to know if it even existed. I could probably make one from the diffuse map, but it's probably not as great as the original thing if it was a thing.
## Post #558
- Username: YourlordAdam
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 15, 2019 7:22 am
- Post datetime: 2022-04-09T16:12:24+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sat Apr 09, 2022 10:22 pm at Sat Apr 09, 2022 10:22 pm
>
> 
Is possible to extract textures with the ultra HD pack? I'm looking for the Ash Rodeo Dahlia textures and the specular and normal maps export in 512x512, though in the game with the pack they're 1024x1024. And as far as I'm aware, the headgear isn't viewable in the game anymore and it's just in the game files so I can't use Ninja Ripper to get them (as far as I know, I'm not 100% sure).

By the way, does anyone have an old version of the game dating back to from release to late 2016? I need the Ash hair specular texture from the old model before they changed it in Chimera in 2017. The model is available publicly, but it's missing the specular map and I'd like to know if it even existed. I could probably make one from the diffuse map, but it's probably not as great as the original thing if it was a thing.

The Ultra HD pack textures are in datapc64_mtx_bnk_textures4.

as for the old version you can download them with the Steam Depot Downerloader over on github, use steamdb.info to get the Appid/Depotid/ManifestID
## Post #559
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-09T16:29:09+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from YourlordAdam ↑Sun Apr 10, 2022 12:12 am at Sun Apr 10, 2022 12:12 am
>
> 
MaZTeR wrote: ↑Sat Apr 09, 2022 10:22 pm
Is possible to extract textures with the ultra HD pack? I'm looking for the Ash Rodeo Dahlia textures and the specular and normal maps export in 512x512, though in the game with the pack they're 1024x1024. And as far as I'm aware, the headgear isn't viewable in the game anymore and it's just in the game files so I can't use Ninja Ripper to get them (as far as I know, I'm not 100% sure).

By the way, does anyone have an old version of the game dating back to from release to late 2016? I need the Ash hair specular texture from the old model before they changed it in Chimera in 2017. The model is available publicly, but it's missing the specular map and I'd like to know if it even existed. I could probably make one from the diffuse map, but it's probably not as great as the original thing if it was a thing.


The Ultra HD pack textures are in datapc64_mtx_bnk_textures4.

as for the old version you can download them with the Steam Depot Downerloader over on github, use steamdb.info to get the Appid/Depotid/ManifestID

Ah thanks. And I don't have the Steam version, that's the thing
## Post #560
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2022-04-09T16:42:14+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sat Apr 09, 2022 10:22 pm at Sat Apr 09, 2022 10:22 pm
>
> 
Is possible to extract textures with the ultra HD pack? And as far as I'm aware, the headgear isn't viewable in the game anymore

Yes. If you generated the .db file with the textures4 forges (UHD DLC files) present dumpmeshprops command should definitely work.

> Reply from MaZTeR ↑Sat Apr 09, 2022 10:22 pm at Sat Apr 09, 2022 10:22 pm
>
> 
as far as I'm aware, the headgear isn't viewable in the game anymore

If you own it you can see it, so either get it or make the game think you have it
## Post #561
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-09T16:47:39+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Sun Apr 10, 2022 12:42 am at Sun Apr 10, 2022 12:42 am
>
> 
MaZTeR wrote: ↑Sat Apr 09, 2022 10:22 pm
Is possible to extract textures with the ultra HD pack? And as far as I'm aware, the headgear isn't viewable in the game anymore


Yes. If you generated the .db file with the textures4 forges (UHD DLC files) present dumpmeshprops command should definitely work.
MaZTeR wrote: ↑Sat Apr 09, 2022 10:22 pm
as far as I'm aware, the headgear isn't viewable in the game anymore


If you own it you can see it, so either get it or make the game think you have it

No I don't own it, but sometimes they're in the bundles tab or whatever it is. But unfortunately Ubisoft often removes unique cosmetics completely to be viewed from the menu, even if they're technically in the game. Not sure why can't they just allow people to get any cosmetic item instead of tying them to some stupid event that happened 10 years ago.
## Post #562
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-09T18:22:24+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

For some  reason it's unable to find the corresponding texture UID for the Rodeo Dahlia mesh from the UHD pack.

The object UID is 194403862641

It does find the standard textures from the ondemand archive.

Edit: Oh nvm, I ran the standard export process and it seemed to find the UHD files automatically without me referencing the UHD pack at all. That's good to know.

So, if anyone is interested in the UHD files, just install the UHD pack normally and then export the models the usual way.
## Post #563
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-10T15:21:54+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

For some reason AssetCatalog keeps crashing after I copy and paste UIDs a certain amount
## Post #564
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2022-04-10T15:23:52+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from MaZTeR ↑Sun Apr 10, 2022 11:21 pm at Sun Apr 10, 2022 11:21 pm
>
> 
AssetCatalog

Use Prism.
## Post #565
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-17T19:55:50+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Are the models' normal maps' green channels automatically inverted? I noticed some of my models I've extracted from other games have the green channels looking up (DirectX) when they should be looking down (for OpenGL/Blender) and was curious if it's a problem with the models extracted with Ninjaripper and these tools. I honestly can't tell with some of these textures what is the correct way up (for example, with clothing that have creases everywhere), so is there like a fool proof method of showing which side is correct for the software you're using? I just want to avoid inverting textures that already are correct.

Also, it's easy to know what's the correct looking texture when you export them yourself out of the game, but often times you end up getting them from the internet and it's hard to tell if people have modified the textures.
## Post #566
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-17T20:09:58+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

For example, how do you tell that the 4k detail normal map of the characters' faces has a correct green channel? I know it's broken because I extracted it from the game so it uses the DirectX method, but if I didn't know this, how honestly can you tell that it needs to be inverted? I can't tell just by looking at it because the white spots give lighting everywhere so it's pretty hard to tell the correct direction of lighting. Using actual lighting on the 3D model doesn't really help either because to me it doesn't look that bad when the green channel is inverted, so you can imagine this with some completely arbitrary clothing object that has many creases and all kinds of detail.

Edit: Actually, the mouth object's normal map is a better example
## Post #567
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-26T12:05:30+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I'm having a new problem with extracting textures, for some reason when I'm dumping everything of a UID, it'll simply dump the model into a single folder and nothing else. It became like this after I updated the game and ran the index.

Here's what it says at the end.

Error while dumping: System.InvalidOperationException: Sequence contains no matching element
   at System.Linq.ThrowHelper.ThrowNoMatchException()
   at DumpTool.DumpMeshPropsCommand.ProcessFlatArchive(ILiteDatabase db, Forge forge, Entry entry, String rootOutputDir, String rootForgeDir) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\DumpMeshPropsCommand.cs:line 109
   at DumpTool.DumpMeshPropsCommand.Run(DumpMeshPropsCommand args) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\DumpMeshPropsCommand.cs:line 38

Edit: Yep, it now says the same with files that I already extracted before just fine.

Edit 2: I resolved this by doing the indexing again.
## Post #568
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-05-09T18:49:54+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I'm having trouble again. For some reason DumpTool is unable to find the Metadata containers for some gadgets, for example both the Twitch drone variants. I've ran the findallmeshpropsglobal function multiple times and it can't find anything for the object UIDs (which are 22439849214 and 42812368857). Same thing with the camera from Valkyrie's Elite skin and the bow and arrow from Hibana's Elite skin. I recently reinstalled the game completely so there can't be any missing files and also ran index couple of times the same day.
## Post #569
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2022-05-15T11:25:56+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Trying to index the forge files using the latest version of the game I just downloaded off steam, but the tool keeps giving me this error. If anyone has any idea what the problem is I' would love to know.

Cheers 



C:\Program Files (x86)\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege>DumpTool.exe index "C:\Program Files (x86)\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege"
Unhandled exception. System.ArgumentNullException: Value cannot be null. (Parameter 'connectionString')
   at LiteDB.ConnectionString..ctor(String connectionString)
   at DumpTool.IndexCommand.Run(IndexCommand args) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\IndexCommand.cs:line 39
   at CommandLine.ParserResultExtensions.WithParsed[T](ParserResult`1 result, Action`1 action)
   at DumpTool.Program.Main(String[] args) in C:\Users\Admin\RiderProjects\RainbowForge\DumpTool\Program.cs:line 9
## Post #570
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2022-05-15T13:19:25+00:00
- Post Title: Re: 2021- Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from gep55 ↑Sun May 15, 2022 7:25 pm at Sun May 15, 2022 7:25 pm
>
> 
Trying to index the forge files using the latest version of the game I just downloaded off steam, but the tool keeps giving me this error. If anyone has any idea what the problem is I' would love to know.

Correct usage for the index command is described here: [https://github.com/parzivail/RainbowForge#index](https://github.com/parzivail/RainbowForge#index)
Usage: DumpTool.exe index <directory of forge files> <output index filename>
Example: DumpTool.exe index "X:\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege" "index.db"
You forgot to give a path/name for the database file.

> Reply from MaZTeR ↑Tue May 10, 2022 2:49 am at Tue May 10, 2022 2:49 am
>
> 
I'm having trouble again. For some reason DumpTool is unable to find the Metadata containers for some gadgets, for example both the Twitch drone variants. I've ran the findallmeshpropsglobal function multiple times and it can't find anything for the object UIDs (which are 22439849214 and 42812368857). Same thing with the camera from Valkyrie's Elite skin and the bow and arrow from Hibana's Elite skin. I recently reinstalled the game completely so there can't be any missing files and also ran index couple of times the same day.

For the Twitch drone: it's probably because of the Y6S3 change where they made it be able to jump, if you search for 362539203462 (W_Gadget_OPS_Twitch_ShockDrone_Jumping_LOD0_CM) it finds 2 entries and you can dump it.
## Post #571
- Username: lenetzp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 14, 2022 11:20 am
- Post datetime: 2022-05-19T11:45:51+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Can I get the material order of mesh?JsonMesh has order,but material only can organize manually.
## Post #572
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-05-19T18:23:03+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

> Reply from floxay ↑Sun May 15, 2022 9:19 pm at Sun May 15, 2022 9:19 pm
>
> 
gep55 wrote: ↑Sun May 15, 2022 7:25 pm
Trying to index the forge files using the latest version of the game I just downloaded off steam, but the tool keeps giving me this error. If anyone has any idea what the problem is I' would love to know.


Correct usage for the index command is described here: https://github.com/parzivail/RainbowForge#index
Usage: DumpTool.exe index <directory of forge files> <output index filename>
Example: DumpTool.exe index "X:\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege" "index.db"
You forgot to give a path/name for the database file.
MaZTeR wrote: ↑Tue May 10, 2022 2:49 am
I'm having trouble again. For some reason DumpTool is unable to find the Metadata containers for some gadgets, for example both the Twitch drone variants. I've ran the findallmeshpropsglobal function multiple times and it can't find anything for the object UIDs (which are 22439849214 and 42812368857). Same thing with the camera from Valkyrie's Elite skin and the bow and arrow from Hibana's Elite skin. I recently reinstalled the game completely so there can't be any missing files and also ran index couple of times the same day.


For the Twitch drone: it's probably because of the Y6S3 change where they made it be able to jump, if you search for 362539203462 (W_Gadget_OPS_Twitch_ShockDrone_Jumping_LOD0_CM) it finds 2 entries and you can dump it.
Ah thanks
## Post #573
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-05-26T22:47:23+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Do you know what the Elite Twitch drone is? The second UID is just the same default model, except there's also a large flat plane included.

Edit: Nevermind, it's 362539218206
## Post #574
- Username: TheLanda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 07, 2022 7:28 am
- Post datetime: 2022-06-07T00:43:17+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hi how are things?
I need help guys, I don't understand much about programming, I know the basics but I would love to know if someone can guide me little by little to be able to use the "R6S File"
## Post #575
- Username: lllIlIIIlllIllI
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 26, 2022 1:52 pm
- Post datetime: 2022-06-26T06:00:50+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

can somone make a tutorial guide video or make a gui tool cuz i don't have knowledge in programming and i would like to get the textures from the game
## Post #576
- Username: jinougaf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 01, 2022 11:54 pm
- Post datetime: 2022-07-15T07:32:07+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Anyone had already found the Y7 DLC's new weapon? the 9mm POF-9 used by Sens?
There are too many asset pack to check, anyone know which asset pack is more likely to have Y7 DLC's items? At least we can narrow down to 1 or 2 pack.
## Post #577
- Username: ghostboy1225
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 24, 2022 3:26 pm
- Post datetime: 2022-07-24T07:38:46+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

thanks for the work done on  these tools going to use this for a seige soundpack i've wanted to make for myself for a while.
## Post #578
- Username: lllIlIIIlllIllI
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 26, 2022 1:52 pm
- Post datetime: 2022-08-28T11:56:48+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

I'm having file not found error why ?
## Post #579
- Username: kayhotic
- Rank: n00b
- Number of posts: 16
- Joined date: Sat May 16, 2020 12:50 pm
- Post datetime: 2023-01-19T04:40:17+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

has anyone managed to get the flores altair model
## Post #580
- Username: SilentMayCry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 25, 2022 7:28 am
- Post datetime: 2023-03-09T08:45:04+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hi, I'm newbie, but I'm interested in exporting models from the game, I would like to find a partner with whom we could study this together. I would also like to clarify which package Lion's elite skin is in. Thanks in advance
## Post #581
- Username: Tapje
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 12, 2023 7:29 pm
- Post datetime: 2023-07-12T11:32:21+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Hey would anyone happen to still have any models that they are willing to share? I would love to experiment to make some rainbow six siege art with blender however in terms of getting the models, texturing and rigging them i don’t understand how to do it.
## Post #582
- Username: boutoron2685
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 28, 2021 10:07 am
- Post datetime: 2023-08-12T15:01:56+00:00
- Post Title: Re: 2022 - Tom Clancy's Rainbow Six: Siege Asset Extraction Tools

Unfortunately, this tool's project seems to [have been discontinued](https://github.com/parzivail/RainbowForge/issues/26).

If you are still interested in using this tool, you should use the [DepotDownloader](https://github.com/SteamRE/DepotDownloader) to get [Manifest 133280937611742404](https://steamdb.info/depot/359551/history/?changeid=M:133280937611742404). This manifest is updated to Y7S2.2.
