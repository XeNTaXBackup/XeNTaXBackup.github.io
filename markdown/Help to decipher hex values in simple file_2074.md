## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-04T18:08:49+00:00
- Post Title: Help to decipher hex values in simple file

Here is something which really made me pull my hair (not that I lost many as a result   ). 

I have quoted here two simple files with their text version down below the hex part. 
The problem   ,  I cannot find any of the values mentioned in the text form (like x, y, angle) in their hex part.  I can submit original files for perusal in hex editor:
[http://files.filefront.com//;5469770;;/](http://files.filefront.com//;5469770;;/)
 Can someone help me here?

[quote]
Report on file D:\VAULT\SFP1TerEditor\DESERT\desert1_1tree205_49
Offset 00000000 to 00000158
Mon Sep 04 12:44:02 2006 

Offset	Bytes	Text
00000000 	00	00	00	00	01	00	00	00	64	00	00	00	08	00	00	00	0c	00	00	00	04	00	00	00	b7	fd	c7	44	7d	5b	bc	43	 .......d......... ...Â·Ã½Ã‡D}[Â¼C 
00000020 	00	00	00	00	00	00	00	00	00	00	00	00	00	00	80	3f	00	00	80	3f	00	00	80	3f	49	66	c8	44	83	74	c2	43	 ..............â‚¬?..â‚¬?..â‚¬?IfÃˆDÆ’tÃ‚C 
00000040 	00	00	00	00	00	00	00	00	00	00	00	00	00	00	80	3f	00	00	00	00	00	00	80	3f	49	66	c8	44	83	74	c2	43	 ..............â‚¬?......â‚¬?IfÃˆDÆ’tÃ‚C 
00000060 	00	03	4a	41	00	00	00	00	00	00	00	00	00	00	80	3f	00	00	00	00	00	00	00	00	b7	fd	c7	44	7d	5b	bc	43	 . JA..........â‚¬?........Â·Ã½Ã‡D}[Â¼C 
00000080 	00	03	4a	41	00	00	00	00	00	00	00	00	00	00	80	3f	00	00	80	3f	00	00	00	00	df	6e	c7	44	23	39	c0	43	 . JA..........â‚¬?..â‚¬?....ÃŸnÃ‡D#9Ã€C 
000000a0 	00	00	00	00	00	00	00	00	00	00	00	00	00	00	80	3f	00	00	80	3f	00	00	80	3f	21	f5	c8	44	dd	96	be	43	 ..............â‚¬?..â‚¬?..â‚¬?!ÃµÃˆDÃ
## Post #2
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-06T21:20:00+00:00
- Post Title: Help to decipher hex values in simple file

Sorry, I can't seem to help you with this one. 
I see no correlation between those floating point numbers and the hex values, at least in any number system I'm familiar with.

How do you know that the text files are a representation of those binaries?

/mikew
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-07T01:44:32+00:00
- Post Title: Help to decipher hex values in simple file

Yeah, 
it is tough one.   

However I KNOW that each file represent 2x2 sided polygons X crossed with semitransparent tree on each side of poly. 
Here are my educated guesswork: 
01 is # of object in the file - 1 tree each 
64 is chance (100) 
08 # of vertexes (both polygons do not have any common cross 0edge)   
EDIT: no perhaps it is ID of the object. 

0C (12) # of vertexes if each polygon is subdivided into triangular faces 
4 triangles 3 vert each =12 (far fetched, but you never know) 

Then there are floats with some sizes, distances or coordinates   . I think they maybe somehow show pos of the vert related to position on the tile. The tile is 256x256 ( it is not just pixels, but coordinates in text part represent relative position of the object on the plane ( where 0,0 upper left and 256,256 lower right).   Maybe the floats are measured from the center ???

On the end I see description of each vertices 00 through 07 = 8 vert.
803F - no idea.    I saw somewhere 403F too. 

I post now file with 4 elements. Box and 3 X trees.
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-07T02:09:15+00:00
- Post Title: Help to decipher hex values in simple file

Report on file D:\VAULT\desert3rd3treesandbuilding
Offset 00000000 to 000006ec

Mon Sep 04 09:40:39 2006 

--------------------------------------------------------------------------------
Offset Bytes Text 
00000000  01 00 00 00 03 00 00 00 64 00 00 00 14 00 00 00 1e 00 00 00 0a 00 00 00 00 da 84 44 00 c0 85 44  ......d......... ....Ãšâ€žD.Ã€â€¦D  
00000020  00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 80 3e 00 00 40 3f 00 ba 86 44 00 c0 85 44  ..........â‚¬?......â‚¬>..@?.Âºâ€ D.Ã€â€¦D  
00000040  00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 00 00 00 00 40 3f 00 ba 86 44 00 c0 85 44  ..........â‚¬?..........@?.Âºâ€ D.Ã€â€¦D  
00000060  00 00 70 41 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 00 00 00 00 00 3f 00 da 84 44 00 c0 85 44  ..pA......â‚¬?...........?.Ãšâ€žD.Ã€â€¦D  
00000080  00 00 70 41 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 80 3e 00 00 00 3f 00 ba 86 44 00 c0 85 44  ..pA......â‚¬?......â‚¬>...?.Âºâ€ D.Ã€â€¦D  
000000a0  00 00 00 00 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 00 3f 00 00 40 3f 00 ba 86 44 00 e0 83 44  ......â‚¬?...â‚¬.......?..@?.Âºâ€ D.Ã Æ’D  
000000c0  00 00 00 00 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 80 3e 00 00 40 3f 00 ba 86 44 00 e0 83 44  ......â‚¬?...â‚¬......â‚¬>..@?.Âºâ€ D.Ã Æ’D  
000000e0  00 00 70 41 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 80 3e 00 00 00 3f 00 ba 86 44 00 c0 85 44  ..pA..â‚¬?...â‚¬......â‚¬>...?.Âºâ€ D.Ã€â€¦D  
00000100  00 00 70 41 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 00 3f 00 00 00 3f 00 ba 86 44 00 e0 83 44  ..pA..â‚¬?...â‚¬.......?...?.Âºâ€ D.Ã Æ’D  
00000120  00 00 00 00 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 40 3f 00 00 40 3f 00 da 84 44 00 e0 83 44  .......â‚¬..â‚¬Â¿......@?..@?.Ãšâ€žD.Ã Æ’D  
00000140  00 00 00 00 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 00 3f 00 00 40 3f 00 da 84 44 00 e0 83 44  .......â‚¬..â‚¬Â¿.......?..@?.Ãšâ€žD.Ã Æ’D  
00000160  00 00 70 41 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 00 3f 00 00 00 3f 00 ba 86 44 00 e0 83 44  ..pA...â‚¬..â‚¬Â¿.......?...?.Âºâ€ D.Ã Æ’D  
00000180  00 00 70 41 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 40 3f 00 00 00 3f 00 da 84 44 00 e0 83 44  ..pA...â‚¬..â‚¬Â¿......@?...?.Ãšâ€žD.Ã Æ’D  
000001a0  00 00 00 00 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 00 3f 00 00 40 3f 00 da 84 44 00 c0 85 44  ......â‚¬Â¿...........?..@?.Ãšâ€žD.Ã€â€¦D  
000001c0  00 00 00 00 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 80 3e 00 00 40 3f 00 da 84 44 00 c0 85 44  ......â‚¬Â¿..........â‚¬>..@?.Ãšâ€žD.Ã€â€¦D  
000001e0  00 00 70 41 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 80 3e 00 00 00 3f 00 da 84 44 00 e0 83 44  ..pA..â‚¬Â¿..........â‚¬>...?.Ãšâ€žD.Ã Æ’D  
00000200  00 00 70 41 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 00 3f 00 00 00 3f 00 da 84 44 00 c0 85 44  ..pA..â‚¬Â¿...........?...?.Ãšâ€žD.Ã€â€¦D  
00000220  00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 80 3e 00 ba 86 44 00 c0 85 44  ..pA..........â‚¬?......â‚¬>.Âºâ€ D.Ã€â€¦D  
00000240  00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 3e 00 00 80 3e 00 ba 86 44 00 e0 83 44  ..pA..........â‚¬?...>..â‚¬>.Âºâ€ D.Ã Æ’D  
00000260  00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 3e 00 00 c0 3e 00 da 84 44 00 e0 83 44  ..pA..........â‚¬?...>..Ã€>.Ãšâ€žD.Ã Æ’D  
00000280  00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 c0 3e 00 00 02 00 01 00 00 00  ..pA..........â‚¬?......Ã€>......  
000002a0  03 00 02 00 04 00 06 00 05 00 04 00 07 00 06 00 08 00 0a 00 09 00 08 00 0b 00 0a 00 0c 00 0e 00  ......... . .. . . ..  
000002c0  0d 00 0c 00 0f 00 0e 00 10 00 12 00 11 00 10 00 13 00 12 00 00 00 00 00 00 00 f0 40 00 00 f0 40   . ...............Ã°@..Ã°@  
000002e0  00 00 70 41 00 00 00 00 a4 b4 29 41 00 ca 85 44 00 d0 84 44


00 00 00 00 00 00 00 00 32 00 00 00  ..pA....Â¤Â´)A.ÃŠâ€¦D.Ã
## Post #5
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-07T13:32:25+00:00
- Post Title: Help to decipher hex values in simple file

Using our "TAW" method of formating in text format here is that 1st part:
the Building Box


> Header of the entire file 
>
> 
>
> 01 00 00 00 03 00 00 00 
>
> 1 Building  3 Trees
>
> 
>
> Here starts Building Box 
>
> 64 00 00 00 14 00 00 00 1e 00 00 00 0a 00 00 00 00 
>
> 64 means chance 100, 
>
> 14 means 20 - maybe ID of the model but maybe also # of vertexes at the same time           
>
> 
>
> here start coordinates they are floats I will post translation to DEC later
>
> they are either 4 pairs 2+2+2+2 (?)
>
> or 2 +3 +3 which would be 2 (?) + xyz + xyz.
>
> but why so many    
>
> 
>
> 00 da 84 44 
>
> 00 c0 85 44 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 80 3f 
>
> 00 00 00 00 
>
> 00 00 80 3e 
>
> 00 00 40 3f 
>
> 
>
> and another set .....
>
> 00 ba 86 44  
>
> 00 c0 85 44  
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 80 3f  
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 40 3f  
>
> 
>
> here is the rest of the coordinates - total 20 records which corresponds to the same # of vertices
>
> 00 ba 86 44 00 c0 85 44 00 00 70 41 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 00 00 00 00 00 3f 
>
> 00 da 84 44 00 c0 85 44 00 00 70 41 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 80 3e 00 00 00 3f 
>
> 00 ba 86 44 00 c0 85 44 00 00 00 00 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 00 3f 00 00 40 3f 
>
> 00 ba 86 44 00 e0 83 44 00 00 00 00 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 80 3e 00 00 40 3f 
>
> 00 ba 86 44 00 e0 83 44 00 00 70 41 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 80 3e 00 00 00 3f 
>
> 00 ba 86 44 00 c0 85 44 00 00 70 41 00 00 80 3f 00 00 00 80 00 00 00 00 00 00 00 3f 00 00 00 3f 
>
> 00 ba 86 44 00 e0 83 44 00 00 00 00 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 40 3f 00 00 40 3f 
>
> 00 da 84 44 00 e0 83 44 00 00 00 00 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 00 3f 00 00 40 3f 
>
> 00 da 84 44 00 e0 83 44 00 00 70 41 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 00 3f 00 00 00 3f 
>
> 00 ba 86 44 00 e0 83 44 00 00 70 41 00 00 00 80 00 00 80 bf 00 00 00 00 00 00 40 3f 00 00 00 3f 
>
> 00 da 84 44 00 e0 83 44 00 00 00 00 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 00 3f 00 00 40 3f 
>
> 00 da 84 44 00 c0 85 44 00 00 00 00 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 80 3e 00 00 40 3f 
>
> 00 da 84 44 00 c0 85 44 00 00 70 41 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 80 3e 00 00 00 3f 
>
> 00 da 84 44 00 e0 83 44 00 00 70 41 00 00 80 bf 00 00 00 00 00 00 00 00 00 00 00 3f 00 00 00 3f 
>
> 00 da 84 44 00 c0 85 44 00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 80 3e 
>
> 00 ba 86 44 00 c0 85 44 00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 3e 00 00 80 3e 
>
> 00 ba 86 44 00 e0 83 44 00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 3e 00 00 c0 3e 
>
> 00 da 84 44 00 e0 83 44 00 00 70 41 00 00 00 00 00 00 00 00 00 00 80 3f 00 00 00 00 00 00 c0 3e 
>
> 
>
> Here are the vertexes 20 of them 
>
> they are grouped into ....triangles I think 
>
> 
>
> 00 02 00 01 00 00 
>
> 00 03 00 02 00 04 
>
> 00 06 00 05 00 04 
>
> 00 07 00 06 00 08 
>
> 00 0a 00 09 00 08 
>
> 00 0b 00 0a 00 0c 
>
> 00 0e 00 0d 00 0c 
>
> 00 0f 00 0e 00 10 
>
> 00 12 00 11 00 10
>
> 00 13 00 12 00 00 
>
> 00 00 00 00 
>
> 
>
> 
>
> This I have no clue... for now 
>
> 00 f0 40 00 
>
> 00 f0 40 00 
>
> 00 70 41 00 
>
> 00 00 00 a4 
>
> b4 29 41 00 
>
> ca 85 44 00 
>
> d0 84 44 00 00 00 00 00 00 00 00

EDIT: 
and finaly Text (extract ) of the above 

> [desert1.bmp] 
>
> ObjectCount=4 
>
> Object000.TypeName=Box Building1 
>
> Object000.MapClass=0 
>
> Object000.Chance=100 
>
> Object000.PositionX=137.000000 
>
> Object000.PositionY=136.000000 
>
> Object000.Angle=0.000000

As you can see the text extract which I was trying to match is really very piece of information about the file above. So that is why it was and STILL IS so difficult to see the connection.
## Post #6
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-08T01:03:31+00:00
- Post Title: Help to decipher hex values in simple file

deleted
## Post #7
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-08T10:41:13+00:00
- Post Title: Help to decipher hex values in simple file

Just to let you know that I don't have the time to look into this,or TAW, at the moment. Please keep posting anything relevant though.
I'll hopefully be back in action sometime next week...assuming you haven't solved everything in the meantime.
## Post #8
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-10T03:18:41+00:00
- Post Title: Help to decipher hex values in simple file

Here is 2nd installment of float values. 

```
00 e0 83 44 	1.05500000e+003
00 00 70 41 	1.50000000e+001
00 00 00 80 	0.00000000e+000
00 00 80 bf 	-1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 00 3f 	5.00000000e-001
00 00 00 3f 	5.00000000e-001

00 ba 86 44 	1.07781250e+003
00 e0 83 44 	1.05500000e+003
00 00 70 41 	1.50000000e+001
00 00 00 80 	-1.00000000e+000
00 00 80 bf 	-1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 40 3f 	7.50000000E-001 
00 00 00 3f 	5.00000000E-001 

00 da 84 44 	1.06281250e+003
00 e0 83 44 	1.05500000e+003
00 00 00 00 	0.00000000e+000
00 00 80 bf 	-1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 00 3f 	5.00000000E-001 
00 00 40 3f 	7.50000000E-001 

00 da 84 44 	1.06281250e+003
00 c0 85 44 	1.07000000e+003
00 00 00 00 	0.00000000e+000
00 00 80 bf 	-1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 80 3e 	2.50000000e-001
00 00 40 3f 	7.50000000E-001 

00 da 84 44	1.06281250e+003
00 e0 83 44	1.05500000e+003
00 00 70 41 	1.50000000e+001
00 00 80 bf 	-1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 00 3f 	5.00000000e-001
00 00 00 3f 	5.00000000e-001

00 da 84 44 	1.06281250e+003
00 c0 85 44 	1.07000000e+003
00 00 70 41 	1.50000000e+001
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 80 3f 	1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 80 3e 	2.50000000e-001

00 ba 86 44 	1.07781250e+003
00 c0 85 44 	1.07000000e+003
00 00 70 41 	1.50000000e+001
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 80 3f 	1.00000000e+000
00 00 00 3e 	1.25000000e-001
00 00 80 3e 	2.50000000e-001

00 ba 86 44 	1.07781250e+003
00 e0 83 44 	1.05500000e+003
00 00 70 41 	1.50000000e+001
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 80 3f 	1.00000000e+000
00 00 00 3e 	1.25000000e-001
00 00 c0 3e 	3.75000000e-001

00 da 84 44 	1.06281250e+003
00 e0 83 44 	1.05500000e+003
00 00 70 41 	1.50000000e+001
00 00 00 00 	0.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 80 3f 	1.00000000e+000
00 00 00 00 	0.00000000e+000
00 00 c0 3e 	3.75000000e-001


```
## Post #9
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-10T16:51:01+00:00
- Post Title: Help to decipher hex values in simple file

I now need help how to read/convert  correctly those sample values in DECimal:

> 00 da 84 44 = 1.06281250e+003 = ???
>
> 00 00 70 41 = 1.50000000e+001 = ???
>
> 00 00 00 80 = 0.00000000e+000 = ???
>
> 00 00 80 bf  = -1.00000000e+000 = ???
>
> 00 00 00 3f  = 5.00000000e-001 =  ???
## Post #10
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-11T13:14:42+00:00
- Post Title: Help to decipher hex values in simple file

A couple of points...

00 da 84 44 = 1.06281250e+003 = ??? =1062.81250
The scientific notation 'e+003' means move the decimal point 3 places to the right, but......
...I have trouble understanding how you've converted the hex values to decimal in the first place.
As far as I can see, 1062.8125 would have a hex equivalent of 44 84 da 00, the bytes are the same but in reverse order.

00 da 84 44, at least according to the IEEE-754 32-bit standard, should be 2.0067586e-38. This is a ridiculously small number though and can't possibly be right.

So there are 3 posssiblities:
1. These bytes aren't floats
2. They are floats but don't follow the Windows standard.
3. I'm completely wrong, in which case I apologise.
## Post #11
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-11T22:20:26+00:00
- Post Title: Help to decipher hex values in simple file

Bored, 
thank you for your kind assistance. Here is my hypothesis about those values. 

Indeed the first two may not be a floats. I need to investigate it further , however, the following values are correct to be interpreted and read as a floats. I am home grown hex editor chaser so I simply rely on the hex editing tools . I am looking at Axe HE picture of the file in question, point out the cursor on what I presume is one of the float and read the value in the "float window" on the left. To be honest I do not know for sure how many bytes contitutes this float , I think it is 4.  


Just the fact that the readings of subsequent quadruples of bytes produce for me very plausible float results like: 1.0,0.0, 15,  1.25, 0.75 , etc. I simply assume that I have found something here and automatically treat the first 2 readings in the group of 8th as floats. It may be  that  my guess is wrong and they are something else. 

I have already assigned all values to each (what I consider a float) and came with somehow interesting, results which I try to post later today.
## Post #12
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-12T00:55:22+00:00
- Post Title: Help to decipher hex values in simple file

Before I post what I have deciphered from those hexes I need to level up with you and post some more informations about the this 3D object  BoxBuilding 1. This additional info is not derrived from hex file, but text file which accompanies the model. Those very numbers below though MUST be in the hexes and that is what I am trying to nail. 

```
ObjectType001.ShapeType=0
ObjectType001.CastShadow=0
ObjectType001.SizeDeviation=0.000000
ObjectType001.Width1=15.000000
ObjectType001.Length1=15.000000
ObjectType001.Height1=15.000000
ObjectType001.TextureCoord01=0.000000,0.500000
ObjectType001.TextureCoord11=0.250000,0.750000
ObjectType001.TextureCoord02=0.250000,0.500000
ObjectType001.TextureCoord12=0.500000,0.750000
ObjectType001.TextureCoord03=0.500000,0.500000
ObjectType001.TextureCoord13=0.750000,0.750000
ObjectType001.TextureCoord04=0.250000,0.500000
ObjectType001.TextureCoord14=0.500000,0.750000
ObjectType001.TextureCoord05=0.000000,0.250000
ObjectType001.TextureCoord15=0.125000,0.375000

```


Texture cordinates are for 5 polygons: front, sidesx2, back and roof. Left upper and right lower corner. And those I see I think in my floats. 


Do I see size and loaction and angle too?
Size of the building is 15x 15x15 
Position of this box on the map sized 256x256 units is: 
X=137.000000 units
Y=136.000000 units 
Object000.Angle=0.000000
## Post #13
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-12T18:29:45+00:00
- Post Title: Help to decipher hex values in simple file

One more time Hexes, Floats and Decimal translations. 
It looks like we have here some 3D coordinates and texture coordinates. And some other numbers in 2 first rows of each group, but DEC translations do not look right here. So maybe those are not floats, but something else. 


```
00 da 84 44    1.06281250E+003   1062.8125 
00 c0 85 44    1.07000000E+003   1070.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3e    2.50000000E-001   0.2500 
00 00 40 3f    7.50000000E-001   0.7500 

Vertex 01    
00 ba 86 44     1.07781250E+003 1077.8125 
00 c0 85 44     1.07000000E+003    1070.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 80 3f     1.00000000E+000    1.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 40 3f    7.50000000E-001    0.7500 

Vertex 02      
00 ba 86 44    1.07781250E+003   1077.8125 
00 c0 85 44    1.07000000E+003  1070.0000 
00 00 70 41   1.50000000E+001   15.0000 
00 00 00 00   0.00000000E+000   0.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 3f    5.00000000E-001   0.5000 

Vertex 03      
00 da 84 44    1.06281250E+003   1062.8125 
00 c0 85 44    1.07000000E+003   1070.0000 
00 00 70 41    1.50000000E+001   15.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3e    2.50000000E-001   0.2500 
00 00 00 3f    5.00000000E-001   0.5000 

Vertex 04      
00 ba 86 44    1.07781250E+003   1077.8125 
00 c0 85 44    1.07000000E+003  1070.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 3f    5.00000000E-001   0.5000 
00 00 40 3f    7.50000000E-001   0.7500 

Vertex 05      
00 ba 86 44    1.07781250E+003   1077.8125 
00 e0 85 44    1.05500000E+003   1055.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3e    2.50000000e-001   0.2500 
00 00 40 3f   7.50000000E-001   0.7500 

Vertex 06      
00 ba 86 44    1.07781250E+003   1077.8125 
00 e0 83 44    1.05500000E+003   1055.0000 
00 00 70 41    1.50000000E+001   15.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 80 3e    2.50000000e-001   0.2500 
00 00 00 3f   5.00000000E-001   0.5000 

Vertex 07      
00 ba 86 44    1.07781250E+003   1077.8125 
00 c0 85 44    1.07000000E+003  1070.0000 
00 00 70 41    1.50000000E+001   15.0000 
00 00 80 3f    1.00000000E+000   1.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 3f    5.00000000E-001   0.5000 
00 00 00 3f   5.00000000E-001   0.5000 

Vertex 08      
00 ba 86 44    1.07781250E+003   1077.8125 
00 e0 83 44    1.05500000E+003   1055.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 80 bf    -1.00000000E+000   -1.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 40 3f    7.50000000E-001   0.7500 
00 00 40 3f    7.50000000E-001   0.7500 
    
Vertex 09  
00 da 84 44    1.06281250E+003   1062.8125 
00 e0 83 44    1.05500000E+003   1055.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 80 bf    -1.00000000E+000   -1.0000 
00 00 00 00    0.00000000E+000   0.0000 
00 00 00 3f    5.00000000E-001   0.5000 
00 00 40 3f    7.50000000E-001   0.7500 
    

Vertex 0A  
00 da 84 44    1.06281250e+003   1062.8125 
00 e0 83 44    1.05500000e+003   1055.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 80 bf    -1.00000000e+000   -1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 3f    5.00000000e-001   0.5000 
00 00 00 3f    5.00000000e-001   0.5000 

Vertex 0B      
00 ba 86 44    1.07781250e+003   1077.8125 
00 e0 83 44    1.05500000e+003   1055.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 00 80    0.00000000e+000   0.0000 
00 00 80 bf    -1.00000000e+000   -1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 40 3f    7.50000000E-001   0.7500 
00 00 00 3f    5.00000000E-001   0.5000 

Vertex 0C      
00 da 84 44    1.06281250e+003   1062.8125 
00 e0 83 44    1.05500000e+003   1055.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 bf    -1.00000000e+000   -1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 3f    5.00000000E-001   0.5000 
00 00 40 3f    7.50000000E-001   0.7500 
    
Vertex 0D  
00 da 84 44    1.06281250e+003   1062.8125 
00 c0 85 44    1.07000000e+003   1070.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 bf    -1.00000000e+000   -1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 3e    2.50000000e-001   0.2500 
00 00 40 3f    7.50000000E-001   0.7500 
    
Vertex 0E  
00 da 84 44   1.06281250e+003   1062.8125 
00 e0 83 44   1.07000000e+003   1070.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 80 bf    -1.00000000e+000   -1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 3e    2.50000000e-001   0.2500 
00 00 00 3f    5.00000000e-001   0.5000 
    
Vertex 0F  
00 da 84 44    1.06281250e+003   1062.8125 
00 e0 83 44    1.55000000e+003   1055.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 80 bf    -1.00000000e+000   -1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 3f    5.00000000e+000   0.5000 
00 00 00 3f    5.00000000e-001   0.5000 

Vertex 10      
00 da 86 44    1.06281250e+003   1062.8125 
00 c0 85 44    1.07000000e+003   1070.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 3f    1.00000000e+000   1.0000 
00 00 00 00    0.00000000e-001   0.0000 
00 00 80 3e    2.50000000e-001   0.2500 
    
Vertex 11  
00 ba 86 44    1.07781250e+003   1077.8125 
00 c0 83 44    1.07000000e+003   1070.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 3f    1.00000000e+000   1.0000 
00 00 00 3e    1.25000000e-001   0.1250 
00 00 80 3e    2.50000000e-001   0.2500 
  
Vertex 12  
00 ba 86 44    1.07781250e+003   1077.8125 
00 e0 83 44    1.05500000e+003   1055.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 3f    1.00000000e+000   1.0000 
00 00 00 3e    1.25000000e+000   0.1250 
00 00 c0 3e    3.75000000e-001   0.3750 
    
Vertex 13  
00 da 84 44    1.06281250e+003   1062.8125 
00 e0 83 44    1.05500000e+003   1055.0000 
00 00 70 41    1.50000000e+001   15.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 80 3f    1.00000000e+000   1.0000 
00 00 00 00    0.00000000e+000   0.0000 
00 00 c0 3e    3.75000000e-001   0.3750 

```
## Post #14
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-12T20:34:30+00:00
- Post Title: Help to decipher hex values in simple file

I can't say I'm sure about what you're trying to do here but it looks like your, and AXE's, interpretation of floats is the right one. I'm damned if I know why though.

Anyway, all I can see in the first two rows are the same 4 numbers:
1077.8125
1070.0000
1062.8125
1055.0000

Now 1077.8125-1062.8125 = 15 and
1070-1055 also = 15....is this significant?? I have no idea!
## Post #15
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-12T22:20:51+00:00
- Post Title: Help to decipher hex values in simple file

> Now 1077.8125-1062.8125 = 15 and 
>
> 1070-1055 also = 15....is this significant?? I have no idea!

Ahhh.... great observation, Mike. 
Possibly this has someting to do with size 15x15x15.
## Post #16
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-13T00:34:59+00:00
- Post Title: 

Getting closer: 

> This is position of the center of the box on 256x256 tile 
>
>                                        X                            Y               
>
> 256.000000	X=136.000000	Y=137.000000
>
> 
>
> 
>
> if 256x256 tile was to represent 2000mx2000m (as it does in the game) center of the box wil be :
>
>                                         X                                Y
>
> 2000.000000	X=1062.500000	Y=1070.312500
>
> and the corners:	    
>
>                                   -7.500000	-7.500000
>
>                                    7.500000	7.500000
>
> 
>
>                     	1055.000000	1062.812500
>
>                       	1070.000000	1077.812500

Those 4 numbers are quite familliar, aren't they
## Post #17
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-13T15:23:55+00:00
- Post Title: 

Good work!

Well, that seems to be all finished now. I'll get back to TAW.
## Post #18
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-14T11:58:06+00:00
- Post Title: 

> Good work! 
>
> Well, that seems to be all finished now.

Well thank you, but still some   remain.

Why we have as many as 20 records for something which is 5 polygon box shape w/o the bottom. My theory is that each polygon of that box is treated and displayed as separate entity: 5x4 =40. Do you see any other possibility?

If then each record is description of the vertexes how the texture coordinates are noted? If the above theory was correct I would need 3 coordinates for each vertex and I think I am finding only 2 . Unless....
## Post #19
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-14T22:41:27+00:00
- Post Title: 

I know that I am on the right track.   

This much I know: 20 records describe each of the vertex. Combine them into groups of 4 and you get 5 polygons.  4 walls and 1 for roof. 

In each recors first are XYZ coordinates in TILE area measuring 2000x 2000 units (m). I have build the cube based on the coordinates - ALL WORKS   Drawing to follow. 

Then something to do with .... maybe angle (I think, not sure yet ) Front wall has 4 vertexes marked 0,1,0 (looks like x=0, y=1, z=0). Back wall would have vertexes marked 0,-1,0 (looks like x=0, y=-1, z=0). 
Side walls 4 vertexes marked 1,0,0 (looks like x=1, y=0, z=0). and 
-1,0,0 (looks like x=-1, y=0, z=0). Roof 0,0,1. 
I can imagine that by proper coding you could determine how the object is oriented. I will make one test object at random angle to see what happens.   

And finally the UV texture coordinates. You do not have the texture   , but I do. So I can check and verify that all I am telling you here works and confirms nicely. 

```
This is 2nd vertex named "01"
00 ba 86 44     1.07781250E+003 1077.8125 
00 c0 85 44     1.07000000E+003    1070.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 80 3f     1.00000000E+000    1.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 00 00    0.00000000E+000    0.0000 
00 00 40 3f    7.50000000E-001    0.7500 


XYZ Coordinates of Vertex 01	
00 ba 86 44     1.07781250E+003 X= 1077.8125        
00 c0 85 44     1.07000000E+003	 Y= 1070.0000      
00 00 00 00    0.00000000E+000	 Z= 0.0000

Something to do with Center of The Object, orientation or ANGLE :!: 
X
Y
Z
00 00 00 00    0.00000000E+000	 0.0000
00 00 80 3f     1.00000000E+000	 1.0000
00 00 00 00    0.00000000E+000	 0.0000

UV Texture Coordinate corresponding to Vertex 01 
00 00 00 00    0.00000000E+000	 0.0000
00 00 40 3f    7.50000000E-001	 0.7500


```
## Post #20
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-14T23:38:03+00:00
- Post Title: 

It would certainly be interesting to see a drawing based on those coordinates....maybe then those 0,0,1 numbers might make more sense.
## Post #21
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T00:26:48+00:00
- Post Title: 

I will make the drawing shortly. At this junction of time I cannot say what are those 0,1,0 bits mean, but after some consideration they are unlikely to be conveying orientation information. For that just set of coordinates X, Y surely do nicely enough. 

0,1,-1 etc. is probable way to establish Normals. 
What else? 

You got vertex location in 3D space, then you build triangle /faces, then out of them construct polygons, polygons gets textures so the ONLY informations missing is facing of all that stuff.  Those are what normals are for. We'll hopefully see.




FRONT: 00, 01,02,03 polygones always clockwise
LEFT SIDE: 04,05,06,07
BACK: 08,09,0A,0B
RIGHT SIDE: 0C,0D,0E,0F
ROOF: 10,11,12,13

In the file there are triangles listed, check them out - they are counterclockwise:
00 02 00 01 00 00 
00 03 00 02 00 04 
00 06 00 05 00 04 
00 07 00 06 00 08 
00 0a 00 09 00 08 
00 0b 00 0a 00 0c 
00 0e 00 0d 00 0c 
00 0f 00 0e 00 10 
00 12 00 11 00 10 
00 13 00 12 00 00 

NOTE: in the previous post with floats translation to DEC there were some mistakes-they have been now corrected and post edited.

Sooo what is that 0,1,0 and etc
## Post #22
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T15:46:00+00:00
- Post Title: 

Coming to the end of this quest. I hope I did not bore you to death.   
Or so it seems.   

Anyway... I made new building box this time I postioned it at angle 30deg. Center of it is also in new location, but this I can recognise now quickly from XYZ coordinates. 
What is puzzling still is that 4th, 5th and 6th line with 0 and 1 coordinates. So I have compared both situations for two walls of the box : FRONT and REAR in both instancies. Here are results:

Box @ angle 0 deg 
FRONT
0,1,0 for the 1st vertex 00
0,1,0 for the 2nd vertex 01
0,1,0 for the 3rd vertex 02
0,1,0 for the 4tht vertex 03
the wall is pararel to x axis 

Box @ angle 0 deg 
REAR
0,-1,0 for the 9st vertex 09
0,-1,0 for the 10nd vertex 0A
0,-1,0 for the 11rd vertex 0B
0,-1,0 for the 12tht vertex 0B
the wall is pararel to x axis, but on the opposite side

Now for Box @ angle 30 deg 
FRONT
0.5,0.86602539, 0 for the 1st vertex 00
0.5,0.86602539, 0 for the 2nd vertex 01
0.5,0.86602539, 0 for the 3rd vertex 02
0.5,0.8660253, 0 for the 4tht vertex 03
the wall is not pararel to x axis but what is this meaning of 0.5,0.86602539, 0   

Box @ angle 30 deg 
REAR
-0.5,-0.86602539, 0 for the 1st vertex 09
-0.5,-0.86602539, 0 for the 2nd vertex 0A
-0.5,-0.86602539, 0 for the 3rd vertex 0B
-0.5,-0.8660253, 0 for the 4tht vertex 0C
## Post #23
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T17:40:08+00:00
- Post Title: 

> but what is this meaning of 0.5,0.86602539, 0
Well ... I cannot leave this unanswered. Of course is the angle as 0.5/0866602539= tan 30deg.
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-15T20:25:43+00:00
- Post Title: 

Are we experiencing problems with the forum??

Like when posting a new topic?
## Post #25
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-15T21:07:57+00:00
- Post Title: 

yes
## Post #26
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-15T21:08:16+00:00
- Post Title: 

yes
## Post #27
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-15T21:10:41+00:00
- Post Title: 

I pressed submit once, but the post came out twice. Now I can't delete any of them.....
## Post #28
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-15T21:12:28+00:00
- Post Title: 

.....and after submitting the last post, I got this, even the post was actually submitted:

Could not insert new word

DEBUG MODE

SQL Error : 1016 Can't open file: 'phpbb_search_wordlist.MYI'. (errno: 145)

INSERT IGNORE INTO phpbb_search_wordlist (word_text, word_common) VALUES ('came', 0), ('delete', 0), ('post', 0), ('pressed', 0), ('submit', 0), ('twice', 0)

Line : 234
File : functions_search.php
## Post #29
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T22:33:31+00:00
- Post Title: 

And finaly the last lines of the file: here I am stumped  
by two values:  
92 0a 06 3f 	0.52359879
a4 b4 29 41 	10.60660170

I am enclosing excerpts of both files box at 30deg first and then 0deg following it. That 0.52359879 has to have something to do with angle as it is present in first and absent in second. 

```
00 00 f0 40 	7.50000000
00 00 f0 40 	7.50000000
00 00 70 41 	15.00000000
92 0a 06 3f 	0.52359879
a4 b4 29 41 	10.60660170
00 ec 29 44 	679.68750000
00 ac 8a 44 	1109.37500000
00 00 00 00 	0.00000000
00 00 00 00 	0.00000000
	
[city1.bmp]	
ObjectCount=1	
Object000.TypeName=BoxBuilding1	
Object000.MapClass=0	
Object000.Chance=100	
Object000.PositionX=87.000000	
Object000.PositionY=142.000000	
Object000.Angle=30.000000	
	
*********************************************	
	
00 00 00 00 	0.00000000
00 00 f0 40 	7.50000000
00 00 f0 40 	7.50000000
00 00 70 41 	15.00000000
00 00 00 00 	0.00000000
a4 b4 29 41 	10.60660170
00 ca 85 44 	1070.31250000
00 d0 84 44 	1062.50000000
00 00 00 00 	0.00000000
00 00 00 00 	0.00000000

[desert1.bmp]	
ObjectCount=4	
Object000.TypeName=Box Building1	
Object000.MapClass=0	
Object000.Chance=100	
Object000.PositionX=137.000000	
Object000.PositionY=136.000000	
Object000.Angle=0.000000	
	

```
## Post #30
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-19T22:11:29+00:00
- Post Title: 

Chip , chip, chip ....I am still on it   
Trying to figure out any significance of those two numbers :
92 0a 06 3f 	0.52359879 
a4 b4 29 41 	10.60660170 

I 'll deal perhaps with the 1st one because I maybe have found out something: 

0.52359879 was in the file when angle was 30 deg. So I created another file with angle 135deg. The number there I found was  2.35619450 
Then I divided both numbers by respective angles in deg and the result was 0.01745329 for both. At least the changes are linear here. 

So what is peculliar about this 0.01745329? Only this, perhaps that when you multiply it by 180 deg the result is 3.14159 ... a famous number pi. So my question, please refresh my geometry and tell me something about:  n=pi/180 or n=2pi/360. Is there anything to it?
## Post #31
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-19T22:25:33+00:00
- Post Title: 

Yes indeed there is something to it: the angle is in RADIANS.
## Post #32
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-20T18:51:20+00:00
- Post Title: 

Excellent. It seems your persistence finally paid off.
## Post #33
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-20T22:27:50+00:00
- Post Title: 

Thanks Mike, 
there is still very little left, but that is of no consequence for righ now. 

The message behind this tread is this: most (if not all) hex files can be dissected on line by line basis and understood like a text in the book. It is only the factor of time, some determination and little luck ... perhaps
(in finding   things quick enough before you get frustrated and fed up).
