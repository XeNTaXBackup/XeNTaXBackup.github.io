## Post #1
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-01-29T14:18:13+00:00
- Post Title: bdae to 3ds model

I've tried to find any info about specified subject and the only cool thing I've been able to find can be seen [here](http://forum.xentax.com/viewtopic.php?f=21&t=9313&start=30). The "import script", mentioned by GMMan, works for some GTR2 models which are also .bdae format. However this script doesn't work with any model from Order & Chaos Online.

I would be happy if I could manage conversion .bdae to .3ds by myself, however I have no idea on what model data to look for in .bdae file. Any suggestions that could point me in the right direction are highly welcomed!

In the attached archive you can find 3 models:
- staff_05 is a Staff weapon, looks more like a simple stick. Includes texture.
- 2 models for male elf body. No textures.

Thanks in advance!
[xentax.zip](https://xentaxbackup.github.io/file/10384_xentax.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-30T23:19:30+00:00
- Post Title: bdae to 3ds model

The static meshes (FVFsize= 32) seem to be simple (though I found the staff to have a strange plane attached):



staff.JPG (39.67 KiB) Viewed 307 times



For the elf (elf_m_h.bdae) use a FVFsize of 60.
H2O file:
0x2E02C 423
Vb1
60 24
0x2C8BA 100
020000
0x0 255

Where the uv pos (24) is unsure (uvs are just a square).
(hex2obj pproduces an obj file, which won't help you Iguess.)
## Post #3
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-01-31T12:14:15+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> The static meshes (FVFsize= 32) seem to be simple (though I found the staff to have a strange plane attached):
...
Where the uv pos (24) is unsure (uvs are just a square).
Sorry for my pretty newbish question, but what does UV and FVFsize abbs stand for?

> Reply from shakotay2
>
> (hex2obj pproduces an obj file, which won't help you Iguess.)
My goal is to display models on a website using three.js. It supports .OBJ files so it seems like one of the possible ways i need
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-31T13:01:34+00:00
- Post Title: bdae to 3ds model

Google for UV mapping.
FVF is flexible vertex format. Its size is the offset from one vertex to the next one.

The parameter FVFsize helps to display the mesh. uv position (offset in FVF block) helps to display the uv map.
## Post #5
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-01-31T19:21:22+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> staff.JPG
After a day of messing up with three.js and creating my very first simple model (manually adding vertices and faces) with the help of [this](https://github.com/mrdoob/three.js/wiki/JSON-Model-format-3) doc, I think I am on the right way! So, as far as I understand, the .bdae model nested inside parent .bdae (which is actually a ZIP) contains vertices, faces and uvs for every face (sorry if terminology is used in wrong way). I noticed that FVFsize is 32 due to repeated "?" every 32 bytes in the middle of .bdae. So.. this 32 bytes contain all the nesessary information? By "all" I mean.. tbh I am not completly sure. My idea is that it might contain data like 3 vertices of triangle, a triangle sequence, maybe UV map and smth else... But this data starts at 0x8df and what are prior bytes for? It also leaves almost 700 bytes in the file end... Meh, could you please point whether I am in the right directions or not? Or explain what info to look within 32 FVFsize bytes . Grrr
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-31T21:20:00+00:00
- Post Title: bdae to 3ds model

> Reply from lolbas
>
> ... But this data starts at 0x8df and what are prior bytes for?some strings, texture/material names, nodes - whatever, who knows
> It also leaves almost 700 bytes in the file end...Mostly face indices; the very last bytes look like a version.nfo file (if you decompress the bdae, which is not required)

> Meh, could you please point whether I am in the right directions or not?more or less, there are three floats (pos x,y,z) for the vertices and two floats for the uv coords (tx, ty), marked blue. (Maybe the remaining 12 bytes build a normal, didn't check it.)

I also marked the first two faces, which consist of 3 face indices each (where you have to add 1 to get the correct values for wavefront obj):



static_bdae.JPG (75.63 KiB) Viewed 291 times


v -0.102100 -0.033354 -0.000709 
vt 0.511508 0.932062 
...

f 1/1 2/2 3/3 
f 3/3 4/4 1/1 
...

btw: the H2O file in my first post was intended to be used with hex2obj (view link in my sig)
## Post #7
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-01T06:08:29+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> ... the very last bytes look like a version.nfo fileVersion data (the one contained in version.nfo within parent bdae) starts at 0x19c

> Reply from shakotay2
>
> (if you decompress the bdae, which is not required)I don't get why! If I want to manually find out what does every byte means, shouldn't I first extract the model file itself?

> Reply from shakotay2
>
>  there are three floats (pos x,y,z) for the vertices and two floats for the uv coords (tx, ty), marked blue.This starts to make sense for me!

> Reply from shakotay2
>
> (Maybe the remaining 12 bytes build a normal, didn't check it.)I tried playing around normals in three.js but I seem to not understand the purpose of it. If I have 3 vertices and connected them into triangle face, what would applied normal do?

> Reply from shakotay2
>
> 
v -0.102100 -0.033354 -0.000709 
vt 0.511508 0.932062 
...

f 1/1 2/2 3/3 
f 3/3 4/4 1/1 
...And this makes not much sense right now... v stands for vertex, vt stand for ???, I also recall some blog mentioned vz or vy... F stands for face, but the following "1/1" etc give no idea what are they @-@

> btw: the H2O file in my first post was intended to be used with hex2obj (view link in my sig)
Thought so. I downloaded this tool, yet I didn't get to try it out
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-01T09:44:38+00:00
- Post Title: bdae to 3ds model

> Reply from lolbas
>
> shakotay2 wrote:(if you decompress the bdae, which is not required)I don't get why! If I want to manually find out what does every byte means, shouldn't I first extract the model file itself?This bdae is a zipped file without compression (at least the contained model doesn't seem to be compressed).

> I tried playing around normals in three.js but I seem to not understand the purpose of it. If I have 3 vertices and connected them into triangle face, what would applied normal do?"The normal is used by a shader when it's calculating the lighting."
(Most 3D applications are capable of recalculating normals from a given mesh - that's the reason why I didn't care for normals in hex2obj.)

You seem to understand/learn fast  but we're going to hurry from one question to the other (next would be "what is a shader?", wouldn't it? ).

So you might google for normal mapping, wavefront object, 3D modeling to get more basic understanding.

> And this makes not much sense right now... v stands for vertex, vt stand for ???, I also recall some blog mentioned vz or vy... F stands for face, but the following "1/1" etc give no idea what are they @-@'vt' denotes the texture coordinates. vx, vy, vz are the components of a vertex v in 3D space.
f 1/1/1 2/2/2 3/3/3 is an abbreviation for three faces:
mesh face: v0,v1,v2
normal face: vn0,vn1,vn2
texture face: vt0,vt1,vt2
Since hex2obj ignores normals we've f 1/1 2/2 3/3 here.

(That's very simplified, though, but that's the way I explained it to myself.  )
You could build a mesh of normals which would display as a sphere.
You can test this very easily in hex2obj by replacing the vertex start address by address +0x0C
(provided that the FVF looks kinda this: 3 floats vx,vy,vz, 3 floats vnx,vny,vnz, ...
 so it doesn't work with the bdae files here.)


(For some practical exercise you could replace the first ten face lines in a wavefront obj file by 
f 1/1/1 1/1/1 1/1/1 each then load the model to look how it's affected by this.)
## Post #9
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-01T13:19:58+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> This bdae is a zipped file without compression (at least the contained model doesn't seem to be compressed)I totally forgot about non-compressing methods.

> Reply from shakotay2
>
> next would be "what is a shader?"Just a quick google search to make sure I knew it already!

> Reply from shakotay2
>
> 'vt' denotes the texture coordinates. vx, vy, vz are the components of a vertex v in 3D space.Why does vt requires 2 coord values: (I assume) x and y?

Well, I have a question I couldn't resolve by myself. Working with three.js to create a triangle we create 3 vertices, say A = (0,0,0), B = (0,0,1) and C = (1,0,1) and then a face data is supplied like: [0, A,B,C], where first 0 stands for "triangle" (1 for "quad"), and then our vertices. This will create a triangle visible from one side (oh, btw, how do I determine this? I seem to not understand how does order of connection affects figure visibility). But I don't see anything similar to this in FVF data!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-01T14:24:37+00:00
- Post Title: bdae to 3ds model

> Reply from lolbas
>
> Why does vt requires 2 coord values: (I assume) x and y?yep - it's a 2-dimensional (texture) map

> This will create a triangle visible from one side (oh, btw, how do I determine this? I seem to not understand how does order of connection affects figure visibility).It's a matter of winding: you can define the order of the vertices clockwise or counter-clockwise. For example f 1 2 3 versa f 1 3 2.
Then it's a matter of your 3D app whether to draw or not to draw a face onto the screen.
## Post #11
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-01T20:36:29+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> I also marked the first two faces, which consist of 3 face indices each (where you have to add 1 to get the correct values for wavefront obj):
static_bdae.JPG
How did hex2obj programmatically finds the first face? I tried to find some logic within first bytes but finished with no luck...
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-01T20:44:03+00:00
- Post Title: bdae to 3ds model

> Reply from lolbas
>
> How did hex2obj programmatically finds the first face?it does not - you may search for 000001000200 in a hex editor. Works in most cases; sometimes there a multiple finds in case the model has more than one submesh.
## Post #13
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-03T20:57:14+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> lolbas wrote:How did hex2obj programmatically finds the first face?it does not - you may search for 000001000200 in a hex editor. Works in most cases; sometimes there a multiple finds in case the model has more than one submesh.
Does hex2obj allows you to determine amount of vertices, faces and uvs? I am trying to find this data within .bdae file, the file contains odd 8-byte values starting at 0x50 and their amount varies from model to model, I have no idea what they might be, aside from my understanding that they are pointers to some specific data sections (actually, usually they point to 5-10 consequent 8-byte values stored in different parts of file).

Also, your first reply contains info about first FVF data. However bdae header has the closest pointer 40 bytes before it (5x 8-byte values), do you happen to know what they might be?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-03T22:25:49+00:00
- Post Title: bdae to 3ds model

> Reply from lolbas
>
> Does hex2obj allows you to determine amount of vertices, faces and uvs?amout of vertices is (in most cases) equal to max face index which is provided by hex2obj provided that you give it the correct face index count (understand that there might be 336 face indices with a max face index of 197 only).

uv count is equal to vertex count in most cases, so you'll need to find the face index count, the 336 above.

Using the 'table' button might reveal helpful infos (or not):

```
address 0x59a:
  197    40     1   152 be09a49c bfae2196 be09a49c 3e09a49c 
3f069b7c 3e09a49c     0    32     3    48     3    56 
    3    64     3    72     0  2240     0     0 
    0     0    12    24     0     6     6     6 
    0     3     3     2     0     0     0     0 
    0     0     0   428     0   112 ffff0100 ffffff02 
ffffffff ffffffff 65535     0   196   336     0  8552 

```
(197 vertices, 336 face indices)

> Also, your first reply contains info about first FVF data. However bdae header has the closest pointer 40 bytes before it (5x 8-byte values), do you happen to know what they might be?It would be helpful if you provided a picture from the values you're talking of.
But guess I can't tell it.

The way it goes (for me) is this: you find a data your sure of, for example the vertex count.
Then you search for the address value pointing to it. Sometimes these addresses are absolute offsets, in some cases they're relative.

This approach fails if the data is part of a table where you'll have to find the starting point of the table then.
## Post #15
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-04T10:21:47+00:00
- Post Title: bdae to 3ds model

> Reply from shakotay2
>
> Also, your first reply contains info about first FVF data. However bdae header has the closest pointer 40 bytes before it (5x 8-byte values), do you happen to know what they might be?It would be helpful if you provided a picture from the values you're talking of.
Here they are. The header field points to the start of selection. The first bytes after selection have been recognized by you as start of FVF data.

[](http://postimg.org/image/gn6jflvw3/)

> Reply from shakotay2
>
> (197 vertices, 336 face indices)
FVF data is 6304 byte long (length does not specified by header info) and thats 197x32 byte (considering FVFsize = 32), just like you said. But I dont understand how could you say for sure that this value at this offset means amount of vertices! And also, why exactly this offset?
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-04T10:52:40+00:00
- Post Title: Re: bdae to 3ds model

> Reply from lolbas
>
> Here they are. The header field points to the start of selection. The first bytes after selection have been recognized by you as start of FVF data.Thx. Sadly I don't know their meaning.

btw: you used the unzipped data which is the correct way, I guess
My previous infos refer all to the zipped bdae, so does the H2O file.

> But I dont understand how could you say for sure that this value at this offset means amount of vertices! And also, why exactly this offset?I can't say it for sure. But 0xC5 (C5 000000) and 0x150 (50010000) appear only once in that bdae so there was a really good chance that they were the counts.
This has to be proven by another (static) model sample, of course.

For the char model elf_m_h.bdae there's no occurence of A701000 (FI count: 423 dec.) so forget about what I said. 

Once in 10 years maybe you'll realize, too that this analyzing stuff is a big waste of life and time, I guess.
That's the reason why I created hex2obj which allows to get the first submesh within 15 min in most cases
(with some experience).
## Post #17
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-04T13:09:01+00:00
- Post Title: Re: bdae to 3ds model

> Reply from shakotay2
>
> 
For the elf (elf_m_h.bdae) use a FVFsize of 60.
H2O file:
0x2E02C 423
Vb1
60 24
0x2C8BA 100
020000
0x0 255
Do you mind posting h2o file for staff_05? The elf one only shows panties
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-04T13:50:55+00:00
- Post Title: Re: bdae to 3ds model

0x21AA 336
Vb1
32 20
0x906 197
020000
0x0 255

to be used with the (compressed) staff bdae.

(Don't ask me for this weird plane attaced!  )
## Post #19
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-04T15:32:05+00:00
- Post Title: Re: bdae to 3ds model

> Reply from shakotay2
>
> 0x21AA 336
Vb1
32 20
0x906 197
020000
0x0 255
I dont understand few things. In the compressed file, 197 FVFs end at 0x21A6, but you say that face indices start at 0x21AA. That's 4 byte wiped out. Why? You also ignore the very last two bytes yet they are 0x00. There is no reason to put them by model specification, can't they be another face that will solve the plane issue? And yes, I understand that that is only 2 out of 3 required values to make up a face

> Reply from shakotay2
>
> (Don't ask me for this weird plane attaced!  )
My understanding is that it's just non-optimized width of model, probably some wrong faces...
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-04T16:09:31+00:00
- Post Title: Re: bdae to 3ds model

> Reply from lolbas
>
> That's 4 byte wiped out. Why?These 01 00 00 00 might be some kind of marker.
It's experience that tells me the face indices must start at 0x21AA (00 00 01 00 02 00).

> You also ignore the very last two bytes yet they are 0x00.yes, I always reduce it to the min.  

> There is no reason to put them by model specification, can't they be another face that will solve the plane issue?Do you have a full format specification for this bdae file?
I don't have. I just give people a start and don't bother with details.
This may lead to severe misses, of course. I'm aware of that.
(But it's just a relaxing hobby of mine - I don't need to earn my money with it, luckily.  )

Nope, I don't think these two zero bytes will solve the plane issue.
I've divided the mesh up into 5 submeshes by inserting group separators (g submesh_x) all 50 face lines
to see whether the sms might be part of a collision mesh or something like that:



staff_5_submeshes.JPG (40.58 KiB) Viewed 304 times


But normally the CS (collision shape) is in a separate file.
## Post #21
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-04T22:39:22+00:00
- Post Title: Re: bdae to 3ds model

> Reply from shakotay2
>
> This bdae is a zipped file without compression (at least the contained model doesn't seem to be compressed).
Yeah its not compressed but with 7-zip you can extract it down one time to where the header begins with bres and looks very much like the one described here
[http://wiki.tockdom.com/wiki/BRRES_(File_Format)](http://wiki.tockdom.com/wiki/BRRES_%28File_Format%29)

edit
fixed the link
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-04T23:33:35+00:00
- Post Title: Re: bdae to 3ds model

Thx - I changed the signature to lowercase but BRRES Viewer v1.3.1, 3 Jan 2011
By Kentilan doesn't recognize it (maybe a matter of endianess?).

There's a brres-splitter, but it doesn't produce an output because a signature like 'MDL0' is missing in the staff05.brres.
Even worse, there's no strings at file's end.
## Post #23
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-02-05T13:18:12+00:00
- Post Title: Re: bdae to 3ds model

> Reply from AceWell
>
> Yeah its not compressed but with 7-zip you can extract it down one time to where the header begins with bres and looks very much like the one described here
http://wiki.tockdom.com/wiki/BRRES_(File_Format)
> Reply from shakotay2
>
> ...BRRES Viewer v1.3.1, 3 Jan 2011 By Kentilan doesn't recognize it (maybe a matter of endianess?).
I assume the BRRES file format has been taken as starting point. Specification described in link and the one I've been able to partly hack within last 3 days differes a lot, starting right after BOM Padding.

Here is my table. Comparing to the one from link will reveal the difference:

```
    'bom'               => '',      # 0x0004    # Byte Order Mark. 0xFE 0xFF for Big Endian #
    'bom_padding'       => 0,       # 0x0006    # BOM padding. 0x0000 #
    'header_size'       => 0,       # 0x0008    # ? 0x50 - might be a header size
    'BDAE_size'         => 0,       # 0x000C    # size of model data
    'data_1_count'      => 0,       # 0x0010    # amount of 8 byte values from offset available at 0x18
    'data_1_offset'     => 0,       # 0x0018    # ? 0x50 - might be a pointer to other kind of data
    'string_start'      => 0,       # 0x0020    # offset to strings (string map: 4 bytes for string length; unknown logic for taking additional zero-value bytes (mod 4), seem to have at least 1 zero-value byte
    'string_end'        => 0,       # 0x0028    # 'string_section' end, start of 'unknown_section_1'
    'unknown_section_2' => 0,       # 0x0030    # 'unknown_section_1' end, start of 'unknown_section_2'
    'unknown_section_3' => 0,       # 0x0038    # 'unknown_section_2' end, start of 'unknown_section_3'; most likely section of model vertices, faces and uvs; with extra 5x 8 bytes values
    'unknown_data_1'    => 0,       # 0x0040    # might be an offset to 'section 4', but doesn't really seem to be so; might be an amount of vertices or polynoms
    'unknown_value_1'   => 0,       # 0x0044    # might be amount of FVF + face indeces blocks (2 for single-object model)
    'unknown_value_2'   => 0,       # 0x0048    # ? 0x0 - check other models
    'unknown_value_3'   => 0,       # 0x004C    # ? 0x0 - check other models
    # possible header end #

```
## Post #24
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-03-05T19:27:15+00:00
- Post Title: Re: bdae to 3ds model

Yay! I've been able to convert .bdae models' objects to one I need to use and it all looks cool with all that shapes and textures but... I failed with normals. The models in game look all that smooth but the one I get are pretty rough. Due to some factors, I assume that every vertex has its normal, but how does this normal builds? I mean, what values does it use?

> Reply from shakotay2
>
>  there are three floats (pos x,y,z) for the vertices and two floats for the uv coords (tx, ty), marked blue. (Maybe the remaining 12 bytes build a normal, didn't check it.)

According to what I've done, a vertex block (size = 32b) consists of:

```
| offset |  content |
+--------+----------+
|   0x00 | vertex x |
+--------+----------+
|   0x04 | vertex y |
+--------+----------+
|   0x08 | vertex z |
+--------+----------+
|   0x0C |  no idea |
+--------+----------+
|   0x10 |  no idea |
+--------+----------+
|   0x14 |  no idea |
+--------+----------+
|   0x18 |     uv x |
+--------+----------+
|   0x1C |     uv y |
+--------+----------+
...

```


Do those 3x "no idea" build a vertex normal (I am not sure, because these values can be negative)? If so, what do they mean?

By the way, some models have vertex block size = 56 bytes, thats 6 extra values, what can they be?
## Post #25
- Username: z3ntu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 06, 2016 10:34 pm
- Post datetime: 2016-06-07T08:11:56+00:00
- Post Title: Re: bdae to 3ds model

Hello,
sorry for poking in this old-ish thread, but I currently want to get textures/models/etc out of the game of files of the Game "Gangstar: Miami Vindication" which was available for Android and is still available for iOS.
The game files mostly contain .bdae files and .tga files (also .bmp, .gmap, .pycst, .pyarray, .array, .bin, .ogg (which are actually playable), and some more). The .bdae files are normal zip files (as mentioned in this forum), which contain the files:
dependancies.txt (yes, it is really wrongly spelled)
little_endian_quantized.bdae
version.nfo

I have looked at the actual (not zip) .bdae file in a bit more detail and as also already mentioned it has a very similar header to the Nintendo BRRES format, although not the same. I have documented my findings until now here: [https://gist.github.com/z3ntu/93d05b38d ... 2d0ae214a6](https://gist.github.com/z3ntu/93d05b38d9ba10811c3f1f2d0ae214a6)

I will attach one .tga file and one .bdae (zip) file so maybe you can find out more, as I have little to no experience in this area.

Cheers.
[xentax.zip](https://xentaxbackup.github.io/file/11029_xentax.zip)
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-14T22:24:31+00:00
- Post Title: Re: bdae to 3ds model

while you can extract the bdae file down to 3 files you gain nothing because the data is already uncompressed
but you should extract it anyway so the offsets in the model file make sense.
this is the first submesh of little_endian_quantized.bdae from your car_delivery.bdae sample 


find byte pattern 30 2C 30 2C 30 2C (0x9E8)
go back 8 bytes and read address
jump to that address which is where the model name offset is
go back 12 bytes to get number of submeshes

the table before the first submesh
0x9840 - number of submeshes counting from zero
0c984C - offset to model name
0x9850 - length of first vertex block
0x9854 - offset to first vertex block
0x9858 - length of first face indices data (divide by 2 to get num faces)
0x985C - offset to first face indices
0x9860 - length of second vertex block
0x9864 - offset to second vertex block
0x9868 - length of second face indices data (divide by 2 to get num faces)
0x986C - offset to second face indices
etc

vertex strides for each submesh in order from 0-6
0x37C0 - 32 
0x3878 - 36
0x3940 - 36
0x3A08 - 32
0x3AC0 - 32
0x3B78 - 32
0x3C30 - 32


the structure of this file looks a little like the bre model files here
[viewtopic.php?f=16&t=14455](http://forum.xentax.com/viewtopic.php?f=16&t=14455)
## Post #27
- Username: z3ntu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 06, 2016 10:34 pm
- Post datetime: 2016-06-15T16:12:38+00:00
- Post Title: Re: bdae to 3ds model

Many, many thanks for finding that out    

Thanks to this wonderful forum full of extremely nice people   I now have this model in the unity engine: 

(everything parsed with BinaryReader, etc in a C# script).
Now I just have to find out, how to get some data out of the .tga (probably) files that I get textures for everything.  
Apparently these are all the textures from a car in the game...

```
-rw-r--r-- 1 luca luca  43716 Jun 25  2011 car_body_reflection.tga
-rw-r--r-- 1 luca luca  43716 Jun 25  2011 car_body_reflection_night.tga
-rw-r--r-- 1 luca luca 174788 Jun 25  2011 car_cops_texture_d.tga
-rw-r--r-- 1 luca luca 174788 Jun 25  2011 car_cops_texture_damage_d.tga
-rw-r--r-- 1 luca luca  87420 Jun 25  2011 car_interior_d.tga
-rw-r--r-- 1 luca luca  16436 Jun 25  2011 car_interior_d_lo.tga
-rw-r--r-- 1 luca luca 699076 Jun 25  2011 car_poor_texture_d.tga
-rw-r--r-- 1 luca luca 262196 Jun 25  2011 car_poor_texture_d_lo.tga
-rw-r--r-- 1 luca luca 699076 Jun 25  2011 car_poor_texture_damage_d.tga
-rw-r--r-- 1 luca luca 262196 Jun 25  2011 car_poor_texture_damage_d_lo.tga
-rw-r--r-- 1 luca luca 699076 Jun 25  2011 car_texture_d.tga
-rw-r--r-- 1 luca luca 262196 Jun 25  2011 car_texture_d_lo.tga
-rw-r--r-- 1 luca luca 699076 Jun 25  2011 car_texture_damage_d.tga
-rw-r--r-- 1 luca luca 262196 Jun 25  2011 car_texture_damage_d_lo.tga
```

The other .tga files are just textures for other objects or atlas*, alpha* or night* (like night59.tga, etc) files...
Link to the "car_texture_d.tga" and a "DefaultEffects.bdae" file is here: [http://www.mediafire.com/download/ylpe6 ... ntax_2.zip](http://www.mediafire.com/download/ylpe69513ekd3bm/xentax_2.zip) (can't attach here because it's too big)
