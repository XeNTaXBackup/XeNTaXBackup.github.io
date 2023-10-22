## Post #1
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2021-12-06T19:20:43+00:00
- Post Title: Unknown Model File Type (Evil Genius 2, Asura Engine)

Got some files here that were extracted from Evil Genius 2 using QuickBMS.
Everything comes out extensionless. Header doesn't tell me anything, maybe someone here knows whats up with these?
I appended a sample file and header screenshot.  




EG2_model_file.png (32.56 KiB) Viewed 136 times



edit: attaching sample file apparently didn't work, so here's a mega link instead
[https://mega.nz/file/Z6RRhCyR#hcD2ivBx6 ... b3oqgIeWFU](https://mega.nz/file/Z6RRhCyR#hcD2ivBx6ABc_BJRG51sRo2F6E1w902WJb3oqgIeWFU)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-06T21:50:54+00:00
- Post Title: Unknown Model File Type (Evil Genius 2, Asura Engine)

Strange, I tried x,y,z and ended up with an uv map!?
Ah, see, mix of shorts (x,y,z) and half floats (uvs), a feature, hex2obj doesn't have (and never will):
.



philanthropist_head.png (136.99 KiB) Viewed 128 times
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-12-06T22:11:44+00:00
- Post Title: Unknown Model File Type (Evil Genius 2, Asura Engine)

Also, some UInt10s apparently for normals and other stuff.

There must also be some companion files because the file doesn't reference any textures/materials.  The vertex data has bone information, but no skeleton data is present.

First Int value in the file is the number of submeshes.  Submesh info starts at 0x10, with 0x14 bytes per entry.  The only useful thing I can see in that info is the number of faces used for each submesh at offset 8 in each entry.
## Post #4
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2021-12-07T12:44:00+00:00
- Post Title: Unknown Model File Type (Evil Genius 2, Asura Engine)

> Reply from shakotay2 ↑Tue Dec 07, 2021 5:50 am at Tue Dec 07, 2021 5:50 am
>
> 
Strange, I tried x,y,z and ended up with an uv map!?
Ah, see, mix of shorts (x,y,z) and half floats (uvs), a feature, hex2obj doesn't have (and never will):
.
philanthropist_head.png

Interesting, could you post the h2obj settings you used for this one?

> Reply from DKDave ↑Tue Dec 07, 2021 6:11 am at Tue Dec 07, 2021 6:11 am
>
> 
Also, some UInt10s apparently for normals and other stuff.

There must also be some companion files because the file doesn't reference any textures/materials.  The vertex data has bone information, but no skeleton data is present.

First Int value in the file is the number of submeshes.  Submesh info starts at 0x10, with 0x14 bytes per entry.  The only useful thing I can see in that info is the number of faces used for each submesh at offset 8 in each entry.

Thanks for the overview! It looks like there aren't even any LODs contained in these.
I am currently working on extracting the texture files and misc stuff. Looks like every part only uses one material.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-07T16:07:44+00:00
- Post Title: Unknown Model File Type (Evil Genius 2, Asura Engine)

p-head.png (9.13 KiB) Viewed 109 times
## Post #6
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2022-01-01T14:18:42+00:00
- Post Title: Unknown Model File Type (Evil Genius 2, Asura Engine)

Happy new year!
First of all, big thank you to both of you again! Both the tip with the face count and type switching were absolutely golden. Making separate objs for mesh and UVs and recombining later is working really well so far. All the heads I needed are successfully done now.

There is just one weirdness with the larger body meshes. See screenshot: the body is off-center and certain parts offset a few units to the side. Still connected though, creating serious stretching. I can theoretically correct this in blender later, but I wonder if there's a way to compensate for this during the hex2obj step already? 

Sample files attached via mega
raw
[https://mega.nz/file/02RVFK4a#sreUseSgQ ... OCj2M5opIU](https://mega.nz/file/02RVFK4a#sreUseSgQtlxKd5zMYwqebbS2YSesf_zFOCj2M5opIU)
result obj
[https://mega.nz/file/tyIVWQDZ#qw-ZFwFaV ... YHfN1dgdZI](https://mega.nz/file/tyIVWQDZ#qw-ZFwFaVbDo6URc54cYwsxFfjc8sYHDRYHfN1dgdZI)

edit: offset, it turns out, is exactly 256, making it an easy fix
[EG2_SampleBody_Shifted.png](https://xentaxbackup.github.io/file/21491_EG2_SampleBody_Shifted.png)
