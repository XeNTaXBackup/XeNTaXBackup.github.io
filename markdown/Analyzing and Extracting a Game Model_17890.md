## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:05:20+00:00
- Post Title: Analyzing and Extracting a Game Model

Attention: This topic is subject to the Manual Researching Section under the tutorial An Imitable Workflow for Reverse Engineering A Game Model.

Part III. Analyzing and Extracting a Game Model

Now we're about to officially start our journal of exploring a game archive.
First you'll need a proper hex editor. My recommendation would be [HexEdit](http://www.hexedit.com/default.aspx). And that's what I'm going to introduce in this tutorial. Get the lastest version [here](https://www.mediafire.com/file/b8wb4ainrm20vm3/HexEdit5build1349.zip).

This is how its UI looks like:



A few fields that you need to pay attention to:
The Offset Field: It records every address of the loaded file by columns and rows. By default the number of columns is set to 16 (0x10 in hex), but you can always expand them if you want to.
Hex View: The true nature of a file, which is consisted of an array of bytes. Each byte is represented by a two-digit hex number.
Text View: It converts each byte into human readable texts according to the ASCII table.
Toolbars: Here you can find some very useful functions. Choose what you need by navigating to View>Toobars. The most frequently used functions are the Calculator, the Bookmarks, and the Properties.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:10:40+00:00
- Post Title: Analyzing and Extracting a Game Model

