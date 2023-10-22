## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-12-21T08:47:34+00:00
- Post Title: God of War 3 Mesh fix

In ps23dformat.wikispaces.com there are some bms script written by "3dmodel" for extract models from different ps2/ps3 games.

There are two scripts for god of war 3 , one for unpack the WAD files and the other for convert the WAD file directly to 3DS, but all surfaces are damaged and the models don't have uv cords



someone can fix the script for obtain perfect surfaces?

here are two WAD files:

[http://www.mediafire.com/download/25cuy ... PS3_BE.rar](http://www.mediafire.com/download/25cuyni4db3jy94/PS3_BE.rar)

this is the script for extract 3d meshes:

```
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
Get Q ASIZE 0 ;
Math number = 0 ;
For T = 0 < Q ;
Math number += 1 ;
findloc OFFSET string "\xFF\xFF\xFF\x9C\x00\x00\x00\x00\xFF\xFF\xFF\x54\x00\x20\x00\x00\x00\x40" 0 0 ;
Math cctest = 278 ;
If OFFSET = 0 ;
Math T = Q ;
Math T += 1 ;
EndIF ;
If OFFSET != 0 ;
GoTo OFFSET 0 ;
SavePos start 0 ;
GoTo 11 0 SEEK_CUR ;
Get cctest Byte 0 ;
Put start Long MEMORY_FILE4 ;
EndIF ;
Next T ;
Get ssk ASIZE MEMORY_FILE4 ;
Math ssk /= 4 ;
Math deersun = 0 ;
For qmk = 1 To ssk ;
GoTo deersun MEMORY_FILE4 ;
Get deerstart Long MEMORY_FILE4 ;
SavePos deersun MEMORY_FILE4 ;
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
Math Qprime = 0 ;
Math Qprimeprime = 0 ;
Math Qer = 0 ;
Math GG = 0 ;
Math YFYF = 0 ;
Math deerstart -= 0x40 ;

GoTo deerstart 0 ;
GoTo 0x4 0 SEEK_CUR ;
Get cvertex1 Byte 0 ;
Get cvertex2 Byte 0 ;




Math cvertex1 *= 256 ;
Math cvertex1 += cvertex2 ;








Math VertexNumber = cvertex1 ;











GoTo deerstart 0 ;
GoTo 0x1C 0 SEEK_CUR ;
Get tto11 Byte 0 ;
Get tto22 Byte 0 ;
Get tto33 Byte 0 ;
Get tto44 Byte 0 ;
Math tto11 *= 16777216 ;
Math tto22 *= 65536 ;
Math tto33 *= 256 ;
Math tto55 = tto11 ;
Math tto55 += tto22 ;
Math tto55 += tto33 ;
Math tto55 += tto44 ;
Math qdeer = tto55 ;
Math qdeer += deerstart ;
Math qdeer += 0x1C ;
For vcx = 1 To VertexNumber ;
GoTo qdeer 0 ;
Get Type4 Byte 0 ;
Get Type3 Byte 0 ;
Get Type2 Byte 0 ;
Get Type1 Byte 0 ;
Get Type8 Byte 0 ;
Get Type7 Byte 0 ;
Get Type6 Byte 0 ;
Get Type5 Byte 0 ;
Get Type12 Byte 0 ;
Get Type11 Byte 0 ;
Get Type10 Byte 0 ;
Get Type9 Byte 0 ;
GoTo 12 0 SEEK_CUR ;
SavePos qdeer 0 ;
GoTo Qer MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
Put 0 Byte MEMORY_FILE6 ;
SavePos Qer MEMORY_FILE6 ;
GoTo Qprime MEMORY_FILE2 ;
Put Type1 Byte MEMORY_FILE2 ;
Put Type2 Byte MEMORY_FILE2 ;
Put Type3 Byte MEMORY_FILE2 ;
Put Type4 Byte MEMORY_FILE2 ;
Put Type5 Byte MEMORY_FILE2 ;
Put Type6 Byte MEMORY_FILE2 ;
Put Type7 Byte MEMORY_FILE2 ;
Put Type8 Byte MEMORY_FILE2 ;
Put Type9 Byte MEMORY_FILE2 ;
Put Type10 Byte MEMORY_FILE2 ;
Put Type11 Byte MEMORY_FILE2 ;
Put Type12 Byte MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
Next vcx ;






Math vik = VertexNumber ;
Math vik -= 3 ;

For fff = 0 To vik ;

Math fafter = fff ;
Math fafter += 1 ;
Math fafterafter = fff ;
Math fafterafter += 2 ;
GoTo YFYF MEMORY_FILE3 ;
Put fff Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;

Put fff Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos YFYF MEMORY_FILE3 ;
Next fff ;













Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math facenumber = Zf3 ;
Math vertexnumber = Zf2 ;


Math lion = vertexnumber ;
Math lion *= 0x14 ;
Math liger = facenumber ;
Math liger *= 0xa ;
Math total3ds = lion ;
Math total3ds += liger ;
Math total3ds += 0x89 ;
Math total1 = total3ds ;
Math total1 -= 0x10 ;
Math total2 = total3ds ;
Math total2 -= 0x54 ;
Math total3 = total3ds ;
Math total3 -= 0x5E ;
Math vertexbase = 0x6c ;
Math WHEREvertex = vertexbase ;
Math tigervertex = vertexnumber ;
Math tigervertex *= 0xc ;
Math facebase1 = vertexbase ;
Math facebase1 += tigervertex ;
Math tigerface = facenumber ;
Math tigerface *= 0x8 ;
Math tigertigerface = facenumber ;
Math tigertigerface *= 0xa ;
Math facebase2 = facebase1 ;
Math facebase2 += 0x8 ;
Math WHEREface = facebase2 ;
Math facebase3 = facebase2 ;
Math facebase3 += tigerface ;
Math tigertigertigerface = facenumber ;
Math tigertigertigerface *= 0x2 ;
Math weretiger = tigertigerface ;
Math weretiger += 0x15 ;
Math tiger1 = tigervertex ;
Math tiger1 += 0x8 ;
Math tiger4 = tigertigertigerface ;
Math tiger4 += 0xd ;
Math WHEREfacecount = facebase3 ;
Math WHEREfacecount += 0xd ;
Math uvbase = WHEREfacecount ;
Math uvbase += tigertigertigerface ;
Math tigon = tigerface ;
Math tigon += 0x8 ;
Math WHEREuv = uvbase ;
Math WHEREuv += 0x8 ;
Math WHEREvertexq = WHEREvertex ;
Math WHEREuvq = WHEREuv ;
Math WHEREfaceq = WHEREface ;
Math WHEREfacecountq = WHEREfacecount ;
log MEMORY_FILE1 0 total3ds ;
Math vertexstart = 0 ;
Math facestart = 0 ;
Math uvstart = 0 ;


set M Byte 0x4d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x4d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xed ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0a ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x3d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x3d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xdd ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xaf ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x3e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0b ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x4e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x65 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x10 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x11 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x09 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x11 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x09 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xcc ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xcc ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xcc ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x30 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xa0 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x11 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x09 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0xff ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x99 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x69 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6x ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x8f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x22 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x01 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x10 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x9d ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x08 ;
Put M Byte MEMORY_FILE1 ;
GoTo 0x2 MEMORY_FILE1 ;
Put total3ds Long MEMORY_FILE1 ;
GoTo 0x12 MEMORY_FILE1 ;
Put total1 Long MEMORY_FILE1 ;
GoTo 0x56 MEMORY_FILE1 ;
Put total2 Long MEMORY_FILE1 ;
GoTo 0x60 MEMORY_FILE1 ;
Put total3 Long MEMORY_FILE1 ;
GoTo 0x66 MEMORY_FILE1 ;
Put tiger1 Long MEMORY_FILE1 ;
GoTo 0x6A MEMORY_FILE1 ;
Put vertexnumber Short MEMORY_FILE1 ;
GoTo facebase1 MEMORY_FILE1 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
Put weretiger Long MEMORY_FILE1 ;
Put facenumber Short MEMORY_FILE1 ;
GoTo facebase3 MEMORY_FILE1 ;
set M Byte 0x30 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
Put tiger4 Long MEMORY_FILE1 ;
set M Byte 0x4e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6f ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x6e ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x65 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x0 ;
Put M Byte MEMORY_FILE1 ;
Put facenumber Short MEMORY_FILE1 ;
GoTo uvbase MEMORY_FILE1 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE1 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE1 ;
Put tigon Long MEMORY_FILE1 ;
Put vertexnumber Short MEMORY_FILE1 ;
For vwolf = 1 To vertexnumber ;
GoTo vertexstart MEMORY_FILE2 ;
Get Type1 Long MEMORY_FILE2 ;
Get Type2 Long MEMORY_FILE2 ;
Get Type3 Long MEMORY_FILE2 ;
SavePos vertexstart MEMORY_FILE2 ;
GoTo WHEREvertexq MEMORY_FILE1 ;
Put Type1 Long MEMORY_FILE1 ;
Put Type2 Long MEMORY_FILE1 ;
Put Type3 Long MEMORY_FILE1 ;
SavePos WHEREvertexq MEMORY_FILE1 ;
Next vwolf ;
For fwolf = 1 To facenumber ;
GoTo facestart MEMORY_FILE3 ;
Get Type1 short MEMORY_FILE3 ;
Get Type2 short MEMORY_FILE3 ;
Get Type3 short MEMORY_FILE3 ;
Get Type4 short MEMORY_FILE3 ;
SavePos facestart MEMORY_FILE3 ;
GoTo WHEREfaceq MEMORY_FILE1 ;
Put Type1 short MEMORY_FILE1 ;
Put Type2 short MEMORY_FILE1 ;
Put Type3 short MEMORY_FILE1 ;
Put Type4 short MEMORY_FILE1 ;
SavePos WHEREfaceq MEMORY_FILE1 ;
Next fwolf ;
For uvwolf = 1 To vertexnumber ;
GoTo uvstart MEMORY_FILE6 ;
Get Type1 Long MEMORY_FILE6 ;
Get Type2 Long MEMORY_FILE6 ;
SavePos uvstart MEMORY_FILE6 ;
GoTo WHEREuvq MEMORY_FILE1 ;
Put Type1 Long MEMORY_FILE1 ;
Put Type2 Long MEMORY_FILE1 ;
SavePos WHEREuvq MEMORY_FILE1 ;
Next uvwolf ;
For fcwolf = 0 < facenumber ;
GoTo WHEREfacecountq MEMORY_FILE1 ;
Put fcwolf short MEMORY_FILE1 ;
SavePos WHEREfacecountq MEMORY_FILE1 ;
Next fcwolf ;
Get purpledragon ASIZE MEMORY_FILE1 ;
Get name FILENAME 0 ;
string name += . ;
string name += qmk ;
string name += .3ds ;
Log name 0 purpledragon MEMORY_FILE1 ;
Next qmk ;
```


here is the script for extract files WAD files:

```
Get max ASIZE 0 ;
GoTo 0 0 ;
SavePos start 0 ;
Do ;
GoTo start 0 ;
SavePos x 0 ;
Get d Long 0 ;
Get size Long 0 ;
Get name String 0 ;
GoTo start 0 ;
GoTo size 0 SEEK_CUR ;
GoTo 0x40 0 SEEK_CUR ;
Padding 0x10 ;
SavePos y 0 ;
Math start = y ;
Math y -= x ;
Log name x y 0 ;
While start < max ;
```


thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-21T11:39:34+00:00
- Post Title: God of War 3 Mesh fix

> Reply from luxox18
>
> this is the script for extract 3d meshes:to be honest: I never would waste my lifetime with trying to understand such horrible unstructured script. Even the indents are missing...
## Post #3
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2013-12-23T01:23:10+00:00
- Post Title: God of War 3 Mesh fix

I also just know about those 2 scripts some days ago, but i really hope someone can help us fix the scripts, i can even pay for them if they could do that. Getting the models in GOW 3 always a target that everyone have.
 Thanks if someone can help .
## Post #4
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2013-12-23T03:07:50+00:00
- Post Title: God of War 3 Mesh fix

Offer 40$ send via Paypal for someone can help complete those script and get the model/textures in the game.
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-23T09:50:53+00:00
- Post Title: God of War 3 Mesh fix

> Reply from shakotay2
>
> to be honest: I never would waste my lifetime with trying to understand such horrible unstructured script. Even the indents are missing...

LOL

What language is that anyway ?

T.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-23T11:33:53+00:00
- Post Title: God of War 3 Mesh fix

it's quickbms. Very good for archive extractions. But not best choice for model conversions.
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-23T12:18:36+00:00
- Post Title: God of War 3 Mesh fix

Oh, ok, so the last part (extracting the WAD file) is a good one 

T.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-23T12:40:32+00:00
- Post Title: God of War 3 Mesh fix

I would say so.  

As for the model extraction script: doesn't make sense to mess around with it, imho.
("mess around"= "try to improve it" - anyway you may use it to extract *.3ds files)

As i wrote in 2 or three answer PMs to some guys it would make more sense to just use the vertices without the weird faceindices and try to figure out the triangles manually.

But there was no reply.

Anyway here's an example of a harpy's claw fingers:
[](http://www.pic-upload.de/view-21711708/R_HARPY20.WAD.4.jpg.html)

iirc there was a resorting of face indices after reexporting the reduced mesh so I failed to fix them.
If I have some spare time I might give it another try.

If anyone could provide a simple model like a box, a chest, a book or something like that it might be easier.
(I tried R_BOX00.WAD but I couldn't find a box in it.)
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-23T12:42:05+00:00
- Post Title: God of War 3 Mesh fix

Btw, I used the last script to extract the content of the wad file, but the dds files are not really dds files, nothing I get to view correctly, and which is the 3D model file? since there are like 700 files.... :/

T.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-23T13:04:38+00:00
- Post Title: God of War 3 Mesh fix

try one of the big files (>100kB)

btw: I made a correction to my previous post. You may use the badly structured script to extract *.3ds files.
(I didn't mean it does not work, it's just hard to understand.)
## Post #11
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2013-12-23T13:47:12+00:00
- Post Title: God of War 3 Mesh fix

Someone please accept 40$ and help us ~,~
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-23T14:06:28+00:00
- Post Title: God of War 3 Mesh fix

> Reply from Yuredacy2311
>
> Someone please accept 40$ and help us ~,~Please stop offering money before this thread turns out to become another Girl hentai super blast thread.  

(Sooner or later someone will work out the correct face indices, I'm sure.)

edit: for the dds fake a DXT1 header (like I wrote here:[viewtopic.php?f=10&t=11041&p=90969#p90969](http://forum.xentax.com/viewtopic.php?f=10&t=11041&p=90969#p90969))
[](http://www.pic-upload.de/view-21712687/WAD_dds.jpg.html)



fake_dds.jpg (81.78 KiB) Viewed 89 times


(Some contain DXT5, so an DXT5 header will be required, of course.)
## Post #13
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2013-12-23T15:03:20+00:00
- Post Title: God of War 3 Mesh fix

> Reply from shakotay2
>
> I would say so.  

As for the model extraction script: doesn't make sense to mess around with it, imho.
("mess around"= "try to improve it" - anyway you may use it to extract *.3ds files)

As i wrote in 2 or three answer PMs to some guys it would make more sense to just use the vertices without the weird faceindices and try to figure out the triangles manually.

But there was no reply.

Anyway here's an example of a harpy's claw fingers:


iirc there was a resorting of face indices after reexporting the reduced mesh so I failed to fix them.
If I have some spare time I might give it another try.

If anyone could provide a simple model like a box, a chest, a book or something like that it might be easier.
(I tried R_BOX00.WAD but I couldn't find a box in it.)

I have to apologise with u   , unfortunately i'm ultra busy this period and i didn't have time work on fixed mesh.

The main problem is , in the process of fixing the mesh the vertexes count is changed from the orginal one...don't ask me why XD

Anyway i have an eye bulb mesh that i fixed "more manually" than the other parts , with the same vertex count of the original 3ds file.  I will send it soon if it could help you.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-23T17:06:17+00:00
- Post Title: God of War 3 Mesh fix

> Reply from Ares722
>
> I will send it soon if it could help you.Might help.   (Would need the original 3ds, too.)
## Post #15
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2013-12-30T07:59:37+00:00
- Post Title: God of War 3 Mesh fix

So no one out there can continue this work?
 Offer still there for whoever fix this problem ~,~
