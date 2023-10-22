## Post #1
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2018-01-13T18:17:24+00:00
- Post Title: Help with UVs

Hi there,

anyone has an idea how the structure for UVs could be for the attached file? 

The UVs begin at 0x6E78.

[/quote]

Any help appreciated!

Thanks
[messer2.7z](https://xentaxbackup.github.io/file/13796_messer2.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-14T10:48:19+00:00
- Post Title: Help with UVs

this looks like uvs; not sure how to unscramble them atm:



messer_uvs.jpg (127.22 KiB) Viewed 87 times


(well - done; had to subtract 1.0 from every uv value > 0.5)
## Post #3
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2018-01-14T13:56:40+00:00
- Post Title: Help with UVs

> Reply from shakotay2
>
> this looks like uvs; not sure how to unscramble them atm:
messer_uvs.jpg
(well - done; had to subtract 1.0 from every uv value > 0.5)

Thank you! Im very impressed.
However, i can not rebuild das, with your tool. Can you tell me, which i settings exactly i have to chose to get that result? i already get corrupt data for "go2".

Also: How did you find out to subtract 1.0 for every UV value > 0.5?

Thanks!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-14T15:46:07+00:00
- Post Title: Help with UVs

> Reply from Ginsor
>
> However, i can not rebuild das, with your tool.with hex2obj you get the left part of the image in my previous post when pressing the 'uvs' button.

(I temporary inserted the (if (uvpos>0.5) condition) into the code to get the right part of the image.)

> Also: How did you find out to subtract 1.0 for every UV value > 0.5?it's one of those tricks you learn after having analyzed hundreds of 3D formats.
## Post #5
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2018-01-14T16:29:44+00:00
- Post Title: Help with UVs

> Reply from shakotay2
>
> I temporary inserted the (if (uvpos>0.5) condition) into the code to get the right part of the image.)
Oh i see, so I cant rebuild it! Then I need to find a way to build an .obj for that somehow. Any idea how I could achieve that? 

> Reply from shakotay2
>
> it's one of those tricks you learn after having analyzed hundreds of 3D formats.
Haha, I get that. Thank you, it is a very useful info.
Also, why is your count 753? Shouldnt it be 1761?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-14T17:04:16+00:00
- Post Title: Help with UVs

> Reply from Ginsor
>
> shakotay2 wrote:I temporary inserted the (if (uvpos>0.5) condition) into the code to get the right part of the image.)
Oh i see, so I cant rebuild it! Then I need to find a way to build an .obj for that somehow. Any idea how I could achieve that?In hex2obj switch to ShortAll, then File / SaveAs mesh
Load the created obj file into a calculation app (Excel or so), blank as a separator , for the vt lines you should get three columns for "vt", tx and ty. Select the tx column apply a formulae which expresses the above conditon (same for ty column), save the changed table and you're done (more or less).

> Also, why is your count 753? Shouldnt it be 1761?Maybe; didn't check that. I care for the first submesh only in most cases.
## Post #7
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2018-01-15T07:14:25+00:00
- Post Title: Help with UVs

> Reply from shakotay2
>
> Ginsor wrote:shakotay2 wrote:I temporary inserted the (if (uvpos>0.5) condition) into the code to get the right part of the image.)
Oh i see, so I cant rebuild it! Then I need to find a way to build an .obj for that somehow. Any idea how I could achieve that? In hex2obj switch to ShortAll, then File / SaveAs mesh
Load the created obj file into a calculation app (Excel or so), blank as a separator , for the vt lines you should get three columns for "vt", tx and ty. Select the tx column apply a formulae which expresses the above conditon (same for ty column), save the changed table and you're done (more or less).
Yea, I did that even before reading your post. Came to my mind as well haha, thanks! When i imported it to blender it still looked messed up tho! I will give it another try tonight when i get home, but in my first attemp the UV map in blender looked not right.

> Reply from shakotay2
>
> Ginsor wrote:Also, why is your count 753? Shouldnt it be 1761?Maybe; didn't check that. I care for the first submesh only in most cases.
Wait, you can see that there are submeshes inside? Sorry, Im a little lost now. For me it all looks like just one big mesh with 1761 counts for vertics and UVs.
Thanks for all your help tho! I appreciate it a lot.