Now it comes to the practical part. I'll take Marvel Avengers: Battle for Earth on Xbox 360 as an example. We're not going to start from the original 
game archives, but the extracted .nif files that contain the models.
Download the example files [here](https://mega.nz/#!ONFxgICb!ylDZFdLXpPMWn6_QlWiDXubaElRZW5ZTuCmcVUmTtAM).

The file we're going to work with is skrull_skin_m.nif. Let's open it in HexEdit. There're some strings at the front part of the file. 
We're not going to reverse the entire file structure since we only need the models. So let's focus on the geometry data. 

Usually it would be easier to locate the geo data by looking for the face buffer. As face indices are stored as an array of intergers, they usually look like a regular 
character table in the text view instead of some random bytes. 

Scroll down and we'll find the indices buffer approximately at offset 0x6760:


Let's keep that in mind, or we can set a bookmark with HexEdit here and return later. Now continue to scroll down. Then we find the structure 
changed around 0xE780.


These compact data should be the vertices chunk. Note that it doesn't have to come after the face buffer. Sometimes it could be at the front. 
But in this case, since the data before the face indices doesn't look compact, basically we can draw the conclusion.

Vertex data are defined as array(s) of vertex elements, and depending on the type of element making up the array(s), there're two most common structure of vertex data: "separate" and "structured".

"separate"
Separate arrays for every type of vertex attributes are defined, and they're placed in file one after another:

```
[
	v1 x y z;
	v2 x y z;
	v3 x y z;
	...	
]
vertex normals
[
	vn1 x y z;
	vn2 x y z;
	vn3 x y z;
	...	
]
vertex UVs
[
	vt1 u v;
	vt2 u v;
	vt3 u v;
	...	
]

```

"structured"
A structure of all vertex attributes is defined, of which the vertex array is made:

```
[
	{v1 x y z, vn1 x y z, vt1 u v};
	{v2 x y z, vn2 x y z, vt2 u v};
	{v3 x y z, vn3 x y z, vt3 u v};
	...
]

```
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:14:15+00:00
- Post Title: Analyzing and Extracting a Game Model

Next we need to figure out the size of one element of the array. 

The sequence bytes 00 10 catch our eyes at the first glance. 



And there're always 0x30 (48 in decimal) bytes between the former and the latter one. 
So let's expand the number of columns to 48, and we got this in the text view:



As you can see the bytes are aligned into a vertical pattern. So now every element of the array is hold exactly in one row. But to find the start of it we need to look at the binary values in the hex view. 
Now it's time to explain you how endianness works.

Endianness refers to the order in which the bytes of a multi-byte word are stored in memory. So the 4-byte value 0x11223344 is stored as 44 33 22 11 for little-endian, and 11 22 33 44 for big-endian. 

Usually Windows, PS4 and Android file systems use little endianness, while console file systems, like Wii, PS3 and Xbox 360, are using big endianness.

As I've mentioned before the game we're working with is for Xbox 360, so the file is in big-endian.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:18:06+00:00
- Post Title: Analyzing and Extracting a Game Model

Now we switch to the hex view:



We can easily identify that the sequence before the highlighted field is 00 04 02 34 instead of the expected 00 00 3C 00, which means the start offset of the vertices is 0xE7C3. The end offset should be at the same column when the data is aligned. We scroll down and find its end at 0x358B3:



You can see that the byte after 0x358B3 is not 0x2C but 0x01, which makes clear our earlier claim. As HexEdit shown, the total size of the vertex chunk is 0x270F0 ( = 0x358B3 - 0xE7C3). We devide it by 0x30, then we have the vertices count: 0xD05(3333).

Now let's do a little more research on the vertex format. Obviously it won't be the "separate" type as the vertex size 48 has already exceeded the maximum amount of bytes needed to store the 3 coordinates x, y and z (even if they use double type it costs merely 24 bytes).  So it's "structured" for sure. 

And we noticed that the sequence 3C 00 seems to be used for distinguishing different elements. We encounter the first 3C 00 after skipping 10 bytes from 0xE7C3. 

10 bytes are barely enough to hold 3 floats(= 12 bytes), so the data type could be short or half-float, both of which use 2 bytes. But there're still 4 bytes left, and natually we will assume that to be another two shorts or half-floats for UVs. 

Then right after the first 3C 00, there're 6 bytes following by another 3C 00, and this pattern repeats for 3 times. Assuming they are all two-byte values, they could be the normal, binormal and tangent vectors. That sounds quite reasonable.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:21:00+00:00
- Post Title: Analyzing and Extracting a Game Model

Now let's open this file in Hex2Obj. Press litE to change the endianness to big-endian, seq to handle "structured" data, noPtC to 
switch to display as point cloud, and fill in the start offset and count of the vertices.



For the data type of the vertices, let's try short type first. 
After clicking the mesh button we got the point cloud shown as in the left figure. 



Seems that is the UVs as we can see they' ll overlap if their 3rd coordinates are flatten. So let's change the offset to 0xE7C7 to 
skip these two values. The point cloud is as shown in the middle figure. 

It doesn't look correct though. Perhaps we should try with half-float now. Then we get the correct result as shown in the right figure.

So we can say that the data type of the vertices is half-float.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:25:21+00:00
- Post Title: Analyzing and Extracting a Game Model

After that let's return to the face indices block, which is at 0x6760 if you don't remember.
We know that our vertices count is 3333 < 65535(maximum value that an unsigned short can represent), so the indices should be using short intergers. 

All game models' face indices are stored as triangles (including those encoded as trixstrips), which means every face is represented by 3 indices. Usually the indices are stored in an increasing order so for most of the cases the first face will be 0, 1, 2. 
Base on these info, plus we've already known the endianness, it's not hard to locate its start: 0x6764. 



The sequence 00 01 02 15 seems more like some signature bytes(indeed it is), and it'll break the regularity if we take it into acount as part of the buffer. 
Besides, we can always correct that if our intuition failed. 

To get the indices count, we'll need to find where it ends. There's an easy way to do that if the faces are defined as a triangle list.
We scroll down to where the pattern changed, then set the number of columns to 3 x 2(the size of the indices data type), which is 6. 
And the last index should end at the same column as the first one.



So it ends at 0xE786. It's impossible to be 0xE78C as 0xF000 has far exceeded the vertices count 0xD05. We measure its size, divide it by 2, and get the indices count: 0x8022 / 2 = 0x4011 (16401). Now let's get the indices loaded:



Looks OK, except for some extra faces. Note that our current vertices count is 2686 out of 3333, which indicates that there're still 647 vertices left not displayed, and that their start offset of the vertices is different from the one we're using now:
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:27:27+00:00
- Post Title: Analyzing and Extracting a Game Model

You can grope around for the proper indices count of submesh1 by decreasing the amount and then check the result. But I'm not going to do it that way. 

We notice that the max vertex index is 2686 (0xA7E), which is larger than the remaining 647 (0x287). 
So the max index no doubts equals the vertex count of submesh1, and the remaining 647 is the one of submesh2. 
Now we're going to find the correspond indices counts for each submeshes according to the vertices counts we have. 

We don't know whether the file will use long or short type to store the counts, so we just search backward from the start of the vertices for the value as short, which is 0A 7E. 
And we actually found it right ahead of the vertices buffer:



And we can figure out the structure of this vertices header at once:

```
01					LOD ID?
00 02 70 F0		Vertices Size
00 00 00 02		Submesh Count
00 00 00 00		First Submesh's Starting Vertex Index
00 00 0A 7E		First Submesh's Vertices Count
00 00 0A 7E		Second Submesh's Starting Vertex Index
00 00 02 87		Second Submesh's Vertices Count
00 00 00 07		Vertices Element IDs Count (the following 7 4-byte sequences are the IDs). There'll be the same amount of elements in a vertex structure.

```
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:29:07+00:00
- Post Title: Analyzing and Extracting a Game Model

We didn't find any info about the face buffer here but we find some similar structure before the indices buffer:



```
00 00 80 22		Face Buffer Size
00 00 00 02		Submesh Count
00 00 00 00		First Submesh's Starting Index
00 00 34 0B		First Submesh's Indices Count
00 00 34 0B		Second Submesh's Starting Index
00 00 0C 06		Second Submesh's Indices Count
00 00 00 01		Indices Element IDs Count (the following sequence 00 01 02 15 is the ID)

```

So now we got both submesh's indices counts: 0x340B (13323) for submesh1, 0xC06 (3078) for submesh2. We sum them up and get 16401, which is exactly the total 
indices count we filled in Hex2Obj. Let's validate it:



So our guess is correct.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:31:10+00:00
- Post Title: Analyzing and Extracting a Game Model

Now it's time to handle the UVs. 
As you may recall, the UVs are ahead of the vertex coordinates, so we can't use its position relative to the coordinates to access to them. 
Instead, we use the obsolute offset of the UVs. The UVB size is the same as the vertices as they're under the same structure. 
We fill in the blanks with the right info, select HF_UV from the data type rollout, then press the UVs button:



Now let's save this model as an obj file by navigating to File>SaveAs mesh.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:32:41+00:00
- Post Title: Analyzing and Extracting a Game Model

We can even test with submesh2 if we want to. Just need several steps of calculations to obtain the start offsets:

Vertices: 0xE7C7 + 2686 * 48 = 0x2DF67
UVs: 0x2DF67 － 0x4 = 0x2DF63
FI: 0x6764 + 13323 * 2 = 0xCF7A

With the assistance of the calculator of HexEdit we can get the results within a few seconds.

We've already got the counts for submesh2: 3078 indices and 647 verts. So let's see how it goes:



Everything play as we expected. So far we can already build the model with all these infomation we have, but there're still some remaining bytes in 
that vertex structure. What are these data? You can actually find the answer from the strings at the front part of the file, which I told you not to pay 
much attention to:



But don't get it wrong. The only reason I skipped these strings is for teaching purpose. When you're actually researching a file format, you should make full 
use of these info. It'll definitely save you a lot of time.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:34:15+00:00
- Post Title: Analyzing and Extracting a Game Model

Up to now, I've shown you how to analyze a model format, and to use Hex2Obj to validate your guess. I've also left you with another nif file (iron_skin_m.nif). 
See if you can extract the model within on your own.

So, I guess that's all for this part.

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
## Post #12
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-08-24T10:33:47+00:00
- Post Title: Analyzing and Extracting a Game Model

Hello! I will try to explain myself in the best possible way. my problem is how I have to read all the data in front of me. It is not clear to me how I can recognize the point at which the vertices begin. If you need it, I leave you the model I'm trying to study. the model comes from a pc version.

[http://www.mediafire.com/file/54sj1d8kv ... 0.flv/file](http://www.mediafire.com/file/54sj1d8kvd663de/c1070.flv/file)
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-24T13:17:51+00:00
- Post Title: Analyzing and Extracting a Game Model

> Reply from dibe91
>
> my problem is how I have to read all the data in front of me.
Are you familiar with the terms of different data types described [here](http://forum.xentax.com/viewtopic.php?p=138999#p138999)?

> Reply from dibe91
>
> It is not clear to me how I can recognize the point at which the vertices begin.
When you find the first face buffer, scroll down to where the table changed. Then measure the size of each vertex:



FvFsize.jpg (56.26 KiB) Viewed 2300 times


Set the number of columns to 40(0x28) to align the vertex data, and you'll see where the vertex chunk begins:


Validate it with hex2obj:
## Post #14
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-08-25T05:27:56+00:00
- Post Title: Analyzing and Extracting a Game Model

> Reply from Bigchillghost
>
> Are you familiar with the terms of different data types described here?

I'm not very familiar with these terms, but I've asked for help from a friend, but it's not clear what you mean by "face buffer"
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-25T06:06:38+00:00
- Post Title: Analyzing and Extracting a Game Model

> Reply from dibe91
>
> 
I'm not very familiar with these terms
It's important to understand the concepts of these data types and you must be able to read the values of the integers. That's the basic requirement.

> Reply from dibe91
>
> but it's not clear what you mean by "face buffer"
It's just a term in computer science though it's placed in a file now. Check the wiki for a detailed explanation if you're interested:
[https://en.wikipedia.org/wiki/Data_buffer](https://en.wikipedia.org/wiki/Data_buffer)

You can comprehend the "face buffer" as "face indices data chunk", or "face indices array", or whatever else terms you can understand. It really doesn't matter anyway.
## Post #16
- Username: luckraken
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 05, 2018 4:45 am
- Post datetime: 2018-09-04T21:30:01+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

Hello, i followed your guide until you start talking about the UVs, then i wanted to try to extract a model up to that point on my own, and i managed to find the vertexs right, but now i can't find in any way the start of the faces.
So the model uses litE has a buffer of 40 (yours in the guide is 48 i dont know if buffer is the right word to indicate it) and maybe it's dWord but im not sure because for the vertexs in both ways seemed to work fine.
I looked to find a point with 00 00 00 01 00 02 but nothing, then i tought that maybe because its litE that would be 00 00 01 00 02 00 but nothing still.. so i tried to search for 00 00 00 00 00 00 00 01 00 00 00 02 

i don't know what else to try, what should i look for in this case?

Thank you very much in advance
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-05T00:19:52+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

for looking for faces what game and platform its for are good information to know to help you.
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-05T02:04:09+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

> Reply from luckraken
>
> i dont know if buffer is the right word to indicate it
It's OK to use that word. 

> Reply from luckraken
>
> maybe it's dWord but im not sure because for the vertexs in both ways seemed to work fine.
I guess you're reffering to the "Word"/"dWord" button of hex2obj? That's for face indices data types and does not affect how the vertex elements are read.

> Reply from luckraken
>
> 
...but now i can't find in any way the start of the faces...
I looked to find a point with 00 00 00 01 00 02 but nothing, then i tought that maybe because its litE that would be 00 00 01 00 02 00 but nothing still.. so i tried to search for 00 00 00 00 00 00 00 01 00 00 00 02 

i don't know what else to try, what should i look for in this case?
Searching for the "0 1 2" pattern is not what I usually do when looking for indices unless you're dealing with a really large file and you can't locate the face buffer with scrolling down till the end of file. But well you did and nothing found. The best solution is the one I described there:

> Reply from Bigchillghost
>
> ...looking for the face buffer. As face indices are stored as an array of intergers, they usually look like a regular character table in the text view instead of some random bytes.
For a more visualized description the face buffer looks like a disordered "alphabet".
About the endianness, you can get a clue there:

> Reply from Bigchillghost
>
> 
Usually Windows, PS4 and Android file systems use little endianness, while console file systems, like Wii, PS3 and Xbox 360, are using big endianness.
## Post #19
- Username: luckraken
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 05, 2018 4:45 am
- Post datetime: 2018-09-05T07:03:25+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

> Reply from chrrox
>
> for looking for faces what game and platform its for are good information to know to help you.

The game it's dark souls 2 , the model has been gave to me by a friend to try, i wrote that uses litE (little endianness) because it's for windows.

> Reply from Bigchillghost
>
> I guess you're reffering to the "Word"/"dWord" button of hex2obj? That's for face indices data types and does not affect how the vertex elements are read.

i see, learned something else new  

> Reply from Bigchillghost
>
> For a more visualized description the face buffer looks like a disordered "alphabet".

i forgot to tell that i searched for that, but i just found only very small buffers unlikely for the tutorial model you used
and so i'm having an hard time finding the right one, also because i cant look for 0,1,2,ecc i dont really know how to find the right start of the indexes
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-05T12:02:35+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

> Reply from luckraken
>
> but i just found only very small buffers unlikely for the tutorial model you used
Usually I just ignore any meshes with less than 4 pages of indices in an hex editor. Try finding a larger face buffer and return to the first one later if necessary.

> Reply from luckraken
>
> also because i cant look for 0,1,2,ecc i dont really know how to find the right start of the indexes
Indentifying the start of the first index is based on recognizing what data belongs to the face indices array, typically, the 0, 1, 2 pattern. You must read and check the values upwards the "alphabet" with your eyes whether it meets with the regularity of the face array. Sometimes you won't make it with a first test, so basically it's a matter of trial and error. 

There's an easier way to do it if the face buffer are triangle list instead of trixstrips. First step is to find a correct start of one face in the "alphabet" part, which can be done in no more than 3 trials. Then set the number of columns of the hex editor to 6 without changing the position of the found start of the face. Finally find the start of the first face forwards at the same column. You can apply the same process downwards to find the end of the buffer.
## Post #21
- Username: hiuuz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 12, 2017 5:21 pm
- Post datetime: 2019-12-20T13:42:39+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

Hi!

I'm have some knowledge about 3d modeling and the structure of a 3d model, it's not hard to understand how the vertex, face and other data stored in the files. Based on your tutorial I can repeat everything and get the mesh from the example file. But I would like to explore The Witcher 2 mesh files and I have difficulties to read the hexadecimal code. I mean I can see the changes in the text wiev and even in hex wiev but can't interpret the meaning of the data, I can't tell what I see is the face buffer or verex data or something else. Can I find somewhere a tutorial about how the hexadecimal code should be read in 3D models?
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-20T14:56:18+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

> Reply from hiuuz ↑Fri Dec 20, 2019 9:42 pm at Fri Dec 20, 2019 9:42 pm
>
> Can I find somewhere a tutorial about how the hexadecimal code should be read in 3D models?

You didn't read the Common Data Types section of [Part I. Background Knowledge before Starting](viewtopic.php?p=138999#p138999)?
There's a link under that section where you'll find the explaination of the terms and how they work.
## Post #23
- Username: hiuuz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 12, 2017 5:21 pm
- Post datetime: 2019-12-22T10:37:22+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

> Reply from Bigchillghost ↑Fri Dec 20, 2019 10:56 pm at Fri Dec 20, 2019 10:56 pm
>
> 
You didn't read the Common Data Types section of Part I. Background Knowledge before Starting?

Oh man, until now I only thought I knowing the stuff! In the last two days I read through that guide and others in here again and I start realizing that it's not enough reading through, I must UNDERSTAND what is written! Eg. what a 32bit floating number and how it looks in hex. Now I can see and find the blocked vertices table  Now I'm analizing the part's of a single vertex. That is the next big step.

Thank you enlighten me, that laziness was what blured my vision
## Post #24
- Username: Infernum31
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 01, 2023 4:37 pm
- Post datetime: 2023-10-07T19:02:30+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

Hi,is it possible to get the skel file from the embb file of the middle earth shadow of mordor game through hex?
## Post #25
- Username: Infernum31
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 01, 2023 4:37 pm
- Post datetime: 2023-10-08T16:57:56+00:00
- Post Title: Re: Analyzing and Extracting a Game Model

> Reply from Bigchillghost ↑Wed Mar 28, 2018 11:05 am at Wed Mar 28, 2018 11:05 am
>
> 

HOW TO EXTRACT THE MODEL FROM THE SOURCE ARCHIVES?
