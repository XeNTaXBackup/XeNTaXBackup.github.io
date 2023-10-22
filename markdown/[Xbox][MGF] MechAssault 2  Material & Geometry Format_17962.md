## Post #1
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-11T17:08:22+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

MechAssault 2: Lone Wolf for Xbox, Material & Geometry Format (.mgf)

This format has been broken down to enable mesh & texture extraction.   I have compiled available resources & tutorials into one download.  Noesis, Hex2Obj, QuickBMS not included.

Mech Wolf (1.0):  [http://www.mediafire.com/file/0765kr4zj ... f_V1.0.zip](http://www.mediafire.com/file/0765kr4zj8y74n8/Mech_Wolf_V1.0.zip)

Many, many, many, many Thanks to AceWell, akderebur & shakotay2 for their help in breaking down this format. 


Original Post

I'm hoping with the near release of BattleTech, perhaps someone has a place in their heart for MechWarrior models or something.  Or at least could for the love of extraction please help?  

Shakotay, AceWell, chrrox, anyone?  I've been trying for years to get help on this without success.  As always, I'm willing to write whatever script need be to translate stuff to a more useable format, but I'm not skilled enough to know how to break everything down without at least being pointed in the correct direction.  I'm willing to compensate, games,  gift card, etc if there's anyway that knowledge can lead to Blender scripts, a Noesis plugin or even access through Hex2Obj.  

Here's a script I wrote to provide the initial offset values and locations of some datablocks, but that is still a far cry from sufficient.  

[https://www.mediafire.com/file/x0tu8bl2 ... a_V0.5.zip](https://www.mediafire.com/file/x0tu8bl2uvd20vo/MGF_Meta_V0.5.zip)

File Samples: [https://www.mediafire.com/file/zc2m2cd2 ... _Files.zip](https://www.mediafire.com/file/zc2m2cd2990j4hk/Unpacked_Files.zip)

I figure there is one of two ways to possibly tackle this.  The traditional method of reversing it.  Here's the documentation on the MGF Format

[https://www.mediafire.com/file/n9js8khw ... ources.zip](https://www.mediafire.com/file/n9js8khw4qifbx8/MGF+Resources.zip)

As best I can tell stuff is stored in a tree format.  I've worked with trees & iterables, but not from a hex stand point, so I would still need help with the pattern before creating something recursive to parse it.  

The other method might be to make use of the parsers that were already made.  I don't work with C, so I don't know the first thing about identifying what's needed for compiling purposes.  But if someone thinks that is possible, there is a capability of converting to Radiance, also something that I don't know anything about, but perhaps that would negate the manual processes if capable of converting to something more easily imported.

[https://www.mediafire.com/file/n16kouor ... gflib2.zip](https://www.mediafire.com/file/n16kouorqrbymr1/mgflib2.zip)

Thank you so much to anyone in advance, who can help.  I've really been wanting some of MechAssault 2's characters for some art projects, that I've never been able to realize due to missing the models from it.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-11T20:19:44+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

I can give some examples in hex2obj. Here are two meshes I got from "00000614_3dlobby.mgf".




I actually don't know what kind of 3d models to expect from these files but the meshes appear to somewhat sensible. So I think I got them right.

I used "idxbin" and "vertbin" keywords to locate the index and vertex data quickly. You can probably locate them fine with your data block scripts. It seems like vertex data comes before the index data. If you find the indices, the vertex data for them is right above the indices. 

Vertex blocks appear to be 20 bytes for all the meshes. Float seems correct for the vertex positions. I haven't checked the uvs.

I don't know if you already knew this stuff, but I hope it helps you with your research. Unfortunately I don't have the time to dig deeper and mechas aren't my cup of tea really  Good luck.
## Post #3
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-11T20:45:47+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

@akderebur  !!!!!!

That's friggn' incredible! Thank you! That's essentially half the battle right there, and I wasn't even expecting that so quick.  No, it's all new info to me, so I should be able to patch some stuff together so I can process the values like I have done with other scripts.  I did a test and changed the UV Pos to 16 and changed Float to HF_UV, it appears to be look like reasonable UV's, so I'm really hoping that's true once I get a chance to export a couple.



If that's your limit, it's already much appreciated.  I'm after the human characters anyway, lol.  If I may ask one more thing, would you have any tips for me to locate the images?  I know their names are squashed together, and it appears that most of them are tifs, but I have not successfully figured out where their data starts or their lengths.  If not, I can hopefully find another brain to pique, but this will give me plenty to dissect for the moment.  I'll drop ya a PM later to see if there's any boon I can throw your way.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-11T21:21:58+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

I will go to sleep now, but I can give it a try tomorrow. I am still not very good with identifying image data in hex though.

I think AceWell will take a look at the files when he sees this thread  He might be able to get those images.
## Post #5
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-12T02:21:40+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

Sounds like a plan.  I've run out of day time too, but I at least got the script updated the to export a list of vertbin & idxbin locations.  It's not the exact positions shown in your examples, but I'll adjust that on the next pass.  

[http://www.mediafire.com/file/sauvsvlfy ... a_V1.1.zip](http://www.mediafire.com/file/sauvsvlfy9gx214/MGF_Meta_V1.1.zip)

Edit: 
Ok, not quite done for the night yet, lol.  I updated the script again now to put index data first and give the vertex & index counts. 

I've also found a few items that have an FVF of 24, no biggie there.  BUT it looks like some of the character models are different.  In the 3D lobby file the characters are toward the end of the list and range in 1000-2000+ Verts.  Looks like some low poly models use FVF 36, but may not have UV's.  Looks like higher poly character parts use FVF 56....

>> Bingo!! This is part of one of the pilots I was looking for.  





Edit 2: Just some notes if of interest.  It looks like  there is an 'MGI' before a lot of the 'PIC' blocks.  I think the image length is 0x08 bytes from PIC, and I think the actual data starts 0x72 from PIC (just guesses of course).  There are some parameters for height, width, mips, etc before the data starts, so hopefully that can help with constructing the header properly to pair it up with the data.  As soon as I get a chance, I'll start updating the script to list PIC locations and stats, until I can jump straight to dumping the full image.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-12T14:19:05+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

about the mgf format: the samples you've provided are binary but the format specs (mgfdoc.pdf) are about ASCII mgf ("human-readable ASCII text"); so is the sample in the mgflib-project, examp1-mgf:

```
v    vc1+ =
	p   24 3.0625 -1.75
	n 0           0       -2
v    vc2+ =
...

```


there's xml blocks in the binary mgf files but they are different from the above:

```
<material_specular_mask version="1" name="sky_planet mat" diffuse="255, 255, 255" selfillum="55, 55, 55" shininess="4.00000000" shin_strength="0.20000000" spec_color="237, 167, 57" opacity="1.00000000" two_sided="false" shading="gouraud" blending="normal" specular_bloom="0.20000000">
...

```
## Post #7
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-12T15:47:25+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

@shakotay,

If the documentation itself is not that useful, it's okay.  When I was struggling to get assistance with this a while back, it was all I could even find on the format.  Like with any engine, I would assume that the developer could have re-purposed the container.  Day One Studios didn't exactly make all the much anyway, so who knows their logic in choosing a non-standard format.  I was just trying to be useful do what I could while arm twisting for support back in the day, lol.  

Since the meshes & uv's are proving to be a reality, it would seem that the skeletons may be the useful thing to dissect out of there if it lined up in anyway.  But beyond images at this point, please disregard that unless it's for a personal curiosity.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-12T16:35:49+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

> Reply from Protocol X27
>
> Looks like some low poly models use FVF 36, but may not have UV's.  Looks like higher poly character parts use FVF 56....
Yea, my bad. I said all meshes have 20 bytes for vertex blocks but clearly I haven't checked enough meshes 

Anyway I did take a look at the vertex blocks for that pilot you posted and it seems like starting from offset 36 (in 56 bytes vertex block) is related to skinning. First 4 bytes are bone ids, so 1 byte for each bone id. The remaining 16 bytes in the block are 4 floats, and they are the weights.

I tried to mark those sections I mentioned. Decided to show it on the second vertex block since it has 2 bones. Sorry for my bad image editing skills.
## Post #9
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-12T22:34:27+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

@akderebur

No worries, I know that info during research is a work in progress  and images don't need to be complicated to get the point across. That's how I do those too.  Thanks for posting that.  I'm lacking in know how to get the skeleton or even how to get one working through Noesis or Blender, so I would need a crash course in the department to put the weight data to use.   

Here's a script update.  I added an Image Meta exporter including Height, Width, Offsets & Length.  I started on a process that can merge the image data with an existing TIFF placeholder since I don't know how to write TIFF headers/footers.  It's a sloppy way to do it, and it's not in complete working order yet.  I'll need help with remaining image stuff since I don't know how the mips, depth or bits could affect the file size.  :-/    As a side note, I added some padding to make the Mesh meta exporter easier to read too. 

[http://www.mediafire.com/file/qj9styn59 ... a_V1.2.zip](http://www.mediafire.com/file/qj9styn59r1w4qm/Mech_Meta_V1.2.zip)
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-12T22:45:03+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

here is bms script to extract the files with names from your mgf samples  

```

idstring "mgf "
get FOLDER basename
get UNK long
get ZERO long
get TABLE1_ENTRIES long
get TABLE1_SIZE long
get TABLE1_OFFSET long
get TABLE2_ENTRIES long
get TABLE2_SIZE long
get TABLE2_OFFSET long
get STR_TABLE_SIZE long
get STR_TABLE_OFFSET long
goto 0x14 0 seek_cur
for i = 1 to TABLE1_ENTRIES
    get UNK2 long
    get UNK3 longlong
    get SIZE[i] long
    get SIZE2 long
    get UNK4 long
    get OFFSET[i] long
    get UNK5 long
next i
for i = 1 to TABLE1_ENTRIES
    get CHECK long
    if CHECK == 0
        get UNK6 long
        get UNK7 long
        get UNK8 long
        get STR_OFFSET long
        xmath NAME_OFFSET "STR_TABLE_OFFSET + STR_OFFSET" 
        get UNK9 long
        savepos TMP
        goto NAME_OFFSET
        get NAME string
        string NAME p "%s\%s" FOLDER NAME
        log NAME OFFSET[i] SIZE[i]
        goto TMP
    else //skipping unique folders
        goto 0x14 0 seek_cur
        math i - 1
    endif
next i
```
## Post #11
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-12T22:59:21+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

@AceWell !!! Incredible, that's killer!    That's going to help pare down all the extra meshes that I'm looking for.  

Works like a champ.  I did try opening the tif files after using the script, and it looks like their custom meta information is still packaged with it so Photoshop/GIMP won't recognize them.  Any ideas how I could translate 'em properly?
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-13T13:32:55+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

yep that is the next step, had to sort the files first, and also never trust extensions,  
the "tif" files have the best header i think i've seen though, tells you everything.
## Post #13
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-13T19:33:25+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

Awesome, didn't know you already had a plan.  If so, I'll patiently await your intel.   

That sounds like good advice, I guess it's something learned along that way that I hadn't encountered enough yet.  I agree that it is nice to have those values available.  So with tinkering trying to better understand the format, I can't make sense of the sizes in comparison to the dimensions.  I was testing a 512 x 512 image and the size provided seemed smaller than if it were the normal RGBA quantity of bytes for an image of the same size.  Even without bytes for alpha channel, I couldn't make it line up, so I'm sure there's more to it than my limited knowledge.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-16T19:13:36+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

I've made some research concerning the submesh alignment of Natalia.

In the xml file Nat_PilotHairDown_Cinema.MGMODEL there's positions of head and root (assumed: transform4)

layer15
<bone name="bone_head" transform1="0.00000298 -1.00000024 0.00003227 0.00000000" transform2="-1.00000000 -0.00000313 0.00000075 0.00000000" transform3="-0.00000073 -0.00003230 -1.00000012 0.00000000" transform4="-0.08515804 0.07527932 0.04588023 1.00000000"/>
<bone name="bone_root" transform1="1.00000000 0.00000000 0.00000000 0.00000000" transform2="0.00000000 1.00000000 0.00000000 0.00000000" transform3="0.00000000 0.00000000 1.00000000 0.00000000" transform4="-0.07527588 0.56100762 -0.09257832 1.00000000"/>

The idea is to build the difference for the vertical axis for example then move the head in blender vertically 'til the same difference is met.

Sadly it didn't work as expected: the difference of the transforms is 0.561 -0.0753 = 0.4857 while in blender it's 0.454 (see picture, 0.28176 + 0.17216 = 0.45392).
Maybe bone_root position is different from the body position?

Maybe some other layer lines to be used or this line
<node_skinned version="1" name="nat_pilot_body" position="0.00001215, 0.20967650, 0.05826531" rot_axis="-1.00000000, 0.00000000, 0.00000000" rot_angle="0.00000000" scale="1.00000000, 1.00000000, 1.00000000" turned_on="true" collidable="true" bounds_cover_children="false" max_normal_mapped_lights="255">

but I couldn't find a suiting line with  _head" position="



Nat_PilotHairDown_Cinema-MGMODEL.jpg (170.66 KiB) Viewed 209 times



btw: using WordUV instead of HF_UV gives better results
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-16T22:29:55+00:00
- Post Title: [Xbox][MGF] MechAssault 2 / Material & Geometry Format

here is first draft of Noesis python script to open the tif texture samples  


 tex_MechAssault2_tif.zip
(811 Bytes) Downloaded 25 times


supports dxt1, dxt3, dxt5, morton swizzled rgba8888
it opens about 90 percent of the samples, there is still a couple
swizzled formats that i have not worked out yet but they are usually 
effect or UI textures, the main ones you need should be handled.   
i will update the script when i figure the rest out.
## Post #16
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-17T00:49:23+00:00
- Post Title: Re: [MGF] Material & Geometry Format

Wow, wow, wow! I only have so many words to express: 'You Guys are Amazing!'  I really appreciate having this thing cracked after soooooo long. 

@shakotay,
Hmmm, it wouldn't be the first time I've seen Blender have alternate scaling even when using exact game scale values, so thank you for at least making an attempt on that.  I'm glad you caught the WordUV change.  I was thinking the UV's were looking a bit sharp, so I'm glad that's resolved now before I really start working on exporting even more obj's.  That would have been frustrating to manually adjust all of those. Thanks! 

@AceWell,
Amazing work.  Definitely correct, that tackles most of them, definitely the body & face textures are covered.  As I move further along I will see what some of the mech & stage textures look like.  I did notice that a couple hair textures fell into the swizzle category, so perhaps when you do circle back you could include these in your testing.  NAT_hair01 & NAT_hair01.spclr. (in cinema_1_1a.mgf)   Totally not a deal breaker since I was already planning to use some better high res textures in that department anyway, but it will be nice to have them as an option down the road.  

      

Just did a quick Blender test! Now the fun begins of modernizing.
## Post #17
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-21T15:57:21+00:00
- Post Title: Re: [MGF] Material & Geometry Format

I updated the first post with a tutorial and a streamed down utility now that it does not need my partial image & meta functions.  I know you guys are community champs and not prone to receive anything for your efforts, but if you change your mind please PM me.  At least to do my part and help anyone else ever interested, I compiled a tutorial & resources for everything done so far.  

[http://www.mediafire.com/file/0765kr4zj ... f_V1.0.zip](http://www.mediafire.com/file/0765kr4zj8y74n8/Mech_Wolf_V1.0.zip)

I updated the first post as well. If anything is unclear or buggy, please let me know. 

At least to show the effort was not in vain and going to use.  Here's an implementation of using some of the assets (Left: My conversion, Right: Render from Marketing).  After looking through the files and partially replaying the game it would seem Microsoft used some assets to promote the game that were not actually included in the data.  At least if they were, my inspection was not thorough enough to find any dormant files.  Still the journey was sufficient since having original assets in part is important for this conversion and other models I intend to work on eventually as well.
## Post #18
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-04-22T09:36:24+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from Protocol X27
>
> Wow, wow, wow! I only have so many words to express: 'You Guys are Amazing!'  I really appreciate having this thing cracked after soooooo long. 

@shakotay,
Hmmm, it wouldn't be the first time I've seen Blender have alternate scaling even when using exact game scale values, so thank you for at least making an attempt on that.  I'm glad you caught the WordUV change.  I was thinking the UV's were looking a bit sharp, so I'm glad that's resolved now before I really start working on exporting even more obj's.  That would have been frustrating to manually adjust all of those. Thanks! 

@AceWell,
Amazing work.  Definitely correct, that tackles most of them, definitely the body & face textures are covered.  As I move further along I will see what some of the mech & stage textures look like.  I did notice that a couple hair textures fell into the swizzle category, so perhaps when you do circle back you could include these in your testing.  NAT_hair01 & NAT_hair01.spclr. (in cinema_1_1a.mgf)   Totally not a deal breaker since I was already planning to use some better high res textures in that department anyway, but it will be nice to have them as an option down the road.  

      

Just did a quick Blender test! Now the fun begins of modernizing.

Wow! Great job! I really hope you can upload a pack containing all models and textures in .obj and .png form or any workable format! Keep it up!
## Post #19
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-04-22T16:53:22+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from Pepsee
>
> 
Wow! Great job! I really hope you can upload a pack containing all models and textures in .obj and .png form or any workable format! Keep it up!

Thanks!  That's a rather tall order considering just how many models are included in 'all'.  Even hair meshes are broken into a ton of parts, so that would take a ton of time not well spent.  In my recent link I posted a walkthrough of how to get the meshes, so by using that it's fair game to extract any meshes available.  The script that AceWell wrote is highly useful for finding specific files.  

I don't mind helping narrow done some factors once you take a shot at which files you're looking for.  The samples I posted already have all of the multiplayer characters and some of cinematic characters.
## Post #20
- Username: Trent24
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 13, 2019 10:55 am
- Post datetime: 2019-05-13T03:30:27+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from Protocol X27 ↑Sat Apr 21, 2018 11:57 pm at Sat Apr 21, 2018 11:57 pm
>
> 
I updated the first post with a tutorial and a streamed down utility now that it does not need my partial image & meta functions.  I know you guys are community champs and not prone to receive anything for your efforts, but if you change your mind please PM me.  At least to do my part and help anyone else ever interested, I compiled a tutorial & resources for everything done so far.  

http://www.mediafire.com/file/0765kr4zj ... f_V1.0.zip

I updated the first post as well. If anything is unclear or buggy, please let me know. 

At least to show the effort was not in vain and going to use.  Here's an implementation of using some of the assets (Left: My conversion, Right: Render from Marketing).  After looking through the files and partially replaying the game it would seem Microsoft used some assets to promote the game that were not actually included in the data.  At least if they were, my inspection was not thorough enough to find any dormant files.  Still the journey was sufficient since having original assets in part is important for this conversion and other models I intend to work on eventually as well.

We're going to have to be doing model by model in hex2obj ??

Is there a faster way to obtain the models?

By the way, excellent work that you have done.

sorry for my english
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-21T13:09:49+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from Trent24 ↑Mon May 13, 2019 11:30 am at Mon May 13, 2019 11:30 am
>
> We're going to have to be doing model by model in hex2obj ??No. hex2obj is just a helpertool for getting/understanding the first submesh(es).

> Is there a faster way to obtain the models?Sooner or later (using the Make_obj project). Just checking some mgf files with about 1000 static submeshes.
Other than with the character meshes (FVFsize of 56 and an UVpos of 32) the buildings usually have 20/16 or 24/20 with weird uvs so far:
.



cinema_10_uvs_static_meshes.jpg (180.21 KiB) Viewed 107 times
## Post #22
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2020-01-09T01:38:23+00:00
- Post Title: Re: [MGF] Material & Geometry Format

@shakotay
Thanks for tackling his questions and adding some new tidbits.  It'd been so long without activity that I wasn't sure if it was to resurrect a dead topic, XD

So is the 'Make_obj' that you're referring to something that you're working on?  

I got a bit burnt out working on some of the vehicles that I still need to revisit.  The other tough aspect was that the trying to match up any buildings with textures since there are so many, and the names are obscure.  :O
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-09T08:09:10+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from Protocol X27 ↑Thu Jan 09, 2020 9:38 am at Thu Jan 09, 2020 9:38 am
>
> So is the 'Make_obj' that you're referring to something that you're working on?From time to time, when I have new "ideas" (uvs are still weird).
Here's a link to it (ignore the ".efo", there's a ".mgf" version contained in the appended zip):

> Reply from shakotay2 ↑Wed Jan 08, 2020 11:24 pm at Wed Jan 08, 2020 11:24 pm
>
> 
(some H2O files need a correction, for example 00000968_cinema_1_1a_507.H2O requires a switch to noStrip)
## Post #24
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2020-01-18T15:51:07+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from shakotay2 ↑Thu Jan 09, 2020 4:09 pm at Thu Jan 09, 2020 4:09 pm
>
> 
Here's a link to it (ignore the ".efo", there's a ".mgf" version contained in the appended zip):
Apologies if I'm missing something obvious.  Do you mean one of the links in your signature?
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-18T17:08:35+00:00
- Post Title: Re: [MGF] Material & Geometry Format

nope (Make_obj-efo.zip).
[download/file.php?id=17313](https://forum.xentax.com/download/file.php?id=17313)
## Post #26
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2020-02-12T01:46:43+00:00
- Post Title: Re: [MGF] Material & Geometry Format

> Reply from shakotay2 ↑Sun Jan 19, 2020 1:08 am at Sun Jan 19, 2020 1:08 am
>
> 
nope (Make_obj-efo.zip).
download/file.php?id=17313

Thanks, This looks intriguing. Have to dust off the cobwebs and experiment with this.
## Post #27
- Username: Amity astray
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 12, 2020 1:19 am
- Post datetime: 2020-11-11T17:21:24+00:00
- Post Title: Re: [MGF] Material & Geometry Format

Is anyone still working on opening the game files?
