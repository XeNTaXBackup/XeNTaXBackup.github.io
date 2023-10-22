## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2019-03-07T12:07:03+00:00
- Post Title: MESH format ".bm" Rakion, file addded

Hello I was searching for weeks and did not find a way to open the ".bm" file of Rakion, it contains the 3d model, maybe someone knows how to open it or could give me some advice what I could do, it would be very helpful . Thanks in advance.
img][https://imgur.com/CV8cxqW](https://imgur.com/CV8cxqW)[/img]  and there is the file format, hope someone could help me
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-07T13:53:30+00:00
- Post Title: MESH format ".bm" Rakion, file addded

using hex2obj (view links in my sig):



sword-bm.png (48.03 KiB) Viewed 170 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2019-03-07T20:42:13+00:00
- Post Title: MESH format ".bm" Rakion, file addded

Thanks alot for  this! I was searching a lot. By the way where u got the values of 12, 103c, 99, 8 and also the 41 XD, I'm trying to find how do you get that values with the tutorial but don't understand how you get these values. Thanks also!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-07T21:51:28+00:00
- Post Title: MESH format ".bm" Rakion, file addded

1st of all: learn how to detect floats. If you can't you're lost. As simple as that.

floats consists of 4 bytes (half floats of two).

You need to gain experience by checking some dozens of simple examples in the forum where hex2obj was used.
And you need to learn some basics.

Understand how to get 15ac, 408 and 41, 170 (the simple part).

Once you succeeded I can explain FVFsize: 12, and 103c and 8 (harder part).




3D_format.png (37.75 KiB) Viewed 151 times
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2019-03-07T22:03:25+00:00
- Post Title: MESH format ".bm" Rakion, file addded

I already know how to get the value 41 and the others values! now need the vertex block values only!. Thanks for answer!
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-07T22:17:14+00:00
- Post Title: MESH format ".bm" Rakion, file addded

8 is 2 floats for texture coords tx, ty.

"99" is a flag only, that tells you: uvs are in a separate uvb block.
Start address of that block= 0x41 + size of vertexblock+ size of normals block // 0x41 + vertexcount x (12+12) = 0x1031 // 12 is decimal, 3x4 floats
+ Dword_string_length + string_length // 4 + 7
= 0x103C
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2019-03-07T22:53:06+00:00
- Post Title: MESH format ".bm" Rakion, file addded

I apologize, I have doubts, how to know where to find the values of:
size of vertexblock
size of normals block
Dword_string_length
string_length

Really thanks for taking the time to answer me, I'm learning
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2019-03-07T23:39:12+00:00
- Post Title: MESH format ".bm" Rakion, file addded

Thanks aloot!!!



test.jpg (119.66 KiB) Viewed 139 times
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-08T05:30:26+00:00
- Post Title: MESH format ".bm" Rakion, file addded

You*re learning very fast!  Cool!

Dword_(for)_string_length: size of DWORD is 4 (value is 7, the string length)
string_length (of "Texture") is 7

size of vertexblock: vertex_count x 12
size of normals block: vertex_count x 12

since size of vertices is 3 floats (3x 4 bytes)
size of normals is 3 floats (3x 4 bytes)
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2019-03-08T13:25:31+00:00
- Post Title: MESH format ".bm" Rakion, file addded

Thank you for clarifying all my doubts
## Post #11
- Username: prielgaier
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 23, 2020 4:23 am
- Post datetime: 2021-06-23T00:19:26+00:00
- Post Title: MESH format ".bm" Rakion, file addded

Was wondering if you created a converter for bm to obj or should i start learning what you've learnt
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-06-23T19:00:10+00:00
- Post Title: MESH format ".bm" Rakion, file addded

Do you have an unpacker for the Rakion.xfs file?
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-23T19:53:47+00:00
- Post Title: MESH format ".bm" Rakion, file addded

I did a crappy Noesis script - I'll post it when it works properly.  It would be good to get a few examples of models with their textures to do some proper testing.
