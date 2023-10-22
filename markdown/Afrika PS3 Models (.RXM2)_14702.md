## Post #1
- Username: Dacentru
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 14, 2015 6:54 pm
- Post datetime: 2016-07-31T18:36:08+00:00
- Post Title: Afrika PS3 Models (.RXM2)

Hi, I managed to extract the data of Afrika using the script posted by FurryFan here:
[viewtopic.php?f=10&t=5346](http://forum.xentax.com/viewtopic.php?f=10&t=5346)

Like he said, the textures are simple .dds but the model format is .rxm2. 
I'll leave some samples if someone wants to look into it. 

[https://mega.nz/#!yoM21YjD!mh9KrwOq9-Q9 ... ee8DZlxgIc](https://mega.nz/#!yoM21YjD!mh9KrwOq9-Q98dluLnpu6bK-q2_jlnxBTee8DZlxgIc)

Thank you for reading !
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-31T21:39:41+00:00
- Post Title: Afrika PS3 Models (.RXM2)

this thread might get more attention in the "3D/2D models" section   

here is the first submesh of elephant_adult.rxm2  



elephant_adult_rxm2.png (28.38 KiB) Viewed 307 times
## Post #3
- Username: Dacentru
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 14, 2015 6:54 pm
- Post datetime: 2016-08-01T07:21:04+00:00
- Post Title: Afrika PS3 Models (.RXM2)

Oh sorry, I was first thinking about posting in "3D/2D models" but some of the threads I read apparently more belonged here so I did the same. :/

And wow !! How did you managed to to do that ? 
Thank you for replying so fast too, I thought I would never get any answer. 

Edit : With Hex2Obj apparently.  I'll try that, thanks !
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-08T18:05:25+00:00
- Post Title: Afrika PS3 Models (.RXM2)

there's too many submeshes (about 20) than to make senseful use of hex2obj:



elephant_adult_rxm2.JPG (36 KiB) Viewed 228 times
## Post #5
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2017-06-14T00:47:47+00:00
- Post Title: Afrika PS3 Models (.RXM2)

so could it be possible to make a script to get the models with noesis?

I would think it is possible.

How did you get the model into blender? 

that's a format I have been trying to crack for a long time!
## Post #6
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2017-09-04T07:40:20+00:00
- Post Title: Afrika PS3 Models (.RXM2)

I was trying to extract from this game, too

but I don't know where the start and end vertices are, and the uv coordinates.

How did you extract that elephant?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-04T15:46:05+00:00
- Post Title: Afrika PS3 Models (.RXM2)

it's a function in my Make_obj project.

(Don't remember why I didn't provide an extractor; guess it just worked with that elephant only
and I had no interest to care for other models.)
## Post #8
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2017-09-04T19:39:29+00:00
- Post Title: Afrika PS3 Models (.RXM2)

this might be my last question,

but do you know exactly where the start and end of the vertices, faces, and uv coordinates begin?

if theres any uv coordinates.

sorry if I'm bothering you about it, I was just curious.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-04T20:49:08+00:00
- Post Title: Afrika PS3 Models (.RXM2)

did you ever look at an rxm2 file in a hex editor? Did you look at the params (addresses, counts) in Ace's post?
Did you use hex2obj, did you do the tutorial ('tut' button)? Should have answered most of your questions.
(Since this format uses half floats it's not that simple for noobs.)

Most face indices (FIs) blocks to be found be searching for 0000 0001 0002 (big endian format). You'll find 13 blocks, should be 6 or 7 more, but with different starting FIs.

Start of vertex blocks, plain to see, they are preceeded by 00000010 FFFFFFFF, add 16 to the offset where that signature is to be found and your done.

uvpos is 10, may vary, don't remember. How to find? Experience or trial and error.
