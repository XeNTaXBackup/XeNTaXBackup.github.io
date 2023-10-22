## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2014-02-20T11:36:05+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

Hi guys. I've just coded my first 3d model application called x-rey. 

Firstly I would like to thank Chorrox for writing the first wwe model import script. I was able to decipher the format by reading through his script. 

Secondly I would like to thank brienj for writing the model import script for 3dsm. 

Ok down to business, my program reads from the yobj model files and enumerates the sub objects in this file. The user can then export and import these objects allowing for the models to be edited. 

I have also coded a viewport which allows the user to preview the sub objects in the file. The viewport code reads the vertice, face and uv data in the file. It then exports this data to wavefront object format. Then it loads the wavefront object in the viewport. 

I need help with the following two things:

a) The older wwe games (2011 and below) use  a slightly different format then the newer games. The difference is that the headers in the new format contain an additional reference to some new data in the new format. The result is that the headers are bigger by 4 bytes and that the file is also bigger due to the additional data. 

At present I have not figured what this additional data is for so I am adding zero byte data for the length specified. The data seems to contain 3 four byte float values for each of the vertices, which I am assuming is coordinate data. The normal, uv, weights, bone and vertice data has already been identified in the file so I don't know what this new data is for. 

I have also added a reference to zero byte data I am adding to the file in the header, increased the header size and also fixed the offsets in the header and face data. 

I am using brienj's import script to test the models in the 3dsm but when I try to open one of the converted models, nothing is displayed. 

To summarize what I am currently doing:

1. Header size - old b4, new b8. Need to add four bytes extra
2. Offsets need to change for each header info.
3. Vertex data in new ends with 20 32 32 32 . Old ends with FF FF FF FF
4. New format has 4 bytes extra added at byte 120 of the headers for each object. This is referencing a new byte array contain data after the uv data.
5. Extra 12 bytes of data per vertice after uv data and before face data. This 12 byte data seems to contain 3 float values of four bytes each (coordinates???) .These float values are in the same format as the UV data except that the UV data only contains 2 coordinates.
6. Face offset needs to be changed for each array.

This is a diagram of the headers for the old and new formats:

OLD FORMAT:



NEW FORMAT:



Here are some sample files. I have included the new format, the old format and the file I have converted:

[http://www28.zippyshare.com/v/1399166/file.html](http://www28.zippyshare.com/v/1399166/file.html)

Any help as to where I am going wrong would be appreciated.
## Post #2
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2014-02-20T11:41:07+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

Edit: Second problem solved thanks to howfie
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-20T13:35:42+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

looks like bad indexing of the second mesh. make sure for OBJs, consecutive meshes don't start indexing at 1, but at 1 + number of total vertices in previous vertex buffers. an OBJ file only has 1 position buffer, 1 normal buffer, and 1 texcoord buffer no matter how many separate buffers the original model has.
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2014-02-21T12:42:52+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

@howfie, thank you very much. Adding the vertices to the face values solved my problem   

Now onto problem number one. Can anyone please assist.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-21T23:18:12+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

what's wrong with the pics? they look fine to me. your question a) seems to be about unknown vertex data... did you try printing it out? is the vector normalized? are the values all less than one?

those samples you uploaded, are they from WWE2k14? you could probably just ignore the new data if you have already got the things that you want (position, normal, uv, blendweights, blendindices, etc.).
## Post #6
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2014-02-22T21:13:32+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

The problem is not loading the models in my program but the issue is loading the converted models in the game. 

After doing the conversion and trying to load the old models in the game, the game freezes. I'm assuming that this means that I missed something in the conversion. For the new dats which is not in the old format, I am just adding zeros in the space that the data would take.

I have uploaded models for 2k14, the old model format from wwe 2011 and also the same 2011 model I've converted.

I can print out the values of the unknown data if it will help.
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2014-02-25T08:05:01+00:00
- Post Title: X-rey, need help converting WWE models & combining obj's

Ok here's a sample file I've created from new model format. The object has 22 vertices. The unknown data has  3 float values for each vertex. I've labeled this "vn" but I'm not sure what these values are for or how it is computed:

```

mtllib previewFull.mtl
v 46.26008 2.821342 143.5536
v 48.11643 3.249135 142.9321
v 48.60737 0.737179 141.4822
v 48.012 5.078175 144.6366
v 50.21607 5.281067 152.9182
v 49.18431 5.808453 151.1292
v 47.4618 4.422986 152.404
v 48.52058 3.51292 153.8498
v 46.87161 4.979527 151.0803
v 48.65148 5.29626 149.0311
v 46.69707 0.378211 142.4466
v 51.40104 3.373698 154.6571
v 49.6362 1.521771 154.8595
v 45.13809 -0.119591 143.0291
v 25.90535 -0.474973 146.5567
v 24.33466 0.30891 146.2817
v 26.94006 0.633142 147.1905
v 44.47673 2.114347 143.7725
v 43.19754 -0.064112 143.578
v 41.77804 1.515825 144.1075
v 41.04669 -0.675029 143.9784
v 38.39975 0.01235 144.4747


vt 0.5155 -0.2741 0
vt 0.517 -0.2899 0
vt 0.506 -0.2932 0
vt 0.5299 -0.288 0
vt 0.5705 -0.2965 0
vt 0.5609 -0.2931 0
vt 0.5665 -0.2718 0
vt 0.575 -0.2772 0
vt 0.5599 -0.2664 0
vt 0.5477 -0.288 0
vt 0.5059 -0.277 0
vt 0.5807 -0.3 0
vt 0.5845 -0.2821 0
vt 0.5059 -0.2575 0
vt 0.5082 -0.1179 0
vt 0.5129 -0.1128 0
vt 0.5112 -0.1367 0
vt 0.5129 -0.2553 0
vt 0.5059 -0.242 0
vt 0.5111 -0.235 0
vt 0.5059 -0.2261 0
vt 0.508 -0.2071 0


vn -0.028826 0.891225 0.452645
vn -0.036655 0.845211 0.533174
vn -0.049004 0.988544 0.142758
vn 0.148994 0.486343 0.860971
vn 0.296188 -0.614518 0.731191
vn 0.175857 -0.159086 0.971476
vn 0.206809 -0.50366 0.838783
vn 0.258235 -0.796157 0.547219
vn 0.170851 -0.435127 0.884011
vn 0.101208 -0.144871 0.984261
vn -0.092125 0.993993 -0.059081
vn 0.250213 -0.931393 0.264387
vn 0.195109 -0.977802 -0.076393
vn -0.174741 0.984064 0.032913
vn 0.063971 -0.940219 -0.33451
vn 0.414182 -0.898512 -0.145355
vn -0.220978 0.955621 0.194828
vn -0.116653 0.93554 0.333402
vn -0.213642 0.969695 0.118526
vn -0.107035 0.986221 0.126142
vn -0.151662 0.979085 0.135615
vn -0.063778 0.990347 0.123068


g Object7
s 1
usemtl Material 01
f 15/15 17/17 16/16
f 14/14 18/18 19/19
f 18/18 20/20 19/19
f 19/19 20/20 21/21
f 20/20 22/22 21/21
f 4/4 1/1 2/2
f 2/2 1/1 3/3
f 3/3 1/1 11/11
f 1/1 14/14 11/11
f 10/10 6/6 9/9
f 9/9 6/6 7/7
f 6/6 5/5 7/7
f 7/7 5/5 8/8
f 5/5 12/12 8/8
f 8/8 12/12 13/13



```
