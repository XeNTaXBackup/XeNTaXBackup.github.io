## Post #1
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-05T01:10:32+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

Hey all, figured I'd ask here for some advice. I've been trying to edit the 3D models used in Star Trek Online. I have access to the .mset files and I'm trying to see how to swap them around. Doing a simple rename and replace leads to the game loading invisible meshes. This tells me that I need to do something within the .mset file itself. I remember seeing on a different forum that another (now inactive) user stated he had figured out model swapping because of the headers he saw during hex editing these files. So far, every attempt I've made leads to crashes on load.

I've attached a few different .mset files in the zip folder. The two Fed_D_Phaser files should be the same 3D model (though with potentially different materials) as the output from an .mset converter is the same. The other two are different. I'm trying to figure out how to ultimately swap around these and other models in game.

Anyone think they can see something I'm missing? I appreciate any help or advice!


 STOMSETS.zip
The two Fed_D_Phasers output the same model. The other two are different models of different qualities. I'd like to swap them all around. (199.59 KiB) Downloaded 20 times
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-06T16:44:25+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

Here's the overall layout of the format based on some rough analysis:

```
long	Files1SigOffset
// big endian below
long	unknown // always 0xD?
long	Magic // 0x08EBE869
word	unkCnt // 0x0001
word	filenameLength
char	filename[filenameLength]
word	unkCnt // 0x0001

long	zipData1Address
long	zipData1Size
long	zipData2Address
long	zipData2Size
long	chunk2Size // zipData2 + tail

// little endian below
word	Files1StringLength // 0x6
char	Files1String[Files1StringLength] // "Files1"
long	headerSize
byte	header[headerSize]
{
	// begin of header
	long	referencedAssetCount
	for i = 0 < referencedAssetCount
	{
		word	assetPathLength
		char	assetPath[assetPathLength]
		byte	alignment[?] // alignment of 4 bytes from `assetPathLength`
		long	unknownCRC
	}
	// end of header, where the absolute address == zipData1Address
}

// big endian below
byte	chunk1[zipData1Size]
{
	// begin of chunk1
	long	stringRelativeAddress // from the location of this variable
	long	unkField1
	long	unkField2
	long	unkCount
	float	unkField3
	long	Null
	long	unkCount2
	long	Null
	for i = 0 < 15
	{
		long	zlibStreamSize
		long	unzipSize // could be negative values, actual size = abs(unzipSize)
		long	zlibStreamAddress // relative from zipData1Address
	}
	byte	Null[4]
	long	unknownCRC2 // 0x86D846FF
	for i = 0 < unkCount
	{
		word	idx
		word	Null
		long	subCount // sum == unkField2
	}
	for i = 0 < 15
	{
		byte	zlibStream[zlibStreamSize]
	}
	// relative address from `stringRelativeAddress` is `stringRelativeAddress`
	word	stringCount
	for i = 0 < stringCount
	{
		word	stringLength
		char	string[stringLength]
	}
	
	// end of chunk1
}

// begin of chunk2
byte	chunk2[zipData2Size] // zlib stream
// end of chunk2
long	zlibStreamSize // == zipData2Size
long	unzipSize
word	unkCount // same as previous
long	unknownCRC2 // 0x86D846FF
for i = 0 < unkCount
{
	word	idx
	word	Null
	long	subCount // sum == unkField2
}
for i = 0 < stringCount
{
	word	stringLength
	char	string[stringLength]
}

```


As you can see there're some fields or strings of which you can't determine their actual use with static analysis and there're a lot of validations required. But for the minimal modification you should edit at least the recorded filename, the referenced file paths (if there actually are any *.Geo or *.Lodinfo files), and all the absolute addresses that're affected.
## Post #3
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-06T18:53:53+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

Thanks for the help! 

This data definitely clears up some of what I was doing. I had managed to replace the data within the .msets to a point where the game no longer crashed, but it still loaded invisible files (and the .mset converter would lock up upon reading the edited file, meaning some value I changed broke the readbility of the file).

I was wondering if I could ask you a couple more questions:

The first is if you'd be willing to take a look at a few more files. I found a mod someone had made for Neverwinter Online, which uses a .mset as well. I've included the original files extracted from the game (labeled as "1-F_Body_Cloth_Wight_Orig_02.mset", and "2-F_Neck_Scarf_01.mset") and the modified file ("3-F_Body_Cloth_Wight_Orig_02.mset"). It looks like they replaced the data within the original file with the second file, but I noticed that some aspects had been changed when I compared the data. I was wondering if those can shed light on exactly which offsets allow for the mesh swapping.


 MSETS2.zip
