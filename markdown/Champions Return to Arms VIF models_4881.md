## Post #1
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-13T23:14:53+00:00
- Post Title: Champions: Return to Arms VIF models

Champions Return to Arms, is a Playstation 2 game, developed by Snowblind Studios, and uses a similar engine to their Baldur's Gate: Dark Alliance, which also has "VIF" models.
Most VIF models all found in archive files called "LMP".
The VIF format is just what the games calls, PS2 2ByteSignedInteger formatted meshes with some differences, and is therefore found in many games like many Tony Hawk games, and Ratchet and Clank.
What I want to know is how the 2bytesigned vertexes, are connected to form faces, as there is no face index, and the meshes are not standard PS2 Tristrips. I call these meshes "69" meshes because in every PS2 game I have looked at that uses the 69 header, the vertexes do not work as in the picture below:

The vertex subsections in "69" games always begins with this:
........
04 00 80 XX 69
2ByteSignedVertexes(X,Y,Z)
(padding if odd number of vertexes XX)
XX 80 XX 6A
........
The raw file im_bodyv1.vif (Iksar Male Body Version 1:
[http://ps23dformat.wikispaces.com/file/ ... bodyv1.vif](http://ps23dformat.wikispaces.com/file/view/im_bodyv1.vif)
is found in the file SELECT.LMP (Character Selection Screen Data)
This game uses real Armor/clothing and textures that are attached to the base mesh
so the feathers and loin cloth in the picture below will not be on the same file I attach but the mesh
should look like it does in this picture:

The base mesh is 8044 vertexes.
Please help me solve the mystery of the "69"
by the way in other PS2 games:
XX 64=Standard PS2 Texture UV Coords
XX 68=Standard PS2 TriStrips Vertexes
XX 6C=PS2 Some Combination of (Vertexes, UV and Normals all Floats) 
XX 6D=PS2 Some Combination of (Vertexes, UV and Normals all SignedIntegers)
XX 74=PS2 Texture UV Coords for "78"
XX 78=PS2 TriStrips Vertexes (unlike 68, some culling must be done to show the faces correctly)
## Post #2
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-08-17T21:49:05+00:00
- Post Title: Champions: Return to Arms VIF models

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-18T00:49:51+00:00
- Post Title: Champions: Return to Arms VIF models

In the sample file the first 11(decimal) bytes are all zero which appears to be common for files in this game.
The next 5 (decimal) bytes are FC FF FF FF FF. I dont know what this means, I think I changed them
on the emulator and nothing happened.
We are now at offset 10 (hex):
The first 4 bytes are "05 00 1A FF". The only thing I can make out of this is that the "1A" is the
number of bone meshes ie each bone will effect only that bone mesh.
The next 12 (decimal) bytes are 00 00 00 00 01 00 00 00 00 00 00 00 again unknown in meaning.
We are now at offset 20 (hex)
The first 4 bytes are "00 00 1A 00" where the "1A" means the same thing as before.
Following these are "1C" different 4byte offsets:
The first offset does not follow the pattern and strangely ends in an odd number, maybe it points to
the place where the head mesh ends/begins as it is the only offset that is not in the small to large offset list.
The next "1A" offsets point to the "1A" different BoneMeshes, they begin at the first bone-mesh's first submesh's vertexes and contain 
several submeshes right in a row. The anm animation files almost surely reference the "1A" differnt bone-meshes
The last offset points to the place where the data in the vif file ends, but continues to be padded with zeros.
We are now at offset 94 (hex)
There is a 10(decimal) byte block for each of the "1A" section. I have not tried changing this its purpose is
unknown but atleast in this file the 8 byte in each block is 00
We are now at offset 198 (hex) this is information about where to attach weapons to the models.
The main idea is 4ByteID followed by 12 (decimal) floatingbyte numbers. These are the only Floating point integers
in any vif files, and there seems to be strange gaps of zero's between some sections possibly maybe because
Iksar (lizardmen) can not equip all types of armor/weapons that the human races can.
Now we are at offset 4E0.
This contains some information I think about shadows and/or Collison Detection
it uses 2ByteSigned integers but I am not sure how it works
Now we are at the beginning of the first bone-mesh which is at offset D80.
Each Bone-mesh contains severalsubmeshes which are in the following format (I am not 100% sure about the padding):
1ByteUnknownID 00 00 "04 00 80 VV 69" 2ByteSignedIntegers
(00 00 if VV=OddNumber otherwise nothing)
"VV 80 VV 6A"
3ByteSpecialIntegerNormalMappings(or textureUV???)
00 Padding???
"GG C0 (VV+SpecialPAD) 03"
UnknownDatasection of size 6*(VV+SpecialPAD)
"HH C0 01 6E 70 FF FF FF (HH+SpecialPAD2) C0 01 6D"
Padding
"(GG+SpecialPAD3) C0 01 6C JJ 80"
Padding??
"00 40 AE 30 13 04 00 00 00 00 00 00 42 00 00 14"
"03 01 00 01 81 C0 JJ 65"
4SpeicalByteTextureUV
"01 01 00 01"

I made a video of me editing textures in the emulator [http://www.youtube.com/watch?v=sYxR60S_xtM](http://www.youtube.com/watch?v=sYxR60S_xtM) I have also found ways to change the pointers so that any character can wear any other characters clothing even if the clothing/hair is normally race/gender specific.
## Post #4
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-08-19T01:48:03+00:00
- Post Title: Champions: Return to Arms VIF models

Alright... Umm... Ya... I followed that for a while then you lost me at well... I'm a programmer so I use 010 Editor's templates to figure out file formats. Here's what I got outta your post... well at least until i got lost  :

```
{
    byte Data[10];
};

byte Zeros[11];
byte Unknown1[5];
short Unknown2;
byte UnknownCount;
byte _FF;
byte Unknown4[12];
short Unknown5;
short BoneMeshes;
int UnknownOffset;
int Offsets[UnknownCount];
int EndOffset;
HeaderEntry Entries[UnknownCount]; // End up at offset 0x198
```


So I got the offsets and stuff, but you lost me at the floating bytes. A 4 byte ID is simple, thats a int. But floating byte? Is that 1, 2, 4 bytes? Idk. Anyways I hope you can understand my lil code there enough to add what you know to it so I can understand it  

EDIT: Oh and I'm using the single byte count for the number of offsets instead of the short that can be used because I have other VIF files that I extracted myself and that single byte is usually 1 when the short is zero and yet there is still a offset there so the single byte works in all cases that I tried.
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-19T14:06:42+00:00
- Post Title: Champions: Return to Arms VIF models

I ment that the attachment point data is this:
4ByteIntegerID, 4ByteFloat#1, 4ByteFloat#2....,. 4ByteFloat#12
So it is 52 byte arrays. In the sample file they begin at the following hex offsets:
1A0, 1D4, 208, and 2D8.
It is strange that there is none at 23C, 270, 2A4, or any until 4E0 when the shadow/collison detection meshes begin
## Post #6
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-08-19T20:13:07+00:00
- Post Title: Champions: Return to Arms VIF models

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-19T23:18:42+00:00
- Post Title: Champions: Return to Arms VIF models

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-08-22T06:53:21+00:00
- Post Title: Champions: Return to Arms VIF models

It would certainly be helpful to see you changing maybe the first 2 bytes and the the effect, then the next two and so on.

I'm sure there are some obsolete variables in the header or some that are just there for file info (compile date/time etc..). I can't find the ps2.sig file online (one site that has it is temporarily down) to use with IDA so I've hit a dead end with decompiling it since I can't tell when it reads from the disc or something. 

On a side note, any luck with .tex files? They obviously have the textures in them since they're 200kb-ish but do you think they might contain the UV data? One odd thing to note is that the v1.tex file is only about 6kb while the others are 200kb. Think it has some good stuff?

Oh I figured out the meaning of a few things in the header and the 10 bytes that are for each attachment (called HeaderData in the code) is actually 5 shorts (if you didn't already know that). Here's my current File structure, I've remade this like 4 times so its not all that complete 

Things with Data in the name are just useless information.

```
struct VectorShort { short X, Y ,Z; };
struct AttachmentInfo { int ID; float A[12]; };
struct BoneData 
{ 
    byte ID; 
    short Data1;
    short A; 
    byte B; 
    byte C; // Number of vectors (Tested mutliple character vif's, verified)
    byte D; 
    VectorShort Vectors[C];
    byte Data2[4 - (FTell() % 4)]; // Padding to the nearest 4 byte boundary
    byte E[4]; // C, 0x80, C, 0x6A

    // Not completed
};

// ------
// Start of the file format
// ------
byte Data1[8];
short A[2];
int Data2;
short B;
byte OCount; // Offset Count
byte Data3;
int Data4[3]; // Data4[1] equals 1 or in the case of hef_bodyv1.vif it's 9
short D[2]; // D[1] does not always equal OCount. hef_bodyv1.vif is an example.

int E;
int Offsets[OCount];
int F; // Size of the v2.tex file. The v1.tex file is usually really small (if there is one)

HeaderData HdData[OCount];
byte Data5[16 - (FTell() % 16)]; // Padding to the neared 16 byte boundary

AttachmentInfo AttchInfo[16]; // Size only is correct with im_bodyv1.vif and hem_bodyv1.vif need to know what its is dependent on, script works cause it jumps to the corrected offset ahead

FSeek(Offsets[0]); // Jump to the first offset which is 0xD80
BoneData Data;
```


How's that look so far? I'm using [010 Editor](http://www.sweetscape.com/010editor/) templates in-case you actually wanna use it
## Post #9
- Username: ibrown
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 23, 2011 10:08 pm
- Post datetime: 2011-11-23T14:19:33+00:00
- Post Title: Champions: Return to Arms VIF models

I've been looking at these model formats recently with mind to try and make a editor for the snow-blind engine games. That may or may not be possible, but the journey will hopefully be interesting.

The vif format is basically a collection of vif tags which upload data to the VU1 and then some microcode executes in order to generate tri-strips. The models are split into small chunks - each resulting in a single GIF tag. I've been playing around with the Dark Alliance data and have some java code which can unpack LMP files, convert (some) .tex files to .png and convert some .vif files to wavefront .obj files. It's research code at the moment rather than anything more useful ... but if you know java, feel free to play around with it ... or read it to find out the details of the formats some more. It is a work in progress and not yet finished.

You can find it here:

[http://code.google.com/p/bgda-explorer/](http://code.google.com/p/bgda-explorer/)

I use intellij IDEA as my IDE and there is a project file for that in the source. Paths etc are mainly hardcoded.

Ian
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-03-10T17:17:14+00:00
- Post Title: Champions: Return to Arms VIF models

> Reply from ibrown
>
> I've been looking at these model formats recently with mind to try and make a editor for the snow-blind engine games. That may or may not be possible, but the journey will hopefully be interesting.

The vif format is basically a collection of vif tags which upload data to the VU1 and then some microcode executes in order to generate tri-strips. The models are split into small chunks - each resulting in a single GIF tag. I've been playing around with the Dark Alliance data and have some java code which can unpack LMP files, convert (some) .tex files to .png and convert some .vif files to wavefront .obj files. It's research code at the moment rather than anything more useful ... but if you know java, feel free to play around with it ... or read it to find out the details of the formats some more. It is a work in progress and not yet finished.

You can find it here:

http://code.google.com/p/bgda-explorer/

I use intellij IDEA as my IDE and there is a project file for that in the source. Paths etc are mainly hardcoded.

Ian

Ibrown you do not know how helpful this will be. And yes I think this game will be on the easier said to edit. By playing around in PCSX2 I can for example change the character's texture armor and weapons to a different characters (even ones that the game would not allow you to wear) by switching the offset to a model/texture to a different offset.

Can you please describe (I'm not source code literate) how the vertexes with have the 68 header and are 2ByteSignedIntegers are formed to make the tristrips, as when I try to do it, it looks like the models have holes compared with other PS2 games, so what is the difference between the tristrips in this game, and other PS2 games? Does the Face generating algorithm involve some function of the distance to the next vertexes?
## Post #11
- Username: ibrown
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 23, 2011 10:08 pm
- Post datetime: 2012-03-10T22:28:14+00:00
- Post Title: Champions: Return to Arms VIF models

It's not easy to describe the format without parsing the VIF tags properly - but I will try and give you an idea.
The code to interpret the format is here:
[http://code.google.com/p/bgda-explorer/ ... Decoder.cs](http://code.google.com/p/bgda-explorer/source/browse/trunk/WorldExplorer/WorldExplorer/DataLoaders/VifDecoder.cs)
you should be able to follow it - if you can figure out the hex like you do, figuring out the c# code should be a walk in the park 

So, the vif file is a collection of VIF tags - in the game, it is just uploaded to VU1 memory and then a function is run in VU1 to deal with the format.

For each mesh section (I think what you call a bone mesh), there are a number of VIF sections. The first one defined the vertices, which you decode correctly. The second section following them defines the normals. Following that there is a third section which I call strip defs. Each def consists of 3 unsigned shorts. The first 2 entries are generally 3, 0, 3 so it is easy to recognise.
By parsing these strip defs you come to the tri-strips that define the list of faces - basically, it is a simple compression scheme.

The decompression code looks as follows (see around line 75 of the file referenced above)

```
                    int v = vlocIndx - 2;
                    int stripIdx2 = (chunk.vlocs[vlocIndx].v2 & 0x1FF) / regsPerVertex;
                    int stripIdx3 = (chunk.vlocs[vlocIndx].v3 & 0x1FF) / regsPerVertex;
                    if (stripIdx3 < vstrip.Length && stripIdx2 < vstrip.Length) {
                        vstrip[stripIdx3] = vstrip[stripIdx2] & 0x1FF;

                        bool skip2 = (chunk.vlocs[vlocIndx].v3 & 0x8000) == 0x8000;
                        if (skip2) {
                            vstrip[stripIdx3] |= 0x8000;
                        }
                    }
                    int stripIdx = (chunk.vlocs[vlocIndx].v1 & 0x1FF) / regsPerVertex;
                    bool skip = (chunk.vlocs[vlocIndx].v1 & 0x8000) == 0x8000;

                    if (v < numVerts && stripIdx < vstrip.Length) {
                        vstrip[stripIdx] = skip ? (v | 0x8000) : v;
                    }
                }

```


this builds up vstrip which is a list of vertices forming the trip strip. so, if it was 1, 2, 3, 4, 5 then we would have faces formed from vertices 1, 2, 3 then 3, 2, 4 then 4, 2, 5 etc.
One thing worth noting is that the indices are actually indices into the GIF tag - so you need to divide them by three (regsPerVertex in the code). 

For each entry in the strip defs, the first element (of the 3) gives the index into the vstrip - and you set that entry to the index in the strip def -2. Element 2 and 3 specify indices into vstrip - the entry pointed to by 3 is copied to that pointer to by 2. In all cases, the flag 0x8000 indicates whether the face should be drawn. If it is set on the 3rd vertex of a face, that face is not drawn.
That's a really complicated explanation of really quite a simple algo - read the code, it will make more sense 

Good Luck, 

Ian
## Post #12
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-04-28T23:32:44+00:00
- Post Title: Champions: Return to Arms VIF models

Guess what ibrown, it is easy to modify the game a little bit by doing the following:
Purchase an Action Replay Max/EVO.
This allows you to transfer game saves to a USB drive.
Then you can use the tool called "PS2 Save Builder" to extract the game save, and then edit it in cheat engine and then put it back to the format, and then back to your memory card.
For example I changed the following text:
natasla.lmp
natasla.vif
natasla.tex

into
warboar.lmp
warboar.vif
warboar.tex

Then when I loaded the save, the Natasla's model was changed into that of the warboar, also the texture was changed properly, and the animation seemed find looked stiff, but looked like an idle animation when I spoke to the npc.
PLUS
I think when you save in a level
you can change any creature into anything you want. 
I also see things in plain text like light1=79,33,58.....

Plus Action Replay Max works on an unmodified PS2, so it is totally legal.
## Post #13
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2012-09-17T17:40:22+00:00
- Post Title: Champions: Return to Arms VIF models

There has been some progress. I've started to work with ibrown on an editor. [LINK](http://code.google.com/p/bgda-explorer/source/list). It supports Baldur's Gate Dark Alliance 1 and we're currently improving support for Champions RTA. I've added support for LMP files and we're working on the .world. It loads .vif files fine (open a .gob, expand the tree and find a .vif entry, click on it and then go to the 3d view tab on the right) and even loads the animations if they're present.
## Post #14
- Username: JohnBarleycorn
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 30, 2015 12:42 am
- Post datetime: 2015-05-29T16:53:15+00:00
- Post Title: Champions: Return to Arms VIF models

> Reply from FurryFan
>
> Guess what ibrown, it is easy to modify the game a little bit by doing the following:
Purchase an Action Replay Max/EVO.
This allows you to transfer game saves to a USB drive.
Then you can use the tool called "PS2 Save Builder" to extract the game save, and then edit it in cheat engine and then put it back to the format, and then back to your memory card.
For example I changed the following text:
natasla.lmp
natasla.vif
natasla.tex

into
warboar.lmp
warboar.vif
warboar.tex

Then when I loaded the save, the Natasla's model was changed into that of the warboar, also the texture was changed properly, and the animation seemed find looked stiff, but looked like an idle animation when I spoke to the npc.
PLUS
I think when you save in a level
you can change any creature into anything you want. 
I also see things in plain text like light1=79,33,58.....

Plus Action Replay Max works on an unmodified PS2, so it is totally legal.

You know, this is EXACTLY what i was trying to do, since.. Since the first time i've player with those games. Precisely i was trying to do that on Dark Alliance 2. I tried to follow what you said here, but i really don't understand how you edit (and especially how do you find) the line you mentioned early. Could you explain me a little better how you do the edit with the cheatengine?
## Post #15
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-05-29T17:48:32+00:00
- Post Title: Champions: Return to Arms VIF models

> Reply from NicotineCaffeine
>
> FurryFan wrote:Guess what ibrown, it is easy to modify the game a little bit by doing the following:
Purchase an Action Replay Max/EVO.
This allows you to transfer game saves to a USB drive.
Then you can use the tool called "PS2 Save Builder" to extract the game save, and then edit it in cheat engine and then put it back to the format, and then back to your memory card.
For example I changed the following text:
natasla.lmp
natasla.vif
natasla.tex

into
warboar.lmp
warboar.vif
warboar.tex

Then when I loaded the save, the Natasla's model was changed into that of the warboar, also the texture was changed properly, and the animation seemed find looked stiff, but looked like an idle animation when I spoke to the npc.
PLUS
I think when you save in a level
you can change any creature into anything you want. 
I also see things in plain text like light1=79,33,58.....

Plus Action Replay Max works on an unmodified PS2, so it is totally legal.

You know, this is EXACTLY what i was trying to do, since.. Since the first time i've player with those games. Precisely i was trying to do that on Dark Alliance 2. I tried to follow what you said here, but i really don't understand how you edit (and especially how do you find) the line you mentioned early. Could you explain me a little better how you do the edit with the cheatengine?
Did you transfer your save game onto your computer using the action reply max? How about you send the save to me, so I can tell you what to edit in cheat engine.
## Post #16
- Username: JohnBarleycorn
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 30, 2015 12:42 am
- Post datetime: 2015-06-01T23:43:25+00:00
- Post Title: Re: Champions: Return to Arms VIF models

Uh... Not exactly the data from the action replay, let's say that i've extracted the data from the fake memory card of the pcsx2.. But i guess inside, when i extract it and save as max in the end is the same, right?
## Post #17
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-06-04T17:05:36+00:00
- Post Title: Re: Champions: Return to Arms VIF models

> Reply from NicotineCaffeine
>
> Uh... Not exactly the data from the action replay, let's say that i've extracted the data from the fake memory card of the pcsx2.. But i guess inside, when i extract it and save as max in the end is the same, right?
Yes that is fine. Use this tool:
[http://www.csclub.uwaterloo.ca:11068/mymc/](http://www.csclub.uwaterloo.ca:11068/mymc/)
## Post #18
- Username: JohnBarleycorn
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 30, 2015 12:42 am
- Post datetime: 2015-06-05T09:54:48+00:00
- Post Title: Re: Champions: Return to Arms VIF models

Yes, that's it! I've used that program to create the file. But on using cheat engine i got totally lost xD
To be honest i'm not even able to follow the tutorial of cheatengine :S
## Post #19
- Username: JohnBarleycorn
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 30, 2015 12:42 am
- Post datetime: 2015-06-21T04:09:01+00:00
- Post Title: Re: Champions: Return to Arms VIF models

Hey, are you still there? Look, i've tried to swap the models directly from the files and then rewriting the iso. It doesn't work. So, since the way you proposed it appears to be the only one working, if you can at least tell me what i have to do once opened the savedata with cheatengine, i would be VERY grateful.
P.s. Or if you want that i send to you directly the savedata tell me where to send and i will do
## Post #20
- Username: LegendOfAB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 15, 2019 11:44 pm
- Post datetime: 2020-10-14T05:27:12+00:00
- Post Title: Re: Champions: Return to Arms VIF models

> Reply from FurryFan ↑Wed Aug 18, 2010 8:49 am at Wed Aug 18, 2010 8:49 am
>
> 
I made a video of me editing textures in the emulator http://www.youtube.com/watch?v=sYxR60S_xtM I have also found ways to change the pointers so that any character can wear any other characters clothing even if the clothing/hair is normally race/gender specific.

We're on the edge of greatness, FurryFan. I would massively appreciate knowing the method to change those pointers, assuming the explanation isn't too much trouble for you (especially after all these years)! I'm assuming cheatengine is involved?
