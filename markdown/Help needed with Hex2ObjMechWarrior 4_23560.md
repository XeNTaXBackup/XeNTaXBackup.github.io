## Post #1
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-07T23:28:53+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

So, I need some help with Hex2Obj.

Lately I've been trying to extract the models of the mechs from their .erf files, with mixed results.

I decided to try out/learn Hex2Obj, and while I've managed to get a relatively good understanding of the program and other hex stuff, I'm unable to find the info I need to convert it (mainly the faceindice/vertex counts.)

I've attached an example of one of the erf files I want to convert, to see if you guys can take a look.

I've also included a bonus file, from the MekPak 3, which has some kind of encryption on it, if you wanna look at that too. However, you can just ignore it for now, since I just want to figure out the base game's .erfs.

Help would be much appreciated, and if you need any other clarifications, let me know.
[atl_hip.zip](https://xentaxbackup.github.io/file/19670_atl_hip.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-08T07:27:46+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

It's byte face indices at 0x6DB in atl_hip.erf, a feature which hex2obj misses. (Maybe try out Bigchillghost's AMR?)
.



atl_hip-erf.png (19.86 KiB) Viewed 250 times

(first submesh only, used 82 vertices only instead of 137, see H2O file)
Looks like there's 6 sub meshes in sum, face indices blocks preceeded by the string @aatl0
.
H2O file for a point cloud (toggle noPtC to PtCld in hex2obj):

0x0 500
Vb1
12 99
0x43 137
040000
0x0 255
## Post #3
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-08T13:21:08+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

Thanks for the help shakotay.

I'll see if I can use this as an example to extract the other pieces.
## Post #4
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-08T13:36:11+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

I'm a bit confused as to where I put in the information.

Would you mind showing me where I put it in?
## Post #5
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-08T14:30:10+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

1 last quick note though

 - @aat10 is also the name of the models texture file.
 - The submeshes are most likely the LODs.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-08T15:43:13+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

> Reply from OPR23b ↑Mon Mar 08, 2021 9:36 pm at Mon Mar 08, 2021 9:36 pm
>
> 
I'm a bit confused as to where I put in the information.

Would you mind showing me where I put it in?It's not sufficient to put in params - you're strongly suggested to do the tutorial ('tut' button)
.



atk_hip-erf-point-cloud.png (20.5 KiB) Viewed 226 times



And as I wrote: hex2obj doesn't support byte face indices!
## Post #7
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-08T15:44:27+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

Ah, i see

I'll do that later then (since I'm busy right now.)
## Post #8
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-10T14:23:24+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

After trying to searching the .erf file in a hex editor for a bit, I think I need some help.

I'd hate to ask, but could someone tell me the locations of the necessary parts in the file? (vertices, UVs, etc.)
I get where the indices start, thanks to shakotay, but I'm honestly lost with the other pieces of info.
Just need the information for atl_hip.erf, and I should be able to use the information from that erf to convert other files.

And a reminder, the sample is at the first post as an attachment.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-10T15:49:52+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

vertices to be found at 0x43. (See picture some posts above.)
Vertex count: 82 (DWord) at 0x3F.
Add 82x12 (dec.) to 0x43 -> 0x41B, 82 dec., DWord uvs' count, same as vertex count.
uvs to follow (0x41F)
## Post #10
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-10T15:56:40+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

Tysm shakotay

I really appreciate it.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-03-10T16:01:22+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

First LOD:



atl_hip.png (74.04 KiB) Viewed 159 times
## Post #12
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-10T17:15:54+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

And a thank you to you too bigchillghost.

I should hopefully be able to get better results with your and shak's information.
## Post #13
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-10T22:25:55+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

With some messing around in AMR, I was able to extract another piece of the mech.

Needs work, yes, but I'm getting there.
## Post #14
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-11T00:59:00+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

Good news everyone!

Using info gathered from atl_hip, I've managed to rip another ERF, atl_ldleg.



Here are the AMR settings I used (Yes, they are a bit hacky, but they get the job done.)
## Post #15
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-11T02:23:06+00:00
- Post Title: Help needed with Hex2Obj/MechWarrior 4

So, I've had a good amount of success with AMR and the ERFs, but I'm having some trouble.

While I'm able to correctly identify the location of the indices and UVs, I can't seem to find the normals for the other 2 files.

