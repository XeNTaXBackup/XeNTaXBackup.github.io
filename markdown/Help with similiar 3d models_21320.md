## Post #1
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-10-30T19:49:03+00:00
- Post Title: Help with similiar 3d models

Here are two samples of fifa head models. One is from fifa 16, the other from fifa online 4. I've noticed that the models, are similiar. So I tried to import fifa online 4 head model into game, but the head is a bit strange. So I tried to export the model using HxD edtor, but I know where to start.
Please help:
[https://www.mediafire.com/file/h7w2sfqc ... s.rar/file](https://www.mediafire.com/file/h7w2sfqc5he88ko/3d_models.rar/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-31T02:50:11+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Thu Oct 31, 2019 3:49 am at Thu Oct 31, 2019 3:49 am
>
> 
but I know where to start.
A writing mistake? 

Extraction with AMR:
(head_330_0.rx3)



head_330_0.png (99.74 KiB) Viewed 234 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-31T03:15:26+00:00
- Post Title: Help with similiar 3d models

head_41_0.rx3



head_41_0.png (84.7 KiB) Viewed 232 times




So the eyebrows and the head are stored in an opposite order in the two files.
## Post #4
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-10-31T08:35:56+00:00
- Post Title: Help with similiar 3d models

> Reply from Bigchillghost ↑Thu Oct 31, 2019 10:50 am at Thu Oct 31, 2019 10:50 am
>
> 
greenlemonade1 wrote: ↑Thu Oct 31, 2019 3:49 am
but I know where to start.

A writing mistake? 

Extraction with AMR:
(head_330_0.rx3)
head_330_0.png

Yes, it was a mistake. So I copy the offset from 0x830 to ox9524 from head_41, and where is the beginn in head_330? No need to convert endians?
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-31T13:18:58+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Thu Oct 31, 2019 4:35 pm at Thu Oct 31, 2019 4:35 pm
>
> 
So I copy the offset from 0x830 to ox9524 from head_41, and where is the beginn in head_330? No need to convert endians?
They're all in little-endian but I doubt it'll work by directly replacing the geo data. But you can try of course.
At offset 0x360 in both files, you'll see they share the following structure:



block.png (38.28 KiB) Viewed 206 times


The first 4-byte integer indicates the size of this chunk. Find the block in the other file of the same size and do your replacements repeatedly untill the size of the block equals to 4. Basically every two blocks are swapped in different files, like in head_330 you have

```
block2
block3
block4
...

```

and in head_41 you'll have

```
block1
block4
block3
...

```
## Post #6
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-10-31T17:14:07+00:00
- Post Title: Help with similiar 3d models

> Reply from Bigchillghost ↑Thu Oct 31, 2019 9:18 pm at Thu Oct 31, 2019 9:18 pm
>
> 
greenlemonade1 wrote: ↑Thu Oct 31, 2019 4:35 pm
So I copy the offset from 0x830 to ox9524 from head_41, and where is the beginn in head_330? No need to convert endians?

They're all in little-endian but I doubt it'll work by directly replacing the geo data. But you can try of course.
At offset 0x360 in both files, you'll see they share the following structure:
block.png
The first 4-byte integer indicates the size of this chunk. Find the block in the other file of the same size and do your replacements repeatedly untill the size of the block equals to 4. Basically every two blocks are swapped in different files, like in head_330 you have
Code: Select allblock1
block2
block3
block4
...

and in head_41 you'll have
Code: Select allblock2
block1
block4
block3
...

I tried to copy geo data, but no results. I don't understand the part the do replacements until the size of block equals to 4. I appreciate your help, so much.
## Post #7
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-01T19:28:18+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Thu Oct 31, 2019 4:35 pm at Thu Oct 31, 2019 4:35 pm
>
> 
Bigchillghost wrote: ↑Thu Oct 31, 2019 10:50 am
greenlemonade1 wrote: ↑Thu Oct 31, 2019 3:49 am
but I know where to start.

A writing mistake? 

Extraction with AMR:
(head_330_0.rx3)
head_330_0.png



Yes, it was a mistake. So I copy the offset from 0x830 to ox9524 from head_41, and where is the beginn in head_330? No need to convert endians?
I tried to replace, but I didn't have a success. I convert head using blender for fifa15, but I noticed when I convert models using cm16, some edges are missplaced, or mouth vertices. I copied geo data from fifa15 to converted head but, but then bugs came. What can you tell me, about this 2 models, is there a easier way to fix converted head (fifa16) or copy blocks from fifa15 to fifa16 in this files. Cheers
[https://www.mediafire.com/file/b2rbwp11 ... y.rar/file](https://www.mediafire.com/file/b2rbwp117ahaw92/easier_way.rar/file)
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-02T10:09:45+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Sat Nov 02, 2019 3:28 am at Sat Nov 02, 2019 3:28 am
>
> 
I convert head using blender for fifa15, 
but I noticed when I convert models using cm16, some edges are missplaced, or mouth vertices. I copied geo data from fifa15 to converted head but, but then bugs came.
Not sure I understood what you said here. You mean you exported the edited model from blender to a certain 3d format and then used cm16(not that I know what it is) to convert this exported format to rx3?

> Reply from greenlemonade1 ↑Sat Nov 02, 2019 3:28 am at Sat Nov 02, 2019 3:28 am
>
> 
What can you tell me, about this 2 models, is there a easier way to fix converted head (fifa16) or copy blocks from fifa15 to fifa16 in this files.
As far as I can see, they're using the same format, except that the chunks are placed in a different order. Take your previous samples for example:



cmp.png (46.3 KiB) Viewed 174 times


The 4-byte integer after the the chunk offset represents the chunk size. As you can see, every two size fields in a rectangle is swapped in the other file, causing the differences on the offset fields when the two sizes are not equal. And forget the part about replacing the chunk repeatedly untill the first 4-byte integer equals to 4(when you're at the chunk marked by the black rectangle in the screenshot), since there're more chunks comming after, which're also swapped. I don't know why you'd ever need to replace the file with data from another file, since they're using the same format. And if it's because the size of the file needs to be constant, this whole replacing thing can work either coz there're data that do not map with size of the corresponding block in the other file.
## Post #9
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-02T14:46:55+00:00
- Post Title: Help with similiar 3d models

> Reply from Bigchillghost ↑Sat Nov 02, 2019 6:09 pm at Sat Nov 02, 2019 6:09 pm
>
> 
greenlemonade1 wrote: ↑Sat Nov 02, 2019 3:28 am
I convert head using blender for fifa15, 
but I noticed when I convert models using cm16, some edges are missplaced, or mouth vertices. I copied geo data from fifa15 to converted head but, but then bugs came. 
Not sure I understood what you said here. You mean you exported the edited model from blender to a certain 3d format and then used cm16(not that I know what it is) to convert this exported format to rx3?
greenlemonade1 wrote: ↑Sat Nov 02, 2019 3:28 am
What can you tell me, about this 2 models, is there a easier way to fix converted head (fifa16) or copy blocks from fifa15 to fifa16 in this files. 

As far as I can see, they're using the same format, except that the chunks are placed in a different order. Take your previous samples for example:
cmp.png
The 4-byte integer after the the chunk offset represents the chunk size. As you can see, every two size fields in a rectangle is swapped in the other file, causing the differences on the offset fields when the two sizes are not equal. And forget the part about replacing the chunk repeatedly untill the first 4-byte integer equals to 4(when you're at the chunk marked by the black rectangle in the screenshot), since there're more chunks comming after, which're also swapped. I don't know why you'd ever need to replace the file with data from another file, since they're using the same format. And if it's because the size of the file needs to be constant, this whole replacing thing can work either coz there're data that do not map with size of the corresponding block in the other file.

My goal is just to fix these vertices, expecially on the back head, and mouth. While after the conversion with cm16,  a tool that  automatically convert fifa15 model, but some vertices are missplaced afterwards. I converted perfectly fifa14 head with blender, but on the other hand, the fifa15 converted model can't be open with blender, with fifa15 python scripts.



2 meshes.PNG (63.58 KiB) Viewed 166 times
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-03T02:31:32+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Sat Nov 02, 2019 10:46 pm at Sat Nov 02, 2019 10:46 pm
>
> My goal is just to fix these vertices, expecially on the back head, and mouth. While after the conversion with cm16,  a tool that  automatically convert fifa15 model, but some vertices are missplaced afterwards. I converted perfectly fifa14 head with blender, but on the other hand, the fifa15 converted model can't be open with blender, with fifa15 python scripts.
You seem to add more details, yet it still didn't answer my qusetions, but makes things more confusing.

In the first place you were trying to convert an FIFA Online 4 head to FIFA16, while now you intend to port an FIFA15 head to FIFA16, am I correct?
Now about this "cm16" tool, when said "automatically convert fifa15 model", you meant convert to FIFA16 rx3 file? That's how you got the file "head_246_0.rx3" in folder "fifa converted head", isn't it?

When you said "convert head using blender", given the fact that you just memtioned about these "fifa15 python scripts"(not one script?), I assume they're import scripts compatible at least for FIFA14, FIFA15 and FIFA16 rx3 files, right?

And when you tried to import this "fifa15 converted model", which is now in an FIFA16 "format", you said it "can't be open with blender", but I've checked that file, which has exactly the same structure and chunk order as "head_330_0.rx3", your previous "fifa 16 face" sample. And this, is against to the assumption that the "fifa15 python scripts" are compatible for FIFA16 rx3 files, hence against to your attempt to import the file back with those scripts, if you're aware of the fact. Then how did you get the "2 meshes" into blender and "noticed some edges are missplaced"?

So why don't you make things easier so people don't have to guess what's happening? And please stop quoting the entire post, it's really messy and confusing for what you're trying to comment on.

Anyway regard to your problem that "some edges are missplaced, or mouth vertices", I exported both head_15_1.rx3 and head_246_0.rx3 with AMR and imported them into 3Ds Max, the vertices of one mesh are identical to the ones of the other. Only difference is that the same vertex has a different  vertex index in each file, which probably explains why some edges are different to the original, since the whole mesh seems to be reconstructed. Another thing to point out, the file head_15_1.rx3 is not exactly like the other files. It doesn't have as many chunks as them, and some of the data chunks don't come with a 4-byte chunk size field.
## Post #11
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-03T07:33:20+00:00
- Post Title: Help with similiar 3d models

> Reply from Bigchillghost ↑Sun Nov 03, 2019 10:31 am at Sun Nov 03, 2019 10:31 am
>
> 
greenlemonade1 wrote: ↑Sat Nov 02, 2019 10:46 pmMy goal is just to fix these vertices, expecially on the back head, and mouth. While after the conversion with cm16,  a tool that  automatically convert fifa15 model, but some vertices are missplaced afterwards. I converted perfectly fifa14 head with blender, but on the other hand, the fifa15 converted model can't be open with blender, with fifa15 python scripts.

You seem to add more details, yet it still didn't answer my qusetions, but makes things more confusing.

In the first place you were trying to convert an FIFA Online 4 head to FIFA16, while now you intend to port an FIFA15 head to FIFA16, am I correct?
Now about this "cm16" tool, when said "automatically convert fifa15 model", you meant convert to FIFA16 rx3 file? That's how you got the file "head_246_0.rx3" in folder "fifa converted head", isn't it?

When you said "convert head using blender", given the fact that you just memtioned about these "fifa15 python scripts"(not one script?), I assume they're import scripts compatible at least for FIFA14, FIFA15 and FIFA16 rx3 files, right?

And when you tried to import this "fifa15 converted model", which is now in an FIFA16 "format", you said it "can't be open with blender", but I've checked that file, which has exactly the same structure and chunk order as "head_330_0.rx3", your previous "fifa 16 face" sample. And this, is against to the assumption that the "fifa15 python scripts" are compatible for FIFA16 rx3 files, hence against to your attempt to import the file back with those scripts, if you're aware of the fact. Then how did you get the "2 meshes" into blender and "noticed some edges are missplaced"?

So why don't you make things easier so people don't have to guess what's happening? And please stop quoting the entire post, it's really messy and confusing for what you're trying to comment on.

Anyway regard to your problem that "some edges are missplaced, or mouth vertices", I exported both head_15_1.rx3 and head_246_0.rx3 with AMR and imported them into 3Ds Max, the vertices of one mesh are identical to the ones of the other. Only difference is that the same vertex has a different  vertex index in each file, which probably explains why some edges are different to the original, since the whole mesh seems to be reconstructed. Another thing to point out, the file head_15_1.rx3 is not exactly like the other files. It doesn't have as many chunks as them, and some of the data chunks don't come with a 4-byte chunk size field.
I'm sorry for quoting so many posts. You are completely right, for all things that you said, I'm fascinated. Well, I saw 2 meshes, before I exported fifa15 converted head, after the export you can't see import this face into blender. So is there a way to fix these vertex index or is hard.
Yes fifa15 has less chunks, I think 14, fifa16 19 chunks (blocks).
Top
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-03T09:59:43+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Sun Nov 03, 2019 3:33 pm at Sun Nov 03, 2019 3:33 pm
>
> 
You are completely right, for all things that you said
At least now we got some direct answers to certain questions. So those blender python scripts support FIFA14, FIFA15 but FIFA16, yet you thought they do?

> Reply from greenlemonade1 ↑Sun Nov 03, 2019 3:33 pm at Sun Nov 03, 2019 3:33 pm
>
> 
Well, I saw 2 meshes, before I exported fifa15 converted head, after the export you can't see import this face into blender.
Then what's the other mesh other than fifa15 imported head?

> Reply from greenlemonade1 ↑Sun Nov 03, 2019 3:33 pm at Sun Nov 03, 2019 3:33 pm
>
> 
So is there a way to fix these vertex index or is hard.
Well, not that I totally understand the steps you took, but the main conclution: you're intending to convert a head mesh from FIFA Online 4, or from FIFA15, to FIFA16, and you can't use the rx3 file from either game directly. Normally I'd say it's impossible to map the vertex index to the target game version since you expect the vertex positions to be different. Luckily when I checked the UVs of head_41_0.rx3, head_15_1.rx3, head_330_0.rx3 and head_246_0.rx3, it turned out they all have the same UVs and of zero error compare with each other. So it's possible to map the source vertices with the target version by finding the vertex refering to the same UV.
## Post #13
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-03T10:24:22+00:00
- Post Title: Help with similiar 3d models

> Reply from Bigchillghost ↑Sun Nov 03, 2019 5:59 pm at Sun Nov 03, 2019 5:59 pm
>
> 
At least now we got some direct answers to certain questions. So those blender python scripts support FIFA14, FIFA15 but FIFA16, yet you thought they do?

Yes, they are supporting fifa14 and fifa15, but fifa16 can be seen in blender and also the models can be modify. http://3dgamedevblog.com/?sdm_downloads ... -ie-v0-66b


Then what's the other mesh other than fifa15 imported head?
the other mesh is fifa20 nintendo version, compatible with fifa14 but not completely for fifa15 or fifa16.
Well, not that I totally understand the steps you took, but the main conclution: you're intending to convert a head mesh from FIFA Online 4, or from FIFA15, to FIFA16, and you can't use the rx3 file from either game directly. Normally I'd say it's impossible to map the vertex index to the target game version since you expect the vertex positions to be different. Luckily when I checked the UVs of head_41_0.rx3, head_15_1.rx3, head_330_0.rx3 and head_246_0.rx3, it turned out they all have the same UVs and of zero error compare with each other. So it's possible to map the source vertices with the target version by finding the vertex refering to the same UV.
[/quote]
Yes I realized that from fifa online 4 is hard to convert, while blocks are mashed up, head and eyes, as you said. So I continued trying to convert perfect model from fifa15 to fifa16.
I don't know how to do last step, that you said, mate 
I realized that mouth offset starts in fifa16 at: 0xff50 and finishes at 0x369b0
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-03T11:24:02+00:00
- Post Title: Help with similiar 3d models

> Reply from greenlemonade1 ↑Sun Nov 03, 2019 6:24 pm at Sun Nov 03, 2019 6:24 pm
>
> 
Yes I realized that from fifa online 4 is hard to convert, while blocks are mashed up, head and eyes, as you said.
I don't know how to do last step, that you said
Replacing both vertex and face index chunks directly is not practically since it might influence other data chunks and causing fatal issues. But if you simply change the position coordinates of the vertices without modifying their indices in the array, it'd be very likely to work. To do so you'll need a head mesh from the target game, and the head mesh you want to replace it with. Then extract the vertices arrays for each submeshes(eyelashes, head) from both files, create new arrays that record both the original vertex indices and the vertex data, and sort these arrays by the UV values, in which way you'll get the mapping info from the source vertices to those of the target version. The rest thing is to resort the source array by their new vertex indices and replace the corresponding chunk of the target file with the resulted data.
## Post #15
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-05T16:01:51+00:00
- Post Title: Help with similiar 3d models

> Reply from Bigchillghost ↑Sun Nov 03, 2019 7:24 pm at Sun Nov 03, 2019 7:24 pm
>
> 
Replacing both vertex and face index chunks directly is not practically since it might influence other data chunks and causing fatal issues. But if you simply change the position coordinates of the vertices without modifying their indices in the array, it'd be very likely to work. To do so you'll need a head mesh from the target game, and the head mesh you want to replace it with. Then extract the vertices arrays for each submeshes(eyelashes, head) from both files, create new arrays that record both the original vertex indices and the vertex data, and sort these arrays by the UV values, in which way you'll get the mapping info from the source vertices to those of the target version. The rest thing is to resort the source array by their new vertex indices and replace the corresponding chunk of the target file with the resulted data.
[/quote]
i've tried for days and days and no success, i tried morhping, but also no success. Maybe if you want to make script, which allow us to open fifa15 converted head, or something similiar, it will be awesome. I can provide fifa15 scripts for blender, that can be helpful. What do you think, master?
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-06T00:48:42+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from greenlemonade1 ↑Wed Nov 06, 2019 12:01 am at Wed Nov 06, 2019 12:01 am
>
> 
i tried morhping, but also no success.
If you did it correctly but it didn't work, then the method explained above won't work either.
BTW I suggest you to make a better quote next time instead of mixing other's post with yours. Probably you'd better preview your post before submission.
## Post #17
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-10T08:47:21+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Wed Nov 06, 2019 8:48 am at Wed Nov 06, 2019 8:48 am
>
> 
greenlemonade1 wrote: ↑Wed Nov 06, 2019 12:01 am
i tried morhping, but also no success. 

If you did it correctly but it didn't work, then the method explained above won't work either.
BTW I suggest you to make a better quote next time instead of mixing other's post with yours. Probably you'd better preview your post before submission.
Actully I'm stucked, but I tried to figure it out, but no results. I belive in your knowledge, that this will work, but it's hard to understand. Maybe if you made a script/ modify the made one. Or to fix just cm16 script, I don't know where is that script in cm16. exe maybe?
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-11T05:29:28+00:00
- Post Title: Re: Help with similiar 3d models

Here's the modified head_330_0.rx3 file using the positions, normals and tangents of head_41_0.rx3. Since the mismatches of bone indices and weights in the vertex structure between the two files just raise uncertainties of the effect caused by the modification, I didn't replace the whole data chunk. The same reason it might look weird in game.
[head_330_0(MorphedFromHead41).7z](https://xentaxbackup.github.io/file/17044_head_330_0(MorphedFromHead41).7z)
## Post #19
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-12T19:20:17+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Mon Nov 11, 2019 1:29 pm at Mon Nov 11, 2019 1:29 pm
>
> 
Here's the modified head_330_0.rx3 file using the positions, normals and tangents of head_41_0.rx3. Since the mismatches of bone indices and weights in the vertex structure between the two files just raise uncertainties of the effect caused by the modification, I didn't replace the whole data chunk. The same reason it might look weird in game.

No, master, It's perfect, in game also. Can you tell me how you did it, or make a tutorial. Incredible!!
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-15T09:46:22+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from greenlemonade1 ↑Wed Nov 13, 2019 3:20 am at Wed Nov 13, 2019 3:20 am
>
> Can you tell me how you did it
Similar procedure as explained previously, except that you just replace part of the vertex data in the target file instead of the whole rearranged source chunk.

Here's a command line tool to map the vertex in the source chunk to the target chunk.
See below for a detailed how-to.
[vertexMap.zip](https://xentaxbackup.github.io/file/17061_vertexMap.zip)
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-15T09:47:25+00:00
- Post Title: Re: Help with similiar 3d models

Dump the vertex data chunk for the face mesh in the file you want to replace with, as  shown below. Say the filename to be face41.dat.




step123.png (121.52 KiB) Viewed 109 times



step 4: repeat step 1 to 3 on the file you want to replace for the corresponding mesh chunk, say the filename of it to be face330.dat;
step 5: open cmd under current path, assuming that you've also got vertexMap.exe in it, input the following commands: 
vertexMap.exe face41.dat face330.dat

step 6: copy everything in face330.dat, and replace the original data in head_330_0.rx3.
step 7: repeat step 1 to 6 for the eyelashes mesh.
## Post #22
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-16T23:15:26+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Fri Nov 15, 2019 5:47 pm at Fri Nov 15, 2019 5:47 pm
>
> 
Dump the vertex data chunk for the face mesh in the file you want to replace with, as  shown below. Say the filename to be face41.dat.


step123.png


step 4: repeat step 1 to 3 on the file you want to replace for the corresponding mesh chunk, say the filename of it to be face330.dat;
step 5: open cmd under current path, assuming that you've also got vertexMap.exe in it, input the following commands: 
vertexMap.exe face41.dat face330.dat

step 6: copy everything in face330.dat, and replace the original data in head_330_0.rx3.
step 7: repeat step 1 to 6 for the eyelashes mesh.

Thank you so much for this explanation in detalis, I'm so thankful, you are so kind! Just one tiny thing, I tried to swape parts of the hair, because hair file has 2 parts, and in fifa16 is is different, like the head and eyes mashes are swapped, altough fifa online 4 hair work in fifa16, but doesn't move, so I realized that the parts are set in different. So i swapped data blocks, and had render problems, can you take a look, it's last thing that I need to know for the fifa conversion, because I realized head conversion, beacuse of you 
[https://www.mediafire.com/file/dmiltkdc ... e.rar/file](https://www.mediafire.com/file/dmiltkdch9qzahd/hair_example.rar/file)
## Post #23
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-17T05:31:09+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from greenlemonade1 ↑Sun Nov 17, 2019 7:15 am at Sun Nov 17, 2019 7:15 am
>
> I tried to swape parts of the hair, ..., altough fifa online 4 hair work in fifa16, but doesn't move, so I realized that the parts are set in different. 
So i swapped data blocks, and had render problems
Are "fifa online 4 hair work in fifa16, but doesn't move" and "had render problems" the same thing? 

This file uses half-float for position coordinates which resulted in the change of the UV offset.



hfPos.png (100.53 KiB) Viewed 79 times



While vertexMap.exe just assume that the UV is at offset 0x14 in the vertex array, the updated chunk file should be much larger than the original, and might has already been messed up. So I have no idea how you got it work in game. Unless you replaced the data with the whole chunk from another file.
## Post #24
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-17T09:12:24+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Sun Nov 17, 2019 1:31 pm at Sun Nov 17, 2019 1:31 pm
>
> 
greenlemonade1 wrote: ↑Sun Nov 17, 2019 7:15 amI tried to swape parts of the hair, ..., altough fifa online 4 hair work in fifa16, but doesn't move, so I realized that the parts are set in different. 
So i swapped data blocks, and had render problems

Are "fifa online 4 hair work in fifa16, but doesn't move" and "had render problems" the same thing? 

This file uses half-float for position coordinates which resulted in the change of the UV offset.
hfPos.png

While vertexMap.exe just assume that the UV is at offset 0x14 in the vertex array, the updated chunk file should be much larger than the original, and might has already been messed up. So I have no idea how you got it work in game. Unless you replaced the data with the whole chunk from another file.
Yes they are working, actually hair_0_0 is moving, and it should hair_0_1. Render problems were when I swappedn blocks, I used fifa file explorer by jenkey, it can be open any rx3 file, and divide chunks, so you got all 14 blocks that are in the file. I think the hair is not messed up, it's like that 2 parts, one part like layer and eyebrows, the other is hair.
p.s. I swappedn blocks: 5,6, 9 and 10. Here is my try: [https://www.mediafire.com/file/1v8odeg7 ... n.rx3/file](https://www.mediafire.com/file/1v8odeg7go1bl54/hair_block_conversion.rx3/file)
[Capture.PNG](https://xentaxbackup.github.io/file/17070_Capture.PNG)
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-17T10:07:28+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from greenlemonade1 ↑Sun Nov 17, 2019 5:12 pm at Sun Nov 17, 2019 5:12 pm
>
> 
p.s. I swappedn blocks: 5,6, 9 and 10.
That makes sense. You replaced both the vertex and the index blocks.

> Reply from greenlemonade1 ↑Sun Nov 17, 2019 5:12 pm at Sun Nov 17, 2019 5:12 pm
>
> 
actually hair_0_0 is moving, and it should hair_0_1.
That's because of the reason I wrote here:

> Reply from Bigchillghost ↑Mon Nov 11, 2019 1:29 pm at Mon Nov 11, 2019 1:29 pm
>
> 
...the mismatches of bone indices and weights in the vertex structure between the two files...
And that's why you can only replace the positions, normals and tangents of each vertex.
## Post #26
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-17T10:37:04+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Sun Nov 17, 2019 6:07 pm at Sun Nov 17, 2019 6:07 pm
>
> 
greenlemonade1 wrote: ↑Sun Nov 17, 2019 5:12 pm
p.s. I swappedn blocks: 5,6, 9 and 10. 

That makes sense. You replaced both the vertex and the index blocks.
greenlemonade1 wrote: ↑Sun Nov 17, 2019 5:12 pm
actually hair_0_0 is moving, and it should hair_0_1. 

That's because of the reason I wrote here:
Bigchillghost wrote: ↑Mon Nov 11, 2019 1:29 pm
...the mismatches of bone indices and weights in the vertex structure between the two files...

And that's why you can only replace the positions, normals and tangents of each vertex.
That I can do with the last tutorial you gave or? I thought it will be easier, because of just one file
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-17T11:32:46+00:00
- Post Title: Re: Help with similiar 3d models

Same procedure, but use this one for half-float positions.
[vertexMapHalfp.zip](https://xentaxbackup.github.io/file/17076_vertexMapHalfp.zip)
## Post #28
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-17T19:46:08+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Sun Nov 17, 2019 7:32 pm at Sun Nov 17, 2019 7:32 pm
>
> 
Same procedure, but use this one for half-float positions.

HAIR: It said that amont of vertices is not the same, when I tried to convert hair, I done exactly as you said, I found the correct offset etc. What shouldI do now? 
HEADS: As I tried to convert new models, strange thing happened, although the lenght is the same  as in older models 25000h, but I got bugs in blender, old models are working like a charm 
[https://www.mediafire.com/file/smiobwmr ... 9.rx3/file](https://www.mediafire.com/file/smiobwmrr3dkdb0/head_0_%281341%29.rx3/file)
## Post #29
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-18T01:47:56+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from greenlemonade1 ↑Mon Nov 18, 2019 3:46 am at Mon Nov 18, 2019 3:46 am
>
> 
HAIR: It said that amont of vertices is not the same, when I tried to convert hair, I done exactly as you said, I found the correct offset etc. What shouldI do now?
You can map the vertices from one file to another only when they have equal amount of vertices. I don't have the other file so can't tell if you did it right.

> Reply from greenlemonade1 ↑Mon Nov 18, 2019 3:46 am at Mon Nov 18, 2019 3:46 am
>
> 
HEADS: As I tried to convert new models, strange thing happened, although the lenght is the same  as in older models 25000h, but I got bugs in blender
Coz this model has UV errors compared to the other (head_330_0.rx3), which causes the mismatches of vertices after sorting.



errors.png (16.71 KiB) Viewed 38 times


In this case it'll require fuzzy matching, and that could be complicated.
## Post #30
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-18T04:06:34+00:00
- Post Title: Re: Help with similiar 3d models

Some vertices of the head in head_330_0.rx3 even have overlapped UVs though they're two different vertices in 3D space.



diffPosSameUV.png (87.46 KiB) Viewed 37 times


It's possible that this could result in mismatching issue. Another factor that makes this method unreliable.
## Post #31
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-11-18T16:21:06+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Mon Nov 18, 2019 12:06 pm at Mon Nov 18, 2019 12:06 pm
>
> 
Some vertices of the head in head_330_0.rx3 even have overlapped UVs though they're two different vertices in 3D space.
diffPosSameUV.png
It's possible that this could result in mismatching issue. Another factor that makes this method unreliable.

Master, nevermind about hair, I realized that I can shrink vertices, and used you too much time for this,  but I ran into one strange model today, while I was exporting all the models from fo4, there is one new model, in which are head and eye position correct ordered, not need to sweep, and I converted other models, in which as you know, first go eye and then head, with blender, and also strange thing I got no buggs, after importing in blender. Maybe can help about mapping the new models, can you take a look?
[https://www.mediafire.com/file/sbj7r3ty ... l.rar/file](https://www.mediafire.com/file/sbj7r3typc8hbda/not_swapped_model.rar/file)
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-19T03:51:18+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from greenlemonade1 ↑Tue Nov 19, 2019 12:21 am at Tue Nov 19, 2019 12:21 am
>
> while I was exporting all the models from fo4, there is one new model, in which are head and eye position correct ordered, not need to sweep, and I converted other models, in which as you know, first go eye and then head, with blender, and also strange thing I got no buggs, after importing in blender. Maybe can help about mapping the new models, can you take a look?
I have no idea what you're talking about. If you were using vertexMap to update the positions and replacing data, then of course you'll need to look for the corresponding data block in the other file yourself, no matter how they're ordered, in which point it's order independent. But if you simply copied the block in the source file and replaced the corresponding block in the target file, then it has nothing to do with vertex mapping. So are you suggesting that you were using the latter method the whole time and it's usually buggy except for this particular model?
## Post #33
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-11-20T10:46:45+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Mon Nov 11, 2019 1:29 pm at Mon Nov 11, 2019 1:29 pm
>
> 
Here's the modified head_330_0.rx3 file using the positions, normals and tangents of head_41_0.rx3. Since the mismatches of bone indices and weights in the vertex structure between the two files just raise uncertainties of the effect caused by the modification, I didn't replace the whole data chunk. The same reason it might look weird in game.

Bigchillghost, you did a quite a work here, I'm looking for this long time ago. Can you maybe made a script for opening 3d models in python, because I extracted now fo4, and models can't be identified because there is no decryptor for fo4 big files. This can maybe help, scripts for opening in blender:
[https://www.mediafire.com/file/olo4s6o0 ... s.rar/file](https://www.mediafire.com/file/olo4s6o0ae4cpbm/fifa_tools.rar/file)
## Post #34
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-11-24T09:24:29+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Fri Nov 15, 2019 5:46 pm at Fri Nov 15, 2019 5:46 pm
>
> 
greenlemonade1 wrote: ↑Wed Nov 13, 2019 3:20 amCan you tell me how you did it

Similar procedure as explained previously, except that you just replace part of the vertex data in the target file instead of the whole rearranged source chunk.

Here's a command line tool to map the vertex in the source chunk to the target chunk.
See below for a detailed how-to.
Master, please can you make a python script, it will be helpful, players can be recognized, just manualy in blender
## Post #35
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-25T14:13:30+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from mita996 ↑Wed Nov 20, 2019 6:46 pm at Wed Nov 20, 2019 6:46 pm
>
> I'm looking for this long time ago.
What's "this"?

> Reply from mita996 ↑Wed Nov 20, 2019 6:46 pm at Wed Nov 20, 2019 6:46 pm
>
> 
Can you maybe made a script for opening 3d models in python
A script for extracting models? Have you tried existing tools for other FIFA games? After all they use the same format.

> Reply from mita996 ↑Wed Nov 20, 2019 6:46 pm at Wed Nov 20, 2019 6:46 pm
>
> 
because I extracted now fo4, and models can't be identified because there is no decryptor for fo4 big files.
Meaning?
## Post #36
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-11-25T23:19:24+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Mon Nov 25, 2019 10:13 pm at Mon Nov 25, 2019 10:13 pm
>
> 
mita996 wrote: ↑Wed Nov 20, 2019 6:46 pmI'm looking for this long time ago. 
What's "this"?
mita996 wrote: ↑Wed Nov 20, 2019 6:46 pm
Can you maybe made a script for opening 3d models in python

A script for extracting models? Have you tried existing tools for other FIFA games? After all they use the same format.
mita996 wrote: ↑Wed Nov 20, 2019 6:46 pm
because I extracted now fo4, and models can't be identified because there is no decryptor for fo4 big files. 

Meaning?
well, fifa online 4 used another format, for other fifa games,like fifa16,15,14 etc, we can identify player by their id's. When we export big files from fifa online 4, we got just bump files, because the decryptor is not provided, and we can just manually import in blender player to identify. That's why is the script so important, so we can faster see model in noesis and identify it.
## Post #37
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-26T01:46:13+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from mita996 ↑Tue Nov 26, 2019 7:19 am at Tue Nov 26, 2019 7:19 am
>
> and we can just manually import in blender player to identify. That's why is the script so important, so we can faster see model in noesis and identify it.
You know you're being nitpicking, right?
Anyway I refuse such wasteful duplication of work so you're on your own.
## Post #38
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-11-26T08:37:16+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Tue Nov 26, 2019 9:46 am at Tue Nov 26, 2019 9:46 am
>
> 
mita996 wrote: ↑Tue Nov 26, 2019 7:19 amand we can just manually import in blender player to identify. That's why is the script so important, so we can faster see model in noesis and identify it. 

You know you're being nitpicking, right?
Anyway I refuse such wasteful duplication of work so you're on your own.

I don't know why am I nitpicking, there are more than 3000 models, that needs to be identified, and it's not wasteful, but nevermind, thanks.
## Post #39
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2019-12-08T10:12:22+00:00
- Post Title: Re: Help with similiar 3d models

> Reply from Bigchillghost ↑Mon Nov 11, 2019 1:29 pm at Mon Nov 11, 2019 1:29 pm
>
> 
Here's the modified head_330_0.rx3 file using the positions, normals and tangents of head_41_0.rx3. Since the mismatches of bone indices and weights in the vertex structure between the two files just raise uncertainties of the effect caused by the modification, I didn't replace the whole data chunk. The same reason it might look weird in game.

Bigchillghost, I've noticed after the conversion, the mouth looks weird in game, like some teeth are black, the other parts are excellent. Also, on thing about newer models, is it too complicated to do fuzzy matching?