(24.84 KiB) Downloaded 16 times



My other question is on what tools/toolsets you recommend for trying to work this out. I've been using HxD to read and edit the files, and then a .mset converter and the game itself to test for any progress. Is there a tool that would allow me to organize the data better/in a more readable format than HxD? 

Thanks again!
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-07T10:09:20+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Jff007 ↑Thu Oct 07, 2021 2:53 am at Thu Oct 07, 2021 2:53 am
>
> I found a mod someone had made for Neverwinter Online ... It looks like they replaced the data within the original file with the second file, but I noticed that some aspects had been changed when I compared the data. I was wondering if those can shed light on exactly which offsets allow for the mesh swapping.
From what I can see, the main difference between "2-F_Neck_Scarf_01.mset" and "3-F_Body_Cloth_Wight_Orig_02.mset", is that in the latter file, the last zlib data block is changed, which's not the actual geometry data, something related to face materials perhaps. It also changed the signature at address 8 (original is 0x08EBE869 in known samples), and removed the one ahead of the first zlib block (0x86D846FF). But the strings weren't changed a bit. So if this mod ever worked, the filename or the recorded string should be irrelevant to the replacement.

> Reply from Jff007 ↑Thu Oct 07, 2021 2:53 am at Thu Oct 07, 2021 2:53 am
>
> 
My other question is on what tools/toolsets you recommend for trying to work this out. I've been using HxD to read and edit the files, and then a .mset converter and the game itself to test for any progress. Is there a tool that would allow me to organize the data better/in a more readable format than HxD?
Creating a template for the format with your hex editor, if it supports such feature, will make it easier to loacte the variables you want to address and validate that if your modification meets with the known specification. But still you'll have do most of the replacements and calculations manually. An automatic script (or whatever programs for such treatment) might be a better solution, the premise of which, however, is based on the fact that you've figured out how to do it manually.
## Post #5
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-08T01:01:28+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Bigchillghost ↑Thu Oct 07, 2021 6:09 pm at Thu Oct 07, 2021 6:09 pm
>
> 
From what I can see, the main difference between "2-F_Neck_Scarf_01.mset" and "3-F_Body_Cloth_Wight_Orig_02.mset", is that in the latter file, the last zlib data block is changed, which's not the actual geometry data, something related to face materials perhaps. It also changed the signature at address 8 (original is 0x08EBE869 in known samples), and removed the one ahead of the first zlib block (0x86D846FF). But the strings weren't changed a bit. So if this mod ever worked, the filename or the recorded string should be irrelevant to the replacement.

Thanks for the analysis on those! I think the modified file had been made about six years ago; in the time since then, Cryptic updated their games' infrastructure a bit, so that file may have worked back then, but maybe won't any more.

> Reply from Bigchillghost ↑Thu Oct 07, 2021 6:09 pm at Thu Oct 07, 2021 6:09 pm
>
> 
Creating a template for the format with your hex editor, if it supports such feature, will make it easier to loacte the variables you want to address and validate that if your modification meets with the known specification. But still you'll have do most of the replacements and calculations manually. An automatic script (or whatever programs for such treatment) might be a better solution, the premise of which, however, is based on the fact that you've figured out how to do it manually.

Unfortunately, I haven't seen a template option with HxD, but I'm already looking into alternatives. I remember using one with templates years ago, but can't remember the name now. Maybe once I get this figured out, I can try my hand at a script to simplify this process for future users.

Thanks again for all your help! I'll have time to test all this out and try to figure it out this upcoming weekend, so I'll probably update here if I have any questions or if I get it to work.
## Post #6
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-09T19:09:14+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

Just to give an update: I've had no luck so far. In a somewhat embarassing way, I realized that I've essentially forgotten most of what I used to know regarding how to parse data and create the templates necessary to make this work easier. Oof. Every attempt I've made at creating a template has led to syntax errors, unfortunately. So, for now, unless someone wants to throw some of their experience into cracking this puzzle, I'll keep trying to go through the hex editors without a template.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-10T06:42:55+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Jff007 ↑Sun Oct 10, 2021 3:09 am at Sun Oct 10, 2021 3:09 am
>
> 
Every attempt I've made at creating a template has led to syntax errors, unfortunately.
Which editor did you use?

Here's a format template created with HexEdit as a start:


 _mset.zip
Updated 2021.10.11 (1.27 KiB) Downloaded 16 times