Would you guys mind taking a look at atl_ldleg and atl_lfoot and comparing their normal locations to atl_hip's?
Just so I can find a pattern with them to find the normals for other files.
[normalsexamples.zip](https://xentaxbackup.github.io/file/19695_normalsexamples.zip)
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-03-11T04:13:12+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

The normals have a vertex count field (as a 4-byte integer) before the buffer, same as positions and uvs. So just search the count in the file and you should be able to locate to it.
## Post #17
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-11T12:51:26+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

I've managed to find the normals for atl_ldleg at 171B.
Should also be able to find the normals for the foot too.

Something I've noticed, however, is that the positions seem to be the same for the hip and femur parts of the mech.

This may also apply for the other files.
## Post #18
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-11T18:37:32+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

I examined the format, here is my understanding of the file spec:

```
    float            x;
    float            y;
    float            z;
    };
    
struct tvertex_entry {
    float            u;
    float            v;
    };
    
struct unk107_entry {
    float            x;
    float            y;
    float            z;
    float            w;
    };
    
struct vnorm_entry {
    float            x;
    float            y;
    float            z;
    };
 
struct mesh_entry {
    uint32_t        unk105;
    uint32_t        vert_count;
    vertex_entry*   vertices;      // read per 'vert_count'
    uint32_t        tvert_count;
    tvertex_entry*  tvertices;     // read per 'tvert_count'
    uint8_t         unk106[25];
    uint32_t        unk107_count;
    uint8_t*         unk107    // read per 'unk107_count'
    uint8_t         unk108[5];
    uint32_t        face_count;
    uint8_t*        faces;         // read per 'face_count'
    uint32_t        unk109_count;
    unk107_entry*   unk109;        // read per 'unk109_count'
    uint32_t        unk110_count;
    uint32_t        norm_count;
    vnorm_entry*    normals;       // read per 'norm_count'
    uint32_t        unk111
};
 
struct lod_entry {
    uint32_t        unk101;
    uint32_t        block_size;
    uint32_t        unk103;
    uint32_t        sub_mesh_count;
    mesh_entry*  meshes;      // read per 'sub_mesh_count'
    };
    
struct erf_file {
    uint32_t        filedid;
    uint32_t        unk001;
    uint32_t        unk002;
    uint32_t        unk003;
    float           unk004[4];
    uint16_t        lod_count;
    uint32_t        unk005;
    uint32_t        unk006;
    uint32_t        unk007;
    lod_entry*     lods;        // read per 'lod_count'
    };

```

[](https://ibb.co/BryK53w)

Below is a python script that will work in the latest version of blender (currently 2.92.0)

usage: start blender, goto the script tab then press NEW in the text editor and paste the below script into the editor. To execute the script press ALT+P or press the [>] play button, a file selection box will appear which will allow you to select erf files to import. Once the script has executed once it can then be accessed through the File > Import Dialog

```

    Python Code:    [PC] MechWarrior 4: Vengeance (for Blender 2.92.0)
    Author:         mariokart64n
    Date:           March 11, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-01-31
        Script Wrote

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
    if msh.validate():
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

    for i in range(0, len(materialIDs)):
        obj.data.polygons[i].material_index = materialIDs[i]

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
    def read_mesh (self, f= fopen()):
        
        
        self.unk101 = readLong(f)
        self.block_size = readLong(f) + ftell(f) + 4
        self.unk103 = readLong(f)
        self.unk104 = readByte(f)
        
        self.face_count1 = readLong(f)
        self.vert_count = readLong(f)
        
        
        if self.vert_count > 0:
            self.vert_array = [[float] * 3] * self.vert_count
            for i in range(0, self.vert_count):
                self.vert_array[i] = [
                    readFloat(f),
                    readFloat(f),
                    readFloat(f)
                    ]
        
        self.tvert_count = readLong(f)
        if self.tvert_count > 0:
            self.tvert_array = [[float] * 2] * self.tvert_count
            for i in range(0, self.tvert_count):
                self.tvert_array[i] = [
                    readFloat(f),
                    readFloat(f)
                    ]
        
        fseek(f, 40, seek_cur) # wtf is this
        
        
        self.face_count2 = readLong(f)
        
        if self.face_count2 > 0:
            self.face_array = [[int] * 3] * int(self.face_count2 / 3)
            for i in range(0, int(self.face_count2 / 3)):
                self.face_array[i] = [
                    readByte(f, unsigned),
                    readByte(f, unsigned),
                    readByte(f, unsigned)
                    ]
        
        self.norm_count = readLong(f)
        if self.norm_count > 0:
            self.norm_array = [[float] * 4] * self.norm_count
            for i in range(0, self.norm_count):
                self.norm_array[i] = [
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
            self.unk105_array = [[float] * 3] * self.unk105_count
            for i in range(0, self.unk105_count):
                self.unk105_array[i] = [
                    readFloat(f),
                    readFloat(f),
                    readFloat(f)
                    ]
        
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
        
        if self.filedid != 0x45524623:
            print ("Unsupported File Type")
            return False # (ERF#)
        
        self.unk001 = readLong(f)
        self.unk002 = readLong(f)
        self.unk003 = readLong(f)
        self.unk004 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.mesh_count = readShort(f)
        self.unk005 = readLong(f)
        self.unk006 = readLong(f)
        self.unk007 = readLong(f)
        
        if self.mesh_count > 0:
            self.meshes = [erf_mesh] * self.mesh_count
            for i in range(0, self.mesh_count):
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

def read (file):
    if not doesFileExist(file): return False
    
    #deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    
    f = fopen(file, 'rb')
    
    erf = erf_file()
    erf.read_erf(f)
    
    
    d = dummy(position=(erf.unk004[0],erf.unk004[1], erf.unk004[2]))
    d.object.empty_display_size = erf.unk004[3]
    d.object.empty_display_type = 'SPHERE'
    
    for i in range(0, erf.mesh_count):
        msh = mesh(
            obj_name=getFilenameFile(file),
            vertices=erf.meshes[i].vert_array,
            faces=erf.meshes[i].face_array,
            tverts=[erf.meshes[i].tvert_array],
            normals=erf.meshes[i].unk105_array
            )
        msh.location = (-erf.unk004[0], -erf.unk004[1], -erf.unk004[2])
        msh.parent = d.object
        break
    
    
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
def mechwarrioriv_imp_callback(fpath="", files=[], clearScene=True):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name)
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
        my_bool2: bpy.props.BoolProperty(name="Skeleton", default=False, description="Imports Bones to an Armature")
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
            bpy.types.Scene.mechwarrioriv_imp_my_float1 = self.my_float1
            bpy.types.Scene.mechwarrioriv_imp_my_bool1 = self.my_bool1
            bpy.types.Scene.mechwarrioriv_imp_my_bool2 = self.my_bool2
            bpy.types.Scene.mechwarrioriv_imp_my_bool3 = self.my_bool3
            bpy.types.Scene.mechwarrioriv_imp_my_bool4 = self.my_bool4
            bpy.types.Scene.mechwarrioriv_imp_my_bool5 = self.my_bool5
            bpy.types.Scene.mechwarrioriv_imp_my_bool6 = self.my_bool6
            bpy.types.Scene.mechwarrioriv_imp_my_bool7 = self.my_bool7
            bpy.types.Scene.mechwarrioriv_imp_my_string1 = self.my_string1

            # Run Callback
            mechwarrioriv_imp_callback(
                self.directory + "\\",
                self.files,
                self.my_bool1
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
            col.label(text="March 11, 2021")

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

    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    read(
        ""
        )
    messageBox("Done!")
else:
    mechwarrioriv_imp(True)


```


The process was recorded and are made available through youtube:

Format Analysis: [https://youtu.be/2f3kJWki5yw](https://youtu.be/2f3kJWki5yw)
Blender Coding: [https://youtu.be/V0JrVue5erE](https://youtu.be/V0JrVue5erE)
## Post #19
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-11T19:55:48+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

I genuinely can't thank you enough for doing this.

I'll test it on some erf files, and then I'll post my results on here.

Really though, TYSM.
## Post #20
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-11T20:49:03+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

After some testing, the script definitely works as intended, but there are some exceptions.

With some files the mechs seem to be either missing vertices or cause blender to freeze.

Here's some files from 3 mechs that seem to have this kind of problem, if you need more samples, let me know.
[erfexamples.zip](https://xentaxbackup.github.io/file/19705_erfexamples.zip)
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-11T23:23:48+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

after you paste the script in blender's text editor, navigate to line #432 of the python script

and replace the line 

```
fseek(f, 40, seek_cur) # wtf is this
```


with this

```
fseek(f, readLong(f) + 5, seek_cur)
```
## Post #22
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T03:19:57+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

I think I've figured out why the script imports certain files with missing pieces.

Its because some ERFs have multiple submeshes, and because the script doesn't support these submeshes, it doesn't import the files correctly.
Keep in mind that there are also LODs for the models, and if you need it, I can send you a tool I've been using to analyze the ERFs.

I've attached some examples of these ERFs for you to look at.
[submeshexamples.zip](https://xentaxbackup.github.io/file/19706_submeshexamples.zip)
## Post #23
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-12T13:46:49+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

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
    if msh.validate():
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

    for i in range(0, len(materialIDs)):
        obj.data.polygons[i].material_index = materialIDs[i]

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
    def read_mesh (self, f= fopen()):
        self.vert_array = []
        self.tvert_array = []
        self.face_array = []
        self.norm_array = []
        self.vcol_array = []
        self.unk105_array = []

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
            fseek(f, readLong(f) + 5, seek_cur)
            
            self.face_count2 = readLong(f)
            if self.face_count2 > 0:
                self.face_array.extend([[[int] for x in range(3)] for y in range(int(self.face_count2 / 3))])
                for i in range(0, int(self.face_count2 / 3)):
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
        
        if self.filedid != 0x45524623:
            print ("Unsupported File Type")
            return False # (ERF#)
        
        self.unk001 = readLong(f)
        self.unk002 = readLong(f)
        self.unk003 = readLong(f)
        self.unk004 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.mesh_count = readShort(f)
        self.unk005 = readLong(f)
        self.unk006 = readLong(f)
        self.unk007 = readLong(f)
        
        if self.mesh_count > 0:
            self.meshes = [erf_mesh] * self.mesh_count
            for i in range(0, self.mesh_count):
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
    
    for i in range(0, erf.mesh_count):
        msh = mesh(
            obj_name=getFilenameFile(file),
            vertices=erf.meshes[i].vert_array,
            faces=erf.meshes[i].face_array,
            tverts=[erf.meshes[i].tvert_array],
            normals=erf.meshes[i].unk105_array,
            flipAxis=True
            )
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
            col.label(text="March 11, 2021")

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
## Post #24
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T14:12:07+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Script works like a charm, no more holes in the meshes.

Great work, can't say enough that you've been a great help.
## Post #25
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T15:16:59+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

So, I have two last requests for MechWarrior 4 related stuff. I don't wanna ask for too much, but I would like to ask just these 2 things.


For mariokart64n:

Could you try to add support for the cockpit files? It's the last thing I'm asking for, and after that, the script should be completely finished.

The attachment below has some examples of the cockpit files.


For anyone with decryption knowledge:

Could someone here try to decrypt the encrypted MekPak files?

I would like to know if it would be possible to decrypt said files, since it would be nice to also have access to those mechs.

The attachment below also has the encrypted files.


Both things are put into 2 separate folders in the .zip, so just select the specific ones and you'll be good.
[finalerfexamples.zip](https://xentaxbackup.github.io/file/19708_finalerfexamples.zip)
## Post #26
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-12T17:12:00+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

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

    for i in range(0, len(materialIDs)):
        obj.data.polygons[i].material_index = materialIDs[i]

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
## Post #27
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T17:14:52+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

As always, big thanks for the help mariokart.

I really have to say that you've helped a lot with this file format, and while I can't really give anything in return, I can at least give thanks.
## Post #28
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T17:31:24+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

There seems to be a problem with the new script

It isn't able to import any of the normal mech files (bodyparts and whatnot), only their cockpits.
## Post #29
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-12T17:55:48+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

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
## Post #30
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T18:02:07+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Alright, works for both the normal parts and cockpits now.


Though I do want to ask, can anyone here take a look at the encrypted files and see if you can decrypt them?

It's the last thing that I wanted to ask for.
## Post #31
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-12T21:41:25+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Just wanna bump this with some info.

Here's the file I attached earlier with ONLY the encrypted ERFs.

If anyone wants to take a crack at decryption, just download the file.

According to a post on the forums that I found, a potential key for decryption could be this:

NV12NV24YV12UYVYYUY2AI44AI88AYUVAIP8AV12PLFFNVMDNVDPNVDBSSAAATOC

No guarantee it will work, but just something to try out.
[encryptedERFs.zip](https://xentaxbackup.github.io/file/19713_encryptedERFs.zip)
## Post #32
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-13T04:34:01+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

I've got some new information.


I managed to find unencrypted versions of certain mechs, which I believe will provide potential reference for decryption.

Make sure to match up the right encrypted and decrypted files though, they have the same names so that should be easy.
[unencryptedERFs.zip](https://xentaxbackup.github.io/file/19717_unencryptedERFs.zip)
## Post #33
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-03-13T10:03:28+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

> Reply from OPR23b ↑Sat Mar 13, 2021 12:34 pm at Sat Mar 13, 2021 12:34 pm
>
> 
I believe will provide potential reference for decryption.
Yeah, for sure.  
The data is definitely compressed. Calculate the CRC32 of the corresponding "unencryptedERF" file and you'll find the result as a little-endian integer at offset 0xE in the "EncryptedERF" file.
So the layout of the "EncryptedERF" is revealed as:

```
long	ZipDataSize // aligned to 8 bytes
long	ZipStreamLength // actual zip data size?
long	CRC32 // of decompressed data
byte	ZipData[ZipDataSize]

```

The first 8 bytes of the ZipData is a fixed sequence, as 76 5C 73 F4 9E BD E9 5B for signature "mektek" and DA 06 93 6C A3 2C 66 D0 for signature "secure". Given the fact that all normal erf files start with the sequence 23 46 52 45 0E 00 00 00, it's possible that there's a layer of encryption on the compressed data. You should try the comtype scanner tool from aluigi to exclude the possibility that the data is merely compressed.
## Post #34
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-13T15:26:18+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

After going through the outputted files from the comtype program, none of them seem to have worked, so it's definitely encrypted data.
## Post #35
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-14T17:27:09+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

I figure that I might as well share the results I got from the comtype scanner.

I've attached the files with the closest file size, so that you can take a look and see if there is anything of note.

There may be some junk files (files with no significant data), but if you come across those, just ignore/delete them.


[https://www.mediafire.com/file/cj7wc42t ... s.zip/file](https://www.mediafire.com/file/cj7wc42tzanfvhr/results.zip/file)
## Post #36
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-27T16:27:40+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Bumping this.


I just want to ask, how should decryption of the mektek files be done?

The data is definitely encrypted, since none of the methods from the comtype scanner worked.
## Post #37
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-04-12T15:17:52+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

> Reply from OPR23b ↑Sun Mar 28, 2021 12:27 am at Sun Mar 28, 2021 12:27 am
>
> 
Bumping this.


I just want to ask, how should decryption of the mektek files be done?

The data is definitely encrypted, since none of the methods from the comtype scanner worked.

you could try creating a batch script for an executable that changes the HEX data for the Encrypted files to the un-encrypted HEX sequence
## Post #38
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-04-18T15:12:52+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

So, in regards of the Mektek encryption, I think I'm just gonna have to ask anyone with good decryption knowledge on here if they can take a look at the encryption.
I have very little experience with encryption/decryption, so I can't really do anything about it.

If anyone thinks they could try to solve it, here's a full mech, with encrypted and unencrypted .erfs.

Sorry if it feels like I'm just giving up, but I just don't know what to do.

[https://www.mediafire.com/file/c0dt8qwr ... r.zip/file](https://www.mediafire.com/file/c0dt8qwrmr8v7u1/Annihilator.zip/file)
## Post #39
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-01T19:43:59+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Bumping this, since it's been a while.


If anyone here needs more files to go about finding a decryption method, I should have all of the mechs from the Mektek release that have non-encrypted version, so I can upload those ones as well.

I really just need someone with proper decryption knowledge to take a look at these files, and come up with some way to decrypt them.
## Post #40
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-06-07T15:03:09+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

So me and my friend were talking about the MekTek encryption and e brought up that if the files are encrypted, they must have a key to unlock them.
leading me to a theory that they might be a key that can unencrypt the files within MW4: Mercs (with MekTek).

I also had an idea of my own, some MekTek models have encrypted and undecrypted parts to them (EX - Clan Infantry:  cin_torso is not encrypted, cin_rgun is encrypted) if both of the .ERFs from the same model can be compared side by side in a hex editor it could probably help show a result on how to unencrypt the models.
## Post #41
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-06-07T16:19:51+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Maybe you could try the possible key that I attached above?, It should be at the top of this page.


Only thing is, that you would need to find a way to use that key to decrypt the files.

And there's no guarantee that key will work, so if it doesn't, I would suggest surfing through the game files to see if anything can be found.
## Post #42
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-06-30T21:22:38+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Yeah I don't think I can really do anything with the key. We would need someone with decryption knowledge to make a program to unencrypt (or decompress) the MekTek ERF's otherwise they will just remain out of reach. If you know anyone with that kind of knowledge you should ask them if they would be willing to help.
## Post #43
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-06-30T23:46:18+00:00
- Post Title: Re: Help needed with Hex2Obj/MechWarrior 4

Asking on the forum would probably be the best bet.

I'm sure there are quite a few people on here with decryption skill.
