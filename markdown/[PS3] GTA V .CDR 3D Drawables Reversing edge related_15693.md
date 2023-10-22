## Post #1
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-07T04:15:28+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

Hello people, a lot of work have been done about drawables of RAGE engine on pc and even on x360, for example on x360 there is this xdr2obj [https://github.com/tgascoigne/xdr2obj](https://github.com/tgascoigne/xdr2obj) but nothing for the ps3 version because there is a different approach to store index and vertex data.

There is a documentation even from that xdr2obj git "xdr.org" with many common things with the ".wdr" doc here: [http://gta.wikia.com/wiki/WDR](http://gta.wikia.com/wiki/WDR) and our .cdr from PS3 is really close but just at some header fields later when starts the ps edge compression approach the things becomes different!.

I started looking around console format's some time ago had done a simple app to decompress RSC resource archive but now i'm working on reversing the 3d data from RAGE engine on GTA V but PS3 version. There are .cdr,cft and cdd formats right now i'm focus on .cdr drawables there are a lot of wiki's and info about the x360 one .xdr and obviusly for pc .wdr (gta iv) the thing is totally different on ps3 -x360, i mean on old gen consoles the format have more things in common with the old .WDR from GTA IV even there was that xdr2obj for x360 because the .xdr(xbox360) and .wdr old gta iv pc are really the same as i see when searching with hxd BUT the thing for PS3 is really different!, have some days and at least with the .cdr i managed to get vertex extracted (i believe they are) (format of vertex is the most common v(x,y,z) etc) and have done reverse engineering of many offsets in the file i'm writing a doc about my findings.

Offsets documented:




The section 0x1D10 that i use is from asteroid .cdr but every .CDR have one section like that maybe is some kind of vertex buffer because have important information for the model.

Here are some .cdr files maybe any other dev with experience can help me. About the .cdr they were decompressed from zlib rockstar it uses RSC format with my experimental program written on java i managed to get it unpacked on ps3 version they just use zlib on x360 they use lzx. because that there is no RSC header on the files.

[https://drive.google.com/open?id=0B7ouK ... jItV2R5SjQ](https://drive.google.com/open?id=0B7ouKHXOy2KdRWkwZjItV2R5SjQ)
That is a image of what i have done in the few time. is an asteroid model with only points.

And this is .zip with .cdr and images with some analysis patterns even i have extracted some blocks that are on the file with hxd. They are three blocks i think i got vertex data from the one named "asteroid_18800-0x2D60-block" being 18800 the offset on that block in the file and 0x2D60 his length and when i check 0x2D60/10 it gives me 0x2D6 that is actually the verts count so maybe i'm not so wrong. the other two i don't know anything must be skeleton or shaders related.

[https://drive.google.com/open?id=0B7ouK ... zBGamJHSWM](https://drive.google.com/open?id=0B7ouKHXOy2KdZEVUVzBGamJHSWM)

That file contains an asteroid model just like this one:



I made some more research but now i know more about this format. Rockstar use Playstation Edge in order to optimize vertex cache and indexes to better load on spus of cell cpu just like this doc says:

[http://www.jonolick.com/uploads/7/9/2/1 ... _final.pdf](http://www.jonolick.com/uploads/7/9/2/1/7921194/gdc_edge_07_final.pdf)

Sony PS Edge vertex and index format is used in many games from GOW 3, Playstation all stars, etc. In any heavy game with lot of 3d stuff it should be used.

Here in this forums i started to see some topics about ps edge compression and see the work of chrrox (thanks to him for his scripts).

There is a function on noesis include's "rapi.decompressEdgeIndices(edgeData, indexCount)" that does all the magic obviusly when you know on the file where is located the index offset, vertex count, index count, index size, etc. I managed today to get that more documented in a doc file there is it: 
[https://drive.google.com/file/d/0B7ouKH ... sp=sharing](https://drive.google.com/file/d/0B7ouKHXOy2KdRnkyZDUxZnZrSTg/view?usp=sharing)

For faster results i just use the asteroid.cdr file so in the doc are some fixed offsets and values for this file only but should work many of that fields with even all .cdr that i look around. Well this doc like i say is usefull when you have the asteroid cdr.

[viewtopic.php?f=18&t=11954](http://forum.xentax.com/viewtopic.php?f=18&t=11954) Here is the link to noesis-plugin that chrrox write for ps all stars and i use that src to check if there is that kind of format and YES i get somethings in common between ps all stars and maybe every edge related format with our .CDR from RAGE GTA V on ps3 and that is what i had wrote on the document.

Here is another picture too with colors of that block (asteroid.cdr:0x1D10 fixed offset) that i quote in the previous document:

[https://drive.google.com/file/d/0B7ouKH ... sp=sharing](https://drive.google.com/file/d/0B7ouKHXOy2KdSVF1TFZ4aE1MOEU/view?usp=sharing)

Hurray! I managed to get decompressed the index data! using that offsets in the doc and as the picture says and using the python plugin with noesis func "rapi.decompressEdgeIndices" but that is just faces and triangles and this time is Ok the data from what i see.

bs.seek(indexOffset, NOESEEK_ABS)
edgeData = bs.readBytes(indexSize)
edgeDecomp = rapi.decompressEdgeIndices(edgeData, indexCount)
(this is from chrrox plugin to ps all stars)

I get this file:
[https://drive.google.com/file/d/0B7ouKH ... sp=sharing](https://drive.google.com/file/d/0B7ouKHXOy2KdQ25qVng1bmVTT0U/view?usp=sharing)

here is a picture of how it looks index data now that is decompressed (v1,v2,v3) short values:
[https://drive.google.com/file/d/0B7ouKH ... sp=sharing](https://drive.google.com/file/d/0B7ouKHXOy2KdZ2VUTlpSMC1QdjQ/view?usp=sharing)

Later i make a simple java app to convert every short to integer values of two bytes as the index data should normally be ( for example: f 1 2 3, f 3 2 0, etc) and get :

[http://pastebin.com/csQjWwd4](http://pastebin.com/csQjWwd4)

Looks according to index information that there are 724 verts in our asteroid cdr sample at least and in the offset that i believe it is vert count says that there are 726 or 0x2D6 so maybe we are more close to the goal 

Here is the "experimental" python (noesis compatible based on chrrox ps all stars, again thanks to him for marvelous work!) this is a modified script to work with (asteroid.cdr but can work with other .cdr with only one geometry i think and changing the value 0x3000 to where graphics section of resource starts according to .RSC format) BUT IT works just to decompress edges at this time don't try to export .obj or anything this script is just to fwrite decompressed faces to another file. The python script doesn have some offsets rights.

[http://pastebin.com/7EEiw3LA](http://pastebin.com/7EEiw3LA)

Again this python script for noesis is just to use this:

```
edgeDecomp = rapi.decompressEdgeIndices(edgeData, indexCount)
```


Until that step the python script works ok but as i'm just in the step of make documentation i'm just using hex editor, building quickly with java, python and anything that can help me in the process of reversing.

Here are some more .cdr files if anyone want to look on this.
[https://drive.google.com/file/d/0B7ouKH ... sp=sharing](https://drive.google.com/file/d/0B7ouKHXOy2KdanB0Ukd1SXVnc0k/view?usp=sharing)

Now need more work with kind of file, it should be great if we can do something with the format because i think that even Red dead redemption work in this way and maybe in the far future we can mod console versions. I need help from more experienced devs with this 3d reversing stuff i'm a programmer but i'm new in these stuff. Again thanks to everyone!. sorry for my bad english.
## Post #2
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-07T15:26:03+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

Good news i think i managed to get vertex values (x,y,z,w?) floats extracted from the block that i "BELIEVE" that have vertex positions, as i say on the post is the block located always maybe all .cdr from what i see on (0x15800+CPU SECTION LENGTH) in the case of asteroid cdr it was 0x3000 so it becomes 0x18800 and according to the possibly "vert count" 0x2D6 after doing (vert count * 0x10) by the vertex stride (4b floats) i get the length 0x2D60 of that block. well there is it on .obj but only vertex.

[http://pastebin.com/nCcH7rAU](http://pastebin.com/nCcH7rAU) vertex 

and the thing is that i get some errors because there are some "NAN" not a number values on some vertex,   

Again as the first post says i already get decompressed face indexed list here is the sample from asteroid too:

[http://pastebin.com/csQjWwd4](http://pastebin.com/csQjWwd4)

The index list says that there should be 724 verts and the vertex data stuff says that too but when i get this two vertex and faces on only one sample .OBJ i get errors. Need more help with this i think
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-07T16:51:48+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from psxmodder
>
> http://pastebin.com/csQjWwd4

The index list says that there should be 724 verts and the vertex data stuff says that too but when i get this two vertex and faces on only one sample .OBJ i get errors. Need more help with this i think

> f 0/0 1/1 2/2
wavefront obj face indices are 1-based. Add 1 to each face index.


btw: very interesting that you deal with edge decompression!  
But you're producing walls of text; sadly I don't have the time to go through it.
## Post #4
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-07T17:09:48+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from shakotay2
>
> 
f 0/0 1/1 2/2
wavefront obj face indices are 1-based. Add 1 to each face index.

btw: very interesting that you deal with edge compression!  
But you're producing walls of text; sadly I don't have the time to go through it.

Yeah i wrote a lot of text i will try to make it shorter, Thanks for that gonna add +1 to each index and i have seen some of your works (codes) too thank you for everything you have done.

Yeah i had spend a few days until i figured out that is using edge compression, i'm starting to use asteroid sample because it just have one geometry from what i see on hxD but i been doing some more research and now today finger out how to work with many geometries or mdls in one file. 

We should do some kind of topic about edge compression in his many ways because i see that many games uses it but they change the offsets and the way they likely mix the pc format with the sony edge compression method from what i see.

Edit: Well now Blender open it but is showing this weird geo:



And in the center is where are a lots of vertex and faces even when i come to wire view i see how there is really the asteroid form (yeah maybe i'm crazy xD) but there is bug that make faces goes beyond every limit and make a ugly form like in the picture well need to finger out what is happening.

I think that i need to do something to the vertex before just take 0x10 bytes and convert to IEEE floats maybe there is something more with the positions of they, or maybe is java converter that is not taking the numbers well, here is the vertex data it is in (4b floats (x,y,z,w)) maybe you can see if i'm not doing a good intbitstofloat convertion.

[https://drive.google.com/file/d/0B7ouKH ... sp=sharing](https://drive.google.com/file/d/0B7ouKHXOy2KdcFpnbkFjZWpNSU0/view?usp=sharing)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-07T18:34:11+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

this all is a little bit confusing to me (maybe you should give your thoughts more structure?  )

First of all I don't think that it's floats in your asteroid_18800-0x2D60-vertex.block

```

000000   5D 4C 7D C0 2C 53 30 03  11 FF 74 FF CF 80 7F FF
```

2ndly when I use your python script on prop_asteroid_01.cdr.out (where I cut off the .out since you claimed it to be a .cdr (!?) in your opening post) I get these face indices:
...
f  164/164/164 163/163/163 160/160/160
f  165/165/165 163/163/163 164/164/164
f  166/166/166 165/165/165 164/164/164

which are far from 724

Also (0x1B560 - 0x18800) / 16 = 726
## Post #6
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-07T20:26:20+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from shakotay2
>
> this all is a little bit confusing to me (maybe you should give your thoughts more structure?  )

First of all I don't think that it's floats in your asteroid_18800-0x2D60-vertex.block
Code: Select allOffset    0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

000000   5D 4C 7D C0 2C 53 30 03  11 FF 74 FF CF 80 7F FF
2ndly when I use your python script on prop_asteroid_01.cdr.out (where I cut off the .out since you claimed it to be a .cdr (!?) in your opening post) I get these face indices:
...
f  164/164/164 163/163/163 160/160/160
f  165/165/165 163/163/163 164/164/164
f  166/166/166 165/165/165 164/164/164

which are far from 724

Also (0x1B560 - 0x18800) / 16 = 726

Uhmm no that python script was just to use the function of rapi.decompress edge and use fwrite to get that index decompressed to the file uploaded before. Don't use the file .obj that noesis exports because i forgot to say that is not correctly generated as you see is not yet using correct vertex info and maybe because that it shrinks the face index number.  If you are using the python script with the .cdr file there should be a new "index-data-decompressed.block" in NOESIS folder i'm working with that file, sorry because i forgot to say that but the thing is that there are a lot of info and i'm working with other stuff too.

The python script is usefull just until it comes to decompressedges part xD.

i'm using a simple java app ("REALLY SIMPLE") to get 2 bytes integer from "index-data-decompressed.block" outputted from noesis to floats in v(a,b,c) patterns and with that i make that .txt with faces index list. Well that stuff looks Ok but maybe as you say i'm wrong with the thing about vertex data that maybe the one i choosen was not the floats that we need.

here is the code from that java app:
[http://pastebin.com/PNFhr5U7](http://pastebin.com/PNFhr5U7)

> Also (0x1B560 - 0x18800) / 16 = 726

0x18800 to 0x1B560 = 0x2D60 Length / 16 = 726 

Yeah that was my thought but as you say it doesn't look to be floats in that data but at least there is the pattern of 0x10(I would have to be blind not to see it xD) that looks good.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-07T21:22:33+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from psxmodder
>
> i'm using a simple java app ("REALLY SIMPLE") to get 2 bytes integer from "index-data-decompressed.block"great!  
That's what most beginners lack in: to gain basic coding knowledges.
So java is a good start!

As for your asteroid; I've a deja vue but I can't really recall from my tired mind what that could mean.  

So I used your index list to get some mesh (at no avail starting from 0x18800)
but seems I got the normals (because of the sphere).



prop_asteroid_01-cdr.JPG (124.05 KiB) Viewed 201 times
## Post #8
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-08T00:15:59+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from shakotay2
>
> psxmodder wrote:i'm using a simple java app ("REALLY SIMPLE") to get 2 bytes integer from "index-data-decompressed.block" great!  
That's what most beginners lack in: to gain basic coding knowledges.
So java is a good start!

As for your asteroid; I've a deja vue but I can't really recall from my tired mind what that could mean.  

So I used your index list to get some mesh (at no avail starting from 0x18800)
but seems I got the normals (because of the sphere).
prop_asteroid_01-cdr.JPG

Thats good but how many verts did you find with your tool?, it looks like they were a few right? or you get all the 726 verts?, well your tool have some alternative way to get the floats because in the ones that i did extract i have not found any 47.??? float but if that are the normals then in the header should be more info about it.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-08T07:56:18+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from psxmodder
>
> Thats good but how many verts did you find with your tool?I entered 726 as vertex count. (Normally hex2obj offers the maximum face index (FI) as the vertex count but it can't handle edgecompressed FIs.)

> to get the floats because in the ones that i did extract i have not found any 47.??? floatthat's the reason why I've switched to ShortAll ('short' means 'signed int', 'All' means verts AND uvs, which isn't proven so far).
## Post #10
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-09T02:22:12+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> that's the reason why I've switched to ShortAll ('short' means 'signed int', 'All' means verts AND uvs, which isn't proven so far).

First you say that in our 0x10 or 16 bytes lines instead of v(x,y,z,w?) x 4b there is v(x,y,z),vn(x,y,z),vt(u,v) x 2b right?. THat make sense according to the .WDR format on PC already documented here : [http://gta.wikia.com/wiki/WDR](http://gta.wikia.com/wiki/WDR)

```
---------------------------------------------------------------------------------------
VertexData (BlockSize VertexCount*0x24 or 0x34 when the Geometry is using a normal map)
---------------------------------------------------------------------------------------
0x00	4b	FLOAT	Position x
0x04	4b	FLOAT	Position y
0x08	4b	FLOAT	Position z
0x0C	4b	FLOAT	Normal x
0x10	4b	FLOAT	Normal y
0x14	4b	FLOAT	Normal z
0x18	4b	DWORD	Color (RGBA)
0x1C	4b	FLOAT	Texcoord u
0x20	4b	FLOAT	Texcoord v
0x24	4b	FLOAT	Tangent/Bi-Normal x   // Only when there is a normal map applied to the Geometry
0x28	4b	FLOAT	Tangent/Bi-Normal y   // Only when there is a normal map applied to the Geometry
0x2C	4b	FLOAT	Tangent/Bi-Normal z   // Only when there is a normal map applied to the Geometry
0x30	4b	FLOAT	Tangent/Bi-Normal w   // Only when there is a normal map 
```


Well obviusly on pc is maybe more suitable the use 4b arrays.

Another question how did you try to work with half floats convert? sorry if it is a dumb question
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T07:43:32+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

it's all wild guessing atm, the data might be compressed, shrinked, whatever. You could switch to HF_all in hex2obj but after pressing the go2 button you'll see that the result is not senseful:



asteroid_HF.JPG (69.59 KiB) Viewed 171 times


v 339 94208 0.067566 or v 5436 0.006973 0.06427 for example are assumed to be wrong vertices.

btw: "shrinked" would mean x xn y yn z zn.
(That's a very wild guess, admitted but I've seen something similar for tx, ty in a PC 3D format, tx tx1 ty ty1.)
## Post #12
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-09T20:03:46+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from shakotay2
>
> it's all wild guessing atm, the data might be compressed, shrinked, whatever. You could switch to HF_all in hex2obj but after pressing the go2 button you'll see that the result is not senseful:
asteroid_HF.JPG
v 339 94208 0.067566 or v 5436 0.006973 0.06427 for example are assumed to be wrong vertices.

btw: "shrinked" would mean x xn y yn z zn.
(That's a very wild guess, admitted but I've seen something similar for tx, ty in a PC 3D format, tx tx1 ty ty1.)

Humm but how did your program exactly get those normal verts ?, maybe is relevant to know what offsets etc. I don't see how they could shrink those bytes but maybe the function that is not properly working on the .py script for noesis can help us if we modify it in a better way here:

```
	#vertexSize = 0x10 * vertexCount
	print('Vertex Size: ' + hex(vertexDataSize))
	vertbuff = bs.readBytes(vertexDataSize)
	print('vertbuff Size: ' + hex(len(vertbuff)))
	rapi.rpgBindPositionBufferOfs(vertbuff, noesis.RPGEODATA_FLOAT, 0x10, 0)
	rapi.rpgSetName(str(i))
	#rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, (vertexSize // 16), noesis.RPGEO_POINTS, 1)
	rapi.rpgCommitTriangles(edgeDecomp, noesis.RPGEODATA_USHORT,vertexCount, noesis.RPGEO_TRIANGLE, 1)
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	f.close()
	rapi.rpgClearBufferBinds()	
```


Actually the code from "edgeDecomp = rapi.decompressEdgeIndices(edgeData, indexCount)" works great with the edges as we get those 726 face indexes but maybe there is another EDGE stuff related to our 0x2D60 bytes that contains our vertex data.

In the script the rpgCommitTriangles and rapi.rpgBindPositionBufferOfs(vertbuff, noesis.RPGEODATA_FLOAT, 0x10, 0) are not properly working as you see in .obj outputted by noesis export.

You know how we can check the output's from those functions without only writing with rpgConstructModel?. so We can check where is failling.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T20:53:15+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from psxmodder
>
> I don't see how they could shrink those bytesthat was an example only. If I knew what they did I would have told you.  

> Humm but how did your program exactly get those normal verts ?It's nothing special, something like xpos = Highbyte*256 + Lowbyte ;
(big endian data)
To handle signed values I use if (xpos>32767.0) xpos -= 65536.0;
xpos /= 256.0 ;
(the divider might be different -> scaling)

> but maybe there is another EDGE stuff related to our 0x2D60 bytes that contains our vertex data.To my knowledge Sony's edge compression is used for face indices only (but I may be wrong).

> You know how we can check the output's from those functions without only writing with rpgConstructModel?I don't get what you mean.
Also rapi.rpgBindPositionBufferOfs(vertbuff, noesis.RPGEODATA_FLOAT, 0x10, 0) can NOT work properly when used on data that is NOT float.
## Post #14
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-09T21:36:16+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

It's ok but i think that the "short all" method must be the one used because you get the normals, how are you converting those 2 bytes in "short all" method? i was thinking that you were using hf kind of conversion but now i see that you were referring to another type.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T21:48:37+00:00
- Post Title: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from psxmodder
>
> It's ok but i think that the "short all" method must be the one used because you get the normals, how are you converting those 2 bytes in "short all" method?like described in my post before

> i was thinking that you were using hf kind of conversion but now i see that you were referring to another type.didn't you understand my post as of Mon Jan 09, 2017 8:43 am? Read carefully, please.
I wrote that the result is not senseful when chosing HF_all. Because the data is not half floats, obviously.
## Post #16
- Username: psxmodder
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 07, 2017 11:52 am
- Post datetime: 2017-01-09T21:59:35+00:00
- Post Title: Re: [PS3] GTA V .CDR 3D Drawables Reversing edge related

> Reply from shakotay2
>
> psxmodder wrote:It's ok but i think that the "short all" method must be the one used because you get the normals, how are you converting those 2 bytes in "short all" method?like described in my post before
 i was thinking that you were using hf kind of conversion but now i see that you were referring to another type.didn't you understand my post as of Mon Jan 09, 2017 8:43 am? Read carefully, please.
I wrote that the result is not senseful when chosing HF_all. Because the data is not half floats, obviously.

Yes but i'm using signed int or short type already on java but i'm not even close to the result of mesh extractor. Thats why i'm asking you how really works your "Short all". Yes sorry because that confussion it was because even when you say that with short all there is a result your tool shows a float so there is a conversion even when it starts as a "short".
## Post #17
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-10T01:20:54+00:00
- Post Title: Re: [PS3] GTA V .CDR 3D Drawables Reversing edge related

It is most unfortunate there is little to none knowledge shared on the topic of PS EDGE Compression, ive been trying to figure out for ages, or even find a good and proper PS3 sdk release without missing code. and correct or more recent edgeLib source.

Finally found a good 1.2  and it seems to be exactly what the doctor ordered ;D  here is main code of interst (not sure on issues with sharing whole pack but drop me a pm and will share it with pleasure)

At quick glance, was interesting to see, :-

* there is seperate routines for handling Vertex compressed blocks && Animation Data (spline / streamable KF's ? )  &&  DXT textures

* It comes in few flavours:-  LZMA / LZO  / Zlib/gz 


Im going to be working on porting edge decomp to c#

p.s. on a sidenote,ive noticed edgeComp is remarkably similar to same data compressed with standard lzma (no dic)

```
 * PS Edge 1.2.0 (2007)
 */

#include "edge/geom/edgegeom.h"
#include "edge/geom/edgegeom_internal.h"
#include "edge/geom/edgegeom_decompress.h"

/**
 *	Decompresses compressed indexes
 * 
 * 	There are 4 main loops here, each doing 1 step in the decompression.  There is
 *  additional documentation inside the LibEdge-Overview document.  
 * 
 * 	The first loop decompress an n-bit stream into halfwords.  There are separate
 *  implementations for n <=8 and n > 8, due to the ability of n-bit values to straddle
 *  3 bytes, requiring additional work (9 is included in this group, even though it 
 *  can't straddle three bytes).  
 * 
 * 	For the n <= 8 case:
 * 		1) Load 3 qw
 * 		2) Align such that the first compressed index is aligned to the left of a quadword
 * 		3) Shuffle n-bit values into appropriate half words
 * 		4) Rotate into correct spot in half word
 * 		5) mask off bits n and higher
 * 		6) store
 * 	For the n > 8 case:
 * 		1) Load 6 qw
 * 		2) Align first 3 to front of quadword.  Align second 3 to front of quadword.
 * 		3) Shuffle portions of n-bit values into upper and lower splits.
 * 		4) Shift/rotate each split into place
 * 		5) Select to combine upper and lower bits.
 * 		6) Mask off garbage upper bits.
 * 		7) Store
 * 
 * 	The second loop applies the delta values.  For delta compression, each index decompressed
 * 	from the n-bit stream will have a base value subtracted from it, and will then be added 
 *  half-word-wise to the previous qw of indices.
 * 		1) Load 4 qw
 * 		2) Subtract base offset
 * 		3) Add previous qw of indices
 * 		4) Store
 * 		
 * 	Some additional info before describing the third loop: 
 * 		Actual construction of triangles is done in the 4th loop, using the output of the 3rd
 * 		loop as input.  Triangles are built by reusing previous triangles' indices, together
 * 		with a "new" index, or if none of the old indices can be reused, 3 new indices.  The
 * 		output of the 3rd loop is the stream from which these new indices are selected.
 * 
 * 		The "new index" stream as generated by the Edge Geometry tools is highly sequential; 
 * 		it is, in general, an incrementing series of indices, occasionally interrupted by an
 * 		index seen earlier in the list {1, 2, 3, 4, 1, 5, 6, 7, 3 . . . }.  The stream that
 * 		we've output from the second loop is an ordered list of the out of sequence entries,
 * 		in this case, {1,3}, for the second appearances of those indices.  
 * 
 * 	The third loop decompresses a 1-bit stream which specifies whether the next index in the
 * 	stream should be drawn from the incrementing sequence, or from the out of sequence list
 * 	output by the second loop.  
 * 		1) Load 1-bit control stream and out of sequence indexes
 * 		2) Align control stream
 * 		3) Build masks according to control bits
 * 		4) Shuffle sequence and index streams to produce output
 * 		5) Update sequence qw
 * 		6) Shuffle sequence and next set of indices to produce next output.
 * 		7) Update sequence
 * 		8) Store final output buffers
 * 
 *  The fourth loop builds the final triangle ordering, using the output of the third loop
 * 	as the input of "new" indexes.  A 2-bit pattern specifies which triangle ordering should
 *  be used (ACa, CBa, BAa, or abc, where A,B,C are from the previous triangle and a,b,c are
 *  the next indexes in the input stream).  This loop decompresses 8 triangles at a time.
 * 
 * 		1) Load control bits for 8 triangles (1 halfword)
 * 		2) Load enough indices for 8 triangles of all new indices
 * 		3) Rotate control bits to be used as offsets into lookup tables (4 bit indices)
 * 		4) Load triangle format masks and input stream update masks
 * 		5) Shuffle inputs to make first triangle.
 * 		6) Shuffle inputs to remove used indices.
 * 		7) Repeat 5 and 6 twice.  
 * 		8) Repeat 5 a third time (inputs needn't be realigned, since they'll be reloaded next 
 * 		   time through)
 * 		9) Shuffle triangles together to form final output stream.
 * 		10)Store outputs.
 * 
 * 	At this point we have our final index list, and can free the space previously taken up
 * 	by the block of index data.
 */
#if !DECOMPRESSINDEXES_INTRINSICS
static void DecompressIndexes_2BitStream(uint16_t *pIndexStream, uint8_t *pControlStream, uint16_t *pOutputStream, uint32_t numTriangles)
{
	//always outputs 48 bytes => 8 triangles
    //4 triangles per control byte
	const uint32_t numTrianglesRounded = (numTriangles + 7) & -8;
	const uint32_t outerLoopCount = numTrianglesRounded >> 2;
	
	for (uint32_t i = 0; i < outerLoopCount; i++) {
		uint8_t controlBits = *pControlStream++;
		for (uint32_t j = 0; j < 4; j++) {
			uint8_t code = controlBits & 0xC0;

			switch (code) {
			case 0xC0: //abca
				pOutputStream[0] = *pIndexStream++;
				pOutputStream[1] = *pIndexStream++;
				pOutputStream[2] = *pIndexStream++;
				pOutputStream += 3;
				break;
			case 0x80: //BAa
				pOutputStream[0] = *(pOutputStream - 2);
				pOutputStream[1] = *(pOutputStream - 3);
				pOutputStream[2] = *pIndexStream++;
				pOutputStream += 3;
				break;
			case 0x40: //CBa
				pOutputStream[0] = *(pOutputStream - 1);
				pOutputStream[1] = *(pOutputStream - 2);
				pOutputStream[2] = *pIndexStream++;
				pOutputStream += 3;
				break;
			case 0x0: //ACa
				pOutputStream[0] = *(pOutputStream-3);
				pOutputStream[1] = *(pOutputStream-1);
				pOutputStream[2] = *pIndexStream++;
				pOutputStream += 3;
				break;
			default:
				EDGE_ASSERT(0);
			}

			controlBits = controlBits << 2;
		}
	}
}

static void DecompressIndexes_Relocate2BitStream(uint8_t *src, uint8_t *dst, uint32_t numTriangles)
{
	uint32_t copyCount = 0;
	const uint32_t num2BitStreamBytes = ((numTriangles + numTriangles) + 7) >> 3;

	do{
		//copy 16 bytes
		for (uint32_t i = 0; i < 16; i++) {
			*dst++ = *src++;
		}
		copyCount += 0x10;
	} while(copyCount < num2BitStreamBytes);
}

static void DecompressIndexes_1BitStream(uint16_t *pIndexStream, uint16_t *pOutputStream, uint8_t *pControlStream, uint32_t numIndexes, uint32_t *pEndOfBuffer)
{
	//writes 32 bytes/16 indexes per iteration
	const uint32_t rounded = (numIndexes + 15) & -16;

	uint16_t next = 0;
	uint8_t mask = 1 << 7;

	for (uint32_t i = 0; i < rounded; i++) {
		uint8_t outOfSequence = *pControlStream & mask;

		if (outOfSequence) {
			*pOutputStream++ = *pIndexStream++;
		}
		else {
			*pOutputStream++ = next++;
		}

		mask = mask >> 1;

		if (!mask) {
			mask = 1 << 7;
			++pControlStream;
		}
	}

	*pEndOfBuffer = (uint32_t)pOutputStream;
}

static void DecompressIndexes_Deltas(uint16_t *pIndexes, uint32_t numIndexes, uint16_t baseDelta)
{
	//32 deltas at a time
	//runs forward
	//writes out 4 quads

	uint16_t outputDelta[8] __attribute__((__aligned__(16)));
	for (uint32_t i = 0; i < 8; i++)
		outputDelta[i] = 0;

	uint32_t numIter = 	((numIndexes + 31) & -32) >> 3;

	for (uint32_t iter = 0; iter < numIter; iter++) {
		for (uint32_t index = 0; index < 8; index++) {
			outputDelta[index] = pIndexes[8*iter + index] - baseDelta + outputDelta[index];
			pIndexes[8*iter + index] = outputDelta[index];
		}
	}
}

static void DecompressIndexes_NBitStream(uint8_t *pIn, uint16_t *pOut, uint32_t n, uint32_t numToExpand)
{
	//32 indexes at a time
	//runs in reverse
	//writes out 4 quads

	const uint32_t rounded = (numToExpand + 31) & -32;
	pOut = pOut + (rounded - 1);

	uint32_t offset = (rounded - 1) * n;
	for (uint32_t i = rounded; i > 0; i--) 
	{
		uint8_t *b = pIn + (offset >> 3);

		uint32_t b0 = b[0];
		uint32_t b1 = b[1];
		uint32_t b2 = b[2];

		uint32_t buf = (b0 << 24) | (b1 << 16) | (b2 << 8);
		buf = buf << (offset & 0x7);

		*pOut-- = buf >> (32 - n);

		offset -= n;
	}
}

static void DecompressIndexes_C_Standalone(const unsigned int numIndexes, const void *indexes)
{
	const uint32_t numTriangles = numIndexes / 3;

	const uint32_t num1Bits = (uint32_t)(((uint16_t *)indexes)[2]) << 3;
	const uint32_t bytesBefore2BitStream = 8 + ((num1Bits + 7) >> 3);
	const uint32_t num2BitStreamBytes = (((numTriangles + numTriangles) + 7) >> 3);

	const uint32_t bytesBeforeNBitStream = bytesBefore2BitStream + num2BitStreamBytes;
	const uint32_t numIndexesInNBitStream = (uint32_t)(((uint16_t *)indexes)[0]);
	uint16_t *decompressedNBitStream = (uint16_t *)((uint32_t)indexes + (bytesBeforeNBitStream + 0xf) & ~0xf);
	const uint32_t n = ((uint8_t *)indexes)[6];

	DecompressIndexes_NBitStream(	(uint8_t *)((uint32_t)indexes + bytesBeforeNBitStream), 
									decompressedNBitStream, 
									n,
									numIndexesInNBitStream);

	const uint16_t deltaOffset =  ((uint16_t *)indexes)[1];
	DecompressIndexes_Deltas(decompressedNBitStream, numIndexesInNBitStream, deltaOffset);

	const uint32_t bytesBeforeDecompressedSequence = ((numTriangles * 6) + 0xf) & ~0xf;
	uint16_t *decompressedSequence = (uint16_t *)((uint32_t)indexes + bytesBeforeDecompressedSequence);
	uint32_t pEndOfDecompressedSequence;
	DecompressIndexes_1BitStream(	decompressedNBitStream,
									decompressedSequence,
									(uint8_t *)((uint32_t)indexes + 8), 
									num1Bits,
									&pEndOfDecompressedSequence);
	

	//copy 2 bit table
	DecompressIndexes_Relocate2BitStream(	(uint8_t *)((uint32_t)indexes + bytesBefore2BitStream),
											(uint8_t *)pEndOfDecompressedSequence,
											numTriangles);

	DecompressIndexes_2BitStream(decompressedSequence, (uint8_t*)pEndOfDecompressedSequence, (uint16_t *)indexes, numTriangles);
}

void DecompressIndexes(EdgeGeomSpuContext *ctx, const void *indexes)
{
	DecompressIndexes_C_Standalone(ctx->spuConfigInfo.numIndexes, indexes);

	void* freePtr = (void *)((uint32_t)indexes + (ctx->spuConfigInfo.numIndexes + ctx->spuConfigInfo.numIndexes));
	freePtr = (void*)(((unsigned int)freePtr + 0xf) & ~0xf);
	edgeGeomSetFreePtr(ctx, freePtr);
}
#endif

#if !DECOMPRESSVERTEXESBYDESCRIPTION_INTRINSICS
static inline float sqrt(float f)
{
	return f * si_to_float(si_fi(si_from_float(f), si_frsqest(si_from_float(f))));
}

void DecompressVertexesByDescription(EdgeGeomSpuContext *ctx,
	const void *vertexes, const void *fixedOffsets, const EdgeGeomVertexStreamDescription *streamDesc,
	uint32_t numVertexes, float blendFactor, uint16_t *blendedVertexTable)
{
	if (numVertexes == 0) {
		return;
	}

	const bool isBlending = blendFactor != 0.f;

	uint32_t *fixedPointOffsets = (uint32_t *)fixedOffsets;

	if (isBlending && (ctx->spuConfigInfo.flagsAndUniformTableCount & EDGE_GEOM_FLAG_INCLUDES_EXTRA_UNIFORM_TABLE) == 0)
	{
		EDGE_PRINTF("ERROR: attempt to use blend shapes without allocating an extra uniform table!\n");
		return;
	}

	const uint32_t unroundedVertexCount = numVertexes;
	const uint32_t vertexCount  = (numVertexes+3)& ~3;
	const uint32_t vertexStride = streamDesc->stride;

#ifdef EDGE_GEOM_DEBUG
	if (streamDesc->stride == 0)
	{
		EDGE_PRINTF("ERROR: input/blend stream description has 0 size!\n");
		return;
	}	
#endif

	const bool isFastStaticPath = (ctx->spuConfigInfo.flagsAndUniformTableCount & EDGE_GEOM_FLAG_STATIC_GEOMETRY_FAST_PATH) != 0;

	const EdgeGeomGenericBlock *nextAttribute = streamDesc->blocks;
	// Process each attribute sequentially.
	for(uint32_t iAttr=0; iAttr<streamDesc->numAttributes; ++iAttr)
	{
		// Load the attribute description

		uint8_t *pIn = (uint8_t *)vertexes;

		EdgeGeomAttributeBlock attribute = nextAttribute->attributeBlock;
		nextAttribute++;

		const int attrId = attribute.edgeAttributeId;
		// If this segment uses the fast path for static geometry, don't decompress anything except
		// position.
		if ( isFastStaticPath && attrId != EDGE_GEOM_ATTRIBUTE_ID_POSITION)
		{
			continue;
		}

		// Get the number of valid uniform tables, excluding the extra table (if present)
		uint32_t uniformTableCount = edgeGeomGetUniformTableCount(ctx);
		if ((ctx->spuConfigInfo.flagsAndUniformTableCount & EDGE_GEOM_FLAG_INCLUDES_EXTRA_UNIFORM_TABLE) == 0)
		{
			uniformTableCount--;
		}
			
		// Decompress this attribute to the next unassigned uniform table.  If we're blending,
		// we decompress the deltas into the spare uniform table first, and then blend them into
		// the final destination table.
		int32_t destTableIndex = -1;
		for(uint32_t iTable=0; iTable<uniformTableCount; ++iTable)
		{
			if (ctx->uniformTableToAttributeIdMapping[iTable] == EDGE_GEOM_ATTRIBUTE_ID_UNKNOWN)
			{
				destTableIndex = iTable;
				break;
			}
		}
		EDGE_ASSERT_MSG(destTableIndex >= 0, ("ERROR: too many vertex attributes, not enough uniform tables!"));

		float *pUniform = isBlending ? ctx->uniformTables[ctx->spuConfigInfo.flagsAndUniformTableCount & 0xF] : ctx->uniformTables[destTableIndex];
		const int32_t attribFormat = attribute.format;
		void *pDestTable = (void *)pUniform;

		// if we're blending, check to make sure there's already a
		// uniform table for the current attribute.  If not, skip it
		// (there's nothing to blend with!)
		float *pBlendTable = 0;
		if (isBlending)
		{
			const uint8_t id = attribute.edgeAttributeId;
			for (uint32_t iTable = 0; iTable < uniformTableCount; iTable++) {
				if (ctx->uniformTableToAttributeIdMapping[iTable] == id) {
					pBlendTable = (float *)edgeGeomGetUniformTable(ctx, iTable);
					break;
				}
			}
			if (pBlendTable == 0)
				continue;
		}

		//offset into vertex
		const uint8_t attribOffset = attribute.offset;

		pIn += attribOffset;

		switch(attribFormat)
		{
		case EDGE_GEOM_ATTRIBUTE_FORMAT_F32:
			{
				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					uint32_t j;
					for (j = 0; j < attribute.componentCount; j++) {
						union {float f; uint8_t b[4];} u;
	
						u.b[0] = pCurr[0];
						u.b[1] = pCurr[1];
						u.b[2] = pCurr[2];
						u.b[3] = pCurr[3];
	
						pUniform[j] = u.f;
						pCurr += 4;
					}
					for (; j < 3; j++) {
						pUniform[j] = 0.f;
					}
					for (; j < 4; j++) {
						pUniform[j] = 1.f;
					}
					pIn += vertexStride;
					pUniform += 4;
				}
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_F16:
			{
				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					for (uint32_t j = 0; j < attribute.componentCount; j++) {
						union {float f; uint32_t u32; uint8_t b[4];} u;
	
						u.b[0] = pCurr[0];
						u.b[1] = pCurr[1];
						u.b[2] = 0;
						u.b[3] = 0;

						//1|5|10
						uint32_t signBit = u.u32 & 0x80000000;
						uint32_t exp = (u.u32 >> 26) & 0x1F;
						uint32_t man = (u.u32 >> 16) & 0x3FF;

						u.u32 = signBit | ((exp + 112) << 23) | (man << 13);
						pUniform[j] = u.f;
						pCurr += 2;
					}
					pIn += vertexStride;
					pUniform += 4;
				}
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_I16:
			for (uint32_t i = 0; i < vertexCount; i++) {
				uint8_t *pCurr = pIn;
				for (uint32_t j = 0; j < attribute.componentCount; j++) {
					union {int16_t i16; uint8_t b[2];} u;
					u.b[0] = pCurr[0];
					u.b[1] = pCurr[1];

					pUniform[j] = (float)u.i16;
					
					pCurr += 2;
				}
				pIn += vertexStride;
				pUniform += 4;
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_I16N:
			{
				const float i16nScale = 2.0f / 65535.0f;
				const float i16nBias = 1.0f / 65535.0f;
				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					for (uint32_t j = 0; j < attribute.componentCount; j++) {
						union {int16_t i16; uint8_t b[2];} u;
						u.b[0] = pCurr[0];
						u.b[1] = pCurr[1];

						pUniform[j] = ((float)u.i16) * i16nScale + i16nBias;

						pCurr += 2;
					}
					pIn += vertexStride;
					pUniform += 4;
				}
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_U8:
			for (uint32_t i = 0; i < vertexCount; i++) {
				uint8_t *pCurr = pIn;
				for (uint32_t j = 0; j < attribute.componentCount; j++) {
					uint32_t u32 = (uint32_t)pCurr[0];
					pUniform[j] = (float)u32;

					pCurr += 1;
				}
				pIn += vertexStride;
				pUniform += 4;
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_U8N:
			{
				const float u8nScale = 1.0f / 255.0f;
				const float u8nBias = 0.0f;

				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					for (uint32_t j = 0; j < attribute.componentCount; j++) {
						uint32_t u32 = (uint32_t)pCurr[0];
						pUniform[j] = ((float)u32) * u8nScale + u8nBias;

						pCurr += 1;
					}
					pIn += vertexStride;
					pUniform += 4;
				}
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_X11Y11Z10N:
			{
				const uint32_t x11y11z10Table[8] = 
				{
					0x3F801002, 0x3F801002, 0x3F802008, 0,
					0x3A001002, 0x3A001002, 0x3A802008, 0x3F800000
				};

				//this violates strict aliasing
				union {const float *f; const uint32_t *u32;} u;
				u.u32 = x11y11z10Table;

				const float x11y11z10ScaleX = u.f[0];
				const float x11y11z10ScaleY = u.f[1];
				const float x11y11z10ScaleZ = u.f[2];
				//const float x11y11z10ScaleW = u.f[3];
	
				const float x11y11z10BiasX = u.f[4];
				const float x11y11z10BiasY = u.f[5];
				const float x11y11z10BiasZ = u.f[6];
				const float x11y11z10BiasW = u.f[7];
	
				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					union {int32_t i32; uint8_t b[4];} u;
	
					u.b[0] = pCurr[0];
					u.b[1] = pCurr[1];
					u.b[2] = pCurr[2];
					u.b[3] = pCurr[3];
	
					int32_t ix = u.i32 << 16;
					int32_t iy = (u.i32 << 8) & 0xFFFF0000;
					int32_t iz = u.i32 & 0xFFFF0000;
	
					ix <<= 5;
					iy <<= 2;
	
					ix &= 0xFFE00000;
					iy &= 0xFFE00000;
					iz &= 0xFFC00000;
	
					float x = ((float)ix / (float)(1 << 31)) * x11y11z10ScaleX + x11y11z10BiasX;
					float y = ((float)iy / (float)(1 << 31)) * x11y11z10ScaleY + x11y11z10BiasY;
					float z = ((float)iz / (float)(1 << 31)) * x11y11z10ScaleZ + x11y11z10BiasZ;
					float w = x11y11z10BiasW;
	
					pUniform[0] = x;
					pUniform[1] = y;
					pUniform[2] = z;
					pUniform[3] = w;
	
					pIn += vertexStride;
					pUniform += 4;
				}
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_FIXED_POINT:
			{
				const uint32_t fixedTable[1] = {0x4F800000};
				union {const float *f; const uint32_t *u32;} u;
				u.u32 = fixedTable;

				const float fixedScale = *(float *)u.f;

				EdgeGeomAttributeFixedBlock fixed = *(EdgeGeomAttributeFixedBlock *)((uint32_t)(streamDesc->blocks) + attribute.fixedBlockOffset);
				uint8_t *bits = (uint8_t *)&fixed;

				const uint32_t intBits[4] = {bits[0], bits[2], bits[4], bits[6]};
				const uint32_t manBits[4] = {bits[1], bits[3], bits[5], bits[7]};
				const uint32_t totBits[4] = {	intBits[0] + manBits[0],
												intBits[1] + manBits[1],
												intBits[2] + manBits[2],
												intBits[3] + manBits[3]};

				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					for (uint32_t j = 0; j < attribute.componentCount; j++) {
						union {int32_t i32; uint8_t u8[4];} u;
						u.u8[0] = pCurr[0];
						u.u8[1] = pCurr[1];
						u.u8[2] = pCurr[2];
						u.u8[3] = pCurr[3];

						//shift and mask out the garbage
						int32_t shifted = u.i32 >> (32 - totBits[j]);
						shifted += fixedPointOffsets[j];
						//shift int bits right, man bits left, convert separately, and add
						const int32_t intShifted = shifted >> manBits[j];
						const uint32_t manShifted = shifted << (32 - manBits[j]);
						const float fInt = (float)intShifted;
						const float fMan = (float)manShifted / fixedScale;

						pUniform[j] = fInt + fMan;
						pCurr += (totBits[j]) >> 3;
					}
					pIn += vertexStride;
					pUniform += 4;
				}
				fixedPointOffsets += 4;
			}
			break;
		case EDGE_GEOM_ATTRIBUTE_FORMAT_UNIT_VECTOR:
			{
				const uint32_t uvTable[2] = 
				{
					0x46352e7c, 0xc6353150
				};

				//this violates strict aliasing
				union {const float *f; const uint32_t *u32;} u;
				u.u32 = uvTable;

				const float uvScale = u.f[0];
				const float uvBias = u.f[1];

				for (uint32_t i = 0; i < vertexCount; i++) {
					uint8_t *pCurr = pIn;
					union {uint32_t u32; uint8_t b[4];} u;
	
					u.b[0] = pCurr[0];
					u.b[1] = pCurr[1];
					u.b[2] = pCurr[2];
					u.b[3] = 0;
	
					uint32_t a = (u.u32 >> 22) & 0x3ff;
					uint32_t b = (u.u32 >> 12) & 0x3ff;
					
					union {float f; uint32_t u32;} ua, ub;
					ua.u32 = a | 0x3f800000;
					ub.u32 = b | 0x3f800000;
	
					ua.f = ua.f * uvScale + uvBias;
					ub.f = ub.f * uvScale + uvBias;
	
					float c = sqrt(1.0f - (ua.f * ua.f + ub.f * ub.f));
					c *= (u.u32 & 0x100) ? 1.0f : -1.0f;
					float w = (u.u32 & 0x200) ? 1.0f : -1.0f;
	
					float x=0, y=0, z=0;
					switch ((u.u32 >> 10) & 0x3) {
					case 0:
						x = c;
						y = ua.f;
						z = ub.f;
						break;
					case 1: 
						x = ua.f;
						y = c;
						z = ub.f;
						break;
					case 2:
						x = ua.f;
						y = ub.f;
						z = c;
						break;
					}
	
					pUniform[0] = x;
					pUniform[1] = y;
					pUniform[2] = z;
					pUniform[3] = w;
	
					pIn += vertexStride;
					pUniform += 4;
				}
			}
			break;
		}

		// For decompression purposes, X11Y11Z10N attributes should have 3 components
		uint32_t numComponents = (attribFormat == EDGE_GEOM_ATTRIBUTE_FORMAT_X11Y11Z10N) ? 3 :
			attribute.componentCount;

		// For position attributes with fewer than 4 components, fill
		// in reasonable defaults for any remaining components
		if (attrId == EDGE_GEOM_ATTRIBUTE_ID_POSITION && numComponents < 4) {
			for (uint32_t i = 0; i < vertexCount; i++) {
				for (uint32_t j = numComponents-1; j<4; ++j) {
					pUniform[4*i + j] = (j < 3) ? 0.0f : 1.0f;
				}
			}
		}

		if (isBlending) {
			//which uniform
			pUniform = (float *)pDestTable;

			//clear out the unused final deltas
			for (uint32_t i = unroundedVertexCount; i < vertexCount; i++) {
				pUniform[4*i + 0] = 0.f;
				pUniform[4*i + 1] = 0.f;
				pUniform[4*i + 2] = 0.f;
				pUniform[4*i + 3] = 0.f;
			}

			for (uint32_t i = 0; i < vertexCount; i++) {
				for (uint32_t j = 0; j < numComponents; j++) {
					// blended vertex table is byte offsets. If the table is NULL,
					// use the delta index as the destination vertex index.
					uint16_t destVertIndex = (blendedVertexTable != 0) ? (blendedVertexTable[i]) >> 4
						: i;
					pBlendTable[4 * destVertIndex + j] += pUniform[4 * i + j] * blendFactor;
				}
			}
		}
		else{
			// Set the uniform table pointers based on the attribute's
			// ID.
			switch(attrId)
			{
			case EDGE_GEOM_ATTRIBUTE_ID_POSITION:
				ctx->positionTable = pDestTable;
				break;
			case EDGE_GEOM_ATTRIBUTE_ID_NORMAL:
				ctx->normalTable = pDestTable;
				break;
			case EDGE_GEOM_ATTRIBUTE_ID_TANGENT:
				ctx->tangentTable = pDestTable;
				break;
			case EDGE_GEOM_ATTRIBUTE_ID_BINORMAL:
				ctx->binormalTable = pDestTable;
				break;
			}

			ctx->uniformTableToAttributeIdMapping[destTableIndex] = attrId;
		}
	}
}
#endif

#if !DECOMPRESSBLENDSHAPERUNTABLE_INTRINSICS
void DecompressBlendShapeRunTable(uint16_t *runTable, uint32_t runTableSize,
	uint32_t numDeltas)
{
	if (runTableSize == 0)
		return;

	//we're decompressing it in place, so get pointers to the last delta
	//and to the last entry in the run table
	uint16_t *pDelta = runTable + (numDeltas);
	uint16_t *pIn = ((uint16_t *)(((uint32_t)runTable) + runTableSize)) - 1;

	uint16_t *pZeroDeltas = pDelta;
	while ((uint32_t)pZeroDeltas & 0xF) {
		*pZeroDeltas++ = 0;
	}

	do {
		uint16_t entry = *pIn;
		pIn--;

		uint16_t *pEnd = pDelta;
		uint8_t runSize = (entry & 0x1F) + 1;
		pDelta -= runSize;
		uint16_t *pStart = pDelta;
		uint16_t base = (entry & 0xFFE0) >> 1;

		while (pStart != pEnd) {
			*pStart = base;
			base += 0x10;
			pStart++;
		}
	} while (pIn >= runTable);
}
#endif

```
## Post #18
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-10T12:59:56+00:00
- Post Title: Re: [PS3] GTA V .CDR 3D Drawables Reversing edge related

my conversion is going horribly wrong, the whole pointer/value/size thing confuses daylights out of me, but here is first out of 4 steps, with sample Edges (original + compressed),  if anyone more clued up on c++, would be greatful for some insight


```
		{
			0x00, 0x00, 0x01, 0x00, 0x02, 0x00, 0x01, 0x00, 0x00, 0x00, 0x03, 0x00, 0x03, 0x00, 0x00, 0x00, 
			0x04, 0x00, 0x03, 0x00, 0x05, 0x00, 0x06, 0x00, 0x04, 0x00, 0x07, 0x00, 0x08, 0x00, 0x08, 0x00, 
			0x07, 0x00, 0x09, 0x00, 0x09, 0x00, 0x07, 0x00, 0x0A, 0x00, 0x09, 0x00, 0x0A, 0x00, 0x0B, 0x00, 
			0x09, 0x00, 0x0B, 0x00, 0x0C, 0x00, 0x09, 0x00, 0x0C, 0x00, 0x0D, 0x00, 0x08, 0x00, 0x0E, 0x00, 
			0x0F, 0x00, 0x0E, 0x00, 0x08, 0x00, 0x10, 0x00, 0x08, 0x00, 0x11, 0x00, 0x12, 0x00, 0x12, 0x00, 
			0x11, 0x00, 0x13, 0x00, 0x13, 0x00, 0x14, 0x00, 0x10, 0x00, 0x15, 0x00, 0x0E, 0x00, 0x16, 0x00, 
			0x15, 0x00, 0x17, 0x00, 0x18, 0x00, 0x18, 0x00, 0x17, 0x00, 0x19, 0x00, 0x19, 0x00, 0x1A, 0x00, 
			0x1B, 0x00, 0x1B, 0x00, 0x1A, 0x00, 0x1C, 0x00, 0x1B, 0x00, 0x1C, 0x00, 0x1D, 0x00, 0x1D, 0x00, 
			0x1C, 0x00, 0x1E, 0x00, 0x1D, 0x00, 0x1E, 0x00, 0x1F, 0x00, 0x1F, 0x00, 0x1E, 0x00, 0x20, 0x00, 
			0x1F, 0x00, 0x20, 0x00, 0x21, 0x00, 0x1F, 0x00, 0x21, 0x00, 0x22, 0x00, 0x22, 0x00, 0x21, 0x00, 
			0x23, 0x00, 0x22, 0x00, 0x23, 0x00, 0x24, 0x00, 0x24, 0x00, 0x23, 0x00, 0x25, 0x00, 0x25, 0x00, 
			0x23, 0x00, 0x26, 0x00, 0x25, 0x00, 0x26, 0x00, 0x27, 0x00, 0x27, 0x00, 0x26, 0x00, 0x28, 0x00, 
			0x27, 0x00, 0x28, 0x00, 0x29, 0x00, 0x29, 0x00, 0x28, 0x00, 0x2A, 0x00, 0x29, 0x00, 0x2A, 0x00, 
			0x2B, 0x00, 0x29, 0x00, 0x2B, 0x00, 0x2C, 0x00, 0x2A, 0x00, 0x2D, 0x00, 0x2B, 0x00, 0x2B, 0x00, 
			0x2D, 0x00, 0x2E, 0x00, 0x2B, 0x00, 0x2E, 0x00, 0x2F, 0x00, 0x2B, 0x00, 0x2F, 0x00, 0x30, 0x00, 
			0x2B, 0x00, 0x30, 0x00, 0x2C, 0x00, 0x2C, 0x00, 0x30, 0x00, 0x31, 0x00, 0x2C, 0x00, 0x31, 0x00, 
			0x32, 0x00, 0x32, 0x00, 0x31, 0x00, 0x33, 0x00, 0x32, 0x00, 0x33, 0x00, 0x34, 0x00, 0x34, 0x00, 
			0x33, 0x00, 0x35, 0x00, 0x36, 0x00, 0x2F, 0x00, 0x2E, 0x00, 0x2F, 0x00, 0x36, 0x00, 0x37, 0x00, 
			0x2F, 0x00, 0x37, 0x00, 0x38, 0x00, 0x2F, 0x00, 0x38, 0x00, 0x39, 0x00, 0x2F, 0x00, 0x39, 0x00, 
			0x3A, 0x00, 0x2F, 0x00, 0x3A, 0x00, 0x30, 0x00, 0x3B, 0x00, 0x3C, 
		} ;
		//Vertex-Count = 118
		//
		unsigned char edgeCompressed[96] =
		{
			0x00, 0x27, 0x00, 0x00, 0x00, 0x14, 0x06, 0x00, 0x04, 0x80, 0x88, 0xAA, 0x20, 0x00, 0x02, 0x88, 
			0x18, 0x44, 0x88, 0x32, 0x0C, 0x09, 0x00, 0x00, 0x6D, 0xB7, 0x07, 0x00, 0xE7, 0xD4, 0x0E, 0xDF, 
			0xDD, 0x11, 0x04, 0x51, 0x10, 0xD0, 0x11, 0x1E, 0x00, 0xFD, 0xD1, 0xDD, 0x1D, 0x57, 0x78, 0x44, 
			0x44, 0x44, 0x3F, 0xDD, 0x55, 0xD1, 0x00, 0x0C, 0x42, 0x08, 0x4D, 0x03, 0x95, 0x5A, 0x68, 0xE4, 
			0x71, 0xE8, 0xA6, 0x89, 0x86, 0x97, 0x69, 0x13, 0x8C, 0x6E, 0x48, 0x24, 0x76, 0x7A, 0xA2, 0x40, 
			0x41, 0x04, 0x10, 0x40, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 
		} ;

         [b]   result = DecompressIndexes_C_Standalone(315,edgeCompressed);[/b]


int DecompressIndexes_NBitStream( uint8_t *pIn, uint16_t *pOut, uint32_t n, uint32_t numToExpand)
{
	//32 indexes at a time
	//runs in reverse
	//writes out 4 quads

	const uint32_t rounded = (numToExpand + 31) & -32;
	pOut = pOut + (rounded - 1);

	uint32_t offset = (rounded - 1) * n;
	for (uint32_t i = rounded; i > 0; i--) 
	{
		uint8_t *b = pIn + (offset >> 3);

		uint32_t b0 = b[0];
		uint32_t b1 = b[1];
		uint32_t b2 = b[2];

		uint32_t buf = (b0 << 24) | (b1 << 16) | (b2 << 8);
		buf = buf << (offset & 0x7);

		*pOut-- = buf >> (32 - n);

		offset -= n;
	}
}
int DecompressIndexes_C_Standalone(const unsigned int numIndexes, const void *indexes)
{
	const uint32_t numTriangles = numIndexes / 3;

	const uint32_t num1Bits = (uint32_t)(((uint16_t *)indexes)[2]) << 3;
	const uint32_t bytesBefore2BitStream = 8 + ((num1Bits + 7) >> 3);
	const uint32_t num2BitStreamBytes = (((numTriangles + numTriangles) + 7) >> 3);

	const uint32_t bytesBeforeNBitStream = bytesBefore2BitStream + num2BitStreamBytes;
	const uint32_t numIndexesInNBitStream = (uint32_t)(((uint16_t *)indexes)[0]);
	uint16_t *decompressedNBitStream = (uint16_t *)((uint32_t)indexes + (bytesBeforeNBitStream + 0xf) & ~0xf);
	const uint32_t n = ((uint8_t *)indexes)[6];

	DecompressIndexes_NBitStream(	(uint8_t *)((uint32_t)indexes + bytesBeforeNBitStream), 
									decompressedNBitStream, 
									n,
									numIndexesInNBitStream);
}



```
## Post #19
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-10T13:08:57+00:00
- Post Title: Re: [PS3] GTA V .CDR 3D Drawables Reversing edge related

First Step now a success  it required EdgeData to be array of shorts
## Post #20
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-10T19:23:51+00:00
- Post Title: Re: [PS3] GTA V .CDR 3D Drawables Reversing edge related

k, its getting stuck on step 3, (deltas), but bulk of edges are already decompressed in step 1.  the rest is just any index with value < 13 (or those numbers taking up only 4 bits)  so remaining bytes would be stored in 6 to 10 bytes somewhere (i suspect is the last few bytes in file).   anyway issue is probably:  endianness /  using array of shorts, rather than bytes or filestream.  i will post working code so far (vs2k13) hopefully someone can solve and we can put this to bed
