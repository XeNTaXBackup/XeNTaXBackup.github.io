## Post #1
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-04-11T14:56:36+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

For some time the model files from the MechWarrior Game 'MechWarrior 4: Mercenaries (MekTek Version)' have been locked behind some encryption, leaving us the BattleTech community unable to export and use them. (Downloadable here: [https://www.moddb.com/games/mechwarrior ... rcs-mektek](https://www.moddb.com/games/mechwarrior-4-mercenaries/downloads/mw4-mercs-mektek)) 

The search has been on for some time to find someone who might be able to assist us, or shed some light on how to finally unlock these files so they can be used by the wider BattleTech community.

I have started this forum to help start spreading the message and get a conversation going on how we can work together to get the MekTek model files!
## Post #2
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-04-11T17:36:10+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

I actually made a topic about this (this and the .erf files in general) a while back, you can find it here:


[viewtopic.php?f=16&t=23560&hilit=mechwarrior](https://forum.xentax.com/viewtopic.php?f=16&t=23560&hilit=mechwarrior)
## Post #3
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-04-11T23:29:51+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

> Reply from OPR23b ↑Mon Apr 12, 2021 1:36 am at Mon Apr 12, 2021 1:36 am
>
> 
I actually made a topic about this (this and the .erf files in general) a while back, you can find it here:


viewtopic.php?f=16&t=23560&hilit=mechwarrior

Looks like you have made a good amount of progress on figuring out the Hex2Obj, keep us posted about your progress
## Post #4
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-04-12T01:46:38+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

Actually, there's already a blender script for 2.92.


mariokart64n came along and coded a python script that lets you import base game .erfs (Vengeance, Mercenaries, and Black Knight).
## Post #5
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-05-27T03:04:28+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

> Reply from OPR23b ↑Mon Apr 12, 2021 9:46 am at Mon Apr 12, 2021 9:46 am
>
> 
Actually, there's already a blender script for 2.92.


mariokart64n came along and coded a python script that lets you import base game .erfs (Vengeance, Mercenaries, and Black Knight).

any place the script can be downloaded from?
## Post #6
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-27T17:47:25+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

```

    Python Code:    [PC] MechWarrior 4: Vengeance (for Blender 2.92.0)
    Author:         mariokart64n
    Date:           March 11, 2021
    Version:        0.2

    Description:
        Imports erf Mesh files into blender, for more info see post
        
        https://forum.xentax.com/viewtopic.php?f=16&t=23560
        
    ======================================================================

    ChangeLog:

    2021-03-11
        Script Wrote
        Fixed a crashed by incorrectly reading data that comes after the
        texture vertex data
    
    2021-03-12
        Corrected to read sub meshes
        Corrected Method for dimensioning Multi-Dimensional Arrays
        Added Toggle to import LOD Meshes
        Flipped the Y - Z Axis
        Patch for cockpits
        By passed mesh validation which was causing issues
        MaterialIds are added to submeshes to be able to seperate them
        Fixed a bugged caused by an array not being initialized
        

    ====================================================================== """


import bpy
from pathlib import Path  # Needed for os stuff
import random
import struct  # Needed for Binary Reader
import math

useOpenDialog = True

# ====================================================================================
# MAXCSRIPT FUNCTIONS
# ====================================================================================
# These function are written to mimic native functions in
# maxscript. This is to make porting my old maxscripts
# easier, so alot of these functions may be redundant..
# ====================================================================================
#

signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function
SEEK_ABS, SEEK_REL, SEEK_END = 0, 1, 2  # Enums for seek function

def rancol4():
    return (random.uniform(0.0, 1.0), random.uniform(0.0, 1.0), random.uniform(0.0, 1.0), 1.0)

class dummy:
    object = None

    def __init__(self, position = (0.0, 0.0, 0.0)):
        self.object = bpy.data.objects.new("Empty", None )
        bpy.context.scene.collection.objects.link(self.object)
        self.object.empty_display_size = 1
        self.object.empty_display_type = 'CUBE'
        self.object.location = position
        
    def position(self, pos=(0.0, 0.0, 0.0)):
        if self.object != None: self.object.location = pos

    def name(self, name=""):
        if self.object != None and name != "": self.object.name = name

    def showLinks(self, enable=False):
        return enable

    def showLinksOnly(self, enable=False):
        return enable


def messageBox(message="", title="Message Box", icon='INFO'):
    def draw(self, context): self.layout.label(text=message)

    bpy.context.window_manager.popup_menu(draw, title=title, icon=icon)
    return None


def doesFileExist(filename):
    file = Path(filename)
    if file.is_file():
        return True
    elif file.is_dir():
        return True
    else:
        return False


def clearListener(len=64):
    for i in range(0, len): print('')


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def findItem(array, value):
    index = -1
    try:
        index = array.index(value)
    except:
        pass
    return index


def append(array, value):
    array.append(value)
    return None


def appendIfUnique(array, value):
    try:
        array.index(value)
    except:
        array.append(value)
    return None


class fopen:
    little_endian = True
    file = ""
    mode = 'rb'
    data = bytearray()
    size = 0
    pos = 0
    isGood = False

    def __init__(self, filename=None, mode='rb', isLittleEndian=True):
        if mode == 'rb':
            if filename != None and Path(filename).is_file():
                self.data = open(filename, mode).read()
                self.size = len(self.data)
                self.pos = 0
                self.mode = mode
                self.file = filename
                self.little_endian = isLittleEndian
                self.isGood = True
        else:
            self.file = filename
            self.mode = mode
            self.data = bytearray()
            self.pos = 0
            self.size = 0
            self.little_endian = isLittleEndian
            self.isGood = False

        return None

    # def __del__(self):
    #    self.flush()

    def resize(self, dataSize=0):
        if dataSize > 0:
            self.data = bytearray(dataSize)
        else:
            self.data = bytearray()
        self.pos = 0
        self.size = dataSize
        self.isGood = False
        return None

    def flush(self):
        print("flush")
        print("file:\t%s" % self.file)
        print("isGood:\t%s" % self.isGood)
        print("size:\t%s" % len(self.data))
        if self.file != "" and not self.isGood and len(self.data) > 0:
            self.isGood = True

            s = open(self.file, 'w+b')
            s.write(self.data)
            s.close()

    def read_and_unpack(self, unpack, size):
        '''
          Charactor, Byte-order
          @,         native, native
          =,         native, standard
          <,         little endian
          >,         big endian
          !,         network

          Format, C-type,         Python-type, Size[byte]
          c,      char,           byte,        1
          b,      signed char,    integer,     1
          B,      unsigned char,  integer,     1
          h,      short,          integer,     2
          H,      unsigned short, integer,     2
          i,      int,            integer,     4
          I,      unsigned int,   integer,     4
          f,      float,          float,       4
          d,      double,         float,       8
        '''
        value = 0
        if self.size > 0 and self.pos + size < self.size:
            value = struct.unpack_from(unpack, self.data, self.pos)[0]
            self.pos += size
        return value

    def pack_and_write(self, pack, size, value):
        if self.pos + size > self.size:
            self.data.extend(b'\x00' * ((self.pos + size) - self.size))
            self.size = self.pos + size
        try:
            struct.pack_into(pack, self.data, self.pos, value)
        except:
            print('Pos:\t%i / %i (buf:%i) [val:%i:%i:%s]' % (self.pos, self.size, len(self.data), value, size, pack))
            pass
        self.pos += size
        return None

    def set_pointer(self, offset):
        self.pos = offset
        return None


def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


def fseek(bitStream, offset, dir):
    if dir == 0:
        bitStream.set_pointer(offset)
    elif dir == 1:
        bitStream.set_pointer(bitStream.pos + offset)
    elif dir == 2:
        bitStream.set_pointer(bitStream.pos - offset)
    return None


def ftell(bitStream):
    return bitStream.pos


def readByte(bitStream, isSigned=0):
    fmt = 'b' if isSigned == 0 else 'B'
    return (bitStream.read_and_unpack(fmt, 1))


def readShort(bitStream, isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'h' if isSigned == 0 else 'H'
    return (bitStream.read_and_unpack(fmt, 2))


def readLong(bitStream, isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'i' if isSigned == 0 else 'I'
    return (bitStream.read_and_unpack(fmt, 4))


def readFloat(bitStream):
    fmt = '>f' if not bitStream.little_endian else '<f'
    return (bitStream.read_and_unpack(fmt, 4))

def readString(bitStream, length=0):
    string = ''
    pos = bitStream.pos
    lim = length if length != 0 else bitStream.size - bitStream.pos
    for i in range(0, lim):
        b = bitStream.read_and_unpack('B', 1)
        if b != 0:
            string += chr(b)
        else:
            if length > 0:
                bitStream.set_pointer(pos + length)
            break
    return string

class StandardMaterial:
    data = None
    bsdf = None

    def __init__(self, name="Material"):
        # make material
        self.data = bpy.data.materials.new(name=name)
        self.data.use_nodes = True
        self.data.use_backface_culling = True
        self.bsdf = self.data.node_tree.nodes["Principled BSDF"]
        self.bsdf.label = "Standard"
        return None

    def diffuse(self, colour=(0.0, 0.0, 0.0, 0.0), name="Diffuse"):
        rgbaColor = self.data.node_tree.nodes.new('ShaderNodeRGB')
        rgbaColor.label = name
        rgbaColor.outputs[0].default_value = (colour[0], colour[1], colour[2], colour[3])
        if self.bsdf != None:
            self.data.node_tree.links.new(self.bsdf.inputs['Base Color'], rgbaColor.outputs['Color'])
        return None

    def diffuseMap(self, imageTex=None):
        if imageTex != None and self.bsdf != None:
            self.data.node_tree.links.new(self.bsdf.inputs['Base Color'], imageTex.outputs['Color'])
        return None

    def opacityMap(self, imageTex=None):
        if imageTex != None and self.bsdf != None:
            self.data.blend_method = 'BLEND'
            self.data.shadow_method = 'HASHED'
            self.data.show_transparent_back = False
            self.data.node_tree.links.new(self.bsdf.inputs['Alpha'], imageTex.outputs['Alpha'])
        return None

    def normalMap(self, imageNode=None):
        if imageTex != None and self.bsdf != None:
            imageTex.image.colorspace_settings.name = 'Linear'
            normMap = self.data.node_tree.nodes.new('ShaderNodeNormalMap')
            normMap.label = 'ShaderNodeNormalMap'
            self.data.node_tree.links.new(normMap.inputs['Color'], imageTex.outputs['Color'])
            self.data.node_tree.links.new(self.bsdf.inputs['Normal'], normMap.outputs['Normal'])
        return None

    def specularMap(self, imageNode=None, invert=True):
        if imageTex != None and self.bsdf != None:
            if invert:
                invertRGB = self.data.node_tree.nodes.new('ShaderNodeInvert')
                invertRGB.label = 'ShaderNodeInvert'
                self.data.node_tree.links.new(invertRGB.inputs['Color'], imageTex.outputs['Color'])
                self.data.node_tree.links.new(self.bsdf.inputs['Roughness'], invertRGB.outputs['Color'])
            else:
                self.data.node_tree.links.new(self.bsdf.inputs['Roughness'], imageTex.outputs['Color'])
        return None

def mesh_validate (vertices, faces):
    for fa in faces:
        if fa[0] == fa[1] or fa[1] == fa[2] or fa[2] == fa[0]:
            print ("face conjunctor")
            return True
    for fa in faces:
        for fb in fa:
            if fb > len(vertices) - 1:
                print ("face index out of range")
                return True
    return False
def mesh(vertices=[], faces=[], materialIDs=[], tverts=[], normals=[], colours=[], materials=[], mscale=1.0,
         flipAxis=False, obj_name="Object", lay_name=''):
    #
    # This function is pretty, ugly
    # imports the mesh into blender
    #

    # Clear Any Object Selections
    # for o in bpy.context.selected_objects: o.select = False
    bpy.context.view_layer.objects.active = None
    
    # Get Collection (Layers)
    if lay_name != '':
        # make collection
        layer = bpy.data.collections.new(lay_name)
        bpy.context.scene.collection.children.link(layer)
    else:
        layer = bpy.data.collections[bpy.context.view_layer.active_layer_collection.name]

    # make mesh
    msh = bpy.data.meshes.new('Mesh')

    # msh.name = msh.name.replace(".", "_")

    # Apply vertex scaling
    # mscale *= bpy.context.scene.unit_settings.scale_length
    if len(vertices) > 0:
        vertArray = [[float] * 3] * len(vertices)
        if flipAxis:
            for v in range(0, len(vertices)):
                vertArray[v] = (
                    vertices[v][0] * mscale,
                    -vertices[v][2] * mscale,
                    vertices[v][1] * mscale
                )
        else:
            for v in range(0, len(vertices)):
                vertArray[v] = (
                    vertices[v][0] * mscale,
                    vertices[v][1] * mscale,
                    vertices[v][2] * mscale
                )

    # assign data from arrays
    msh.from_pydata(vertArray, [], faces)

    # set surface to smooth
    msh.polygons.foreach_set("use_smooth", [True] * len(msh.polygons))

    # Set Normals
    if len(faces) > 0:
        if len(normals) > 0:
            msh.use_auto_smooth = True
            if len(normals) == (len(faces) * 3):
                msh.normals_split_custom_set(normals)
            else:
                normArray = [[float] * 3] * (len(faces) * 3)
                if flipAxis:
                    for i in range(0, len(faces)):
                        for v in range(0, 3):
                            normArray[(i * 3) + v] = (
                                [normals[faces[i][v]][0],
                                 -normals[faces[i][v]][2],
                                 normals[faces[i][v]][1]]
                            )
                else:
                    for i in range(0, len(faces)):
                        for v in range(0, 3):
                            normArray[(i * 3) + v] = (
                                [normals[faces[i][v]][0],
                                 normals[faces[i][v]][1],
                                 normals[faces[i][v]][2]]
                            )
                msh.normals_split_custom_set(normArray)

        # create texture corrdinates
        #print("tverts ", len(tverts))
        # this is just a hack, i just add all the UVs into the same space <<<
        if len(tverts) > 0:
            uvw = msh.uv_layers.new()
            # if len(tverts) == (len(faces) * 3):
            #    for v in range(0, len(faces) * 3):
            #        msh.uv_layers[uvw.name].data[v].uv = tverts[v]
            # else:
            uvwArray = [[float] * 2] * len(tverts[0])
            for i in range(0, len(tverts[0])):
                uvwArray[i] = [0.0, 0.0]

            for v in range(0, len(tverts[0])):
                for i in range(0, len(tverts)):
                    uvwArray[v][0] += tverts[i][v][0]
                    uvwArray[v][1] += 1.0 - tverts[i][v][1]

            for i in range(0, len(faces)):
                for v in range(0, 3):
                    msh.uv_layers[uvw.name].data[(i * 3) + v].uv = (
                        uvwArray[faces[i][v]][0],
                        uvwArray[faces[i][v]][1]
                    )


    # Create Face Maps?
    # msh.face_maps.new()

    # Update Mesh
    msh.update()

    # Check mesh is Valid
    if mesh_validate(vertices, faces): #msh.validate(verbose=True):
        # Erase Mesh
        print("Mesh Invalid!")

        msh.user_clear()
        bpy.data.meshes.remove(msh)
        return None

    # Assign Mesh to Object
    obj = bpy.data.objects.new(obj_name, msh)
    # obj.name = obj.name.replace(".", "_")

    for i in range(0, len(materials)):

        if len(obj.material_slots) < (i + 1):
            # if there is no slot then we append to create the slot and assign
            obj.data.materials.append(materials[i])
        else:
            # we always want the material in slot[0]
            obj.material_slots[0].material = materials[i]
        # obj.active_material = obj.material_slots[i].material
    
    if len(faces) > 0 and len(faces) == len(materialIDs):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i]
    elif len(materialIDs) > 0:
        print("Supplied Mat Ids to not Match faces:\t%i / %i" % (len(faces), len(materialIDs)))

    # obj.data.materials.append(material)
    layer.objects.link(obj)

    # Generate a Material
    # img_name = "Test.jpg"  # dummy texture
    # mat_count = len(texmaps)

    # if mat_count == 0 and len(materialIDs) > 0:
    #    for i in range(0, len(materialIDs)):
    #        if (materialIDs[i] + 1) > mat_count: mat_count = materialIDs[i] + 1

    # Assign Material ID's
    bpy.context.view_layer.objects.active = obj
    bpy.ops.object.mode_set(mode='EDIT', toggle=False)
    bpy.context.tool_settings.mesh_select_mode = [False, False, True]

    bpy.ops.object.mode_set(mode='OBJECT')
    # materialIDs

    # Redraw Entire Scene
    # bpy.context.scene.update()

    return obj

class erf_mesh:
    unk101 = 0
    block_size = 0
    unk103 = 0  # hx4B
    unk104 = 0
    vert_count = 0
    face_count1 = 0
    tvert_count = 0
    # need to inspect this
    mat_name = ""
    face_count2 = 0
    norm_count = 0
    vcol_count = 0
    unk105_count = 0
    vert_array = []
    tvert_array = []
    face_array = []
    norm_array = []
    vcol_array = []
    unk105_array = []
    matid_array = []
    mat_names = []
    def read_mesh (self, f= fopen()):
        self.vert_array = []
        self.tvert_array = []
        self.face_array = []
        self.norm_array = []
        self.vcol_array = []
        self.unk105_array = []
        self.matid_array = []

        self.unk101 = readLong(f)
        self.block_size = readLong(f) + ftell(f) + 4
        self.unk103 = readLong(f)
        self.unk104 = readByte(f)
        
        vert_idx_off = 0
        tvert_idx_off = 0
        face_idx_off = 0
        norm_idx_off = 0
        vcol_idx_off = 0
        unk105_idx_off = 0
        
        mat_index = 0
        self.mat_names = []
        
        for m in range(0, self.unk104):
            self.face_count1 = readLong(f)
            self.vert_count = readLong(f)
            
            if self.vert_count > 0:
                self.vert_array.extend([[[float] for x in range(3)] for y in range(self.vert_count)])
                for i in range(0, self.vert_count):
                    self.vert_array[i + vert_idx_off] = [
                        readFloat(f),
                        readFloat(f),
                        readFloat(f)
                        ]
            
            self.tvert_count = readLong(f)
            if self.tvert_count > 0:
                self.tvert_array.extend([[[float] for x in range(2)] for y in range(self.tvert_count)])
                for i in range(0, self.tvert_count):
                    self.tvert_array[i + tvert_idx_off] = [
                        readFloat(f),
                        readFloat(f)
                        ]
            
            fseek(f, 25, seek_cur) # wtf is this
            self.mat_name = readString(f, readLong(f))
            appendIfUnique(self.mat_names, self.mat_name)
            mat_index = findItem(self.mat_names, self.mat_name)
            fseek(f, 5, seek_cur)
            #print("Name:\t%s" % self.mat_name)
            
            self.face_count2 = readLong(f)
            if self.face_count2 > 0:
                self.face_array.extend([[[int] for x in range(3)] for y in range(int(self.face_count2 / 3))])
                self.matid_array.extend([[int] for y in range(int(self.face_count2 / 3))])
                for i in range(0, int(self.face_count2 / 3)):
                    self.matid_array[i + face_idx_off] = mat_index
                    self.face_array[i + face_idx_off] = [
                        readByte(f, unsigned) + vert_idx_off,
                        readByte(f, unsigned) + vert_idx_off,
                        readByte(f, unsigned) + vert_idx_off
                        ]
            
            self.norm_count = readLong(f)
            if self.norm_count > 0:
                self.norm_array.extend([[[float] for x in range(4)] for y in range(self.norm_count)])
                for i in range(0, self.norm_count):
                    self.norm_array[i + norm_idx_off] = [
                        readFloat(f),
                        readFloat(f),
                        readFloat(f),
                        readFloat(f)
                        ]
            
            self.vcol_count = readLong(f)
            if self.vcol_count > 0:
                print ("Inspect this")
            
            self.unk105_count = readLong(f)
            if self.unk105_count > 0:
                self.unk105_array.extend([[[float] for x in range(3)] for y in range(self.unk105_count)])
                for i in range(0, self.unk105_count):
                    self.unk105_array[i + unk105_idx_off] = [
                        readFloat(f),
                        readFloat(f),
                        readFloat(f)
                        ]
            
            vert_idx_off += self.vert_count
            tvert_idx_off += self.tvert_count
            face_idx_off += int(self.face_count2 / 3)
            norm_idx_off += self.norm_count
            vcol_idx_off += self.vcol_count
            unk105_idx_off += self.unk105_count
        
        fseek(f, self.block_size, seek_set)

class erf_file:
    filedid = 0     # ERF#
    unk001 = 0      # hx0E
    unk002 = 0      # hx90
    unk003 = 0      # hx09
    unk004 = [0.0, 0.0, 0.0, 0.0]
    mesh_count = 0
    unk005 = 0
    unk006 = 0      # hx12
    unk007 = 0      # hx00
    meshes = []
    
    def read_erf (self, f = fopen()):
        
        self.filedid = readLong(f)
        
        isCockpit = False
        
        if self.filedid != 0x45524623:
            print ("Unsupported File Type")
            return False # (ERF#)
        
        self.unk001 = readLong(f)
        self.unk002 = readLong(f)
        self.unk003 = readLong(f)
        self.unk004 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.mesh_count = readShort(f)
        
        if self.mesh_count == 21027:
            self.mesh_count = 1
            fseek(f, -2, seek_cur)
            isCockpit = True
            
        self.unk005 = readLong(f)
        self.unk006 = readLong(f)
        self.unk007 = readLong(f)
        
        if self.mesh_count > 0:
            self.meshes = [erf_mesh] * self.mesh_count
            for i in range(0, self.mesh_count):
                if isCockpit: fseek(f, -8, seek_cur)
                self.meshes[i] = erf_mesh()
                self.meshes[i].read_mesh(f)
                
        return True

def deleteScene(include=[]):
    if len(include) > 0:
        # Exit and Interactions
        if bpy.context.view_layer.objects.active != None:
            bpy.ops.object.mode_set(mode='OBJECT')

        # Select All
        bpy.ops.object.select_all(action='SELECT')

        # Loop Through Each Selection
        for o in bpy.context.view_layer.objects.selected:
            for t in include:
                if o.type == t:
                    bpy.data.objects.remove(o, do_unlink=True)
                    break

        # De-Select All
        bpy.ops.object.select_all(action='DESELECT')
    return None

def read (file, impLOD = False):
    if not doesFileExist(file): return False
    
    #deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    
    f = fopen(file, 'rb')
    
    erf = erf_file()
    erf.read_erf(f)
    
    
    d = dummy(position=(erf.unk004[0],erf.unk004[1], erf.unk004[2]))
    d.object.empty_display_size = erf.unk004[3]
    d.object.empty_display_type = 'SPHERE'
    
    
    #
    mat_lib_names = []
    for i in range(0, erf.mesh_count):
        for mn in erf.meshes[i].mat_names:
            appendIfUnique(mat_lib_names, mn)
    
    mat_lib = []
    mat = None
    for i in range(0, len(mat_lib_names)):
        mat = StandardMaterial(name=mat_lib_names[i])
        mat.diffuse(rancol4())
        mat_lib.append(mat.data)
        
    
    for i in range(0, erf.mesh_count):
        msh = mesh(
            obj_name=getFilenameFile(file),
            vertices=erf.meshes[i].vert_array,
            faces=erf.meshes[i].face_array,
            tverts=[erf.meshes[i].tvert_array],
            normals=erf.meshes[i].unk105_array,
            materialIDs=erf.meshes[i].matid_array,
            materials=mat_lib,
            flipAxis=True
            )
        if msh != None:
            msh.location = (-erf.unk004[0], erf.unk004[2], -erf.unk004[1])
            msh.parent = d.object
        if not impLOD: break
    
    
    fclose(f)
    return True


# ====================================================================================
# BLENDER API FUNCTIONS
# ====================================================================================
# These are functions or wrappers specific with dealing with blenders API
# ====================================================================================
#

def deleteScene(include=[]):
    if len(include) > 0:
        # Exit and Interactions
        if bpy.context.view_layer.objects.active != None:
            bpy.ops.object.mode_set(mode='OBJECT')

        # Select All
        bpy.ops.object.select_all(action='SELECT')

        # Loop Through Each Selection
        for o in bpy.context.view_layer.objects.selected:
            for t in include:
                if o.type == t:
                    bpy.data.objects.remove(o, do_unlink=True)
                    break

        # De-Select All
        bpy.ops.object.select_all(action='DESELECT')
    return None


# Callback when file(s) are selected
def mechwarrioriv_imp_callback(fpath="", files=[], clearScene=True, impLOD=False):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE', 'EMPTY'])
    for file in files:
        read(fpath + file.name, impLOD)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def mechwarrioriv_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_mechwarrioriv_imp"):  # print(bpy.ops.importhelper.mechwarrioriv_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_mechwarrioriv_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_mechwarrioriv_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_mechwarrioriv_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.mechwarrioriv_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.erf', options={'HIDDEN'}, subtype='FILE_PATH')

        # Variables
        filepath: bpy.props.StringProperty(subtype="FILE_PATH")  # full path of selected item (path+filename)
        filename: bpy.props.StringProperty(subtype="FILE_NAME")  # name of selected item
        directory: bpy.props.StringProperty(subtype="FILE_PATH")  # directory of the selected item
        files: bpy.props.CollectionProperty(
            type=bpy.types.OperatorFileListElement)  # a collection containing all the selected items�f filenames

        # Controls
        my_int1: bpy.props.IntProperty(name="Some Integer", description="Tooltip")
        my_float1: bpy.props.FloatProperty(name="Scale", default=1.0, description="Changes Scale of the imported Mesh")
        # my_float2: bpy.props.FloatProperty(name="Some Float point", default = 0.25, min = -0.25, max = 0.5)
        my_bool1: bpy.props.BoolProperty(name="Clear Scene", default=True,
                                         description="Deletes everything in the scene prior to importing")
        my_bool2: bpy.props.BoolProperty(name="LOD Meshes", default=False, description="Imports Lower Res Meshes")
        my_bool3: bpy.props.BoolProperty(name="Vertex Weights", default=False, description="Builds Vertex Groups")
        my_bool4: bpy.props.BoolProperty(name="Vertex Normals", default=False, description="Applies Custom Normals")
        my_bool5: bpy.props.BoolProperty(name="Vertex Colours", default=False, description="Builds Vertex Colours")
        my_bool6: bpy.props.BoolProperty(name="Guess Parents", default=False,
                                         description="Uses algorithm to Guess Bone Parenting")
        my_bool7: bpy.props.BoolProperty(name="Dump Textures", default=False,
                                         description="Writes Textures from a file pair '_tex.bin'")
        my_string1: bpy.props.StringProperty(name="", default="Armature",
                                             description="Name of Armature to Import Bones to")
        my_dropdown1: bpy.props.EnumProperty(
            name="Drop",
            items=[
                ('CLEAR', 'clear scene', 'clear scene'),
                ('ADD_CUBE', 'add cube', 'add cube'),
                ('ADD_SPHERE', 'add sphere', 'add sphere')
            ]
        )
        my_dropdown2: bpy.props.EnumProperty(
            name="Drop",
            items=[
                ('CLEAR', 'clear scene', 'clear scene'),
                ('ADD_CUBE', 'add cube', 'add cube'),
                ('ADD_SPHERE', 'add sphere', 'add sphere')
            ]
        )

        # Runs when this class OPENS
        def invoke(self, context, event):

            # Retrieve Settings
            try:
                self.filepath = bpy.types.Scene.mechwarrioriv_imp_filepath
            except:
                bpy.types.Scene.mechwarrioriv_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try:
                self.directory = bpy.types.Scene.mechwarrioriv_imp_directory
            except:
                bpy.types.Scene.mechwarrioriv_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try:
                self.my_float1 = bpy.types.Scene.mechwarrioriv_imp_my_float1
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try:
                self.my_bool1 = bpy.types.Scene.mechwarrioriv_imp_my_bool1
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool1 = bpy.props.BoolProperty(default=False)

            try:
                self.my_bool2 = bpy.types.Scene.mechwarrioriv_imp_my_bool2
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool2 = bpy.props.BoolProperty(default=False)

            try:
                self.my_bool3 = bpy.types.Scene.mechwarrioriv_imp_my_bool3
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool3 = bpy.props.BoolProperty(default=False)

            try:
                self.my_bool4 = bpy.types.Scene.mechwarrioriv_imp_my_bool4
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool4 = bpy.props.BoolProperty(default=False)

            try:
                self.my_bool5 = bpy.types.Scene.mechwarrioriv_imp_my_bool5
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool5 = bpy.props.BoolProperty(default=False)

            try:
                self.my_bool6 = bpy.types.Scene.mechwarrioriv_imp_my_bool6
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool6 = bpy.props.BoolProperty(default=False)

            try:
                self.my_bool7 = bpy.types.Scene.mechwarrioriv_imp_my_bool7
            except:
                bpy.types.Scene.mechwarrioriv_imp_my_bool7 = bpy.props.BoolProperty(default=False)

            try:
                self.my_string1 = bpy.types.Scene.my_string1
            except:
                bpy.types.Scene.my_string1 = bpy.props.BoolProperty(default=False)

            # Open File Browser
            # Set Properties of the File Browser
            context.window_manager.fileselect_add(self)
            context.area.tag_redraw()

            return {'RUNNING_MODAL'}

        # Runs when this Window is CANCELLED
        def cancel(self, context):
            print("run bitch")

        # Runs when the class EXITS
        def execute(self, context):

            # Save Settings
            bpy.types.Scene.mechwarrioriv_imp_filepath = self.filepath
            bpy.types.Scene.mechwarrioriv_imp_directory = self.directory
            #bpy.types.Scene.mechwarrioriv_imp_my_float1 = self.my_float1
            bpy.types.Scene.mechwarrioriv_imp_my_bool1 = self.my_bool1
            bpy.types.Scene.mechwarrioriv_imp_my_bool2 = self.my_bool2
            #bpy.types.Scene.mechwarrioriv_imp_my_bool3 = self.my_bool3
            #bpy.types.Scene.mechwarrioriv_imp_my_bool4 = self.my_bool4
            #bpy.types.Scene.mechwarrioriv_imp_my_bool5 = self.my_bool5
            #bpy.types.Scene.mechwarrioriv_imp_my_bool6 = self.my_bool6
            #bpy.types.Scene.mechwarrioriv_imp_my_bool7 = self.my_bool7
            bpy.types.Scene.mechwarrioriv_imp_my_string1 = self.my_string1

            # Run Callback
            mechwarrioriv_imp_callback(
                self.directory + "\\",
                self.files,
                self.my_bool1,
                self.my_bool2
                )

            return {"FINISHED"}

            # Window Settings

        def draw(self, context):

            # Set Properties of the File Browser
            # context.space_data.params.use_filter = True
            # context.space_data.params.use_filter_folder=True #to not see folders

            # Configure Layout
            # self.layout.use_property_split = True       # To Enable Align
            # self.layout.use_property_decorate = False   # No animation.

            self.layout.row().label(text="Import Settings")

            self.layout.separator()
            self.layout.row().prop(self, "my_bool1")
            self.layout.row().prop(self, "my_bool2")
            #self.layout.row().prop(self, "my_float1")

            #box = self.layout.box()
            #box.label(text="Include")
            #box.prop(self, "my_bool2")
            #box.prop(self, "my_bool3")
            #box.prop(self, "my_bool4")
            #box.prop(self, "my_bool5")

            #box = self.layout.box()
            #box.label(text="Misc")
            #box.prop(self, "my_bool6")
            #box.prop(self, "my_bool7")
            #box.label(text="Import Bones To:")
            #box.prop(self, "my_string1")

            self.layout.separator()

            col = self.layout.row()
            col.alignment = 'RIGHT'
            col.label(text="  Author:", icon='QUESTION')
            col.alignment = 'LEFT'
            col.label(text="mariokart64n")

            col = self.layout.row()
            col.alignment = 'RIGHT'
            col.label(text="Release:", icon='GRIP')
            col.alignment = 'LEFT'
            col.label(text="March 12, 2021")

        def menu_func_import(self, context):
            self.layout.operator(
                "importhelper.mechwarrioriv_imp",
                text="MechWarrior 4: Vengeance (*.erf)"
                )

    # Register Operator
    bpy.utils.register_class(ImportHelper_mechwarrioriv_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_mechwarrioriv_imp.menu_func_import)

    # Assign Shortcut key
    # bpy.context.window_manager.keyconfigs.active.keymaps["Window"].keymap_items.new('bpy.ops.text.run_script()', 'E', 'PRESS', ctrl=True, shift=False, repeat=False)

    # Call ImportHelper
    bpy.ops.importhelper.mechwarrioriv_imp('INVOKE_DEFAULT')




clearListener()  # clears out console
if not useOpenDialog:

    deleteScene(['MESH', 'ARMATURE', 'EMPTY'])  # Clear Scene
    read(
        ""
        )
    messageBox("Done!")
else:
    mechwarrioriv_imp(True)
```


This is the latest version of the script mariokart made. It supports the .erfs from Vengeance, Mercenaries and Black Knight.

It does not support the encrypted .erfs though, however, it can import the older, unencrypted versions of mechs from earlier Mekpak releases.


If you do happen to see any odd normals (as in, it looks oddly smooth), just go into edit mode, select the "Mesh" button on top, and go to Normals > Average > Face Area.


To use it, all you need to do is copy-paste the code into Blender's script area, run it, and import it. If you are going to import multiple .erfs, make sure to turn off the "Clear scene" option.
## Post #7
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-06-21T23:11:52+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

Is there a new version of the script that has been released recently?
## Post #8
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-06-21T23:36:51+00:00
- Post Title: MechWarrior 4: MekTek File Encryption Breaking

No, but this is the most recent release.
