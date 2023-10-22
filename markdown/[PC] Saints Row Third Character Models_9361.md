## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-28T09:53:04+00:00
- Post Title: [PC] Saints Row Third: Character Models

Source Code:

[pc_saints_row3.h](http://code.google.com/p/sticklove/source/browse/trunk/source/xentax/ripper/pc_saints_row3.h)
[pc_saints_row3.cpp](http://code.google.com/p/sticklove/source/browse/trunk/source/xentax/ripper/pc_saints_row3.cpp)

Instructions:

```
* Use Rick's UnpackVPP tool to extract the VPP_PC files by dragging and dropping.
* Rick's latest UnpackVPP build crashes on soundboot.vpp_pc.
* You should have a bunch of folders and you can delete the extra VPP_PC files.
* Don't use Rick's UnpackSTR2; ripper takes care of this.
* Place ripper.exe and the zlib DLL in this directory as well.
* Before you run ripper, I would delete any directories that don't contain models files (like sound directories). ripper will run faster this way.
* Run ripper.exe.
* Look at image below to see how your folder should look before running ripper.

```



Notes:

```
* Character models only.
* Texturing is manual (for now).
* Models are in LWO files.
* Skeletons are in OBJ files. They were kind of complex and best I can do is just joints connected by lines.
* Use your modeler to reconstruct bones to your liking using the OBJ file.
* Skeletons need to be rotated.

```


If you want static models, and there are over 100,000 of them (there are many duplicate files in different STR2_PC files though), either reply here or hit that thanks button to let me know there's interest. I tend to stop working on things when there is no interest (One Piece, Rise of Nightmares, etc.).

If there is anything wrong with any of the models, let me know. It is too hard to browse through 2,690 model files, 2,890 texture files, etc., to see if everything is OK. Some models had multiple UV channels; hope I got the right ones lol.
[saintsrowthird.7z](https://xentaxbackup.github.io/file/5613_saintsrowthird.7z)
## Post #2
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2012-07-28T11:02:05+00:00
- Post Title: [PC] Saints Row Third: Character Models

lol greats Job ^^ look like you work really hard^^
## Post #3
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-28T11:31:45+00:00
- Post Title: [PC] Saints Row Third: Character Models

Thanks again o/
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-28T13:12:02+00:00
- Post Title: [PC] Saints Row Third: Character Models

NP.

There was a ZLIB bug in the extractor... some of the DLC archives contain 0-byte files, which is why you see a ZLIB error around
Processing file 2396 of 6393: C:\Users\semory\source\xentax\Release\saints\dlc1\Running Man DLC.str2_pc.

Problem fixed and first post updated.

There is also a problem with some of the head LOD models. An eye point is off and I think this is intentional since the UV's are fine and the point is like in the middle of the vertex buffer. Not sure why... many of them are the same point... point #200 in the vertex buffer. I will look into it soon.
## Post #5
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-28T19:19:08+00:00
- Post Title: [PC] Saints Row Third: Character Models

Ok i apreciate that info howfie and thanks for release this.
## Post #6
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-28T21:00:07+00:00
- Post Title: [PC] Saints Row Third: Character Models

head's must be hiding from us  

DxRipper rip no UV's.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-28T21:19:07+00:00
- Post Title: [PC] Saints Row Third: Character Models

send me that file... i will convert some of the points to hex and do a file search for these numbers, even if they exist in the EXE lol. that pic you posted might be from cf_body.
## Post #8
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-28T21:42:19+00:00
- Post Title: [PC] Saints Row Third: Character Models

> Reply from howfie
>
> send me that file... i will convert some of the points to hex and do a file search for these numbers, even if they exist in the EXE lol. that pic you posted might be from cf_body.
There's a npc_basehead for male(john) and female(iory) they have good quality, I think the game uses morphs on them, maybe.
I'll pm you that head file in a sec.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-29T02:01:00+00:00
- Post Title: [PC] Saints Row Third: Character Models

not just maybe, that is indeed the case . you pretty much guessed it. just have to figure out the morph format. for example, the base mesh has 0x592 vertices and shaundi's morph file has this at the end. this is going to require the ripper to do another pass at the files.

```
9105 6D75 8400 0000 0000 0000

```


i still haven't found that super high-resolution face you posted. it's not any of the base meshes lol. i couldn't search for it because dx ripper must scale the points (the head model in the OBJ wasn't on the same scale as the base meshes).
## Post #10
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-29T15:27:57+00:00
- Post Title: [PC] Saints Row Third: Character Models

> Reply from howfie
>
> not just maybe, that is indeed the case . you pretty much guessed it. just have to figure out the morph format. for example, the base mesh has 0x592 vertices and shaundi's morph file has this at the end. this is going to require the ripper to do another pass at the files.
Code: Select all9005 6779 8500 151B 1548 D1F6
9105 6D75 8400 0000 0000 0000


i still haven't found that super high-resolution face you posted. it's not any of the base meshes lol. i couldn't search for it because dx ripper must scale the points (the head model in the OBJ wasn't on the same scale as the base meshes).

It's from the initiation station, I couldn't get dxripper working with the full game.
## Post #11
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-30T00:33:38+00:00
- Post Title: [PC] Saints Row Third: Character Models

Hey howfie just curius how i can import the LW0 files into max ? there is any plugin for that ?
i didnt research but dont find any usefull info.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-30T00:52:09+00:00
- Post Title: [PC] Saints Row Third: Character Models

No there is no light waves plugins for 3 d studio max that I know of. There are some things that complicate matters such that skin controllers in 3 d studio max must have weights associated with bones. Also the 3 d studio max plugin sdk is really really ugly. I might write a max script  plugin for lwo files pretty soon. But for now there are some things that you can do. You can use light wave and convert the lwo to either obj or fbx. You can also use blender to convert the files as well, which is what rexil does.
## Post #13
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-30T01:46:55+00:00
- Post Title: [PC] Saints Row Third: Character Models

Oh ok , thanks for clarify that .
## Post #14
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-07-30T10:10:31+00:00
- Post Title: [PC] Saints Row Third: Character Models

Heyo there,

howfire, is the ripper application working properly? Because there are a few files, at least for me, which the ripper cant unpack, mostly from the patch_compressed and patch_uncompressed directories and then just stops. If I remove all those unpackable files and let it do its job, the dds textures are all...invalid. At least for Photoshop.

Or did I miss something?
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-30T10:26:50+00:00
- Post Title: [PC] Saints Row Third: Character Models

i have 72 game files in patch_compressed, plus 3 files ripper ripped for a total of 75 files. first version of ripper had a bug because i didn't test it with DLC... some DLC str2_pc files had empty files and it caused some problems but textures should be OK. i fixed it maybe a few hours after i posted first post. btw, NVIDIA's DDS photoshop plugin is known to be shit, too many phoney disc errors and other errors etc. when irfanview and other applications load them just fine.
## Post #16
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-07-30T12:39:25+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Thanks for the headsup. I have used another application to re-rip the dds textures from the files and those dds textures loaded up fine in Photoshop tho. I got it from the SRTT Modding forums.

I will check out, if i can load the extracted dds textures from ripper with irfanview or something else.
## Post #17
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-30T14:04:54+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

That's strange. I don't have any problems with the textures in PS, they all work fine.
## Post #18
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-08-05T19:48:29+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

I've noticed that all the exported textures seem to be in a cubemap format . -They also do not load in photoshop for me, I get a disc error.


Though I have been able to convert them by noesis, which shows them correctly. (without the cubemap padding)



Also as you can see, a lot of textures have a messed up exposure - my guess is textures with an alpha map.
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-05T20:40:00+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

While I have the option for cubemaps available to set in my code, I don't use it for Saints Row Third. There are two very specific bitflags for cubemaps and I only use one of them (DDSCAPS_COMPLEX and DDSCAPS2_CUBEMAP). I generate valid DDS files; Irfanview loads them just fine... I too also have the photoshop problem with the disc error, but Rexil doesn't (that plugin is highly sensitive to the version/update of photoshop you are using, there was a time where it did work for me but one day it just stopped). And if you go to the Adobe forums they just tell you shit like oh reinstall blah blah blah use scandisk etc. lol. I have the latest updates for CS4. Next time, I am just going to pirate photoshop like everybody else to have it work properly lol.

However, the photoshop plugin is old, and in old versions of DDS, DDSCAPS_COMPLEX is equal to DDS_SURFACE_FLAGS_CUBEMAP. So photoshop might be treating DDSCAPS_COMPLEX to mean cubemap, which is wrong (DDSCAPS_COMPLEX means more than one surface); DDS specification says DDSCAPS_COMPLEX is required for mipmaps as well.

I'll look into the exposure thing, now that you mention it... actually I can't; I deleted the original texture files. For now try [scanti's texture extractor](http://www.saintsrowmods.com/forum/index.php?threads/sr3-texture-utilities.566/) on the problem files and let me know if they are different. They shouldn't, because shaundi's textures use the same format code as grace's and shaundi's is fine. However, if scanti's loads grace's textures fine let me know so I can check it out.
## Post #20
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-08-09T05:26:26+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Tried extracting with that other program - same weird exposure. The odd thing is, though that most other textures seem to extract fine though. And I didn't notice these gray exposure issues in the game itself.
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-09T19:32:02+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

You can try asking scanti over there since they are modders and might have noticed something. Lol my steam profile says I have played the game a whopping one hour and that ain't going to grow anytime soon ha ha ha.
## Post #22
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-14T02:52:48+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Woot! Finally a tutorial that can mod this shit. Although I am having an issue opening the .dds in photoshop, maybe because mine was from a source engine tutorial? Although it was from the nvidia website, might have to update that.

EDIT: hey if shaundi got lod why dont your char got it...
## Post #23
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-08-14T13:16:59+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

> Reply from soulslayerzx
>
> Woot! Finally a tutorial that can mod this shit. Although I am having an issue opening the .dds in photoshop, maybe because mine was from a source engine tutorial? Although it was from the nvidia website, might have to update that.

EDIT: hey if shaundi got lod why dont your char got it...
Why would you need a LOD of something you are constantly, like 100% of the time.
## Post #24
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-15T00:44:56+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

> Reply from rexil
>
> soulslayerzx wrote:Woot! Finally a tutorial that can mod this shit. Although I am having an issue opening the .dds in photoshop, maybe because mine was from a source engine tutorial? Although it was from the nvidia website, might have to update that.

EDIT: hey if shaundi got lod why dont your char got it...
Why would you need a LOD of something you are constantly, like 100% of the time.

My shaundi model has lod some reason, layers of stuff on her.

Also, my uv mapping is messed up maybe  cuz lwo import broke uv mapping but ill see what happens.
## Post #25
- Username: Voltarox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 15, 2012 8:35 am
- Post datetime: 2012-08-15T01:16:17+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

I thank you all for this very informative thread.  

I play SaintsRow3 and have always wanted to be able to work on some of the 3D models in that game.
You are making good progress on the SRTT ( Saints Row The Third ) 3D models and 
I appreciate the outstanding work you have accomplished.  

May I ask, ( sry if it may seem off topic ) if anyone has been able to extract and work with the 3D files for the VTOL ? ( Vertical Take Off & Landing aircraft from SRTT F-69 )

I have created/designed about 12 custom Air/Space craft vehicle 3D models using AC3D ( a 3D modeling program ) and would like to do some custom 3D work on the VTOL. ( redesigned landing gears and wing configurations )


Any advice would be appreciated.  

Thank you & keep up the good work.
## Post #26
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-15T02:14:14+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

> Reply from Voltarox
>
> I thank you all for this very informative thread.  

I play SaintsRow3 and have always wanted to be able to work on some of the 3D models in that game.
You are making good progress on the SRTT ( Saints Row The Third ) 3D models and 
I appreciate the outstanding work you have accomplished.  

May I ask, ( sry if it may seem off topic ) if anyone has been able to extract and work with the 3D files for the VTOL ? ( Vertical Take Off & Landing aircraft from SRTT F-69 )

I have created/designed about 12 custom Air/Space craft vehicle 3D models using AC3D ( a 3D modeling program ) and would like to do some custom 3D work on the VTOL. ( redesigned landing gears and wing configurations )


Any advice would be appreciated.  

Thank you & keep up the good work.

lol the dude said player models only as of now, i checked the cars and theres no .lwo or .obj when using rippper
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-15T16:06:48+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

i remember seeing one of the jets... do a search for all LWO files and sort them by file size and open the largest ones. i never textured the jet so i don't know if the uv coordinates are correct (some models had 4 sets of UV coordinates lol, i just took the first one in most cases).
## Post #28
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-15T19:35:02+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

> Reply from howfie
>
> i remember seeing one of the jets... do a search for all LWO files and sort them by file size and open the largest ones. i never textured the jet so i don't know if the uv coordinates are correct (some models had 4 sets of UV coordinates lol, i just took the first one in most cases).

So how did you get the uv map properly onto your model???? full process please, so im supposing you deleted the extra lods.
## Post #29
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-15T22:00:15+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Pm me a model with all textures. I ain't running that thing for another hour lol.
## Post #30
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-08-15T23:52:45+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

> Reply from howfie
>
> Pm me a model with all textures. I ain't running that thing for another hour lol.
Mine only took like 10 seconds extracting all the model files for the character, please see my thread in re-uv mapping Shaundi
## Post #31
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-11T09:03:47+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Thank you very much "howfie" for your help and tools.
## Post #32
- Username: crossfayt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 23, 2010 10:15 am
- Post datetime: 2012-11-16T21:09:01+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

I have been looking around all over and I am wondering if it's possible to get the textures to work in 3ds max.  I get as far as getting the model in, but once I try and apply a texture it comes out a single maroon like color.
## Post #33
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2013-07-09T01:30:13+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Dude. Does anyone know how to extract characters properly from the game. 

I can extract the models and textures, but the uv mapping is f***ed up and it just spams the texture all over the model 

Someone please help.
## Post #34
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-06-11T04:32:10+00:00
- Post Title: Re: [PC] Saints Row Third: Character Models

Any chance of updating this to support the remaster now?
