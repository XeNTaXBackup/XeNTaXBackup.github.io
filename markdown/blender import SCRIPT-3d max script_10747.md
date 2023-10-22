## Post #1
- Username: elenadg
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 16, 2013 8:25 am
- Post datetime: 2013-09-03T21:24:29+00:00
- Post Title: blender import SCRIPT->3d max script

[](http://s951.photobucket.com/user/ldd209/media/K-609_zpsefba05a2.jpg.html)

blender import SCRIPT->3d max DW7 script help~

3D MAX 2012 / SCRIPT -> DW7 ->UV ERROR?


file

texture file: file-G1T
[http://www.mediafire.com/?ywfw7e4wu7a4k43](http://www.mediafire.com/?ywfw7e4wu7a4k43)


character modeling file: file-elixir(ez)
[http://www.mediafire.com/?7q6eb4ufuaq24em](http://www.mediafire.com/?7q6eb4ufuaq24em)

I can't do it.

Please tell us blender  

3d max script want I'm asking

[until43636599@gmail.com](mailto:until43636599@gmail.com)

howfie blender import script code

```
# PYTHON IMPORTS
#
import array
import collections
import math
import os
import struct
import sys

#
# BLENDER IMPORTS
#
import Blender
from Blender import Image
from Blender import Material
from Blender import Modifier
from Blender import Mathutils
from Blender.Mathutils import *
from Blender import Texture
from Blender import Window
import bpy

#
# MATH UTILITIES
#

def Array4x4ToBlenderMatrix(data):

	r1 = [data[ 0], data[ 1], data[ 2], data[ 3]]
	r2 = [data[ 4], data[ 5], data[ 6], data[ 7]]
	r3 = [data[ 8], data[ 9], data[10], data[11]]
	r4 = [data[12], data[13], data[14], data[15]]
	return Blender.Mathutils.Matrix(r1, r2, r3, r4)

def NormalizeVector(data):

	norm = math.sqrt(data[0]*data[0] + data[1]*data[1] + data[2]*data[2])
	temp = [data[0]/norm, data[1]/norm, data[2]/norm]
	return temp
		
#
# STRING UTILITIES
#

def StripNullsFromStr(str):
	'''
	Strips null characters from a string.
	Notes: Blender does not like strings that contain null characters. This can
	happen when we load strings from binary files that were created using lang-
	uages such as C or C++.
	'''
	# make a copy, removing null characters
	retval = ''
	for c in str:
		if c != '\x00':
			retval += c
	return retval

#
# INPUT FILE STREAM
#

class InputFileStream:
	'''
	'''

	# CONSTRUCTOR
	def __init__(self):
		
		pass
	
	# PUBLIC METHOD: OPEN
	def open(self, filename):
		
		# open file
		try: self.ifile = open(filename, "rb")
		except: raise Exception('SMC Import Error: Failed to open file.')

	# PUBLIC METHOD: TELL
	def tell(self):
	
		return self.ifile.tell()
		
	# PUBLIC METHOD: SEEK
	def seek(self, position):
	
		# seek position
		self.ifile.seek(position)
		
	# PUBLIC METHOD: SKIP
	def skip(self, offset):
	
		# seek position
		self.ifile.seek(offset, 1)

	# PUBLIC METHOD: READ STRING
	def read_string(self, n):
	
		tmp = array.array('c')
		tmp.fromfile(self.ifile, n)
		ret = ''.join(tmp)
		return StripNullsFromStr(ret)
	
	# PUBLIC METHOD: READ UINT08
	def LE_read_uint08(self):
		
		tmp = self.ifile.read(1)
		if len(tmp) == 1: return struct.unpack('<B', tmp)[0];
		raise EOFError()

	# PUBLIC METHOD: READ UINT16
	def LE_read_uint16(self):
		
		tmp = self.ifile.read(2)
		if len(tmp) == 2: return struct.unpack('<H', tmp)[0];
		raise EOFError()

	# PUBLIC METHOD: READ UINT32
	def LE_read_uint32(self):
		
		tmp = self.ifile.read(4);
		if len(tmp) == 4: return struct.unpack('<I', tmp)[0];
		raise EOFError()

	# PUBLIC METHOD: READ UINT64
	def LE_read_uint64(self):
		
		tmp = self.ifile.read(8);
		if len(tmp) == 8: return struct.unpack('<Q', tmp)[0];
		raise EOFError()

	# PUBLIC METHOD: READ UINT08 ARRAY
	def LE_read_uint08_array(self, n):

		if(n == 0): raise Exception('SMC Import Error: Arrays must have at least one item.')
		ret = array.array('B')
		ret.fromfile(self.ifile, n)
		return ret;
		
	# PUBLIC METHOD: READ UINT16 ARRAY
	def LE_read_uint16_array(self, n):

		if(n == 0): raise Exception('SMC Import Error: Arrays must have at least one item.')
		ret = array.array('H')
		ret.fromfile(self.ifile, n)
		if sys.byteorder == "big": ret.byteswap()
		return ret;

	# PUBLIC METHOD: READ UINT32 ARRAY
	def LE_read_uint32_array(self, n):

		if(n == 0): raise Exception('SMC Import Error: Arrays must have at least one item.')		
		ret = array.array('I')
		ret.fromfile(self.ifile, n)
		if sys.byteorder == "big": ret.byteswap()
		return ret;
	
	# PUBLIC METHOD: READ UINT64 ARRAY
	def LE_read_uint64_array(self, n):

		if(n == 0): raise Exception('SMC Import Error: Arrays must have at least one item.')
		ret = array.array('Q')
		ret.fromfile(self.ifile, n)
		if sys.byteorder == "big": ret.byteswap()
		return ret;

	# PUBLIC METHOD: READ REAL32
	def LE_read_real32(self):
		
		tmp = self.ifile.read(4);
		if len(tmp) == 4: return struct.unpack('<f', tmp)[0];
		raise EOFError()

	# PUBLIC METHOD: READ REAL64
	def LE_read_real64(self):
		
		tmp = self.ifile.read(8);
		if len(tmp) == 8: return struct.unpack('<d', tmp)[0];
		raise EOFError()

	# PUBLIC METHOD: READ REAL32 ARRAY
	def LE_read_real32_array(self, n):

		if(n == 0): raise Exception('SMC Import Error: Arrays must have at least one item.')		
		ret = array.array('f')
		ret.fromfile(self.ifile, n)
		if sys.byteorder == "big": ret.byteswap()
		return ret;
	
	# PUBLIC METHOD: READ REAL64 ARRAY
	def LE_read_real64_array(self, n):
		
		if(n == 0): raise Exception('SMC Import Error: Arrays must have at least one item.')
		ret = array.array('d')
		ret.fromfile(self.ifile, n)
		if sys.byteorder == "big": ret.byteswap()
		return ret;

#
# STRUCTURES
#

class SMCHEADER:
	# uint32 magic
	# uint16 major_version
	# uint16 minor_version
	# uint32 n_vbuffers
	# uint32 n_ibuffers
	# uint32 n_images
	# uint32 n_surfaces
	# uint32 n_surfmats
	# uint32 n_skeletons
	# uint32 n_animations
	# uint32 reserved1
	# uint32 reserved2
	# uint32 reserved3
	# uint32 reserved4
	# uint32 reserved5
	# uint32 reserved6
	# uint32 reserved7
	pass

class SMCVTXBUFFER:
	# uint32 flags
	# string name
	# uint16 uvchan
	# uint16 uvtype[i]
	# uint16 colors
	# uint32 elem
	# real32 positions[[]]
	# real32 normals[[]]
	# real32 tangents[[]]
	# real32 binormals[[]]
	# real32 blendweights[[]]
	# uint16 blendindices[[]]
	# real32 texcoords[[]]
	# real32 vtxcolors[[]]
	pass

class SMCIDXBUFFER:
	# uint08 format
	# uint08 primitive
	# uint08 direction
	# string name
	# uint32 elem
	# T data[]
	pass

class SMCSURFMAT:
	# string name
	# uint08 twoside
	# uint08 unused1
	# uint08 unused2
	# uint08 unused3
	# uint16 basemap
	# uint16 specmap
	# uint16 tranmap
	# uint16 bumpmap
	# uint16 normmap
	# uint16 lgthmap
	# uint16 envimap
	# uint16 glssmap
	# uint16 resmap1
	# uint16 resmap2
	# uint16 resmap3
	# uint16 resmap4
	# uint16 resmap5
	# uint16 resmap6
	# uint16 resmap7
	# uint16 resmap8
	# uint08 basemapchan
	# uint08 specmapchan
	# uint08 tranmapchan
	# uint08 bumpmapchan
	# uint08 normmapchan
	# uint08 lghtmapchan
	# uint08 envimapchan
	# uint08 glssmapchan
	# uint08 resmapchan1
	# uint08 resmapchan2
	# uint08 resmapchan3
	# uint08 resmapchan4
	# uint08 resmapchan5
	# uint08 resmapchan6
	# uint08 resmapchan7
	# uint08 resmapchan8
	pass

class SMCSURFACE:
	# string name
	# uint32 references
	# SMCREFERENCE reflist[]
	# uint16 surfmat
	pass

class SMCSURFREF:
	# uint32 vb_index
	# uint32 vb_start
	# uint32 vb_width
	# uint32 ib_index
	# uint32 ib_start
	# uint32 ib_width
	# uint32 jm_index
	pass

class SMCJOINT:
	# string name
	# uint32 id
	# uint32 parent
	# real32 matrix[16]
	# real32 quaternion[4]
	# real32 position[4]
	pass

class SMCJOINTNODE:
	# Blender.Mathutils.Vector p_world
	# Blender.Mathutils.Matrix m_world
	pass

class SMCSKELETON:
	# uint16 format
	# real32 tiplen (optional)
	# string name
	# uint32 n_joints
	# SMCJOINT joints[]
	pass

#
# JOINT TRAVERSAL CLASS
#
class SMCJointVisitor:

	# dictionary self.jntmap[joint_id] -> [jnt_index, [list of children joint ids]];
	# SMCSKELETON self.skeleton;
	# SMCJOINT self.joints[];
	# Blender.Armature self.armature;

	DEFAULT_JOINT_LENGTH = 0.1
	
	# CONSTRUCTOR
	def __init__(self, jntmap, skeleton, armature):
		"""
		
		"""
		
		self.jntmap = jntmap
		self.joints = skeleton.joints
		self.secmap = {}
		self.skeleton = skeleton
		self.armature = armature
	
	# PUBLIC METHOD: VISIT
	def visit(self, jntid, parentBone):
		"""
		Visits a joint node and recursively visits child joints.
		node -> The uint32 identifier of the node to visit.
		"""
		
		# joint must be present
		if not(jntid in self.jntmap):
			raise Exception('SMC Import Error: Joint identifier not found.')
		
		# tree must not be cyclic and joints cannot have multiple parents
		# each one of these conditions would cause us to process the same
		# joint more than once during depth first search
		if jntid in self.secmap:
			raise Exception('SMC Import Error: Invalid joint tree.')
		
		#
		nodedata = self.jntmap[jntid]
		jntindex = nodedata[0]
		children = nodedata[1]

		# if parent joint exists
		jntdata = self.joints[jntindex]
		jntnode = SMCJOINTNODE()
		if jntdata.parent != SMC.INVALID_JOINT:

			# secondary parent data must exist
			parent_id = jntdata.parent
			if not(parent_id in self.secmap):
				raise Exception('SMC Import Error: Invalid joint tree; secondary parent data is missing.')

			# get parent data
			pardata = self.joints[self.jntmap[parent_id][0]]
			parnode = self.secmap[parent_id]

			# get matrix (child)
			matrix = Array4x4ToBlenderMatrix(jntdata.matrix)
			matrix[0][3] = jntdata.position[0]
			matrix[1][3] = jntdata.position[1]
			matrix[2][3] = jntdata.position[2]

			# compute joint position in world coordinates
			if self.skeleton.format & SMC.JOINT_FORMAT_ABSOLUTE:
				jntnode.m_world = matrix
			else:
				jntnode.m_world = parnode.m_world * matrix

			# joint coordinate system
			x = [matrix[0][0], matrix[0][1], matrix[0][2]]
			y = [matrix[1][0], matrix[1][1], matrix[1][2]]
			z = [matrix[2][0], matrix[2][1], matrix[2][2]]
			joint_X_axis = Blender.Mathutils.Vector(NormalizeVector(x))
			joint_Y_axis = Blender.Mathutils.Vector(NormalizeVector(y))
			joint_Z_axis = Blender.Mathutils.Vector(NormalizeVector(z))
			
			# joint position
			jntnode.p_world = Blender.Mathutils.Vector([0.0, 0.0, 0.0])
			jntnode.p_world[0] = jntnode.m_world[0][3]
			jntnode.p_world[1] = jntnode.m_world[1][3]
			jntnode.p_world[2] = jntnode.m_world[2][3]

			# create blender bone
			bone = Blender.Armature.Editbone()
			bone.head = jntnode.p_world
			bone.tail = jntnode.p_world + SMCJointVisitor.DEFAULT_JOINT_LENGTH*joint_X_axis
			bone.roll = 0
			if parentBone != None: bone.parent = parentBone
			
			# assign bone to armature
			bonename = jntdata.name
			self.armature.bones[bonename] = bone

			# insert joint into secondary map
			self.secmap[jntid] = jntnode
			
			# recursively visit children
			for child in children:
				self.visit(child, bone)
				
		# parent joint does not exists
		else:

			# get joint matrix
			matrix = Array4x4ToBlenderMatrix(jntdata.matrix)
			matrix[0][3] = jntdata.position[0]
			matrix[1][3] = jntdata.position[1]
			matrix[2][3] = jntdata.position[2]
			matrix[3][3] = 1.0
			
			# set joint's orientation in world space
			jntnode.m_world = matrix

			# set joint's position in world space
			jntnode.p_world = Blender.Mathutils.Vector([0.0, 0.0, 0.0])
			jntnode.p_world[0] = jntdata.position[0]
			jntnode.p_world[1] = jntdata.position[1]
			jntnode.p_world[2] = jntdata.position[2]

			# get joint coordinate system
			x = [matrix[0][0], matrix[0][1], matrix[0][2]]
			y = [matrix[1][0], matrix[1][1], matrix[1][2]]
			z = [matrix[2][0], matrix[2][1], matrix[2][2]]
			joint_X_axis = Blender.Mathutils.Vector(NormalizeVector(x))
			joint_Y_axis = Blender.Mathutils.Vector(NormalizeVector(y))
			joint_Z_axis = Blender.Mathutils.Vector(NormalizeVector(z))
			
			# create blender bone
			bone = Blender.Armature.Editbone()
			bone.head = jntnode.p_world
			bone.tail = jntnode.p_world + SMCJointVisitor.DEFAULT_JOINT_LENGTH*joint_X_axis
			bone.roll = 0
			
			# assign bone to armature
			bonename = jntdata.name
			self.armature.bones[bonename] = bone
			
			# insert joint into secondary map
			self.secmap[jntid] = jntnode
			
			# recursively visit children
			for child in children:
				self.visit(child, bone)
			
#
# IMPORT SMC CLASS
#

class SMC:

	# CONSTANTS (VERTEX BUFFER FLAGS)
	VERTEX_POSITION = 0x01
	VERTEX_NORMAL   = 0x02
	VERTEX_TANGENT  = 0x04
	VERTEX_BINORMAL = 0x08
	VERTEX_WEIGHTS  = 0x10
	VERTEX_UV       = 0x20
	VERTEX_COLORS   = 0x40
	VERTEX_SKELETON = 0x80
	
	# CONSTANTS (INDEX BUFFER INDEX FORMAT)
	UINT08 = 0x00
	UINT16 = 0x01
	UINT32 = 0x02

	# CONSTANTS (INDEX BUFFER PRIMITIVE TYPE)
	TRIANGLES   = 0x00
	TRISTRIP    = 0x01
	TRISTRIPCUT = 0x02
	
	# CONSTANTS (INDEX BUFFER WINDING ORDER)
	CW  = 0x00
	CCW = 0x01
	
	# CONSTANTS (INVALID VALUES)
	INVALID_SURFMAT    = 0xFFFF
	INVALID_TEXTURE    = 0xFFFF
	INVALID_BLENDINDEX = 0xFFFF
	INVALID_JOINT      = 0xFFFFFFFF
	INVALID_INDEX      = 0xFFFFFFFF
	INVALID_JMAP_INDEX = 0xFFFFFFFF

	# CONSTANTS (TEXTURE MAPS)
	DIFFUSE_MAP     = 0x0001
	SPECULAR_MAP    = 0x0002
	BUMP_MAP        = 0x0004
	NORMAL_MAP      = 0x0008
	ALPHA_MAP       = 0x0010
	LIGHT_MAP       = 0x0020
	GLOSS_MAP       = 0x0040
	ENVIRONMENT_MAP = 0x0080
	INVALID_MAP     = 0x8000
	
	# CONSTANTS (SKELETONS)
	JOINT_FORMAT_ABSOLUTE   = 0x0001
	JOINT_FORMAT_RELATIVE   = 0x0002
	JOINT_FORMAT_MATRIX     = 0x0004
	JOINT_FORMAT_QUATERNION = 0x0008
	JOINT_FORMAT_TIP_LENGTH = 0x0010
	JOINT_FORMAT_X_BONEAXIS = 0x0020
	JOINT_FORMAT_Y_BONEAXIS = 0x0040
	JOINT_FORMAT_Z_BONEAXIS = 0x0080
	
class SMCImporter:

	# CONSTRUCTOR
	def __init__(self):
		
		self.flip_U = False
		self.flip_V = True

	# PRIVATE METHOD:
	def __readString(self, defaultValue):

		# validate length of default value
		if len(defaultValue) == 0:
			raise Exception('SMC Import Error: Default string values cannot be null.')
			
		# read length
		namelen = self.ifile.LE_read_uint32()
		if namelen == 0: return defaultValue
		
		# excessively long string
		if namelen > 0xFF:
			raise Exception('SMC Import Error: The maximum length for all names is 255 characters.')

		# read string
		name = self.ifile.read_string(namelen)
		if len(name) < 1: raise Exception('SMC Import Error: String values cannot be null.')
		
		# return string
		return name
		
	# PRIVATE METHOD: 
	def __processSMCHeader(self):

		# read magic number
		self.header = SMCHEADER()
		self.header.magic = self.ifile.LE_read_uint32()
		if self.header.magic != 0x20434D53: raise Exception('SMC Import Error: Invalid SMC file.')
		
		# read version
		self.header.major_version = self.ifile.LE_read_uint16()
		self.header.minor_version = self.ifile.LE_read_uint16()
		if self.header.major_version != 0x01:
			raise Exception('SMC Import Error: Script is meant for SMC files of versions 1.0 and lower.')
		if self.header.minor_version != 0x00:
			raise Exception('SMC Import Error: Script is meant for SMC files of versions 1.0 and lower.')
		
		# read number of buffers
		self.header.n_vbuffers = self.ifile.LE_read_uint32()
		self.header.n_ibuffers = self.ifile.LE_read_uint32()
		
		# read number of images
		self.header.n_images = self.ifile.LE_read_uint32()
		
		# read number of surfaces and materials
		self.header.n_surfaces = self.ifile.LE_read_uint32()
		self.header.n_surfmats = self.ifile.LE_read_uint32()
		
		# read number of skeletons
		self.header.n_skeletons = self.ifile.LE_read_uint32()
		if (self.header.n_skeletons != 0 and self.header.n_skeletons != 1):
			raise Exception('SMC Import Error: Invalid number of skeletons; this value must be 0 or 1.')

		# read number of joint maps
		self.header.n_jointmaps = self.ifile.LE_read_uint32()
			
		# read number of animations
		self.header.n_animations = self.ifile.LE_read_uint32()
		if self.header.n_animations != 0:
			raise Exception('SMC Import Error: Animations are not yet supported.')
		
		# read reserved values
		self.header.reserved1 = self.ifile.LE_read_uint32()
		self.header.reserved2 = self.ifile.LE_read_uint32()
		self.header.reserved3 = self.ifile.LE_read_uint32()
		self.header.reserved4 = self.ifile.LE_read_uint32()
		self.header.reserved5 = self.ifile.LE_read_uint32()
		self.header.reserved6 = self.ifile.LE_read_uint32()

		return True
	
	# PRIVATE METHOD: 
	def __processFileList(self):

		# construct filelist
		self.images = []
		for i in range(self.header.n_images):
			namelen = self.ifile.LE_read_uint32()
			if namelen < 0x001: raise Exception('SMC Import Error: Invalid filename.')
			if namelen > 0x400: raise Exception('SMC Import Error: Invalid filename.')
			namedat = self.ifile.read_string(namelen)
			self.images.append(namedat)
		
		return True

	# PRIVATE METHOD: 
	def __processVBuffers(self):

		# initialize vertex buffer list
		self.vblist = []
		
		# for each vertex buffer
		for i in range(self.header.n_vbuffers):
			
			# read vertex buffer flags
			vb = SMCVTXBUFFER()
			vb.flags = self.ifile.LE_read_uint32()
			
			# read vertex buffer name
			len = self.ifile.LE_read_uint32()
			if (len < 0x01) or (len > 0xFF): raise Exception('SMC Import Error: Invalid vertex buffer name.')
			vb.name = self.ifile.read_string(len)
		
			# read number and type of texture channels
			vb.uvchan = self.ifile.LE_read_uint16()
			if vb.uvchan > 8: raise Exception('SMC Import Error: Invalid number of UV channels.')
			vb.uvtype = self.ifile.LE_read_uint16_array(8)

			# read number of color channels
			vb.colors = self.ifile.LE_read_uint16()
			if vb.colors > 8: raise Exception('SMC Import Error: Invalid number of color channels.')

			# read number of vertices
			vb.elem = self.ifile.LE_read_uint32()
			if vb.elem == 0: raise Exception('SMC Import Error: Vertex buffers must have at least one vertex.')

			# initialize vertex data
			vb.positions = []
			vb.normals = []
			vb.tangents = []
			vb.binormals = []
			vb.blendweights = []
			vb.blendindices = []
			vb.texcoords = [[], [], [], [], [], [], [], []]
			vb.vtxcolors = [[], [], [], [], [], [], [], []]

			# read vertices
			vb.data = []
			for j in range(vb.elem):

				# read position
				if (vb.flags & SMC.VERTEX_POSITION):
					vb.positions.append(self.ifile.LE_read_real32_array(3))

				# read normal
				if (vb.flags & SMC.VERTEX_NORMAL):
					vb.normals.append(self.ifile.LE_read_real32_array(3))

				# read tangent
				if (vb.flags & SMC.VERTEX_TANGENT):
					vb.tangents.append(self.ifile.LE_read_real32_array(3))

				# read binormal
				if (vb.flags & SMC.VERTEX_BINORMAL):
					vb.binormals.append(self.ifile.LE_read_real32_array(3))

				# read blend weights
				if (vb.flags & SMC.VERTEX_WEIGHTS):
					vb.blendweights.append(self.ifile.LE_read_real32_array(8))
					vb.blendindices.append(self.ifile.LE_read_uint16_array(8))

				# read texture coordinates
				if (vb.flags & SMC.VERTEX_UV):
					for k in range(vb.uvchan):
						tmp = self.ifile.LE_read_real32_array(2)
						if self.flip_U: tmp[0] = 1.0 - tmp[0]
						if self.flip_V: tmp[1] = 1.0 - tmp[1]
						vb.texcoords[k].append(tmp)

				# read vertex colors
				if (vb.flags & SMC.VERTEX_COLORS):
					for k in range(vb.colors):
						tmp = self.ifile.LE_read_real32_array(4)
						vb.vtxcolors[k].append(tmp)

			# append vertex buffer
			self.vblist.append(vb)

		return True

	# PRIVATE METHOD: 
	def __processIBuffers(self):

		# initialize index buffer list
		self.iblist = []

		# for each index buffer
		for i in range(self.header.n_ibuffers):

			# read index buffer format
			ib = SMCIDXBUFFER()
			ib.format = self.ifile.LE_read_uint08()
			if (ib.format < SMC.UINT08) or (ib.format > SMC.UINT32):
				raise Exception('SMC Import Error: Invalid index buffer format.')

			# read index buffer primitive type
			ib.primitive = self.ifile.LE_read_uint08()
			if (ib.primitive < SMC.TRIANGLES) or (ib.primitive > SMC.TRISTRIPCUT):
				raise Exception('SMC Import Error: Invalid index buffer primitive type.')

			# read winding order
			ib.direction = self.ifile.LE_read_uint08()
			if (ib.direction != SMC.CW) and (ib.direction != SMC.CCW):
				ss = 'SMC Import Error: Invalid winding order ' + str(ib.direction) + ' at ' + str(self.ifile.tell()) + '.'
				raise Exception(ss)

			# read reserved byte
			ib.reserved = self.ifile.LE_read_uint08()
			if ib.reserved != 0: ib.reserved = 0				
				
			# read index buffer name
			len = self.ifile.LE_read_uint32()
			if (len < 0x01) or (len > 0xFF): raise Exception('SMC Import Error: Invalid index buffer name.')
			ib.name = self.ifile.read_string(len)

			# read number of indices
			ib.elem = self.ifile.LE_read_uint32()
			ib.data = []

			# read indices
			if ib.elem > 0:
				if ib.format == SMC.UINT08:
					ib.data = self.ifile.LE_read_uint08_array(ib.elem)
				elif ib.format == SMC.UINT16:
					ib.data = self.ifile.LE_read_uint16_array(ib.elem)
				elif ib.format == SMC.UINT32:
					ib.data = self.ifile.LE_read_uint32_array(ib.elem)

			# read extra byte for odd number of AMC_UINT08 indices
			if (ib.format == SMC.UINT08) and (ib.elem % 2 == 1):
				self.ifile.skip(1)			
			
			# append index buffer
			self.iblist.append(ib)

		return True

	# PRIVATE METHOD: 
	def __processSurfmats(self):

		# initialize material list
		self.surfmats = []
		
		# for each material
		for i in range(self.header.n_surfmats):

			# read material name
			sm = SMCSURFMAT()
			len = self.ifile.LE_read_uint32()
			if (len < 0x01) or (len > 0xFF): raise Exception('SMC Import Error: Invalid material name.')
			sm.name = self.ifile.read_string(len)

			# read material properties
			sm.twoside = self.ifile.LE_read_uint08()
			sm.unused1 = self.ifile.LE_read_uint08()
			sm.unused2 = self.ifile.LE_read_uint08()
			sm.unused3 = self.ifile.LE_read_uint08()
			
			# read texture references
			sm.basemap = self.ifile.LE_read_uint16()
			sm.specmap = self.ifile.LE_read_uint16()
			sm.tranmap = self.ifile.LE_read_uint16()
			sm.bumpmap = self.ifile.LE_read_uint16()
			sm.normmap = self.ifile.LE_read_uint16()
			sm.lgthmap = self.ifile.LE_read_uint16()
			sm.envimap = self.ifile.LE_read_uint16()
			sm.glssmap = self.ifile.LE_read_uint16()
			sm.resmap1 = self.ifile.LE_read_uint16()
			sm.resmap2 = self.ifile.LE_read_uint16()
			sm.resmap3 = self.ifile.LE_read_uint16()
			sm.resmap4 = self.ifile.LE_read_uint16()
			sm.resmap5 = self.ifile.LE_read_uint16()
			sm.resmap6 = self.ifile.LE_read_uint16()
			sm.resmap7 = self.ifile.LE_read_uint16()
			sm.resmap8 = self.ifile.LE_read_uint16()
			
			# read texture channel references
			sm.basemapchan = self.ifile.LE_read_uint08()
			sm.specmapchan = self.ifile.LE_read_uint08()
			sm.tranmapchan = self.ifile.LE_read_uint08()
			sm.bumpmapchan = self.ifile.LE_read_uint08()
			sm.normmapchan = self.ifile.LE_read_uint08()
			sm.lghtmapchan = self.ifile.LE_read_uint08()
			sm.envimapchan = self.ifile.LE_read_uint08()
			sm.glssmapchan = self.ifile.LE_read_uint08()
			sm.resmapchan1 = self.ifile.LE_read_uint08()
			sm.resmapchan2 = self.ifile.LE_read_uint08()
			sm.resmapchan3 = self.ifile.LE_read_uint08()
			sm.resmapchan4 = self.ifile.LE_read_uint08()
			sm.resmapchan5 = self.ifile.LE_read_uint08()
			sm.resmapchan6 = self.ifile.LE_read_uint08()
			sm.resmapchan7 = self.ifile.LE_read_uint08()
			sm.resmapchan8 = self.ifile.LE_read_uint08()
	
			# append material
			self.surfmats.append(sm)
			
		return True
	
	# PRIVATE METHOD: 
	def __processSurfaces(self):

		# initialize surface list
		self.surfaces = []
		
		# for each surface
		for i in range(self.header.n_surfaces):

			# read surface name
			surf = SMCSURFACE()
			tmp = self.ifile.LE_read_uint32()
			if (tmp < 0x01) or (tmp > 0xFF): raise Exception('SMC Import Error: Invalid surface name.')
			surf.name = self.ifile.read_string(tmp)
			if len(surf.name) < 1: raise Exception('SMC Import Error: Invalid surface name.')

			# read number of buffer references
			surf.references = self.ifile.LE_read_uint32()
			if surf.references < 1: raise Exception('SMC Import Error: A surface must have at least one buffer reference.')
						
			# read references
			surf.reflist = []
			for j in range(surf.references):
			
				# read vertex buffer index
				ref = SMCSURFREF()
				ref.vb_index = self.ifile.LE_read_uint32()
				if ref.vb_index < 0:
					raise Exception('SMC Import Error: Invalid vertex buffer reference.')
				if not(ref.vb_index < self.header.n_vbuffers):
					raise Exception('SMC Import Error: Invalid vertex buffer reference.')
				
				# read vertex buffer start index
				ref.vb_start = self.ifile.LE_read_uint32()
				if ref.vb_start < 0:
					raise Exception('SMC Import Error: Invalid vertex buffer start index.')
				if not(ref.vb_start < self.vblist[ref.vb_index].elem):
					raise Exception('SMC Import Error: Invalid vertex buffer start index.')
				
				# read vertex buffer width
				ref.vb_width = self.ifile.LE_read_uint32()
				if ref.vb_width < 1:
					raise Exception('SMC Import Error: Invalid vertex buffer surface width.')
				if self.vblist[ref.vb_index].elem < ref.vb_width:
					raise Exception('SMC Import Error: Invalid vertex buffer surface width.')
				if self.vblist[ref.vb_index].elem < (ref.vb_start + ref.vb_width):
					raise Exception('SMC Import Error: Invalid vertex buffer surface width.')

				# read index buffer index, start index, and width
				ref.ib_index = self.ifile.LE_read_uint32()
				ref.ib_start = self.ifile.LE_read_uint32()
				ref.ib_width = self.ifile.LE_read_uint32()
				
				# read joint map index (0xFFFFFFFF if not using a joint map)
				ref.jm_index = self.ifile.LE_read_uint32()

				# validate
				# note that if the index is invalid, this surface only contains points!
				if ref.ib_index != SMC.INVALID_INDEX:
				
					# validate index buffer index
					if ref.ib_index < 0:
						raise Exception('SMC Import Error: Invalid index buffer reference.')
					if not(ref.ib_index < self.header.n_ibuffers):
						raise Exception('SMC Import Error: Invalid index buffer reference.')
				
					# validate index buffer start index
					if ref.ib_start < 0:
						raise Exception('SMC Import Error: Invalid index buffer start index.')
					if not(ref.ib_start < self.iblist[ref.ib_index].elem):
						raise Exception('SMC Import Error: Invalid index buffer start index.')
				
					# validate index buffer width
					if ref.ib_width < 1:
						raise Exception('SMC Import Error: Invalid index buffer surface width.')
					if self.iblist[ref.ib_index].elem < ref.ib_width:
						raise Exception('SMC Import Error: Invalid index buffer surface width.')
					if self.iblist[ref.ib_index].elem < (ref.ib_start + ref.ib_width):
						raise Exception('SMC Import Error: Invalid index buffer surface width.')
					
				# append reference
				surf.reflist.append(ref)
			
			# read surface material
			surf.surfmat = self.ifile.LE_read_uint16()
			if surf.surfmat != SMC.INVALID_SURFMAT:
				if surf.surfmat < 0: raise Exception('SMC Import Error: Invalid material reference.')
				if not(surf.surfmat < self.header.n_surfmats): raise Exception('SMC Import Error: Invalid material reference.')

			# append surface
			self.surfaces.append(surf)

		return True

	# PRIVATE METHOD: 
	def __processSkeleton(self):

		# initialize surface list
		self.skeletons = []
		
		# for each skeleton
		for i in range(self.header.n_skeletons):

			# read format
			skel = SMCSKELETON()
			skel.format = self.ifile.LE_read_uint16()

			# validate format
			if skel.format & SMC.JOINT_FORMAT_ABSOLUTE:
				if skel.format & SMC.JOINT_FORMAT_RELATIVE:
					raise Exception('SMC Import Error: Skeletons cannot be absolute and relative.')
			elif skel.format & SMC.JOINT_FORMAT_RELATIVE:
				if skel.format & SMC.JOINT_FORMAT_ABSOLUTE:
					raise Exception('SMC Import Error: Skeletons cannot be absolute and relative.')
			else:
				raise Exception('SMC Import Error: Skeletons must be absolute or relative.')
			
			# validate format
			if skel.format & SMC.JOINT_FORMAT_MATRIX:
				if skel.format & SMC.JOINT_FORMAT_QUATERNION:
					raise Exception('SMC Import Error: Skeletons cannot use matrices and quaternions.')
			elif skel.format & SMC.JOINT_FORMAT_QUATERNION:
				if skel.format & SMC.JOINT_FORMAT_MATRIX:
					raise Exception('SMC Import Error: Skeletons cannot use matrices and quaternions.')
			else:
				raise Exception('SMC Import Error: Skeletons must use matrices or quaternions.')
			
			# validate format
			if skel.format & SMC.JOINT_FORMAT_X_BONEAXIS:
				if (skel.format & SMC.JOINT_FORMAT_Y_BONEAXIS) or (skel.format & SMC.JOINT_FORMAT_Z_BONEAXIS):
					raise Exception('SMC Import Error: Skeletons cannot use more than one bone axis.')
			elif skel.format & SMC.JOINT_FORMAT_Y_BONEAXIS:
				if (skel.format & SMC.JOINT_FORMAT_X_BONEAXIS) or (skel.format & SMC.JOINT_FORMAT_Z_BONEAXIS):
					raise Exception('SMC Import Error: Skeletons cannot use more than one bone axis.')
			elif skel.format & SMC.JOINT_FORMAT_Z_BONEAXIS:
				if (skel.format & SMC.JOINT_FORMAT_X_BONEAXIS) or (skel.format & SMC.JOINT_FORMAT_Y_BONEAXIS):
					raise Exception('SMC Import Error: Skeletons cannot use more than one bone axis.')
			else:
				raise Exception('SMC Import Error: Skeletons must define a bone axis.')

			# read tip length
			if skel.format & SMC.JOINT_FORMAT_TIP_LENGTH:
				skel.tiplen = self.ifile.LE_read_real32()
				if skel.tiplen < 0.0:
					raise Exception('SMC Import Error: Skeleton tip lengths must be positive.')
				elif skel.tiplen > 1024.0:
					raise Exception('SMC Import Error: Skeleton tip lengths must be shorter than 1024.')
			
			# read name
			skel.name = self.__readString('default')

			# read joints
			skel.n_joints = self.ifile.LE_read_uint32()
			skel.joints = []
			for j in range(skel.n_joints):

				# read name
				jnt = SMCJOINT()
				defaultValue = 'jnt_' + str(j)
				jnt.name = self.__readString(defaultValue)

				# read id
				jnt.id = self.ifile.LE_read_uint32()
				if jnt.id == SMC.INVALID_JOINT:
					raise Exception('SMC Import Error: Invalid joint identifier.')

				# read parent
				jnt.parent = self.ifile.LE_read_uint32()

				# read matrix or quaternion
				if skel.format & SMC.JOINT_FORMAT_MATRIX:
					jnt.matrix = self.ifile.LE_read_real32_array(16)
				elif skel.format & SMC.JOINT_FORMAT_QUATERNION:
					jnt.quaternion = self.ifile.LE_read_real32_array(4)

				# read position
				jnt.position = self.ifile.LE_read_real32_array(4)
				
				# insert joint
				skel.joints.append(jnt)

			# insert skeleton
			self.skeletons.append(skel)
			
		return True

	# PRIVATE METHOD:
	def __processJointMap(self):

		# initialize surface list
		self.jntmaplist = []
		
		# for each joint map
		for i in range(self.header.n_jointmaps):
			n_items = self.ifile.LE_read_uint32()
			items = []
			for j in range(n_items):
				temp = self.ifile.LE_read_uint32()
				items.append(temp)
			self.jntmaplist.append(items)
	
	# PRIVATE METHOD: 
	def __processAnimList(self):
		
		return True

	# PRIVATE METHOD:
	def __buildVBuffer(self, surf):

		# for each reference
		for index, ref in enumerate(surf.reflist):
		
			# create name for mesh object
			meshname = surf.name
			meshname += '_ref_'
			meshname += str(index)

			# create Blender mesh for this vertex buffer
			mesh = Blender.Mesh.New()
			mesh.name = meshname

			# vertex and index buffers
			vb = self.vblist[ref.vb_index]
			ib = self.iblist[ref.ib_index]
			
			# positions
			verts = []
			for dst_index in range(ref.vb_width):
				src_index = ref.vb_start + dst_index
				verts.append(vb.positions[src_index])
			mesh.verts.extend(verts)

			# normals
			if vb.flags & SMC.VERTEX_NORMAL:
				for vertex in mesh.verts:
					nx = vb.normals[ref.vb_start + vertex.index][0]
					ny = vb.normals[ref.vb_start + vertex.index][1]
					nz = vb.normals[ref.vb_start + vertex.index][2]
					vertex.no = Blender.Mathutils.Vector(nx, ny, nz)
			
			# texture coordinates
			uvmap = [[], [], [], [], [], [], [], []]
			if vb.flags & SMC.VERTEX_UV:

				# for each UV channel
				for i in range(8):
				
					# copy UVs if UV map channel exists
					if vb.uvtype[i] != SMC.INVALID_MAP:

						# copy UVs
						for dst_index in range(ref.vb_width):
							src_index = ref.vb_start + dst_index
							uvmap[i].append(vb.texcoords[i][src_index])

			# faces
			faces = []
			if ref.ib_index != SMC.INVALID_INDEX:

				# from triangle list
				if ib.primitive == SMC.TRIANGLES:
				
					# must have triangles
					if ref.ib_width < 3:
						raise Exception('SMC Import Error: The number of triangle indices must be greater than three.')
					if ref.ib_width % 3:
						raise Exception('SMC Import Error: The number of triangle indices must be divisible by three.')
					
					# build triangles
					for i in range((ref.ib_width / 3)):
					
						# triangle indices
						src_index = ref.ib_start + i * 3
						a = ib.data[src_index + 0]
						b = ib.data[src_index + 1]
						c = ib.data[src_index + 2]
						if not(a < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						if not(b < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						if not(c < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						
						# insert triangle
						if (a != b) and (a != c) and (b != c):
							if ib.direction == SMC.CW:
								faces.append([a, b, c])
							else:
								faces.append([a, c, b])
					
				elif ib.primitive == SMC.TRISTRIP:
	
					# first triangle
					a = ib.data[ref.ib_start + 0]
					b = ib.data[ref.ib_start + 1]
					c = ib.data[ref.ib_start + 2]
					if not(a < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
					if not(b < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
					if not(c < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
					
					# insert first triangle
					if (a != b) and (a != c) and (b != c):
						if ib.direction == SMC.CW:
							faces.append([a, b, c])
						else:
							faces.append([a, c, b])
					
					# reamaining triangles
					for i in range(3, ref.ib_width):
					
						# triangle indices
						a = b
						b = c
						c = ib.data[ref.ib_start + i]
						if not(c < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						
						# insert triangle
						if (a != b) and (a != c) and (b != c):
							if i % 2:
								if ib.direction == SMC.CW:
									faces.append([a, c, b])
								else:
									faces.append([a, b, c])
							else:
								if ib.direction == SMC.CW:
									faces.append([a, b, c])
								else:
									faces.append([a, c, b])
						
				elif ib.primitive == SMC.TRISTRIPCUT:

					# maintain a tristrip index
					tristrip_data = []
					tristrip_curr = []
					
					# value of restart index depends on the data type
					strip_index = 0xFFFFFFFF
					if ib.format == SMC.UINT08:
						strip_index = 0xFF
					elif ib.format == SMC.UINT16:
						strip_index = 0xFFFF
					elif ib.format == SMC.UINT32:
						strip_index = 0xFFFFFFFF
						
					# create a list of triangle strips
					for i in range(ref.ib_width):
					
						temp = ib.data[ref.ib_start + i]
						if temp == strip_index:
							if len(tristrip_curr) < 3: raise Exception('SMC Import Error: Not enough indices for a triangle strip.')
							tristrip_data.append(tristrip_curr)
							tristrip_curr = []
						else:
							tristrip_curr.append(temp)
							if ((i + 1) == ref.ib_width): # last index is not an strip index
								tristrip_data.append(tristrip_curr)
								tristrip_curr = []								

					# process triangle strips
					for tristrip in tristrip_data:

						# first triangle
						a = tristrip[0]
						b = tristrip[1]
						c = tristrip[2]
						if not(a < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						if not(b < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						if not(c < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
						if (a != b) and (a != c) and (b != c):
							if ib.direction == SMC.CW: faces.append([a, b, c])
							else: faces.append([a, c, b])
						
						# remaining triangles
						for i in range(3, len(tristrip)):
							a = b
							b = c
							c = tristrip[i]
							if not(c < ref.vb_width): raise Exception('SMC Import Error: Triangle index out of bounds.')
							if (a != b) and (a != c) and (b != c):
								if i % 2:
									if ib.direction == SMC.CW: faces.append([a, c, b])
									else: faces.append([a, b, c])
								else:
									if ib.direction == SMC.CW: faces.append([a, b, c])
									else: faces.append([a, c, b])

				# construct blender mesh faces
				mesh.faces.extend(faces)
				
				# smooth vertex normals
				if vb.flags & SMC.VERTEX_NORMAL:
					for face in mesh.faces:
						face.smooth = 1

				# assign texture coordinates
				if vb.flags & SMC.VERTEX_UV:
	
					# for each UV channel
					for i in range(8):

						# if UV channel exists
						if vb.uvtype[i] != SMC.INVALID_MAP:
						
							# create UV layer
							mapname = 'uvmap_channel_' + str(i)
							mesh.addUVLayer(mapname)
							mesh.activeUVLayer = mapname
					
							# assign texture coordinates to faces
							# WARNING: THIS IS OLD CODE THAT CAUSED ROTATED UV COORDINATES!!!
							#for face in mesh.faces:
							#	a = faces[face.index][0]
							#	b = faces[face.index][1]
							#	c = faces[face.index][2]
							#	uv_a = Mathutils.Vector(uvmap[i][a][0], uvmap[i][a][1])
							#	uv_b = Mathutils.Vector(uvmap[i][b][0], uvmap[i][b][1])
							#	uv_c = Mathutils.Vector(uvmap[i][c][0], uvmap[i][c][1])
							#	face.uv = [ uv_a, uv_b, uv_c ]

							# set sticky per-vertex UV coordinates
							mesh.vertexUV = True
							for j in range(len(mesh.verts)):
								mesh.verts[j].uvco = Blender.Mathutils.Vector(uvmap[i][j])
							mesh.update()
							
							# set face UV coordinates
							mesh.faceUV = True;
							for face in mesh.faces:
								face.uv = [v.uvco for v in face.verts];
								face.smooth = 1
							mesh.update()
								
			# update Blender mesh object
			mesh.update()
        
			# add mesh to current scene and make mesh active
			scene = Blender.Scene.GetCurrent()
			meshobject = scene.objects.new(mesh, meshname)
			scene.objects.active = meshobject
			self.meshlist.append(meshobject)

			# assign material to mesh object
			if surf.surfmat != SMC.INVALID_SURFMAT:
				meshobject.colbits = 1
				meshobject.setMaterials([self.materials[surf.surfmat]])
				mesh.update()
		
			# blend weights
			# NOTE: blend weights must be added after a mesh has been associated with a mesh object!
			bidict = {}
			if vb.flags & SMC.VERTEX_WEIGHTS:
			
				# for each set of blendweights and blendindices
				for dst_index in range(ref.vb_width):

					src_index = ref.vb_start + dst_index
					for i in range(8):
					
						# get blend weight and blend index
						bw = vb.blendweights[src_index][i]
						bi = vb.blendindices[src_index][i]

						# if blend index is valid
						if bi != SMC.INVALID_BLENDINDEX:
						
							# if this surface reference uses a joint map
							# remap the blend index using the map
							if ref.jm_index != SMC.INVALID_JMAP_INDEX:
							
								if not(ref.jm_index < len(self.jntmaplist)):
									raise Exception('SMC Import Error: Joint map index out of range.')
									
								# given a blend index, look it up in an array to get new blend index
								if not(bi < len(self.jntmaplist[ref.jm_index])):
									error = 'SMC Import Error: Joint map blending index '
									error = error + str(bi)
									error = error + ' out of range. The joint map only has '
									error = error + str(len(self.jntmaplist[ref.jm_index]))
									error = error + ' elements.'
									raise Exception(error)

								# remap blend index
								bi = self.jntmaplist[ref.jm_index][bi]

							# associate blend weight with blend index
							if not (bi in bidict): bidict[bi] = []
							bidict[bi].append([dst_index, bw])

				# for each vertex weight map
				for dk, dv in bidict.iteritems():
				
					# create vertex group and assign weights
					mapname = 'jnt_' + ('%(value)03d' % {'value':dk}) # + str(dk)
					mesh.addVertGroup(mapname)
					for item in dv:
						try:
							mesh.assignVertsToGroup(mapname, [item[0]], item[1], Blender.Mesh.AssignModes.ADD)#REPLACE)
						except Exception as e:
							print('item = ' + str(item[0]) + ', ' + str(item[1]))
							print('vertices = ' + str(vb.elem) + ', ' + str(len(mesh.verts)))
							raise e
						
	# PRIVATE METHOD:
	def __buildMeshTextures(self):

		# construct textures from filelist using relative directories
		# this is why we preface filename with '//'
		# see http://www.blender.org/documentation/blender_python_api_2_59_0/bpy.path.html
		self.texlist = []
		for index, filename in enumerate(self.images):
			try:
				# create texture name based on index
				name = 'texture_' + str(index)
				# create texture
				temp = Blender.Image.Load('//' + filename)
				texture = Blender.Texture.New(name)
				texture.setImage(temp)
				# append data
				self.texlist.append(texture)
			except Exception as e:
				self.texlist.append(None)
				print('Failed to load texture file ' + filename + '.')
	
	def __buildMeshMaterials(self):

		def isTextureValid(textureIndex):
			if textureIndex == SMC.INVALID_TEXTURE: return False
			if not (textureIndex < len(self.texlist)): return False
			if self.texlist[textureIndex] is None: return False
			return True
		
		# for each surface material
		self.materials = []
		for surfmat in self.surfmats:

			# create new material
			# set material to shadeless so we can see texture using Blender GLSL Materials 
			mat = Blender.Material.New(surfmat.name)
			mat.setMode(Blender.Material.Modes['SHADELESS'])

			# each material supports up to ten texture layters
			index = 0
			if isTextureValid(surfmat.basemap):
				mat.setTexture(index, self.texlist[surfmat.basemap], Texture.TexCo.UV, Texture.MapTo.COL)
				mattex = mat.getTextures()
				mattex[index].uvlayer = 'uvmap_channel_' + str(surfmat.basemapchan)
				index = index + 1
			if isTextureValid(surfmat.specmap):
				mat.setTexture(index, self.texlist[surfmat.specmap], Texture.TexCo.UV, Texture.MapTo.SPEC)
				mattex = mat.getTextures()
				mattex[index].uvlayer = 'uvmap_channel_' + str(surfmat.specmapchan)
				index = index + 1
			if isTextureValid(surfmat.normmap):
				mat.setTexture(index, self.texlist[surfmat.normmap], Texture.TexCo.UV, Texture.MapTo.NOR)
				mattex = mat.getTextures()
				mattex[index].uvlayer = 'uvmap_channel_' + str(surfmat.normmapchan)
				index = index + 1

			# append material
			self.materials.append(mat)
		
	# PRIVATE METHOD:
	def __buildMeshObjects(self):

		# save blender mesh objects
		self.meshlist = []
		
		# for each surface
		for surf in self.surfaces:
		
			self.__buildVBuffer(surf)

		return True
	
	def __buildArmatureObjects(self):

		# for each skeleton
		for skel in self.skeletons:

			# keep track of all root nodes
			root_nodes = []
			for jnt in skel.joints:
				if jnt.parent == SMC.INVALID_JOINT:
					root_nodes.append(jnt.id)
					
			# must have at least one root node
			if len(root_nodes) == 0:
				raise Exception('SMC Import Error: A skeleton was defined with no root node.')
				
			# now that we know we have good root nodes, let's create a diction-
			# ary where given a joint ID we can index its data and find out how
			# many children joint IDs it has
			jntmap = {}
			for (jnt_index, jnt) in enumerate(skel.joints):
			
				# joint identifier must be unique
				if jnt.id in jntmap:
					raise Exception('SMC Import Error: Joint identifiers must be unique.')

				# insert joint to map with empty child list
				jntmap[jnt.id] = [jnt_index, []]
			
			# insert joints into their parent's list of children
			for jnt in skel.joints:
				if jnt.parent != SMC.INVALID_JOINT:
					if not(jnt.parent in jntmap): raise Exception('SMC Import Error: Invalid parent joint identifier.')
					jntmap[jnt.parent][1].append(jnt.id)
					
			# create blender armature
			armature = Blender.Armature.New(skel.name)
			armature.drawType = Blender.Armature.STICK
			armature.envelopes = False
			armature.vertexGroups = False

			# create blender armature object
			scene = Blender.Scene.GetCurrent()
			armatureObjectName = skel.name + '_object'
			armatureObject = scene.objects.new(armature, armatureObjectName)

			# set armature object to use vertex groups (not envelopes)
			for meshobj in self.meshlist:
				mod = meshobj.modifiers.append(Modifier.Types.ARMATURE)
				mod[Blender.Modifier.Settings.OBJECT] = armatureObject
				mod[Blender.Modifier.Settings.ENVELOPES] = False
				mod[Blender.Modifier.Settings.VGROUPS] = True
	
			# make armature editable before adding bones
			armature.makeEditable()

			# traverse joints to add bones
			jvisitor = SMCJointVisitor(jntmap, skel, armature)
			for root in root_nodes: jvisitor.visit(root, None)

			# update armature
			armature.update()
			
			# parent mesh objects to armature so it can modify the meshes
			armatureObject.makeParent(self.meshlist)
			
		return True

	# PUBLIC METHOD: IMPORT
	def run(self, filename):

		# open file
		self.ifile = InputFileStream()
		self.ifile.open(filename)
		
		# file processing
		if self.__processSMCHeader() == False: return False
		if self.__processFileList() == False: return False
		if self.__processVBuffers() == False: return False
		if self.__processIBuffers() == False: return False
		if self.__processSurfmats() == False: return False
		if self.__processSurfaces() == False: return False
		if self.__processSkeleton() == False: return False
		if self.__processJointMap() == False: return False
		if self.__processAnimList() == False: return False

		# model construction
		self.__buildMeshTextures()
		self.__buildMeshMaterials()
		self.__buildMeshObjects()
		self.__buildArmatureObjects()
		
		# success
		print "SMC import successful."
		Window.RedrawAll()
		return True

#
# IMPORT SMC
#

def importSMC(filename):

	obj = SMCImporter()
	obj.run(filename)

#
# CONTROL EXECUTION
# main() is called if and only if module is not imported
#

def main():

	Blender.Window.FileSelector(importSMC, "Import SMC", '*.smc')

if __name__ == '__main__':
	
    main()
```

[dw7-1.zip](https://xentaxbackup.github.io/file/6591_dw7-1.zip)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-04T02:29:15+00:00
- Post Title: blender import SCRIPT->3d max script

blender -> fbx -> 3ds max should preserve uv data.

jesus you posted my entire blender script lol, looking at my own code scares me.
