## Post #1
- Username: andrewly3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 12, 2021 1:45 am
- Post datetime: 2021-05-11T17:54:06+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

The game is called 1 vs. 100. The online multiplayer game. More about it: [https://en.wikipedia.org/wiki/1_vs._100 ... ideo_game)](https://en.wikipedia.org/wiki/1_vs._100_%282009_video_game%29)

Here's the 3D file I want to open: [https://www.mediafire.com/file/bgc80bxm ... b.bin/file](https://www.mediafire.com/file/bgc80bxmaf6ijw4/1vs100set.mb.bin/file)

Now, in the game's files in the models folder there were these .mb.bin files. The thing is, .mb file is used exclusively for Autodesk Maya, and I think Microsoft did use it when developing the game. But the problem is the .bin extension. Why is there? I can't open the model with Maya, even if I remove the .bin part. The game file 100% isn't corrupted, because I could convert the .xwb soundtrack into normal audio files and play them.

Thanks in advance! I'll provide more information as needed.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-11T19:01:00+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

> Reply from andrewly3 ↑Wed May 12, 2021 1:54 am at Wed May 12, 2021 1:54 am
>
> I can't open the model with Maya, even if I remove the .bin part.Removing the .bin extension? You didn't really expect this could work, did you?  

The bin is a CAFF file which needs to be extracted.
.



gpu.png (38.17 KiB) Viewed 125 times


(uv pos= 16, half floats)
## Post #3
- Username: andrewly3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 12, 2021 1:45 am
- Post datetime: 2021-05-11T20:29:02+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

> Reply from shakotay2 ↑Wed May 12, 2021 3:01 am at Wed May 12, 2021 3:01 am
>
> 
andrewly3 wrote: ↑Wed May 12, 2021 1:54 amI can't open the model with Maya, even if I remove the .bin part.Removing the .bin extension? You didn't really expect this could work, did you?  

The bin is a CAFF file which needs to be extracted.
.
gpu.png
(uv pos= 16, half floats)

Ok, I downloaded the program, I put the exact same numbers as you did, opened the same file, yet when I click "mesh" there's just a mess of triangles and whatever. Btw, would you mind exporting the model you opened and send it, just in case I don't succeed on my own.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-12T09:46:14+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

Read what I wrote: The bin is a CAFF file which needs to be extracted.

Did you extract it?

Find link to possible tool here:

> Reply from shakotay2 ↑Thu Jan 21, 2021 8:41 pm at Thu Jan 21, 2021 8:41 pm
>
>
## Post #5
- Username: andrewly3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 12, 2021 1:45 am
- Post datetime: 2021-05-12T12:20:40+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

> Reply from shakotay2 ↑Wed May 12, 2021 5:46 pm at Wed May 12, 2021 5:46 pm
>
> 
Read what I wrote: The bin is a CAFF file which needs to be extracted.

Did you extract it?

Find link to possible tool here:
shakotay2 wrote: ↑Thu Jan 21, 2021 8:41 pm

Oh, now I downloaded that program, built it with Visual Studio, but can you tell me which command did you use in that program? There are 2: s - dump sections and a - dump files. When I tried both it generated some random files but I'm not sure which one should I open in hex2obj.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-12T14:42:53+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

It's caffextractor s "D:\test\1vs100set.mb.bin" D:\test which creates a subfolder RawSectionDumps with 4 files contained.
The .gpu file is the one in question.
## Post #7
- Username: andrewly3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 12, 2021 1:45 am
- Post datetime: 2021-05-12T18:00:27+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

> Reply from shakotay2 ↑Wed May 12, 2021 10:42 pm at Wed May 12, 2021 10:42 pm
>
> 
It's caffextractor s "D:\test\1vs100set.mb.bin" D:\test which creates a subfolder RawSectionDumps with 4 files contained.
The .gpu file is the one in question.

It works! Here is the .obj file if someone needs it: [https://www.mediafire.com/file/d11vg7zg ... t.obj/file](https://www.mediafire.com/file/d11vg7zgd96vdwa/test.obj/file)

Now I'll try doing the rest of the files...

Thank you!
## Post #8
- Username: andrewly3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 12, 2021 1:45 am
- Post datetime: 2021-05-12T20:51:28+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

> Reply from shakotay2 ↑Wed May 12, 2021 10:42 pm at Wed May 12, 2021 10:42 pm
>
> 
It's caffextractor s "D:\test\1vs100set.mb.bin" D:\test which creates a subfolder RawSectionDumps with 4 files contained.
The .gpu file is the one in question.

By the way, do I use custom settings for other models with the same file extension or can I use the ones I already used? I'm quite a beginner, can you just tell me how did you find the required data? I know that I must use a hex editor, but what I mean are what patterns and numbers and such should I look for in there.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-13T09:14:45+00:00
- Post Title: Opening .mb.bin file from a Xbox 360 game

> Reply from andrewly3 ↑Thu May 13, 2021 4:51 am at Thu May 13, 2021 4:51 am
>
> By the way, do I use custom settings for other models with the same file extensionExcept from the data format (float here), FVFsize and UVpos everything changes. (Sometimes there's different FVFsizes in the same file, though.)  
> I'm quite a beginner, can you just tell me how did you find the required data? I know that I must use a hex editor, but what I mean are what patterns and numbers and such should I look for in there.Read the tutorial ('tut' button in hex2obj). Read Bigchillghost's tutorial (see link in my sig). There's no simple recipe to get patterns and numbers. You need experience for such, read some of the linked threads given here:

> Reply from shakotay2 ↑Tue Oct 22, 2013 10:09 pm at Tue Oct 22, 2013 10:09 pm
>
> 

For getting the start address of face indices blocks search for 000000010002 (big endian here, so different to 000001000200 for little endian).
