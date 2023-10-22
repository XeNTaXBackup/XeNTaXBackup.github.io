## Post #1
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-04-09T12:26:29+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

Hi There!

I'm currently in the (long) process of trying to make sense of the model fileformats for the Ni No Kuni PS3 game. But I'm not getting any further.

What I've gotten so far:
FILE FORMATS

UNKNOWN
p3mmg - ?model data?
p3mms - ?model, material, shader?
p3msh - ?Model SHader? (looks hierarchical)
p3amt - ?animation model type?
p3atm

ALMOST KNOWN
p3msk - Model SKeleton
p3ask - Animation SKeleton / animation,skeleton,keyframes
actcfgbin - action config binary
adtcfgbin - animation config binary
mevcfgbin - event config binary
mdtcfgbin - model config binary
procfgbin - prop config binary
hitcfgbin - ?hit box?
lcscfgbin - locus config binary
prtcfgbin - part config bin
laicfg - look at info config

SKELETON FORMAT DEFINITION .p3msk 
	(REF c001100.p3msk)

```
	0x0000:   4b - header
	0x0004:   4b - unknown
	0x0008:   4b - 12304 - A - filesize
	0x0012:   4b - bool or int
	0x0016:   4b - 176 - B (<A)
	0x0020:   4b - 12128 - C (A-B)
	0x0024:  24b - unknown
	0x0048:   2b - unknown
	0x0050:   2b - 93 - AMOUNT OF BONES
	0x0052:   4b - unknown
	0x0056:   4b - 752 - SIZE IN BYTES OF NAME BLOCK
	0x0060:   4b - 2240 (+ headersize = bone hierarchy offset)
	0x0064:   4b - 2816 (+ headersize = IDs offset)
	0x0068:   4b - 2432 (+ headersize = post hierarchy offset)
	0x0072:   4b - 3200 (+ headersize = z offset) // pose 1?
	0x0076:   4b - 7664 (+ headersize = u offset) // pose 2?
	0x0080: 100b - unknown

0x0176: BLOCK - BONE NAMES
	list of null terminated strings
	0x0176:   4b - null
   {	
	0x0180:   8b - null terminated string
        AMOUNT OF BONES times 8b
   }
	0x0924:   4b - null

0x0928: BLOCK - UNKNOWN DATA
   {
	0x0928:  32b - matrix, translation?
        AMOUNT OF BONES times 32b
   }
	
0x2416: BLOCK - BONE HIERARCHY
	0x2416:   2b - Start of hierarchy 0xFFFF
   {
        0x2418:   2b - index of parent bone
        0x2420:   2b - index of child bone
        AMOUNT OF BONES times 4b
   }

0x2604:   4b - padding NULL

0x2608: BLOCK - auto incrementing values
   {
	0x2608:   4b - value = (i * 8) + 4
   }

0x2980:  12b - padding NULL

0x2992:	BLOCK - UNKNOWN (0x2992)
   {
	0x2992: 4b UNKNOWN
	AMOUNT OF BONES times 4b
   }

0x3364: 12b PADDING

0x3376: BLOCK - UNKNOWN
   {
	0x3376: 48b per bone (3x4 matrix)
   }

0x7840: BLOCK - UNKNOWN
   {
	0x7840: 48b per bone (3x4 matrix)
   }

0x12304: EOF
```


Now, I've read on here that the actual models are stored in the .P3MMG files, the header structure is very much like the .P3MSK files. within these files are separate blocks of what i think are separate meshes (head, eyes, hooves, whatever)
The vertex format is what is breaking my brain. Either the floats are stored in a weird format (mantissa kept separate from exponent...) or i'm totally not seeing what i'm missing now.

I will continue to post in this thread to keep showing my progress (and keep my sanity), if you have any input or comments i'd love to hear them!

