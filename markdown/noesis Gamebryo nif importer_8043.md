## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T06:05:41+00:00
- Post Title: noesis Gamebryo nif importer

nif files always seemed amusing cause it's just a bunch of chunks ordered in some tree structure with nodes all over the place.

Documentation is available on niftools, so why not.

The file structure for later formats is convenient because you can quickly just skip everything that you don't need (which is usually the case cause we probably don't care about half the things in there), and if you suddenly needed something you can just throw in a parser function for it.

Earlier formats looks like it'll have to be parsed each struct at a time cause the node sizes in the header were introduced in 20.2.0.7...

Most of the games I have that use the nif format is archived away ATM so the only samples I have to work with are from [West & East fantasy](http://event.goorm.com/eventPage/we/event_20090721/) which is supported by nifskope (eg: can compare with what it loads)

Currently parses the geometry only. No textures (cause I have to do some image parsing...and I'm not really building a node tree so I haven't thought about how I the material will be assigned.

[http://xtsukihime.webs.com/Noesis%20Plu ... ryo_nif.py](http://xtsukihime.webs.com/Noesis%20Plugins/fmt_Gamebryo_nif.py)

It seems like it would be easier to just write separate plugins for each version, rather than a single plugin for all versions, cause that would require some actual planning on how to write the code without making too much of a mess.

For anyone that's having a hard time following the docs, you basically need to parse each chunk one at a time.

First you start with the header: [http://niftools.sourceforge.net/doc/nif/Header.html](http://niftools.sourceforge.net/doc/nif/Header.html)
If you're working with anything after 20.2.0.7, it is eas(ier) because you can skip stuff by seeking offsets (ie: minimal coding)

Otherwise, you're going to end up going back to the [index](http://niftools.sourceforge.net/doc/nif/index.html), searching for the object you want, and then following it. You can load it in nifskope and follow it in block view to make it easier.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-01-13T21:40:29+00:00
- Post Title: noesis Gamebryo nif importer

Is a good cause, as the conversion process at current for nif models is a bit awkward to say the least. My primary interest is getting SMT Imagine demon models.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T21:54:16+00:00
- Post Title: noesis Gamebryo nif importer

What kind of importers do they have right now anyways?
It looks like they've stopped supporting their 3dmax and blender plugins, and nifskope only exports geometry.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-13T22:09:08+00:00
- Post Title: noesis Gamebryo nif importer

Isn't nifskope that one project that's says it's 600,000 lines of code and worth several millions of dollars lol?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-14T00:44:31+00:00
- Post Title: noesis Gamebryo nif importer

lol ya they have a gif on their page. 4 devs, 322k+ lines, $4.6 million
It's definitely one of the more interesting game modding tools, kind of like the one that works with the unreal engine.

It looks like there's no documentation for some of the structs that appeared in games like RO2, catherine, or microvolts. Referred to the microvolts blender script for it, but the vertices are still a little odd.

The more I write, the more the file gets bloated.

Anyways I've done some minor edits to add the NiDataStream### objects, but am not getting the vertices right (particularly skinned models like monsters).

But some of the stuff comes out. This is one of the tutorial maps for RO2. Looks like static meshes are fine.
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-01-14T13:25:18+00:00
- Post Title: noesis Gamebryo nif importer

nice going, I am eagerly hoping that you will crack this. Alot of the new nif games are really nice looking but seems nif-forum only look at skyrim now
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-21T19:26:35+00:00
- Post Title: noesis Gamebryo nif importer

There isn't much to crack.

Most of the newer formats don't really add anything new (lots of NiDataBlock018, 118, 124, ...) but other than that, the docs on niftools should be sufficient.

I'm not putting too much time towards this atm cause of issues like papers and projects and stuff, but the script so far is somewhat flexible (just write a function for a chunk and add the case under parse_nodes(). It might get done eventually.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T04:53:38+00:00
- Post Title: noesis Gamebryo nif importer

Need a way to structure the files.

Basically, we know that gamebryo has a whole slew of formats from their first engine to what...30.whatever now?
Each version basically introduced new stuff, removed old stuff, or changed existing stuff.

The docs on niftools explains what was available in what version, since what version, and until what version.

Without using anything fancy like their XML file, how should I be organizing the plugins?
I don't want to cram everything into one big nif plugin, as trying to look for anything is pretty hard. Debugging would also be hard.

I want to use inheritance properly.
I can write separate plugins for each format, but since they share a lot of stuff, it'd probably easier to just push everything up to a parent class and only write whatever I need for the new format.

Put the stuff in a package? Just have a bunch of plugins lying around?
Looking for ideas.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T02:28:02+00:00
- Post Title: noesis Gamebryo nif importer

I've been looking at 20.6.0.0 using the catherine blender import for reference.

The vert data is stored in NiDataStream018, but it is rather weird.

It indicates the size of the vertex by "building" a bunch of pieces of together.

So for example, you might read in an integer count of 6, followed by 6 integers that provides the size of the vertex data but it's not obvious *what* it might be.

If you read "197687" that means there's another 12 bytes in your vertex struct.
But that could be vertex coords...or vertex normals. Or something else.

And it doesn't always appear in the same order either.

Sometimes it'll piece it together like

```
4 bytes
12 bytes
12 bytes
4 bytes
8 bytes

```


Other times it'll piece it together like

```
12 bytes
4 bytes
8 bytes

```


It's not like every vertex buffer has the same data in a single model either. You could have one mesh with 48 byte vertices and another mesh with 32 byte vertices.

Maybe there's another struct that determines the order that they appear in, but I don't know which one it might be cause there are so many chunks. 

When I write out the chunks, it might narrow down where the data is stored though.
## Post #10
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-02-23T19:08:39+00:00
- Post Title: noesis Gamebryo nif importer

Yeah I guess there is a reason why nifskope has taken some time to make the update
## Post #11
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-02T06:00:45+00:00
- Post Title: noesis Gamebryo nif importer

Not sure if this is any help.
In 30.0.0.2 the vertex data is stored in NiDataStream 1 18 , along with the normals, UVs and such.
The NiDataStream 0 18 contains the triangle data.
All three of the NiDataStreams i've found, 0 18, 1 18 and 3 3, all follow the same basic format.

```
00000000
01000000
00000000
E6010000 - 486     <----- number of elements in data
01000000
3704     - 1079   <---- ????
0300                 <---- ????
+ 5832 bytes data
+ terminator byte (usually 01)

```
 

The references to what each node is, is referenced in the NiMesh.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T06:47:46+00:00
- Post Title: noesis Gamebryo nif importer

Oh, nice find.

> NiMesh 495541
>
> NiTexturingProperty 495774
>
> NiSourceTexture 495814
>
> NiDataStream018 495850
>
> NiDataStream118 497763
>
> NiDataStream33 508464
>
> NiSkinningMeshModifier 508509
>
> NiMesh 509159
>
> NiTexturingProperty 509414
>
> NiSourceTexture 509463
>
> NiSourceTexture 509499
>
> NiMaterialProperty 509535
>
> NiDataStream018 509603
>
> NiDataStream118 522720
>
> NiDataStream33 619117
>
> NiSkinningMeshModifier 619442

Here's some sample output containing chunk names and offsets that I used.

Cutting out some of those niMesh chunks, I quickly noticed that near the end of the chunk, it gives you a count followed by some more odd integers.

The count is the same as the number of vertex data, so I can probably figure out what these odd integers mean and then just use a dictionary or something when I'm binding my buffers to bind the correct data...

This can't be a coincidence. Or maybe it is.
On the left is portion from NiMesh. The right is the portion from NiDataStream118



I should be able to quickly narrow it down by finding the ones that have like 12 bytes per vertex.

Looking at some of the values even more, it looks like there is some sort of chunk numbering going on (the first integer of the chunk. Only applies to Nodes and Meshes it seems)

You can see some others integers increasing in count by 1 after every few bytes. Top left example shows 0x0268, 0x0269, 0x026A. I don't know what they actually mean though.

Maybe they keep track of the number of groups of data as well...
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T07:56:37+00:00
- Post Title: noesis Gamebryo nif importer

NiMesh is annoying.
ya...

Here's how I parsed it

```
		
		for i in range(count):
				chunkNum = self.inFile.readUInt()
				self.inFile.readByte()
				count2 = self.inFile.readUInt()
				self.inFile.read("%dH" %(count2 - 1))
				count3 = self.inFile.readUInt()
				for j in range(count3):
						self.inFile.read('2L')

def parse_NiMesh(self):
		
		nodeNum = self.inFile.readUInt()
		self.inFile.read("2L")
		self.inFile.readUInt()
		self.inFile.readUShort()
		self.inFile.read('12f')
		count = self.inFile.readUInt()
		self.inFile.read('%dL' %count)
		self.inFile.read('5l') #-1 0 -1 0 ?
		self.inFile.read('4f')
		count2 = self.inFile.readUInt()
		self.parse_NiMesh_part(count2)

```


And that's just getting the general structure.

In the helper function, the very last two lines is what is interesting.
One of the iterations will run into the case where the number of parts is equal to the number of vertex parts. Unfortunately there is no real way to determine when that would arise, or whether it actually has anything to do with it.
## Post #14
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-02T18:30:31+00:00
- Post Title: noesis Gamebryo nif importer

Yep, it's going to be annoying having that many formats, wouldn't have thought they would rewrite the structures too much, not unless they rewrite the graphics engine.
Anyway, here's a quick look at a NiMesh from 30.0.0.2 
(from criticals red blood samples - chevalier_arm_00_m.nif)
(125 nodes, 120 names)

```
07000000 
65000000 66000000 67000000 68000000 69000000 6A000000 6B000000 

FFFFFFFF 
1600
00000000 00000000 00000000 0000803F
00000000 00000000 00000000 0000803F
00000000 00000000 00000000 0000803F
0000803F

03000000 
72000000 6D000000 6C000000
FFFFFFFF

01000000
6E000000

FFFFFFFF
00000000
00000000
00010000
75E98640 
E6C4AF3E 
C97E1541 
4E107E3E

09000000
 node id                                      name id
73000000 00 01000000 01000000    6F000000 00000000 - INDEX     -triangles
74000000 00 01000000 01000000    70000000 00000000 - TEXCOORD
75000000 00 01000000 01000000    71000000 00000000 - POSITION_BP    - x,y,z
76000000 00 01000000 01000000    72000000 00000000 - NORMAL_BP
77000000 00 01000000 01000000    73000000 00000000 - BLENDINDICES
78000000 00 01000000 01000000    74000000 00000000 
79000000 00 01000000 01000000    75000000 00000000
7A000000 00 01000000 01000000    76000000 00000000 
7B000000 00 01000000 01000000    77000000 00000000 

01000000 
7C000000            

```


The data and structure is unimportant at this point, it's the references that seem to matter more.
Think it's going to be important to list both the node list and name list complete with their index value to sort it out.
You can clearly see, the Nimesh is like a build list of parts, it even references the textures.
Not seen it reference the bones yet, think these are part of the NiNode system which starts with the scene root.
So NiMesh must be part of a NiNode ?? and the Nodes are part of a scene tree??
Got the vertices(POSITION_BP) into noesis for models with 1 object, models with more than one object just load the 1st object, which is why i'm looking at NiMesh for a solution.

Any chance of uploading or pointing to the file your working on for comparison?
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T18:37:25+00:00
- Post Title: noesis Gamebryo nif importer

I realize that while there are many formats, I haven't set up the file to be as flexible as it should for the future.
So now it just hardcodes a bunch of versions that I looked at. Maybe in the future I will just create one large file and have other versions inherit from it and override some methods if necessary.

[http://db.tt/XkAI9sIm](http://db.tt/XkAI9sIm)

It uses the Sanae3D package cause I do things like outputting values into a text file and plotting points.
While I can just copy all of the methods over, I just do it for convenience and quick testing.

But hmm node references...

Maybe 30.x is also different from 20.6.x
## Post #16
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-03T06:33:30+00:00
- Post Title: Re: noesis Gamebryo nif importer

My hack of your code before you hacked it 
[http://pastebin.com/daiBP38B](http://pastebin.com/daiBP38B)
The 3.xx header isn't much different, used byte compares to circumvent the korean letters.
The NiDataStream.1.18 loader is real ugly, need to get the correct names from the NiMesh to do it correctly.
Not come across the counter you use, it's always 01 in the models I've come across, but looking at the NiNode structure your probably correct.
There's an 01 in the 3 longs after the size data, might be another counter, if the NiNode structure is anything to go by.
You sure the 4 bytes 'data' following the counter are long and not 2 shorts?
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-03T09:32:40+00:00
- Post Title: Re: noesis Gamebryo nif importer

Anything that's unknown (not assigned) is just stuff I randomly skipped over.
## Post #18
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-03-03T23:05:45+00:00
- Post Title: Re: noesis Gamebryo nif importer

When I tried to load a Gamebryo 20.6.5.0 file in Noesis with Tsukihime's latest plugin, it gave me this error:

> Detected file type: Gamebryo
>
> 0x14060500
>
> Traceback (most recent call last):
>
>   File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 34, in noepyLoadModel
>
>     parser.parse_file()
>
>   File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 356, in parse_file
>
>     self.parse_chunks(numChunks, numNodes)        
>
>   File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 344, in parse_chunks
>
>     self.sectionNames.append(self.read_name())
>
>   File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 97, in read_name
>
>     string = self.inFile.readBytes(length)
>
>   File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\inc_noesis.py", line 111, in readBytes
>
>     return noesis.bsReadBytes(self.h, numBytes)
>
> MemoryError
>
> Cleaned 8.00MB (in 2 pools).
## Post #19
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-04T00:10:48+00:00
- Post Title: Re: noesis Gamebryo nif importer

Getting bad triangles with multiple objects, but getting there slowly.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-04T00:41:08+00:00
- Post Title: Re: noesis Gamebryo nif importer

Nice, I wonder if it applies to the previous formats lol

> Reply from Mirrorman95
>
> When I tried to load a Gamebryo 20.6.5.0 file in Noesis with Tsukihime's latest plugin, it gave me this error:
Detected file type: Gamebryo
0x14060500
Traceback (most recent call last):
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 34, in noepyLoadModel
    parser.parse_file()
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 356, in parse_file
    self.parse_chunks(numChunks, numNodes)        
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 344, in parse_chunks
    self.sectionNames.append(self.read_name())
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 97, in read_name
    string = self.inFile.readBytes(length)
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\inc_noesis.py", line 111, in readBytes
    return noesis.bsReadBytes(self.h, numBytes)
MemoryError
Cleaned 8.00MB (in 2 pools).

Post some of those. I don't think I have any 20.6.5.0.
## Post #21
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-03-04T01:23:37+00:00
- Post Title: Re: noesis Gamebryo nif importer

> Reply from finale00
>
> Nice, I wonder if it applies to the previous formats lol
Mirrorman95 wrote:When I tried to load a Gamebryo 20.6.5.0 file in Noesis with Tsukihime's latest plugin, it gave me this error:
Detected file type: Gamebryo
0x14060500
Traceback (most recent call last):
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 34, in noepyLoadModel
    parser.parse_file()
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 356, in parse_file
    self.parse_chunks(numChunks, numNodes)        
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 344, in parse_chunks
    self.sectionNames.append(self.read_name())
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\fmt_Gamebryo_nif.py", line 97, in read_name
    string = self.inFile.readBytes(length)
  File "C:\Users\BenDesktop\Downloads\noesis\plugins\python\inc_noesis.py", line 111, in readBytes
    return noesis.bsReadBytes(self.h, numBytes)
MemoryError
Cleaned 8.00MB (in 2 pools).

Post some of those. I don't think I have any 20.6.5.0.
Here are three separate NIFs for ElecTRONica Pete (one is a texture NIF):
[http://www.mediafire.com/?kxlud8mt6plqh ... 4kl8r82b9a](http://www.mediafire.com/?kxlud8mt6plqh5y,bxo267tbz8bsiqe,szzo84kl8r82b9a)
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-04T03:26:45+00:00
- Post Title: Re: noesis Gamebryo nif importer

Cool, 20.6.5.0 decided to add a short right before the chunk name and use a single byte to give the length of the chunk name.
It also added a random byte right after the number of chunks.

I wonder if there are more 20.6.5.0's from a different game to compare with.

Now I'm pretty amazed at how nifskope handles all these crazy formats.
## Post #23
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-03-04T09:32:53+00:00
- Post Title: Re: noesis Gamebryo nif importer

> Reply from finale00
>
> Cool, 20.6.5.0 decided to add a short right before the chunk name and use a single byte to give the length of the chunk name.
It also added a random byte right after the number of chunks.

I wonder if there are more 20.6.5.0's from a different game to compare with.

Now I'm pretty amazed at how nifskope handles all these crazy formats.
Actually, NifSkope can't load this properly either. Can anything?
## Post #24
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2012-03-04T10:05:47+00:00
- Post Title: Re: noesis Gamebryo nif importer

I post here some nif files from Brawl busters if somebody can take a look on this files. Thanks
[http://www.sendspace.com/file/lukdpd](http://www.sendspace.com/file/lukdpd)
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-04T10:24:32+00:00
- Post Title: Re: noesis Gamebryo nif importer

> Reply from Mirrorman95
>
> finale00 wrote:Cool, 20.6.5.0 decided to add a short right before the chunk name and use a single byte to give the length of the chunk name.
It also added a random byte right after the number of chunks.

I wonder if there are more 20.6.5.0's from a different game to compare with.

Now I'm pretty amazed at how nifskope handles all these crazy formats.
Actually, NifSkope can't load this properly either. Can anything?

Probably not, unless someone has been working on their own nif importer.

Nif tools team probably has been too busy with skyrim and life. I mean, I guess we ideally we should be updating their xml file with our new findings cause they can definitely handle the data better than whatever crap we throw together in a couple days...
## Post #26
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-05T14:22:47+00:00
- Post Title: Re: noesis Gamebryo nif importer

I can try to find some nifs later when I get home, I have alot of different nif games
## Post #27
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-08T21:50:15+00:00
- Post Title: Re: noesis Gamebryo nif importer

[http://www.2shared.com/file/DESnUfAB/Nifs.html](http://www.2shared.com/file/DESnUfAB/Nifs.html)

Some mixed nifs 2.0.6 and also one 3.xx to look at from different games
## Post #28
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-08T22:45:14+00:00
- Post Title: Re: noesis Gamebryo nif importer

Thanks for the files, much appreciated.

As far as I can tell there only seems to be 2 real differences in the model formats, the ones where the vertex, uv, normal.. data are in separate chunks, and the ones where they are mixed up together.
Apart from the oddities of adding tiny bits of data wherever they want to, the vast majority of data can be skipped easily in order to extract the models, which will probably be a game specific format.
So assuming you can use the version code to determine the game, it might be best to have one script determine which game it's from and a loader class for each 'new' game? 
Not sure how to do that though.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T00:06:21+00:00
- Post Title: Re: noesis Gamebryo nif importer

The nif docs indicates two version numbers: the engine version, and a "user" version. These are the 8 bytes after the idstring.

If you've found two formats with identical versions but different structs for the same node...well that is a huge problem then lol.

Otherwise you can do your type-checking on all of these values, or create a more abstract parser that will determine which plugin to call, based on the versions.

```
user_version = readUInt()

if engine_version == 23...
   if user_version == "2"...
      parser = Nif_Parser_23_2()
   else
      parser = Nif_Parser_23()
elif engine_version == 26...
   ...
   parser = Nif_Parser_26()

#parse it
parser.parse_file()

```


```
   
   def parse_file(self):
       #parse my file

class Nif_Parser_26(GenericNifParser):

   def parse_file(self):
       #parse my file

class Nif_Parser_23_2(GenericNifParser):

   def parse_file(self):
       #parse my file


```
## Post #30
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-09T03:59:01+00:00
- Post Title: Re: noesis Gamebryo nif importer

That would be a huge problem yes, but I meant the two general major differences between different formats is the way the main data is structured, seems to be either separate chunks or all mixed up. Formatted by the NiMesh structure.

The best approach IMO is to treat each GAME as a unique format but remember they aren't that dissimilar, once you have parsers that can get data from both chunks and mixed data it's going to be relatively simple to adapt the scripts for other versions.

Plugins - is that a parser class in a separate files, that needs an include? that would be great.
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T06:38:23+00:00
- Post Title: Re: noesis Gamebryo nif importer

Ya, it's just a typical inheritance structure. Naturally the generic parser (which would be an interface of abstract class in C++ or java) would contain a bunch of structs that are common and really don't change, while the child classes add or override things like NiMesh, NiDataStream, etc. as necessary.

```

class GenericNifParser(object):

   def parse_NiTextureData(self):
      '''stuff'''

   def parse_NiMaterial(self):
      '''stuff'''

   def parse_NiMesh(self):
      '''stuff'''

```


```

from _NifParser import GenericNifParser

class NifParser20060500(GenericNifParser):
   '''20.6.5.00 nif parser'''

   def parse_NiDataStream118(self):
      '''Add some new methods for these new structs'''

   ...

```


```

from _NifParser import GenericNifParser

class NifParser30010000(GenericNifParser):
   '''30.1.0.00 nif parser'''

   ...

   def parse_NiMesh(self):
      '''Overrides parent method'''

      ...

```


My original design was to have all of the plugins in a sub-folder (package) called "NifParser", and then have one that does the type-checking in the main plugins folder. 

The main problem I had with that design was this:

Some formats (say, 10.1.0.0 to 20.0.0.0) may use a particular struct for one of the nodes, and then starting in a later version (say, 20.6.0.0) they decided to change it. And then that change persists until some other later version.

I would like only one copy of the first struct to exist at any given time, and I would also like only one copy of the new struct to exist at any given time as well (to reduce redundancy).

But then how would you structure the inheritance tree? I guess instead of just inheriting from a generic nif parser, you could instead inherit from one of the later nif parsers as well...? Since each version pretty much seems to build on the previous.
## Post #32
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-03-09T08:05:36+00:00
- Post Title: Re: noesis Gamebryo nif importer

Tried loading a 20.5.0.0 file from Splatterhouse in here, got this error if it helps any:

File I'm trying to work with: [http://randomselect.piiym.net/sh_resour ... 3_mask.nif](http://randomselect.piiym.net/sh_resources/dlc_ps3_mask.nif)
## Post #33
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T08:46:39+00:00
- Post Title: Re: noesis Gamebryo nif importer

Great, they have multilingual versions as well and the idstring is even longer.
Looks like we can't just say "read 39 bytes". Instead, we should read 38 bytes, and then read another byte to see if it's a newline char 0xA. If it's not, then I guess we read some more...

Or just read it one byte at a time until you reach 0xA ...........

20.5.0.0 BR 0.0.0.2 has the same chunk table as 20.6.5.0 posted before.

```
byte length
char[length] node name
byte null

```
## Post #34
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-03-10T01:28:05+00:00
- Post Title: Re: noesis Gamebryo nif importer

After doing some work with trying to get the PS3 mask into the Xbox version of the game, I got an interesting result: the model loaded, but the textures did not. Took it a bit further and grabbed two files of the same kind. Turns out the PS3 version of the game is significantly smaller, though I'm uncertain as to why.

Here are the files in question:
[http://randomselect.piiym.net/sh_resour ... r_dmg2.nif](http://randomselect.piiym.net/sh_resources/xbox_g_furnboss_chair_dmg2.nif)
[http://randomselect.piiym.net/sh_resour ... r_dmg2.nif](http://randomselect.piiym.net/sh_resources/ps3_g_furnboss_chair_dmg2.nif)
## Post #35
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-10T06:14:23+00:00
- Post Title: Re: noesis Gamebryo nif importer

It's Big Endian name lengths.
The names are the same formatting as your original importer, they just using big endian instead of little endian. 

Kung fu man, guess the xbox needs extra data for something special
## Post #36
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-10T06:19:25+00:00
- Post Title: Re: noesis Gamebryo nif importer

Oh, good catch. Never occurred to me that they export nif in big endian for console games lol
## Post #37
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2012-03-26T02:33:38+00:00
- Post Title: Re: noesis Gamebryo nif importer

So I've made a little headway fooling around with the header and seeing what will load with NifScope...currently the file format seems to be closer to 20.2.0.7 (Skyrim's) or 20.3.0.2 I can at least get SOME of the data to load, but not enough to produce a working model. Instead the results give the following:

[http://randomselect.piiym.net/sh_resources/error.txt](http://randomselect.piiym.net/sh_resources/error.txt)

Files used: [http://randomselect.piiym.net/sh_resources/rick.rar](http://randomselect.piiym.net/sh_resources/rick.rar)

Dunno if that HELPS anything but I've got to try. With this much I can browse some of the data, including switches and what dds files are tied to what at least.  :\
## Post #38
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-30T02:22:27+00:00
- Post Title: Re: noesis Gamebryo nif importer

Who was screwing around with vertex morphs in a Noesis NIF script? Whoever it was crashed Noesis by providing vertex morphs without normals. Noesis now handles that and uses the base mesh normals (if there are any) when no morph normals are provided.

It would've been easier if whoever it was had simply posted the file and script and told me it crashed, instead of making me figure out what happened by looking up addresses and tracing backward through disassembly.
## Post #39
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-04-25T15:12:56+00:00
- Post Title: Re: noesis Gamebryo nif importer

I have this (and many other) very old NIF files (dated 2009), which I am not able to properly convert to other formats: I always loose textures, whatever converter I use: blender+plugin, nifskope, noesis,...
[http://3dreamteamvizerra.s3.amazonaws.c ... 0.0%5D.zip](http://3dreamteamvizerra.s3.amazonaws.com/Locations/SanPietro/SanPietro%5B1.0.0.0%5D.zip)

It would be also interesting to know how to properly position each file in the overall environment: this information is stored in the .xblock files in World folder, but how to implement these data in the exported file?
