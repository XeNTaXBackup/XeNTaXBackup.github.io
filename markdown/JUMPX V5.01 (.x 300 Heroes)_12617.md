## Post #1
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2015-02-19T04:57:15+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

Hi there, i've been trying to take a look of this file format which seems to have everything inside(bones, skins, geometry, even a description?)

This is a model format used in the lol fake chinese game, and i thought it would be easy to try this format out  but i'm still a noob at this and the scn format was easier than this probably.

For now i've only figured out the header but i can't manage to continue it.



From what it looks it seems like it's a chunk binary file and describes the component of the files with tags such as ntex and atex, although most of the .x have the same, some of them don't have the "mtsi" at the end...

Here is a log of the header of 5v_lfti01a.x -> [http://puu.sh/g3fuU/cde8194aaf.txt](http://puu.sh/g3fuU/cde8194aaf.txt)  (used [this maxscript](http://puu.sh/g3fCW/2c31247d1e.txt))
It's logged until the grey part of the previous picture, which is what i understand until the pile of garbage kicks in.

Looks like a lot of flags going in before starting, and probably it's reading in the same order than they are listed there, howevern ot all of them have the same amount of flags so it's kind of confusing.

Also seems like the format author is in this website according to the file: [http://tw.weibo.com/wuyaxit](http://tw.weibo.com/wuyaxit) i don't know chinese but i guess so since it has 300H stuff. Also Jumpw.com seems to be the website of the 300 heores devs or publishers.

i'm still noob at reading this kind of stuff so i provided all can and hopefully someone can give me a little guideline to go foward.

I packed a lot of .x that i have no clue what they are, they are probably buildings or little meshes from the enviroment, i could put the characters in, but that's too complex for now i guess(which makes sense hwy most of the flags are 0 in the case they are flags in the first place?).

If i figure out something i'll post it here eventually, hopefully i'll bring something(or not, probably, but i'll try my best to :C)

Thanks in advance
Seyren  
[5v5s.rar](https://xentaxbackup.github.io/file/8703_5v5s.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-19T10:46:39+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

using offzip -a 5v_lfti01a.x D:\extracted 0 
creates two files in the folder extracted, 00000194.wuy and 00000317.neo
The .neo file contains this flat point cloud:



317_neo_ptCloud.JPG (11.05 KiB) Viewed 646 times
## Post #3
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2015-02-19T19:11:09+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

Oh wow, didn't think about that program, thanks 

It's the first time though i've seen a file inside a file, since i can't gather of this information on the .x file, it's some sort of encryption? damn, this is too much for me.

However everything seems way clearer on the .neo file, since you can see the Vertices, faces, etc by just looking at them, and we can clearly see everythingi s there, but i can't manage to find the count to arrange the loops.

I'm not even sure if i find everything at all since i tried to see how many bytes the vertex buff had and it's a total of 3392, which probably is mistaken since either not only this has to be a giant mesh with 1k vertices, but also we can't divide it by 3, being the result  1130,66. so something is wrong. 

I tried by looking at the numbers that the .x provided such as the values from the ngeo or ageo, but they are too low (272) to be it, the closest i found was 882.

The only clue i have has to be that there are two things together which would explain the pair number.
However, what i noticed is that there is a 3 on the .x filed with the "ngeo" tag behind it and there is indeed 3 meshes there by looking at it, so it's probably the number of meshes inside the  neo. It ends up with a |GE:TERRAIN which i don't really know what that means.

I'll keep looking and see if i manage to get the count from somewhere, no wonder i couldn't find anything related to mesh, i  would never have figured out to use offzip, thanks
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-19T19:51:01+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

> Reply from Seyren
>
> it's some sort of encryption?it's zlib compression. I think, offzip just searches for 0x78 0x9C to find the start of compressed data in a file.

In 00000317.neo there seems to be about 106 normals starting from 0x5CC. Maybe use this info to structure the file.
well, got it: it's 106 vertices (3x float) from 0xD4:



317_neo.JPG (18.15 KiB) Viewed 626 times


uvs to follow at AC4, here's the H2O file for hex2obj (view link in my sig):
0xE78 288
Vb1
12 99
0xD4 106
020000
0xAC4 8
## Post #5
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2015-02-20T18:59:48+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

Then i guess we'll have to scratch making a simple maxscript for this format.

Also, did you find the actual counts or you managed to get it by trial and error? just curious to get information about it, since the only place where there is an int with 106 is in the .wuy file in 012C, so maybe we'll have to read both formats to get the whole thing?

Sorry for asking too many questions, it's kind of confusing for me while trying to figure out how it works...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-20T19:20:03+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

> Reply from Seyren
>
> Then i guess we'll have to scratch making a simple maxscript for this format.yeah; sadly I'm too busy with my info viewer project atm.

> Also, did you find the actual counts or you managed to get it by trial and error?neither/nor. I calculated the face indices count from face index start/stop addresses.
Then hex2obj gives me the max face index which is equal to the vertex count.

> since the only place where there is an int with 106 is in the .wuy file in 012C, so maybe we'll have to read both formats to get the whole thing?yep, at 0x130 is the faces count (96 dec.)

> Sorry for asking too many questions, ...there's no reason to apologize...
## Post #7
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-29T03:59:43+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

> Reply from shakotay2
>
> using offzip -a 5v_lfti01a.x D:\extracted 0 
creates two files in the folder extracted, 00000194.wuy and 00000317.neo
The .neo file contains this flat point cloud:
317_neo_ptCloud.JPG
What settings do you make to export .obj file and send to 3ds max ？
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-29T08:14:59+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

copy the 6 lines of the H2O in the post as of Thu Feb 19, 2015 8:51 pm
into a text file and name it whatever.H2O.

Load 00000317.neo into hex2obj then load the H2O file; press the 'mesh' button
to view the model. Chose File/SaveAs mesh to save it as wavefront obj file.
## Post #9
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-29T08:25:21+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

> Reply from shakotay2
>
> copy the 6 lines of the H2O in the post as of Thu Feb 19, 2015 8:51 pm
into a text file and name it whatever.H2O.

Load 00000317.neo into hex2obj then load the H2O file; press the 'mesh' button
to view the model. Chose File/SaveAs mesh to save it as wavefront obj file.

I open the second file and save a H2O file, then I load two files by order, but when I press the 'mesh' button it has a message box:
Vertex count must be set to: max face index!
Check/use value in lower left listbox.
(Did you start with go1? - if 'no': read the tut!)
and there is no .obj file.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-29T09:13:59+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

0317_neo.jpg (140.31 KiB) Viewed 489 times


00000317_0.obj

# 0xd4: verts= 106
v -136.746155 -204.175385 2.417484 
v -69.989868 -209.845551 2.235855 
v -72.402130 -196.968994 4.839732 
v -144.479553 -191.604721 4.848117 
v -136.746155 -204.175385 2.417484 
v -165.678162 -181.877960 6.129420 
[...]
v 31.941174 52.069206 27.534113 
v -37.753925 52.069195 27.534088 
v -32.578964 44.346493 41.994495 
# 0x5cc
# 0xac4 (UVBlockSize= 8 )
vt 0.203178 0.985251 
vt 0.453629 0.985000 
vt 0.390534 0.923255 
vt 0.156111 0.923243 
vt 0.203178 0.985251 
vt 0.086631 0.902907 
[...]
vt 2.127676 0.635169 
vt 2.108288 0.680525 

# 0xe78: faceIndices= 288, triangles= 96
g submesh_0
f 1/1 1/1 1/1 
f 1/1 2/2 3/3 
f 3/3 4/4 1/1 
f 5/5 6/6 7/7 
f 7/7 8/8 5/5 
f 9/9 10/10 11/11 
[...]
f 96/96 104/104 105/105 
f 105/105 106/106 96/96
## Post #11
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-29T09:47:26+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

Sorry, Failed!
[up.png](https://xentaxbackup.github.io/file/10234_up.png)
## Post #12
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-29T10:20:49+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

If you can get the right result by using this file, could you send me your tools -- offzip and hex2obj ?
[5v_lfti01a.zip](https://xentaxbackup.github.io/file/10235_5v_lfti01a.zip)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-29T10:49:14+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

Did you have a look at the picture I posted?
Guess you didn't.

Have a look at the picture you posted.
Does it look like the one I posted?
Obviously not.

(Enter the values manually or load the H2O file to have the same values in the editboxes.)

Why do I have the strange feeling that your kidding me?  

btw: I'm using hex2obj v0.24c. Should be the same as the one you're using (though it looks a little bit different).
## Post #14
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-29T11:21:55+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

Oh, I'm so sorry.
I just think the data is got automatically:
0xE78 288
Vb1
12 99
0xD4 106
020000
0xAC4 8
I open the .neo file, and save the .h2o file, but the file:
0x0 500
Vb0
0x0
0x0 500
020000
0x0 255
Can you tell me how to get the data ?
Please, sincere.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-29T12:31:33+00:00
- Post Title: JUMPX V5.01 (.x 300 Heroes)

what you save is what you see (in the editboxes)

ok, here's the H2O file:


 00000317_0.zip
(174 Bytes) Downloaded 45 times
## Post #16
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-29T13:12:03+00:00
- Post Title: Re: JUMPX V5.01 (.x 300 Heroes)

Thank you very much.
I'm not a English speaker, so I can't read and understand English well.
I read the FAQ of hex2obj and I have found something I missed. I'm so sorry for my careless.
I'm now trying to learn how to use the tool.
Thanks again.
## Post #17
- Username: plgkm6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 29, 2015 11:23 am
- Post datetime: 2015-12-30T01:29:21+00:00
- Post Title: Re: JUMPX V5.01 (.x 300 Heroes)

The first 84 bytes is meaningless content -- the file header and some chinese, url and etc.
Then 4 bytes means the number of bytes in the following -- the 4 bytes of word and 8 bytes something.
And next is 4bytes*4: file1 unzip size, file2 unzip size, file1 zip size and file2 zip size.
Finally, there are two offzip file.
I'm a Chinese and my English is not very well.
