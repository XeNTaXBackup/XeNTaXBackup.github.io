## Post #1
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-08-22T13:47:07+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

Hello folks, I am attempting to extract models and textures from an Android game called The Respawnables that was long delisted, since the game has got some really cool looking models. I recall someone trying to do this some time ago in Zenhax forums, and Luigi actually made a quickbms script to decompile the game archives (pakd, pakh format, the quickbms script is 8kap). The person was successful in getting some textures, and mentioned about the .bin files containing the metadata (though they did not say how they convert the texture). After extracting the pakd and pakh files, I got a bunch of .mesh and .tex, which I could not work out how to use. 

If anyone experienced at converting meshes and textures can lend me a hand, I will really appreciate it.

Thanks in advance.

A sample mesh + texture:
[https://drive.google.com/file/d/1PTdvts ... sp=sharing](https://drive.google.com/file/d/1PTdvtsTqJswjQMBJQy5iiyCtdJnCjdxI/view?usp=sharing)

The whole archive extracted using quickbms script:
[https://drive.google.com/file/d/16OW2W9 ... sp=sharing](https://drive.google.com/file/d/16OW2W9g188hjEvrldlrvGbyLUchcDCue/view?usp=sharing)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-08-23T10:59:34+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

If you open werebat_d1f34c3af35ba573b6b47bca6c876265.tex with your favorite hex editor, you'll see the string "etc_rgb" near the front, which means 
[Ericsson Texture Compression](https://en.wikipedia.org/wiki/Ericsson_Texture_Compression) ([see also ](https://blog.unity.com/technology/crunch-compression-of-etc-textures)) that uses 8-byte chunks of 4x4 tiles. I'm not sure whether Raw Texture Cooker supports ETC under a different alias, but it's visually pretty close to BC1 and BC4. I'd try different formats from the list to find the right one.
[raw-texture-cooker-with-respawnables-werebat.jpg](https://xentaxbackup.github.io/file/24260_raw-texture-cooker-with-respawnables-werebat.jpg)
## Post #3
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-08-23T12:46:49+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

Hello there, thanks for the reply! I have given the raw texture converter a shot, trying all the possible formats in the drop down menu, unfortunately getting no results (apart from BC4 that you pointed out, it does have good resemblance of the texture, though its only gray, the colours are missing?).
## Post #4
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-08-23T13:12:00+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

Another update, I've successfully found a tool that can view ETC format! Kuriimu2's Raw Image Viewer seems to work perfectly, though there seems to be a couple of weird pixels on the top left. Took a peek at the meshes using HxD, can't make out the formats though. Any leads on the meshes?
[Capture.JPG](https://xentaxbackup.github.io/file/24261_Capture.JPG)
## Post #5
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-08-24T07:07:57+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

Cool, glad KRIV worked for the textures.

As for meshes, I wish you luck. You can look at the filename extension (which appears uselessly generic in this case), open the file with a hex editor (e.g. HxD, like you already did) to look at the header to see if it matches anything ("1FDKENONCTX" doesn't sound familiar to me though), try to parse the header via inspection (looks like named strings followed by either some flags, sizes, or element counts, then followed by binary data starting at 0x3C0 which is probably the vertex coordinates, polygon indices, and material information), or see if any other games by the same company (as they often reuse formats) have similar assets, in case someone else has already learned more about that game.There's also a "Game Modding - 3D/2D models" forum here...
## Post #6
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-08-24T09:33:04+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

> Reply from piken ↑Thu Aug 24, 2023 3:07 pm at Thu Aug 24, 2023 3:07 pm
>
> 
Cool, glad KRIV worked for the textures.

As for meshes, I wish you luck. You can look at the filename extension (which appears uselessly generic in this case), open the file with a hex editor (e.g. HxD) to look at the header to see if it matches anything ("1FDKENONCTX" doesn't sound familiar to me though), try to parse the header via inspection (looks like named strings followed by either some flags, sizes, or element counts, then followed by binary data starting at 0x3C0 which is probably the vertex coordinates, polygon indices, and material information), or see if any other games by the same company (as they often reuse formats) have similar assets, in case someone else has already learned more about that game.There's also a "Game Modding - 3D/2D models" forum here...
Hey there, thanks again for the response, really appreciate it! Will ask at the correct forum about the meshes.
## Post #7
- Username: coriolis14
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 26, 2023 9:25 pm
- Post datetime: 2023-08-26T13:40:36+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

I am this person: 

> I recall someone trying to do this some time ago in Zenhax forums

What a coincidence I'd look into this again at the same time somebody else did! 

The main things I wanted out of the Respawnables APK were shop item images, GUI elements, and music. I managed to get all of the above, so I stopped researching before I ever looked into the meshes and textures. (Well done pulling out the latter, that's awesome.)

Not sure I know anything that you don't at this point, but here's what my process was to recover the images, in case that has transfer value (or other people find this thread). 

1. Unzip the .obb file in the most recent Respawnables APK to get the pakh/d files. Point 8kap.bms to the pakh file to pull out the directory structure (thanks Luigi). 
2. You will get a lot of .tex files with header "1FDKENONCTX5". My understanding is these files are "wrappers" for an actual file you want to extract. For the images I wanted, these "1FDKENONCTX5" files were in fact hiding .tga images. The table of strings and flags (?) is not part of the real file you want (and I never parsed it so I don't know its significance). 
3. Extracting the files was a matter of making a few offset tables for where the "real" data starts for each type of image (i.e. skipping the table of strings etc), then merging that data with custom .tga headers (because the original files are missing .tga headers). You can make a script for this. 
4. I had to change the order of the bytes in the .tga files as the colours were incorrect. Also, the resulting picture is inverted on the y-axis, but that's simple to fix with ImageMagick. 
5. Convert the pictures to .png with ImageMagick and the transparency is conveniently retained! Here [https://imgur.com/a/1IDJrIk](https://imgur.com/a/1IDJrIk) are some examples of what comes out.

I really hope this will be of use for the meshes, which I frankly don't know shit about -- I wouldn't know it if I pulled out an intact file. Do update if you find anything. Maybe the people who worked on this [https://twitter.com/TheRespawnabl3s](https://twitter.com/TheRespawnabl3s) know something.
## Post #8
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-08T07:11:41+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

> Reply from coriolis14 ↑Sat Aug 26, 2023 9:40 pm at Sat Aug 26, 2023 9:40 pm
>
> 

Hey, glad to see that you're around here too! For the meshes, I've posted this question over in 3D file format forum, and someone found the vertices of the meshes using 3D Model Researcher. Though the faces could not be found, so its just a point cloud so far.

I see that someone is working on a fan-game, though the development seemed to have halted for now, and the discord servers are pretty inactive. I will ask one of the devs if I get the chance.
## Post #9
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2023-09-12T11:48:36+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

Yes!... been wanting to extract assets from this game a couple years ago but to no extent. This really gives me hope again to pursue the extraction. I'm glad that I am not alone on this one.
## Post #10
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-12T17:55:06+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

[viewtopic.php?t=27134](https://forum.xentax.com/viewtopic.php?t=27134)

Bigchillghost has successfully gotten the mesh using AXE. Check it out!
## Post #11
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2023-09-14T13:36:31+00:00
- Post Title: The Respawnables model and texture (.mesh and .tex)

nice one. i'll check this out. thanks.
