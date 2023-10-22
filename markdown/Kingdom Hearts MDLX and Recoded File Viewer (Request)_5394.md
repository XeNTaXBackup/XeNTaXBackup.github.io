## Post #1
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T18:13:20+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I have been using ModelViewerWXD3D9 for the longest time to view my Kingdom Hearts models, but it only can view about half of them without crashing. When I export those models to OBJs with 3D Ripper DX 1.8, they all get stretched upwards, which makes them difficult to look at and completely ruins some models like Jafar's lamp. It can't even view a.fm or adpx files. Also, there are no programs that can extract and/or view the 3D models within the p2 and z files from 358/2 and Re:coded, and no one has posted on the original topic for those models in weeks. And furthermore, the Re:COM 3D model format has not been cracked either, to the best of my knowledge. Is there a program, or a plugin for a program, or anything else that could help solve any of the above problems?
## Post #2
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-15T18:27:50+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

For MDLX, there is another model view that supports animations. Can't remember it's name though.

Nobody has bothered with Re Com because all the models in there are in KH1/2. There are no Highpoly models because all the cutscenes are pre recorded. There isn't much new stuff to get from it.
## Post #3
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T18:34:14+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Where can I download this other viewer?
## Post #4
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-15T18:45:00+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T18:54:27+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

The 3D viewport won't show me anything. How do I see the models?