How i got the assets from the game:
[viewtopic.php?f=18&t=11104](http://forum.xentax.com/viewtopic.php?f=18&t=11104)
[viewtopic.php?f=18&t=10103](http://forum.xentax.com/viewtopic.php?f=18&t=10103)
[viewtopic.php?f=10&t=7932](http://forum.xentax.com/viewtopic.php?f=10&t=7932)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-04-09T17:47:26+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

if i recall this game used ps3 edge sdk.
## Post #3
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-04-09T20:23:29+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

is that the edge sdk for encryption or the edge animation api?
## Post #4
- Username: n0y8
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-04-09T23:09:58+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

edge for face index compression.
## Post #5
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-04-11T17:27:24+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

Very interesting. I've been reading up on that now and the compression algorithm (from the noesis import script by chrrox) used in playstation All stars is weird enough, I've also found some sample code in the sdk which is intimidating. 

Firstly I'd like to get the vertex positional data sorted and have the models show up as a point cloud, before moving on to normals, bone weights, face indices and uv-maps. 

the pkchr __lbrmdl02 seems to be a cube with 12 triangles. But if this game is using edge face indices compression there would be no reason to declare the same vertex multiple times. Oh well, back to the drawing board. 

So if anyone has info about the vertex positional data that would be great. In the mean time back to hexeditor and puzzle away
## Post #6
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-04-12T13:01:19+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

> Reply from n0y8
>
> Very interesting. I've been reading up on that now and the compression algorithm (from the noesis import script by chrrox) used in playstation All stars is weird enough, I've also found some sample code in the sdk which is intimidating. 

Firstly I'd like to get the vertex positional data sorted and have the models show up as a point cloud, before moving on to normals, bone weights, face indices and uv-maps. 

the pkchr __lbrmdl02 seems to be a cube with 12 triangles. But if this game is using edge face indices compression there would be no reason to declare the same vertex multiple times. Oh well, back to the drawing board. 

So if anyone has info about the vertex positional data that would be great. In the mean time back to hexeditor and puzzle away
Maybe a side effect of edge compression on really small models?
## Post #7
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2015-04-13T23:47:19+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

It looks like they actually took the time to (slightly) customize the PPU Config Info structure. That wasn't hard to figure out, but it looks like they're using fully customized SPU input/output stream descriptors and attribute blocks. Also the index data only lists a sequence size. Index count, index base, and index bit size are all zero.....so that's interesting. I'll try and figure it out, but
## Post #8
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-04-14T15:51:45+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

@TheDude you seem to be making progress, thank you for your time!

Care to share how you've come to those conclusions? I love puzzling like this and would like to learn more.
## Post #9
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2015-04-15T13:50:20+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

Maybe I should just start a new thread for a Playstation EDGE tutorial?
It's pretty much impossible to talk about though without using information straight from the SDK
and I'm not sure what I could or couldn't post (legally).
## Post #10
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-04-15T15:32:51+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

Yeah that *would* be great  

i've sorted out the skeleton (p3msk) matrix data after reading some header file in the SDK as being 
EDGE_GEOM_MATRIX_3x4_ROW_MAJOR filled with EDGE_GEOM_ATTRIBUTE_FORMAT_X11Y11Z10N, but even that might be saying too much right? It would be great to talk openly about this as a reference and an entrance to reversing 3D files that use the EDGE SDK.
## Post #11
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-05-25T20:48:36+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

So, that last comment was not correct, it's just matrices of normal floats...

Here's some Python i wrote to parse the .p3msk files:

```
from sys import argv
import os

def getFileSize(file):
	file.seek(0,2)
	return file.tell()

def parse_F32(input):
	b = BitStream(input)
	return b.unpack('float:32')

def parse_X11Y11Z10N(input):
    b = BitStream(input)

    raw = b.unpack('int:10, int:11, int:11')
    x = xBitIntToNormalizedFloat(raw[0], 10)
    y = xBitIntToNormalizedFloat(raw[1], 11)
    z = xBitIntToNormalizedFloat(raw[2], 11)
    return [x, y, z]

def parse_MATRIX_3x4_ROW_MAJOR(input):
	output = [[], [], [], []]
	output[0] = [parse_F32(input.read(32)), parse_F32(input.read(32)), parse_F32(input.read(32)), parse_F32(input.read(32))]
	output[1] = [parse_F32(input.read(32)), parse_F32(input.read(32)), parse_F32(input.read(32)), parse_F32(input.read(32))]
	output[2] = [parse_F32(input.read(32)), parse_F32(input.read(32)), parse_F32(input.read(32)), parse_F32(input.read(32))]
	return output

def xBitIntToNormalizedFloat(i, bitsizeOfInt):
	f = 0.0
	i = float(i)
	boundary = (2**(bitsizeOfInt-1))
	if i>0:
		# weird fix fox 10 bit int normalization
		f = i/(boundary-1.0)
	elif i<0:
		f = i/boundary

	return i

class NNKObject(object):
	id = 0

class NNKBone(NNKObject):
	name = ""
	index = ""
	matrix = []
	parentId = ""
	children = []

	def log(self):
		print "%s: " % self.name, hex(self.id)
		print "matrix: %s" % self.matrix

class P3MSK(object):
	filename = ""
	names = []
	ids = []
	hierarchy = []
	matrices_a = []
	matrices_b = []
	_NNKBones = []
	rootBoneIndex = 0

	# return the NNKBone with the given id
	def getNNKBoneWithId(self, id):
		index = self.ids.index(id)
		return self.getNNKBoneAtIndex(index)

	# return the NNKBone at the given index
	def getNNKBoneAtIndex(self, i):
		if(i > -1 and i < len(self.names)):
			# the bone doesn't exist yet so create it
			if i < len(self._NNKBones) and not self._NNKBones[i]:
				self.__createNNKBoneFromIndex(i)
			# return the bone at the index
			return self._NNKBones[i]
		else:
			return None # there isn't a bone there

	# create an NNKBone object and store it from the data at the index
	def __createNNKBoneFromIndex(self, i):
		bone = NNKBone()
		bone.name = self.names[i]
		bone.id = self.ids[i]
		bone.matrix = self.matrices_a[i]
		parentId = -1

		# get the parent ID
		if(i > 0):
			parentId = self.ids[i]
		bone.parentId = parentId

		if(parentId is -1): #this is the root bone
			self.rootBoneIndex = i

		# get the children IDs
		childrenIndices = [_i for _i, x in enumerate(self.hierarchy) if x == i]
		bone.children = []
		for j in range(0, len(childrenIndices)):
			bone.children.append(self.ids[childrenIndices[j]])

		return bone

	# create complete bone structure
	def createNNKBones(self):
		boneCount = len(self.names)
		for i in range(0, boneCount):
			bone = self.__createNNKBoneFromIndex(i)
			self._NNKBones.append(bone)
	
	def log(self):
		print "filename: %s" % self.filename
		print "objects: %d" % len(self.names)

		rootbone = self.getNNKBoneAtIndex(self.rootBoneIndex)
		self.log_bone(rootbone, 0)


	def log_bone(self, bone, depth):
		indent = ""
		for i in range (0, depth):
			indent = indent + "-"

		print "%s" % indent+bone.name,"(",hex(bone.id),")"
		
		if(len(bone.children) > 0):
			self.log_children(bone, depth + 1)

	def log_children(self, bone, depth):
		for i in range(0, len(bone.children)):
			self.log_bone(self.getNNKBoneWithId(bone.children[i]), depth)

	# FromFile parses file into object of methods class
	# so it's kinda a factory pattern, right?
	@staticmethod
	def FromFile(file):
		p3msk = P3MSK()
		p3msk.filename = file.name
		file = ConstBitStream(file)

		file.pos = 8 *8
		filesize = file.read('uint:32')
		file.pos = 16*8
		headersize = file.read('uint:32')
		datasize = file.read('uint:32')
		file.pos = 50*8
		boneCount = file.read('uint:16')
		file.pos = 56*8
		nameBlockSize = file.read('uint:32') # 56
		boneHierarchyOffset = file.read('uint:32') # 60 
		idBlockOffset = file.read('uint:32') # 64
		postHierarchyOffset = file.read('uint:32')
		matrixCollectionAOffset = file.read('uint:32')
		matrixCollectionBOffset = file.read('uint:32')

		# BLOCK - BONE NAMES 
		file.pos = headersize * 8 

		# read the names from the block
		_names = file.read(nameBlockSize * 8) 
		# convert into hex and decode to string
		_names = _names.hex.decode('hex') 
		# split string on NULL character
		_names = _names.split('\x00')
		# discard the emty list items 
		_names = filter(None, _names) 

		# BLOCK - BONE HIERARCHY
		file.pos = (headersize + boneHierarchyOffset) * 8

		# read the hierarchy in 16 bit ints (index of object list)
		_hierarchy = file.readlist(str(boneCount)+'*(int:16)')
		
		# BLOCK - ID DATA
		file.pos = (headersize + idBlockOffset) * 8
		
		#read the ids which are 64 bit ids
		_ids = file.readlist(str(boneCount)+'*(uint:32)')
		
		# --------------------------
		# BLOCK - MATRICES A
		# --------------------------
		file.pos = (headersize + matrixCollectionAOffset) * 8
		_matrices_a = []

		for i in range(0, boneCount):
			matrix = parse_MATRIX_3x4_ROW_MAJOR(file)
			_matrices_a.append(matrix)

		# --------------------------
		# BLOCK - MATRICES B
		# --------------------------
		file.pos = (headersize + matrixCollectionBOffset) * 8
		_matrices_b = []

		for i in range(0, boneCount):
			matrix = parse_MATRIX_3x4_ROW_MAJOR(file)
			_matrices_b.append(matrix)


		# FILL THE DATA TO THE P3MSK OBJECT
		p3msk.names = _names
		p3msk.hierarchy = _hierarchy
		p3msk.ids = _ids
		p3msk.matrices_a = _matrices_a
		p3msk.matrices_b = _matrices_b
		p3msk.createNNKBones()

		return p3msk

	

filename = 'c001000.p3msk' #'a020000.p3msk' #'_lbrmdl02.p3msk' #'c309500.p3msk' #
file = open(filename, mode='rb')
print(os.path.realpath(file.name))
p3msk = P3MSK.FromFile(file)
p3msk.log()

file.close

```


I'm now busy trying to make sense of the .p3ask file format. as far as i can see it's an animation file format with keyframes stored in them. Currently writing a similar parser in python (which is new for me, but python feels good!)
## Post #12
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-05-27T19:29:34+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

Some stuff i'm using to make sense of the data in the game.

[http://www.opengpu.org/forum.php?mod=vi ... &tid=10656](http://www.opengpu.org/forum.php?mod=viewthread&tid=10656)
[https://vimeo.com/41417095](https://vimeo.com/41417095) (There's some more videos from Nabe on Vimeo regarding ni no uni and the specific tooling used in its development.)
[https://www.youtube.com/watch?v=mFs18vBeTGk](https://www.youtube.com/watch?v=mFs18vBeTGk)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-27T20:37:49+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

It would be nice to have a p3msk sample to try out your script.  

When hovering the mouse over "OpenGPU" the tooltip says:
"Open Source Computer Graphics Community".



OpenSource.JPG (15.57 KiB) Viewed 343 times


Is there any "open source Ni No Kuni"? (I'm just curious, or is the tooltip info simply outdated?)
## Post #14
- Username: n0y8
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 07, 2015 3:21 am
- Post datetime: 2015-05-27T21:28:04+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

That forum post is a magazine scan from the japanese publication of "computer Graphics Magazine". I don't think there's an open source version of ni no kuni. 

I'm not at my laptop right now, but I'll see if I can send you a file when I am.
## Post #15
- Username: ureshiiiiii
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 22, 2017 9:14 am
- Post datetime: 2018-02-24T01:10:16+00:00
- Post Title: Ni No Kuni - 3D Model fileformats

Sorry to ask, but has there been any progress on .p3mmg or .p3mms model data files?

I can't find any information about them online aside from this forum.

I'm just curious to know if it's possible to convert these file types into a format that 3ds max can import?
