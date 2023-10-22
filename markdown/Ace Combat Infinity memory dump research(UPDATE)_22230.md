## Post #1
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2020-06-03T18:26:20+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

(Original title : "Ace Combat Infinity model sample(Memory Dump)")
Recently started to dump and search into the memory of the game using RPCS3 and Cheat Engine.
Model files are listed as NDP3, which is the in-house model format for Playstation 3 of Bandai Namco Entertainment

The following games it uses this format :
-Mobile Suit Gundam Extreme Vs Full Boost(.fhm)
-Tekken 6(.bin)
-Naruto Ultimate Ninja Storm 1, 2, 3 and Generations(.xfbin)
-Super Smash Bros for the Nintendo Wii U(.nud)

Some tools and scripts was developed for those games, thing is the NDP3 header changes depending of the game, so running those with the sample file i have at the moment doesn't work(by the way the script was programmed for each game)

The following pictures of the model sample in-game, textures aren't included, but they are rippable, despite tedious for getting them by memory dump, but for interresed, they used NTP3 GIDX, simply replacing the header with the correct DXT type and with exact resolution, you can emulate it fine :
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-04T11:53:44+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

ndp3_.png (235.57 KiB) Viewed 576 times
## Post #3
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2020-06-04T15:42:52+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

If possible, you could explain more or less the areas when the vertex/UV data starts for each separated mesh part? due i know you are the creator of Hex2OBJ, and recently i started to make some float editing of UE4 uassets from other games, which made me understand a bit of how hex structures work in terms, as part of a programmer which i entered in contact, he also explained a bit of the notion of finding vertex structures. i was comparing the files with another one, so i would be curious at least to have a little notion of the start point of the NDP3's data to start learning to use your tool as a experience.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-04T17:02:08+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

Search for FFFF (triangle strips terminal/separator), look for the gaps. There submeshes usually start.
.



ndp3_vertex_start.png (29.66 KiB) Viewed 571 times
## Post #5
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2021-01-07T12:30:25+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

Hi, wanted to give the headups that in fact, i finally learned how to extract mesh data with Hex2obj. it was a bit hard for sure considering i was trying before but gave up at first, i got confused during the tests due i was picking up the wrong address(using the half-float UVs as the main mesh), at times i tend to suffer some "bruh moments" like that with a lot of people and projects i work, even without entering in such details about why. but in short, would like to give you heads up for creating this tool in fact, along for Bigchillghost, which was the host of the tutorial basis. it can be tedious at first, but learning and getting results by yourself in fact is a good experience to go went.

Got the same results as you did, getting the fuselage basis for now, despite my face indices count calculations went a bit wrong, merging with other faces. i may focus at trying this to some mesh parts i will want at the moment, seeing i did before provisory rips with the external branch of Renderdoc with the FBX exporter, despite the models begin broke in backface, flatterend when import, and missing some components like the canopies, those rips by far was the second award i did get for researching the minimum details of them, except for obviously, lack of UV maps. at the same time i wanted to work on the rips, considering the components each model got, including the gears...is a bit too much considering for a roster of like, 71 aircrafts in total, considering i also got my IRL depedencies to focus too BTW. but leaving it here a reply, considering at times is rare to obviously a user who asked help for a model, giving you a reply like that without starting to beg you for getting the other parts, to the whole model and working into a script.
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-23T12:23:57+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

