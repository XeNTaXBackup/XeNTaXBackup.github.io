## Post #1
- Username: zzh8829
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 16, 2014 7:11 am
- Post datetime: 2014-03-17T00:11:20+00:00
- Post Title: Disney Infinity Scene Format

Someone already figured out that *.vbuf and *.ibuf are just plain vertex/index data. [viewtopic.php?f=16&t=11187](http://forum.xentax.com/viewtopic.php?f=16&t=11187)
There is absolutely no meta information inside vbuf ibuf, actual model info are stored in *.bent and *.oct file.

Based on my research *.bent, *.oct, *.banm, *.mer *.tup(from cars2) are in exactly same binary format.
so I'll Just call that a scene format
here is the format:

```
    detail: 
        magic = int8[12] '\x29\x76\x01\x45\xcd\xcc\x8c\x3f\x00\x00\x00\x00' 
        something = int8[10] some flags maybe ?
        padding =  int8[39]
strings section: c-style 0 ending strings
    detail:
        "string_1",0,"string_2",0...,"string_n",0,0x01,0x00,0x00,0x00
    notices:
        strings array should starts with "", string_1 actually means index at 1. 
data section:
    data structure are indentation based. each data has its indentation,type and name.
    So, there is NO character for begin/end, structure looks like this
    
    SceneNodes = 
        Node "1" = 
            name = "hello"
            type = "node"
    Textures = 
        Texture "1" = 
            name = "xxx"
    blahblah
    
    read until end:
   
        flag = int16
        nameindex = int16

        name = strings[nameindex]
        indentation = flag // 0x400
        format = flag % 0x400

        *format is really complex, you can just read the python script i provided.


```


TL DR: here is the script, python 3.2. 

```
# Author: zzh8829
# Email: zzh8829#gmail.com
import os
import io
import pprint
import sys
import struct

types = {
	'int8_t': 'b',
	'uint8_t': 'B',
	'int16_t': 'h',
	'uint16_t': 'H',
	'int32_t': 'i',
	'uint32_t': 'I',
	'int64_t': 'q',
	'uint64_t': 'Q',
	'float': 'f',
	'double': 'd',
	'char': 'c',
    'bool': '?',
    'pad': 'x',
    'void*': 'P',
}

class BStream:
	def __init__(self, **kwargs):
		if "file" in kwargs:
			self.stream = open(kwargs["file"], "rb")
		elif "stream" in kwargs:
			self.stream = kwargs["stream"]
		elif "bytes" in kwargs:
			self.stream = io.BytesIO(kwargs["bytes"])
		else:
			raise Exception("UnityStream arguments error")

	def read(self, type_name='char'):
		if isinstance(type_name,int):
			return self.unpack('%ds'%type_name)[0]
		fmt = types[type_name.lower()]
		return self.unpack(fmt)[0]

	def unpack(self, fmt):
		return struct.unpack(fmt, self.stream.read(struct.calcsize(fmt)))

	def read_cstring(self):
		string = ""
		while True:
			char = self.read('char')
			if ord(char) == 0:
				break
			string += char.decode("utf-8")
		return string

	def read_string(self):
		return self.unpack('%ds'%self.read('uint32_t'))[0].decode('utf-8')

	def read_all(self):
		return self.read(self.size() - self.get_position())

	def read_int12(self):
		return int.from_bytes(self.read(3),byteorder="little")

	def get_position(self):
		return self.stream.tell()

	def set_position(self, pos, whence=0):
		self.stream.seek(pos, whence)

	def size(self):
		pos = self.get_position()
		self.set_position(0,2)
		end = self.get_position()
		self.set_position(pos,0)
		return end

	def align(self, alignment=4):
		self.set_position((self.get_position() + alignment - 1) // alignment * alignment) 


def read_oct(stream):
	file_size = stream.size()

	magic = stream.read(12)
	header = stream.read(10)
	padding = stream.read(39)
	strings = [""]

	s = ""
	while s!="\x01":
		s = stream.read_cstring()
		strings.append(s)

	padding = stream.read(2)

	while stream.get_position() != file_size:
		flag = stream.read("uint16_t")
		name = strings[stream.read("uint16_t")]

		indent,format = divmod(flag,0x400)

		print("\t"*(indent-1) + name + "[%04x]"%format, end=" = ")

		# unknown sign all treat as unsigned !!!

		if format == 0x01: 
			print()
		elif format == 0x05: 
			data = strings[stream.read("uint16_t")]
			print("'%s'"%data)
		elif format == 0x0A:
			count = stream.read("uint8_t")
			data = []
			for i in range(count):
				data.append(strings[stream.read("uint16_t")])
			print(data)
		elif format == 0x0B:
			data = strings[stream.read("uint16_t")]
			print("'%s'"%data)
		elif format == 0x12:
			count = stream.read("uint8_t")
			data = []
			for i in range(count):
				data.append(stream.read("float"))
			print(data)
		elif format == 0x13:
			data = stream.read("float")
			print(data)
		elif format == 0x1A:
			count = stream.read("uint8_t")
			data = []
			for i in range(count):
				data.append(stream.read("int8_t"))
			print(data)
		elif format == 0x1B:
			data = stream.read("int8_t")
			print(data)
		elif format == 0x23:
			count = stream.read("uint8_t")
			data = []
			for i in range(count):
				data.append(stream.read("uint8_t"))
			print(data)
		elif format == 0x4A:
			count = stream.read("uint16_t")
			data = []
			for i in range(count):
				data.append(strings[stream.read("uint16_t")])
			print(data)
		elif format == 0x5A:
			count = stream.read("uint16_t")
			data = []
			for i in range(count):
				data.append(stream.read("uint8_t"))
			print(data)
		elif format == 0x63: # binary data
			count = stream.read("uint16_t")
			data = []
			for i in range(count):
				data.append(stream.read("uint8_t"))
			print(data)
		elif format == 0x11A:
			count = stream.read("uint8_t")
			data = []
			for i in range(count):
				data.append(stream.read("uint16_t"))
			print(data)
		elif format == 0x11B:
			data = stream.read("uint16_t")
			print(data)
		elif format == 0x15A:
			count = stream.read("uint16_t")
			data = []
			for i in range(count):
				data.append(stream.read("uint16_t"))
			print(data)
		elif format == 0x21A:
			count = stream.read("uint8_t")
			data = []
			for i in range(count):
				data.append(stream.read_int12())
			print(data)	
		elif format == 0x21B:
			data = stream.read_int12()
			print(data)
		elif format == 0x31B:
			data = stream.read("uint32_t")
			print(data)
		else:
			print("unknown format: %x offset: %x"%(flag,stream.get_position()))
			sys.stderr.write("unknown format: %x offset: %x\n"%(flag,stream.get_position()))
			print(stream.read_all()[:100])
			break

if __name__ == '__main__':
	read_oct(BStream(file="fro_elsa.oct"))


```


this script prints whole reversed document to stdout
you can redirect output to a file.

I reversed most formats (like 95+%), there is still some unknown format. 

OK End of Scene Format
------------------------------------------------------------------

Let's talk about model and animation now.
I'll just use fro_elsa as example (elsa from frozen) 
link to files here (I didn't include the whole folder, there are like 1000 animations lol)
[http://www.mediafire.com/download/y0c5s ... o_elsa.zip](http://www.mediafire.com/download/y0c5ssijkhexk0v/fro_elsa.zip)

*.txt is reversed files using my script

fro_elsa.bent file includes animation mapping [anim_name]->[file_name]
fro_elsa.oct file includes texture,index,vertex and maybe ???bones???
fro_elsa.mtb is material bundle, format unknown
texture/*.tbody are the textures in DDS format, their name should be some sort of hash value. 
characters/*/*.[oct/banm] are animation files. they are all in Scene Format. 

===Index/Vertex===
each index/vertex pair are called Idata/Vdata in fro_elsa.oct file

example:

```
	VertexBuffer[0005] = '0'
		Name[000b] = 'Static'
		Flags[001b] = 73
		Size[021b] = 216760
		HeapLoc[001b] = 0
		FileName[000b] = 'fro_elsa_0.vbuf'
IndexBufferPool[0001] = 
	IndexBuffer[0005] = '0'
		Width[001b] = 2
		Name[000b] = 'Static'
		Flags[001b] = 91
		Size[021b] = 53610
		FileName[000b] = 'fro_elsa_0.ibuf'
SceneTreeNodePool 
        ...
	Node
        ... 
		Primitives[0001] = 
			Primitive[0005] = '0'
				MaterialName[000b] = 'characters__fro_elsa__materials__fro_elsa_pupil__skinning_isEnabled_true'
				MaterialReference[001b] = 0
				vformatCRC[031b] = 1630786171
				RenderCaps[011b] = 4096
				BillboardType[001b] = -1
				OcclusionType[001b] = 0
				OcclusionCheckRadius[0013] = 0.25
				OcclusionFadeKp[0013] = 0.10000000149011612
				Idata[011a] = [0, 0, 0, 1728]
				Vdata[021a] = [2, 5419, 0, 0, 24, 0, 130056, 16]
			Primitive[0005] = '1'
				MaterialName[000b] = 'characters__fro_elsa__materials__fro_elsa_head__skinning_isEnabled_true'
				MaterialReference[001b] = 1
				vformatCRC[031b] = 1630786171
				RenderCaps[011b] = 4096
				BillboardType[001b] = -1
				OcclusionType[001b] = 0
				OcclusionCheckRadius[0013] = 0.25
				OcclusionFadeKp[0013] = 0.10000000149011612
				Idata[011a] = [0, 1728, 0, 14097]
				Vdata[021a] = [2, 5419, 0, 0, 24, 0, 130056, 16]


```

I have no idea what are these number represents

===Bones===
I am not sure how bones stored.
there are some "Influences" in fro_elsa.oct
and also some weird subnetwork and datanode stuff....

===Animations===
I believe animation data is stored in
*.oct->SubNetworkPool->SubNetwork->DataNodePool->DataNode->ClipDataBlock
but the clip data block is just a array of binary data.
I have no idea how that works lol xD
Just take a look at reversed .txt file

If you find out something new pls post here.   
Feel free to modify my script
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-17T03:56:57+00:00
- Post Title: Disney Infinity Scene Format

Very nice.  
Did you find the parenting information or is there even parenting information in these files?
## Post #3
- Username: zzh8829
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 16, 2014 7:11 am
- Post datetime: 2014-03-17T05:14:50+00:00
- Post Title: Disney Infinity Scene Format

I think the influence part contains bone weights
Name and Bind Inverse Matrix

```
		Influences[0001] = 
			Influence[0005] = '0'
				Name[000b] = 'Head'
				BindPoseSkinLocalToWorldMatrixInverseData[0012] = [1.0, 0.0, 0.0, 0.0, 0.0, -0.15287145972251892, 0.9882460832595825, 0.0, 0.0, -0.9882460832595825, -0.15287145972251892, 0.0, 0.0, 0.2044771909713745, -1.3348443508148193, 1.0]
			Influence[0005] = '1'
				Name[000b] = 'BrowLeft'
				BindPoseSkinLocalToWorldMatrixInverseData[0012] = [0.6839881539344788, 5.219752657786348e-16, 0.7294931411743164, 0.0, 5.415912253480643e-16, 1.0, -9.643804682504375e-16, 0.0, -0.7294931411743164, 9.650119313126156e-16, 0.6839881539344788, 0.0, 0.03923764452338219, -1.5224781036376953, -0.1655174046754837, 1.0]

```


Follow by this is 

```
		InfluenceRemapInfluenceRefs[001a] = [15, 16, 0, 6, 60, 19, 0, 20, 21, 6, 60, 1, 61, 4, 35, 9, 10, 12, 2, 7, 5, 45, 34, 32, 3, 15, 44, 43, 33, 11, 16, 8, 37, 62, 63, 59, 41, 42, 39, 40, 38, 36, 43, 35, 44, 61, 45, 0, 22, 33, 32, 23, 31, 34, 24, 30, 58, 27, 29, 25, 28, 26, 54, 52, 55, 53, 48, 14, 13, 51, 50, 49, 13, 14, 18, 17, 26, 55, 51, 59, 40, 37, 25, 56, 28, 24, 57, 47, 46, 61, 34, 45, 33, 32, 44, 35, 43, 22]
		InfluenceRemapPrimitiveData[001a] = [0, 5, 5, 27, 72, 26, 32, 40]

```

I am not sure what is a Remap, maybe this is parenting info? or just reorder the bones

I don't know what does Basis mean, but this might be the joints hierarchy

```
				Name[000b] = 'Body'
				ParentRef[001b] = 3
				Behavior[000b] = 'Normal'
			Basis[0005] = '131'
				Name[000b] = 'Spine1'
				ParentRef[011b] = 130
				Behavior[000b] = 'Normal'
			Basis[0005] = '132'
				Name[000b] = 'Spine2'
				ParentRef[011b] = 131
				Behavior[000b] = 'Normal'
			Basis[0005] = '133'
				Name[000b] = 'Spine3'
				ParentRef[011b] = 132
				Behavior[000b] = 'Normal'

```


It seems that Disney used a huge complex home-made game engine, can't find anything on internet.
The animation system of this engine is very complicated.
Based on some reversed files, I guess the engine is called Octane/Meridian
.oct probably stands for Octane, and .mer stands for Meridian
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-18T12:36:10+00:00
- Post Title: Disney Infinity Scene Format

Nice find +1
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-11-30T12:16:41+00:00
- Post Title: Disney Infinity Scene Format

Hello

Here is  importer for models from PS3 . 

It requires Blender version 249 and Python 2.6. 

I use  scene format research done by zzh8829.

It works with .oct files from Disney Infinity 1 and 2 for PS3 console.

It imports:
- models with weights
- bind bones for each mesh (no bones parenting  )
- armature with bone parenting (not perfect, approximate) 

Textures are not supported. I don't know where to find file names for apply to meshes.


Update: 2014-12-02:
-support for PC version
[Blender249[DisneyInfinity][PC][PS3].zip](https://xentaxbackup.github.io/file/8181_Blender249[DisneyInfinity][PC][PS3].zip)
## Post #6
- Username: zzh8829
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 16, 2014 7:11 am
- Post datetime: 2014-12-01T07:22:51+00:00
- Post Title: Disney Infinity Scene Format

Thanks for making use of my script. I spend so much time on this hoping to get animation data
## Post #7
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-12-02T09:31:20+00:00
- Post Title: Disney Infinity Scene Format

Is this only possible with the PS3 version? I tested on Disney Infinity 2.0 PC version and I got an error :/
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-02T14:43:02+00:00
- Post Title: Disney Infinity Scene Format

> Reply from Szkaradek123
>
> Hello

Here is  importer for models from PS3 . 

It requires Blender version 249 and Python 2.6. 

I use  scene format research done by zzh8829.

It works with .oct files from Disney Infinity 1 and 2 for PS3 console.

It imports:
- models with weights
- bind bones for each mesh (no bones parenting  )
- armature with bone parenting (not perfect, approximate) 

Textures are not supported. I don't know where to find file names for apply to meshes.


Update: 2014-12-02:
-support for PC versionHello, thank you, my friend, I tested the PS3 model, the script runs very well.Ask a question, how do I get HD textures, after I added the DDS file headers, are low resolution DDS textures
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-12-10T21:20:17+00:00
- Post Title: Disney Infinity Scene Format

I can't run the python script:
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-10T21:55:48+00:00
- Post Title: Disney Infinity Scene Format

windows 7: I copied the newGameLib folder into the Blender 2.49b directory (where the blender.exe resides)
## Post #11
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-12-10T22:04:11+00:00
- Post Title: Disney Infinity Scene Format

> Reply from shakotay2
>
> windows 7: I copied the newGameLib folder into the Blender 2.49b directory (where the blender.exe resides)

Thanks.
## Post #12
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-08T17:21:48+00:00
- Post Title: Disney Infinity Scene Format

Any chance the blender script can be updated for 3.0? The script currently gives an error when trying to import the files. I can upload some samples if needed.
## Post #13
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2015-11-08T17:26:09+00:00
- Post Title: Disney Infinity Scene Format

[http://zenhax.com/viewtopic.php?f=5&t=1686](http://zenhax.com/viewtopic.php?f=5&t=1686)
## Post #14
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-08T17:39:22+00:00
- Post Title: Disney Infinity Scene Format

Oh thank you! I didn't realise it was updated
