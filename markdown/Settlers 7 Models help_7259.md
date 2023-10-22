## Post #1
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2011-08-29T19:08:59+00:00
- Post Title: Settlers 7 Models help

I've succesfully extracted the S7 models   (lol)
but i'm lost on importing 'em 
they seems more like an xml file than a real meshes file so i'm here asking for help

help  
[Clerics.zip](https://xentaxbackup.github.io/file/4673_Clerics.zip)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-29T19:50:51+00:00
- Post Title: Settlers 7 Models help

Yes, the xml file is indeed extensible markup language. It is just defining materials; not too special.

Format doesn't look too bad. Only took a quick glance though. Although I say it doesn't look too bad, chances of figuring it out 100% and re-importing, can't say.

There seems to be some chunk tags, but didn't verify. Probably not a chunk-based format; they just decided to throw in random tags and random stuff after it.

The outline looks like this:

```
textures

vertices section
another vertices section
more vertex related

faces (bunch of indices)
Bones

```


Some of them have the tag, some of them don't. The tag appears after an integer, and I see VST0, VST1, and VST2. Maybe it just indicates what type of vertex information you're looking at.

Might code something up later to see if my guesses are accurate.
Or maybe someone that's looking for practice can get around to it.

Now, what did you use to extract them?
## Post #3
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2011-08-29T21:35:43+00:00
- Post Title: Settlers 7 Models help

s7bbaex which coming from [here](http://uploaded.to/file/ojl92q) (should be 1.1 but i'm not sure)
written by TheMachine

I've been at your conclusion too, maybe it's just so easy, and it's a 3D ascii file (maybe a directX file), but i'm not so good hex file reading/converting, that's why i'm looking for some ninja which are good to extract the correct vertex/face index.. after that, i think someone can made an importer shouldn't be a problem... maybe with 3dsmax script
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-29T22:02:07+00:00
- Post Title: Settlers 7 Models help

No lol it's not ascii nor is it directx.
It's just less confusing than the more complicated formats.

Post more samples of varying sizes, from small ones to slightly larger ones.
I can't tell much from the same file (although there are 4, it's basically the same thing)
## Post #5
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2011-08-30T11:37:19+00:00
- Post Title: Settlers 7 Models help

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: anujraghav
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 14, 2010 6:28 pm
- Post datetime: 2012-08-08T05:45:01+00:00
- Post Title: Settlers 7 Models help

so any news on it  , is there anyway to  modify  them , or  use  custom made  models
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-08T11:56:31+00:00
- Post Title: Settlers 7 Models help

Can't seem to download s7bbaex.

Can anyone help.

I dl the file, checking it right now

T.
## Post #8
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2012-08-08T14:37:54+00:00
- Post Title: Settlers 7 Models help

Settler 7 uses the Vision Engine ([http://en.wikipedia.org/wiki/Vision_%28game_engine%29](http://en.wikipedia.org/wiki/Vision_%28game_engine%29)) as you can se there, "Orc Must Die!" uses this engine too.

so perhapse the model import script for noesis works also with the settler 7 models?
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-08T19:01:20+00:00
- Post Title: Settlers 7 Models help

> Reply from delium
>
> Settler 7 uses the Vision Engine (http://en.wikipedia.org/wiki/Vision_%28game_engine%29) as you can se there, "Orc Must Die!" uses this engine too.

so perhapse the model import script for noesis works also with the settler 7 models?

Naa, already tried that :/

T.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-08T19:03:57+00:00
- Post Title: Settlers 7 Models help

I couldn't figure it out with just one model sample. Three were included in the folder but they're just LOD's and basically the same thing.
## Post #11
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-12T08:37:29+00:00
- Post Title: Settlers 7 Models help

> Reply from finale00
>
> I couldn't figure it out with just one model sample. Three were included in the folder but they're just LOD's and basically the same thing.

I'm interested in a .s7m to obj/3ds-Converter. I've upload 4 more models for you.
1 Unit, 1 Animal, 2 Buildings- if you need more models, let me know.

[models.rar](http://www.file-upload.net/download-4673647/models.rar.html) (Download-Button is the small one in the center of the page)
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-12T10:01:13+00:00
- Post Title: Settlers 7 Models help

I have the settlers 7, so could you upload the s7bbaex extracter so i can do the extraction of the bba file myself. Thnx

T.
## Post #13
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-12T21:02:48+00:00
- Post Title: Settlers 7 Models help

Char[4] -> S7MF
UInt32 -> Version Minor
UInt32 -> Major Version

Pos 52 -> Length of the names -2

Pos 65 -> start of the names of the maps, textures and the name of the object devided by \0

Don't seem to find the offset of VST0, VST1 and VST2

The UInt32 just in front of VST is always 24
and the number befor that is (I think) a UInt32 that contains the number of vertices..

Weird... could it be compressed ???

in the list there are a lot of NaN ( Not A Number) ???


T.
## Post #14
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-12T21:06:53+00:00
- Post Title: Settlers 7 Models help

> Reply from TaylorMouse
>
> I have the settlers 7, so could you upload the s7bbaex extracter so i can do the extraction of the bba file myself. Thnx

T.

Download: [s7bbaex.rar](http://www.file-upload.net/download-4666071/s7bbaex.rar.html)
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-12T22:30:40+00:00
- Post Title: Settlers 7 Models help

> Reply from TaylorMouse
>
> Char[4] -> S7MF
UInt32 -> Version Minor
UInt32 -> Major Version

Pos 52 -> Length of the names -2

Pos 65 -> start of the names of the maps, textures and the name of the object devided by \0

Don't seem to find the offset of VST0, VST1 and VST2

The UInt32 just in front of VST is always 24
and the number befor that is (I think) a UInt32 that contains the number of vertices..

Weird... could it be compressed ???

in the list there are a lot of NaN ( Not A Number) ???


T.

I think it is a chunk-based format, where each chunk is 16-byte aligned.
I think it should be parsed sequentially, remembering to pad the end of each chunk appropriately.

First you start by reading in the texture names, then you read the VST0, then VST1, maybe VST2, followed by a bunch of indices.

```
int chunksize
int structsize
char[4] chunktag

```


For example, consider M_MF_Musketeer_01.s7m. At offset 224, you read two shorts. Then the chunk size 26808. The struct size is 24, and the chunk ID is VST0

Then you read 26808 bytes, followed by some padding. Note that in the header at offset 12 you get the vert count 1117, and that * 24 = 26808.

Then you read another two shorts, followed by 4468 chunk size, a 4 for struct size, then VST1. 

Read in 4468 bytes, then you see more 0 padding to the next 16 bytes. Again, vert count of 1117 * 4 = 4468. 

Repeat for VST2. 8936 / 8 = 1117.

Afterwards, there's a chunk with no ID (1st short is a 1), but if we follow the pattern and pad the chunk, we'll come to the next chunk (1st short is a 4), which doesn't have a chunk ID either but you can see that it follows the same chunk struct and this one holds a bunch of indices.

7206 chunk size for faces, short per index, and 7206 / 2 = 3603, which is the integer right after the vert count, so there's your index count.

It might be using half-floats to store a lot of data, I don't know.

The fact that a couple structs aren't following the chunk struct might mean they just hardcode it as TexNames, VST0, VST1, VST2, unk, faces

EDIT:

Ok ya it's a chunk-based format.
The 4-char tag is not really important.
The first short is the chunk type:

1 - VST0
2 - VST1
3 - VST2
4 - faces
5 - that VBIN chunk, skeleton or whatever "Shadow" could refer to
6 - textures
7 - small chunk, not sure

16-byte aligned

```
    ''' 16-byte chunk alignment'''
    
    pad = (16 - (size % 16)) % 16
    self.inFile.seek(pad, 1)
    
def parse_file(self):
    '''Main parser method'''
    
    idstring = self.inFile.readBytes(4)
    unk, unk, numVerts, numIdx = self.inFile.read('4L')
    self.inFile.read('2H')
    self.inFile.read('6f')
    
    # chunk based parsing
    while not self.inFile.checkEOF():
        chunkType, unk = self.inFile.read('2H')
        chunkSize = self.inFile.readUInt()
        structSize = self.inFile.readUInt()
        chunkID = noeStrFromBytes(self.inFile.readBytes(4))
        
        if chunkID == 1:
            self.parse_VST0(structSize)
        elif chunkID == 2:
            self.parse_VST1(structSize)
        elif chunkID == 3:
            self.parse_VST2(structSize)
        elif chunkID == 4:
            self.parse_faces(numIdx)
        else:
            self.inFile.seek(chunkSize, 1)
        self.seek_padding(chunkSize)
        print(chunkType, chunkSize, chunkID)

```
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T10:35:00+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from Sammie
>
> TaylorMouse wrote:I have the settlers 7, so could you upload the s7bbaex extracter so i can do the extraction of the bba file myself. Thnx

T.

Download: s7bbaex.rar

Thnx
T.
## Post #17
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-13T11:47:21+00:00
- Post Title: Re: Settlers 7 Models help

@finale00
Sounds complicated  i wish i could understand this stuff  
so is it possible to build a s7m->obj converter?
## Post #18
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T11:51:11+00:00
- Post Title: Re: Settlers 7 Models help

what does the 
read('4L') mean ?

T.
## Post #19
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-13T12:33:47+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> what does the 
read('4L') mean ?

T.

4L= Unsigned Long Integer (Standardsize = 4)
2H = Unsigned Short Integer (Standardsize = 2)

Standardsize is the size of the packed value in bytes
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T15:44:55+00:00
- Post Title: Re: Settlers 7 Models help

```

try
{
using(System.IO.BinaryReader r = new System.IO.BinaryReader(System.IO.File.Open(file, FileMode.Open, FileAccess.Read)))
{
	char[] chars = r.ReadChars(4);
	
	Debug.WriteLine(chars[0].ToString() + chars[1].ToString() + chars[2].ToString() + chars[3].ToString() );
		
	Debug.WriteLine(String.Format("Minor Version {0}", r.ReadUInt32()));
	Debug.WriteLine(String.Format("Major Version {0}", r.ReadUInt32()));
	int nVerts = (int)r.ReadUInt32();
	Debug.WriteLine(String.Format("Number Verts {0}",nVerts ));
	Debug.WriteLine(String.Format("Number Indexes {0}", r.ReadUInt32()));

 	for (int i = 0; i < 8; i++)
	{
		r.ReadUInt32();
	}
	
	int len = (int)r.ReadUInt32();
	len = len - (len%16) + 16; // 16 byte chunks
	Debug.WriteLine(String.Format("Texture Names Length {0}", len));
	
	r.ReadUInt32();
	r.ReadUInt32();
	
	char[] textures = r.ReadChars(len);
	
	string tmp = "";
	for	(int i = 0; i < len; i++)
	{ tmp += textures[i].ToString(); }
	
	string[] texNames = tmp.Split('\0');
	for(int i = 0; i < texNames.Length; i++)
	{
		if( texNames[i].Length > 0)
		Debug.WriteLine(texNames[i]);
	}
	
	int chunkType = (int) r.ReadUInt16();
	int chunkSize = (int)r.ReadUInt16();
	int structSize = (int)r.ReadUInt32();

	Debug.WriteLine(String.Format("Chunk Type {0}", chunkType ));
	Debug.WriteLine(String.Format("Chunk Size {0}", chunkSize  ));
	Debug.WriteLine(String.Format("Struct Size {0}", structSize ));	

	Debug.WriteLine(String.Format("This must be 24 => {0}", r.ReadUInt32() ));	
	
	char[] chunkName = r.ReadChars(4);
	
	Debug.WriteLine(chunkName[0].ToString() + chunkName[1].ToString() + chunkName[2].ToString() + chunkName[3].ToString() );

	for(int i = 0; i < nVerts; i++)
	{
		Debug.WriteLine(String.Format("[{0},{1},{2}] uv [{3},{4}]" ,  r.ReadSingle(),r.ReadSingle(),r.ReadSingle(),r.ReadSingle(),r.ReadSingle() ));
		 r.ReadSingle();
	}
	
	
	r.Close();

}
}
catch(Exception ex)
{
	Debug.WriteLine(ex);
}


```


```
Minor Version 1
Major Version 1
Number Verts 461
Number Indexes 1656
Texture Names Length 112
A_Sheep_A_Sheep_Shorn
Textures\Animals\A_Sheep_01_Shorn_D.dds
Models\Animals\A_Sheep\A_Sheep_Shorn_01.s7m
Chunk Type 1
Chunk Size 1383
Struct Size 11064
This must be 24 => 24
VST0
[5.652521E+08,2.943147E-41,0.0001288966] uv [1.642716E-38,-6.431651E+37]
[5.631549E+08,2.943147E-41,6.159579E-05] uv [1.642734E-38,-6.431651E+37]
[1.186988E+09,2.895503E-41,0.0001603965] uv [1.120339E-38,-6.431651E+37]
[2.074171E+09,2.928854E-41,0.0002157032] uv [1.198274E-38,NaN]


```


I think I'm on the right track, but then I run into a NaN... :/  any idea?

T.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-13T17:52:33+00:00
- Post Title: Re: Settlers 7 Models help

btw, it is

```
int unk = r.ReadUInt16();
int chunkSize = (int)r.ReadUInt32();
int structSize = (int)r.ReadUInt32();

```


If you see e+41, you know there's something wrong lol
## Post #22
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T19:01:34+00:00
- Post Title: Re: Settlers 7 Models help

mmm.. ok 

```
                    int unk = (int)r.ReadUInt16();
                    int chunkSize = (int)r.ReadUInt32();
                    int structSize = (int)r.ReadUInt32();
                    char[] chunkName = r.ReadChars(4);

```


I already figured that out... thnx

Then I tried to read the chunk part ( at least I try to parse it)

but it has stuff like

```
FF FF FF FF
```


and that, results in NaN :/

So if you have any idea...


T.
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-13T19:06:54+00:00
- Post Title: Re: Settlers 7 Models help

It could just be an integer -1.
## Post #24
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T20:43:21+00:00
- Post Title: Re: Settlers 7 Models help

Sorry... what?

```
FF FF FF FF
```


equals -1 as a signed Int or a signed Byte, but what do I do with it?

If I build it up like

v1,v2,v3,uv1,uv2 

the uv2, mostly ends up in -1, but is that an ok uv value?

T.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-13T20:45:37+00:00
- Post Title: Re: Settlers 7 Models help

Don't know, probably ignore it and look at the other values. I don't know what they're for. I don't really even have an idea how the VST chunks are supposed to look like. All we know is that they store vertex information, but why there is VST1 with 4-bytes per struct and VST2 with 8-bytes per struct is unknown.
## Post #26
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T21:00:53+00:00
- Post Title: Re: Settlers 7 Models help

Yeah, the numbers seem to add up, just not the chunks...

VST0 ->24  I assume 5 floats + 1 Signed Int ( could be if this is the w coordinate), being the xyz of the vertex, then the uvw of the vertex, but when I read them, they result in something weird like:


v[7.383575E-38,5.123147E-42,5.605194E-45] uvw[3.089743E-09,3935990,5]
v[971787.4,500305.2,342601.9] uvw[2980.65,9363.131,5]
v[0.01895693,0.01895693,0.05817918] uvw[9363.131,-5001.346,5]
v[-1.46332E+07,-1.46332E+07,-301668.3] uvw[-5001.346,0.01895693,5]
v[-301668.3,-301668.3,0.05817918] uvw[0.01895693,9363.131,5]
v[500305.2,500305.2,2980.65] uvw[9363.131,-24357.89,5]
v[-301610.5,189772.8,14740.71] uvw[8532.812,0.2564926,5]
v[212298.7,8564.812,14772.71] uvw[190284.8,207694.3,5]
v[185165.1,112550.2,14772.71] uvw[8564.812,277041.9,5]
v[1389705,1930855,139553.2] uvw[180506.2,492048.1,5]
v[811605.4,1389715,947213.9] uvw[828412.9,30628.46,5]
v[-0.4927383,1572864,5283178] uvw[3919609,2903857,5]
v[2660.574,17316.54,7077888] uvw[4365644,3247874,5]
v[1894346,255245.3,24868.12] uvw[5308416,3735552,5]
v[1041434,1010183,2056192] uvw[-16.53608,-180516.7,5]
v[-0.8916748,0.009964556,3.875] uvw[-55.07215,-453192.3,5]
v[-2593206,-202752,-41541.79] uvw[-52.56723,-6.31767E+07,5]
v[-1036288,-413696,0.001602173] uvw[2548.573,17316.54,5]
v[72337.03,-0.4927383,-180516.7] uvw[-55.07215,-453192.3,5]
v[-2593206,-6.31767E+07,161050.3] uvw[453136.2,0.009964556,5]
v[-9937.269,-202752,-1036288] uvw[-1.625293E+07,3.875,5]
v[-52.56723,-41541.79,-413696] uvw[811612,877591.9,5]
v[281137.9,161050.3,140577.2] uvw[1826816,1389705,5]

...
and so on, 
but the red numbers, are so weird :/

T.
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-13T21:51:01+00:00
- Post Title: Re: Settlers 7 Models help

Here I quickly printed out the VST chunk as half-floats and got this

```
   Halffloat[3] vx, vy, vz
   byte[18] ?
}

```



I'll look into VST1 and VST2 later. I don't think there are normals or UV's in VST0 though.
If anything I would think the other values to be related to bone indices and weights. I mean, there really isn't anywhere else you'd put them...
## Post #28
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-13T22:23:36+00:00
- Post Title: Re: Settlers 7 Models help

Damn, I was so close...

I don't seem to have a Half Precision Floating point in c#... :/


T.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-13T22:55:14+00:00
- Post Title: Re: Settlers 7 Models help

lol I wish they had half-floats in 010 editor's inspector.

Not tested, but it was recommended on SO

[http://sourceforge.net/projects/csharp-half/](http://sourceforge.net/projects/csharp-half/)

I think you just need to pass in a short and it'll convert it to half-float.

You can roll your own binary reader so that you can say ReadHalfFloat or something, but 
You might have your own binary reader already since BinaryReader doesn't support reading in big endian natively.
## Post #30
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-14T02:33:18+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> the uv2, mostly ends up in -1, but is that an ok uv value?

VST0 ->24 I assume 5 floats + 1 Signed Int ( could be if this is the w coordinate), being the xyz of the vertex, then the uvw of the vertex, but when I read them, they result in something weird like

Yes, UVs can have positve and negatives values.. The UV-Space has a default 0-1 range (the upper right), but if the gameengine supports UV-repeating or if the mesh have multiple UVs or the UVs are just bad, then they can have -1 or +2,3,4... - in X or Y. I saw it in old settler-games where many UVs are in 1|1 or -1|0 space. Its allowed. 



The VST0-chunksize is 24. If you read 6 floatchunks á 4 bytes you get the XYZ + UV-XY Coordinates + 1 extra chunk. There is no "W" - UVs are flat 2D. 3D-Textures exists, but not in games like this. The 6th chunk is something else...

The VST-Blocks have a chunkType (UInt16), a dataSize (UInt16), a chunkSize(UInt32), a structSize(UInt32) and chunkName(Char4)
finale00 figured out the most things. The dataSize*8 is equal or lower than the chunkSize. If the dataSize is lower, you have to add the difference + 8 Bytes after the chunkSize until the next block.

Example @ M_MF_Musketeer_01.s7m:
chunkType: 1
dataSize: 3351 (26808)
chunkSize: 26808
structSize: 24
chunkName: VST0
# skip 8+0 bytes
#000069b0

chunkType: 2
dataSize: 558 (4464)
chunkSize: 4468
structSize: 4
chunkName: VST1
# skip 8+4 bytes
#00007b40

chunkType: 3
dataSize: 1117 (8936)
chunkSize: 8936
structSize: 8
chunkName: VST2
# skip 8+0 bytes
#00009e40

I think the stuff behind is not really relevant for us. Seems to be the faces/triangle-count in chunktype 4 and other bones and shader data behind.

> Reply from finale00
>
> 
I'll look into VST1 and VST2 later. I don't think there are normals or UV's in VST0 though.
If anything I would think the other values to be related to bone indices and weights. I mean, there really isn't anywhere else you'd put them...
Hmm, I think the normals und specular maps sharing the same UVs from VST0. 
But the size in VST1 (1/6 from VST0) and VST2 (1/3 from VST0) is strange. 
Too regular for bones. And buildings don't have any weights. I don't know if we need them.
Could you upload your converter?
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T03:00:03+00:00
- Post Title: Re: Settlers 7 Models help

The chunks are 16-byte aligned.
Just add 

```

```


as the padding.

I'm not sure what the second short is in the chunk header really. You wrote data size, but sometimes it is drastically different from the chunk size.

Noesis plugin: [https://www.dropbox.com/sh/7stlpd4qvkq3 ... rs7_s7m.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/Rj4ubJJwMF/fmt_Settlers7_s7m.py)

I really have no clue what the rest of the data might be.
The VST1 chunk has half-floats greater than 1.0, so I assume those can't be UV's
VST2 chunk also has half-floats greater than 1.0.
## Post #32
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-14T08:55:32+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> The chunks are 16-byte aligned.
I'm not sure what the second short is in the chunk header really. You wrote data size, but sometimes it is drastically different from the chunk size.
Hm, I thought the dataSize multiplied by 8 is the relevant datalength for the chunk-block. If the result differ from the chunkSize I see only additional "0"-Bytes at the end, which I have to add to the regular 8 byte-padding until the next chunkblock. But okay, I don't really understand this stuff. 


thx for the plugin. Hm, the Noesis export model looks okay. but the UVs are definitively wrong (or not exported?). All UV-texture data is set to 0.0.

If you say "greater" - how much greater? If the value is a float beween -1 and +2 it could be normal. You can also store UV-data at 10000, but thats extremely unlikely.
Its common for 3d artists to store the UV-data around the default 0|1 Space +/-1. In some old settler games, the UVs were in 0|2 space. If the gameengine supports UV-repeating, it doesn't matter in what UV Space the UVs are.

Edit:
VST1 second and last value per chunk is a specific number (converted to decimal). Dont think that this are float-values.
130 58 89 51
61 59 64 51
58 59 218 50
58 59 218 50
130 58 89 51
156 58 44 52
232 59 91 54
230 59 174 53
210 59 191 53
137 59 244 58
184 59 96 59
184 59 96 59
137 59 244 58
137 59 244 58
239 59 57 59 

VST2 seems to have only 2 Values per Vertex. Looks strange to me. Too many repeating values, definitely no UVs.
FF 00 00 00 
0A 00 00 00 
FF 00 00 00 
0B 00 00 00 
FF 00 00 00 
0A 06 00 00 
7F 7F 00 00 
0A 08 00 00
## Post #33
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T12:02:34+00:00
- Post Title: Re: Settlers 7 Models help

I decided to give up to try it in c# and see what I can do with the .py scripts


What tool do you guys use to test/debug etc the .py script before you test it in Noesis?

T.
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T17:56:32+00:00
- Post Title: Re: Settlers 7 Models help

Wing IDE for python syntax errors

I use noesis' debug console for testing/debugging lol

You could always use C++ if you're into that. I couldn't go from C# to C++ though.
## Post #35
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T18:40:31+00:00
- Post Title: Re: Settlers 7 Models help

in VST0, the chunk is 24, and only 6 bytes are being used, in our code,

6 bytes being 3 * half floats ( 2 bytes per float )

what about the other 18 bytes?

they aren't vertex weights, cause there does not seem to be any reference to any bones here...

could it be normals ? also half floats
could it be uvw ? also half floats

Just thinking out load 

btw : checking out Wing IDE 101 right now

T.
## Post #36
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-14T19:59:28+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> could it be normals ? also half floats
could it be uvw ? also half floats

Yes, for the UVs add to the Phyton-code:

```
rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_HALFFLOAT, 24, 8)
```
## Post #37
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T20:03:03+00:00
- Post Title: Re: Settlers 7 Models help

Oh, so they're stored in VST0.
How does the resulting model look?
## Post #38
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-14T20:15:20+00:00
- Post Title: Re: Settlers 7 Models help

Looks okay.. if I export the model as obj, and load it in Maya, I have to rotate the model -90° in X-axis and the UVs should be flipped vertically to match with the diffuse-textures.
Maybe you can add this in your plugin.

But its necessary to find out which textures are used. If the model use more than one texture (e.g the buildings), I dont know which polygon should have a specific texture. I think this data is stored in VST1.
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T21:13:28+00:00
- Post Title: Re: Settlers 7 Models help

There is an xml file that defines material info. But the ones I have only seem to use one texture so I don't know how they deal with multiple materials.
## Post #40
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-14T21:32:02+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> There is an xml file that defines material info. But the ones I have only seem to use one texture so I don't know how they deal with multiple materials.

Look at [my post](http://forum.xentax.com/viewtopic.php?p=76984#p76984) - there is an tavern-building in the downloadfile, with wall, windows and roof textures. The xml is just an info about light, shadow, ambient and displacementsettings for the gameengine, but the info which polygon uses a specific texture must be inside the .s7m-file. The texturenames are defined behind the verts and Idx-count. At Offset 00000038 is the length of the texture-string until the VST0-chunk starts.
## Post #41
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T21:36:54+00:00
- Post Title: Re: Settlers 7 Models help

I did the same, imported into Max, indeed the uv mappings need to be flipped horizontally, didn't need to rotate it since you can tell in the importer to do so

Smoothing groups suck :/

here is a little render on a Cavalier:



iz nize no   

Texture name can be found in the ChunkType = 6

it also contains the name of the material file , which ends with _mat and has the .xml extension
there it has this:

```
    <TextureEdge>
     <BlockVersion name="TextureEdge" version="1"/>
     <Usage>Diffuse</Usage>
     <Dimension>2D</Dimension>
     <TextureData>
      <BlockVersion name="TextureData" version="1"/>
      <Name>Textures\Units\M_MT_Cavalier_d.dds</Name>
     </TextureData>
    </TextureEdge>
   </Textures>

```


_d for diffuse but the mipmaps are split into 3 different levels

M_MT_Cavalier_d_l1.dds
M_MT_Cavalier_d_l2.dds
M_MT_Cavalier_d_l3.dds -> contains the  highest mipmaps

I think this is done so that the loading of the textures is speed up in game

ps: sorry sammie didn't see your post, was busy making mine  


T.
## Post #42
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-14T21:54:34+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> indeed the uv mappings need to be flipped horizontally
really horizontally in Max? I need to flip them vertically in Maya.
## Post #43
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T22:13:24+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from Sammie
>
> TaylorMouse wrote:indeed the uv mappings need to be flipped horizontally
really horizontally in Max? I need to flip them vertically in Maya.

My bad, my bad, it is of course VERTICALLY   

T.
## Post #44
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-15T01:37:03+00:00
- Post Title: Re: Settlers 7 Models help

I don't see how you would separate the vertex buffer into the correct meshes..

Maybe they decided to store it as such

<mesh1> <mesh2> ... <mesh n>

But then it's not really obviously when one mesh ends and the next one begins.
## Post #45
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-15T10:29:45+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> I don't see how you would separate the vertex buffer into the correct meshes..

Maybe they decided to store it as such

<mesh1> <mesh2> ... <mesh n>

But then it's not really obviously when one mesh ends and the next one begins.

I don't think there is more than one mesh-object per .s7m-file. All vertices & faces are combined together to one mesh for the gameengine. The whole thing has one pivot point.
Some buildings have additional s7m files for goods (crates, barrels..) around the building or other decals, but they are combined too.

So it should be possible to make a rotation around the x-axis with a transform-matrix and flip the UVs, too. If I flip the UVs via the option in Noesis they flipped to 0|-1 space, but that doesn't matter when importing it to Maya or Max. But would be better if the UVs stay within 0|1 space. Some buildings have UVs outside the 0|1 space like the bakery, they use UV-repeating.
## Post #46
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-15T17:11:25+00:00
- Post Title: Re: Settlers 7 Models help

I can't think of how they might be referencing the materials.

For example, in some formats you have a bunch of different meshes and each mesh gets a material.
Other formats have a single mesh, but each face has a material index.

There doesn't seem to be an obvious way how to determine, for example in the tavern, which vertices/faces correspond to the roof and which correspond to the door.

The texture names and the order they appear might be a clue, but then looking around I was hoping to find some sort of index that that matches the number of textures.

btw, if the UV's are in 0|2 space how do I map them to 0|1 space? Just divide everything by 2?
Is the lower-bound always a 0? Can it be -1|1 space? Or n|m space for arbitrary integers n and m?
## Post #47
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-15T20:14:39+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> I can't think of how they might be referencing the materials.

For example, in some formats you have a bunch of different meshes and each mesh gets a material.
Other formats have a single mesh, but each face has a material index.

There doesn't seem to be an obvious way how to determine, for example in the tavern, which vertices/faces correspond to the roof and which correspond to the door.

The texture names and the order they appear might be a clue, but then looking around I was hoping to find some sort of index that that matches the number of textures.
I think every face has a material index. We only have to figured out, how they have stored the data in the file 

> Reply from finale00
>
> 
btw, if the UV's are in 0|2 space how do I map them to 0|1 space? Just divide everything by 2?
Is the lower-bound always a 0? Can it be -1|1 space? Or n|m space for arbitrary integers n and m?
They use repeating-UVs.. its standard in every gameengine or 3D program. The texture you see in 0|1 is the same as in 0|-1 or -2|5 or 10|10 (even if you don't see any texture in the other UV spaces). Every UV space use the same texture, so it doesn't matter where the UVs are.

Of course you can disable the repeating UVs in your 3D programm and put individual textures in the seperate UV-spaces. 3D-Shooter-Games made this normally for characters. You can put the UV for the body in 0|1 and for the head in 0|2. If both UV spaces use a 512x512 texture, the head has more pixeldetails, because same pixelspace but less surface than the body. [See here](http://www.neilblevins.com/cg_education/multiple_uv_tiles/multiple_uvs_tiles.htm). But games like settlers don't use this feature.

Btw.. the numeration has no standard - 3D Studio Max, Maya, Mari, ZBrush and other programs use different startnumbers when creating UVs. Some start at 0|0 other at 0|1. Some count from left to right on multiple UVs, other from the bottom upwards. Its often confusing if you use multiple UVs in different programs.
## Post #48
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-16T15:31:13+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> I don't seem to have a Half Precision Floating point in c#... :/
Look @ this tiny function: [http://www.criticalsecurity.net/index.p ... ntry233825](http://www.criticalsecurity.net/index.php/topic/41444-how-to-convert-fromto-mini-floats16bit/page__p__233825&#entry233825)

@finale00
I have print out the chunks in a table. You see x,y,z as halffloats, 2 junkbytes and uv x/y as halffloat. The data behind (displayed as Hex) is unknown. Seems to be two blocks á 3 bytes. Some values of U1 matching always the X value. If U1 = 7FA706, then X = 64.1875. If U1 = DCD685 then X = 65.9375. But no idea what this is good for. U2 and U4 is unknown, too. Any idea?

Musketeer


Building
## Post #49
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-16T16:28:16+00:00
- Post Title: Re: Settlers 7 Models help

@sammy
Hey, thanks man

I think I will make an extension method for the BinaryReader class in C# so you can get it by doing this :

```

reader.ReadHalf();
or 
reader.ReadFloat16();

```


btw the tabmle you printed out, does it come from a object that has more than 1 texture?

Edit: ( paste it in a new .cs file)

```

namespace System.IO
{
    public static class ExtensionMethods
    {
        /// <summary>
        /// Read a Half Precision Point Float and advance the reader by 2 bytes.
        /// </summary>
        /// <returns>Returns a full precision point float </returns>
        public static float ReadHalf(this BinaryReader binaryReader)
        {
            UInt16 u = binaryReader.ReadUInt16();
            int sign = (u >> 15) & 0x00000001;
            int exp = (u >> 10) & 0x0000001F;
            int mant = u & 0x000003FF;

            exp = exp + (127 - 15);
            
            int i = (sign << 31) | (exp << 23) | (mant << 13);
            byte[] buff = BitConverter.GetBytes(i);
            
            return BitConverter.ToSingle(buff, 0);
        }

        /// <summary>
        /// Convert a precisioin point float to a half precision Point
        /// </summary>
        /// <returns>Returns a half precision point of 2 bytes in the form of a UInt16</returns>
        public UInt16 ToHalf(this float f)
        {
            byte[] bytes = BitConverter.GetBytes((double)f);
            ulong bits = BitConverter.ToUInt64(bytes, 0);
            ulong exponent = bits & 0x7ff0000000000000L;
            ulong mantissa = bits & 0x000fffffffffffffL;
            ulong sign = bits & 0x8000000000000000L;
            int placement = (int)((exponent >> 52) - 1023);
            if (placement > 15 || placement < -14)
                return ToHalf(-1.0f); //Whatever counts as error

            UInt16 exponentBits = (UInt16)((15 + placement) << 10);
            UInt16 mantissaBits = (UInt16)(mantissa >> 42);
            UInt16 signBits = (UInt16)(sign >> 48);
            return (UInt16)(exponentBits | mantissaBits | signBits);
        
        }
    
    }
}

```


T.
## Post #50
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-16T16:38:03+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> 
btw the tabmle you printed out, does it come from a object that has more than 1 texture?
Nope, its the musketeer. I have add another table for a multitexture-building. Only more FFs at the end
## Post #51
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-16T16:43:20+00:00
- Post Title: Re: Settlers 7 Models help

mmmm....

there  is no other value for the J value anywhere in the Building table??

T.
## Post #52
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-16T16:52:51+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from TaylorMouse
>
> mmmm....

there  is no other value for the J value anywhere in the Building table??

T.
No. just a junkbyte. Always 00.

Thats another table from VST1. Musketeer left, Building right. Can't see something special. Every 2nd and 4th column has a specific value (displayed as decimal & hex) (57,58,59,60),(3A,3B,3C), but can't figured out what this is good for. Nothing of this looks like a material-id or something. VST2 is uninteresting.. usually only FF, 00 alternatingly - sometimes another value.


Btw: The 2-Byte Value at offset 00000014 is the total number of textures (01 for the musketeer, 04 for the noble residence building). I'm sure the 28 unkown bytes in the middle are relevant for the textures, but I can't figure out how to read them.

Thats my current fileheader-info:

```
$fileHeader = $file->readChars(4);					// Fileheader
$majorVersion = $file->readUInt32LE();				// Major Version
$minorVersion = $file->readUInt32LE();				// Minor Version
$nVerts = $file->readUInt32LE();						// Number of Vertices 
$nIndexes = $file->readUInt32LE();					// Number of Indexes
$nTextures = $file->readUInt16LE();					// Number of Textures
$lTextures = $file->readUInt16LE();					// Number of Chars for Textures
$unknown = $file->read(28); 							// Unknown bytes
$lTexturesTotal = $file->readUInt32LE();			// Number of Chars for Textures + Filename
$empty = $file->read(8);								// 0-Bytes Padding
# End of chunk
# offset 00000040
$chunkSize = $lTexturesTotal - ($lTexturesTotal%16) + 16;
$lFilename = (int)$lTexturesTotal - $lTextures;

$textures = $file->readChars($lTextures);				// Texture-Infos splited by 0-Bytes
$filename = $file->readChars($lFilename);				// Path to .s7m File
$file->read(($chunkSize-$lTexturesTotal)%16);			// 0-Bytes Padding to fill the chunk
# Start of VST0

```
## Post #53
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-17T01:14:24+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> 
1 - VST0
2 - VST1
3 - VST2
4 - faces
5 - that VBIN chunk, skeleton or whatever "Shadow" could refer to
6 - textures
7 - small chunk, not sure

16-byte aligned
Hm, I never saw a chunkType #6. But i found out, chunkType 7 is between 3 and 4. His size varied and depend on the numbers of diffuse-textures. If the model has only one texture the chunksize is 32 bytes. if the model has 3 textures the chunksize has 64 bytes, and with 4 textures 80 bytes. So it could be relevant. Hint: if you add the last both values (e.g. the tavern f1 0e & 55 5f = UInt 28230 / cannon  b2 0b & d8 00 = Uint 3210) - its same value as the Indexes of the model. Maybe the single values are the numbers how many polygons have a specific texture.

I have parsed some models as HTML-Tables (open in a browser - takes a few seconds to load  ), so you can better look at the data-structure.
[Download](http://uploading.com/files/get/8bdd294m/models_parsed.rar)
## Post #54
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T05:40:47+00:00
- Post Title: Re: Settlers 7 Models help

6 is at the top where the texture names are.

Btw good find.
## Post #55
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-17T11:59:53+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> 6 is at the top where the texture names are.

Btw good find.
Ahh.. damn.. I have parsed this header-part manually, 'cuz it has a fix size.   
But I still can't see any informationen about which polygon has a specific texture.
Have you take a look at my parsed html-Files?
## Post #56
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T17:23:08+00:00
- Post Title: Re: Settlers 7 Models help

No. Can you upload it to google docs or something since it's an html file?
## Post #57
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-17T19:48:35+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> No. Can you upload it to google docs or something since it's an html file?

Why? The files are to big to load them via internet. Just download the .rar and look this html-files on your local system. Every browser can load local files.

Btw chunkType 7 describes how to read chunkType 6

Texture-Data from chunkType6:
B_NobleResidence_01_Windows Textures\Buildings\G_Windows_02_D.dds Textures\Buildings\G_Windows_02_N.dds Textures\Buildings\G_Windows_02_M.dds Textures\Buildings\G_Windows_Backdrop01_D.dds
B_NobleResidence_01_FabricRoof Textures\Buildings\G_Fabric_Roof_01_D.dds Textures\Buildings\G_Fabric_Roof_01_N.dds Textures\Buildings\G_Fabric_Roof_01_M.dds 
B_NobleResidence_01_building Textures\Buildings\B_NobleResidence_D.dds Textures\Buildings\B_NobleResidence_N.dds Textures\Buildings\B_NobleResidence_M.dds
B_NobleResidence_01_ShingleRoof Textures\Buildings\G_Shingle_Roof_02_D.dds Textures\Buildings\G_Shingle_Roof_02_N.dds Textures\Buildings\G_Shingle_Roof_02_M.dds

Data from chunkType 7:
01 00 1d 00 43 00 69 00 8f 00 00 00 69 00 00 00 00 00 00 00  
bd 00 dc 00 06 01 30 01 00 00 00 00 3c 00 00 00 69 00 00 00  
5a 01 77 01 a1 01 cb 01 00 00 00 00 a6 47 00 00 a5 00 00 00  
f5 01 15 02 40 02 6b 02 00 00 00 00 9b 01 00 00 4b 48 00 00

Translated to numbers (model with 4 textures)
1 29 67 105 143 => 105 & 0
189 220 261 304 => 60 & 105
346 375 417 459 => 18342 & 165
501 533 576 619 => 411 & 18407

The first 4/5 Numbers are byte-offsets to jump to every texture name (name, diffuse, normal, material, backdrop). The first number behind must be the number of polygons with this texture. The second number is the summary of the polygons above - so the summary of the last line must be equivalent to the total numbers of polygons. But still no material-ids here.
## Post #58
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T20:57:42+00:00
- Post Title: Re: Settlers 7 Models help

lol sorry maybe I got you thinking too much about material indices.
You actually already found the answer.

Chunk 7 is composed of a sequence of "mesh info" structs, each totaling 20 bytes in size. So the Tavern example has chunksize of 60, so that's 3 meshes.

It describes what kinds of material is used on a mesh, and which indices form that mesh.
The name offsets are relative to the start of the texture chunk (well, it includes matName as well and something else I think it's the mesh name).

```
   short matNameOfs
   short diffName ofs
   short normal_name_ofs
   short matte_name_ofs ?
   short backdrop_name_ofs 
   short another_ofs
   int32 numIdx
   int32 idxStart
}

```


Material index is not needed in this case.
So like if matName = "blah", idxStart = 0 and numIdx = 30, that means the faces formed by indices 0 to 30 use "blah".

I have updated the noesis script with your findings.



Also, if you look closer at the texture chunk, you'll notice that the very last filename is actually the path of the current model. Not really sure what it's for, but there's probably some reference to it somewhere.

So I might call chunk 6 the "names chunk" since it just has a bunch of paths that could be anything.

btw, I imagine a building can have bones and weights. Maybe the doors and windows can open or close.

And the textures are "mirrored" in my previews, forcing you to rotate the model. Why is it stored like that?
## Post #59
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-17T23:41:48+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> lol sorry maybe I got you thinking too much about material indices.
You actually already found the answer.

Chunk 7 is composed of a sequence of "mesh info" structs, each totaling 20 bytes in size. So the Tavern example has chunksize of 60, so that's 3 meshes.

It describes what kinds of material is used on a mesh, and which indices form that mesh.
The name offsets are relative to the start of the texture chunk (well, it includes matName as well and something else I think it's the mesh name).

Material index is not needed in this case.
So like if matName = "blah", idxStart = 0 and numIdx = 30, that means the faces formed by indices 0 to 30 use "blah".

I have updated the noesis script with your findings.
Oh   I'm glad that I'm the only one, who can't see the wood for the trees.  
I've tried your script but can't see any textures in Noesis. What do I wrong?
filename.s7m
Textures/Buildings/*.dds

> Reply from finale00
>
> 
Also, if you look closer at the texture chunk, you'll notice that the very last filename is actually the path of the current model. Not really sure what it's for, but there's probably some reference to it somewhere.
Don't think, its relevant for us. It's just filepath to the .s7m-file after unpacking the .bba-archive.

> Reply from finale00
>
> btw, I imagine a building can have bones and weights. Maybe the doors and windows can open or close.
Yes, thats correct. In older settlers-games the doors can be opened too and bones were used.

> Reply from finale00
>
> And the textures are "mirrored" in my previews, forcing you to rotate the model. Why is it stored like that?
I don't know. But I saw this in many games before. Normally I flip the UVs vertically instead of mirroring the building.
## Post #60
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T23:59:38+00:00
- Post Title: Re: Settlers 7 Models help

I don't know sometimes I just cross my fingers and hope noesis finds the textures >_>
Try putting them in the same folder.
## Post #61
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2012-08-18T00:27:37+00:00
- Post Title: Re: Settlers 7 Models help

> Reply from finale00
>
> I don't know sometimes I just cross my fingers and hope noesis finds the textures >_>
Try putting them in the same folder.
Okay, same folder works. Thx!  

In addition I've add a transform-matrix to your script to rotate the model in the right direction.

```
							  NoeVec3((0, 0, 1)),
							  NoeVec3((0, -1, 0)),
							  NoeVec3((0, 0, 0))))
            rapi.rpgSetTransform(trans)  
```
## Post #62
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2013-03-23T13:56:58+00:00
- Post Title: Re: Settlers 7 Models help

Blender249 - Settlers 7 models(.s7m) and animation(.anim) importer.
Link for blend file and example:
[http://www.mediafire.com/?bknby17x7fcwea0](http://www.mediafire.com/?bknby17x7fcwea0)
## Post #63
- Username: xuxo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 30, 2012 4:17 am
- Post datetime: 2015-11-23T16:51:30+00:00
- Post Title: Re: Settlers 7 Models help

amazing Szkaradek123!! How did you imported to Blender? Animated models need !!! : D