Check the link in this post to get the latest version of the mentioned editor:
[viewtopic.php?p=139002#p139002](viewtopic.php?p=139002#p139002)

You can create a new empty template first and save it to reveal the location of the templates folder. Then place the mset template in it and restart HexEdit to get it work. Beware NOT to use it on that mod sample you provided coz it'll crash the program.
## Post #8
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-10T16:48:07+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Bigchillghost ↑Sun Oct 10, 2021 2:42 pm at Sun Oct 10, 2021 2:42 pm
>
> 
Which editor did you use?

I remembered I had access to 010 Editor, so I tried that one initially.

> Reply from Bigchillghost ↑Sun Oct 10, 2021 2:42 pm at Sun Oct 10, 2021 2:42 pm
>
> 
Here's a format template created with HexEdit as a start:
...
You can create a new empty template first and save it to reveal the location of the templates folder. Then place the mset template in it and restart HexEdit to get it work. Beware NOT to use it on that mod sample you provided coz it'll crash the program.

So, that template worked for most of the files, but it crashes on a few of them, giving an error of "unexpected EOF". I've attached the mentioned files. I'm guessing that every file smaller than 14 KB reaches an unexpected end with the template, as the Pistol_10.mset file was the only one in the file I've attached that works.


 MSETS3.zip
(82.36 KiB) Downloaded 22 times



Anyway, thank you for the help! Your template allowed me to see where my snytax was off. I'll definitely have to give myself a refresher after (or maybe even during) this project.
## Post #9
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2021-10-10T19:15:40+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

I don't see any information for materials or textures.  Is there something in the .mset file that tells what the model uses, or is this information found elsewhere?
## Post #10
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-11T06:06:47+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from roswell ↑Mon Oct 11, 2021 3:15 am at Mon Oct 11, 2021 3:15 am
>
> 
I don't see any information for materials or textures.  Is there something in the .mset file that tells what the model uses, or is this information found elsewhere?

From what the mset export/convert program states, there's .mtl data within the .mset, but I haven't identified it yet.
The textures themselves are in the texture.hogg files, though they're a strange combo of .wtex and .htex files--looks like htex is higher resolution, while wtex is lower. Some have extra ones with the suffix "nx" (normals) while others don't. Some have files which are labeled "s" (probably specular maps), while others are missing them. I'm trying to figure out what the "c" suffix is as well. Some use "l" files (lighting, probably), while others use "e" (emissives). Some have "r" suffixes (reflections) while others don't. It's a huge mess.

So far, model swaps have still been unsuccessful. I've even tried some ship swaps (boy is that section of the files a mess), to see if I could figure it out there. No luck. I feel like I'm missing something obvious, but I'm not sure what. I know the client loads the loose files, as they appear as invisible meshes when loaded up, but that means something is zeroing out the mesh data.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-11T14:41:25+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Jff007 ↑Mon Oct 11, 2021 12:48 am at Mon Oct 11, 2021 12:48 am
>
> 
So, that template worked for most of the files, but it crashes on a few of them, giving an error of "unexpected EOF".
These samples contain uncompressed data chunks where the recorded data sizes are zeros. Template is updated at the same post.
## Post #12
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2021-10-12T16:49:25+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Jff007 ↑Mon Oct 11, 2021 2:06 pm at Mon Oct 11, 2021 2:06 pm
>
> 
From what the mset export/convert program states, there's .mtl data within the .mset, but I haven't identified it yet.

Ok, but, the texture filename isn't stored in the .mset file.  So, if there's just a material index stored, what does that index reference?
Is there a master listfile of texture filenames somewhere?

According to the MSET decompiler source code, each mesh object has 12 predefined zlib streams.  There is a zlib stream for material indices (index 9), but I don't understand why they're listed per vertex, instead of per face.  Source code calls them "bone materials", but it looks like they never figured out how to use them:

```
                var mz_verts =    mzm[i, 1];
                var mz_norms =    mzm[i, 2];
                var mz_binorms =  mzm[i, 3];
                var mz_tangents = mzm[i, 4];
                var mz_sts =      mzm[i, 5];
                var mz_sts3 =     mzm[i, 6];
                var mz_colors =   mzm[i, 7];
                //var mz_weights =  mzm[i, 8];
                //var mz_matidxs =  mzm[i, 9];
                var mz_verts2 =   mzm[i, 10];
                var mz_norms2 =   mzm[i, 11];

                int fc = file.Models[mz_tris.Model].FaceCount;
                var vc = file.Models[mz_tris.Model].VertexCount;

                // ...
                var l_tris =     mz_tris.DataProcessed != null ? new ThreeDFace[fc] : null;
                var l_verts =    mz_verts.DataProcessed != null ? new ThreeDVertex[vc] : null;
                var l_norms =    mz_norms.DataProcessed != null ? new ThreeDNormal[vc] : null;
                var l_binorms =  mz_binorms.DataProcessed != null ? new ThreeDBinormal[vc] : null;
                var l_tangents = mz_tangents.DataProcessed != null ? new ThreeDTangent[vc] : null;
                var l_sts =      mz_sts.DataProcessed != null ? new ThreeDTextureCoordinate[vc] : null;
                var l_sts3 =     mz_sts3.DataProcessed != null ? new ThreeDTextureCoordinate[vc] : null;
                var l_colors =   mz_colors.DataProcessed != null ? new ThreeDColor[vc] : null;

                //var l_weights =  mz_matidxs.DataProcessed != null ? new ThreeDBoneWeight[] : null;
                //var l_matidxs =  mz_weights.DataProcessed != null ? new ThreeDBoneMaterials[] : null;

                var l_verts2 =   mz_verts2.DataProcessed != null ? new ThreeDVertex[vc] : null;
                var l_norms2 =   mz_norms2.DataProcessed != null ? new ThreeDNormal[vc] : null;

```
## Post #13
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-13T00:56:15+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from Bigchillghost ↑Mon Oct 11, 2021 10:41 pm at Mon Oct 11, 2021 10:41 pm
>
> 
These samples contain uncompressed data chunks where the recorded data sizes are zeros. Template is updated at the same post.

Thanks for the updated template! It works flawlessly on everything I've tried.

> Reply from roswell ↑Wed Oct 13, 2021 12:49 am at Wed Oct 13, 2021 12:49 am
>
> 
Ok, but, the texture filename isn't stored in the .mset file.  So, if there's just a material index stored, what does that index reference?
Is there a master listfile of texture filenames somewhere?

According to the MSET decompiler source code, each mesh object has 12 predefined zlib streams.  There is a zlib stream for material indices (index 9), but I don't understand why they're listed per vertex, instead of per face.  Source code calls them "bone materials", but it looks like they never figured out how to use them:

This is where all I can do is agree with you. I've not seen any master list anywhere (Yet). I know they tend to reuse a *lot* of files for various things, so I could be looking for dozens of files or just one.

In good news/bad news fashion I have an update though.

Good news: texture swapping works. I swapped the textures of two identical mesh sets around (the fleet phasers and the mirror universe fleet phasers). All I did was rename the .wtex files and the folder they were in for the swap. It loaded right, and the textures were different, though not full "swaps" per-se. For reference, the fleet phasers are blue, light grey, and dark grey, while the mirror phasers are red, medium grey, and dark grey. The swapped textures loaded the fleet phasers as medium grey and dark grey with no blue or red accents, while the mirror phasers went from predominently medium grey to predominently red. Interesting results, but promising since it confirms that texture swapping (and thus editing if you use the old tools to export/import into .wtex) still works well.

Bad news: I still haven't gotten any mesh swaps to work. They still load up as invisible. I tried just doing the meshes, then I tried doing meshes and textures again, with the same results. I also tried a few ship pieces: those caused crashes. There's definitely something I'm missing and it's probably something ridiculously simple once I spot it.
## Post #14
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2021-10-13T11:11:07+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

btw, are STO models animated in any way?  Do they have bones/joints or skeletons?  Any external animation or skeleton files?  Just wondering why source code mentions "bone weights", when I don't see any bones in the file or any kind of hierarchy.
## Post #15
- Username: Jff007
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 30, 2021 2:01 am
- Post datetime: 2021-10-13T16:30:15+00:00
- Post Title: Anyone With Experience with Cryptic .mset Files?

> Reply from roswell ↑Wed Oct 13, 2021 7:11 pm at Wed Oct 13, 2021 7:11 pm
>
> 
btw, are STO models animated in any way?  Do they have bones/joints or skeletons?  Any external animation or skeleton files?  Just wondering why source code mentions "bone weights", when I don't see any bones in the file or any kind of hierarchy.

I know that some are. A couple of the weapons have animated joints. Then there's the outfit pieces, too.

They have an entire section of the files devoted to the animation files.
## Post #16
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-11-13T17:31:46+00:00
- Post Title: Re: Anyone With Experience with Cryptic .mset Files?

Hi, everyone!
I wanna get some models from Neverwinter online for my mod,but can't find atools for extracting something from the game.
Can someone give me a name of tool or where to get it?

UPD: so, i found the unpacker, I get models in MSET files and textures in WTEX. But I an open only normal maps, colormaps give me error in all software (I use Irfran view and Nvidia tools). 
Do someone know how to get textures normally?

But what tools can convert MSET to fbx? 
I found Mset to obj tools only. It's working so.
