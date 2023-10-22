## Post #1
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-08-28T07:39:05+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

Model files are in .tmd2. 
Textures files are in .lds.

Motion/Animations files in .takdjpkg.

Any documentation? Interested one?
[Files test.7z](https://xentaxbackup.github.io/file/18660_Files test.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-28T08:47:52+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

Using hex2obj (view link in my sig):
.



upperbody02_01_01_03-tmd2.png (101.33 KiB) Viewed 884 times


(uvs might need a deeper look at.)
## Post #3
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-29T17:05:09+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

You can try this one, not sure if it works for all files

*.py is a script for Noesis and the other one is used to extract dds files from .lds

Link: [Here](https://forum.xentax.com/viewtopic.php?f=16&t=22608&p=166307#p166307)
## Post #4
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-08-30T07:07:19+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from andy97 ↑Sun Aug 30, 2020 1:05 am at Sun Aug 30, 2020 1:05 am
>
> 
You can try this one, not sure if it works for all files

*.py is a script for Noesis and the other one is used to extract dds files from .lds
[https://i.gyazo.com/6bfb969ff40cedc242d ... e9512f.png](https://i.gyazo.com/6bfb969ff40cedc242dcbc88bde9512f.png)
## Post #5
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-30T08:38:20+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> https://i.gyazo.com/6bfb969ff40cedc242d ... e9512f.png

Open that .py by notepad or something and delete that line. Otherwise, this is the fixed one with some other changes.

Edited: (31/08) Upload newer version: Add submesh's name based on file name + index, bone name by unique id, and handle faceType.
[Captain Tsubasa tool.rar](https://xentaxbackup.github.io/file/18674_Captain Tsubasa tool.rar)
## Post #6
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-08-30T09:30:49+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from andy97 ↑Sun Aug 30, 2020 4:38 pm at Sun Aug 30, 2020 4:38 pm
>
> 

https://i.gyazo.com/6bfb969ff40cedc242d ... e9512f.png


Open that .py by notepad or something and delete that line. Otherwise, this is the fixed one with some other changes.

The model script is working perfectly. I think the texture extractor is not. I'm not sure, but I think he's extracting the alpha or something weird?

"Face_tsubasa" 
[https://i.gyazo.com/f1931abf0cd8478688e ... 750097.png](https://i.gyazo.com/f1931abf0cd8478688edabf32e750097.png)

Can provide you the files if you want to.
## Post #7
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-30T09:53:31+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from Kaem ↑Sun Aug 30, 2020 5:30 pm at Sun Aug 30, 2020 5:30 pm
>
> 

The model script is working perfectly. I think the texture extractor is not. I'm not sure, but I think he's extracting the alpha or something weird?

"Face_tsubasa" 
https://i.gyazo.com/f1931abf0cd8478688e ... 750097.png

Can provide you the files if you want to.

Maybe that one is alpha.

The extractor just simply extracts (splits) all original dds files from lds file - no decryption or decompression required. I've checked some files of face and most of them use the same tex   I have no idea why. 

If I'm not wrong, maybe they reuse the same tex but different meshes for the players, since their faces are similar except the appearance.
## Post #8
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-08-30T10:04:51+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from andy97 ↑Sun Aug 30, 2020 5:53 pm at Sun Aug 30, 2020 5:53 pm
>
> 
Kaem wrote: ↑Sun Aug 30, 2020 5:30 pm

The model script is working perfectly. I think the texture extractor is not. I'm not sure, but I think he's extracting the alpha or something weird?

"Face_tsubasa" 
https://i.gyazo.com/f1931abf0cd8478688e ... 750097.png

Can provide you the files if you want to.


It just simply extracts (splits) all original dds files from lds file - no decryption or decompression required. I've checked some files of face and they all use the same tex   I have no idea why.

It makes sense. Eyes, eyelashes or hairs are separated so the face textures should be practically the same. But yeah It does not extract correctly, all the .dds obtained are in black/white like my example.
## Post #9
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-30T10:14:31+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from Kaem ↑Sun Aug 30, 2020 6:04 pm at Sun Aug 30, 2020 6:04 pm
>
> 

It makes sense. Eyes, eyelashes or hairs are separated so the face textures should be practically the same. But yeah It does not extract correctly, all the .dds obtained are in black/white like my example.

I have checked and it's nothing wrong with the extracted files, better you should try to apply the tex on the mesh and see if it looks reasonable.

I assume the tex originally is not obvious, it's just a combination of colors in its suitable position for uvs.

Original tex:



Result:


P/s: the actual face tex is in pl00xx_face00, not face_xx I think?
## Post #10
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-08-30T10:20:27+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

I'm blind it's a 4x4 texture lol. I was expecting for something with the size of the "alpha channel" texture or so. Ty.
## Post #11
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-30T10:27:12+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from Kaem ↑Sun Aug 30, 2020 6:20 pm at Sun Aug 30, 2020 6:20 pm
>
> 
I'm blind it's a 4x4 texture lol. I was expecting for something with the size of the "alpha channel" texture or so. Ty.

> P/s: the actual face tex is in pl00xx_face00, not face_xx I think?

If you want to get a bigger size, this is a clue. It is more detailed than 'face_xyz', I got the texture above from that. Good luck!
## Post #12
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-08-30T10:47:59+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

Fuck, did you test the upperbody ones? Sounds like They're using some paintable script in the game...
## Post #13
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-30T11:14:04+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from Kaem ↑Sun Aug 30, 2020 6:47 pm at Sun Aug 30, 2020 6:47 pm
>
> 
Fuck, did you test the upperbody ones? Sounds like They're using some paintable script in the game...

strange  I have double-checked the .lds file and they are the same as they are supposed to be. So no idea about it, sorry
## Post #14
- Username: kenji69
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2020 6:31 pm
- Post datetime: 2020-09-01T13:33:05+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

Hi, could you explain how you open the tmd2 file? I have tryed with the tool but It doesn't work.
## Post #15
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-09-01T17:57:14+00:00
- Post Title: Captain Tsubasa: Rise of New Champions Models?

> Reply from kenji69 ↑Tue Sep 01, 2020 9:33 pm at Tue Sep 01, 2020 9:33 pm
>
> 
Hi, could you explain how you open the tmd2 file? I have tryed with the tool but It doesn't work.

it's a noesis script - file .py, and if you familiar with it, just put the script into plugins/python folder and then open it by Noesis
## Post #16
- Username: microbio10
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 10, 2020 6:06 pm
- Post datetime: 2020-09-01T18:10:15+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hi, I'm interested in modding this game, is there any tool to convert dds back to lds? so i can mod the game textures
## Post #17
- Username: kenshinova
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 06, 2020 2:59 pm
- Post datetime: 2020-09-06T07:10:28+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hi 

Anyone knows how to open animation/motion files?

moreover, where can i find kits of teams? which files or at least extension file to search for
## Post #18
- Username: cOiSMatOrGent
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 02, 2021 12:10 am
- Post datetime: 2021-05-01T16:28:22+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hello everyone, I wanted to know what program is used to view the files:
* Texture files are in .lds
* Motion / animation files in .takdjpkg.

at this time I'm talking about the rise of the new game of the champion captain tsubasa thanks   

If someone can help me with the textures please and thank you
## Post #19
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-07-08T10:51:32+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hello, could anyone help with extracting textures? I tried drag and dropping and running the exe provided in previous posts, but i can't seem to get textures. I get this error: 
[https://imgur.com/a/a9QceB1](https://imgur.com/a/a9QceB1)
## Post #20
- Username: koytavugu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 07, 2021 10:49 pm
- Post datetime: 2021-09-04T09:56:31+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Does anyone here know how we can convert a model to tmd2?
## Post #21
- Username: olidall
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 19, 2021 11:39 pm
- Post datetime: 2021-09-20T15:59:58+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hello, could someone help me extract textures? run the exe provided in the previous posts, but I get this error:
## Post #22
- Username: olidall
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 19, 2021 11:39 pm
- Post datetime: 2021-09-30T18:36:24+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from kenshinova ↑Sun Sep 06, 2020 3:10 pm at Sun Sep 06, 2020 3:10 pm
>
> 
Hi 

Anyone knows how to open animation/motion files?

moreover, where can i find kits of teams? which files or at least extension file to search for

I studied the folder structure of the game, I think we can find the teams kits in "\ Gamedata \ Graphics \ AppExtend \ cat"

theses thread helped me to understand where the files come from [https://www.vg-resource.com/thread-34826.html](https://www.vg-resource.com/thread-34826.html) 
[viewtopic.php?f=16&t=14419&p=131160&hil ... ft#p131160](https://forum.xentax.com/viewtopic.php?f=16&t=14419&p=131160&hilit=cat+cat+tamsoft#p131160)
[https://www.undertow.club/threads/hyper ... 333/page-2](https://www.undertow.club/threads/hyperdimension-neptunia-rebirth-1-nude-compilation.10333/page-2)
## Post #23
- Username: olidall
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 19, 2021 11:39 pm
- Post datetime: 2021-10-22T20:59:49+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

I managed to modify the textures of the modification emblems to make them look like the other national emblems. I created the Canada Jr. Youth emblem
## Post #24
- Username: olidall
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 19, 2021 11:39 pm
- Post datetime: 2021-10-27T14:37:25+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Tuto on how to use QuickBMS to custom the texture of Captain Tsubasa: Rise of New Champions
Step 1. Extract the .cat file you want to edit. [You can choose multiple .cat files]
- Open QuickBMS [You can just otherwise click on the script and have the BMS files open with QuickBMS]
- Find Tamsoft CAT script and click on it.
- Click the .Cat file
- Then click the folder to extract to
- Delete things that aren't .tmd files unless you're into modeling
Step 2. Extract the .tmd files [You can choose multiple .tmd files]
- Open QuickBMS
- Find Tamsoft GXT script and click on it.
- Click the .tmd file
- Then click the folder to extract to
Step 3 Edit the .dds file [with GIMP or Photoshop (install the Intel DDS plugin)]
- Make a back up
- Change what you want to change
- Make sure you save it as DXT1, 5 or 10 keeping it the same as the original, [Look at the type of DXT by looking with Hex Edit the TMD file]
- If your new file doesn't match the same filesize as the old, then your DXT is the wrong number. DDS with Transparent space will be 5 or 10
Step 4 Repack GXT
- Open reimport.bat
- Find Tamsoft GXT script and click on it.
- Click the .tmd file
- Then click your modified .dds file
- If it's not the right filesize you'll get an error.
Step 5 Repack CAT
- Open reimport.bat
- Find Tamsoft CAT script and click on it.
- Click the .cat file
- Then click the .tmd file
Step 6 Replace the .cat file in the  Captain Tsubasa: Rise of New Champions Steam files. Be sure to back up the root file before handling.

Only repeat steps 3-6 when making any changes. Yes you have to do this everytime.

This zip contain Tamsoft GXT and Tamsoft CAT
[Captain Tsubasa Texture Tool.zip](https://xentaxbackup.github.io/file/21081_Captain Tsubasa Texture Tool.zip)
## Post #25
- Username: olidall
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 19, 2021 11:39 pm
- Post datetime: 2021-12-05T18:09:06+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

All texture files are in the "\ Gamedata \ Graphics \ AppExtend \ cat". The textures of the uniforms are called "team***.cat"
All files numbered 000 to 009 are teams are collegiate teams, 010 to 20 are national teams. From 100 to 159 are the customizable uniforms in Dream Team Edit. from 160 to 220 are the are the uniforms used as a pattern in Dream Team Edit. from 1000 to 1005 are the uniforms of the DLC players' events.
## Post #26
- Username: Carbune
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 07, 2021 5:25 am
- Post datetime: 2021-12-07T04:22:09+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from olidall ↑Mon Sep 20, 2021 11:59 pm at Mon Sep 20, 2021 11:59 pm
>
> 
Hello, could someone help me extract textures? run the exe provided in the previous posts, but I get this error:
https://i.imgur.com/JEmMoQE.png

> Reply from Makoto ↑Thu Jul 08, 2021 6:51 pm at Thu Jul 08, 2021 6:51 pm
>
> 
Hello, could anyone help with extracting textures? I tried drag and dropping and running the exe provided in previous posts, but i can't seem to get textures. I get this error: 
https://imgur.com/a/a9QceB1
Were either of you able to solve this or find an alternative? I'm getting this error as well. I'm also trying to figure out the difference between what that tool would've put out and the files from the last couple of posts, as the GXT extraction part fails for specific files and I have no idea which ones would be relevant for me to look at beyond guessing through the file size. My guess right now is that the stuff in the last 2 posts is about the frontend and create-a-player stuff as well as things like the kits and numbers, whereas the lds files contain things that are more specific like the textures for existing players (things like GameData/mdl/tex/eye_hyuga.lds matching the existing GameData/mdl/tmd/eye_hyuga.tmd2).

It probably requires much more effort than it's worth, but what I'm trying to do is to take the models and textures and export at least one fully built player model (say, Hyuga's) into Blender, where I would need to work with it further. The models being split into so many submodels is frustrating enough as is (though manageable), but the textures look significantly more difficult to figure out.

EDIT: Turns out the GXT extractor can extract the textures from the LDS files just fine. I've now run into an entirely different issue: I don't think the previous posts talking about how the resulting DDS files are black&white are entirely right, because for everything that isn't a special object like Wakabayashi's hat I'm getting very similar textures that don't seem to have anything to do with the intended model texture. If it's not these, then what do I need to use for the bits that are clearly meant to be colored, like the eyes? The generic stuff like the skin color and kits works fine (with some issues for textures that are clearly meant to go on top of others, like emblems and numbers) when using the exported skin textures, but I'm struggling with the more player-specific stuff.

EDIT 2: Took a while, but I've figured it out.
[](https://i.imgur.com/l65uFBV.png)

Turns out that, as mentioned in a previous post, the pl00xx_[...] textures (also located in the LDS files) are indeed the right ones and not the ones that are actually named after the players in question. In some cases it's definitely difficult to figure out exactly which player is associated with which ID, but it's also how I figured out that this is what was actually happening, as the ID 02 files (Wakabayashi) had the textures for his hat which are also present in the hair_wkbys files. From there on out it's just a question of mixing and matching everything accordingly.
## Post #27
- Username: kenanmu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 03, 2016 1:10 pm
- Post datetime: 2021-12-22T05:58:54+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from olidall ↑Sat Oct 23, 2021 4:59 am at Sat Oct 23, 2021 4:59 am
>
> 
I managed to modify the textures of the modification emblems to make them look like the other national emblems. I created the Canada Jr. Youth emblem

Hi! how do you extract and reimport dds and .dat files (emblems)? Thank you in advance!
## Post #28
- Username: olidall
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 19, 2021 11:39 pm
- Post datetime: 2021-12-23T17:44:46+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from kenanmu ↑Wed Dec 22, 2021 1:58 pm at Wed Dec 22, 2021 1:58 pm
>
> 
olidall wrote: ↑Sat Oct 23, 2021 4:59 am
I managed to modify the textures of the modification emblems to make them look like the other national emblems. I created the Canada Jr. Youth emblem



Hi! how do you extract and reimport dds and .dat files (emblems)? Thank you in advance!

Hi! For modify a emblem, intall quickbms with this link [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
For original game team emblem, it is in "\Gamedata\ui\fr\swap"
for emblem set it is in "Gamedata\Graphics\AppExtend\cat\"
## Post #29
- Username: kenanmu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 03, 2016 1:10 pm
- Post datetime: 2021-12-24T00:03:46+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from olidall ↑Fri Dec 24, 2021 1:44 am at Fri Dec 24, 2021 1:44 am
>
> 
kenanmu wrote: ↑Wed Dec 22, 2021 1:58 pm
olidall wrote: ↑Sat Oct 23, 2021 4:59 am
I managed to modify the textures of the modification emblems to make them look like the other national emblems. I created the Canada Jr. Youth emblem



Hi! how do you extract and reimport dds and .dat files (emblems)? Thank you in advance!


Hi! For modify a emblem, intall quickbms with this link https://aluigi.altervista.org/quickbms.htm
For original game team emblem, it is in "\Gamedata\ui\fr\swap"
for emblem set it is in "Gamedata\Graphics\AppExtend\cat\"

Thank you very much! it works!!! GXT script works with .dat files
## Post #30
- Username: kenanmu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 03, 2016 1:10 pm
- Post datetime: 2021-12-25T20:32:07+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hi guys! someone knows how i can change the collars and kit numbers (type and colours) of preset teams (National and school teams)? [/img]Thanks in advance!
[CAPTAIN TSUBASA_ RISE OF NEW CHAMPIONS 25-12-2021 17_24_06.png](https://xentaxbackup.github.io/file/21470_CAPTAIN TSUBASA_ RISE OF NEW CHAMPIONS 25-12-2021 17_24_06.png)
## Post #31
- Username: zodiacholiday
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 26, 2021 8:02 am
- Post datetime: 2021-12-26T06:56:28+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Can confirm that following the steps founded here, you can extract models, textures and even port them to other games.
Tnx for the info 
[atom.png](https://xentaxbackup.github.io/file/21471_atom.png)
## Post #32
- Username: Carbune
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 07, 2021 5:25 am
- Post datetime: 2021-12-26T15:06:13+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Has anyone had any luck specifically exporting the contents of obj03_00.tmd2 (and _01 and _02)? I've had no luck finding some very specific things like the Tachibana brothers' teeth, and given that there are 3 such files I'm tempted to say that a lot of the shared files for the 3 different body types are in there, but neither Noesis nor hex2obj seem to be able to handle any of the 3 files at all ("RuntimeError: Tried to set offset beyond buffer size." for Noesis specifically when the script tries to seek to the hierarchyAddress address on line 112 (1086126104 > 1838584 for file obj03_00.tmd2), both when exporting and when previewing).

EDIT: No dice - I've fixed the script myself (as simple as changing the "if boneFlag not in [16, 24]: " to "if boneFlag not in [16, 17, 24]: "), but the objects just have the dressing room shirts that you can see in the background before international matches.
Has anyone found the stuff I mentioned earlier anywhere else? I'm losing my mind trying to look for the additional face objects that are missing, like the aforementioned teeth. Some players with very "special" faces have them in their relevant pl00xx_face file, but that's likely just because whatever generic object is normally used isn't good enough for that case and I'm specifically looking for those.

EDIT 2: I got it! The Noesis script has yet another problem: submeshCount is almost certainly not at all what the script writer thought it was, because a cursory glance at the hex values in one of the face tmd2 files showed that the mesh for loop stopped way short of the mark! It doesn't apply to every single file (I tried one of the upperbody files and the calculation was correct there), but editing that last part of the code to loop until submeshIdxCount + submeshOffset = faceIdxCount has made things like the Tachibana brothers' teeth appear. Very lazy example below.

```
submeshCurrentCount = 0
i = 0
while submeshCurrentCount < faceIdxCount:
       rapi.rpgSetName(filename + "_mesh_" + str(i))
       submeshIdxCount = self.inFile.readUInt()
       submeshOffset = self.inFile.readUInt()
       submeshBuff = faceBuff[submeshOffset * 3 * faceTypeFlag : submeshIdxCount * 3 * faceTypeFlag + submeshOffset * 3 * faceTypeFlag]
       rapi.rpgCommitTriangles(submeshBuff, faceType, submeshIdxCount * 3, noesis.RPGEO_TRIANGLE, 1)
       i += 1
       submeshCurrentCount += submeshIdxCount
                
pass

```

[](https://i.imgur.com/ElpL0Vh.png)
Oh yeah, and change the 16 in the 

```
self.inFile.seek(16, NOESEEK_REL)
```
 line to 12 to fix the skeletons.
## Post #33
- Username: AspiringMob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 22, 2022 11:02 am
- Post datetime: 2022-04-17T01:07:17+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

How do you made it look exactly the same? would you help me? please.

> Reply from olidall ↑Sat Oct 23, 2021 4:59 am at Sat Oct 23, 2021 4:59 am
>
> 
I managed to modify the textures of the modification emblems to make them look like the other national emblems. I created the Canada Jr. Youth emblem
## Post #34
- Username: tyranitares
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 01, 2022 3:39 am
- Post datetime: 2022-05-01T09:37:54+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hello.Is there any excel with the id and names of the players??There are too similar and is crazy search them by ID. Thanks
## Post #35
- Username: kenanmu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 03, 2016 1:10 pm
- Post datetime: 2022-05-20T15:08:36+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hi guys! anyone know how i can change the kit settings? for example i need to change collar and number font colour and model and if is possible delete the number in the shorts. Thank u in advance
## Post #36
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-06-03T04:38:32+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from olidall ↑Wed Oct 27, 2021 10:37 pm at Wed Oct 27, 2021 10:37 pm
>
> 
Tuto on how to use QuickBMS to custom the texture of Captain Tsubasa: Rise of New Champions
Step 1. Extract the .cat file you want to edit. [You can choose multiple .cat files]
- Open QuickBMS [You can just otherwise click on the script and have the BMS files open with QuickBMS]
- Find Tamsoft CAT script and click on it.
- Click the .Cat file
- Then click the folder to extract to
- Delete things that aren't .tmd files unless you're into modeling
Step 2. Extract the .tmd files [You can choose multiple .tmd files]
- Open QuickBMS
- Find Tamsoft GXT script and click on it.
- Click the .tmd file
- Then click the folder to extract to
Step 3 Edit the .dds file [with GIMP or Photoshop (install the Intel DDS plugin)]
- Make a back up
- Change what you want to change
- Make sure you save it as DXT1, 5 or 10 keeping it the same as the original, [Look at the type of DXT by looking with Hex Edit the TMD file]
- If your new file doesn't match the same filesize as the old, then your DXT is the wrong number. DDS with Transparent space will be 5 or 10
Step 4 Repack GXT
- Open reimport.bat
- Find Tamsoft GXT script and click on it.
- Click the .tmd file
- Then click your modified .dds file
- If it's not the right filesize you'll get an error.
Step 5 Repack CAT
- Open reimport.bat
- Find Tamsoft CAT script and click on it.
- Click the .cat file
- Then click the .tmd file
Step 6 Replace the .cat file in the  Captain Tsubasa: Rise of New Champions Steam files. Be sure to back up the root file before handling.

Only repeat steps 3-6 when making any changes. Yes you have to do this everytime.

This zip contain Tamsoft GXT and Tamsoft CAT
Hi, I know it's been a long time since you posted this but...would you have any idea how to help me!? I managed to do step 1 just fine and extract the .tmd files from the the team164_etc.cat files, but now I'm stuck in step 2 because, whenever I try to use Tamsoft GXT to extract the .dds files from the .tmd files, I receive this message:

Error: incomplete input file 0: C:\....\Desktop\QuickBMS\EXPORTS\team164_00_00_00_00_0.tmd
       Can't read 4 bytes from offset 000000000000001c.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   28         28         . offset 000000000000001c

Last script line before the error or that produced the error:
  9   get FILESIZE long
  coverage file 0   100%   28         28         . offset 000000000000001c

and nothing is extracted, I've tried with both regular and 4gb versions of QuickBMS and it's the same result, do you have any idea what could be causing this error? thank you very much for the attention!
## Post #37
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-06-03T04:58:57+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from tyranitares ↑Sun May 01, 2022 5:37 pm at Sun May 01, 2022 5:37 pm
>
> 
Hello.Is there any excel with the id and names of the players??There are too similar and is crazy search them by ID. Thanks

Well, since I also couldn't find one on the internet, I actually kinda did the crazy thing and checked each PL file to see which face and hair was what and saved a list for myself on a .txt, here is what I got, it's very basic and I did this a while back so I hope things haven't changed since then, I hope it helps.
[PL ID List.rar](https://xentaxbackup.github.io/file/22305_PL ID List.rar)
## Post #38
- Username: AspiringMob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 22, 2022 11:02 am
- Post datetime: 2022-06-04T18:05:34+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from Bela20 ↑Fri Jun 03, 2022 12:38 pm at Fri Jun 03, 2022 12:38 pm
>
> 
Hi, I know it's been a long time since you posted this but...would you have any idea how to help me!? I managed to do step 1 just fine and extract the .tmd files from the the team164_etc.cat files, but now I'm stuck in step 2 because, whenever I try to use Tamsoft GXT to extract the .dds files from the .tmd files, I receive this message:

Error: incomplete input file 0: C:\....\Desktop\QuickBMS\EXPORTS\team164_00_00_00_00_0.tmd
       Can't read 4 bytes from offset 000000000000001c.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   28         28         . offset 000000000000001c

Last script line before the error or that produced the error:
  9   get FILESIZE long
  coverage file 0   100%   28         28         . offset 000000000000001c

and nothing is extracted, I've tried with both regular and 4gb versions of QuickBMS and it's the same result, do you have any idea what could be causing this error? thank you very much for the attention!

I can help you. Usually, when you extract the tmd files there's one with no information in it and the filename always is finished with "_0.tmd". Try the file "team164_00_00_00_00_1.tmd" it should contain the jersey's texture.

Also, delete all "_0.tmd" files or files with 1 kB after extracting from cat files
## Post #39
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-06-05T06:31:16+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from AspiringMob ↑Sun Jun 05, 2022 2:05 am at Sun Jun 05, 2022 2:05 am
>
> 
Bela20 wrote: ↑Fri Jun 03, 2022 12:38 pm
Hi, I know it's been a long time since you posted this but...would you have any idea how to help me!? I managed to do step 1 just fine and extract the .tmd files from the the team164_etc.cat files, but now I'm stuck in step 2 because, whenever I try to use Tamsoft GXT to extract the .dds files from the .tmd files, I receive this message:

Error: incomplete input file 0: C:\....\Desktop\QuickBMS\EXPORTS\team164_00_00_00_00_0.tmd
       Can't read 4 bytes from offset 000000000000001c.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   28         28         . offset 000000000000001c

Last script line before the error or that produced the error:
  9   get FILESIZE long
  coverage file 0   100%   28         28         . offset 000000000000001c

and nothing is extracted, I've tried with both regular and 4gb versions of QuickBMS and it's the same result, do you have any idea what could be causing this error? thank you very much for the attention!


I can help you. Usually, when you extract the tmd files there's one with no information in it and the filename always is finished with "_0.tmd". Try the file "team164_00_00_00_00_1.tmd" it should contain the jersey's texture.

Also, delete all "_0.tmd" files or files with 1 kB after extracting from cat files

You are a god send, I was about to lose my shit not knowing what it was, it was exactly those 1kb files, once they were gone everything went fine, thank you so much kind sir, now it's time to relearn some photoshopping!
## Post #40
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-06-13T18:10:20+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from kenanmu ↑Fri May 20, 2022 11:08 pm at Fri May 20, 2022 11:08 pm
>
> 
Hi guys! anyone know how i can change the kit settings? for example i need to change collar and number font colour and model and if is possible delete the number in the shorts. Thank u in advance

The only thing I know is how to change the collar color!

You do it by editing the "kits .dds" files that you extract from "teams .cat" files.

If I ever find out how to change the other stuff I'll come back here to tell you...and if you ever find the answers before I do I'd appreciate it if you hit me up 'cause I'm also looking for them!
## Post #41
- Username: AspiringMob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 22, 2022 11:02 am
- Post datetime: 2022-07-24T14:21:17+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hey, when you create a new kit, where do you replace it? in the kits for custom teams or the spots for DLC teams?
## Post #42
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-08-07T04:11:19+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from AspiringMob ↑Sun Jul 24, 2022 10:21 pm at Sun Jul 24, 2022 10:21 pm
>
> 
Hey, when you create a new kit, where do you replace it? in the kits for custom teams or the spots for DLC teams?

Not sure if I understood the question correctly but...when I mod a kit, I replace "Set Kits" as in the French Ligue 1 kits for Custom Teams
## Post #43
- Username: AspiringMob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 22, 2022 11:02 am
- Post datetime: 2022-08-11T00:39:35+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from HoldTheReggae ↑Sun Aug 07, 2022 12:11 pm at Sun Aug 07, 2022 12:11 pm
>
> 

Not sure if I understood the question correctly but...when I mod a kit, I replace "Set Kits" as in the French Ligue 1 kits for Custom Teams

Thanks, that was the answer I was looking for. Unfortunately, I have a pirate copy and Ligue 1 kits are locked so I have limited spots for Custom Teams. If any knows a how to unlock Ligue 1 kits, please let me know.
## Post #44
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-08-11T01:41:14+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from AspiringMob ↑Thu Aug 11, 2022 8:39 am at Thu Aug 11, 2022 8:39 am
>
> 
HoldTheReggae wrote: ↑Sun Aug 07, 2022 12:11 pm

Not sure if I understood the question correctly but...when I mod a kit, I replace "Set Kits" as in the French Ligue 1 kits for Custom Teams


Thanks, that was the answer I was looking for. Unfortunately, I have a pirate copy and Ligue 1 kits are locked so I have limited spots for Custom Teams. If any knows a how to unlock Ligue 1 kits, please let me know.

Tbf the customizable kits are also modable, but I never tried and I don't know what/how they would look like...

I assume it would only show the design and they'd have to be edited in a way that you'd have to use the in-game colors to finish it off

If you want to give it a shot, I have a .txt that lists the files of kits IDs and it's location,
you can download it here:
[https://www.nexusmods.com/users/27417645?tab=user+files](https://www.nexusmods.com/users/27417645?tab=user+files)
## Post #45
- Username: AspiringMob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 22, 2022 11:02 am
- Post datetime: 2022-08-17T01:06:33+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

That's cool HoldTheReggae. You even acknowledge the time I helped you. Maybe we can share mods? I have a Barcelona 21/22 mod kit and Bayern 22/23 kit.

Where do you get League Team Jersey's mod?
## Post #46
- Username: HoldTheReggae
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 03, 2022 11:53 am
- Post datetime: 2022-08-17T18:08:06+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

> Reply from AspiringMob ↑Wed Aug 17, 2022 9:06 am at Wed Aug 17, 2022 9:06 am
>
> 
That's cool HoldTheReggae. You even acknowledge the time I helped you. Maybe we can share mods? I have a Barcelona 21/22 mod kit and Bayern 22/23 kit.

Where do you get League Team Jersey's mod?

Don't mention it, I always remember those who helped me accomplish things!

Hey, I'm not going to say no to that offer haha
I only intend on starting to mod Team kits after I'm done making kits for all major National Teams on Captain Tsubasa so, I'd really like to check out your Barça and Bayern kits!

Btw, got the Team Jersey's mod from here:
[https://youtu.be/GW38aXLF8F4](https://youtu.be/GW38aXLF8F4)
## Post #47
- Username: Tyranitares1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 29, 2022 9:57 pm
- Post datetime: 2022-08-29T14:04:51+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hello guys. I´m having a porblem with noesis. I want to export files of any player and when i click export says me that nothing has exported. Doesn´t matter which player is, doesn´t give me any file. Is there any way to solve it?? Thanks
[https://imgur.com/a/7SQeJ1m](https://imgur.com/a/7SQeJ1m)
## Post #48
- Username: FLICKERZ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 30, 2022 10:23 pm
- Post datetime: 2022-09-01T19:54:21+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

How can I add a Face animation to my New Hero character. Like in this Video:[https://www.youtube.com/watch?v=1BiOP4l ... nnel=WreyT](https://www.youtube.com/watch?v=1BiOP4ldqKk&ab_channel=WreyT)
## Post #49
- Username: Schimica95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 24, 2022 7:07 pm
- Post datetime: 2023-01-11T21:12:50+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Hi, is there any way to use the Ultimate edit base uniforms for modded uniforms like we do with the preset ones? It seems like I can't but does anyone have a definitive answer?
## Post #50
- Username: Schimica95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 24, 2022 7:07 pm
- Post datetime: 2023-01-11T21:16:24+00:00
- Post Title: Re: Captain Tsubasa: Rise of New Champions Models?

Is there still no way to modify original players appearences?
