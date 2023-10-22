## Post #1
- Username: Jigglebone
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 08, 2011 11:43 pm
- Post datetime: 2011-07-18T05:59:12+00:00
- Post Title: writing BRRES importer help (for blender)

Im using this reference: [http://wiki.tockdom.de/index.php?title= ... _Format%29](http://wiki.tockdom.de/index.php?title=BRRES_%28File_Format%29)

First could you refresh my memory? I know Type "char" is 1 byte, but whats "uN"? Is it unsigned, N bits of lenght (eg. u32)? Im a Python user and we dont have that syntax here.
Also, what is "padding"? Should it just be skipped?
## Post #2
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-07-18T17:06:00+00:00
- Post Title: writing BRRES importer help (for blender)

Padding is stuff that is presumed to be useless. You can either completely skip it or just put it into a dummy variable.

u32 = unsigned int; 4 bytes
u16 = unsigned short; 2 bytes
u8 = byte; 1 byte
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-18T18:03:13+00:00
- Post Title: writing BRRES importer help (for blender)

How are signed ints/shorts are usually denoted?
How is a float usually distinguished from a long or an int?
Also, for practical purposes, can one simply treat an int as a long?
## Post #4
- Username: Jigglebone
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 08, 2011 11:43 pm
- Post datetime: 2011-07-18T19:09:59+00:00
- Post Title: writing BRRES importer help (for blender)

OK. Proof of concept

```
"""
Name: 'BRRES (*.brres)...'
Blender: 249
Group: 'Import'
Tooltip: 'Import *.brres files'
"""
__author__ = "jigglebone"
__version__ = '0.0.1'
__bpydoc__ = """ \
Import *.brres files
"""

import Blender
import struct
import sys, os

def readFile(filepath):
	file = open(filepath, 'rb')
	
	# char[4] - 'bres' in ASCII; File identifier
	datachunk = file.read(4)
	if datachunk != "bres":
		print "Invalid BRRES file, or file corrupt!"
		return
	
	# u16  - Byte order mark. 0xFEFF is the big endian byte order, 0xFFFE is little endian.
	endian = None
	
	datachunk = file.read(2)
	endianness = struct.unpack('H', datachunk)[0]
	
	if endianness == 0xFEFF:
		endian = ">"
	elif endianness == 0xFFFE:
		endian = "<"
	else:
		print "file corrupt"
		return
	
	# u16 - Padding.
	file.seek(2, 1) # move cursor 2 bytes from current position (set by 1)
	
	# u32 - Length of the file in bytes.
	datachunk = file.read(4)
	filelenght = struct.unpack(endian + 'I', datachunk)[0]
	
	# u16 - Offset to root section relative to start. (0x0010)
	datachunk = file.read(4)
	offset = struct.unpack(endian + 'H', datachunk)[0]
	
	# u16 -Number of sections (including root).
	datachunk = file.read(4)
	sectioncount = struct.unpack(endian + 'H', datachunk)[0]
	
	# The root section of the brres file contains all pointers to files and filenames The header of the root is 0x8 in length.
	# char[4] - 'bres' in ASCII; File identifier
	datachunk = file.read(4)
	if datachunk != "root":
		print "file corrupt!"
		return
	
	# u32 - Length of section in bytes.
	datachunk = file.read(4)
	rootlenght = struct.unpack(endian + 'I', datachunk)[0]
	
	# BRRES Index Group
	# u32 - Length of group in bytes.
	datachunk = file.read(4)
	grouplenght = struct.unpack(endian + 'I', datachunk)[0]
	
	# u32 - Number in group.
	datachunk = file.read(4)
	numberingroup = struct.unpack(endian + 'I', datachunk)[0]
	
	# Under construction...

def main():
	def fileSelector(filepath):
		if filepath and not Blender.sys.exists(filepath):
			Blender.Draw.PupMenu("Error%%t|The file %s does not exist." % filepath)
		else:
			Blender.Window.WaitCursor(1)
			readFile(filepath)
			Blender.Window.WaitCursor(0)
	
	Blender.Window.FileSelector(fileSelector, 'OK', Blender.sys.makename(ext = '.brres'))

if __name__ == "__main__":
	main()

```


I hope you dont mind more questions.
Forgive my english, "Offset to root section relative to start." means "location of "root" measured from beginning of file"?

Also, there's "Number of sections (including root). " and then the doc says "This header is then followed by a BRRES Index Group.". There's one index group right? And they entries in that "group" are the sections mentioned earlier?

And in the "BRRES Index Group" page it says "Number in group.". What does that mean?

A lot of questions...
## Post #5
- Username: Jigglebone
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 08, 2011 11:43 pm
- Post datetime: 2011-07-20T11:10:28+00:00
- Post Title: writing BRRES importer help (for blender)

ahem...
## Post #6
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-08-31T20:45:23+00:00
- Post Title: writing BRRES importer help (for blender)

this would be interesting to have given the pain it is to export somtimes.
## Post #7
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-03-17T05:25:28+00:00
- Post Title: writing BRRES importer help (for blender)

I found someone's python script but it won't work.Can u check it for me Jigglebone?

```
""" 
Name: 'BRRES File Import (.brres)'
Blender: 245
Group: 'Import'
Tooltip: 'Import from BRRES file format (.brres)'
"""

# import needed stuff
import Blender
import struct
from common import Struct
import os.path
import math
from math import *
from Blender import Mathutils
from Blender.Mathutils import *

# imports a brres file to the current scene
def import_brres(path):
    
    dataf = open(path,'rb')
    data = dataf.read()
    dataf.close()
    bres = Bres()
    bres._load(data)
    return "END"


# load the model
def fileCallback(filename):
    error = import_brres(filename)
    if error!="":
        Blender.Draw.PupMenu("An error occured during import: " + error + "|Not all data might have been imported succesfully.", 2)

Blender.Window.FileSelector(fileCallback, 'Import')




class Bres:
    class BresHeader(Struct):
        __endian__ = Struct.BE
        def __format__(self):
            self.tag = Struct.string(4)
            self.version = Struct.uint32
            self.size = Struct.uint32
            self.root_offset = Struct.uint16
            self.num_chunks = Struct.uint16
    class BresRootHeader(Struct):
        __endian__ = Struct.BE
        def __format__(self):
            self.tag = Struct.string(4)
            self.size = Struct.uint32
    class BresCommonHeader(Struct):
        __endian__ = Struct.BE
        def __format__(self):
            self.tag = Struct.string(4)
            self.size = Struct.uint32
            self.version = Struct.int32
            self.bres_offset = Struct.int32
    class ResDict(Struct):
        __endian__ = Struct.BE
        def __format__(self):
            self.size = Struct.uint32
            self.count = Struct.uint32
    class ResEntry(Struct):
        __endian__ = Struct.BE
        def __format__(self):
            self.id = Struct.uint16
            self.pad = Struct.int16
            self.left_index = Struct.uint16
            self.right_index = Struct.uint16
            self.string_offset = Struct.int32
            self.data_offset = Struct.int32
    def __init__(self):
        self.MDL0Files = []
    def _load(self, data):
        offset = 0
        
        header = self.BresHeader()
        blah = len(header)
        header.unpack(data[offset:offset + len(header)])
        print "BRRES Header, tag=%s version=%s size=%s root offset=%s chunks=%srn" % (header.tag, header.version, header.size, header.root_offset, header.num_chunks),
        offset += len(header)
        if offset != header.root_offset:
            print "warning: skipping to root offset"
            offset = header.root_offset
            
        root_header = self.BresRootHeader()
        root_header.unpack(data[offset:offset + len(root_header)])
        offset += len(root_header)
        print "BRRES ROOT header, tag=%s size=%srn" % (root_header.tag, root_header.size),
        print "Root Group:rn"
        (offset, root_dict) = self._loadDict(data, offset)
        
        for e in root_dict.children:
            if e.id == 0xFFFF:
                continue
            print "Child Dict: %srn" % (e.name),
            offset = e.total_data_offset; 
            (offset, dict) = self._loadDict(data, offset)
            for c in dict.children:
                e.children.append(c)
            
        for g in root_dict.children:
            if g.id == 0xFFFF:
                continue
            for e in g.children:
                if e.id == 0xFFFF:
                    continue
                bc = self.BresCommonHeader()
                bc.unpack(data[e.total_data_offset: e.total_data_offset + len(bc)])
                bc.name = e.name
                #print "BRES HEADER, TAG=%s VERSION=%s NAME=%s" % (bc.tag, bc.version, bc.name)
                if bc.tag == "MDL0":
                    m = self.MDL0()
                    m._load(self, data, e.total_data_offset)

    def _loadEntry(self, data, offset, dict):
        entry = self.ResEntry()
        entry.unpack(data[offset:offset + len(entry)])
        entry.total_data_offset = 0 #dict.offset + entry.data_offset
        entry.total_string_offset = dict.offset + entry.string_offset
        entry.name = ''
        entry.children = []
        if entry.data_offset != 0:
            entry.total_data_offset = dict.offset + entry.data_offset
        if entry.string_offset != 0:
            strlen = struct.unpack_from("B", data[entry.total_string_offset-1])[0]
            entry.name = data[entry.total_string_offset:entry.total_string_offset+strlen]
        dict.children.append(entry)
        entry.dict = dict
        offset += len(entry)
        if(entry.id != 0xFFFF):
            print "E %s: %s so: %s do: %srn" % (entry.id, entry.name, entry.total_string_offset, entry.total_data_offset),
        return (offset, entry)
    def _loadDict(self, data, offset):
        dict = self.ResDict()
        dict.unpack(data[offset:offset + len(dict)])
        dict.offset = offset
        dict.children = []
        offset += len(dict)
        print "D %s rn" % (dict.count),
        for c in xrange(dict.count+1):
            (offset, entry) = self._loadEntry(data, offset, dict)
        return (offset, dict)
    
    class MDL0:
        class MDL0Properties(Struct):
            __endian__ = Struct.BE
            def __format__(self):
                self.unk0 = Struct.uint32
                self.size = Struct.uint32
                self.mdl0offset = Struct.int32
                self.unk1 = Struct.int32
                self.unk2 = Struct.int32
                self.vertice_count = Struct.uint32
                self.face_count = Struct.uint32
                self.unk3 = Struct.int32
                self.chunk_count = Struct.uint32
                self.unk4 = Struct.int16
                self.unk5 = Struct.int16
                self.dataoffset = Struct.uint32
                self.box_min_x = Struct.float
                self.box_min_y = Struct.float
                self.box_min_z = Struct.float
                self.box_max_x = Struct.float
                self.box_max_y = Struct.float
                self.box_max_z = Struct.float
            
        class MDL0Bone(Struct):
            __endian__ = Struct.BE
            def __format__(self):
                self.header_size = Struct.uint32
                self.mdl0offset = Struct.int32
                self.string_offset = Struct.int32
                self.index = Struct.int32
                self.nodeid = Struct.int32
                self.flags = Struct.uint32
                self.pad1 = Struct.uint32
                self.pad2 = Struct.uint32
                self.scale_x = Struct.float
                self.scale_y = Struct.float
                self.scale_z = Struct.float
                self.rot_x = Struct.float
                self.rot_y = Struct.float
                self.rot_z = Struct.float
                self.trans_x = Struct.float
                self.trans_y = Struct.float
                self.trans_z = Struct.float
                self.box_min_x = Struct.float
                self.box_min_y = Struct.float
                self.box_min_z = Struct.float
                self.box_max_x = Struct.float
                self.box_max_y = Struct.float
                self.box_max_z = Struct.float
                self.parent_offset = Struct.int32
                self.next_offset = Struct.int32
                self.prev_offset = Struct.int32
                self.add_offset = Struct.int32
                
                self.trans0 = Struct.float
                self.trans1 = Struct.float
                self.trans2 = Struct.float
                self.trans3 = Struct.float
                self.trans4 = Struct.float
                self.trans5 = Struct.float
                self.trans6 = Struct.float
                self.trans7 = Struct.float
                self.trans8 = Struct.float
                self.trans9 = Struct.float
                self.trans10 = Struct.float
                self.trans11 = Struct.float
                
                self.transi0 = Struct.float
                self.transi1 = Struct.float
                self.transi2 = Struct.float
                self.transi3 = Struct.float
                self.transi4 = Struct.float
                self.transi5 = Struct.float
                self.transi6 = Struct.float
                self.transi7 = Struct.float
                self.transi8 = Struct.float
                self.transi9 = Struct.float
                self.transi10 = Struct.float
                self.transi11 = Struct.float
        class MDL0Vertex(Struct):
            __endian__ = Struct.BE
            def __format__(self):
                self.size = Struct.uint32
                self.mdl0offset = Struct.int32
                self.data_offset = Struct.int32
                self.string_offset = Struct.int32
                self.index = Struct.int32
                self.isxyz = Struct.int32
                self.type = Struct.int32
                self.divisor = Struct.uint8
                self.stride = Struct.uint8
                self.vertice_count = Struct.uint16
                self.box_min_x = Struct.float
                self.box_min_y = Struct.float
                self.box_min_z = Struct.float
                self.box_max_x = Struct.float
                self.box_max_y = Struct.float
                self.box_max_z = Struct.float
                self.pad1 = Struct.int32
                self.pad2 = Struct.int32
                
        def _load(self, bres, data, offset):
            header = Bres.BresCommonHeader()
            header.unpack(data[offset:offset+len(header)])
            if header.tag != "MDL0":
                print "not a mdl0 file? tag is wrong!"
            if header.version != 9 and header.version != 11:
                print "unkown mdl0 version? version is %s" % header.version
            startoffset = offset
            
            
            offset += len(header)
            
            groups = []
            numgroups = 11
            
            if header.version == 11:
                numgroups = 14 
            
            offset_table = {}
            for c in xrange(numgroups):
                goffset = struct.unpack(">I", data[offset+c*4:offset+((1+c)*4)])[0]
                offset_table[c] = goffset
                
                #if(goffset != 0):
                    #group = Bres.ResDict()
                    #(goffset, group) = bres._loadDict(data, offset + goffset)
            print "offsets: %s" % offset_table
            offset += numgroups * 4
            print "offset: %s" % offset
            props = self.MDL0Properties()
            props.unpack(data[offset:offset+len(props)])
            offset += len(props)
            print "MDL0 Properties: Vertice %s Face %s Node %s box [%s,%s,%s] box [%s,%s,%s]rn" % (props.vertice_count, props.face_count, props.chunk_count, props.box_min_x, props.box_min_y,props.box_min_z, props.box_max_x,props.box_max_y,props.box_max_z),
            
            index_table = {}
            element_count = struct.unpack(">I", data[offset:offset+4])[0]
            offset += 4;
            for c in xrange(element_count):
                index_table[c] = struct.unpack(">I", data[offset+(c*4):offset+(c*4)+4])[0]
            offset += element_count * 4;
            print "Index Table: %srn" % index_table,
            
            
            '''#Definitions
            (offset, group) = bres._loadDict(data, offset)
            self.Type2Data = []
            self.Type3Data = []
            self.Type4Data = []
            self.Type5Data = []
            
            for c in group.children:
                if c.id != 0xFFFF:
                    goffset = c.total_data_offset
                    type = struct.unpack("B", data[goffset])[0]
                    
                    if type == 2:
                        goffset += 1
                        print "pos %s" % goffset
                        boneIndex = struct.unpack(">H", data[goffset:goffset+2])[0]
                        goffset += 2
                        parentID = struct.unpack(">H", data[goffset:goffset+2])[0]
                        goffset += 2
                        print "type 2 data read. bone Index %s parent ID %srn" % (boneIndex, parentID),
                        
                    if type == 4:
                        goffset += 1;
                        matID = struct.unpack(">H", data[goffset:goffset+2])[0]
                        goffset += 2
                        polyID = struct.unpack(">H", data[goffset:goffset+2])[0]
                        goffset += 2
                        boneID = struct.unpack(">H", data[goffset:goffset+2])[0]
                        goffset += 2
                        val4 = struct.unpack("B", data[goffset])[0]
                        print "type 4 data read. mat %s poly %s bone %s val4 %srn" % (matID, polyID, boneID, val4),'''
            offset = startoffset + offset_table[1] #skip to bones
            #Bones
            print "Reading Bone Group... from %s" % offset
            bones = {}
            (offset, group) = bres._loadDict(data, offset)
            for c in group.children:
                if c.id == 0xFFFF:
                    continue
                doffset = c.total_data_offset
                bone = self.MDL0Bone()
                bone.unpack(data[doffset:doffset+len(bone)])
                bone.name = ''
                bone.offset = doffset
                if bone.string_offset != 0:
                    strlen = struct.unpack_from("B", data[doffset+bone.string_offset-1])[0]
                    bone.name = data[doffset+bone.string_offset:doffset+bone.string_offset+strlen]
                bone.scale = Vector([bone.scale_x, bone.scale_y, bone.scale_z])
                bone.rot = Vector([bone.rot_x, bone.rot_y, bone.rot_z])
                bone.trans = Vector([bone.trans_x, bone.trans_y, bone.trans_z])
                bones[doffset] = bone #store offset for parent calc.
                print "load bone: name %s index %s nodeid %s scale [%s]rn rot [%s] trans [%s]rn" % (bone.name, bone.index, bone.nodeid, bone.scale, bone.rot, bone.trans),
            
            for b in bones:
                bone = bones[b]
                bone.parent = None
                if bone.parent_offset < 0:
                    #print bone
                    bone.parent = bones[bone.offset+bone.parent_offset]
                    #print "Parent %s Bone %s" % (bone.parent.name, bone.name),
            
            scn = Blender.Scene.GetCurrent()        
            mesh = Blender.Mesh.New("MilkShape3D Mesh"+str(props.vertice_count))
            meshOb = scn.objects.new(mesh)
            
            armOb = Blender.Object.New('Armature', "Skeleton"+str(props.vertice_count))
            armature = Blender.Armature.New("Skeleton"+str(props.vertice_count))
            armature.drawType = Blender.Armature.STICK
            armOb.link(armature)
            scn.objects.link(armOb)
            armOb.makeParentDeform([meshOb])
            armature.makeEditable()
            armature.restPosition = True
            
            for i in bones:
                b = bones[i]
                
                
                bonex = Blender.Armature.Editbone()
                bonex.name = b.name
                armature.bones[b.name] = bonex
                if(b.parent == None):
                    
                    bonex.head = Vector(b.trans)
                    bonex.matrix = self.RM(b.rot)
                    bvec = bonex.tail - bonex.head
                    bvec.normalize()
                    bonex.tail = bonex.head + 0.1 * bvec
                
                
            for i in bones:
                b = bones[i]
                bonex = armature.bones[b.name]
                if(b.parent != None):
                    bonex.parent = armature.bones[b.parent.name]
                    #print "setting parent %srn" % armature.bones[b.parent.name]
                    bonex.head =  Vector(b.trans) * bonex.parent.matrix + bonex.parent.head
                    tempM = self.RM(b.rot) * bonex.parent.matrix
                    tempM.transpose;
                    bonex.matrix = tempM
                else:
                    bonex.head = Vector(b.trans)
                    bonex.matrix = self.RM(b.rot)
                    
                bvec = bonex.tail - bonex.head
                bvec.normalize()
                bonex.tail = bonex.head + 0.1 *bvec
            armature.update();
            
            
            
            scn = Blender.Scene.GetCurrent()
            #lets load some vertices
            offset = startoffset + offset_table[2]
            print "Reading vert Group... from %srn" % offset
            (offset, group) = bres._loadDict(data, offset)
            for c in group.children:
                if c.id == 0xFFFF:
                    continue
                
                doffset = c.total_data_offset
                vert = self.MDL0Vertex()
                vert.unpack(data[doffset:doffset+len(vert)])
                vert.offset = doffset
                vert.name = ''
                
                if vert.string_offset != 0:
                    strlen = struct.unpack_from("B", data[doffset+vert.string_offset-1])[0]
                    vert.name = data[doffset+vert.string_offset:doffset+vert.string_offset+strlen]
                mesh = Blender.Mesh.New(vert.name)
                meshOb = scn.objects.new(mesh)
                #print "group %s stride %s count %s type %s d %s xyz %srn" % (vert.name, vert.stride, vert.vertice_count, vert.type, vert.divisor, vert.isxyz),
                doffset = c.total_data_offset + vert.data_offset
                vertices = []
                for s in xrange(vert.vertice_count):
                    vertice = []
                    for c in xrange(3):
                        if vert.type == 0:
                            vertice.append(float(struct.unpack_from(">B", data[doffset:doffset+1])[0]) * (1.0 / (1 << vert.divisor)))
                            doffset += 1
                        if vert.type == 1:
                            vertice.append(float(struct.unpack_from(">b", data[doffset:doffset+1])[0]) * (1.0 / (1 << vert.divisor)))
                            doffset += 1
                        elif vert.type == 2:
                            vertice.append(float(struct.unpack_from(">H", data[doffset:doffset+2])[0]) * (1.0 / (1 << vert.divisor)))
                            doffset += 2
                        elif vert.type == 3:
                            vertice.append(float(struct.unpack_from(">h", data[doffset:doffset+2])[0]) * (1.0 / (1 << vert.divisor)))
                            doffset += 2
                        elif vert.type == 4:
                            vertice.append(float(struct.unpack_from(">f", data[doffset:doffset+4])[0]) * (1.0 / (1 << vert.divisor)))
                            doffset += 4
                        else:
                            print "unk vert type! %srn" % vert.type
                    vertices.append(vertice)
                    
                    
                #print "adding %s verticesrn" % len(vertices)
                #print vertices
                mesh.verts.extend(vertices)
                
            Blender.Redraw()
            
        def RM(self,a):
            sy = sin(a[2])
            cy = cos(a[2])
            sp = sin(a[1])
            cp = cos(a[1])
            sr = sin(a[0])
            cr = cos(a[0])
            return Matrix([cp*cy, cp*sy, -sp], [sr*sp*cy+cr*-sy, sr*sp*sy+cr*cy, sr*cp],[cr*sp*cy+-sr*-sy, cr*sp*sy+-sr*cy, cr*cp])
```
## Post #8
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-03-22T03:15:57+00:00
- Post Title: writing BRRES importer help (for blender)

Enyone help me make this script to work?I need it.thank you.
