## Post #1
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-23T18:23:22+00:00
- Post Title: matrix path of neo

Yeah I know the game is old but I love it. 
After writing this topic I did a search but I never founded anything.
Well, after installing the pc version I watch a folder called 'actors'. I think there are the models of the characters.
the file formats are '.mlb_INW11' and '.dcn_11 files'. In internet there isn't anything except this [http://wiki.xentax.com/index.php?title= ... ath_of_Neo](http://wiki.xentax.com/index.php?title=Game_Tools#Matrix:_Path_of_Neo) , it's about the textures and the link never works.
here there are some files from the game:
[http://www.mediafire.com/?c8m9fgt7w2xnptr](http://www.mediafire.com/?c8m9fgt7w2xnptr)
thanks in advance for the reply and sorry for my bad english.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-23T18:36:02+00:00
- Post Title: matrix path of neo

Textures are stored inside the material library (mlb_INW11). They're just regular DDS files with a custom header.

dcm_INW11 I guess would be the models. Looks like a mesh anme followed by vertex and index buffers, but not sure.

At least, the data is in plain sight.
## Post #3
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-24T09:10:42+00:00
- Post Title: matrix path of neo

> Reply from finale00
>
> Textures are stored inside the material library (mlb_INW11). They're just regular DDS files with a custom header.

dcm_INW11 I guess would be the models. Looks like a mesh anme followed by vertex and index buffers, but not sure.

At least, the data is in plain sight.
well, is there any extractor?
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-22T22:00:02+00:00
- Post Title: matrix path of neo

The .dcn files have the following format:
Offset 0X1c is a 4byte Integer that tells us the amount of data that will be in the mandatory section
of every dcn file. We will get back to this in a second.

Offset 0x48 is a 4ByteInteger that tells us the number of meshes in the dcn file.
Offset 0x4C is unknown.
Starting at offset of 0x50 is an entry for each of the meshes in an dcn file.
We need to use the first entry to calculate the rest of the entries.
What we do is subtract the first entry from all entries.
Then the calculated first entry will be 0x00 which we will define as beginning right after the mandatory section and
is the first mesh. Then the second mesh will be the calculated by adding it to right after the mandatory section.

For example reading from offset 0x48 from the niobe_lp2.dcn_11 file (the lp2 means low polygon mesh level of detail 2)
we have:
04 00 00 00 -The mesh count
0B 00 00 00 -Unknown
CC 73 71 0F First mesh
1C 79 71 0F Second mesh
FC 82 71 0F Third mesh
DC 8C 71 0F Fourth mesh
We subtract CC 73 71 0F from each entry to get
0x0 First mesh
0x550 Second mesh
0xF30 Third mesh
0x1910 Fourth mesh

These offsets are releative to after the mandatory section (some type of bone/shadow/collision/unknown matrix)
The mandatory section begins right after the mesh offset table. And the size of the mandatory section is the integer
located in offset 0X1c multipled by the integer 3C.

Thus the first mesh begins at offset:
0x50 + [0x48]*0x4 + [0x1c]*0x3C
Which in the niobe_lp2.dcn_11 is offset 0x144c
Thus the meshes begin as follows:
First Mesh 0x144c
Second Mesh 0x550+0x144c
Third Mesh 0xF30+0x144c
Fourth Mesh 0x1910+0x144c


Then there is the format and types of meshes. More on that tomorrow (EST time Monday)
## Post #5
- Username: Leocodorna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 31, 2017 3:56 pm
- Post datetime: 2023-05-23T13:20:03+00:00
- Post Title: matrix path of neo

Hi, I was revisiting this game after this many years.
Do you have an extractor or something?
I am a 3d artist and It would be nice to mod de animations and the models.
