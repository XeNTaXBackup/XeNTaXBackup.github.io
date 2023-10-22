## Post #1
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2019-04-23T22:32:45+00:00
- Post Title: Help needed figuring out the X3D Files from the Precure 3DS games.

Hi Guys,

I've spent roughly the last two weeks, to figure out, how this Format works. During this time, I managed to find the Vertex, Face and UVs in a reproduceable manner -> Vertices start in the SMDL block as a block of 64 Bytes per Vertex. The first 12 Bytes are the X Y and Z coordinates as Floats. The next 4 Bytes are usually 00 00 80 FF. The Following 12 Bytes are the normals as Float, followed by 4 bytes as usually 0 and 4 bytes as FF. The next 8 Bytes are the UVs as Float again. Followed by 4 bytes as 0 yet again. I don't know what the last 16 Bytes do though, but 00 00 80 FF appear frequently as the first 4 bytes. The Faces start imediately after the last vertex. They are laid out as Short Tri-Strips.



M_TopDreNon_0001.x3d_Fri_Apr_19_23-35-28_2019.png (103.49 KiB) Viewed 86 times


This in itself works fine with Models, where the is only one mesh, like Tops, or Accessories. However it doesn't work as intuitively with models with multiple meshes, like the heads, where I have to piece together the amount of faces and vertices per mesh.

Can you help me figure out, where the Mesh Table is?

[Sample Files](https://mega.nz/#F!RmhEgIyS!PhIJ5661szUb0eLvTT8Y8A)
## Post #2
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2019-05-06T23:26:23+00:00
- Post Title: Help needed figuring out the X3D Files from the Precure 3DS games.

Since asking the Question, I've managed to find out where the Mesh Table is.

I've attempted to write a small noesis script, that can open this format, however I'm struggling with the Faces, since noesis requires me to use regular triangles, but the game uses Tri-Strips.



HaCha_PC_script_progress_02.png (166.81 KiB) Viewed 58 times

How can I convert Tri-Strips into the Triangle representation, that noesis is expecting?( Note: I've appended the face array with 0s, to make the array divisible by 3)

the script is available [here](https://mega.nz/#!Bu4g1IaQ!OZVyknvKL5dmSjc78tgoDClXuZVggNy2LZlpMRlkt6Y)
## Post #3
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-07T02:15:21+00:00
- Post Title: Help needed figuring out the X3D Files from the Precure 3DS games.

you basicly reassemble the index list to index the per triangle vertices. this is clockwise order.
## Post #4
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2019-05-07T06:23:01+00:00
- Post Title: Help needed figuring out the X3D Files from the Precure 3DS games.

Thank you that works like a charm  

For anyone interested, here is the fixed script

 fmt_precure_x3d_fixed.zip
(1.42 KiB) Downloaded 18 times
