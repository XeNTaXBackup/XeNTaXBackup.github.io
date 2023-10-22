## Post #1
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2019-08-18T23:41:06+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Hello! Could I get help with hex2obj settings for Frogger The Great Quest's models? I'll upload an example below.

I happen to have a model ripped with NinjaRipper, however I'm not actually sure which file is that model in the games files.

So, I'm asking here for help. Thanks!


File (Big mushroom): [https://www.dropbox.com/s/yximlybydgiqo ... G.VTX?dl=0](https://www.dropbox.com/s/yximlybydgiqoyc/MUSHBIG.VTX?dl=0)
## Post #2
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2019-08-18T23:49:35+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Update! It turns out, I do actually have a side-by-side comparison between a .obj model and a .vtx model. I've attached it below.


 Frogger.zip
(255.32 KiB) Downloaded 26 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-19T08:20:03+00:00
- Post Title: Frogger The Great Quest 3D Model Format

once you have the FVFsize you can get a decent point cloud but I don't have a clue about the face indices (FIs), might be quads?
.



3725-vtx.png (60.05 KiB) Viewed 210 times
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-19T11:39:23+00:00
- Post Title: Frogger The Great Quest 3D Model Format

frogger.png (47.91 KiB) Viewed 208 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-19T11:55:41+00:00
- Post Title: Frogger The Great Quest 3D Model Format

yeah, great! (I was sure the FVFsize to be 136  )
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-19T12:39:26+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Wasn't sure about the FVFsize. So I looked for the vertex count at 0x20, which happened to be two times of yours.

It's interesting that the method I used to generate dummy indices for AMR also work with this case. Might consider adding similar features in the future.



frogger_amr.png (84.25 KiB) Viewed 204 times
## Post #7
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2019-08-19T23:05:22+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Hey! Thank you so much for the help. I don't know how you're able to figure this out so fast. I'll have a program to fully read these models soon.
## Post #8
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2019-08-25T02:37:14+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Another quick question. What was the "Fake" button in your hex2obj screenshot? I can't seem to make that happen.

Also! I believe this is a 3D model for a map. Could you assist in finding the 3D data for it? Thanks again!

[https://www.dropbox.com/s/unw56ic1ksbrmis/20.zip?dl=0](https://www.dropbox.com/s/unw56ic1ksbrmis/20.zip?dl=0)
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-25T04:23:27+00:00
- Post Title: Frogger The Great Quest 3D Model Format

All objects loaded into Noesis:



allObjs.png (116.71 KiB) Viewed 171 times
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-25T04:25:06+00:00
- Post Title: Frogger The Great Quest 3D Model Format

The Noesis python script for this file:


 fmt_FroggerTheGreatQuest_TOC.zip
(901 Bytes) Downloaded 22 times



You'll find everything you need inside the code.
## Post #11
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-03-28T01:48:39+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Alright guys, it's been a while. 

I've managed to use information from here + information I've figured out myself to create a model exporter which mostly works.
However, there's a good 30% of models where the faces are all wrong.

I have uploaded two models, one where faces work properly and one where they don't. Does anyone have any ideas why the faces are wrong?





Download Link: [https://drive.google.com/open?id=1DCmHH ... k2t8C77wBf](https://drive.google.com/open?id=1DCmHHvkJDz7k8hdHyBCCJVk2t8C77wBf)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-28T07:06:56+00:00
- Post Title: Frogger The Great Quest 3D Model Format

> Reply from Kneesnap ↑Sat Mar 28, 2020 9:48 am at Sat Mar 28, 2020 9:48 am
>
> I have uploaded two models, one where faces work properly and one where they don't. Does anyone have any ideas why the faces are wrong?Fish uses autocreated linear face indices, dragon uses tristrips, obviously. It's a matter of a suiting triangle strips algorithm:
.



triStrips.png (150.61 KiB) Viewed 110 times


This one I called "Noesis TriStrips" (guess because I found similar faces in obj created by Noesis  ).
But it's not perfect, some superfluous faces need to be deleted manually. (Removing double vertices is a good idea, too.)

Should be possible to write a simple Noesis script to solve this.
Example to be found here:

> Reply from shakotay2 ↑Sat Mar 14, 2020 5:04 am at Sat Mar 14, 2020 5:04 am
>
> 
(Problem is the autocreation of the strips - I don't have a simple solution here - I'd append a binary index buffer to the .vtx file. )

well, no, why not use existing solutions?
Use hex2obj (surpise!  ) then append the face indices as a txt file:

0x0 500
Vb1
68 48
0x5D8 4780
021000
0x0 255

(btw: when you drag'n drop the resulting beast onto Noesis you'll need to enable face cull (F4) or you'll see some holes in the mesh.)
## Post #13
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-03-28T07:55:33+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Damn. You guys are awesome, whenever I get stuck you guys are always able to point me in a helpful direction.
I'll check this out. I guess my problem going forward will be that I'm hoping to be able to do this automatically in my extractor while also preserving UV values. It seems like that'll be doable once I understand how the algorithm works though.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-28T08:07:21+00:00
- Post Title: Frogger The Great Quest 3D Model Format

> Reply from Kneesnap ↑Sat Mar 28, 2020 3:55 pm at Sat Mar 28, 2020 3:55 pm
>
> It seems like that'll be doable once I understand how the algorithm works though.Pmed you. (In case you'll manage to improve the uvs here I'd be interested in the "how to" .  )
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-04-07T18:10:39+00:00
- Post Title: Frogger The Great Quest 3D Model Format

Kneesnap,

Did you cut the first 8 bytes from the evilfish.vtx and dragon.vtx files?

The 3725.vtx and MUSHBIG.VTX files have the '6YTV' id (4 bytes) and the (about) file size value (4 bytes).

I have extracted the files from the data.bin file with the frogger_great_quest.bms, but all of the .vtx files have the  '6YTV' id (4 bytes) and the (about) the file size value (4 bytes).
## Post #16
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-04-07T23:04:58+00:00
- Post Title: Re: Frogger The Great Quest 3D Model Format

> Reply from Karpati ↑Wed Apr 08, 2020 2:10 am at Wed Apr 08, 2020 2:10 am
>
> 
Kneesnap,

Did you cut the first 8 bytes from the evilfish.vtx and dragon.vtx files?

The 3725.vtx and MUSHBIG.VTX files have the '6YTV' id (4 bytes) and the (about) the file size value (4 bytes).

I have extracted the files from the data.bin file with the frogger_great_quest.bms, but all of the .vtx files have the  '6YTV' id (4 bytes) and the (about) the file size value (4 bytes).

I don't know entirely what your question is, but yes. 6YTV is a chunk header, along with the 4 trailing bytes being the size. This is automatically read and handled by the file parser.
## Post #17
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-04-08T16:06:27+00:00
- Post Title: Re: Frogger The Great Quest 3D Model Format

The evilfish.vtx and dragon.vtx files you uploaded have not the '6YTV' id (4 bytes) and the file size value (4 bytes).

I don't know why?
## Post #18
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-04-08T18:01:38+00:00
- Post Title: Re: Frogger The Great Quest 3D Model Format

> Reply from Karpati ↑Thu Apr 09, 2020 12:06 am at Thu Apr 09, 2020 12:06 am
>
> 
The evilfish.vtx and dragon.vtx files you uploaded have not the '6YTV' id (4 bytes) and the file size value (4 bytes).

I don't know why?

It's because I have a file parser which parses all of the files in the game now. That 6YTV is a chunk identifier, and I just uploaded the chunk data itself.
## Post #19
- Username: JamesBone
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jan 08, 2022 4:43 pm
- Post datetime: 2022-01-15T10:16:21+00:00
- Post Title: Re: Frogger The Great Quest 3D Model Format

> Reply from Kneesnap ↑Mon Aug 19, 2019 7:41 am at Mon Aug 19, 2019 7:41 am
>
> 
Hello! Could I get help with hex2obj settings for Frogger The Great Quest's models? I'll upload an example below.

I happen to have a model ripped with NinjaRipper, however I'm not actually sure which file is that model in the games files.

So, I'm asking here for help. Thanks!


File (Big mushroom): https://www.dropbox.com/s/yximlybydgiqo ... IG.VTX?dl=0

Yeah I'm wondering this too
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-15T11:25:34+00:00
- Post Title: Re: Frogger The Great Quest 3D Model Format

@JamesBone: using hex2obj requires some basic understanding of 3D model formats.
Did you try the Noesis script from Bigchillghost?

btw: quoting a thread's first post whose issue has already been solved (more or less) doesn't make sense somehow, does it?
