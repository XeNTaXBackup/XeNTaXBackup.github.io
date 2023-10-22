## Post #1
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-11T15:06:24+00:00
- Post Title: Help retrieving faces from a file with one mesh

Hey guys, I'm a bit new to the whole game research thing although I have some programming experience.

I'm trying to extract the models from a game, I manage to do it on the files that have the mesh faces with 4 constant values on int16's separated by 0xFFFF but on other files I get random number of face values between the 0xFFFF, Examples:
FFFF 003F 0029 0010 0011 000F 002B 0032 0034 0033 0035 0037 0036 0039 0038
FFFF 0029 002A 0011 002B
FFFF 002A 003A 002B 003B 0034 0013 0035 0012 0040
FFFF 0012 0013 0014 003B 003A
FFFF 0038 0036 0040 0035
FFFF 00B5 00B6 00B4 00B7 00BB 00BC 00B9 0101 0109 0100 0107 010A 010F 00FE 0102 00FD FFFF 00BC 00B7 0101 0100
If I only had 4 int16's separated by the 0xFFFF like the other files this would be easy but I have no clue what to do here.

Any idea why some files have constant 4 values faces and others dont? If yes how can I organize the faces data to display it properly?

This might be a simple question but as I said, Im a bit new.

Thank you in advance for any help.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-11T20:37:26+00:00
- Post Title: Help retrieving faces from a file with one mesh

it might be due to the rendering mode of the polygons - [https://en.wikipedia.org/wiki/Triangle_strip](https://en.wikipedia.org/wiki/Triangle_strip) - for example only 2 vertex points are needed to make a triangle. other modes vary

obviously also the value 0xFFFF is -1 as a signed short type
## Post #3
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-12T15:50:57+00:00
- Post Title: Help retrieving faces from a file with one mesh

> Reply from WRS
>
> it might be due to the rendering mode of the polygons - https://en.wikipedia.org/wiki/Triangle_strip - for example only 2 vertex points are needed to make a triangle. other modes vary

obviously also the value 0xFFFF is -1 as a signed short type

Thank you, you helped me understand it a bit.
Is there anywhere were I can check the formats that are usually used, especially (for the faces), or how to identify them?
I have a few other questions though if you don't mind answering. The model I'm trying to extract Noesis already supports it (partially). So I'm kind of trying to "recreate" it to be able to extract all the data correctly.
For example in the case of the mesh that I have 5 values that end (or start) with 0xFFF, I have 1020 bytes, I know from the info I get in Noesis that it has 204 triangles, if I divide the 1020 bytes by 5 (= 204) I dont have any decent data (5 bytes don't seam to be enough data for a face) but if I divide the 1020 bytes by 10 (half the triangles) the data seems to make much more sense (4 signed shorts), so does that mean that each 5 shorts give the data for 2 faces? Also I have no idea how to use that data to "build" the faces into an .obj file for example. Example data:


 0 - 1 - 2 - 5 - 65535 - (0000000100020005FFFF)
 5 - 1 - 4 - 3 - 65535 - (0005000100040003FFFF)
 3 - 1 - 6 - 7 - 65535 - (0003000100060007FFFF)
(102 total) (the bytes might not be in the correct order, its just an example)

And that same data after being exported into .obj by Noesis is:

f  1/1/1 2/2/2 3/3/3
f  4/4/4 3/3/3 2/2/2
f  4/4/4 2/2/2 5/5/5
f  6/6/6 5/5/5 2/2/2
f  6/6/6 2/2/2 7/7/7
f  8/8/8 7/7/7 2/2/2
(204 total)

There is an obvious relation between those values especially if I increment them all by 1, but I have no idea how to "put it together". Is it engine related?

Thank you.
## Post #4
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-15T11:57:11+00:00
- Post Title: Help retrieving faces from a file with one mesh

Already got this solved on another topic.
Thank you
