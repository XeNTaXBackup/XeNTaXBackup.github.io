## Post #1
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-07-04T03:32:26+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

Hello. I would like to ask if it is possible to extract somehow the "Goh Hinogami" model from Virtua Fighter 4.
I managed to find all the files that involve this character (the ones that I think at least).

I really wonder if it's possible to combine all the needed files so it can be an usable model file (for 3ds max, milkshape e.t.c.). I want the model in T-pose but that's in the lowest priority since I first want the model (in any pose) .

So here are they are (about 3MB).:
[http://www.mediafire.com/?mmjqm1yci44](http://www.mediafire.com/?mmjqm1yci44)

I 'm completaly inexperianced with coding/decoding but I think that one file of those (.MRG_GZ) uses gzip compression!

[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=CH_JDKMRG_GZ.png)
I also found some extensions that is proof that those files include models or textures (or even animations).:
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=JD2_FACE_01MRG.png)

Any kind of help would be appreciated... For real.
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-07T01:22:10+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

I think your right about the Gzip compression, though I could not get it to work with a gzip library that I used. As for the files that are not compressed, I think they are tristrips. Each model is stored in chunks:
4ByteFloat(X,Y,Z) 00 00 FF FF
4ByteFloatNormalMapping 4ByteFloatWeight (usually 1.0 ie "00 00 80 3f")
4ByteFloatTextureMapping 4ByteFloatWeight#1 4ByteFloat#2 (Both usually "00 00 80 4F")

I'll work on this more tomorrow.
## Post #3
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-07-07T18:26:12+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

> Reply from FurryFan
>
> I think your right about the Gzip compression, though I could not get it to work with a gzip library that I used. As for the files that are not compressed, I think they are tristrips. Each model is stored in chunks:
4ByteFloat(X,Y,Z) 00 00 FF FF
4ByteFloatNormalMapping 4ByteFloatWeight (usually 1.0 ie "00 00 80 3f")
4ByteFloatTextureMapping 4ByteFloatWeight#1 4ByteFloat#2 (Both usually "00 00 80 4F")

I'll work on this more tomorrow.

Sounds great! 
I really appreciate that you are interested/
For your information though, it's supposed to be the same model, but with different versions (clothes, attachments e.t.c.).

Some artwork to get an idea on how the model should be:

Here, Goh wears the judo uniform and this is exactly the model that I want.
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=GohVF4E.jpg)

You may also find the model like this:
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=GohPortraitVF4E-2.jpg)
OR(less likely cause he wears the hood):
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=goh-evol.jpg)

Notice that you may find small model parts or different colours! Try to find the correct ones like in the #1st screenshot of artwork.
Thanks
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-07T18:49:22+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

Something tells me that these may not be tristrips per se, but here are some vertexes from one of those small files:


Maybe this is part of his hood?
## Post #5
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-07-07T19:44:46+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

> Reply from FurryFan
>
> Something tells me that these may not be tristrips per se, but here are some vertexes from one of those small files:


Maybe this is part of his hood?

Hmm it actually can be anything! It's very unclear!
What is the name of the file?

EDIT: 
I just read some of your [posts](http://forum.xentax.com/viewtopic.php?f=16&t=2897) and I saw that you are familiar with PCSX2 (not sure though).
Please tell me if I can do anything with PCSX2.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-08T12:32:56+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

Glad you asked, if you can get this game working with PCX2, version .94 [http://www.generalemu.net/pcsx2archive/ ... /index.htm](http://www.generalemu.net/pcsx2archive/archive/pcsx2_v0.9.4/index.htm) then you can send me a save state. It has to be version .94 though.
## Post #7
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-07-08T15:48:02+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

> Reply from FurryFan
>
> Glad you asked, if you can get this game working with PCX2, version .94 http://www.generalemu.net/pcsx2archive/ ... /index.htm then you can send me a save state. It has to be version .94 though.

Hey, here you go: 
[http://www.mediafire.com/?d3dhnamzdqj](http://www.mediafire.com/?d3dhnamzdqj)

However, I dislike PCSX2 0.9.4 because it's slow and buggy. The emulation showed a buggy overlay on the half of the window, I really hope that it won't corrupt the file.

EDIT: This save state was taken from the EDIT menu which shows the model that I want. (like in the #1 artwork.)
## Post #8
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-23T23:29:31+00:00
- Post Title: Model from Virtua Fighter 4 Evolution (PS2), *.MRG, *.MRG_GZ

I'm still looking at this game heres what I found so far:
In Memory the model is loaded several times, but only one instance controls the visuals.
Most of the model is located between offsets:
base+01A78250 and base+01AA5F00
The model is stored as sections with about 1 body part per section:
4BytePointers(#1-#5)
4ByteFloatWeights (#1-#8)
Unknown4Bytes
4ByteFloatWeight#9
00 00 00 00
4byteID???
Unknown22byte
2Byte#Subsections:(Unknown2Byte+ 4ByteFloatWeight+FF FF FF FF 00 00 00 00 FF FF FF FF
00 00 00 00 FF FF FF FF 00 00 00 00)......

If you change the weights you can make giant ears and noses and such but it is more complicated than a simple X Y Z scale modifier.
