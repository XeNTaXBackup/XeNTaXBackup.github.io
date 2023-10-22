## Post #1
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2019-12-05T07:14:28+00:00
- Post Title: webgl model

Can anyone get verts as a point cloud, or face indicies for any of these two files? I was sent them from my chinese friend to look at and I believe they are from webgl, but no extension. I have tried to create a point cloud with hex2obj but I can't find where the verts start exactly. Any help would be appreciated

[https://www.mediafire.com/file/xyljf520 ... s.zip/file](https://www.mediafire.com/file/xyljf520s17q5hh/parts.zip/file)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-12-05T11:36:21+00:00
- Post Title: webgl model

that looks like complications. that's definetely not float data. tried half float or variable integer encodings. the face index (that's kinda easy to spot in hex) is definetely some kind of codificated.

may ask your friend if he got the data in another format. or any url to ninja rip it might be easier then this coded file (for the trashcan).
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-06T03:04:40+00:00
- Post Title: webgl model

On part decompressed data:



part_dec.png (130.51 KiB) Viewed 162 times
## Post #4
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2019-12-06T04:01:44+00:00
- Post Title: webgl model

> Reply from Bigchillghost ↑Fri Dec 06, 2019 11:04 am at Fri Dec 06, 2019 11:04 am
>
> 
On part decompressed data:
part_dec.png

Wow that is incredible you found that, may I ask how you decompressed it? To me not all of it looks compressed.   I kept it shortened otherwise they could patch it much like sketchfab did, and my friend gets sent preview meshes on this site so patching or changing the code would be a hassle. I have never seen advanced mesh reaper before but I must give it a try since it seems to have more options. The other thing I noticed is that part you ripped seems to be facing upwards rather than facing right, does this mean the vertex aren't in the right position right away? And the object is just transformed/rotated into place after the fact? And finally, did you try more than one part? If so, were the counts, start addresses stored in a similar place? Thanks again for your help, you figured it out so quickly
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-06T06:40:44+00:00
- Post Title: webgl model

> Reply from modelsarequitenice ↑Fri Dec 06, 2019 12:01 pm at Fri Dec 06, 2019 12:01 pm
>
> 
may I ask how you decompressed it? To me not all of it looks compressed.
The data in the file named "part" is zstd compressed. You'll see the compression & decompression sizes in the header. Didn't bother to check the other file since it's too small for interest.

> Reply from modelsarequitenice ↑Fri Dec 06, 2019 12:01 pm at Fri Dec 06, 2019 12:01 pm
>
> The other thing I noticed is that part you ripped seems to be facing upwards rather than facing right, does this mean the vertex aren't in the right position right away? And the object is just transformed/rotated into place after the fact?
It was towards the right. I just rotated it for better observation.

> Reply from modelsarequitenice ↑Fri Dec 06, 2019 12:01 pm at Fri Dec 06, 2019 12:01 pm
>
> 
And finally, did you try more than one part? If so, were the counts, start addresses stored in a similar place?
There's only one object in the decompressed data of "part". And as said I didn't check the other file, though which doesn't seem to contain compressed data. You'll find the counts in the header of the decompressed stream, that's all I can say.
## Post #6
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2019-12-06T08:19:06+00:00
- Post Title: webgl model

Perfect thank you for the explaining, I did notice the zstd earlier when looking at the zenhax tutorial section, it is the latest version. I guess I will have to make some kind of bms script for it
## Post #7
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2019-12-07T06:31:38+00:00
- Post Title: webgl model

> Reply from Bigchillghost ↑Fri Dec 06, 2019 2:40 pm at Fri Dec 06, 2019 2:40 pm
>
> 
There's only one object in the decompressed data of "part". And as said I didn't check the other file, though which doesn't seem to contain compressed data. You'll find the counts in the header of the decompressed stream, that's all I can say.
One more thing in regards to what you said here. I managed to decompress, however you say the header contains the counts, I found one of the counts (the indices one) And right next to that there is a value similar to the one you put for vertex count but not the same. Maybe it decompressed wrong, or did you only see the indices one? Sorry to bother you
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-07T06:53:52+00:00
- Post Title: webgl model

> Reply from modelsarequitenice ↑Sat Dec 07, 2019 2:31 pm at Sat Dec 07, 2019 2:31 pm
>
> And right next to that there is a value similar to the one you put for vertex count but not the same. Maybe it decompressed wrong, or did you only see the indices one?
There's no exact vertex count for the mesh, but a sum of the amount of the mesh vertices and the wireframe vertices. So either you calculate the max value of the face indices, or you take the value of the first wire index.