[](https://ibb.co/YBxT2MY)

> Below is a python script I wrote for blender that was tested in the latest version (currently 2.92.0)
>
> 
>
> usage: Start blender, goto the script tab then press the 'NEW' button, then paste the below script into the editor. To execute the script press ALT+P or press the [>] play button. When pressed a file selection dialog will appear which will prompt to open a file to import. Once the script has executed once, thereafter the file prompt may then be accessed through the File > Import Dialog until blender is restarted

```

    PythonScript:   [PC] Ace Combat Assault Horizon
    Author:         mariokart64n
    Date:           March 22, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-22
        Script Wrote

    2021-03-23
        Adapted to work with PS3 Memory dump from Ace Combat Infinity

    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff


useOpenDialog = True


signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function
SEEK_ABS, SEEK_REL, SEEK_END = 0, 1, 2  # Enums for seek function


def messageBox(message="", title="Message Box", icon='INFO'):
    def draw(self, context): self.layout.label(text=message)

    bpy.context.window_manager.popup_menu(draw, title=title, icon=icon)
    return None


def clearListener(len=64):
    for i in range(0, len): print('')


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def getFilenameType(file):  # returns: ".jpg"
    return Path(file).suffix


def toUpper(string):
    return string.upper()


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

    def set_endian(self, isLittle = True):
        self.little_endian = isLittle
        return isLittle

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


def readHalf(bitStream):
    uint16 = bitStream.read_and_unpack('>H' if not bitStream.little_endian else '<H', 2)
    uint32 = (
            (((uint16 & 0x03FF) << 0x0D) | ((((uint16 & 0x7C00) >> 0x0A) + 0x70) << 0x17)) |
            (((uint16 >> 0x0F) & 0x00000001) << 0x1F)
    )
    return struct.unpack('f', struct.pack('I', uint32))[0]


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


def mesh_validate (vertices=[], faces=[]):
    #
    # Returns True if mesh is BAD
    #
    # check face index bound
    face_min = 0
    face_max = len(vertices) - 1
    
    for face in faces:
        for side in face:
            if side < face_min or side > face_max:
                print("Face Index Out of Range:\t[%i / %i]" % (side, face_max))
                return True
    return False

def mesh(
    vertices=[],
    faces=[],
    materialIDs=[],
    tverts=[],
    normals=[],
    colours=[],
    materials=[],
    mscale=1.0,
    flipAxis=False,
    obj_name="Object",
    lay_name='',
    position = (0.0, 0.0, 0.0)
    ):
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
        layer = bpy.data.collections.get(lay_name)
        if layer == None:
            layer = bpy.data.collections.new(lay_name)
            bpy.context.scene.collection.children.link(layer)
    else:
        if len(bpy.data.collections) == 0:
            layer = bpy.data.collections.new("Collection")
            bpy.context.scene.collection.children.link(layer)
        else:
            try:
                layer = bpy.data.collections[bpy.context.view_layer.active_layer_collection.name]
            except:
                layer = bpy.data.collections[0]
    

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
    if mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None
    
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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")

        

    # Assign Mesh to Object
    obj = bpy.data.objects.new(obj_name, msh)
    obj.location = position
    # obj.name = obj.name.replace(".", "_")

    for i in range(0, len(materials)):

        if len(obj.material_slots) < (i + 1):
            # if there is no slot then we append to create the slot and assign
            obj.data.materials.append(materials[i])
        else:
            # we always want the material in slot[0]
            obj.material_slots[0].material = materials[i]
        # obj.active_material = obj.material_slots[i].material

    if len(materialIDs) == len(obj.data.polygons):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i] % len(materials)
    elif len(materialIDs) > 0:
        print("Error:\tMaterial Index Out of Range")

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

class ndxr_entry_info_cmd_table2:
    unk081 = 0
    name_addr = 0
    name = ""
    unk083 = 0
    unk084 = 0
    unk085 = 0.0
    unk086 = 0.0
    unk087 = 0.0
    unk088 = 0.0

    def read_info_cmd_table2(self, strings_addr=0, f=fopen()):
        self.unk081 = readLong(f, unsigned)
        self.name_addr = readLong(f, unsigned)
        self.unk083 = readLong(f, unsigned)
        self.unk084 = readLong(f, unsigned)
        self.unk085 = readFloat(f)
        self.unk086 = readFloat(f)
        self.unk087 = readFloat(f)
        self.unk088 = readFloat(f)
        pos = ftell(f)
        fseek(f, (strings_addr + self.name_addr), seek_set)
        self.name = readString(f)
        fseek(f, pos, seek_set)


class ndxr_entry_info_cmd_table1:  # 24 bytes
    unk061 = 0
    unk062 = 0
    unk063 = 0
    unk064 = 0
    unk065 = 0
    unk066 = 0
    unk067 = 0
    unk068 = 0
    unk069 = 0
    unk070 = 0
    unk071 = 0
    unk072 = 0
    unk073 = 0
    unk074 = 0
    unk075 = 0
    unk076 = 0

    def read_info_cmd_table1(self, f=fopen()):
        self.unk061 = readByte(f, unsigned)
        self.unk062 = readShort(f, unsigned)
        self.unk063 = readLong(f, unsigned)
        self.unk064 = readByte(f, unsigned)
        self.unk065 = readShort(f, unsigned)
        self.unk066 = readLong(f, unsigned)
        self.unk067 = readByte(f, unsigned)
        self.unk068 = readByte(f, unsigned)
        self.unk069 = readByte(f, unsigned)
        self.unk070 = readByte(f, unsigned)
        self.unk071 = readByte(f, unsigned)
        self.unk072 = readByte(f, unsigned)
        self.unk073 = readByte(f, unsigned)
        self.unk074 = readByte(f, unsigned)
        self.unk075 = readByte(f, unsigned)
        self.unk076 = readByte(f, unsigned)


class ndxr_entry_info_cmd:
    unk041 = 0
    unk042 = 0
    unk043 = 0
    unk044 = 0
    unk045 = 0
    table1_count = 0  # count
    unk046 = 0
    unk047 = 0
    unk048 = 0
    unk049 = 0
    unk050 = 0
    table1 = []
    unk051 = 0
    unk052 = 0
    unk053 = 0
    table2 = []

    def read_info_cmd(self, strings_addr=0, f=fopen()):
        self.unk041 = readByte(f, unsigned)
        self.unk042 = readShort(f, unsigned)
        self.unk043 = readByte(f, unsigned)
        self.unk044 = readShort(f, unsigned)
        self.unk045 = readLong(f, unsigned)
        self.table1_count = readShort(f, unsigned)
        self.unk046 = readShort(f, unsigned)
        self.unk047 = readLong(f, unsigned)
        self.unk048 = readLong(f, unsigned)
        self.unk049 = readByte(f, unsigned)
        self.unk050 = readShort(f, unsigned)
        if self.table1_count > 0:
            self.table1 = [ndxr_entry_info_cmd_table1] * self.table1_count
            for i in range(0, self.table1_count):
                self.table1[i] = ndxr_entry_info_cmd_table1()
                self.table1[i].read_info_cmd_table1(f)
                self.unk051 = readByte(f, unsigned)
                self.unk052 = readShort(f, unsigned)
                self.unk053 = readLong(f, unsigned)
                i = -1
                while True:
                    i += 1
                    append(self.table2, (ndxr_entry_info_cmd_table2()))
                    self.table2[i].read_info_cmd_table2(strings_addr, f)
                    if self.table2[i].unk081 != 0x20: break


class ndxr_entry_info:
    face_addr = 0  # face buffer addr?
    vert_addr = 0  # vert buffer addr?
    unk033 = 0  # 0
    vert_count = 0  # vertex count?
    unk036 = 0  # 6
    unk037 = 0  # ? vertex format? 17=28bytes, 16=20bytes
    cmd_addr = 0
    cmd = ndxr_entry_info_cmd()
    unk038 = 0  # 0
    unk039 = 0  # 0
    unk040 = 0  # 0
    face_count = 0  # face count?
    unk042 = 0  # 0
    unk043 = 0  # 0
    unk044 = 0  # 0
    unk045 = 0  # 0

    def read_info(self, pos=0, strings_addr=0, f=fopen(), addr_off = 0):
        self.face_addr = readLong(f, unsigned)
        self.vert_addr = readLong(f, unsigned)
        self.unk033 = readLong(f, unsigned)
        self.vert_count = readShort(f, unsigned)
        self.unk036 = readByte(f, unsigned)
        self.unk037 = readByte(f, unsigned)
        self.cmd_addr = readLong(f, unsigned) - addr_off
        self.unk038 = readLong(f, unsigned)
        self.unk039 = readLong(f, unsigned)
        self.unk040 = readLong(f, unsigned)
        self.face_count = readShort(f, unsigned)
        self.unk042 = readShort(f, unsigned)
        self.unk043 = readLong(f, unsigned)
        self.unk044 = readLong(f, unsigned)
        self.unk045 = readLong(f, unsigned)
        if self.cmd_addr > 0:
            fseek(f, pos + self.cmd_addr, seek_set)
            self.cmd.read_info_cmd(strings_addr, f)


class ndxr_entry:
    unk011 = 0.0
    unk012 = 0.0
    unk013 = 0.0
    unk014 = 0.0
    unk015 = 0.0
    unk016 = 0.0
    unk017 = 0.0
    unk018 = 0
    name_addr = 0
    name = ""
    unk019 = 0
    unk020 = 0
    unk021 = 0
    unk022 = 0  # info count
    info_addr = 0
    info = []

    def read_entry(self, pos=0, strings_addr=0, f=fopen(), addr_off = 0):
        self.unk011 = readFloat(f)
        self.unk012 = readFloat(f)
        self.unk013 = readFloat(f)
        self.unk014 = readFloat(f)
        self.unk015 = readFloat(f)
        self.unk016 = readFloat(f)
        self.unk017 = readFloat(f)
        self.unk018 = readLong(f, unsigned)
        self.name_addr = readLong(f, unsigned)
        self.unk019 = readShort(f, unsigned)
        self.unk020 = readShort(f, unsigned)
        self.unk021 = readShort(f, unsigned)
        self.unk022 = readShort(f, unsigned)
        self.info_addr = readLong(f, unsigned) - addr_off
        fseek(f, (strings_addr + self.name_addr), seek_set)
        self.name = readString(f)
        if self.unk022 > 0 and self.info_addr > 0:
            self.info = [ndxr_entry_info] * self.unk022
            for i in range(0, self.unk022):
                fseek(f, (pos + self.info_addr + (i * 48)), seek_set)
                self.info[i] = ndxr_entry_info()
                self.info[i].read_info(pos, strings_addr, f, addr_off)


class ndxr_file:
    fileid = 0
    unk001 = 0
    unk002 = 0
    count = 0
    unk007 = 0
    unk003 = 0
    face_addr = 0
    face_size = 0
    vert_size = 0
    unk004 = 0
    unk005 = 0
    unk006 = [0.0, 0.0, 0.0]
    entries = []

    def read(self, f=fopen(), mscale = 1.0, col_name = "", addr_off = 0):
        pos = ftell(f)
        header_size = 48
        self.fileid = readLong(f, unsigned)
        self.unk001 = readLong(f, unsigned)
        self.unk002 = readShort(f, unsigned)
        self.count = readShort(f, unsigned)
        self.unk007 = readShort(f, unsigned)
        self.unk003 = readShort(f, unsigned)
        self.face_addr = readLong(f, unsigned)
        self.face_size = readLong(f, unsigned)
        self.vert_size = readLong(f, unsigned)
        self.unk004 = readLong(f, unsigned)
        self.unk005 = readLong(f, unsigned)
        self.unk006 = [readFloat(f), readFloat(f), readFloat(f)]

        self.face_addr += pos + header_size
        vert_addr = self.face_addr + self.face_size
        strings_addr = vert_addr + self.vert_size
        entry_size = 48
        vertArray = []
        normArray = []
        faceArray = []
        matidArray = []
        tvertArray = []
        msh = None
        tmp = []
        vertex_stride = 0
        face = [0, 0, 0]
        facePosition = 0
        faceCW = True
        maxIndex = 0

        if self.count > 0:
            self.entries = [ndxr_entry] * self.count
            for i in range(0, self.count):
                fseek(f, (pos + header_size + (i * entry_size)), seek_set)
                self.entries[i] = ndxr_entry()
                self.entries[i].read_entry(pos, strings_addr, f, addr_off)
        
        
            
        
        # Generate Size List to Estimate the Vertex Stride
        for i in range(0, self.count):
            for ii in range(0, self.entries[i].unk022):
                appendIfUnique(tmp, (self.entries[i].info[ii].vert_addr + vert_addr))

        append(tmp, strings_addr)
        tmp.sort()
        
        for i in range(0, self.count):  # mesh entry
            vertArray = []
            tvertArray = []
            faceArray = []
            normArray = []
            matidArray = []
            facePosition = 0
            for ii in range(0, self.entries[i].unk022):  # level of detail meshes?

                # Read Faces
                fseek(f, (self.face_addr + self.entries[i].info[ii].face_addr), seek_set)
                v = 0
                
                while v < self.entries[i].info[ii].face_count:
                    faceCW = True
                    face[0] = readShort(f, unsigned)
                    face[1] = readShort(f, unsigned)
                    v += 2
                    while v < self.entries[i].info[ii].face_count:
                        face[2] = readShort(f, unsigned)
                        v += 1
                        if face[0] == 0xFFFF or face[1] == 0xFFFF or face[2] == 0xFFFF: break
                        if face[0] != face[1] and face[1] != face[2] and face[0] != face[2]:
                            if faceCW:
                                append(faceArray, [face[0] + facePosition, face[1] + facePosition, face[2] + facePosition])
                            else:
                                append(faceArray, [face[0] + facePosition, face[2] + facePosition, face[1] + facePosition])
                            append(matidArray, ii)
                        faceCW = not faceCW
                        face = [face[1], face[2], face[0]]
                        
                facePosition += self.entries[i].info[ii].vert_count
                vertex_stride = 20
                # Reading Vertices
                if self.entries[i].info[ii].vert_count != 0:
                    vertex_stride = int(
                        (tmp[(findItem(tmp, self.entries[i].info[ii].vert_addr + vert_addr)) + 1] -
                        (self.entries[i].info[ii].vert_addr + vert_addr)) / self.entries[i].info[ii].vert_count
                        )
                    vertex_stride = int(vertex_stride - (vertex_stride % 4))

                # format "Vertex Addr:\t%\n" (entries[i].info[ii].vert_addr + vert_addr)
                # format "Vertex Count:\t%\n" entries[i].info[ii].vert_count

                # format "Vertex Format:\t%\n" entries[i].info[ii].unk037
                if self.entries[i].info[ii].unk036 == 0:
                    vertex_stride = 20
                elif self.entries[i].info[ii].unk036 == 6:
                    vertex_stride = 28
                elif self.entries[i].info[ii].unk036 == 7:
                    vertex_stride = 44
                else:
                    print("Error:\tUnsupported Vertex Stride [%i]" % self.entries[i].info[ii].unk036)

                # format "Vertex Stride:\t%\n" vertex_stride
                # vertArray[entries[i].info[ii].vert_count] = [0.0, 0.0, 0.0]
                for v in range(0, self.entries[i].info[ii].vert_count):
                    fseek(f, (vert_addr + self.entries[i].info[ii].vert_addr + (v * vertex_stride)),
                          seek_set)
                    append(vertArray, [readFloat(f), readFloat(f), readFloat(f)])
                    if vertex_stride >= 28:
                        fseek(f, 8, seek_cur)  # append normArray ([readHalf f, readHalf f, readHalf f] * (readHalf f))
                        append(tvertArray, [readFloat(f), readFloat(f), 0.0])
                    else:
                        fseek(f, 4, seek_cur)  # readLong(f) # normal
                        append(tvertArray, [readHalf(f), readHalf(f), 0.0])
            
            mats = []
            mat = None
            for ii in range(0, self.entries[i].unk022):
                mat = StandardMaterial()
                mats.append(mat.data)
            
            msh = mesh(
                vertices=vertArray,
                faces=faceArray,
                tverts=[tvertArray],
                materialIDs=matidArray,
                materials=mats,
                obj_name=self.entries[i].name,
                flipAxis=True,
                lay_name=col_name,
                mscale=mscale
                )
        return None

class fhm_table_addr_entry:
    unk021 = 0
    addr = 0
    def read_addr_entry(self, f=fopen()):
        self.unk021 = readLong(f, unsigned)
        self.addr = readLong(f, unsigned)


class fhm_table_entry:
    unk031=0
    unk032 = 0
    unk033 = 0
    addr = 0
    size = 0
    def read_entry(self, f=fopen()):
        self.unk031 = readShort(f)
        self.unk032 = readShort(f)
        self.unk033 = readLong(f, unsigned)
        self.addr = readLong(f, unsigned)
        self.size = readLong(f, unsigned)


class fhm_file:
    fileid=0
    unk001 = 0
    unk002 = 0
    unk003 = 0
    unk004 = 0
    unk005 = 0
    unk006 = 0
    unk007 = 0
    unk008 = 0
    unk009 = 0
    unk010 = 0
    unk011 = 0
    file_count = 0
    file_addr_table =[]
    file_table =[]
    def read(self, f=fopen()):
        self.fileid = readLong(f, unsigned)
        if self.fileid != 0x004D4846:
            print("Error:\tInvalid File Type\n")
            return False
        
        self.unk001 = readLong(f, unsigned)
        self.unk002 = readLong(f, unsigned)
        self.unk003 = readLong(f, unsigned)
        self.unk004 = readLong(f, unsigned)
        self.unk005 = readLong(f, unsigned)
        self.unk006 = readLong(f, unsigned)
        self.unk007 = readLong(f, unsigned)
        self.unk008 = readLong(f, unsigned)
        self.unk009 = readLong(f, unsigned)
        self.unk010 = readLong(f, unsigned)
        self.unk011 = readLong(f, unsigned)
        self.file_count = readLong(f, unsigned)
        if self.file_count > 0:
            self.file_addr_table = [fhm_table_addr_entry] * self.file_count
            self.file_table = [fhm_table_entry] * self.file_count
            for i in range(0, self.file_count):
                self.file_addr_table[i] = fhm_table_addr_entry()
                self.file_addr_table[i].read_addr_entry(f)
    
            for i in range(0, self.file_count):
                fseek(f, (0x30 + self.file_addr_table[i].addr), seek_set)
                self.file_table[i] = fhm_table_entry()
                self.file_table[i].read_entry(f)
        return True

def dump_fhm(file=""):
    f = fopen(file, "rb")
    s = None

    fseek(f, 0x30, seek_set)
    count = readLong(f)

    fseek(f, (count * 8), seek_cur)

    pos = ftell(f)
    addr = 0
    size = 0
    type = ""
    for i in range(0, count):
        fseek(f, (pos + (i * 16)), seek_set)

    readLong(f)
    readLong(f)
    addr = readLong(f)
    size = readLong(f)

    fseek(f, (addr + 0x30), seek_set)
    type = "."
    for x in range(0, 4):
        type += chr(readByte(f))

    s = fopen((file + "_" + str(i) + type), "wb")

    fseek(f, (addr + 0x30), seek_set)
    for x in range(0, size):
        writeByte(s, (readByte(f)))

    fclose(s)
    fclose(f)

def read(file="", mscale = 1.0):
    fhm = fhm_file()
    type = 0
    ndxr = ndxr_file()
    fileID = 0
    
    f = fopen(file, "rb")
    if f.isGood:
        fname = getFilenameFile(file)
        fileID = readLong(f, unsigned)
        fseek(f, 0, seek_set)

        if fileID == 0x004D4846:  # FHM
            fhm.read(f)

            for i in range(0, len(fhm.file_table)):
                fseek(f, (fhm.file_table[i].addr + 0x30), seek_set)
                type = readLong(f, unsigned)
                fseek(f, (fhm.file_table[i].addr + 0x30), seek_set)
                if type == 0x5258444E:
                    ndxr = ndxr_file()
                    ndxr.read(f, mscale, fname + "_" + str(i + 1))
                else:
                    print("#%i\tUnknown Block:\t%i\t@ 0x%s\n" % (i, type, hex(fhm.file_table[i].addr + 0x30)))


        elif fileID == 0x5258444E:  # NDXR
            ndxr = ndxr_file()
            ndxr.read(f, mscale)
            
        elif fileID == 0x3350444E:  # NDP3 (Memory Dump)
            
            # a sample was provided from a memory dump
            # in which the addresses are assigned to memory
            # and are out of bounds of the supplied file sample
            # For this we need to try and derive the address
            # relative to the file and not the PS3 Memory block
            
            f.set_endian(False)
            fseek(f, 0x0A, seek_set)
            count = readShort(f)
            fseek(f, 0x5C, seek_set)
            addr_off = readLong(f) - (48 + (count * 0x30))
            print("addr_off:\t%i" % addr_off)
            fseek(f, 0, seek_set)
            
            
            ndxr = ndxr_file()
            ndxr.read(f, mscale, "", addr_off)
        else:
            print("Error:\tUnsupported File Type\n")

        fclose(f)

    else:
        print("Error:\tFailed to Read File\n")


# Callback when file(s) are selected
def acecombat_ah_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def acecombat_ah_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_acecombat_ah_imp"):  # print(bpy.ops.importhelper.acecombat_ah_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_acecombat_ah_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_acecombat_ah_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_acecombat_ah_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.acecombat_ah_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.fhm;*.ndxr;*.ndp3', options={'HIDDEN'}, subtype='FILE_PATH')

        # Variables
        filepath: bpy.props.StringProperty(subtype="FILE_PATH")  # full path of selected item (path+filename)
        filename: bpy.props.StringProperty(subtype="FILE_NAME")  # name of selected item
        directory: bpy.props.StringProperty(subtype="FILE_PATH")  # directory of the selected item
        files: bpy.props.CollectionProperty(type=bpy.types.OperatorFileListElement)  # a collection containing all the selected items as filenames

        # Controls
        my_float1: bpy.props.FloatProperty(name="Scale", default=1.0, description="Changes Scale of the imported Mesh")
        my_bool1: bpy.props.BoolProperty(name="Clear Scene", default=True, description="Deletes everything in the scene prior to importing")

        # Runs when this class OPENS
        def invoke(self, context, event):

            # Retrieve Settings
            try: self.filepath = bpy.types.Scene.acecombat_ah_imp_filepath
            except: bpy.types.Scene.acecombat_ah_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.acecombat_ah_imp_directory
            except: bpy.types.Scene.acecombat_ah_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.acecombat_ah_imp_my_float1
            except: bpy.types.Scene.acecombat_ah_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.acecombat_ah_imp_my_bool1
            except: bpy.types.Scene.acecombat_ah_imp_my_bool1 = bpy.props.BoolProperty(default=False)


            # Open File Browser
            # Set Properties of the File Browser
            context.window_manager.fileselect_add(self)
            context.area.tag_redraw()

            return {'RUNNING_MODAL'}

        # Runs when this Window is CANCELLED
        def cancel(self, context): print("run bitch")

        # Runs when the class EXITS
        def execute(self, context):

            # Save Settings
            bpy.types.Scene.acecombat_ah_imp_filepath = self.filepath
            bpy.types.Scene.acecombat_ah_imp_directory = self.directory
            bpy.types.Scene.acecombat_ah_imp_my_float1 = self.my_float1
            bpy.types.Scene.acecombat_ah_imp_my_bool1 = self.my_bool1

            # Run Callback
            acecombat_ah_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

            return {"FINISHED"}

            # Window Settings

        def draw(self, context):

            self.layout.row().label(text="Import Settings")

            self.layout.separator()
            self.layout.row().prop(self, "my_bool1")
            self.layout.row().prop(self, "my_float1")

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
            col.label(text="March 23, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.acecombat_ah_imp", text="Ace Combat Assault Horizon (*.fhm)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_acecombat_ah_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_acecombat_ah_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.acecombat_ah_imp('INVOKE_DEFAULT')



if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        #"C:\\Users\\Corey\\Desktop\\AuditionOnlien\\nozomi\\model_id\\mech\\airp\\d_tnd4\\d_tnd4_pcom.fhm"
        #"C:\\Users\\Corey\\Desktop\\AuditionOnlien\\nozomi\\model_id\\mech\\airp\\d_tnd4\\d_tnd4_pcom\\d_tnd4_pcom.fhm_13.NDXR"
        "G:\\WA3_memory\\f16xl.ndp3"
        )
    messageBox("Done!")
else: acecombat_ah_imp(True)

```
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-25T17:47:09+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

RythusOmega provided more memory dumps so the script was updated to work better with the samples they provided

Change Log:
        Major update to work better with PS3 memory Dumps
        Added Scan option in import dialog to scan for any nested mesh blocks
        Added support for fvf type 7 (44 bytes per vertex)
        Added fix to read names from memory dumps

```

    PythonScript:   [PC] Ace Combat Assault Horizon
    Author:         mariokart64n
    Date:           March 25, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-22
        Script Wrote

    2021-03-23
        Adapted to work with PS3 Memory dump from Ace Combat Infinity
    
    2021-03-25
        Major overhaul to work better with PS3 memory Dumps
        Added Scan option in import dialog to scan for any nested mesh blocks
        Added support for fvf type 7 (44 bytes per vertex)
        Added fix to read names from memory dumps

    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff


useOpenDialog = True


signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function
SEEK_ABS, SEEK_REL, SEEK_END = 0, 1, 2  # Enums for seek function


def messageBox(message="", title="Message Box", icon='INFO'):
    def draw(self, context): self.layout.label(text=message)

    bpy.context.window_manager.popup_menu(draw, title=title, icon=icon)
    return None


def clearListener(len=64):
    for i in range(0, len): print('')


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def getFilenameType(file):  # returns: ".jpg"
    return Path(file).suffix


def toUpper(string):
    return string.upper()


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

    def set_endian(self, isLittle = True):
        self.little_endian = isLittle
        return isLittle

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


def readHalf(bitStream):
    uint16 = bitStream.read_and_unpack('>H' if not bitStream.little_endian else '<H', 2)
    uint32 = (
            (((uint16 & 0x03FF) << 0x0D) | ((((uint16 & 0x7C00) >> 0x0A) + 0x70) << 0x17)) |
            (((uint16 >> 0x0F) & 0x00000001) << 0x1F)
    )
    return struct.unpack('f', struct.pack('I', uint32))[0]


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


def mesh_validate (vertices=[], faces=[]):
    #
    # Returns True if mesh is BAD
    #
    # check face index bound
    face_min = 0
    face_max = len(vertices) - 1
    
    for face in faces:
        for side in face:
            if side < face_min or side > face_max:
                print("Face Index Out of Range:\t[%i / %i]" % (side, face_max))
                return True
    return False

def mesh(
    vertices=[],
    faces=[],
    materialIDs=[],
    tverts=[],
    normals=[],
    colours=[],
    materials=[],
    mscale=1.0,
    flipAxis=False,
    obj_name="Object",
    lay_name='',
    position = (0.0, 0.0, 0.0)
    ):
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
        layer = bpy.data.collections.get(lay_name)
        if layer == None:
            layer = bpy.data.collections.new(lay_name)
            bpy.context.scene.collection.children.link(layer)
    else:
        if len(bpy.data.collections) == 0:
            layer = bpy.data.collections.new("Collection")
            bpy.context.scene.collection.children.link(layer)
        else:
            try:
                layer = bpy.data.collections[bpy.context.view_layer.active_layer_collection.name]
            except:
                layer = bpy.data.collections[0]
    

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
    if mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None
    
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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")

        

    # Assign Mesh to Object
    obj = bpy.data.objects.new(obj_name, msh)
    obj.location = position
    # obj.name = obj.name.replace(".", "_")

    for i in range(0, len(materials)):

        if len(obj.material_slots) < (i + 1):
            # if there is no slot then we append to create the slot and assign
            obj.data.materials.append(materials[i])
        else:
            # we always want the material in slot[0]
            obj.material_slots[0].material = materials[i]
        # obj.active_material = obj.material_slots[i].material

    if len(materialIDs) == len(obj.data.polygons):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i] % len(materials)
    elif len(materialIDs) > 0:
        print("Error:\tMaterial Index Out of Range")

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

class ndxr_entry_info_cmd_table2:
    unk081 = 0
    name_addr = 0
    name = ""
    unk083 = 0
    unk084 = 0
    unk085 = 0.0
    unk086 = 0.0
    unk087 = 0.0
    unk088 = 0.0

    def read_info_cmd_table2(self, strings_addr=0, f=fopen()):
        self.unk081 = readLong(f, unsigned)
        self.name_addr = readLong(f, unsigned)
        self.unk083 = readLong(f, unsigned)
        self.unk084 = readLong(f, unsigned)
        self.unk085 = readFloat(f)
        self.unk086 = readFloat(f)
        self.unk087 = readFloat(f)
        self.unk088 = readFloat(f)
        pos = ftell(f)
        fseek(f, (strings_addr + self.name_addr), seek_set)
        self.name = readString(f)
        fseek(f, pos, seek_set)


class ndxr_entry_info_cmd_table1:  # 24 bytes
    unk061 = 0
    unk062 = 0
    unk063 = 0
    unk064 = 0
    unk065 = 0
    unk066 = 0
    unk067 = 0
    unk068 = 0
    unk069 = 0
    unk070 = 0
    unk071 = 0
    unk072 = 0
    unk073 = 0
    unk074 = 0
    unk075 = 0
    unk076 = 0

    def read_info_cmd_table1(self, f=fopen()):
        self.unk061 = readByte(f, unsigned)
        self.unk062 = readShort(f, unsigned)
        self.unk063 = readLong(f, unsigned)
        self.unk064 = readByte(f, unsigned)
        self.unk065 = readShort(f, unsigned)
        self.unk066 = readLong(f, unsigned)
        self.unk067 = readByte(f, unsigned)
        self.unk068 = readByte(f, unsigned)
        self.unk069 = readByte(f, unsigned)
        self.unk070 = readByte(f, unsigned)
        self.unk071 = readByte(f, unsigned)
        self.unk072 = readByte(f, unsigned)
        self.unk073 = readByte(f, unsigned)
        self.unk074 = readByte(f, unsigned)
        self.unk075 = readByte(f, unsigned)
        self.unk076 = readByte(f, unsigned)


class ndxr_entry_info_cmd:
    unk041 = 0
    unk042 = 0
    unk043 = 0
    unk044 = 0
    unk045 = 0
    table1_count = 0  # count
    unk046 = 0
    unk047 = 0
    unk048 = 0
    unk049 = 0
    unk050 = 0
    table1 = []
    unk051 = 0
    unk052 = 0
    unk053 = 0
    table2 = []

    def read_info_cmd(self, strings_addr=0, f=fopen()):
        self.unk041 = readByte(f, unsigned)
        self.unk042 = readShort(f, unsigned)
        self.unk043 = readByte(f, unsigned)
        self.unk044 = readShort(f, unsigned)
        self.unk045 = readLong(f, unsigned)
        self.table1_count = readShort(f, unsigned)
        self.unk046 = readShort(f, unsigned)
        self.unk047 = readLong(f, unsigned)
        self.unk048 = readLong(f, unsigned)
        self.unk049 = readByte(f, unsigned)
        self.unk050 = readShort(f, unsigned)
        if self.table1_count > 0:
            self.table1 = [ndxr_entry_info_cmd_table1] * self.table1_count
            for i in range(0, self.table1_count):
                self.table1[i] = ndxr_entry_info_cmd_table1()
                self.table1[i].read_info_cmd_table1(f)
                self.unk051 = readByte(f, unsigned)
                self.unk052 = readShort(f, unsigned)
                self.unk053 = readLong(f, unsigned)
                i = -1
                while True:
                    i += 1
                    append(self.table2, (ndxr_entry_info_cmd_table2()))
                    self.table2[i].read_info_cmd_table2(strings_addr, f)
                    if self.table2[i].unk081 != 0x20: break


class ndxr_entry_info:
    face_addr = 0  # face buffer addr?
    vert_addr = 0  # vert buffer addr?
    unk033 = 0  # 0
    vert_count = 0  # vertex count?
    unk036 = 0  # 6
    unk037 = 0  # ? vertex format? 17=28bytes, 16=20bytes
    cmd_addr = 0
    cmd = ndxr_entry_info_cmd()
    unk038 = 0  # 0
    unk039 = 0  # 0
    unk040 = 0  # 0
    face_count = 0  # face count?
    unk042 = 0  # 0
    unk043 = 0  # 0
    unk044 = 0  # 0
    unk045 = 0  # 0

    def read_info(self, pos=0, strings_addr=0, f=fopen(), addr_off = 0):
        self.face_addr = readLong(f, unsigned)
        self.vert_addr = readLong(f, unsigned)
        self.unk033 = readLong(f, unsigned)
        self.vert_count = readShort(f, unsigned)
        self.unk036 = readByte(f, unsigned)
        self.unk037 = readByte(f, unsigned)
        self.cmd_addr = readLong(f, unsigned) - addr_off
        self.unk038 = readLong(f, unsigned)
        self.unk039 = readLong(f, unsigned)
        self.unk040 = readLong(f, unsigned)
        self.face_count = readShort(f, unsigned)
        self.unk042 = readShort(f, unsigned)
        self.unk043 = readLong(f, unsigned)
        self.unk044 = readLong(f, unsigned)
        self.unk045 = readLong(f, unsigned)
        if self.cmd_addr > 0:
            fseek(f, pos + self.cmd_addr, seek_set)
            self.cmd.read_info_cmd(strings_addr, f)


class ndxr_entry:
    unk011 = 0.0
    unk012 = 0.0
    unk013 = 0.0
    unk014 = 0.0
    unk015 = 0.0
    unk016 = 0.0
    unk017 = 0.0
    unk018 = 0
    name_addr = 0
    name = ""
    unk019 = 0
    unk020 = 0
    unk021 = 0
    unk022 = 0  # info count
    info_addr = 0
    info = []

    def read_entry(self, pos=0, strings_addr=0, f=fopen(), addr_off = 0):
        self.unk011 = readFloat(f)
        self.unk012 = readFloat(f)
        self.unk013 = readFloat(f)
        self.unk014 = readFloat(f)
        self.unk015 = readFloat(f)
        self.unk016 = readFloat(f)
        self.unk017 = readFloat(f)
        self.unk018 = readLong(f, unsigned)
        self.name_addr = readLong(f, unsigned)
        self.unk019 = readShort(f, unsigned)
        self.unk020 = readShort(f, unsigned)
        self.unk021 = readShort(f, unsigned)
        self.unk022 = readShort(f, unsigned)
        self.info_addr = readLong(f, unsigned) - addr_off
        fseek(f, (strings_addr + self.name_addr - addr_off), seek_set)
        if addr_off == 0:
            self.name = readString(f)
        #print("NameAddr:\t%i" % (self.name_addr))
        #print("Name:\t%s" % self.name)
        if self.unk022 > 0 and self.info_addr > 0:
            self.info = [ndxr_entry_info] * self.unk022
            for i in range(0, self.unk022):
                fseek(f, (pos + self.info_addr + (i * 48)), seek_set)
                self.info[i] = ndxr_entry_info()
                self.info[i].read_info(pos, strings_addr, f, addr_off)


class ndxr_file:
    fileid = 0
    unk001 = 0
    unk002 = 0
    count = 0
    unk007 = 0
    unk003 = 0
    face_addr = 0
    face_size = 0
    vert_size = 0
    unk004 = 0
    unk005 = 0
    unk006 = [0.0, 0.0, 0.0]
    entries = []

    def read(self, f=fopen(), mscale = 1.0, col_name = "", addr_off = 0):
        pos = ftell(f)
        header_size = 48
        self.fileid = readLong(f, unsigned)
        self.unk001 = readLong(f, unsigned)
        self.unk002 = readShort(f, unsigned)
        self.count = readShort(f, unsigned)
        self.unk007 = readShort(f, unsigned)
        self.unk003 = readShort(f, unsigned)
        self.face_addr = readLong(f, unsigned)
        self.face_size = readLong(f, unsigned)
        self.vert_size = readLong(f, unsigned)
        self.unk004 = readLong(f, unsigned)
        self.unk005 = readLong(f, unsigned)
        self.unk006 = [readFloat(f), readFloat(f), readFloat(f)]

        self.face_addr += pos + header_size
        vert_addr = self.face_addr + self.face_size
        #print("vert_addr:\t%i" % vert_addr)
        strings_addr = vert_addr + self.vert_size
        #print("strings_addr:\t%i" % strings_addr)
        
        
        entry_size = 48
        vertArray = []
        normArray = []
        faceArray = []
        matidArray = []
        tvertArray = []
        msh = None
        tmp = []
        vertex_stride = 0
        face = [0, 0, 0]
        facePosition = 0
        faceCW = True
        maxIndex = 0
        
        
        # calculate string buffer offset for memory dumps
        str_addrs = []
        str_addr_offset = 0
        
        
        if self.count > 0:
            self.entries = [ndxr_entry] * self.count
            for i in range(0, self.count):
                fseek(f, (pos + header_size + (i * entry_size)), seek_set)
                self.entries[i] = ndxr_entry()
                self.entries[i].read_entry(pos, strings_addr, f, addr_off)
                appendIfUnique(str_addrs, self.entries[i].name_addr)
        
        
        if addr_off > 0 and len(str_addrs) > 0:
            str_addrs.sort()
            str_buffer = []
            fseek(f, strings_addr, seek_set)
            for i in range(0, len(str_addrs)):
                str_buffer.append(readString(f))
                fseek(f, ((16 - ((ftell(f)) % 16)) % 16), seek_cur)
            
            for i in range(0, self.count):
                self.entries[i].name = str_buffer[findItem(str_addrs, self.entries[i].name_addr)]
        
        
        # Generate Size List to Estimate the Vertex Stride
        for i in range(0, self.count):
            for ii in range(0, self.entries[i].unk022):
                appendIfUnique(tmp, (self.entries[i].info[ii].vert_addr + vert_addr))

        append(tmp, strings_addr)
        tmp.sort()
        
        for i in range(0, self.count):  # mesh entry
            vertArray = []
            tvertArray = []
            faceArray = []
            normArray = []
            matidArray = []
            facePosition = 0
            for ii in range(0, self.entries[i].unk022):  # level of detail meshes?

                # Read Faces
                fseek(f, (self.face_addr + self.entries[i].info[ii].face_addr), seek_set)
                v = 0
                
                while v < self.entries[i].info[ii].face_count:
                    faceCW = True
                    face[0] = readShort(f, unsigned)
                    face[1] = readShort(f, unsigned)
                    v += 2
                    while v < self.entries[i].info[ii].face_count:
                        face[2] = readShort(f, unsigned)
                        v += 1
                        if face[0] == 0xFFFF or face[1] == 0xFFFF or face[2] == 0xFFFF: break
                        if face[0] != face[1] and face[1] != face[2] and face[0] != face[2]:
                            if faceCW:
                                append(faceArray, [face[0] + facePosition, face[1] + facePosition, face[2] + facePosition])
                            else:
                                append(faceArray, [face[0] + facePosition, face[2] + facePosition, face[1] + facePosition])
                            append(matidArray, ii)
                        faceCW = not faceCW
                        face = [face[1], face[2], face[0]]
                        
                facePosition += self.entries[i].info[ii].vert_count
                vertex_stride = 20
                # Reading Vertices
                if self.entries[i].info[ii].vert_count != 0:
                    vertex_stride = int(
                        (tmp[(findItem(tmp, self.entries[i].info[ii].vert_addr + vert_addr)) + 1] -
                        (self.entries[i].info[ii].vert_addr + vert_addr)) / self.entries[i].info[ii].vert_count
                        )
                    vertex_stride = int(vertex_stride - (vertex_stride % 4))

                #print("Vertex Addr:\t%i" % (self.entries[i].info[ii].vert_addr + vert_addr))
                # format "Vertex Count:\t%\n" entries[i].info[ii].vert_count

                #print("Vertex Format:\t%i" % self.entries[i].info[ii].unk036)
                if self.entries[i].info[ii].unk036 == 0:
                    vertex_stride = 20
                elif self.entries[i].info[ii].unk036 == 6:
                    vertex_stride = 28
                elif self.entries[i].info[ii].unk036 == 7:
                    vertex_stride = 44
                else:
                    print("Error:\tUnsupported Vertex Stride [%i]" % self.entries[i].info[ii].unk036)

                #print("Vertex Stride:\t%i" % vertex_stride)
                # vertArray[entries[i].info[ii].vert_count] = [0.0, 0.0, 0.0]
                for v in range(0, self.entries[i].info[ii].vert_count):
                    fseek(f, (vert_addr + self.entries[i].info[ii].vert_addr + (v * vertex_stride)), seek_set)
                    
                    if self.entries[i].info[ii].unk036 == 0:
                        append(vertArray, [readFloat(f), readFloat(f), readFloat(f)])
                        fseek(f, 4, seek_cur)  # readLong(f) # normal
                        append(tvertArray, [readHalf(f), readHalf(f), 0.0])
                        
                        
                    elif self.entries[i].info[ii].unk036 == 6:
                        append(vertArray, [readFloat(f), readFloat(f), readFloat(f)])
                        fseek(f, 8, seek_cur)  # append normArray ([readHalf f, readHalf f, readHalf f] * (readHalf f))
                        append(tvertArray, [readFloat(f), readFloat(f), 0.0])
                        
                        
                    elif self.entries[i].info[ii].unk036 == 7:
                        append(vertArray, [readFloat(f), readFloat(f), readFloat(f)])
                        fseek(f, 24, seek_cur)
                        append(tvertArray, [readFloat(f), readFloat(f), 0.0])
                        
                        
                    else:
                        append(vertArray, [readFloat(f), readFloat(f), readFloat(f)])
                        
                    

                    
                    
            
            mats = []
            mat = None
            for ii in range(0, self.entries[i].unk022):
                mat = StandardMaterial()
                mats.append(mat.data)
            
            #print("name:\t%s" % self.entries[i].name)
            msh = mesh(
                vertices=vertArray,
                faces=faceArray,
                tverts=[tvertArray],
                materialIDs=matidArray,
                materials=mats,
                obj_name=self.entries[i].name,
                flipAxis=True,
                lay_name=col_name,
                mscale=mscale
                )
        return None

class fhm_table_addr_entry:
    unk021 = 0
    addr = 0
    def read_addr_entry(self, f=fopen()):
        self.unk021 = readLong(f, unsigned)
        self.addr = readLong(f, unsigned)


class fhm_table_entry:
    unk031=0
    unk032 = 0
    unk033 = 0
    addr = 0
    size = 0
    def read_entry(self, f=fopen()):
        self.unk031 = readShort(f)
        self.unk032 = readShort(f)
        self.unk033 = readLong(f, unsigned)
        self.addr = readLong(f, unsigned)
        self.size = readLong(f, unsigned)


class fhm_file:
    fileid=0
    unk001 = 0
    unk002 = 0
    unk003 = 0
    unk004 = 0
    unk005 = 0
    unk006 = 0
    unk007 = 0
    unk008 = 0
    unk009 = 0
    unk010 = 0
    unk011 = 0
    file_count = 0
    file_addr_table =[]
    file_table =[]
    def read(self, f=fopen()):
        self.fileid = readLong(f, unsigned)
        if self.fileid != 0x004D4846:
            print("Error:\tInvalid File Type\n")
            return False
        
        self.unk001 = readLong(f, unsigned)
        self.unk002 = readLong(f, unsigned)
        self.unk003 = readLong(f, unsigned)
        self.unk004 = readLong(f, unsigned)
        self.unk005 = readLong(f, unsigned)
        self.unk006 = readLong(f, unsigned)
        self.unk007 = readLong(f, unsigned)
        self.unk008 = readLong(f, unsigned)
        self.unk009 = readLong(f, unsigned)
        self.unk010 = readLong(f, unsigned)
        self.unk011 = readLong(f, unsigned)
        self.file_count = readLong(f, unsigned)
        if self.file_count > 0:
            self.file_addr_table = [fhm_table_addr_entry] * self.file_count
            self.file_table = [fhm_table_entry] * self.file_count
            for i in range(0, self.file_count):
                self.file_addr_table[i] = fhm_table_addr_entry()
                self.file_addr_table[i].read_addr_entry(f)
    
            for i in range(0, self.file_count):
                fseek(f, (0x30 + self.file_addr_table[i].addr), seek_set)
                self.file_table[i] = fhm_table_entry()
                self.file_table[i].read_entry(f)
        return True

def dump_fhm(file=""):
    f = fopen(file, "rb")
    s = None

    fseek(f, 0x30, seek_set)
    count = readLong(f)

    fseek(f, (count * 8), seek_cur)

    pos = ftell(f)
    addr = 0
    size = 0
    type = ""
    for i in range(0, count):
        fseek(f, (pos + (i * 16)), seek_set)

    readLong(f)
    readLong(f)
    addr = readLong(f)
    size = readLong(f)

    fseek(f, (addr + 0x30), seek_set)
    type = "."
    for x in range(0, 4):
        type += chr(readByte(f))

    s = fopen((file + "_" + str(i) + type), "wb")

    fseek(f, (addr + 0x30), seek_set)
    for x in range(0, size):
        writeByte(s, (readByte(f)))

    fclose(s)
    fclose(f)


def calc_addr_offset(f = fopen(), addr = 0):
    addr_off = 0
    fseek(f, addr + 0x0A, seek_set)
    count = readShort(f)
    if count > 0:
        fseek(f, addr + 0x5C, seek_set)
        addr_off = readLong(f, unsigned) - (48 + (count * 0x30))
    fseek(f, addr, seek_set)
    return addr_off

def calc_endian(f = fopen()):
    cur = ftell(f)
    fseek(f, 10, seek_cur)
    if readShort(f, unsigned) > 255:
        f.set_endian(False)
    fseek(f, cur, seek_set)
    return None


def read(file="", mscale = 1.0, scanFile = False):
    fhm = fhm_file()
    type = 0
    ndxr = ndxr_file()
    fileID = 0
    addr_off = 0
    
    
    
    f = fopen(file, "rb")
    
    
    if f.isGood and f.size > 24:
        fname = getFilenameFile(file)
        
        
        if not scanFile:
            
            fileID = readLong(f, unsigned)
            
            # return to start of file
            fseek(f, 0, seek_set)
            
        
            if fileID == 0x004D4846:  # FHM
                fhm.read(f)

                for i in range(0, len(fhm.file_table)):
                    fseek(f, (fhm.file_table[i].addr + 0x30), seek_set)
                    type = readLong(f, unsigned)
                    fseek(f, (fhm.file_table[i].addr + 0x30), seek_set)
                    if type == 0x5258444E:
                        ndxr = ndxr_file()
                        ndxr.read(f, mscale, fname + "_" + str(i + 1))
                    else:
                        print("#%i\tUnknown Block:\t%i\t@ 0x%s\n" % (i, type, hex(fhm.file_table[i].addr + 0x30)))


            elif fileID == 0x5258444E:  # NDXR
                calc_endian(f)
                addr_off = calc_addr_offset(f, ftell(f))
                print("addr_off:\t%i" % addr_off)
                ndxr = ndxr_file()
                ndxr.read(f, mscale, "", addr_off)
                
            elif fileID == 0x3350444E:  # NDP3 (Memory Dump)
                
                # a sample was provided from a memory dump
                # in which the addresses are assigned to memory
                # and are out of bounds of the supplied file sample
                # For this we need to try and derive the address
                # relative to the file and not the PS3 Memory block
                
                calc_endian(f)
                addr_off = calc_addr_offset(f, ftell(f))
                
                ndxr = ndxr_file()
                ndxr.read(f, mscale, "", addr_off)


            else:
                print("Error:\tUnsupported File Type\n")
        else:
            type = 0
            files_found = []
            endian_check = False
            while (ftell(f) + 8) < f.size:
                type = readLong(f)
                if type == 0x4E445033 or type == 0x5258444E or type == 0x3350444E or type == 0x4E445852:
                    if not endian_check:
                        # need to detect the file endian
                        fseek(f, -4, seek_cur)
                        calc_endian(f)
                        fseek(f, 4, seek_cur)
                        endian_check = True
                    files_found.append(ftell(f) - 4)
                    fseek(f, ftell(f) - 8 + readLong(f), seek_cur)
                    fseek(f, (16-(ftell(f) % 16)) % 16, seek_cur)
                fseek(f, 12, seek_cur)
            
            # Import Each Located Mesh
            for i in range(0, len(files_found)):
                
                # Derive Address Offset
                addr_off = calc_addr_offset(f, files_found[0])
                print("addr_off[%i]:\t%i" % (i, addr_off))
                ndxr = ndxr_file()
                ndxr.read(f, mscale, fname + "_" + str(i), addr_off)
        
        fclose(f)

    else:
        print("Error:\tFailed to Read File\n")


# Callback when file(s) are selected
def acecombat_ah_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0, scanFile = False):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale, scanFile)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def acecombat_ah_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_acecombat_ah_imp"):  # print(bpy.ops.importhelper.acecombat_ah_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_acecombat_ah_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_acecombat_ah_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_acecombat_ah_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.acecombat_ah_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.fhm;*.ndxr;*.ndp3', options={'HIDDEN'}, subtype='FILE_PATH')

        # Variables
        filepath: bpy.props.StringProperty(subtype="FILE_PATH")  # full path of selected item (path+filename)
        filename: bpy.props.StringProperty(subtype="FILE_NAME")  # name of selected item
        directory: bpy.props.StringProperty(subtype="FILE_PATH")  # directory of the selected item
        files: bpy.props.CollectionProperty(type=bpy.types.OperatorFileListElement)  # a collection containing all the selected items as filenames

        # Controls
        my_float1: bpy.props.FloatProperty(name="Scale", default=1.0, description="Changes Scale of the imported Mesh")
        my_bool1: bpy.props.BoolProperty(name="Clear Scene", default=True, description="Deletes everything in the scene prior to importing")
        my_bool2: bpy.props.BoolProperty(name="File Scan", default=True, description="scans file for known signatures and imports them")

        # Runs when this class OPENS
        def invoke(self, context, event):

            # Retrieve Settings
            try: self.filepath = bpy.types.Scene.acecombat_ah_imp_filepath
            except: bpy.types.Scene.acecombat_ah_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.acecombat_ah_imp_directory
            except: bpy.types.Scene.acecombat_ah_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.acecombat_ah_imp_my_float1
            except: bpy.types.Scene.acecombat_ah_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.acecombat_ah_imp_my_bool1
            except: bpy.types.Scene.acecombat_ah_imp_my_bool1 = bpy.props.BoolProperty(default=False)
            
            try: self.my_bool2 = bpy.types.Scene.acecombat_ah_imp_my_bool2
            except: bpy.types.Scene.acecombat_ah_imp_my_bool2 = bpy.props.BoolProperty(default=True)


            # Open File Browser
            # Set Properties of the File Browser
            context.window_manager.fileselect_add(self)
            context.area.tag_redraw()

            return {'RUNNING_MODAL'}

        # Runs when this Window is CANCELLED
        def cancel(self, context): print("run *SPAM*")

        # Runs when the class EXITS
        def execute(self, context):

            # Save Settings
            bpy.types.Scene.acecombat_ah_imp_filepath = self.filepath
            bpy.types.Scene.acecombat_ah_imp_directory = self.directory
            bpy.types.Scene.acecombat_ah_imp_my_float1 = self.my_float1
            bpy.types.Scene.acecombat_ah_imp_my_bool1 = self.my_bool1
            bpy.types.Scene.acecombat_ah_imp_my_bool2 = self.my_bool2

            # Run Callback
            acecombat_ah_imp_callback(
                self.directory + "\\", self.files, self.my_bool1, 
                self.my_float1, 
                self.my_bool2
                )

            return {"FINISHED"}

            # Window Settings

        def draw(self, context):

            self.layout.row().label(text="Import Settings")

            self.layout.separator()
            self.layout.row().prop(self, "my_bool1")
            self.layout.row().prop(self, "my_bool2")
            self.layout.row().prop(self, "my_float1")

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
            col.label(text="March 23, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.acecombat_ah_imp", text="Ace Combat Assault Horizon (*.fhm)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_acecombat_ah_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_acecombat_ah_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.acecombat_ah_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        #"C:\\Users\\Corey\\Desktop\\AuditionOnlien\\nozomi\\model_id\\mech\\airp\\d_tnd4\\d_tnd4_pcom.fhm"
        #"C:\\Users\\Corey\\Desktop\\AuditionOnlien\\nozomi\\model_id\\mech\\airp\\d_tnd4\\d_tnd4_pcom\\d_tnd4_pcom.fhm_13.NDXR"
        #"G:\\WA3_memory\\f16xl.ndp3"
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\ACIdumpsplusAC6dumpsamples\\fa44.ndp3"
        )
    messageBox("Done!")
else: acecombat_ah_imp(True)

```
## Post #8
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-01-25T23:14:39+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

Alright, so it was some months since the last activity of this thread, and considering the AC fans from time got the curiosity thanks to me, but seeing the dumping process wasn't very detailed, i decided to release a mini guide i made of the whole process during August, so for people that would like to give a try, despite the obstacles the process got, and still has, now you're free to try themselves

[https://1drv.ms/u/s!ApONtI1SBUFngso5VYA ... g?e=KO7xyJ](https://1drv.ms/u/s!ApONtI1SBUFngso5VYASFX-R7wSJCg?e=KO7xyJ)

(̶B̶T̶W̶,̶ ̶t̶h̶i̶s̶ ̶w̶i̶l̶l̶ ̶b̶e̶ ̶m̶y̶ ̶l̶a̶s̶t̶ ̶a̶c̶t̶i̶v̶i̶t̶y̶ ̶f̶o̶r̶ ̶n̶o̶w̶ ̶i̶n̶ ̶e̶n̶t̶e̶r̶i̶n̶g̶ ̶X̶e̶n̶t̶a̶x̶/̶Z̶e̶n̶h̶a̶x̶,̶ ̶c̶u̶r̶r̶e̶n̶t̶l̶y̶ ̶i̶'̶m̶ ̶b̶u̶s̶y̶ ̶w̶i̶t̶h̶ ̶r̶e̶a̶l̶ ̶l̶i̶f̶e̶ ̶i̶s̶s̶u̶e̶s̶ ̶o̶n̶ ̶m̶y̶ ̶e̶n̶d̶,̶ ̶d̶e̶c̶i̶d̶e̶d̶ ̶t̶o̶ ̶g̶i̶v̶e̶ ̶t̶h̶e̶m̶ ̶p̶r̶i̶o̶r̶i̶t̶y̶ ̶a̶n̶d̶ ̶s̶a̶c̶r̶i̶f̶i̶c̶e̶ ̶o̶v̶e̶r̶ ̶m̶y̶ ̶h̶o̶b̶b̶y̶ ̶r̶o̶u̶t̶i̶n̶e̶,̶ ̶t̶h̶e̶r̶e̶'̶s̶ ̶n̶o̶ ̶E̶T̶A̶ ̶o̶f̶ ̶w̶h̶e̶n̶ ̶i̶'̶l̶l̶ ̶b̶e̶ ̶g̶e̶t̶t̶i̶n̶g̶ ̶t̶h̶o̶s̶e̶ ̶s̶o̶l̶v̶e̶d̶,̶ ̶s̶o̶ ̶i̶t̶'̶l̶l̶ ̶t̶a̶k̶e̶ ̶t̶h̶e̶ ̶t̶i̶m̶e̶ ̶i̶t̶ ̶n̶e̶e̶d̶s̶)̶
## Post #9
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2022-09-12T19:55:30+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

[Follow up from this thread](https://forum.xentax.com/viewtopic.php?f=16&t=11681&p=187072#p187104)

[https://github.com/GreenTrafficLight/Ac ... nder-Addon](https://github.com/GreenTrafficLight/Ace-Combat-Blender-Addon)
( Putting the link to the Blender Addon just in case )

So far I worked mainly on the ACI samples you gave, I didn't add support for the AC6 models for now since there is a different data ( GYZ ) which maybe replace the MNT/MOP2 since they aren't present here. But I added support for the AC6 samples like the Stauros warhead and the SU-33 prop.

For ACI, you will have to tell me if there are models that doesn't work since I think some may be missing MNT/NDP3 and mess up the entire armature order. So I guess I pretty much got lucky with these models.

Also since they are memory dumps, I think the emulator messed up the normals, so I didn't import them.

For the o_/d_ models, they can be imported but I don't think it's working 100% ( shadow meshes are missing and there maybe a error in the linking of empty, though it doesn't seem affect anything ) 




I will see what can I do with the AC6 samples since it may be difficult due to the fact they are memory dumps + a slighty different format.
## Post #10
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-09-14T00:58:19+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

Sorry for late reply, i went a bit busy during those days, at the time i went to write, a storm came into my region, but finally tested it out to check, as you said, don't worry due i'll be giving bug report of the script along working on the memory dumps, at least i found out i had some complete ones i assembled in hands, and two errors already occured from the tests, one which is minimum, which is a index list error with the MNT data but seems to not be such destructive as the models are imported(i think is this linked error you mentioned), and the first major glitch, the XFA-33 Fenrir model fails to parse the MNT data correctly, even that the structure is still the same



In general, the conception is the same as the first version tests, the workflow is much better now that the pivots are in their correct positions, and it still retrieves the sockets, but now applied to the ACI models, i don't remember sharing a X-02A memory dump at public, so i can say you followed my guide and the reference of the Su-33 one i sent to get by yourself, which is a nice touch

About the addition of the o_/d_ support, which summed with the standalone NDP3/NDXR dump reading, is indeed as how i expected, and it turned out to be very powerful, as when i was checking the models folder, i decided to test with William Bishop's character model for the giggles, and suprisingly, it frightening worked very good, even if it wasn't the main purpose




Just a minimum detail on the aspect of the Su-33 prop, nice it went able to begin parsed, but still, part of the issue with it wasn't yet solved due the issue with it was all the UV maps begin packed into a single one, and by the lack of materials is annoying due as from what i seen, i'll probably need to use text scripts or addons to fix that. i know the mesh is originaly a single one, and not sure if a O_OBJ could be read to separate parts based on UV, but yeah, in case i may look into solving this one if it turns out to not be possible, which about the normals, don't worry either as from what i checked, the model layout still went the same as how they looked on Mario's script


But overall, really satisfied with the current update, about the AC6 update, don't worry as yeah, i would already expect it would look different by the overall structure begin different on the other data aside of the NDXR, and from the rigged models, Aigaion is one of them that i can remember begin animated and unique, as the roster also appeared on the later games but still i would like to check them to verify if they got unique pylons, as the differences they'll probably have are on the cockpit aspect due some stuff worked different compared to the later two

The approximate ETA i may send a new reply will probably after the memory dumps are finished, probably more due even i had some spare time, i'm still busy with projects on my hand, so if i became a bit AFK, is because of that








---









*(texture colors are approximates)
**(first pictures are based on the PS1 models)
## Post #11
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-10-04T16:22:10+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

Hi, first, but most, i'm really, really sorry for the silence since, after the day i posted the previous message, at the following day the https connection to Xentax expired because of the certificate, isn't the first time as last year the same thing did occured, even that i could make a exception to enter the site earlier, as Xentax always showed with the triangle warning symbol, i didn't wanted to play dumb as yeah, forums are one thing compared to like, normal websites which you wouldn't need to input most of the time, i did a exception today, and for now, Firefox didn't warned about if i want to revert, but just to be safe, i won't be posting images today as is one of the flags mentioned
(not sure if a Xentax staff would be reading this, but if you could explain if when a certificate expires, i could still use Xentax fine, or what i did was correct)

Aside of a really busy previous week, i did tested out the last revision of the script, which now fixed the errors of the linked rigs and the XFA-33 imcompatbility, along it now can import the remaining data outside of the FHM stuff like the missile and emblem models, some dumps went already uploaded to the repository, despite i would need to revise later some as the ADF aircraft for some reason is lacking the emblem meshes, and noticed their range was outsourced above the normal space, but i'll need to focus on this later as yeah, currently i'm without a GPU at the moment, sent them to technical support already, and expecting to get news next week, after that, i won't be able to focus still due aside of severe stress tests(due i paid for a reballing service) due i also got a project that went pending and i'll need to return after i get the GPU in my hands

Tested out also reading the FHM dumps i did for AC6, but as expected by them begin placeholder containers of the sciprt, i think this is why they crash during the loading process, however the standalone NDXR/NDP3 dumps only still works like a charm

Not sure if Green will be reading this now, as probably if the certificate also striked him, but yeah, don't worry about needing to rush the progress, take your time, however i apologize for the sudden silence since, as it wasn't my fault, but more of website shenanigans
## Post #12
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2022-10-08T15:55:01+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

EDIT : Nevermind, got the response from Megalith, Ignore that post, I assumed you got in contact with Razgriz after reading your DPL Zenhax thread, which I turned out to be wrong

Haha actually I should be the one sorry for the silence since I didn't want to bump the thread about the small updates I made on the script. Though since you bumped it, there's something I wanted to talk you about. 

I recently looked in the [open-horizon GitHub repository](https://github.com/undefined-darkness/open-horizon/tree/040376952e3d5b2ef813081ab2dfa70a657471c1) and found many interesting things. Example being the FHM format being more detailed than the one in Smash Forge ( I should have used that instead lol ) and apparently proving that the animations aren't quantized aka compressed. So I'm planning to rewrite the entire script following open-horizon code.

But the thing that interest me the most ( I asked Megalith to ask you about this, don't know if you seen his email. Though he is busy now so I think it better to continue the research in this thread ) is the [decrypt table](https://github.com/undefined-darkness/open-horizon/blob/040376952e3d5b2ef813081ab2dfa70a657471c1/containers/decrypt.h) that you can find in the repositry. It's apparently used in the [DPL code](https://github.com/undefined-darkness/open-horizon/blob/040376952e3d5b2ef813081ab2dfa70a657471c1/containers/dpl.cpp) but I didn't see being used for the encrypted DPL in the ACAH PC version anywhere. But I still wonder if It can manage to decrypt it since it work for Ace Combat 6 when I used converted_location ( managed to download from webarchive since the download link doesn't work anymore, [here if you want it](https://www.mediafire.com/file/daagxpf6qmoy3lo/open-horizon-demo7.5-alpha2.zip/file), file too big to attach it ). Since AC6 and ACI / ACAH use the same game engine, I'm just wondering if it use the same crypt table. 

And I was also wondering if you can ask the author if it actually decrypt ACAH PC encrypted DPL since you managed get in contact with the author. And if we are lucky and it decrypt it, then ACI maybe use the same crypt table.
## Post #13
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-10-09T00:04:02+00:00
- Post Title: Ace Combat Infinity memory dump research(UPDATE)

Don't worry, as yeah, i did write the reply during the morning period, so i had a notion if would be delievered later when i woke up, unfortunately, i really wanted to have some sort of contact with Razgriz, but the closest i went was at the time i send the email about the ACI updates, i had plans at trying to entering in contact with her by email due it was linked on the Github page, but after the reply she mentioned about not liking social networks or Discord, i decided to avoid bothering her, as yeah, she probably got new interests to focus which turned Open Horizon inrelevant, like the PC version begin unlisted on Steam, AC7 and PW release and modding scenarios, other modders/researcher doing their homework like Charles(DtheD0g) with the PS2 games, which on the comment i asked to be redirected or the one i wrote, i tried to mentioning it to see if she would be interested due it was one of her wishlists for the project, but yeah, i can understand her reasons she probably won't want to continue the project, as mentioned on ZX Studio, there were times she gave up of the project before by begin demanding, but until then, the situation wasn't critical to the point of like, people needing to go to gray areas to play Open Horizion, as it required the game files to run the frontend based on Nya Engine

From the rest, i gave most of the information i gathered based on reading the articles and updates from Open Horizon at the time, summed with part of my research and tests, by the FHM begin more documented, as the first posts she showed some previews of the models begin preloaded, probably the dumps will require more external files, like dumping the MNT data or other container that refers to them, the good thing is at least you can do those for the testing purposes, so with the script begin updated, those new dependencies will be taken notes later for the repository at both files and guides

Seeing QDF tool is effective, and the containers folder of Github contains most of her research through the formats, the best i can say is indeed, the DPL probably got documented to work at least, even if only for the DATA.PAC of the QDF's, due Open Horizon uses that data when loading the file on the frontend, showing the correct skin and some interesing stuff like dummy textures for Shinden, and except for the datapack.bin and the QDF's, most of the DPL .PAC follows the same structure, of what she mentioned of a XOR deflate compression

So yeah, the DPL script i know it'll take some considerable time, as compared to the model ones which i helped with part from my research, part from Mario and Smash Forge, i read you mentioned about writing a quick test build based on the codes with Python, but it didn't worked well, which i guess the container documentation was written in C# or C++, when ACAH and ACI suprisingly uses LUA script for some files like on the missions by default, there are chances the code could be very WIP and obviously it won't work, despite i have my doubts seeing Razgriz had to research a bit of the DPL to open DATA.PAC, at the time i also tried to use Visual Studio to convert the QDF Tool into a "DPL Tool" replacing the callbacks of the QDF code to the DPL ones, but it didn't worked as yeah, swaping code bytes isn't simple like in common modding techniques, along currently i don't have VS2019 at my computer due my SSD is only 110GB, and most of the coding programs/files tend to eat a considerable part of the space when instaling

At least, wish you good luck if you indeed manage to adapt the current leftovers of Open Horizon for the first breakthrough of the DPL files, which will be a huge thing as yeah, probably they are even chances my ACI revival project may goes forward, if some of the ideas i could try with the unencrypted files indeed works, despite yeah, i may even take a bit of time to check it by default, due i got pending projects on my end for now, and i'll need to focus on those first, after that, i'll probably be AFK yet due i'll need to focus on some IRL plans i had related to job offers and studies, so yeah, compared to reversing models, i know the DPL will be a very complex task by using a strong encryption and compression, so take your time
