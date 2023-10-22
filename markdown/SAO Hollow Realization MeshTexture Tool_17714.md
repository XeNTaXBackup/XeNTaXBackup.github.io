## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-19T00:49:21+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

Hello,

I made this tool to quickly get meshes and textures from the game files. I decided to polish it a bit and release it. It might be useful to someone. I tested it with weapons and characters so far, not sure how well it will handle the maps and other stuff.

It can decompress CRI and OFS3, so you can directly load the files in the "chr/mod" or "wep/mod" game folders. No need to decompress beforehand.

An overview : 


How to use:
- File -> Open to load the game file.
- Export -> Export All to export all loaded files (meshes as IQE(skinned)/Obj, textures as png).
- You can select the mesh/texture in the file list to see a preview. Don't close the mesh preview window, once you open it. Or you need to restart the app to open it again.
- You can export files one at a time by clicking "Save as Obj/Iqe/Png".

Supported:
- Mesh - vertex coords, uvs, normals
- Skeleton - no bone names and hair rigs are problematic
- Texture - bc1-7 and raw pixels

Download: [http://www.mediafire.com/file/92sj23j6o ... er_Upd.rar](http://www.mediafire.com/file/92sj23j6o8ra311/SAOViewer_Upd.rar)
Note: You need to have .Net 4.6.2 installed. Also sorry that there are lots of dll files 

Extracted character with rig :


Credits:
- esperknight for CriPakTools
- Liquid-S for OFS3 Tool
- daemon1's texture tool for giving an idea of dds headers
## Post #2
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-02-19T07:03:14+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

any chance of SMD or DAE export for bones in the future?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-19T10:21:16+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from demonslayerx8
>
> any chance of SMD or DAE export for bones in the future?
Yea, maybe in the future. I will take a look at the skeleton data when I have the time.
## Post #4
- Username: Visker0z
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 23, 2018 7:56 am
- Post datetime: 2018-02-23T00:09:08+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

could this tool be used on SAO:HR for PC ? 
because i cant seem to get it work in game, i want to change some armor color, already extract the texture and change the color using Photoshop, then where to put the file? 
i put the file in : "[sao install folder]/pkg/data/chr/mod/b030/Textures/[filename].dds.phyre.png" still no change in the game (still old texture), is that the right path? or need to convert .png into .dds? or decompress it again into data.cpk?
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-23T03:08:22+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from Visker0z
>
> could this tool be used on SAO:HR for PC ? 
because i cant seem to get it work in game, i want to change some armor color, already extract the texture and change the color using Photoshop, then where to put the file? 
i put the file in : "[sao install folder]/pkg/data/chr/mod/b030/Textures/[filename].dds.phyre.png" still no change in the game (still old texture), is that the right path? or need to convert .png into .dds? or decompress it again into data.cpk?
It is for the pc version, but it won't let you mod the game. This tool is just for extracting assets from the game files. Unfortunately no support for re-importing them.

---

Btw I got the skeleton to work too. Bodies and faces seem to be fine, but hairs are not. Bone weights seem weird for the hairs, I am not sure what the problem is though. So just use static hair, or edit the weights. Also no bone names.

I updated the first post with an image and new link.
## Post #6
- Username: Visker0z
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 23, 2018 7:56 am
- Post datetime: 2018-02-23T04:56:07+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from akderebur
>
> Visker0z wrote:could this tool be used on SAO:HR for PC ? 
because i cant seem to get it work in game, i want to change some armor color, already extract the texture and change the color using Photoshop, then where to put the file? 
i put the file in : "[sao install folder]/pkg/data/chr/mod/b030/Textures/[filename].dds.phyre.png" still no change in the game (still old texture), is that the right path? or need to convert .png into .dds? or decompress it again into data.cpk?
It is for the pc version, but it won't let you mod the game. This tool is just for extracting assets from the game files. Unfortunately no support for re-importing them.

---

Btw I got the skeleton to work too. Bodies and faces seem to be fine, but hairs are not. Bone weights seem weird for the hairs, I am not sure what the problem is though. So just use static hair, or edit the weights. Also no bone names.

I updated the first post with an image and new link.

i see it's not for modding the game, well.. 1 more question, is the filename not change from original before extracted ?
## Post #7
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-02-23T09:05:38+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

IQE export for rigged meshes? hmm... never heard of that format before, nor know what tool to use to convert to FBX (3ds max user here)

Also, know which files is for main chars?
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-23T13:59:36+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from Visker0z
>
> 
i see it's not for modding the game, well.. 1 more question, is the filename not change from original before extracted ?
I am not sure if I fully understood your question. I think you mean the files in "chr/mod" folder by original files. They are basically containers (OFS3 format)  that have assets (textures, models) inside. The tool will unpack those assets and if they have a name you will see it on the list. Some of them seem to have empty names. 

I am using a program created by someone else to unpack the OFS3 files, so I don't really know that much myself.

> Reply from demonslayerx8
>
> IQE export for rigged meshes? hmm... never heard of that format before, nor know what tool to use to convert to FBX (3ds max user here)
It is a fairly easy format (human readability), and really convenient for skinned meshes. It has few importers. You have 2 options :

1) You can use this blender script : [Script](https://www.mediafire.com/file/akdda4pssxtvjd9/iqe_import.py/file)

After importing to Blender, you can export it as FBX. Note that blender applies a -90 degrees rotation on X axis to the root bone. It is not really a problem though. You can just set it to 0, after you import it into 3ds Max.

2) You can use  [IqeBrowser](http://www.moddb.com/mods/r-reinhard/addons/iqebrowser-v217) and [Noesis](http://richwhitehouse.com/index.php?content=inc_projects.php)

Open the iqe file with the IqeBrowser. Click the "Save" button on the lower left, and it will save it as iqm. Noesis can open iqm files, and after that you can export to lots of other formats.

Also I noticed that I messed up the non-skinned meshes while working on the skeleton, so make sure to download the tool again from the link in the first post.

> Reply from demonslayerx8
>
> Also, know which files is for main chars?
I am also finding by trial and error. Files starting with 3 (3000, 3001, 3002 etc.) are upper body, 4 is lower body, 5 is hair, 6 is face.

Characters seem to be indexed too. Like Kirito hair/face is 5000/6000, for Asuna it is 5001/6001. So first is Kirito, after that Asuna. I haven't checked the other characters.
## Post #9
- Username: NeonZed
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 09, 2015 11:15 pm
- Post datetime: 2018-03-16T11:55:37+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

How did you extract the cpk? I tried with noesis and it keeps giving me "Unexpected error parsing CPK" after a while.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-16T12:03:55+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from NeonZed
>
> How did you extract the cpk? I tried with noesis and it keeps giving me "Unexpected error parsing CPK" after a while.

Game files are compressed with CRILAYLA, so I used the "DecompressCRILAYLA" method from CriPakTools : [https://github.com/esperknight/CriPakTools](https://github.com/esperknight/CriPakTools)
## Post #11
- Username: TJorgi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 07, 2016 2:05 pm
- Post datetime: 2018-04-02T14:06:07+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

tested with PC version of Re:Hollow Fragment files, same type(OFS3 container, .phyre compression), the .dae extracts without problems, however i can´t extract the .tga texture. if possible to make a quick modification release of the SAO Viewer by adding suport(like how you made with the tokyo xanadu one). i will be on the wait.
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-02T14:30:23+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

Nice to hear that the models work fine.

Acewell already released a script for the textures on zenhax : [http://zenhax.com/viewtopic.php?f=7&t=7644](http://zenhax.com/viewtopic.php?f=7&t=7644)
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-04-07T04:48:58+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

Awesome tool!
It also works on the PC/ps4 secret of mana remake, it works fine for characters and some props, but it won't export maps at all unfortunatly.

Would it be possible to add support?
I can share some files if you don't have them readily available.
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-07T05:37:51+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from lionheartuk
>
> 
I can share some files if you don't have them readily available.
That would be great. I am abroad atm, and don't have the  files with me. I will take a look at the maps, if you share them.
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-04-07T06:54:22+00:00
- Post Title: SAO: Hollow Realization Mesh/Texture Tool

> Reply from akderebur
>
> lionheartuk wrote:
I can share some files if you don't have them readily available.
That would be great. I am abroad atm, and don't have the  files with me. I will take a look at the maps, if you share them.

Sure thing, will PM you.
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-12T17:45:54+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

Updated the tool, you can download the new version from the link in the first post.

What's new
- Added support for maps. There are still couple of problematic SAO maps, Secret of Mana maps seem to be fine.
- Fixed some problems with the IQE export
- Improved model preview

Maps from SAO :
 

Maps from Secret of Mana :
## Post #17
- Username: Fallenleader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 2:30 am
- Post datetime: 2018-05-27T02:03:47+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

Just noting here that I have had success loading in Hollow Fragment models as well, including a few maps. I haven't exhaustively tested it though, because the maps are in tiny pieces (chunks if you will) compared to a ninjaripped scene which if imported into blender with remove duplicate meshes enabled produces clean map rips once you delete UI elements and any character/monster models.

This will indeed be useful for character ripping though, because ninjaripper doesn't play nice when ripping them.

Do note I haven't tried exporting them, just loading them.

Edit: I stand corrected. I can readily extract meshes with some success, but textures are not read. Meshes export with no bones, which is fine since I can add my own rigs. I haven't tested actual maps as I aforementioned are in pieces compared to a good ninjaripped scene. This might me useful for the hollow area though, which seems to be much more fickle to rip than aincrad maps. Not sure where heads and hair are located though.
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-28T10:02:54+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

> Reply from Fallenleader
>
> I can readily extract meshes with some success, but textures are not read.
Yea, I already mentioned that on the previous page :

> Reply from akderebur
>
> Acewell already released a script for the textures on zenhax : http://zenhax.com/viewtopic.php?f=7&t=7644

> Reply from Fallenleader
>
> 
Meshes export with no bones, which is fine since I can add my own rigs.
Interesting, I think the skeleton was working before. Maybe I broke it when I released the update for the maps. I am not doing any tests with Hollow Fragment files. I will see if I can add proper support for Hollow Fragment, when I have the time.

Can you send me the file you are exporting? The one that gets exported with no bones.
## Post #19
- Username: Fallenleader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 2:30 am
- Post datetime: 2018-05-29T23:49:32+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

I don't mind, and no bones is no big deal for my particular case (though it would be a nice addition as long as they can get exported with a sane naming scheme for rigging and animation purposes, also assuming they don't export in a borked manor) as I can make a generic base and simply weight armor sets to each model for the ability to swap meshes to a single rig, simplifying things.

I am having an issue getting the preview working though. IDK why it was working before and hangs up and fails now. Trying to extract heathcliff's sword for what I am working on right now, but that's is literally impossible without being able to see and identify it.

For now, I will upload an extracted mesh along with the source file in a PM, because I am not too sure how it would be approached sharing game files directly here.

My only suggestion right now would be an about window or embed a version number on releases so it is easy to identify and ensure that the application is up to date. I just obtained it the day I made that post, so I think I am up to date unless the link contains an outdated tool.

I will be providing the animation data as well. Hopefully this is useful, and the ability to export it would be a massively appreciated bonus to boot. No worries if you don't support it though (I can make my own if need be, and pretty much bank on having to), just figured it may be useful. if you need anything else, let me know.
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-30T10:56:02+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

> Reply from Fallenleader
>
> I don't mind, and no bones is no big deal for my particular case
Bones are fine actually.



Are you using "Save as IQE"? OBJ has no support for skeleton.

> Reply from Fallenleader
>
> though it would be a nice addition as long as they can get exported with a sane naming scheme for rigging and animation purposes, also assuming they don't export in a borked manor
No proper names for the bones unfortunately, they will be numbered.

> Reply from Fallenleader
>
> 
I will be providing the animation data as well. Hopefully this is useful, and the ability to export it would be a massively appreciated bonus to boot.
I have no plans for adding animation support atm. Maybe in the future.
## Post #21
- Username: Fallenleader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 2:30 am
- Post datetime: 2018-06-08T22:49:45+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

Ah, I wasn't aware of that limitation, my apologies.

What about weapons though? I still cannot get them to load whatsoever, and lack Heathcliff's sword and Asuna's rapier to finish my current project. Being able to rip more is nice, but not a priority for me right now aside from those listed. Models resource only has Kirito's swords.

[SNIP]

Got the tool working again. will try loading weapons later.
## Post #22
- Username: Fallenleader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 29, 2018 2:30 am
- Post datetime: 2018-07-06T08:35:36+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

I might have found a serious issue with the tool.

When loading anything from Hollow Fragment (PC), it will open the mesh preview the first time. After that, preview fails to load further for either Hollow Fragment or Hollow Realization. Last time, I searched the registry for any key related to the tool and removed it, and it suddenly worked again.
I have actually narrowed down which registry key is causing this issue, though why it causes it, I am unsure. I just know deleting it and relaunching the application results in the preview working again. I also don't think the issue is limited to HF, as it is registry specific.

Registry key causing the issue is actually a few keys:
Computer\HKEY_CURRENT_USER\Software\ \
Computer\HKEY_CURRENT_USER\Software\ \SAOViewer\
Computer\HKEY_CURRENT_USER\Software\ \SAOViewer\1.0.0.0\

My theory is that it is because of the blank space in the structure name, but it very well could be that the entire keyset itself is causing the issue.

In the meantime, I can simply delete this key manually because I use the tool sparingly as I progress in my project, but it admittedly becomes quite inconvenient.

Anyhow, if anyone else here has this issue, just open regedit (windows key + r, type in "regedit" without the quotes, and find and delete the key with the name "SAOViewer" without quotes. This will temporarily fix the issue until you close the application again.
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-06T10:24:27+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

It is possible that the preview loads but it is minimized for some reason, so you think that it isn't getting loaded. Next time this happens try doing this : hover to the program icon on the windows task bar, hover over to "View Model", right-click and select Maximize or Restore if available.
## Post #24
- Username: mryesung
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 25, 2018 12:39 am
- Post datetime: 2018-11-24T17:26:48+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

How should we use this tool? When I load the SAOHR.exe file, or load data.cpk file, the program says that the file is not supported
## Post #25
- Username: mryesung
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 25, 2018 12:39 am
- Post datetime: 2018-12-26T06:04:49+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

Sorry but How did you unpack cpk files? I cannot find wep folder. Only adv, attach, chcr, chr folders
## Post #26
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-01-24T13:49:11+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

WHew okay, so after hours of trying and failing I'm so frustrated I want to check my computer out the window. can we please. PLEASE get an update for this tool to work with hollow fragment. I can not for the life of me get the texturest o extract or convert with any script,mod or program out there. and I'm really good and doing stuff like this, if its not one error it's another, no matter what I do I can't get the extension to add to the file I can't get noises to see the file I can get the model only and into blender but nothing with the textures.
PLEASE this is such a cool toll could you please update it for the PC version of hollow fragment.

WHen I try to add the Phyre ext to the file I get unexpected extension, osf3 expected RYHP. acewell did a wonderful job putting out a script for use, but gave no instruction how or what files to use it on.
## Post #27
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-24T14:30:34+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

If I remember correctly the game had both ofs3 and crilayla compression. You are probably having a problem with one of the decompression steps.

Acewell's script should work after yoh decompress properly.
## Post #28
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-01-24T14:43:40+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

> Reply from akderebur
>
> If I remember correctly the game had both ofs3 and crilayla compression. You are probably having a problem with one of the decompression steps.

Acewell's script should work after yoh decompress properly.

hey thank you for getting back to me so quick. OKAY so I FINALLY got it to work. but not with Acewells script. I had to use OFS3 tools I finally got them to unpack. 

But it would be SO much easier if you could add support for the textures to your tool.  Your tool is so amazing for realization files. please think about adding support for fragment to
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-25T08:15:35+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

> Reply from Xr79
>
> I can not for the life of me get the texturest o extract or convert with any script,mod or program out there. and I'm really good and doing stuff like this.... no matter what I do I can't get the extension to add to the file....WHen I try to add the Phyre ext to the file I get unexpected extension, osf3 expected RYHP. acewell did a wonderful job putting out a script for use, but gave no instruction how or what files to use it on.
the title of the script gives you all the hints on usage   
Noesis python script for PC version of Sword Art Online: Re Hollow Fragment *.phyre files. 

the script does not perform any decompression , that should be done prior,
and it was only tested on SAO:ReHF, no guarantee on it working with other games.  
if you're having to add extensions by hand then you are doing something wrong.
## Post #30
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-01-26T10:17:01+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

Hey Acewell, Thank you for replying I finally figured it out, your script was very helpful what was never said by anyone was that the steam files are in fact encrypted as OFS3 and that I needed to use a tool not at all made for HF to decrypt them and THEN your tool worked on them like a charm that was great, i was able to get the textures.


But I have realized that there are problems with the SAO viewer and this game, it can not view certain models like the main character heads are blank files for the tool, while all weapons and player armor and NPC heads not main characters work fine without textures.

it's pretty much a mess or a crap shoot if anything works for this game. and I understand that, the tool was made for Realization not fragment, totally fine. anyways just wanted to report my findings and thank you for your script!
## Post #31
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-05-02T21:28:04+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

how did you manage to extract the data.cpk without crashing after awhile?
This 34GB file keep crash CriPakTools while extracting
## Post #32
- Username: SusCX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 8:19 pm
- Post datetime: 2021-09-05T12:45:45+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

@akderebur Have you upgraded your tool to batch export ofs3 files for this game plus correcting the bones from SAO:HR, HF and also AL?
## Post #33
- Username: homelesskodai
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 11, 2020 5:33 am
- Post datetime: 2021-09-23T18:12:27+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

can someone tell the names of the files that contain Kirito and BallsDeep69 (Klein)
## Post #34
- Username: Justin39
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 30, 2022 4:08 pm
- Post datetime: 2022-03-30T08:11:19+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

How did you extract the cpk? I tried with noesis and it keeps giving me "Unexpected error parsing CPK" after a while.
## Post #35
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2022-09-02T23:34:46+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

> Reply from akderebur ↑Mon Feb 19, 2018 8:49 am at Mon Feb 19, 2018 8:49 am
>
> 
Thanks a lot for the tool! I was doing some comparison render of eugeo armor model, between hollow realization and alicization

but the alicization .dae.phyre doesn't seem to be supported, as it keeps giving me this.


Is there any way you could take a look at it? I've included two samples of .dae.phyre and their container.
[https://www.mediafire.com/file/mxgydlyv ... s.zip/file](https://www.mediafire.com/file/mxgydlyv2tnkj3w/SAO_Al_Samples.zip/file)
## Post #36
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2022-10-06T05:04:19+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

How to extract audio files then ?
## Post #37
- Username: LSparky
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 01, 2023 7:58 am
- Post datetime: 2023-07-06T23:14:08+00:00
- Post Title: Re: SAO: Hollow Realization Mesh/Texture Tool

Seeing that SAO Viewer doesn't support extracting the TGA files for the maps, are there any other programs that are able to do this?
