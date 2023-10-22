## Post #1
- Username: Zakia
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 21, 2020 4:19 pm
- Post datetime: 2020-05-14T10:00:33+00:00
- Post Title: Extracting models from the Zelda Zone of Sonic Lost World Wii U?

Hello ^^

I hope I posted in the right section, if not, I apologise ^^'

As the title say, I'm trying to extract the models of the Zelda Zone dlc from Sonic Lost World Wii U.

I'm specifically looking for the models of Sonic, Link and the Crimson Loftwing (it's a red big bird, he and Link in this dlc are from Skyward Sword), the rupees, hearts and the chests.

After some research, I managed to get the pac files out of the cpk thanks to quickbms and the cpk script.

To extract the files containted in the pac files, I used the pacpack-WiiU in this : [https://github.com/slashiee/libgens-sonicglvl/tree/WiiU](https://github.com/slashiee/libgens-sonicglvl/tree/WiiU) since the others sonicglvl didn't work because it's a Wii U game.

I got Sonic's files consisting of: .model, .shadow-model, .skl.hkx, .dds and .material.

Also, I can't open the dds files.
Looking into the dds files with the hex editor HxD, I found that they're apparently Gfx textures, as the begining start with: Gfx2.
What can I do to open theses files?

How do I convert the models with their bones intact so that I can open them in Blender?

By using the modelfbx_2012 found in the link I gave, I could convert the .model into fbx, but it doesn't have bones.
They are probably in the .skl.hkx file, but how do I convert it?

I can send all the files if needed : the cpk of the dlc, the folder of the extracted cpk.

*Edit*
I found the files for Link, his bird, the hearts, the rupees and the chests, so I deleted the part of my post saying I couldn't find them
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-14T10:52:24+00:00
- Post Title: Extracting models from the Zelda Zone of Sonic Lost World Wii U?

File samples (.model, .skl.hkx)? (One small sample of each, if possible and NOT "all the files"  )
## Post #3
- Username: Zakia
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 21, 2020 4:19 pm
- Post datetime: 2020-05-14T18:37:32+00:00
- Post Title: Extracting models from the Zelda Zone of Sonic Lost World Wii U?

Hi @shakotay2 ^^

Here's the link for the sample files of LinkSonic: [http://www.mediafire.com/file/maqvrnx5q ... s.rar/file](http://www.mediafire.com/file/maqvrnx5qtm9jtm/LinkSonic_Sample_files.rar/file)

Also, I found something strange, I can't convert the zdlc03_obj_fairy.model into fbx while my attempts with others files were successful...

When I try using the modelfbx_2012, I get this message on the command prompt : A string different than water for the 4th slot? Report this model! special1

I can't even look at the file using SonicGLvl, I get the same message.

Here's the .model files, along with samples of other .model files for comparison: [http://www.mediafire.com/file/nr39g1c6h ... d.rar/file](http://www.mediafire.com/file/nr39g1c6hpskvnl/Samples_model_files_from_Zelda_Zone_of_Sonic_Lost_World.rar/file)

Also, just by curiosity, is there a way to convert .anm.hkx files?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-18T15:01:46+00:00
- Post Title: Extracting models from the Zelda Zone of Sonic Lost World Wii U?

Hi Zakia,

> Reply from Zakia ↑Fri May 15, 2020 2:37 am at Fri May 15, 2020 2:37 am
>
> Also, I found something strange, I can't convert the zdlc03_obj_fairy.model into fbxIt's converted, but the fbx contains 5 small planes only.

> When I try using the modelfbx_2012, I get this message on the command prompt : A string different than water for the 4th slot? Report this model! special1press ENTER three times

> Also, just by curiosity, is there a way to convert .anm.hkx files?*.anm.hkx is in the batch file. So maybe...
## Post #5
- Username: Zakia
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 21, 2020 4:19 pm
- Post datetime: 2020-05-19T09:37:33+00:00
- Post Title: Extracting models from the Zelda Zone of Sonic Lost World Wii U?

Hello Shatokay ^^

Thanks for your help ^^ Your tip worked, and I guess it's normal that the fairy's mesh is made of planes, as the textures is what will give it the fairy's shape ^^

On another forum, I was told to use texconv2 or switch tool box to convert the .dds files.

Since texconv2 gave me this error: Error loading DDS file. Exiting, I used switch tool, and it worked ^^

And thanks to this thread: [https://www.vg-resource.com/post-593546.html](https://www.vg-resource.com/post-593546.html), I managed to get the fbx model with their bones by using the HKXConverter-2012-With-Metadata.7z given to download to first convert them like said
