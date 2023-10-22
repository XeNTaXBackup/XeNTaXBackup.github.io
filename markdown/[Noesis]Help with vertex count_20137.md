## Post #1
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-04-29T04:24:00+00:00
- Post Title: [Noesis]Help with vertex count

Hi, I'm a newbie in parsing 3d model. I'm learning to write my own Noesis script. I have a question:

Based on my knowledge in using shakotay's hex2obj, I know that we have 3 ways to get the vertex count:
- It is defined in the data
- Divide vertex block length by 1-vertex stride length
- Max face index

Unfortunately, the file that I'm working on doesn't have defined vertex count but in another file. As far as I know, Noesis scripts must have VCount and FCount. Since I'm a newbie, I just want to work with a single format only. Is there any solution for this case? Thanks in advance   

P/s: Also, regarding to the files that have vertex count defined in them, how can we recognize "vertex count" exactly?
[Sample.zip](https://xentaxbackup.github.io/file/16131_Sample.zip)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-29T10:51:50+00:00
- Post Title: [Noesis]Help with vertex count

interesting sample. you interpretation is not entirely correct or imcomplete. anyway...

if you know the file that contains the buffer lenghts or vertex or index counts or whatever describes this data container you should load that first and then the data file. how you do it depends if the description file has the same name or got a filename in it that relates to the data file here.

have an xsample code. [http://www.mediafire.com/file/39v5gg5t9 ... ed_wip.rar](http://www.mediafire.com/file/39v5gg5t9touilb/cwa_rigged_wip.rar) it's slightly messy and maybe to advanced to read for you rn. but you should get something out of it and get there. no file examples, cause they are not relevant. the adr file just links the model and skeleton. but you get the idea of file relations. you base the script on and load the file higher in the hierarchy aka the description first then load the data container into this 2nd bytearray and bitstream, to parse it. be smart and label your bitstreams. makes it all easy. you can access the description and data at the same time and composite/compile whatever you need in the process.

now, for this example: those are multiple 'submeshes'. the first vertex count is 52 you should get that from the description file. you potentially have a vertex stride to figure out, but it could be an all in one default format. either way.

52 * 48 bytes - position+w, normal+pad, tangent+bitangentsign
52 * 32 bytes - 4 * blendweights + 4 * blendindices (uint32)
52 * 8 bytes - tu + tv

then the indices of 48 triangles or 144 (x3) index length you should get from the description too. whether the description contains buffer size or relative offsets the next part/submesh starts at 0x1270.

for the sake of readability: when you have power of two components or arrays that align, you can write hex notation. absolute offsets or relatively (0x10) aligned jumps should be written as hex too.
## Post #3
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-04-29T16:55:17+00:00
- Post Title: [Noesis]Help with vertex count

> Reply from episoder
>
> 
makes it all easy. you can access the description and data at the same time and composite/compile whatever you need in the process.

This is my first attempt to write a script, that's why I wanted to make it basic as it could be and handle a single file only. However, due to your example code and chroxx's answer in another old thread, I'm successfully in importing 2 files at the same time in my script. Thank you 





> then the indices of 48 triangles or 144 (x3) index length you should get from the description too. whether the description contains buffer size or relative offsets the next part/submesh starts at 0x1270.

In my attachment, .srd is the file that contains the count, and the vertex count is the Int32, starts from 21th byte after "$VTX". 34 00 00 00 (LE) is equal to 52 in dec


Then there came a new problem: I found vertex counts but not face counts or anything related to "face" in that file. What should I do now?
[Sample1.zip](https://xentaxbackup.github.io/file/16133_Sample1.zip)
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-29T17:26:12+00:00
- Post Title: [Noesis]Help with vertex count

at 0x430 you have the offset and count for the index buffer. this probalby belongs into this $RSI structure. guessing the "I" is something index releated.
## Post #5
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-04-30T12:57:47+00:00
- Post Title: [Noesis]Help with vertex count

Thanks so much for your help  I got it
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-30T18:25:19+00:00
- Post Title: [Noesis]Help with vertex count

you know it's just the first mesh in this file tho, do you?!? anyway. glad you figured it out.
## Post #7
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-05-01T04:24:35+00:00
- Post Title: [Noesis]Help with vertex count

Obviously I know it as I have worked on this file by using hex2obj . That mesh was just a test to help me know if I was on the right track.

Otherwise, I'm trying to figure out the way to work with all remaining submeshes. 

That's very kind of you, I fully appreciate it