Hold on, I figured it out. Thank you.
## Post #6
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T22:06:06+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Also, is it possible to make a MDLX plugin for Noesis? Or at least a way to capture them without being stretched?
## Post #7
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-21T02:29:52+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Not yet....don't know when i will get around to converting my code over to noesis.
[](http://img543.imageshack.us/i/mpxvkh2actorsora.jpg/)
## Post #8
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-21T12:32:55+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Well, I can sleep soundly at night knowing that there will be a MDLX plugin for Noesis eventually. Thank you, revelation.
## Post #9
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-22T03:36:47+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I'd personally appreciate a re:coded/days (same format for the models in both games) plug in for Noesis more. Though either would be great. Mostly I'm posting to get notifications of when a reply is posted.
## Post #10
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-22T09:54:14+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

revelation you are aweeeeeesome
Even Mr.Burn say
## Post #11
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-23T21:47:54+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I have found out the next step in extracting the models from 358/2, and by extension, Re:coded. The z files in the data/mi/ch/ folder contain character models. I think 0D, 43, and 56 all are models of Xion, and 3E is the model of Ven. If you download DSDecmp, and make a bat in the same folder with the command "DSDecmp X Y", where X is the filepath of the .z file and Y is is the filepath of the folder you would like the extracted file to go, then by running that bat, a .KAPH file of the same name will appear in that folder. Within those .KAPH files are BMD0 (Models), BCA0 (Animations), and other things. I learned much of this from [http://forums.qhimm.com/index.php?topic=10792.0](http://forums.qhimm.com/index.php?topic=10792.0) and [http://forums.qhimm.com/index.php?topic=8521.0](http://forums.qhimm.com/index.php?topic=8521.0) .
The BMD0 files can be opened with the nsbmd tool, but they have "custom opcodes" which makes it difficult to view them properly. I'm still not sure how to extract the BMD0s from the KAPHs, and I don't know how to fix the opcode issue.
The NSBMD Tool can be found at [http://pokemonhackingclub.webs.com/Programs/NSBMD.zip](http://pokemonhackingclub.webs.com/Programs/NSBMD.zip) .
Crystal Tile 2 has AsmView, which shows the file in terms of the ARM9 NDS processor.
A tool that is also useful for this is the video game Console Tool.
And apparently, Zerox already extracted the models.
## Post #12
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-24T00:19:54+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

If you guys want I could post what I used to extract the BMD0 and BMT (texture files) from the compressed files. Because if we can just figure out the already decompressed models that'd be good enough for me.
## Post #13
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-24T03:17:11+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-12-01T03:28:26+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Mirror man they're the same as 358/2 days models. So to decrypt them you could use the programs Barubary made. Here's those and info on the format:

I have more progress on the files of Days and Re:coded thanks to Barubary. I'll post quotes of what he told me about it. I hope this can help you guys figure out this format even further.

> Reply from Barubary
>
> 
- .z files are LZ-compressed files
- .p2 files have the following format:
Code: Select allchar[2] magicHeader; // 'P2'
WORD nFiles; // maybe longer/shorter. MSB flags filenames
QWORD padding;
DWORD dataStart;
WORD offsets[nFiles]; // to get real offset: << 9 + dataStart
WORD padding; // only if nFiles % 2 = 1
DWORD sizesAndFlags[nFiles]; // MSB flags compression
char filenames[8][nFiles]; // length 0 if nFiles & 0x8000 != 0
byte* data; // possibly preceded by padding, so that start matches dataStart
- .pak files have the following format:
Code: Select allchar[4] magicHeader; // 'KAPH'
DWORD padding; // ?
// if any of the offsets below are FFFFFFFF, it is not present
DWORD BCAdataOffset;
DWORD BVAdataOffset;
DWORD BMAdataOffset;
DWORD BTPdataOffset;
DWORD BTAdataOffset;
DWORD unknownOffset1;
DWORD unknownOffset2;
DWORD BMDdataOffset;

each offsets points to data formatted as such:
DWORD one; // always 1? (maybe number of files with this format? never seen something else though)
DWORD fileStart;
DWORD fileLength;
- .p2d / .pobj files have the following format:
Code: Select allchar[4] magicHeader; // 'D2KP'
DWORD padding;
DWORD* FATFolderEntryOffsets; // continues up to first offset. some offsets may be 0xFFFFFFFF

// each FAT Folder entry is formatted as follows:
DWORD numFiles;
DWORD[numFiles] offsets;
DWORD[numFiles] sizes;

// the data follows, possibly preceded by padding.

And how he actually decompressed them with his tools:

> Reply from Barubary
>
> For 358/2 Days (and for my R:c rips) I used an unpacker that could only decompress one specific file or folder at a time, and thus quite unusable for anybody who didn't create the program in the first place. I've now ported it to my more generic unpacker, NinUnpack, which should now be able to unpack all packages in both KH DS games. Drag a folder or a (set of) files on the executable (or use the command line) to unpack the given files. (providing a folder will only unpack the files directly in that folder; it is not recursive)
The game has three pack formats: P2, PK2D an HPAK. The first is just a generic archive file, like NARC but without folders. It has extension .p2 (or sometimes .p2f), but sometimes there is no extension at all for these files. PK2D (extension .D2KP, possibly others as well) only packs 2D graphic files. HPAK (extension .KAPH or .pak) only packs 3D graphic files.

Note that some files are compressed as well (in the normal filesystem, in packs, and I believe also in packs in packs). DSDecmp (or any other decompressor for DS formats) should work on those files (they usually have a .z extension, but sometimes none).

Edit: You also say it's possible to convert them by extracting the MDL0 via hex editor and then using that converter but my attempt at such has failed. Have you had any luck in actually converting a model through this method?
## Post #15
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-01T04:16:23+00:00
- Post Title: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I've had as much success as I've already shown, but as far as I've checked the two decryptors make the HEX method almost obsolete. Now, I've been trying to dump W_EX010_20_TR.mdlx from my KH2 disk for a while now, but what it all boils down to is that the file is there somewhere but the KH2 Dumper can't or won't find it. It's in the objentry file, but none of the blades, staffs, or shields customized for Tron or any other keyblade-changing world just aren't dumping. Does anyone have the texture for the Paranoids Oblivion?
## Post #16
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-18T22:34:23+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Sorry to bump this, but I was wondering if anyone managed to extract Xion's mdl0 file from the BDM0 one. I've tried with a hex editor like MirrorMan explained, but it failed when I tried to use the mdl0 converter.

Edit: After a few hours of hunting around the internet, I found a somewhat solution, thanks to this post here:
[http://forums.sonicretro.org/index.php?showtopic=20088](http://forums.sonicretro.org/index.php?showtopic=20088)

I now have xion's model (although the bone data is messed up), but I was able to rip it from the nsbmd linked in that post with 3dvia and also with ogle. I don't think the unhooded xion model has uv data, but the hooded one does. I've uploaded both models in dae format here:
hooded (with uv data) 
[http://www.3dvia.com/models/D0F6ADC6D8E ... 2011-3dxml](http://www.3dvia.com/models/D0F6ADC6D8EAFCCE/nsbmd-exe-fri-mar-18-22-02-00-2011-3dxml)

unhooded (no uv data) 
[http://www.3dvia.com/models/6C521862744 ... 2011-3dxml](http://www.3dvia.com/models/6C5218627446586A/nsbmd-exe-sat-mar-19-01-19-47-2011-3dxml)

Some of the vertices are messed up, so I'm working on fixing that now.
## Post #17
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-19T20:31:21+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Ah Xion's models! So good to see someone attempting to get them. I'll be watching to see if your able to fix them. Please keep us/me updated.
## Post #18
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-19T22:01:20+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Yay someone else is interested in Xion. Argh, I can't get the textures for her unhooded version though. Also her unhooded version has no UVs.   But her hooded version does have UVS, which includes her robe, which is basically the same, except from the shoulder up. I'm thinking that I'll try to use the UVs from the hooded version, for her unhooded robe. The model is really low poly though. 

Do you think anyone would be interested in an edited xion model that's higher poly? I'm going to make one for myself but if someone else wants it I'll post it here. Once I get the robe straightened out I'll modify larxene's robe so that it has similar dimensions to xion's. Then, I can use either kairi or namine as a base for her face, and kairi's KH1 hairstyle for the hair. It looks really similar, just parted differently. Larxene also has the same style of boots as Xion has. Larxene is just a lot taller and has a lot longer limbs, so I need to edit her mesh a lot to have it fit with Xion's/Kairi's/Namine's. 

Here's what I have so far. I have no clue if I actually untangled the vertices correctly or not though.
## Post #19
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-19T23:56:24+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Looks correct to me. I'd be happy if you were to upload that and post the link here or pm it to me.

You can get textures for unhooded Xion here: [http://www.textures-resource.com/other_ ... index.html](http://www.textures-resource.com/other_systems/KH358/index.html)

If you unscramble the mess of vertex on her unhooded model then I would be happy to see if I can correct the UV maps.
## Post #20
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-03-20T03:01:30+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Do you think anyone would be interested in an edited xion model that's higher poly? I'm going to make one for myself but if someone else wants it I'll post it here.
I definitely would be. I'm interested in all the models in this series, and the fact that this is probably the most elusive of all of them.. Yeah, I think there's definitely an interest in it.
## Post #21
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-20T20:24:14+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Yay someone else is interested in Xion. Argh, I can't get the textures for her unhooded version though. Also her unhooded version has no UVs.   But her hooded version does have UVS, which includes her robe, which is basically the same, except from the shoulder up. I'm thinking that I'll try to use the UVs from the hooded version, for her unhooded robe. The model is really low poly though. 

Do you think anyone would be interested in an edited xion model that's higher poly? I'm going to make one for myself but if someone else wants it I'll post it here. Once I get the robe straightened out I'll modify larxene's robe so that it has similar dimensions to xion's. Then, I can use either kairi or namine as a base for her face, and kairi's KH1 hairstyle for the hair. It looks really similar, just parted differently. Larxene also has the same style of boots as Xion has. Larxene is just a lot taller and has a lot longer limbs, so I need to edit her mesh a lot to have it fit with Xion's/Kairi's/Namine's. 

Here's what I have so far. I have no clue if I actually untangled the vertices correctly or not though.   

http://i54.tinypic.com/2cqcg88.jpg
http://i53.tinypic.com/16j59ac.jpg Those look correct to me. Great work! I for one would love to have a Xion model out there in a format that Noesis or Blender can understand. Does it have bones?
## Post #22
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-21T18:38:43+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Mirrorman95
>
> Those look correct to me. Great work! I for one would love to have a Xion model out there in a format that Noesis or Blender can understand. Does it have bones?

Yay I'm glad I could help out with something or other here. A once in a lifetime chance. lol. And no sorry, no bones.    I was able to get her only because 3dvia and ogle both worked with ntsb.exe, so all it did was capture the geometry.

But... I don't think it would be hard to add bones manually. After all, now that I have rigged versions of the typical org robe, I can just use that as a template. Plus, Xion is so darn low poly, so even less work. I'm planning on adding bones myself once I make sure I have all her vertices in correct postion, and have the UVs made up. When I do that, I'll upload her as an attachment.

Really though, what I ultimately want to do is just use xion's low poly model as a template, and modify larxene's robe, and use kairi's kh2 face and other parts as a base, and kairi's kh1 hair as a starting point, so that I can create an edited high poly version of xion.

> Reply from Krisan Thyme
>
> I definitely would be. I'm interested in all the models in this series, and the fact that this is probably the most elusive of all of them.. Yeah, I think there's definitely an interest in it.

Awesome. I'm kinda confused about why anyone would be interested in any of the models that we can find in the other games, because the polycount is soooooo much lower. Like for the others like axel or marluxia or namine or roxas, we already have those models in much better quality, so why would someone want the low quality ones from 358 days? 

Is it just a collection type of thing? That we have the models from that game, even if they're lower quality? Cause I can understand it from that angle cause I like to have complete collections of things myself. lol.

Xion is just so.. like you said. D@mn elusive! Her actual model only appears in one game, and then we get teased by seeing a higher quality version of her model that was pre-rendered, but not actually included in any game. Square. You teasers!   

> Reply from Zerox
>
> 
Looks correct to me. I'd be happy if you were to upload that and post the link here or pm it to me.

You can get textures for unhooded Xion here: http://www.textures-resource.com/other_ ... index.html

If you unscramble the mess of vertex on her unhooded model then I would be happy to see if I can correct the UV maps.

Thanks for the help with the UVS! It's more that they just don't exist...    They like aren't there at all. lol. So it's starting from scratch. But, since other models like namine have working uvs, I'm planning on using her as a template for part of it. But any help is appreciated!

I just discovered that console viewer 2.0 shows Xion's model correctly (and with textures.) Before I was using the 3.0 version and was wondering how the heck people were viewing the models in 3d. lol fail. While I can't capture the 3d data, it does have a wireframe only view, so I can take some screencaps of her model from the front, side and top, and then use that with maya to make sure I got the arm and robe verteies in the right area. Cause honestly, I was just winging it and hoping it looked vaguely correct.   

If anyone wants to mess with the 3dvia snapshots I've made, you can get them here:
unhooded w/no UV or Tex: 
[http://www.3dvia.com/models/4D2C39435567794B/xion-v2](http://www.3dvia.com/models/4D2C39435567794B/xion-v2)

Hooded w UV and Tex: 
[http://www.3dvia.com/models/6C521862744 ... m-ntsb-exe](http://www.3dvia.com/models/6C5218627446586A/xion-hooded-with-texture-from-ntsb-exe)

Unhooded with the ntsb player that makes them explode more (horrors!!! - no UV or text, not that it makes a difference ohgodmyeyes):
[http://www.3dvia.com/models/8CF0F78294A ... zoomed-out](http://www.3dvia.com/models/8CF0F78294A6B88A/xion-v1-zoomed-out)

I found another version of the ntsb viewer that seems to show the models slightly better (as in, they don't look like a bomb went off inside of them quite as much.) I'll upload that too as soon as I find what folder I saved it in. I can also upload the progress I made in a dae and obj format. But maya isn't open right now and it takes its god awful time loading for me.  Next time I open it I'll export what I have so far.   

Also, I kind of want to wait and upload the progress I've made after I use the console viewer as a double checker tool. I have a feeling I probably have some things in places where they shouldn't be... lol

EDIT: Wait never mind, I downloaded the viewer from the creator's website and now it works fine.

EDIT AGAIN: it looks like more faces are added to the model whenever i rip it from ogle or 3dvia. Argh. 

BUT OH. 
I found something that I think can view BMD0 files, but there's no precompiled binary and oh god I suck at that. Part of the summary was that it has BMD0 Reading and Writing and a BMD0 renderer, and it includes an export feature to json.
http://code.google.com/p/poke-tools/

WHY must I suck at programming and compiling. WHY.   Cgywin keeps beating me up with errors. lol
## Post #23
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-24T00:31:41+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I have Vista and Ubuntu. How do I compile poke-tools so I can use it?
## Post #24
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-24T21:20:02+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Mirrorman95
>
> I have Vista and Ubuntu. How do I compile poke-tools so I can use it?

I have XP and an ancient rock of a computer. But I have cygwin as a compiler. I'm able to run the build script and it compiles the .c and .h files with no problem, but when g++ tries to link to the open gl library, it fails because it can't find them. (even though I have them downloaded.) Woa is me. 

I'm a perfectionist, so even if I 'wing it' with vert placement, I'm still not happy. I'm going to redo my unhooded xion now that I can see the vert placement with console tool. But for now I'm focusing on unhooded xion (cause honestly, I want her head lol). 

It also seems that ogle and 3dvia split faces up that are otherwise unsplit when viewed with both console tool and nsbmd, which makes it harder in maya when I start unscrambling things. 

I made up a little basic template for myself that has the general placement of the verts for the model from the front and back, but because the model ends up with faces split up that were otherwise whole, the model doesn't exactly match my template. lol yay for confusion. 

What I really wish was that console tool had a simple front/back/side/top view that was not perspective/orthographic/etc, cause even looking at the model face on there has to be distortion from the projection. 

Here's my template thing, it might be of use if anyone else decides to unscramble a model: if you want a larger version just PM me, cause I resized this one so it wasn't LOLHUGE. 

yellow verts are ones that run along the 'seam' or whatever, where the front and back of the model meet and merge together. 



One more thing: the back robe part from the waist down also has a set of duplicate verts/faces that don't connect to the model. It's like they copied the entire thing and just cloned it and moved it forward just a bit. The only difference is one vert merges with its counterpart from the original lower part of the robe.

Here's a pic, I circled the vert that verges with its counterpart.






I'm working on a side view, because there's no depth data here. It's also 'general' placement because the view I used as a reference is perspective, so there's distortions. But it's the general vicinity that the verts should be in. When I load the model in maya the arms are inverted and the robe is rotated the wrong way, and two verts that belong to the robe are flung way way far away from the model. 

I'm making this mostly so that I'll know if something's way off with my attempt at fixing things. I don't want to place a robe vertex that should be up around the top of her boot all the way at the bottom of her feet, for example. Or have the top seam of her robe end up rotated so it's on the bottom on accident. Or something equally wacky (cause it's honestly hard to tell, and it looks 'right-ish' even if it's totally not.)

here's one of the shots I took as reference for the front and back template:
## Post #25
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-25T14:29:45+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Mirrorman95 wrote:I have Vista and Ubuntu. How do I compile poke-tools so I can use it?

I have XP and an ancient rock of a computer. But I have cygwin as a compiler. I'm able to run the build script and it compiles the .c and .h files with no problem, but when g++ tries to link to the open gl library, it fails because it can't find them. (even though I have them downloaded.) Woa is me. 

I'm a perfectionist, so even if I 'wing it' with vert placement, I'm still not happy. I'm going to redo my unhooded xion now that I can see the vert placement with console tool. But for now I'm focusing on unhooded xion (cause honestly, I want her head lol). 

It also seems that ogle and 3dvia split faces up that are otherwise unsplit when viewed with both console tool and nsbmd, which makes it harder in maya when I start unscrambling things. 

I made up a little basic template for myself that has the general placement of the verts for the model from the front and back, but because the model ends up with faces split up that were otherwise whole, the model doesn't exactly match my template. lol yay for confusion. 

What I really wish was that console tool had a simple front/back/side/top view that was not perspective/orthographic/etc, cause even looking at the model face on there has to be distortion from the projection. 

Here's my template thing, it might be of use if anyone else decides to unscramble a model: if you want a larger version just PM me, cause I resized this one so it wasn't LOLHUGE. 

yellow verts are ones that run along the 'seam' or whatever, where the front and back of the model meet and merge together. 



One more thing: the back robe part from the waist down also has a set of duplicate verts/faces that don't connect to the model. It's like they copied the entire thing and just cloned it and moved it forward just a bit. The only difference is one vert merges with its counterpart from the original lower part of the robe.

Here's a pic, I circled the vert that verges with its counterpart.






I'm working on a side view, because there's no depth data here. It's also 'general' placement because the view I used as a reference is perspective, so there's distortions. But it's the general vicinity that the verts should be in. When I load the model in maya the arms are inverted and the robe is rotated the wrong way, and two verts that belong to the robe are flung way way far away from the model. 

I'm making this mostly so that I'll know if something's way off with my attempt at fixing things. I don't want to place a robe vertex that should be up around the top of her boot all the way at the bottom of her feet, for example. Or have the top seam of her robe end up rotated so it's on the bottom on accident. Or something equally wacky (cause it's honestly hard to tell, and it looks 'right-ish' even if it's totally not.)

here's one of the shots I took as reference for the front and back template:

But will you release an OBJ of this model when you're done?
## Post #26
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-25T20:18:29+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Yep. When I get it sorted out I'll post an obj and a dae for anyone that wants them. Darn. if only console tool had a way to rip the 3d data.
## Post #27
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-26T00:47:14+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Yep. When I get it sorted out I'll post an obj and a dae for anyone that wants them. Darn. if only console tool had a way to rip the 3d data.

I doesn't, for the time being, except for geometry.
## Post #28
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-26T05:45:14+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

wait, console tool can rip geometry???
## Post #29
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-26T19:49:40+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> wait, console tool can rip geometry???

No, I mean the geometry loads correctly in v02b, and in that version you can rip the geometry with 3D Via Printscreen.
## Post #30
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-28T23:20:45+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Mirrorman95
>
> SoftIce wrote:wait, console tool can rip geometry???

No, I mean the geometry loads correctly in v02b, and in that version you can rip the geometry with 3D Via Printscreen.

oh oh! you mean that version of console tool? zomg so off to do that now.  and I swear that one vertex is just not there when i load the model into maya. The last vertex on her robe on the back. It like doesn't exist in maya. So confusing.  

Edit: Nooooooooo, version 02b loads the skeleton for xion incorrectly. lol And it lags the heck out of my comp. back to square one. But maybe it'll capture that one vertex that was missing otherwise. That way I can actually fix it.

Edit2: And it doesn't capture it on mine. whyyyy. Crap. I have the latest 3dvia printscreen thing too.  If it still can't can you upload a capture you made if I upload the bdm0 model? lol
## Post #31
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-04-23T23:30:54+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Hi yall. Wanted to bump to say I've made lots of progress with Xion's low poly model. I have the unhooded model's verticies correctly placed now, so no more broken limbs or twisted torsos. But because the unhooded model has no UV data I've had to go and make them myself, which is taking a bit longer than expected. But, I have her entire robe done now, and her face and her neck, so all that's left is to make the UVs for her hair and her ears. Ears will be a piece of cake. Hair will take a bit longer. I've started on the front part, but it's messed up still so I need to fix it. lol

Here's some screenshots. 




When I finish the UVs, I'll upload the model here for anyone who wants to fool around with it. It's not rigged or anything, but if you want to rig it that shouldn't be very hard considering how low poly it is. I also plan on making a custom high poly version of xion using Larx's robe (modified to xion's bodytype), plus kairi's face, and either kairi's kh hairstyle or aqua's hairstyle... or a modified version of both (i have to see which one fits xion's hair closer and modify that.)
## Post #32
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-04-24T00:14:18+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

wow awesome   SoftIce wil you also upload the high poly version when it is finished? i will need it for my Kingdom Hearts remark as a boss
## Post #33
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-24T02:07:55+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Ah it looks great so far. I'm excited to see the end result posted. Didn't she have more hair in front of her face/eyes?
## Post #34
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-04-26T00:02:15+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Thanks for the feedback guys! Yep, I plan to upload the custom high poly version when I complete it (I haven't even started on it though.. lol.)

Her hair was messed up in the preview pics I posted. lol. The UV's weren't scaled or arranged so it was a WIP. Her hair is all fixed now, and she's pretty much done. But then I noticed a few of the faces on her robe sleeve had the UVs messed up... so now I'm off to fix that, and then I started wondering if I had the verts right on the sleeve.. so yeah.   

Here's a pic of what I have at the moment. Please excuse the bright robe and hair textures..  heh, I had to lighten them because it was too hard to see the detail otherwise.    When I get everything set, I'll replace the edited textures with the originals. 



But yay for Xion no longer looking like she stuck her head in a lawn mower. But now she looks like she's going gray prematurely from stress or something.    

Also... is anyone interested in custom edits for some of the main KH2 characters? if anyone is I'll upload them here.  I don't mean new fanmade ones... I just mean fooling around with trying to give Kairi or Sora or Riku or Namine different outfits or different hairstyles. Haven't done any yet, but I'm going to eventually. 

.. Because I'm a nerd like that. Yeah.  

Oh, any Maya people here know how to deal with transparency settings? I use png images, but the entire mesh part appears semi-transparent sometimes. Oddest thing. Also, what texture do you use? At the moment I'm using surface shaders because they aren't affected by shadows, but when I try to render them, the transparency goes away, even though it's transparent in the viewport. Woe is me.. lol
## Post #35
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-26T21:14:03+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Ah yeah putting the textures brightened does help with black textures. It still looks quite improved from the last hair. "Yay for Xion not looking like she stuck her head in a lawn mower!" I totally agree. =P So your doing the UV's from scratch right? I must commend you on the work you've done so far imitating UV's exactly is a difficult process.
## Post #36
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-04-28T18:29:12+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Yeah, thank God for the console viewer which displays the textures/model correctly. lol. and for the fact that xion's hooded model and larxene's model both have the uv's preserved. So I had a lot of references to go off of. Still was a pain generating them from scratch though, since maya's attempts at auto-generationg UVs almost always ends messed up for me.   

I haven't played days yet, but I watched the cutscenes with xion in them. Now I'm all depressed because of her back story. Jeez, for a game with disney characters it can sure be depressing at times.
## Post #37
- Username: Tazuka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 29, 2011 7:48 am
- Post datetime: 2011-04-28T23:58:41+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Hello !

I would like to extract 3D model of a NSBMD file WITH UV data and texture   
I tested 3DVIA, HijackGL, Ogle, 3D Ripper DX
I can't extract with UV data   

Someone knows a program which extract 3D model of NSBMD file with UV data ? :'(

Thanks you very much for your future answers and sorry if you are busy

PS: Sorry for my bad english, I'm french
## Post #38
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-30T00:12:26+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> I haven't played days yet, but I watched the cutscenes with xion in them. Now I'm all depressed because of her back story. Jeez, for a game with disney characters it can sure be depressing at times.
 Kingdom Hearts has a immersive well thought out storyline. There are good moments and bad. Heck 358/2 made me cry.
## Post #39
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-02T01:46:24+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

great job softice
## Post #40
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-05-04T22:30:43+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Thanks for the encouragement guys.   

Oh lord, I was reading some threads over on the khinsider forum where people were discussing exactly what the nature of nobodies/sombodies/heartless is and all that. I must be dumb because some of it makes my brain want to melt. Some of the people there seriously know their stuff. I'm usually all 'hurrr lemme bash the bad guys with my giant key - oh yay triggered a cut scene finally.'. >_> 

I'm also the biggest procrastinator ever. I've had the low poly model of Xion done for several days but then I went all ADD and forgot about her because I got obsessed with the high poly counterpart's hair of all things.  yea..  

I'll upload an obj, dae and fbx version of her here, along with the textures I used. I got from the texture resource. You'll probably have to reassign the textures though, since I apparently fail at being able to export an obj that knows where the textures are. Whoo... 

I've gotten neurotic over high poly Xion's hair. I thought before it was just KH Kairi's hair flipped, but her front bangs are slightly different, her side bangs are different, her part line is not nearly as pronounced, and the back is different, and there's no freaking good quality video or shot of the back of her freaking head in any of the cutscenes. The best shot is one where you see it kinda off to the side, and even then it's confusing. Curse only having low quality cutscene material to work with! 

I think I'm still going to use KH Kairi's hair as the base though, and go from that. I also might use part's of kh2 yuffie's, and parts of Aqua's and a few others. I also found a random npc from ffx2 that has the back part of her hair kinda similar. Making Xion's high poly hair has been my obsession over the last few days.  I am such a nerd. 

Oh, and to Tazuka:
Which models are you trying to get? NSBMD.exe rips some with UV data and others with no UV data. I have no clue why it picks up on one model's UV data and not another one's. I've tried with ogle and 3dvia. Both seem to pick up the same basic shape. But, nsbmd.exe displays the models all distorted, so it's a huge mess to sort through, even if you get the UV data. Console tool (version 2.0) display's unhooded xion correctly, with UV data, but I've seen it mess up other models.. so not sure on that. And you can't rip 3d data from console tool, but you can use it as a reference. 

The only model that we don't have any version of from days is Xion, to my knowledge. All the others have high quality versions available in other games.
## Post #41
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-04T22:58:30+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Thanks for the encouragement guys.   

Oh lord, I was reading some threads over on the khinsider forum where people were discussing exactly what the nature of nobodies/sombodies/heartless is and all that. I must be dumb because some of it makes my brain want to melt. Some of the people there seriously know their stuff. I'm usually all 'hurrr lemme bash the bad guys with my giant key - oh yay triggered a cut scene finally.'. >_> 

I'm also the biggest procrastinator ever. I've had the low poly model of Xion done for several days but then I went all ADD and forgot about her because I got obsessed with the high poly counterpart's hair of all things.  yea..  

I'll upload an obj, dae and fbx version of her here, along with the textures I used. I got from the texture resource. You'll probably have to reassign the textures though, since I apparently fail at being able to export an obj that knows where the textures are. Whoo... 

I've gotten neurotic over high poly Xion's hair. I thought before it was just KH Kairi's hair flipped, but her front bangs are slightly different, her side bangs are different, her part line is not nearly as pronounced, and the back is different, and there's no freaking good quality video or shot of the back of her freaking head in any of the cutscenes. The best shot is one where you see it kinda off to the side, and even then it's confusing. Curse only having low quality cutscene material to work with! 

I think I'm still going to use KH Kairi's hair as the base though, and go from that. I also might use part's of kh2 yuffie's, and parts of Aqua's and a few others. I also found a random npc from ffx2 that has the back part of her hair kinda similar. Making Xion's high poly hair has been my obsession over the last few days.  I am such a nerd. 

Oh, and to Tazuka:
Which models are you trying to get? NSBMD.exe rips some with UV data and others with no UV data. I have no clue why it picks up on one model's UV data and not another one's. I've tried with ogle and 3dvia. Both seem to pick up the same basic shape. But, nsbmd.exe displays the models all distorted, so it's a huge mess to sort through, even if you get the UV data. Console tool (version 2.0) display's unhooded xion correctly, with UV data, but I've seen it mess up other models.. so not sure on that. And you can't rip 3d data from console tool, but you can use it as a reference. 

The only model that we don't have any version of from days is Xion, to my knowledge. All the others have high quality versions available in other games.

I'm excited to see the hooded/unhooded versions upload. Perhaps you should share them at ModelsResource as well then I won't be the only one with a 358/2 model there. Good luck making a high poly version, I'd personally recommend using Aqua's HP head for the base of the face because her face is just as HQ looking as the others but it's more conservative in polys. There are other things such as the few heartless like the (Large Armor, aka the armored Largebody) and then there's the Final Boss models. Those are unique as well.
## Post #42
- Username: Tazuka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 29, 2011 7:48 am
- Post datetime: 2011-05-05T19:49:25+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

To SoftIce,

First, thanks you very much for your answer. 
So, I tried with NSBMD files of Mario Kart DS on NSBMD.exe and when I rip with 3dvia, I don't have UV. 
With Ogle and 3D ripper DX, I can't get the result I should have ( No UV ).
I have tried with ConsoleTool, but It doesn't open my NSBMD files. 

Thanks you very much for your futur answers.

Sorry for my bad english, I'm french.
## Post #43
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-05-07T23:17:58+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Zerox
>
> I'm excited to see the hooded/unhooded versions upload. Perhaps you should share them at ModelsResource as well then I won't be the only one with a 358/2 model there. Good luck making a high poly version, I'd personally recommend using Aqua's HP head for the base of the face because her face is just as HQ looking as the others but it's more conservative in polys. There are other things such as the few heartless like the (Large Armor, aka the armored Largebody) and then there's the Final Boss models. Those are unique as well.
I'm trying to make it my goal to fire up maya today and finally export the unhooded xion model. *is such a procrastinator* The hooded model is much easier, since it has UVs. I can find that one and fix it and upload it too if you'd like it. I think I'll upload them to model resource too, so other people can enjoy my hard hard work. *laugh* They'll have two lonely models under that game then. lol

I probably won't focus on any other days models except for Xion in her cloak. She just caught my fascination and I *had* to get her model. Plus, I fear for my sanity if I attempt to unscramble one of the complex armor models. *dead* What happens to her in days made me quite depressed for a while.   

I don't really mind the higher poly count. I kind of want to have the highest amount I can out of the models available. Plus, because Xion has an identical facial structure to Kairi/Namine, it makes it much easier for me in the long run to start with their faces. I might use parts of Aqua's hair though, for part of Xion's side bang. Ah Aqua, another favorite character of mine. A strong badass female character? Oh heck yes. Er, anyway. 

> Reply from Tazuka
>
> To SoftIce,
First, thanks you very much for your answer. 
So, I tried with NSBMD files of Mario Kart DS on NSBMD.exe and when I rip with 3dvia, I don't have UV. 
With Ogle and 3D ripper DX, I can't get the result I should have ( No UV ).
I have tried with ConsoleTool, but It doesn't open my NSBMD files. 

Thanks you very much for your futur answers.

Sorry for my bad english, I'm french.

Don't worry, your english is fine.  I think it's very cool that you can speak two languages. I wish I could. lol.

And oooh, I see you're trying for a different game than KH days. Mario Cart. Hm. The best I can say is that you might get more luck with the link I posted below, which deals with mario cart ds and ripping stuff from it. I used their guide to help with ripping xion's model.

Ripping 3d models from the nitendo ds
[http://forums.sonicretro.org/index.php?showtopic=20088](http://forums.sonicretro.org/index.php?showtopic=20088)

Let me know if you get anywhere. lol. 

Oh also, with nsbmd, sometimes I would get UVs and sometimes I wouldn't... so it could just be that you have bad luck with the model you're trying to get. 

Console Tool acts strangely on my computer, so if the model isn't loading it could be that the program is acting weird again. I know the most recent version doesn't support the model format we're using anymore, so you need to use version 2.0. 

Here's a link to the version I use, with Xion's model included. See if you can get it to load her model. If it doesn't, then it's something with your computer since she loads on mine.

The version of Console Tool I'm using:
[http://www.mediafire.com/?kkcnaegq2w58xsk](http://www.mediafire.com/?kkcnaegq2w58xsk)

What operating system do you use, by the way? Xp, Vista or Windows 7?

Oh - if you notice the model dissapears if you turn off things like joints or the grid, try switching users on your computer so it goes back to the start logon screen, wait a few mins, and then switch back to your user account. It fixes the display for me 7 times out of 10. 

No clue why that helps. lol.

Edit:  HAHAHHA. Under my username it says I'm a 'veteran' now. That's ironic, since I know almost nothing about programming.
## Post #44
- Username: Chaquan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 09, 2011 5:15 pm
- Post datetime: 2011-05-10T00:27:35+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

If you want I can post my BMD0 from the compressed file to extract and bone marrow transplantation (texture file). Because if we simply find the extracted model, could not have been enough for me.
[lipsrsealed.gif](https://xentaxbackup.github.io/file/4219_lipsrsealed.gif)
## Post #45
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-05-13T22:13:24+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Thanks Chaquan, but I'm able to extract the BDM0 files okay. But, maybe yours somehow was extracted better than mine was. lol. Which model are you referring to, or do you just mean in general?

Anywayz... I finally got around to uploading my finished Xion model to mediafire. And since I'm neurotic, I included a bunch of different formats.   

Here ya guys go: The fruits of my hard labor. (Pffft... well it did take me a long time to do the UVS and fix the model cause I'm a n00b with Maya). 
Edit/Updated link - go here if you got the other pack. The models work better here.   
http://www.mediafire.com/?l505uffyk4ffeie

In this pack I included Dae, FBX, and OBJ files. 

the .DAE file was exported with opencollada. Still can't get the transparency to work for me. It needs to be RGB intensity and I'm retarded and can't figure out how to do that with lambert material and Maya (sorry.)

the FBX files were exported with Maya's default FBX exporter. The FBX is ascii and has the textures embedded. The transparency works for these and the materials are lambert. I included the 2006, 2009, 2010 and 2011 FBX versions. (I would have also included 2007 and 2008 versions.. but Maya didn't give me that option. Hurp.)  

But, both FBX and DAE don't seem to recognize Maya's surface shaders and convert them to lambert ones. Also... the materials don't work for the OBJ files. I have no clue... I'm retarded. I included one OBJ file with a mtl library and one OBJ file with no materials assigned. 

Each format has it's own folder with the textures inside it. 

When I figure out how to make the dae files use transparency I'll submit them to the model resource center... or I might just post a message at the forum there saying I'm retarded and can't figure out transparency for Dae files and can't figure out how to get OBJ files to know where the material files are. LOLOL

And why do I always end up writing novel length posts. I just like to ramble I guess. Derp. Anyway, let me know how the files work and if you need some other format or if I somehow managed to royally screw something up.  

Edit: Uh.. anyone know the policy over at the model resource for sharing ripped textures? Because I used Barubary's rip of Xion's textures for her textures, since when I ripped the model they didn't show up. I don't wanna get in trouble for including someone else's ripped textures in my file packet. Although, for her face, I did modify the texture so that it's not just half the face, but the entire face, so that I could add the second eye and not have her look cross eyed. 

Mmm, if it comes to it, I know console tool v3 showed the textures used... so I could 'rip' them myself and then edit them in photoshop to make them transparent.
## Post #46
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-14T17:21:23+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Looks fantastic! Thank you very much. As for textures I'm don't believe Barburary has ever "demanded" credits on anything. You could always ask him if your concerned, but there are people submitting models and stating they got the texture from the textures portion of the site and they are allowing it.

Besides the thing about ripped textures is that pretty much anyone could rip it themselves and get identical results.
## Post #47
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-14T19:11:08+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I had to heavily modify the mtl to map to the textures correctly, and that OBJ is the only one that will apply the textures.
## Post #48
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-05-14T22:49:39+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Thanks for the feedback you guys! I posted a message on the model resource comm, so I'll see what they say as well. I'm thinking that including a readme.txt crediting Barburary with originally ripping the textures will be fine. I know that anyone can get them, but since he was the one that got them for me I wanted to give him credit (because I only was able to get crappy quality jpegs when I tried *facepalm*)

Mirrorman, could you tell me what happens when you try to load the model? Were the UVs messed up, or was it that the program wasn't able to find where the textures were located? Also, what program are you using, and which version? 

I exported them from maya 2011, student or learning edition (whatever it's called.) Not sure if that makes a difference. I can try loading them into max 2009, which I also have. 

Sorry for asking like 20 questions. 

Edit Again: Re-uploaded the model pack. This time there's fbx ascii files, 1 opencollada dae file, and an obj with an mtl. Had to manually edit the files so that they would stop trying to link to my desktop. lol. fbx is still the only version that I can get transparency to work on. Although, I fixed the mtl file so that it should load the materials now, but, it doesn't load any transparency.  

New link:
[http://www.mediafire.com/?l505uffyk4ffeie](http://www.mediafire.com/?l505uffyk4ffeie)
## Post #49
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-15T06:00:11+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Thanks for the feedback you guys! I posted a message on the model resource comm, so I'll see what they say as well. I'm thinking that including a readme.txt crediting Barburary with originally ripping the textures will be fine. I know that anyone can get them, but since he was the one that got them for me I wanted to give him credit (because I only was able to get crappy quality jpegs when I tried *facepalm*)

Mirrorman, could you tell me what happens when you try to load the model? Were the UVs messed up, or was it that the program wasn't able to find where the textures were located? Also, what program are you using, and which version? 

I exported them from maya 2011, student or learning edition (whatever it's called.) Not sure if that makes a difference. I can try loading them into max 2009, which I also have. 

Sorry for asking like 20 questions. 

Edit Again: Re-uploaded the model pack. This time there's fbx ascii files, 1 opencollada dae file, and an obj with an mtl. Had to manually edit the files so that they would stop trying to link to my desktop. lol. fbx is still the only version that I can get transparency to work on. Although, I fixed the mtl file so that it should load the materials now, but, it doesn't load any transparency.  

New link:
http://www.mediafire.com/?l505uffyk4ffeie

The mtl file didn't point to the actual texture files. I had to find which ones went where, but after that it looked fine.
## Post #50
- Username: Tazuka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 29, 2011 7:48 am
- Post datetime: 2011-05-15T15:25:49+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Tazuka wrote:To SoftIce,
First, thanks you very much for your answer. 
So, I tried with NSBMD files of Mario Kart DS on NSBMD.exe and when I rip with 3dvia, I don't have UV. 
With Ogle and 3D ripper DX, I can't get the result I should have ( No UV ).
I have tried with ConsoleTool, but It doesn't open my NSBMD files. 

Thanks you very much for your futur answers.

Sorry for my bad english, I'm french. 

Don't worry, your english is fine.  I think it's very cool that you can speak two languages. I wish I could. lol.

And oooh, I see you're trying for a different game than KH days. Mario Cart. Hm. The best I can say is that you might get more luck with the link I posted below, which deals with mario cart ds and ripping stuff from it. I used their guide to help with ripping xion's model.

Ripping 3d models from the nitendo ds
http://forums.sonicretro.org/index.php?showtopic=20088

Let me know if you get anywhere. lol. 

Oh also, with nsbmd, sometimes I would get UVs and sometimes I wouldn't... so it could just be that you have bad luck with the model you're trying to get. 

Console Tool acts strangely on my computer, so if the model isn't loading it could be that the program is acting weird again. I know the most recent version doesn't support the model format we're using anymore, so you need to use version 2.0. 

Here's a link to the version I use, with Xion's model included. See if you can get it to load her model. If it doesn't, then it's something with your computer since she loads on mine.

The version of Console Tool I'm using:
http://www.mediafire.com/?kkcnaegq2w58xsk

What operating system do you use, by the way? Xp, Vista or Windows 7?

Oh - if you notice the model dissapears if you turn off things like joints or the grid, try switching users on your computer so it goes back to the start logon screen, wait a few mins, and then switch back to your user account. It fixes the display for me 7 times out of 10. 

No clue why that helps. lol.

Edit:  HAHAHHA. Under my username it says I'm a 'veteran' now. That's ironic, since I know almost nothing about programming.

Thanks for your answer,

I tried with [http://forums.sonicretro.org/index.php?showtopic=20088](http://forums.sonicretro.org/index.php?showtopic=20088) metasequoia, but, the object file is really messed up, and not uv-mapped.


With ConsoleToolv2.0 :

Render : [http://s2.noelshack.com/old/up/consolet ... 96d978.jpg](http://s2.noelshack.com/old/up/consoletool2-eac896d978.jpg) 
I don't have a good UV rendering 
3DVia Printscreen don't print 3D Model 

With NSBMD Viewer : 

Render : [http://s2.noelshack.com/old/up/nsbmdvie ... 97e898.jpg](http://s2.noelshack.com/old/up/nsbmdviewer-074f97e898.jpg)
I have a good UV rendering
3DVia Printscreen print 3D model but not UV data   

I use Windows XP x86

Thanks.
## Post #51
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-05-16T21:37:41+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Mirrorman95
>
> The mtl file didn't point to the actual texture files. I had to find which ones went where, but after that it looked fine.

Oh that's a big relief. I was worried the data was corrupted or something. Did you try with the updated pack? The obj mtl file lists all the materials, and it loads correctly in maya for me. (Maya generates incorrect mtl files, I discovered. For me, anyway.)

> Reply from Tazuka
>
> 
Thanks for your answer,

I tried with http://forums.sonicretro.org/index.php?showtopic=20088 metasequoia, but, the object file is really messed up, and not uv-mapped.


With ConsoleToolv2.0 :

Render : http://s2.noelshack.com/old/up/consolet ... 96d978.jpg 
I don't have a good UV rendering 
3DVia Printscreen don't print 3D Model 

With NSBMD Viewer : 

Render : http://s2.noelshack.com/old/up/nsbmdvie ... 97e898.jpg
I have a good UV rendering
3DVia Printscreen print 3D model but not UV data   

I use Windows XP x86

Thanks.

No problem.  I usually can't help out here at all, so when I get the chance to try to i'm always happy. You also have the same operating system as me. haha. 

And sorry! I wasn't clear before. Console Tool doesn't let you rip any 3d data. I only mentioned it because it displayed the model I was trying to rip correctly, while the NSBMD viewer did not. 

It looks like nsbmd and console tool both display your model geometry the same, which is good. It also looks like they pick up the same texture files. I can see they both also miss the same ones (rainbow ...cars, I believe...?)

It looks like you're trying to rip a race track of sorts? Is it a model the world/level/race track/whatever? And you say that nsbmd doesn't rip the UV data? Oh, that's harsh because making new UVs is a great pain (as I have learned.) 

How is the model you ripped messed up, besides for no uv data? Is the geometry actually screwed up... like are the vertices in the wrong area, or is it just that there are no textures? If your model's geometry is messed up, that adds a new problem. For me, I was working with one individual model. If you have an entire race track that has screwed up vertices, it'll take more time. If the geometry of the ripped model IS screwed up, let me know and I'll tell you what I did in my case. (it's a cumbersome and not streamlined process, so if you don't have that issue, I won't bother cluttering up the post with it lol) 

Oh, is there only one Mario Cart game for the DS? Which level or model are you trying to get? If it is a race track, is it a track that has been used in other Mario Cart games? If it has, you still have more options than trying to fix messed up vertices or making all new UVs. 

If it's a whole new race track, and it's just that the UV and textures are gone, then I'd suggest trying this: See if any other of the race track models pick up UV data when you rip them, and if they do, use those UVs as a guide of sorts for when you go to make your own UVs (eg, how they map out the road and the cars etc.) 

Let me know if you get anywhere or if I wasn't clear somewhere. (I know I tend to ramble on and on   )

Oh, could you post a screenshot of what the model looks like when you rip it? What 3d editing program are you using? You know, you can get the educational or whatever version of maya 2011, for free!! Just tell them you are a student (I am lol), and then you can use a fully functional version of Maya, that just has a screen saying this is for educational purposes don't use this for profit, and all that. 

For me, I have maya 2011 student edition, 3d max 09, blender, and milkshape. I use maya the most now though. And max if maya is acting wonky.
## Post #52
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-17T00:40:58+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

The new OBJ looks all black in P3DO, but the DAE looks fine now in GLC Player, except it doesn't detect the transparency.
## Post #53
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-05-17T19:14:50+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

lol. let me try using that program. And 3dmax 2009. Maya2011 might be acting strangely for me or something.
## Post #54
- Username: HeartofFire
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 16, 2011 5:42 am
- Post datetime: 2011-06-15T21:46:51+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Umm.... do you mind if I use this to make a model for MMD? There isn't an official one yet. I would totally credit you.
## Post #55
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2011-10-24T20:44:24+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Okay, I have a ROM for Re: coded and am using Tahaxan to peek inside... and I'm completely lost on what to do to extract everything. Furthermore, is there anything available to view models/whatnot if I get this ROM extracted?

(Old topic is old, I know, but I figured a little help is better than none.)
## Post #56
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-10-25T02:07:17+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Assuming you actually have the Re:coded game legally and you just downloaded an identical ROM, you would use dslazy to extract everything, but then use [http://www.propl.nl/random/DSDecmp4b.zip](http://www.propl.nl/random/DSDecmp4b.zip) and [http://www.propl.nl/random/NinUnpack.zip](http://www.propl.nl/random/NinUnpack.zip) in alternation to unpack and decompress the models and other data. The models are bmd0 files in NSBMD format, and although there are many model viewers that can read that format, only Version 2.0 of the ConsoleTool at [http://www.romhacking.net/forum/index.php?topic=8407.0](http://www.romhacking.net/forum/index.php?topic=8407.0) can actually display the game's character models properly. I think it's because Re:coded and 358/2's NSBMD format uses different bone opcodes than that of most other NDS games. You can only export them with other NSBMD viewers, but any model with a posable armature converted this way will be completely off. At [http://www.romhacking.net/forum/index.p ... #msg190237](http://www.romhacking.net/forum/index.php/topic,8407.msg190237.html#msg190237) , LowLines has given specific documentation on the model and container formats used in 358/2 and Re:coded, as he hopes to reincorporate them in a later ConsoleTool release.
## Post #57
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2011-10-25T21:57:00+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Mirrorman95
>
> Assuming you actually have the Re:coded game legally and you just downloaded an identical ROM, you would use dslazy to extract everything, but then use http://www.propl.nl/random/DSDecmp4b.zip and http://www.propl.nl/random/NinUnpack.zip in alternation to unpack and decompress the models and other data. The models are bmd0 files in NSBMD format, and although there are many model viewers that can read that format, only Version 2.0 of the ConsoleTool at http://www.romhacking.net/forum/index.php?topic=8407.0 can actually display the game's character models properly. I think it's because Re:coded and 358/2's NSBMD format uses different bone opcodes than that of most other NDS games. You can only export them with other NSBMD viewers, but any model with a posable armature converted this way will be completely off. At http://www.romhacking.net/forum/index.p ... #msg190237 , LowLines has given specific documentation on the model and container formats used in 358/2 and Re:coded, as he hopes to reincorporate them in a later ConsoleTool release.
Yeah, I own a copy of Re:coded, but I must point out that DSDecmp seems to crash a lot on my computer. Still seem to have managed to extract some stuff, but it's really slow going, not to mention the only stuff I've found definitively seems to be the character "pictures" used in cutscenes since digging through all those directories is a bit of a pain. Really wish this were easier, but oh well.
## Post #58
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2011-11-10T20:27:22+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Shameless bump with another question: Would it just be easier to drag the unpacked game's main folder onto each decomposer, or do I really need to dig into the subdirectories and do it? It seems like it'd be a lot quicker to just drag the main folder itself onto them, but I dunno whether that would work.  

Also, which directory are the character models in? All my digging for them has proved relatively fruitless right now...
## Post #59
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2012-01-25T04:04:09+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

where do I find the ntsb viewer?
## Post #60
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2012-04-20T19:57:51+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from SoftIce
>
> Mirrorman95 wrote:Those look correct to me. Great work! I for one would love to have a Xion model out there in a format that Noesis or Blender can understand. Does it have bones?

Yay I'm glad I could help out with something or other here. A once in a lifetime chance. lol. And no sorry, no bones.    I was able to get her only because 3dvia and ogle both worked with ntsb.exe, so all it did was capture the geometry.

But... I don't think it would be hard to add bones manually. After all, now that I have rigged versions of the typical org robe, I can just use that as a template. Plus, Xion is so darn low poly, so even less work. I'm planning on adding bones myself once I make sure I have all her vertices in correct postion, and have the UVs made up. When I do that, I'll upload her as an attachment.

Really though, what I ultimately want to do is just use xion's low poly model as a template, and modify larxene's robe, and use kairi's kh2 face and other parts as a base, and kairi's kh1 hair as a starting point, so that I can create an edited high poly version of xion.
Krisan Thyme wrote:I definitely would be. I'm interested in all the models in this series, and the fact that this is probably the most elusive of all of them.. Yeah, I think there's definitely an interest in it.

Awesome. I'm kinda confused about why anyone would be interested in any of the models that we can find in the other games, because the polycount is soooooo much lower. Like for the others like axel or marluxia or namine or roxas, we already have those models in much better quality, so why would someone want the low quality ones from 358 days? 

Is it just a collection type of thing? That we have the models from that game, even if they're lower quality? Cause I can understand it from that angle cause I like to have complete collections of things myself. lol.

Xion is just so.. like you said. D@mn elusive! Her actual model only appears in one game, and then we get teased by seeing a higher quality version of her model that was pre-rendered, but not actually included in any game. Square. You teasers!   
Zerox wrote:
Looks correct to me. I'd be happy if you were to upload that and post the link here or pm it to me.

You can get textures for unhooded Xion here: http://www.textures-resource.com/other_ ... index.html

If you unscramble the mess of vertex on her unhooded model then I would be happy to see if I can correct the UV maps. 


Thanks for the help with the UVS! It's more that they just don't exist...    They like aren't there at all. lol. So it's starting from scratch. But, since other models like namine have working uvs, I'm planning on using her as a template for part of it. But any help is appreciated!

I just discovered that console viewer 2.0 shows Xion's model correctly (and with textures.) Before I was using the 3.0 version and was wondering how the heck people were viewing the models in 3d. lol fail. While I can't capture the 3d data, it does have a wireframe only view, so I can take some screencaps of her model from the front, side and top, and then use that with maya to make sure I got the arm and robe verteies in the right area. Cause honestly, I was just winging it and hoping it looked vaguely correct.   

If anyone wants to mess with the 3dvia snapshots I've made, you can get them here:
unhooded w/no UV or Tex: 
http://www.3dvia.com/models/4D2C39435567794B/xion-v2

Hooded w UV and Tex: 
http://www.3dvia.com/models/6C521862744 ... m-ntsb-exe

Unhooded with the ntsb player that makes them explode more (horrors!!! - no UV or text, not that it makes a difference ohgodmyeyes):
http://www.3dvia.com/models/8CF0F78294A ... zoomed-out

I found another version of the ntsb viewer that seems to show the models slightly better (as in, they don't look like a bomb went off inside of them quite as much.) I'll upload that too as soon as I find what folder I saved it in. I can also upload the progress I made in a dae and obj format. But maya isn't open right now and it takes its god awful time loading for me.  Next time I open it I'll export what I have so far.   

Also, I kind of want to wait and upload the progress I've made after I use the console viewer as a double checker tool. I have a feeling I probably have some things in places where they shouldn't be... lol

EDIT: Wait never mind, I downloaded the viewer from the creator's website and now it works fine.

EDIT AGAIN: it looks like more faces are added to the model whenever i rip it from ogle or 3dvia. Argh. 

BUT OH. 
I found something that I think can view BMD0 files, but there's no precompiled binary and oh god I suck at that. Part of the summary was that it has BMD0 Reading and Writing and a BMD0 renderer, and it includes an export feature to json.
http://code.google.com/p/poke-tools/

WHY must I suck at programming and compiling. WHY.   Cgywin keeps beating me up with errors. lol

Can you send me he link for ntsb viewer & what was the creator's website that you got the ntsb viewer?
## Post #61
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2012-04-24T17:50:05+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Zerox
>
> Ah Xion's models! So good to see someone attempting to get them. I'll be watching to see if your able to fix them. Please keep us/me updated.

SoftIce, Can you send me the link to download the ntsb viewer?
## Post #62
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2012-09-25T07:02:15+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

I still live!    I'll re-upload her as soon as I find where I stored her file on my hd. (It's been like a year, my  memory is fuzzy.   )
## Post #63
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-09-25T14:34:20+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

> Reply from Escope12
>
> SoftIce wrote:Mirrorman95 wrote:Those look correct to me. Great work! I for one would love to have a Xion model out there in a format that Noesis or Blender can understand. Does it have bones?

Yay I'm glad I could help out with something or other here. A once in a lifetime chance. lol. And no sorry, no bones.    I was able to get her only because 3dvia and ogle both worked with ntsb.exe, so all it did was capture the geometry.

But... I don't think it would be hard to add bones manually. After all, now that I have rigged versions of the typical org robe, I can just use that as a template. Plus, Xion is so darn low poly, so even less work. I'm planning on adding bones myself once I make sure I have all her vertices in correct postion, and have the UVs made up. When I do that, I'll upload her as an attachment.

Really though, what I ultimately want to do is just use xion's low poly model as a template, and modify larxene's robe, and use kairi's kh2 face and other parts as a base, and kairi's kh1 hair as a starting point, so that I can create an edited high poly version of xion.
Krisan Thyme wrote:I definitely would be. I'm interested in all the models in this series, and the fact that this is probably the most elusive of all of them.. Yeah, I think there's definitely an interest in it.

Awesome. I'm kinda confused about why anyone would be interested in any of the models that we can find in the other games, because the polycount is soooooo much lower. Like for the others like axel or marluxia or namine or roxas, we already have those models in much better quality, so why would someone want the low quality ones from 358 days? 

Is it just a collection type of thing? That we have the models from that game, even if they're lower quality? Cause I can understand it from that angle cause I like to have complete collections of things myself. lol.

Xion is just so.. like you said. D@mn elusive! Her actual model only appears in one game, and then we get teased by seeing a higher quality version of her model that was pre-rendered, but not actually included in any game. Square. You teasers!   
Zerox wrote:
Looks correct to me. I'd be happy if you were to upload that and post the link here or pm it to me.

You can get textures for unhooded Xion here: http://www.textures-resource.com/other_ ... index.html

If you unscramble the mess of vertex on her unhooded model then I would be happy to see if I can correct the UV maps. 


Thanks for the help with the UVS! It's more that they just don't exist...    They like aren't there at all. lol. So it's starting from scratch. But, since other models like namine have working uvs, I'm planning on using her as a template for part of it. But any help is appreciated!

I just discovered that console viewer 2.0 shows Xion's model correctly (and with textures.) Before I was using the 3.0 version and was wondering how the heck people were viewing the models in 3d. lol fail. While I can't capture the 3d data, it does have a wireframe only view, so I can take some screencaps of her model from the front, side and top, and then use that with maya to make sure I got the arm and robe verteies in the right area. Cause honestly, I was just winging it and hoping it looked vaguely correct.   

If anyone wants to mess with the 3dvia snapshots I've made, you can get them here:
unhooded w/no UV or Tex: 
http://www.3dvia.com/models/4D2C39435567794B/xion-v2

Hooded w UV and Tex: 
http://www.3dvia.com/models/6C521862744 ... m-ntsb-exe

Unhooded with the ntsb player that makes them explode more (horrors!!! - no UV or text, not that it makes a difference ohgodmyeyes):
http://www.3dvia.com/models/8CF0F78294A ... zoomed-out

I found another version of the ntsb viewer that seems to show the models slightly better (as in, they don't look like a bomb went off inside of them quite as much.) I'll upload that too as soon as I find what folder I saved it in. I can also upload the progress I made in a dae and obj format. But maya isn't open right now and it takes its god awful time loading for me.  Next time I open it I'll export what I have so far.   

Also, I kind of want to wait and upload the progress I've made after I use the console viewer as a double checker tool. I have a feeling I probably have some things in places where they shouldn't be... lol

EDIT: Wait never mind, I downloaded the viewer from the creator's website and now it works fine.

EDIT AGAIN: it looks like more faces are added to the model whenever i rip it from ogle or 3dvia. Argh. 

BUT OH. 
I found something that I think can view BMD0 files, but there's no precompiled binary and oh god I suck at that. Part of the summary was that it has BMD0 Reading and Writing and a BMD0 renderer, and it includes an export feature to json.
http://code.google.com/p/poke-tools/

WHY must I suck at programming and compiling. WHY.   Cgywin keeps beating me up with errors. lol

Can you send me he link for ntsb viewer & what was the creator's website that you got the ntsb viewer?

LowLine's Console Tool is the only program that can load the BMD0 files from Re:Coded and 358/2 Days correctly.
## Post #64
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2014-05-12T20:31:54+00:00
- Post Title: Re: Kingdom Hearts MDLX and Re:coded File Viewer (Request?)

Sorry for bumping such an old thread, but I'm trying to find the character files in Re:coded. Console Tool can read the models fine, I just don't know where the character models themselves are stored (the directories are very confusing). Thanks!
