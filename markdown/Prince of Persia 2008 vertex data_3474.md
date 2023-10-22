## Post #1
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2009-05-12T03:34:29+00:00
- Post Title: Prince of Persia 2008 vertex data

Been staring myself blind on this one for far too long. 
I've figured out a few of the other formats (getting somewhere with the character meshes was actually easier), but I can't put my finger on this 28 byte vertex format used for static stuff.
Following the standard "first 12 bytes are 4 32bit floats for x/y/z" the others use gives me way too many NANs to be right.
(The last 8 bytes are probably uvs like for the others tho)

It's probably blindingly obvious, but can someone else take a look at it and shine the light of understanding for me because it's driving me crazy 

Anyway, attached 2 example files.

JCT4_OB1_FAKE.415D9568
vertexdata start offset 106 (528 vertices, 14784 bytes)
triangle data start offset 14890 (667 triangles, 4002 bytes)

OB_OBJ_Lamp_04.415D9568
first object
vertexdata start offset 107 (567 vertices, 15876 bytes)
triangle data start offset 16711 (538 triangles, 3348 bytes)
[testfiles.rar](https://xentaxbackup.github.io/file/2028_testfiles.rar)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-05-12T12:33:59+00:00
- Post Title: Prince of Persia 2008 vertex data

Just have a quick look on those files!
The verts position are NOT in float format!
They should be a 16bits signed integer * scale factor
So the first 6 bytes are 3 16bits signed integer XYZ

And the last 8 bytes are definate 2 float UV value.

Right before the UV should be 4 unsigned 8bits color value, which should be Vertex Color!

A interesting value on offset 7-8(the forth 16bits signed integer) are always 3/-3 !?


Hope this help!
## Post #3
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2009-05-12T23:01:10+00:00
- Post Title: Prince of Persia 2008 vertex data

Doh, thanks.
I'd tried with float16s, but they weren't fractional, so I'd abandoned and moved on. -_-
(really weird storage method btw, if the 4th 16 bit value is positive, you need to change the sign of the xyz values)
