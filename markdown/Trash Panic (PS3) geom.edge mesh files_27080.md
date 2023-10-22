## Post #1
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-08T15:16:46+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Hi guys, I am working on reverse engineering the 3d mesh format for an old PS3 game called Trash Panic. I've come quite far but I am completely stumped at the moment. I've attached a screenshot of the hex of one of the easy meshes. 



xentax.png (184.04 KiB) Viewed 211 times



I've already been able to extract the vertices and texture coordinates, but the index array is packed in a format I've never seen before. In the screenshot I have highlighted the index array. D means 2 triangles out of 4 vertices and F means 2 triangles out of 6 vertices. i.e.:
    NibbleAction(  0,  1,  2,     2,  1,  3,     4),   // D
    NibbleAction(  0,  1,  2,     1,  0,  3,     3),   // E
    NibbleAction(  0,  1,  2,     3,  4,  5,     6),   // F
18 points to the actual offset of the first triangle, the count starts from offset 0x108
Note all the zeroes that precede it, in other meshes, these bytes have can have values and they affect the triangles.
I've written a preliminary parser in C++ ([https://github.com/BlackStar-EoP/geomparse](https://github.com/BlackStar-EoP/geomparse)) which can already parse quite a bit
as long as the pre-face data only contains zeroes. As an added bonus, it seems that nibbles can also influence each other's behavior:
        case 0x0E:
            add_tris(action, v, nib);
            nibble_actions[0x1].SetTri1(-2, 0, 1);
            nibble_actions[0x1].SetTri2(1, 0, 2);
            nibble_actions[0x7].SetVertexInc(5);
Has anyone ever seen anything like this? For reference, I have modified RPCS3 to be able to dump memory, therefore I have the output
of these arrays for quite a bunch of meshes, but it still doesn't make sense at all...

Attached are 2 meshes, one is from the screenshot. The other is a hamburger. It already has working .obj files since I ripped the index array from the PS3's memory.


If anyone can shed a bit of light on this obscure way of storing index arrays it would be greatly appreciated!
## Post #2
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-08T15:22:46+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Stage1Dmp_Correct.zip
(220.23 KiB) Downloaded 18 times



Somehow the other attachment couldn't be added to the OP, anyway here it is. It contains several .geom.edge files with the wavefront obj.
All of these were generated with the geomparse tool I linked on github.

To clarify a bit, the IDX files that are present are handmade, I made those using the dumps from the system memory. I've managed to alter the decoder to match a lot of them (especially the monolith ones) but I haven't got a clue about the data that precedes the index array, and the bytes that come after it in some meshes. It seems like the pre-face and post-face data contains backreferences to earlier vertices somehow.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-08T20:51:47+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Hi, welcome back to the forum after a year and 7 months!  

I compiled your source; after adjusting the files.push_back() path it created an mtl file.

allWithout.txt is an input file? How should its contents look like?
## Post #4
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-08T21:18:33+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Hey, I could post that file here but it has 2000 entries that list all the files that have no preface data and only 1 model, this is how I wanted to determine the lookup nibbles 

However, on discord I got a tip from someone to look into the PS Edge format, and after jumping through some hoops and reading a lot of forum posts, I am now looking at some source code for decompressing the PS Edge geometry! 

Seems like it's not just a 'nibble' format, it deals with a delta array and a triangle array, which is variable bit...

edit: oh and apologies for the mess in that codebase, it's just tinkering so I don't clean up properly
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-08T22:50:55+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

> Reply from BlackStarEOP ↑Wed Aug 09, 2023 5:18 am at Wed Aug 09, 2023 5:18 am
>
> , I am now looking at some source code for decompressing the PS Edge geometry!Sony's edge compression? Was mentioned here (click up arrow):

> Reply from shakotay2 ↑Tue Jun 25, 2019 8:56 pm at Tue Jun 25, 2019 8:56 pm
>
>
## Post #6
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-09T07:20:14+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

> Reply from shakotay2 ↑Wed Aug 09, 2023 6:50 am at Wed Aug 09, 2023 6:50 am
>
> 
BlackStarEOP wrote: ↑Wed Aug 09, 2023 5:18 am, I am now looking at some source code for decompressing the PS Edge geometry!Sony's edge compression? Was mentioned here (click up arrow):
shakotay2 wrote: ↑Tue Jun 25, 2019 8:56 pm

Yup that is the thread I got from DKDave as well, unfortunately my python skills are non-existent so I'm continuing in geomparse.cpp, it seems the data is stored a bit differently but at least I have a very good lead now. 
Thanks for the help!
## Post #7
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-09T11:36:09+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Took a bit of tinkering, but it's working!



6c19d29e-6697-43ce-859d-8f05ffee37d2.jpg (155.52 KiB) Viewed 149 times



I will update the code soon (tm) but for now I am extremely happy.
Seems I was pretty far with understanding how this compressed index array works I just couldn't correlate the 1 bit and var bit arrays.

Thank you again for your help shakotay2!
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-10T21:08:09+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

> Reply from BlackStarEOP ↑Wed Aug 09, 2023 7:36 pm at Wed Aug 09, 2023 7:36 pm
>
> 
I will update the code soon (tm)That would be extremely cool.  (Since I don't know any source code except the original from Sony.)
## Post #9
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-12T20:04:23+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

> Reply from shakotay2 ↑Fri Aug 11, 2023 5:08 am at Fri Aug 11, 2023 5:08 am
>
> 
BlackStarEOP wrote: ↑Wed Aug 09, 2023 7:36 pm
I will update the code soon (tm) That would be extremely cool.  (Since I don't know any source code except the original from Sony.)

Code is updated! I've tested it on all the geom.edge files and it parses everything without any issues. The only thing missing is another block in the geom.edge but so far I haven't needed it (possibly normals/tangent vectors?)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-12T22:37:37+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Thanks!
How does one extract the vertices and indices of one single geom.edge, say MONOLITH_L_break_break_1.geom.edge?

When I uncomment //#define DECODE_ONLY
the code doesn't compile.
## Post #11
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-14T11:07:48+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

If you compile it in release mode, the executable takes a commandline argument, so it would be
"geomparse MONOLITH_L_break_break_1.geom.edge"

decode only was made for debugging purposes, it doesn't overwrite the wavefront obj/mtl.
weird that it doesn't compile on your side... it does here, just committed latest code.

Be sure to have both the geom.edge and mat.edge in the same directory, I haven't put any protection around that
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-14T13:47:26+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Thank you! Seems, during my tests, MONOLITH_L_break_break_1.geom.edge0.obj had already been created and I've overlooked it merely. 
.



monolith.png (38.68 KiB) Viewed 101 times
## Post #13
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-16T09:58:59+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Nice!

I just updated the code, normalmaps should be working now (still untested) and I parsed the second float block, seems to have the normals, they are not normalized so I normalized them and they appear to look good.
## Post #14
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2023-08-16T11:39:24+00:00
- Post Title: Trash Panic (PS3) geom.edge mesh files

Normals are functioning fine it seems.
As for the normalmap, it does store it in the material file, but there are no tangent/binormals present in the mesh itself, not sure how PS Edge handles this but at least the bulk of the files is decoded now

edit:
Seems the normals are not correct, I'll continue to investigate
