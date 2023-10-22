## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T20:36:24+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

After succesfully extracting the archives from Offroad Legends ([https://zenhax.com/viewtopic.php?p=62852#p62852](https://zenhax.com/viewtopic.php?p=62852#p62852)), I need to get the 3D models. The 3D models are in .geo format and they have the MAGIC of "H3DG". Can anybody help me? There's also a "H3D" format in the car's folder but that seems to be an XML for the car's properties. Also, if you're gonna make any importers for programs, keep in mind I use Blender.
Sample (GEO): [https://www.mediafire.com/file/hh7ej3up ... s.geo/file](https://www.mediafire.com/file/hh7ej3ups6f7gu0/carry_chassis.geo/file)
Sample (H3D) if it is required: [https://www.mediafire.com/file/ncd0hntk ... s.h3d/file](https://www.mediafire.com/file/ncd0hntkokut9dl/carry_chassis.h3d/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-15T21:28:56+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

carry_chassis-geo.png (69.11 KiB) Viewed 191 times
## Post #3
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T21:31:10+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

nice. also how did you find the data?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-15T21:52:49+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

I followed the tutorial.   (see 'tut' button in hex2obj)
## Post #5
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T21:55:27+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 5:52 am at Tue Mar 16, 2021 5:52 am
>
> 
I followed the tutorial.   (see 'tut' button in hex2obj)

Thx, would be cool to get the positions of the parts.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-15T21:59:22+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

Speaking of which parts? Wheels for example? May be they're in a different file?

Well, I see. You mean the doors, that's a little big tricky, I guess (.h3d file might contain the infos).
## Post #7
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T22:06:00+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 5:59 am at Tue Mar 16, 2021 5:59 am
>
> 
Speaking of which parts? Wheels for example? May be they're in a different file?

Well, I see. You mean the doors, that's a little big tricky, I guess (.h3d file might contain the infos).

Oof. How do I make it so the model exported is not flat? I found out the exported mesh is not smooth.
## Post #8
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T22:06:57+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

Also the pieces are conjoined with the mesh.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-15T22:10:34+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

<please avoid double postings! You can edit your posts>

"not flat"?
(I've corrected the vertex start in my first post to 5C, btw.)

For the parts: devide the model up like so (right door, vertRStart="3618" vertREnd="3625"):

```
		<Mesh name="#fallpart_rdoor" material="$path$/carry_chassis#carry_window" batchStart="10818" batchCount="18" vertRStart="3618" vertREnd="3625" />
	</Mesh>
```
Use tx,ty,tz as an offset. (Didn't check this.)

edit:
change the obj file like so:
...
f 3612 3616 3614 
f 3616 3613 3617 
g SM_7b
f 3615 3614 3618 
f 3618 3617 3615 
f 3614 3616 3618 
f 3617 3618 3616 
f 3619 3620 3621 
f 3621 3622 3619 
f 3623 3622 3621 
f 3624 3623 3621 
f 3624 3621 3625 
f 3621 3626 3625 
g SM_7c
f 3627 3628 3629 
f 3629 3630 3627 
.



parts.png (55.88 KiB) Viewed 179 times


As you can see it's a little bit tricky. I got one face to much.
## Post #10
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T22:17:14+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 6:10 am at Tue Mar 16, 2021 6:10 am
>
> 
<please avoid double postings! You can edit your posts>

"not flat"?
(I've corrected the vertex start in my first post to 5C, btw.)

For the parts: devide the model up like so (right door, vertRStart="3618" vertREnd="3625"):
Code: Select all<Mesh name="fallpart_rdoor" material="$path$/carry_chassis#carry_chassis" tx="-0.750686" ty="0.492256" tz="0.279097" batchStart="10239" batchCount="579" vertRStart="3415" vertREnd="3617">
		<Mesh name="#fallpart_rdoor" material="$path$/carry_chassis#carry_window" batchStart="10818" batchCount="18" vertRStart="3618" vertREnd="3625" />
	</Mesh>Use tx,ty,tz as an offset. (Didn't check this.)

The 3D model in the preview is fine, but when I exported the 3D model as obj, it is flat.
Also this might be a dumb question but how do I find a 5 digit address?
how do I make it so it doesn't split the mesh up into "submesh"?
Well thanks for all the info, wish there was a proper importer for this stuff.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-15T22:42:35+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Tue Mar 16, 2021 6:17 am at Tue Mar 16, 2021 6:17 am
>
> 
Also this might be a dumb question but how do I find a 5 digit address?which address are you talking of?

> how do I make it so it doesn't split the mesh up into "submesh"?delete g submesh_x lines in obj file 

> Well thanks for all the info, wish there was a proper importer for this stuff.Proper importers take time to write.
(Best thing would be you'd learn how to create a Noesis script, for example.)

Placing a part:
-----------------
Right door, median in blender:
0.03291 0.12206 0.04862

add (from .h3d): tx="-0.750686" ty="0.492256" tz="0.279097" 

result, correct "absolut" position:
-0,717776  0,614316 0,327717

(manually dragged,for comparison only)
-0.71511 0.63207 0.32835
.



rightDoor_position.png (104.4 KiB) Viewed 175 times


(again an extra face, sorry  )
## Post #12
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-15T22:55:09+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 6:42 am at Tue Mar 16, 2021 6:42 am
>
> 
ReVolt wrote: ↑Tue Mar 16, 2021 6:17 am
Also this might be a dumb question but how do I find a 5 digit address?which address are you talking of?
how do I make it so it doesn't split the mesh up into "submesh"?delete g submesh_x lines in obj file 
Well thanks for all the info, wish there was a proper importer for this stuff.Proper importers take time to write.
(Best thing would be you'd learn how to create a Noesis script, for example.)

Placing a part:
-----------------
Right door, median in blender:
0.03291 0.12206 0.04862

add (from .h3d): tx="-0.750686" ty="0.492256" tz="0.279097" 

result, correct "absolut" position:
-0,717776  0,614316 0,327717

(manually dragged,for comparison only)
-0.71511 0.63207 0.32835
.
rightDoor_position.png
(again an extra face, sorry  )

The extra faces could be easily fixed by just seperating them and joining them to the corresponding part.
But I'm confused. What would I add to the H3D position? (Ohh, I  get it, you're adding to the median. Where would I find the median? Keep in mind I'm using the latest version of blender.)
For the five-digit address, I mean a hex address, like this: 24366
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-15T23:08:26+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Tue Mar 16, 2021 6:55 am at Tue Mar 16, 2021 6:55 am
>
> Where would I find the median? Keep in mind I'm using the latest version of blender.I don't use the latest version. Try edit mode, then press 'N'

> For the five-digit address, I mean a hex address, like this: 24366You load the .geo into a hex editor and choose the (offset) addresses to be shown as hex.
Most hex editors have a "goto" feature where you enter said address. Or simply scroll down in the view of data.

Or, if you meant, "how to find start address of face indices", it's DWords here, so search for 000000000100000002000000

Good night.
## Post #14
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T00:08:44+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 5:52 am at Tue Mar 16, 2021 5:52 am
>
> 
I followed the tutorial.   (see 'tut' button in hex2obj)

Got the maz truck 3d model converted. Now here's the hard part: UVs? How do I get them? the tut doesn't seem that all too helpful on that topic.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-16T07:47:25+00:00
- Post Title: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Tue Mar 16, 2021 8:08 am at Tue Mar 16, 2021 8:08 am
>
> Got the maz truck 3d model converted.Great! 

> Now here's the hard part: UVs? How do I get them? the tut doesn't seem that all too helpful on that topic.There's hundreds of possibilities how 3D data can be organized. You wouldn't expect me to decsribe them all, would you?  
The magic word is "experience" - you just need to extract at least a dozen of different 3D formats to learn more.

I usually spend 15 min on new formats - these are eaten up three times here.

Search for uvs in the block from 0xCCB0 to 0x1BB22, normals to be found here, too, I guess.

btw: reh already gave you an uv address in your other thread
## Post #16
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T12:51:29+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 3:47 pm at Tue Mar 16, 2021 3:47 pm
>
> 
ReVolt wrote: ↑Tue Mar 16, 2021 8:08 am
btw: reh already gave you an uv address in your other thread


Cool. How do I make it so the UVs are baked into the model? The uvs export as a single mesh, which I don't want.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-16T12:57:51+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

File/SaveAs mesh
## Post #18
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T14:57:58+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Tue Mar 16, 2021 8:57 pm at Tue Mar 16, 2021 8:57 pm
>
> 
File/SaveAs mesh

Thanks! Also managed to get the UVs! The way to tell where the UVs are is a pattern, there's a 3(letter) byte at the end of each 4-byte sequence.
## Post #19
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-16T15:16:37+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

[](https://ibb.co/Dp7G7Zg)

> Below is a python script I wrote for blender that was tested in the latest version (currently 2.92.0)
>
> 
>
> usage: start blender, goto the script tab then press NEW in the text editor and paste the below script into the editor. To execute the script press ALT+P or press the [>] play button, a file selection box will appear which will allow you to select GEO files to import. Once the script has executed once it can then be accessed through the File > Import Dialog until blender is restarted

```

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 16, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote


    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True


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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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


def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")
        if mesh_validate(vertArray, faces):
            # Erase Mesh
            msh.user_clear()
            bpy.data.meshes.remove(msh)
            print("Mesh Deleted!")
            return None
        

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

    if len(materialIDs) == len(faces):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i]
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0
    unk02 = 0
    matrix = ((1.0, 0.0, 0.0, 0.0), (0.0, 1.0, 0.0, 0.0), (0.0, 0.0, 1.0, 0.0), (0.0, 0.0, 0.0, 1.0))
    unk03 = 0
    vertex_count = 0
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        self.unk02 = readLong(f)
        self.matrix = (
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
        )
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)

        # Read Vertices
        self.vertices.index = readLong(f)
        self.vertices.stride = readLong(f)

        if self.vertices.stride != 0x0C:
            print("Error:\tInvalid Vertex Stride")
            return False
        comp = int(self.vertices.stride / 4)
        self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.vertices.data[x][y] = readFloat(f)

        # Read Normals
        self.normals.index = readLong(f)
        self.normals.stride = readLong(f)
        if self.normals.stride != 0x06:
            print("Error:\tInvalid Normal Stride:\t%i" % self.normals.stride)
            return False

        comp = int(self.normals.stride / 2)
        self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.normals.data[x][y] = float(readShort(f) / 32767.0)

        # Read UV-0
        self.texcoord0.index = readLong(f)
        self.texcoord0.stride = readLong(f)
        if self.texcoord0.stride != 0x08:
            print("Error:\tInvalid UV0 Stride")
            return False

        comp = int(self.texcoord0.stride / 4)
        self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord0.data[x][y] = readFloat(f)

        # Read UV-1
        self.texcoord1.index = readLong(f)
        self.texcoord1.stride = readLong(f)
        if self.texcoord1.stride != 0x08:
            print("Error:\tInvalid UV1 Stride")
            return False

        comp = int(self.texcoord1.stride / 4)
        self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord1.data[x][y] = readFloat(f)

        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        for x in range(0, self.face_count):
            self.faces[x] = readLong(f)

        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    try:
        h3d = minidom.parse(h3d_file)

        h3d_mat = []
        h3d_mat_index = 0
        h3d_sp = h3d_sampler()
        h3d_un = h3d_uniform()

        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        return False

    mats = []
    for m in h3d_mat:
        mat = StandardMaterial(m.name)
        for t in m.sampler:
            if t.name == 'albedoMap':
                if '/' in t.map:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                else:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
        mats.append(mat.data)

    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    for gmesh in h3d.getElementsByTagName('Mesh'):
        try:
            msh_name = gmesh.attributes['name'].value
        except:
            pass
        try:
            msh_matn = gmesh.attributes['material'].value
        except:
            pass
        try:
            msh_tx = float(gmesh.attributes['tx'].value)
        except:
            pass
        try:
            msh_ty = float(gmesh.attributes['ty'].value)
        except:
            pass
        try:
            msh_tz = float(gmesh.attributes['tz'].value)
        except:
            pass
        try:
            msh_batchStart = int(gmesh.attributes['batchStart'].value)
        except:
            pass
        try:
            msh_batchCount = int(gmesh.attributes['batchCount'].value)
        except:
            pass
        try:
            msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
        except:
            pass
        try:
            msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
        except:
            pass

        mat_index = 0
        if '#' in msh_matn:
            mat_name = msh_matn.split('#')[-1:][0]
            for i in range(0, len(h3d_mat)):
                if h3d_mat[i].name == mat_name:
                    mat_index = i
                    break

        matidArray = [mat_index for i in range(int(msh_batchCount / 3))]

        msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
        vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])

        for i in range(0, msh_vertRCount):
            vertArray[i] = geo.vertices.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            normArray[i] = geo.normals.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]

        faceArray = []
        read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)

        msh = mesh(
            vertices=vertArray,
            tverts=[uvw0Array, uvw1Array],
            normals=normArray,
            faces=faceArray,
            obj_name=msh_name,
            flipAxis=True,
            mscale=mscale,
            materials=mats,
            materialIDs=matidArray,
            position=(msh_tx, -msh_tz, msh_ty)
        )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\carry_chassis.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)


```
## Post #20
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T15:48:07+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from mariokart64n ↑Tue Mar 16, 2021 11:16 pm at Tue Mar 16, 2021 11:16 pm
>
> 

Below is a python script I wrote for blender that was tested in the latest version (currently 2.92.0)

usage: start blender, goto the script tab then press NEW in the text editor and paste the below script into the editor. To execute the script press ALT+P or press the [>] play button, a file selection box will appear which will allow you to select GEO files to import. Once the script has executed once it can then be accessed through the File > Import Dialog until blender is restarted
Code: Select all""" ======================================================================

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 16, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote


    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True


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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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


def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")
        if mesh_validate(vertArray, faces):
            # Erase Mesh
            msh.user_clear()
            bpy.data.meshes.remove(msh)
            print("Mesh Deleted!")
            return None
        

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

    if len(materialIDs) == len(faces):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i]
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0
    unk02 = 0
    matrix = ((1.0, 0.0, 0.0, 0.0), (0.0, 1.0, 0.0, 0.0), (0.0, 0.0, 1.0, 0.0), (0.0, 0.0, 0.0, 1.0))
    unk03 = 0
    vertex_count = 0
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        self.unk02 = readLong(f)
        self.matrix = (
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
        )
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)

        # Read Vertices
        self.vertices.index = readLong(f)
        self.vertices.stride = readLong(f)

        if self.vertices.stride != 0x0C:
            print("Error:\tInvalid Vertex Stride")
            return False
        comp = int(self.vertices.stride / 4)
        self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.vertices.data[x][y] = readFloat(f)

        # Read Normals
        self.normals.index = readLong(f)
        self.normals.stride = readLong(f)
        if self.normals.stride != 0x06:
            print("Error:\tInvalid Normal Stride:\t%i" % self.normals.stride)
            return False

        comp = int(self.normals.stride / 2)
        self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.normals.data[x][y] = float(readShort(f) / 32767.0)

        # Read UV-0
        self.texcoord0.index = readLong(f)
        self.texcoord0.stride = readLong(f)
        if self.texcoord0.stride != 0x08:
            print("Error:\tInvalid UV0 Stride")
            return False

        comp = int(self.texcoord0.stride / 4)
        self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord0.data[x][y] = readFloat(f)

        # Read UV-1
        self.texcoord1.index = readLong(f)
        self.texcoord1.stride = readLong(f)
        if self.texcoord1.stride != 0x08:
            print("Error:\tInvalid UV1 Stride")
            return False

        comp = int(self.texcoord1.stride / 4)
        self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord1.data[x][y] = readFloat(f)

        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        for x in range(0, self.face_count):
            self.faces[x] = readLong(f)

        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    try:
        h3d = minidom.parse(h3d_file)

        h3d_mat = []
        h3d_mat_index = 0
        h3d_sp = h3d_sampler()
        h3d_un = h3d_uniform()

        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        return False

    mats = []
    for m in h3d_mat:
        mat = StandardMaterial(m.name)
        for t in m.sampler:
            if t.name == 'albedoMap':
                if '/' in t.map:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                else:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
        mats.append(mat.data)

    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    for gmesh in h3d.getElementsByTagName('Mesh'):
        try:
            msh_name = gmesh.attributes['name'].value
        except:
            pass
        try:
            msh_matn = gmesh.attributes['material'].value
        except:
            pass
        try:
            msh_tx = float(gmesh.attributes['tx'].value)
        except:
            pass
        try:
            msh_ty = float(gmesh.attributes['ty'].value)
        except:
            pass
        try:
            msh_tz = float(gmesh.attributes['tz'].value)
        except:
            pass
        try:
            msh_batchStart = int(gmesh.attributes['batchStart'].value)
        except:
            pass
        try:
            msh_batchCount = int(gmesh.attributes['batchCount'].value)
        except:
            pass
        try:
            msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
        except:
            pass
        try:
            msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
        except:
            pass

        mat_index = 0
        if '#' in msh_matn:
            mat_name = msh_matn.split('#')[-1:][0]
            for i in range(0, len(h3d_mat)):
                if h3d_mat[i].name == mat_name:
                    mat_index = i
                    break

        matidArray = [mat_index for i in range(int(msh_batchCount / 3))]

        msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
        vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])

        for i in range(0, msh_vertRCount):
            vertArray[i] = geo.vertices.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            normArray[i] = geo.normals.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]

        faceArray = []
        read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)

        msh = mesh(
            vertices=vertArray,
            tverts=[uvw0Array, uvw1Array],
            normals=normArray,
            faces=faceArray,
            obj_name=msh_name,
            flipAxis=True,
            mscale=mscale,
            materials=mats,
            materialIDs=matidArray,
            position=(msh_tx, -msh_tz, msh_ty)
        )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\carry_chassis.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)

WOW! AMAZING WORK! This work perfectly! Even with UVs and correct position!
Also, can you make it so the script can read the XML of the car? The XML of the cars has wheel positions. (carry.xml)
It's a shame it can't read the data from Off The Road, that has some exclusive cars. I'll see if it works with Offroad Legends 2 though.
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-16T15:56:30+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

I did not notice any carry.xml file so I can't help you
## Post #22
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T15:57:28+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from mariokart64n ↑Tue Mar 16, 2021 11:56 pm at Tue Mar 16, 2021 11:56 pm
>
> 
I did not notice any carry.xml file so I can't help you

Oops, I forgot to get the XML of carry.
Here

```
<VEHICLE>
  <CHASSIS>
    <SHAPE type="box" mass="600.0">
      <SIZE x="1.6" y="0.8" z="2.6"/>
      <POS x="0" y="0.25" z="0.9"/>
    </SHAPE>
    <SHAPE type="box" mass="25.0">
      <SIZE x="1.7" y="0.7" z="1.1"/>
      <POS x="0" y="0.85" z="0.20"/>
    </SHAPE>
    
    <SHAPE type="box" mass="25.0">
      <SIZE x="1.6" y="0.1" z="2.3"/>
      <POS x="0" y="0.15" z="-1.40"/>
    </SHAPE>
 

    <SHAPE type="box" mass="25.0">
      <SIZE x="0.15" y="1.1" z="2.3"/>
      <POS x="0.55" y="0.5" z="-1.40"/>
    </SHAPE>
    <SHAPE type="box" mass="25.0">
      <SIZE x="0.15" y="1.1" z="2.3"/>
      <POS x="-0.55" y="0.5" z="-1.40"/>
    </SHAPE>
    <SHAPE type="box" mass="25.0">
      <SIZE x="1.2" y="0.9" z="0.4"/>
      <POS x="0.0" y="0.40" z="-2.46"/>
    </SHAPE>
    
  </CHASSIS>
  <WHEELS>
    <WHEEL>
      <CONNECTIONPOINT x="-0.86" y="0.65" z="1.6"/>
      <SUSPENSION_RESTLENGTH value="1.1"/>
      <SUSPENSIONTRAVEL value="0.1"/>
      <STIFFNESS value="20.0"/>
      <DAMPINGCOMPRESSION value ="2.0"/>
      <DAMPINGRELAXATION value ="1.8"/>
      <STEERED value="1"/>
      <DRIVERATIO value="0.4"/>
      <RADIUS value="0.38"/>
    </WHEEL>
    <WHEEL>
      <CONNECTIONPOINT x="0.86" y="0.65" z="1.6"/>
      <SUSPENSION_RESTLENGTH value="1.1"/>
      <SUSPENSIONTRAVEL value="0.1"/>
      <STIFFNESS value="20.0"/>
      <DAMPINGCOMPRESSION value ="2.0"/>
      <DAMPINGRELAXATION value ="1.8"/>
      <STEERED value="1"/>
      <DRIVERATIO value="0.4"/>
      <RADIUS value="0.38"/>
    </WHEEL>
    <WHEEL>
      <CONNECTIONPOINT x="-0.86" y="0.65" z="-1.495"/>
      <SUSPENSION_RESTLENGTH value="1.1"/>
      <SUSPENSIONTRAVEL value="0.1"/>
      <STIFFNESS value="20.0"/>
      <DAMPINGCOMPRESSION value ="2.0"/>
      <DAMPINGRELAXATION value ="1.5"/>
      <STEERED value="0"/>
      <DRIVERATIO value="0.1"/>
      <RADIUS value="0.38"/>
    </WHEEL>
    <WHEEL>
      <CONNECTIONPOINT x="0.85" y="0.65" z="-1.495"/>
      <SUSPENSION_RESTLENGTH value="1.1"/>
      <SUSPENSIONTRAVEL value="0.1"/>
      <STIFFNESS value="20.0"/>
      <DAMPINGCOMPRESSION value ="2.0"/>
      <DAMPINGRELAXATION value ="1.5"/>
      <STEERED value="0"/>
      <DRIVERATIO value="0.1"/>
      <RADIUS value="0.38"/>
    </WHEEL>
  </WHEELS>
  <FRICTION side="1.0" forward="1.25" air="16.0" rolling="0.005"/>
  <ENGINE idleRpm="650.0" maxRpm="6500.0" friction="1.0" mass="0.57">
    <TORQUETABLE>
      <ELEM rpm="0.0" torque="0.0"/>
      <ELEM rpm="1000.0" torque="395.0"/>
      <ELEM rpm="2000.0" torque="375.0"/>
      <ELEM rpm="3000.0" torque="420.0"/>
      <ELEM rpm="4000.0" torque="445.0"/>
      <ELEM rpm="5000.0" torque="380.0"/>
      <ELEM rpm="6000.0" torque="345.0"/>
      <ELEM rpm="7000.0" torque="323.0"/>
      <ELEM rpm="8000.0" torque="280.0"/>
    </TORQUETABLE>
    <GEARBOX numGears="5" effectiveness="0.85" diffratio="4.2">
      <RATIO value="0.0"/>
      <RATIO value="2.73"/>
      <RATIO value="1.92"/>
      <RATIO value="1.38"/>
      <RATIO value="0.99"/>
      <RATIO value="0.79"/>
    </GEARBOX>
  </ENGINE>


</VEHICLE>
```
## Post #23
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T16:14:05+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Tue Mar 16, 2021 11:48 pm at Tue Mar 16, 2021 11:48 pm
>
> 
mariokart64n wrote: ↑Tue Mar 16, 2021 11:16 pm

Below is a python script I wrote for blender that was tested in the latest version (currently 2.92.0)

usage: start blender, goto the script tab then press NEW in the text editor and paste the below script into the editor. To execute the script press ALT+P or press the [>] play button, a file selection box will appear which will allow you to select GEO files to import. Once the script has executed once it can then be accessed through the File > Import Dialog until blender is restarted
Code: Select all""" ======================================================================

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 16, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote


    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True


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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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


def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")
        if mesh_validate(vertArray, faces):
            # Erase Mesh
            msh.user_clear()
            bpy.data.meshes.remove(msh)
            print("Mesh Deleted!")
            return None
        

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

    if len(materialIDs) == len(faces):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i]
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0
    unk02 = 0
    matrix = ((1.0, 0.0, 0.0, 0.0), (0.0, 1.0, 0.0, 0.0), (0.0, 0.0, 1.0, 0.0), (0.0, 0.0, 0.0, 1.0))
    unk03 = 0
    vertex_count = 0
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        self.unk02 = readLong(f)
        self.matrix = (
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
        )
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)

        # Read Vertices
        self.vertices.index = readLong(f)
        self.vertices.stride = readLong(f)

        if self.vertices.stride != 0x0C:
            print("Error:\tInvalid Vertex Stride")
            return False
        comp = int(self.vertices.stride / 4)
        self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.vertices.data[x][y] = readFloat(f)

        # Read Normals
        self.normals.index = readLong(f)
        self.normals.stride = readLong(f)
        if self.normals.stride != 0x06:
            print("Error:\tInvalid Normal Stride:\t%i" % self.normals.stride)
            return False

        comp = int(self.normals.stride / 2)
        self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.normals.data[x][y] = float(readShort(f) / 32767.0)

        # Read UV-0
        self.texcoord0.index = readLong(f)
        self.texcoord0.stride = readLong(f)
        if self.texcoord0.stride != 0x08:
            print("Error:\tInvalid UV0 Stride")
            return False

        comp = int(self.texcoord0.stride / 4)
        self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord0.data[x][y] = readFloat(f)

        # Read UV-1
        self.texcoord1.index = readLong(f)
        self.texcoord1.stride = readLong(f)
        if self.texcoord1.stride != 0x08:
            print("Error:\tInvalid UV1 Stride")
            return False

        comp = int(self.texcoord1.stride / 4)
        self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord1.data[x][y] = readFloat(f)

        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        for x in range(0, self.face_count):
            self.faces[x] = readLong(f)

        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    try:
        h3d = minidom.parse(h3d_file)

        h3d_mat = []
        h3d_mat_index = 0
        h3d_sp = h3d_sampler()
        h3d_un = h3d_uniform()

        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        return False

    mats = []
    for m in h3d_mat:
        mat = StandardMaterial(m.name)
        for t in m.sampler:
            if t.name == 'albedoMap':
                if '/' in t.map:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                else:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
        mats.append(mat.data)

    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    for gmesh in h3d.getElementsByTagName('Mesh'):
        try:
            msh_name = gmesh.attributes['name'].value
        except:
            pass
        try:
            msh_matn = gmesh.attributes['material'].value
        except:
            pass
        try:
            msh_tx = float(gmesh.attributes['tx'].value)
        except:
            pass
        try:
            msh_ty = float(gmesh.attributes['ty'].value)
        except:
            pass
        try:
            msh_tz = float(gmesh.attributes['tz'].value)
        except:
            pass
        try:
            msh_batchStart = int(gmesh.attributes['batchStart'].value)
        except:
            pass
        try:
            msh_batchCount = int(gmesh.attributes['batchCount'].value)
        except:
            pass
        try:
            msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
        except:
            pass
        try:
            msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
        except:
            pass

        mat_index = 0
        if '#' in msh_matn:
            mat_name = msh_matn.split('#')[-1:][0]
            for i in range(0, len(h3d_mat)):
                if h3d_mat[i].name == mat_name:
                    mat_index = i
                    break

        matidArray = [mat_index for i in range(int(msh_batchCount / 3))]

        msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
        vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])

        for i in range(0, msh_vertRCount):
            vertArray[i] = geo.vertices.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            normArray[i] = geo.normals.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]

        faceArray = []
        read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)

        msh = mesh(
            vertices=vertArray,
            tverts=[uvw0Array, uvw1Array],
            normals=normArray,
            faces=faceArray,
            obj_name=msh_name,
            flipAxis=True,
            mscale=mscale,
            materials=mats,
            materialIDs=matidArray,
            position=(msh_tx, -msh_tz, msh_ty)
        )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\carry_chassis.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)




WOW! AMAZING WORK! This work perfectly! Even with UVs and correct position!
Also, can you make it so the script can read the XML of the car? The XML of the cars has wheel positions. (carry.xml)
It's a shame it can't read the data from Off The Road, that has some exclusive cars. I'll see if it works with Offroad Legends 2 though.

Hmm, it's not working with Offroad Legends 2 models. Here's the new Carry from that game,
GEO: [https://www.mediafire.com/file/2vbpspby ... s.geo/file](https://www.mediafire.com/file/2vbpspbyvwgt80k/chassis.geo/file)
H3D: [https://www.mediafire.com/file/hca3t835 ... s.h3d/file](https://www.mediafire.com/file/hca3t835e72akcf/chassis.h3d/file)
## Post #24
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T17:15:29+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

Also here's a list of vehicles that don't load correctly (Offroad Legends 1)
FireStar - Won't even load at all, just says list index out of range.

Reaper (Xperia) - Pieces are out of place.

GoldStar - Only loads front bumper, same error as FireStar.

Hunter - Same error as FireStar.

Jeep - Just says "Done!" and nothing imports.

Karma - Pieces are out of place.

MAZ - Pieces are out of place.

Rainbow - Pieces are out of place.

Smokey - Pieces are out of place.

Too tired to upload all the cars as individual parts, here's a zip of all the broken vehicles.
[https://www.mediafire.com/file/0fsz9n9a ... s.zip/file](https://www.mediafire.com/file/0fsz9n9af4gjylq/OL_Brokencars.zip/file)
..Yeah, was excited about this tool, but now a bit disappointed. Oh well, will probably have to stick with the hex2obj method. Using Android files for these, too.
(Also sorry for double-posting again. I felt like this post was too large to fit into my previous post.)
## Post #25
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-16T18:13:27+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

traceback error was related to the materials, so i just deleted that section... seems to work on those files now..

```

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 16, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote


    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True


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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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


def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")
        if mesh_validate(vertArray, faces):
            # Erase Mesh
            msh.user_clear()
            bpy.data.meshes.remove(msh)
            print("Mesh Deleted!")
            return None
        

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
        if len(materialIDs) > 0:
            for i in range(0, len(materialIDs)):
                obj.data.polygons[i].material_index = materialIDs[i]
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0
    unk02 = 0
    matrix = ((1.0, 0.0, 0.0, 0.0), (0.0, 1.0, 0.0, 0.0), (0.0, 0.0, 1.0, 0.0), (0.0, 0.0, 0.0, 1.0))
    unk03 = 0
    vertex_count = 0
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        self.unk02 = readLong(f)
        self.matrix = (
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
        )
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)

        # Read Vertices
        self.vertices.index = readLong(f)
        self.vertices.stride = readLong(f)

        if self.vertices.stride != 0x0C:
            print("Error:\tInvalid Vertex Stride")
            return False
        comp = int(self.vertices.stride / 4)
        self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.vertices.data[x][y] = readFloat(f)

        # Read Normals
        self.normals.index = readLong(f)
        self.normals.stride = readLong(f)
        if self.normals.stride != 0x06:
            print("Error:\tInvalid Normal Stride:\t%i" % self.normals.stride)
            return False

        comp = int(self.normals.stride / 2)
        self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.normals.data[x][y] = float(readShort(f) / 32767.0)

        # Read UV-0
        self.texcoord0.index = readLong(f)
        self.texcoord0.stride = readLong(f)
        if self.texcoord0.stride != 0x08:
            print("Error:\tInvalid UV0 Stride")
            return False

        comp = int(self.texcoord0.stride / 4)
        self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord0.data[x][y] = readFloat(f)

        # Read UV-1
        self.texcoord1.index = readLong(f)
        self.texcoord1.stride = readLong(f)
        if self.texcoord1.stride != 0x08:
            print("Error:\tInvalid UV1 Stride")
            return False

        comp = int(self.texcoord1.stride / 4)
        self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord1.data[x][y] = readFloat(f)

        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        for x in range(0, self.face_count):
            self.faces[x] = readLong(f)

        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    try:
        h3d = minidom.parse(h3d_file)

        h3d_mat = []
        h3d_mat_index = 0
        h3d_sp = h3d_sampler()
        h3d_un = h3d_uniform()

        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        return False

    mats = []
    for m in h3d_mat:
        mat = StandardMaterial(m.name)
        for t in m.sampler:
            if t.name == 'albedoMap':
                if '/' in t.map:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                else:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
        mats.append(mat.data)

    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    for gmesh in h3d.getElementsByTagName('Mesh'):
        try:
            msh_name = gmesh.attributes['name'].value
        except:
            pass
        try:
            msh_matn = gmesh.attributes['material'].value
        except:
            pass
        try:
            msh_tx = float(gmesh.attributes['tx'].value)
        except:
            pass
        try:
            msh_ty = float(gmesh.attributes['ty'].value)
        except:
            pass
        try:
            msh_tz = float(gmesh.attributes['tz'].value)
        except:
            pass
        try:
            msh_batchStart = int(gmesh.attributes['batchStart'].value)
        except:
            pass
        try:
            msh_batchCount = int(gmesh.attributes['batchCount'].value)
        except:
            pass
        try:
            msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
        except:
            pass
        try:
            msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
        except:
            pass

        mat_index = 0
        if '#' in msh_matn:
            mat_name = msh_matn.split('#')[-1:][0]
            for i in range(0, len(h3d_mat)):
                if h3d_mat[i].name == mat_name:
                    mat_index = i
                    break

        matidArray = [mat_index for i in range(int(msh_batchCount / 3))]

        msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
        vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])

        for i in range(0, msh_vertRCount):
            vertArray[i] = geo.vertices.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            normArray[i] = geo.normals.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]

        faceArray = []
        read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)

        msh = mesh(
            vertices=vertArray,
            tverts=[uvw0Array, uvw1Array],
            normals=normArray,
            faces=faceArray,
            obj_name=msh_name,
            flipAxis=True,
            mscale=mscale,
            materials=mats,
            materialIDs=matidArray,
            position=(msh_tx, -msh_tz, msh_ty)
        )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\OL_Brokencars\\BrokenCars\\goldstar\\monster_wheel.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)


```
## Post #26
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T18:57:45+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from mariokart64n ↑Wed Mar 17, 2021 2:13 am at Wed Mar 17, 2021 2:13 am
>
> 
traceback error was related to the materials, so i just deleted that section... seems to work on those files now..
Code: Select all""" ======================================================================

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 16, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote


    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True


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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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


def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")
        if mesh_validate(vertArray, faces):
            # Erase Mesh
            msh.user_clear()
            bpy.data.meshes.remove(msh)
            print("Mesh Deleted!")
            return None
        

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
        if len(materialIDs) > 0:
            for i in range(0, len(materialIDs)):
                obj.data.polygons[i].material_index = materialIDs[i]
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0
    unk02 = 0
    matrix = ((1.0, 0.0, 0.0, 0.0), (0.0, 1.0, 0.0, 0.0), (0.0, 0.0, 1.0, 0.0), (0.0, 0.0, 0.0, 1.0))
    unk03 = 0
    vertex_count = 0
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        self.unk02 = readLong(f)
        self.matrix = (
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
            (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
        )
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)

        # Read Vertices
        self.vertices.index = readLong(f)
        self.vertices.stride = readLong(f)

        if self.vertices.stride != 0x0C:
            print("Error:\tInvalid Vertex Stride")
            return False
        comp = int(self.vertices.stride / 4)
        self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.vertices.data[x][y] = readFloat(f)

        # Read Normals
        self.normals.index = readLong(f)
        self.normals.stride = readLong(f)
        if self.normals.stride != 0x06:
            print("Error:\tInvalid Normal Stride:\t%i" % self.normals.stride)
            return False

        comp = int(self.normals.stride / 2)
        self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.normals.data[x][y] = float(readShort(f) / 32767.0)

        # Read UV-0
        self.texcoord0.index = readLong(f)
        self.texcoord0.stride = readLong(f)
        if self.texcoord0.stride != 0x08:
            print("Error:\tInvalid UV0 Stride")
            return False

        comp = int(self.texcoord0.stride / 4)
        self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord0.data[x][y] = readFloat(f)

        # Read UV-1
        self.texcoord1.index = readLong(f)
        self.texcoord1.stride = readLong(f)
        if self.texcoord1.stride != 0x08:
            print("Error:\tInvalid UV1 Stride")
            return False

        comp = int(self.texcoord1.stride / 4)
        self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
        for x in range(0, self.vertex_count):
            for y in range(0, comp):
                self.texcoord1.data[x][y] = readFloat(f)

        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        for x in range(0, self.face_count):
            self.faces[x] = readLong(f)

        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    try:
        h3d = minidom.parse(h3d_file)

        h3d_mat = []
        h3d_mat_index = 0
        h3d_sp = h3d_sampler()
        h3d_un = h3d_uniform()

        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        return False

    mats = []
    for m in h3d_mat:
        mat = StandardMaterial(m.name)
        for t in m.sampler:
            if t.name == 'albedoMap':
                if '/' in t.map:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                else:
                    mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
        mats.append(mat.data)

    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    for gmesh in h3d.getElementsByTagName('Mesh'):
        try:
            msh_name = gmesh.attributes['name'].value
        except:
            pass
        try:
            msh_matn = gmesh.attributes['material'].value
        except:
            pass
        try:
            msh_tx = float(gmesh.attributes['tx'].value)
        except:
            pass
        try:
            msh_ty = float(gmesh.attributes['ty'].value)
        except:
            pass
        try:
            msh_tz = float(gmesh.attributes['tz'].value)
        except:
            pass
        try:
            msh_batchStart = int(gmesh.attributes['batchStart'].value)
        except:
            pass
        try:
            msh_batchCount = int(gmesh.attributes['batchCount'].value)
        except:
            pass
        try:
            msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
        except:
            pass
        try:
            msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
        except:
            pass

        mat_index = 0
        if '#' in msh_matn:
            mat_name = msh_matn.split('#')[-1:][0]
            for i in range(0, len(h3d_mat)):
                if h3d_mat[i].name == mat_name:
                    mat_index = i
                    break

        matidArray = [mat_index for i in range(int(msh_batchCount / 3))]

        msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
        vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
        uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])

        for i in range(0, msh_vertRCount):
            vertArray[i] = geo.vertices.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            normArray[i] = geo.normals.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]

        for i in range(0, msh_vertRCount):
            uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]

        faceArray = []
        read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)

        msh = mesh(
            vertices=vertArray,
            tverts=[uvw0Array, uvw1Array],
            normals=normArray,
            faces=faceArray,
            obj_name=msh_name,
            flipAxis=True,
            mscale=mscale,
            materials=mats,
            materialIDs=matidArray,
            position=(msh_tx, -msh_tz, msh_ty)
        )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\OL_Brokencars\\BrokenCars\\goldstar\\monster_wheel.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)
That fixes most of the vehicles, but the others still have problems. The vehicles with the pieces out of place, you can fix that by placing the chassis to 0, 0, 0. But we need to find out the root of that. As for Jeep (Wheely), it just refuses to load. It just says "Done!".
## Post #27
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-03-16T19:01:11+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

mariokart64n,

This game uses the Horde 3D engine:
[http://horde3d.org/docs/manual.html](http://horde3d.org/docs/manual.html)

I have used the .geo file format information about 6 years ago in my program.
## Post #28
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T20:08:13+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from Karpati ↑Wed Mar 17, 2021 3:01 am at Wed Mar 17, 2021 3:01 am
>
> 
mariokart64n,

This game uses the Horde 3D engine:
http://horde3d.org/docs/manual.html

I have used the .geo file format information about 6 years ago in my program.

Which program?
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-16T20:20:20+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Wed Mar 17, 2021 2:57 am at Wed Mar 17, 2021 2:57 am
>
> As for Jeep (Wheely), it just refuses to load. It just says "Done!".If it's only this one try
.



Jeep_chassis.png (118.49 KiB) Viewed 67 times


(But guess you know meanwhile how to get uvs' address.)
## Post #30
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T20:33:19+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Wed Mar 17, 2021 4:20 am at Wed Mar 17, 2021 4:20 am
>
> 
ReVolt wrote: ↑Wed Mar 17, 2021 2:57 amAs for Jeep (Wheely), it just refuses to load. It just says "Done!".If it's only this one try
.
Jeep_chassis.png
(But guess you know meanwhile how to get uvs' address.)

The script also doesn't work with Offroad Legends 2. By that, I mean all the cars, they won't load. (also I do know how to get uv address now)
Well, sampling time!
The new carry:
GEO: [https://www.mediafire.com/file/2vbpspby ... s.geo/file](https://www.mediafire.com/file/2vbpspbyvwgt80k/chassis.geo/file)
H3D: [https://www.mediafire.com/file/hca3t835 ... s.h3d/file](https://www.mediafire.com/file/hca3t835e72akcf/chassis.h3d/file)
Edit: Also we still need to figure out the position of the wheels. I tried using the XML from the files but got this... (Also the Y and Z is swapped.)
## Post #31
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-17T19:58:56+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

Not sure why the thread just decided to die, but here's what prints when it tries to import the broken Jeep:

```
Error:   Failed to Read File
```

 
Well, in an update DB decided to change Wheely's design into a UAZ for some reason... This error also appears in Offroad Legends 2 and Off the Road.  So, I'm just going with the conclusion that Horde3D changed the structure of their GEOs. Can this be fixed?
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-17T23:18:29+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Thu Mar 18, 2021 3:58 am at Thu Mar 18, 2021 3:58 am
>
> 
Not sure why the thread just decided to die, but here's what prints when it tries to import the broken Jeep:
Code: Select allError:  Invalid UV0 Stride
Error:   Failed to Read File"decided to die"?  Maybe think about your expectations?
I did some manual fixing for the jeep:
.



Jeep.png (200.3 KiB) Viewed 132 times


But for a better solution (than that per-model-fix) you need to wait for our scripting genius to return.
## Post #33
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-17T23:23:17+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from shakotay2 ↑Thu Mar 18, 2021 7:18 am at Thu Mar 18, 2021 7:18 am
>
> 
ReVolt wrote: ↑Thu Mar 18, 2021 3:58 am
Not sure why the thread just decided to die, but here's what prints when it tries to import the broken Jeep:
Code: Select allError:  Invalid UV0 Stride
Error:   Failed to Read File
"decided to die"?  Maybe think about your expectations?
I did some manual fixing for the jeep:
.
Jeep.png
But for a better solution (than that per-model-fix) you need to wait for our scripting genius to return.

Yeah, that's who I'm waiting for. Hex2OBJ still works, but it still seems a bit tricky than the script. One DWord off and you're screwed...eek!
A̶l̶s̶o̶ ̶t̶o̶ ̶t̶h̶a̶t̶ ̶c̶r̶e̶a̶t̶o̶r̶ ̶o̶f̶ ̶t̶h̶e̶ ̶s̶c̶r̶i̶p̶t̶,̶ ̶t̶h̶e̶ ̶s̶m̶o̶o̶t̶h̶ ̶s̶h̶a̶d̶i̶n̶g̶ ̶o̶n̶ ̶t̶h̶e̶ ̶m̶e̶s̶h̶e̶s̶ ̶l̶o̶o̶k̶s̶ ̶o̶d̶d̶.̶.̶.̶ (I went to your deviantart page to check out your other tools and I was blasted with p***n  )
## Post #34
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-19T03:28:48+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

only thing on my DA account is programs, so you would have had to enable 18+ content in your account and have searched through all my likes <_< If i could private my likes I would, holy

Anyway if you had missed it, Karpati posted this

> Reply from Karpati ↑Wed Mar 17, 2021 3:01 am at Wed Mar 17, 2021 3:01 am
>
> 
mariokart64n,

This game uses the Horde 3D engine:
http://horde3d.org/docs/manual.html

I have used the .geo file format information about 6 years ago in my program.

Try Karpati's Program: 
[http://www.i3dconverter.com/index.html](http://www.i3dconverter.com/index.html)
## Post #35
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-19T11:46:41+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from mariokart64n ↑Fri Mar 19, 2021 11:28 am at Fri Mar 19, 2021 11:28 am
>
> 
only thing on my DA account is programs, so you would have had to enable 18+ content in your account and have searched through all my likes <_< If i could private my likes I would, holy

Anyway if you had missed it, Karpati posted this
Karpati wrote: ↑Wed Mar 17, 2021 3:01 am
mariokart64n,

This game uses the Horde 3D engine:
http://horde3d.org/docs/manual.html

I have used the .geo file format information about 6 years ago in my program.


Try Karpati's Program: 
http://www.i3dconverter.com/index.html

nice program, I guess I will use it as an alternative to your script, on the broken vehicles
## Post #36
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-19T16:59:08+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from Karpati ↑Wed Mar 17, 2021 3:01 am at Wed Mar 17, 2021 3:01 am
>
> 
mariokart64n,

This game uses the Horde 3D engine:
http://horde3d.org/docs/manual.html

I have used the .geo file format information about 6 years ago in my program.
Coming back to you, it seems like the models from "Off the Road" won't load. It just tells me the 1st polygon is "bad". ????
Here: [https://www.mediafire.com/file/s7i3tbfr ... 9.geo/file](https://www.mediafire.com/file/s7i3tbfr6l3d3ju/chassis%25282%2529.geo/file)
## Post #37
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-20T20:38:15+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

This will be the LAST UPDATE (I will no longer be involved with this format from this point on)

I made tweaks to the script to work with that one geo file u shared (i don't know if it'll work with anything else) alot of code had to be deleted or restructured because the file you sent does not have a h3d so it was impossible to load the file without deleting sections of the material code.

in the future please put some effort into organizing information and uploading a variety of sufficient file samples. it is frustrating working on only a few files, files that are missing side files, or files that are mixed in from different games of different versions or generations of files...

Anyway Goodluck

```

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 20, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote
       
    2021-03-20
        Updates Made to work with Version 6 files
        H3D loading was stripped to load just geo (materials are now removed gone)

    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True

signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function
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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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

def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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

    if mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")

        # Erase Mesh
        #msh.user_clear()
        #bpy.data.meshes.remove(msh)
        #print("Mesh Deleted!")
        #return None
        

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
        if len(materialIDs) > 0:
            for i in range(0, len(materialIDs)):
                obj.data.polygons[i].material_index = materialIDs[i]
    elif len(materialIDs) > 0:
        for i in range(0, len(obj.data.polygons)):
            if i < len(materialIDs):
                obj.data.polygons[i].material_index = materialIDs[i]
            else:
                obj.data.polygons[i].material_index = 0
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0   # VERSION '5'
    unk02 = 0   # Num Bones
    matrix = []
    unk03 = 0   # Num Vertex Components
    vertex_count = 0
    # Vertex Stream starts here
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        if self.unk01 != 5 and self.unk01 !=6:
            print("Version Unsupported")
            return False
        self.unk02 = readLong(f)
        for i in range(0, self.unk02):
            self.matrix.append((
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
                ))
        
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)
        #print ("vertex_count:\t%i" % self.vertex_count)
        for vs in range(0, self.unk03):
            block_id = readLong(f)
            block_stride = readLong(f)
            block_start = f.pos
            #print ("block_start:\t%i" % block_start)
            #print ("block_stride:\t%i" % block_stride)
            if block_id == 0:   # Positions
                print('BlockID:\tPOSITION')
                comp = int(block_stride / 4)
                self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.vertices.data[x][y] = readFloat(f)
            elif block_id == 1: # Normals
                print('BlockID:\tNORMAL')
                comp = int(block_stride / 2)
                self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.normals.data[x][y] = float(readShort(f) / 32767.0)
            #elif block_id == 2: # Tangents
            #elif block_id == 3: # BiNormals
            #elif block_id == 4: # Bone Ids
            #elif block_id == 5: # Weights
            elif block_id == 6: # Texture UV0
                print('BlockID:\tTEXCOORD0')
                if block_stride == 4:
                    comp = int(block_stride / 2)
                    self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                    for x in range(0, self.vertex_count):
                        for y in range(0, comp):
                            self.texcoord0.data[x][y] = float(readShort(f) / 32767.0)
                elif block_stride == 6:
                    comp = int(block_stride / 4)
                    self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                    for x in range(0, self.vertex_count):
                        for y in range(0, comp):
                            self.texcoord0.data[x][y] = readFloat(f)
            elif block_id == 7: # Texture UV1
                print('BlockID:\tTEXCOORD1')
                comp = int(block_stride / 4)
                self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.texcoord1.data[x][y] = readFloat(f)
            else:
                print("Unidentified Block ID:\t%i" % block_id)
            f.set_pointer(block_start + (self.vertex_count * block_stride))
        
        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        
        face_stride = 4
        if self.unk01 == 6:
            face_stride = readLong(f)
        if face_stride == 4:
            for x in range(0, self.face_count):
                self.faces[x] = readLong(f)
        elif face_stride == 2:
            for x in range(0, self.face_count):
                self.faces[x] = readShort(f)
        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        #return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    h3d = None
    h3d_mat = []
    h3d_mat_index = 0
    h3d_sp = h3d_sampler()
    h3d_un = h3d_uniform()
    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    uvSet = []
    mats = []
    try:
        h3d = minidom.parse(h3d_file)
        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        #return False

    if h3d != None:
        for m in h3d_mat:
            mat = StandardMaterial(m.name)
            for t in m.sampler:
                if t.name == 'albedoMap':
                    if '/' in t.map:
                        mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                    else:
                        mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
            mats.append(mat.data)


        for gmesh in h3d.getElementsByTagName('Mesh'):
            try:
                msh_name = gmesh.attributes['name'].value
            except:
                pass
            try:
                msh_matn = gmesh.attributes['material'].value
            except:
                pass
            try:
                msh_tx = float(gmesh.attributes['tx'].value)
            except:
                pass
            try:
                msh_ty = float(gmesh.attributes['ty'].value)
            except:
                pass
            try:
                msh_tz = float(gmesh.attributes['tz'].value)
            except:
                pass
            try:
                msh_batchStart = int(gmesh.attributes['batchStart'].value)
            except:
                pass
            try:
                msh_batchCount = int(gmesh.attributes['batchCount'].value)
            except:
                pass
            try:
                msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
            except:
                pass
            try:
                msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
            except:
                pass

            mat_index = 0
            if '#' in msh_matn:
                mat_name = msh_matn.split('#')[-1:][0]
                mat_index = 0
                for i in range(0, len(h3d_mat)):
                    if h3d_mat[i].name == mat_name:
                        mat_index = i
                        break
                mat_index = mat_index % len(h3d_mat)
            
            msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
            vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvSet = []
            for i in range(0, msh_vertRCount):
                vertArray[i] = geo.vertices.data[msh_vertRStart + i]

            for i in range(0, msh_vertRCount):
                normArray[i] = geo.normals.data[msh_vertRStart + i]
            
            if len(geo.texcoord0.data) >= msh_vertRStart + msh_vertRCount:
                for i in range(0, msh_vertRCount):
                    uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]
                uvSet.append(uvw0Array)
            
            if len(geo.texcoord1.data) >= msh_vertRStart + msh_vertRCount:
                for i in range(0, msh_vertRCount):
                    uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]
                uvSet.append(uvw1Array)
                
            faceArray = []
            matidArray = []
            matidArray = [mat_index for i in range(int(msh_batchCount / 3))]
            read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)
       
            msh = mesh(
                vertices=vertArray,
                tverts=uvSet,
                normals=normArray,
                faces=faceArray,
                obj_name=msh_name,
                flipAxis=True,
                mscale=mscale,
                materials=mats,
                materialIDs=matidArray,
                position=(msh_tx, -msh_tz, msh_ty)
                )

    else:
        uvSet = []

        if len(geo.texcoord0.data) > 0:
            uvSet.append(geo.texcoord0.data)

        if len(geo.texcoord1.data) > 0:
            uvSet.append(geo.texcoord1.data)

        faceArray = []
        read_triangle_list(geo.faces, faceArray, geo.face_count, 0, 0)
        
        msh = mesh (
            vertices=geo.vertices.data,
            tverts=uvSet,
            normals=geo.normals.data,
            faces=faceArray,
            flipAxis=True,
            mscale=mscale
            )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\OL_Brokencars\\BrokenCars\\jeep\\chassis.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)


```
## Post #38
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-20T21:36:58+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from mariokart64n ↑Sun Mar 21, 2021 4:38 am at Sun Mar 21, 2021 4:38 am
>
> 
This will be the LAST UPDATE (I will no longer be involved with this format from this point on)

I made tweaks to the script to work with that one geo file u shared (i don't know if it'll work with anything else) alot of code had to be deleted or restructured because the file you sent does not have a h3d so it was impossible to load the file without deleting sections of the material code.

in the future please put some effort into organizing information and uploading a variety of sufficient file samples. it is frustrating working on only a few files, files that are missing side files, or files that are mixed in from different games of different versions or generations of files...

Anyway Goodluck
Code: Select all""" ======================================================================

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 20, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote
       
    2021-03-20
        Updates Made to work with Version 6 files
        H3D loading was stripped to load just geo (materials are now removed gone)

    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True

signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function
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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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

def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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

    if mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")

        # Erase Mesh
        #msh.user_clear()
        #bpy.data.meshes.remove(msh)
        #print("Mesh Deleted!")
        #return None
        

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
        if len(materialIDs) > 0:
            for i in range(0, len(materialIDs)):
                obj.data.polygons[i].material_index = materialIDs[i]
    elif len(materialIDs) > 0:
        for i in range(0, len(obj.data.polygons)):
            if i < len(materialIDs):
                obj.data.polygons[i].material_index = materialIDs[i]
            else:
                obj.data.polygons[i].material_index = 0
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0   # VERSION '5'
    unk02 = 0   # Num Bones
    matrix = []
    unk03 = 0   # Num Vertex Components
    vertex_count = 0
    # Vertex Stream starts here
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        if self.unk01 != 5 and self.unk01 !=6:
            print("Version Unsupported")
            return False
        self.unk02 = readLong(f)
        for i in range(0, self.unk02):
            self.matrix.append((
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
                ))
        
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)
        #print ("vertex_count:\t%i" % self.vertex_count)
        for vs in range(0, self.unk03):
            block_id = readLong(f)
            block_stride = readLong(f)
            block_start = f.pos
            #print ("block_start:\t%i" % block_start)
            #print ("block_stride:\t%i" % block_stride)
            if block_id == 0:   # Positions
                print('BlockID:\tPOSITION')
                comp = int(block_stride / 4)
                self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.vertices.data[x][y] = readFloat(f)
            elif block_id == 1: # Normals
                print('BlockID:\tNORMAL')
                comp = int(block_stride / 2)
                self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.normals.data[x][y] = float(readShort(f) / 32767.0)
            #elif block_id == 2: # Tangents
            #elif block_id == 3: # BiNormals
            #elif block_id == 4: # Bone Ids
            #elif block_id == 5: # Weights
            elif block_id == 6: # Texture UV0
                print('BlockID:\tTEXCOORD0')
                if block_stride == 4:
                    comp = int(block_stride / 2)
                    self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                    for x in range(0, self.vertex_count):
                        for y in range(0, comp):
                            self.texcoord0.data[x][y] = float(readShort(f) / 32767.0)
                elif block_stride == 6:
                    comp = int(block_stride / 4)
                    self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                    for x in range(0, self.vertex_count):
                        for y in range(0, comp):
                            self.texcoord0.data[x][y] = readFloat(f)
            elif block_id == 7: # Texture UV1
                print('BlockID:\tTEXCOORD1')
                comp = int(block_stride / 4)
                self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.texcoord1.data[x][y] = readFloat(f)
            else:
                print("Unidentified Block ID:\t%i" % block_id)
            f.set_pointer(block_start + (self.vertex_count * block_stride))
        
        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        
        face_stride = 4
        if self.unk01 == 6:
            face_stride = readLong(f)
        if face_stride == 4:
            for x in range(0, self.face_count):
                self.faces[x] = readLong(f)
        elif face_stride == 2:
            for x in range(0, self.face_count):
                self.faces[x] = readShort(f)
        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        #return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    h3d = None
    h3d_mat = []
    h3d_mat_index = 0
    h3d_sp = h3d_sampler()
    h3d_un = h3d_uniform()
    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    uvSet = []
    mats = []
    try:
        h3d = minidom.parse(h3d_file)
        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        #return False

    if h3d != None:
        for m in h3d_mat:
            mat = StandardMaterial(m.name)
            for t in m.sampler:
                if t.name == 'albedoMap':
                    if '/' in t.map:
                        mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                    else:
                        mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
            mats.append(mat.data)


        for gmesh in h3d.getElementsByTagName('Mesh'):
            try:
                msh_name = gmesh.attributes['name'].value
            except:
                pass
            try:
                msh_matn = gmesh.attributes['material'].value
            except:
                pass
            try:
                msh_tx = float(gmesh.attributes['tx'].value)
            except:
                pass
            try:
                msh_ty = float(gmesh.attributes['ty'].value)
            except:
                pass
            try:
                msh_tz = float(gmesh.attributes['tz'].value)
            except:
                pass
            try:
                msh_batchStart = int(gmesh.attributes['batchStart'].value)
            except:
                pass
            try:
                msh_batchCount = int(gmesh.attributes['batchCount'].value)
            except:
                pass
            try:
                msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
            except:
                pass
            try:
                msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
            except:
                pass

            mat_index = 0
            if '#' in msh_matn:
                mat_name = msh_matn.split('#')[-1:][0]
                mat_index = 0
                for i in range(0, len(h3d_mat)):
                    if h3d_mat[i].name == mat_name:
                        mat_index = i
                        break
                mat_index = mat_index % len(h3d_mat)
            
            msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
            vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvSet = []
            for i in range(0, msh_vertRCount):
                vertArray[i] = geo.vertices.data[msh_vertRStart + i]

            for i in range(0, msh_vertRCount):
                normArray[i] = geo.normals.data[msh_vertRStart + i]
            
            if len(geo.texcoord0.data) >= msh_vertRStart + msh_vertRCount:
                for i in range(0, msh_vertRCount):
                    uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]
                uvSet.append(uvw0Array)
            
            if len(geo.texcoord1.data) >= msh_vertRStart + msh_vertRCount:
                for i in range(0, msh_vertRCount):
                    uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]
                uvSet.append(uvw1Array)
                
            faceArray = []
            matidArray = []
            matidArray = [mat_index for i in range(int(msh_batchCount / 3))]
            read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)
       
            msh = mesh(
                vertices=vertArray,
                tverts=uvSet,
                normals=normArray,
                faces=faceArray,
                obj_name=msh_name,
                flipAxis=True,
                mscale=mscale,
                materials=mats,
                materialIDs=matidArray,
                position=(msh_tx, -msh_tz, msh_ty)
                )

    else:
        uvSet = []

        if len(geo.texcoord0.data) > 0:
            uvSet.append(geo.texcoord0.data)

        if len(geo.texcoord1.data) > 0:
            uvSet.append(geo.texcoord1.data)

        faceArray = []
        read_triangle_list(geo.faces, faceArray, geo.face_count, 0, 0)
        
        msh = mesh (
            vertices=geo.vertices.data,
            tverts=uvSet,
            normals=geo.normals.data,
            faces=faceArray,
            flipAxis=True,
            mscale=mscale
            )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\OL_Brokencars\\BrokenCars\\jeep\\chassis.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)

love it!
## Post #39
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-20T21:47:45+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from mariokart64n ↑Sun Mar 21, 2021 4:38 am at Sun Mar 21, 2021 4:38 am
>
> 
This will be the LAST UPDATE (I will no longer be involved with this format from this point on)

I made tweaks to the script to work with that one geo file u shared (i don't know if it'll work with anything else) alot of code had to be deleted or restructured because the file you sent does not have a h3d so it was impossible to load the file without deleting sections of the material code.

in the future please put some effort into organizing information and uploading a variety of sufficient file samples. it is frustrating working on only a few files, files that are missing side files, or files that are mixed in from different games of different versions or generations of files...

Anyway Goodluck
Code: Select all""" ======================================================================

    PythonScript:   [Mobile] Offroad Legends
    Author:         mariokart64n
    Date:           March 20, 2021
    Version:        0.1

    ======================================================================

    ChangeLog:

    2021-03-16
        Script Wrote
       
    2021-03-20
        Updates Made to work with Version 6 files
        H3D loading was stripped to load just geo (materials are now removed gone)

    ====================================================================== """

import bpy  # Needed to interface with blender
import struct  # Needed for Binary Reader
import math
from pathlib import Path  # Needed for os stuff
from xml.dom import minidom

useOpenDialog = True

signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function
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



def getFilenamePath(file):  # returns: "g:\subdir1\subdir2\"
    return (str(Path(file).resolve().parent) + "\\")


def getFilenameFile(file):  # returns: "myImage"
    return Path(file).stem


def Bitmaptexture(mat, filename="", name="ShaderNodeTexImage"):
    imageTex = mat.node_tree.nodes.new('ShaderNodeTexImage')
    imageTex.label = name
    try:
        imageTex.image = bpy.data.images.load(
            filepath=filename,
            check_existing=False
        )
        imageTex.image.name = filenameFromPath(filename)
        imageTex.image.colorspace_settings.name = 'sRGB'
    except:
        imageTex.image = bpy.data.images.new(
            name=filename,
            width=8,
            height=8,
            alpha=False,
            float_buffer=False
        )
    return imageTex


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

def fclose(bitStream):
    bitStream.flush()
    bitStream.isGood = False


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

    if mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None


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
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # and additional or a replacement valatiation function
    # would be required
    
    if msh.validate():
        print("Mesh Failed Validation")

        # Erase Mesh
        #msh.user_clear()
        #bpy.data.meshes.remove(msh)
        #print("Mesh Deleted!")
        #return None
        

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
        if len(materialIDs) > 0:
            for i in range(0, len(materialIDs)):
                obj.data.polygons[i].material_index = materialIDs[i]
    elif len(materialIDs) > 0:
        for i in range(0, len(obj.data.polygons)):
            if i < len(materialIDs):
                obj.data.polygons[i].material_index = materialIDs[i]
            else:
                obj.data.polygons[i].material_index = 0
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


class h3d_uniform:
    name = ""
    a = 0.0
    b = 0.0
    c = 0.0
    d = 0.0


class h3d_sampler:
    name = ""
    map = ""


class h3d_material:
    name = ""
    sampler = []
    uniform = []


class h3d_geo_block:
    index = 0
    stride = 0
    data = []


class h3d_geo_file:
    fileid = 0  # 0x47443348 'H3DG'
    unk01 = 0   # VERSION '5'
    unk02 = 0   # Num Bones
    matrix = []
    unk03 = 0   # Num Vertex Components
    vertex_count = 0
    # Vertex Stream starts here
    vertices = h3d_geo_block()
    normals = h3d_geo_block()
    texcoord0 = h3d_geo_block()
    texcoord1 = h3d_geo_block()
    face_count = 0
    faces = []

    def __repr__(self):
        return 'VertexCount:\t%i\nFaceCount:\t%i\nUnknowns:\t%i\t%i\t%i' % (
        self.vertex_count, self.face_count, self.unk01, self.unk02, self.unk03)

    def read(self, f=fopen()):
        self.fileid = readLong(f)
        if self.fileid != 0x47443348:
            print("Error:\tInvalid File")
            return False

        self.unk01 = readLong(f)
        if self.unk01 != 5 and self.unk01 !=6:
            print("Version Unsupported")
            return False
        self.unk02 = readLong(f)
        for i in range(0, self.unk02):
            self.matrix.append((
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f)),
                (readFloat(f), readFloat(f), readFloat(f), readFloat(f))
                ))
        
        self.unk03 = readLong(f)
        self.vertex_count = readLong(f)
        #print ("vertex_count:\t%i" % self.vertex_count)
        for vs in range(0, self.unk03):
            block_id = readLong(f)
            block_stride = readLong(f)
            block_start = f.pos
            #print ("block_start:\t%i" % block_start)
            #print ("block_stride:\t%i" % block_stride)
            if block_id == 0:   # Positions
                print('BlockID:\tPOSITION')
                comp = int(block_stride / 4)
                self.vertices.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.vertices.data[x][y] = readFloat(f)
            elif block_id == 1: # Normals
                print('BlockID:\tNORMAL')
                comp = int(block_stride / 2)
                self.normals.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.normals.data[x][y] = float(readShort(f) / 32767.0)
            #elif block_id == 2: # Tangents
            #elif block_id == 3: # BiNormals
            #elif block_id == 4: # Bone Ids
            #elif block_id == 5: # Weights
            elif block_id == 6: # Texture UV0
                print('BlockID:\tTEXCOORD0')
                if block_stride == 4:
                    comp = int(block_stride / 2)
                    self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                    for x in range(0, self.vertex_count):
                        for y in range(0, comp):
                            self.texcoord0.data[x][y] = float(readShort(f) / 32767.0)
                elif block_stride == 6:
                    comp = int(block_stride / 4)
                    self.texcoord0.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                    for x in range(0, self.vertex_count):
                        for y in range(0, comp):
                            self.texcoord0.data[x][y] = readFloat(f)
            elif block_id == 7: # Texture UV1
                print('BlockID:\tTEXCOORD1')
                comp = int(block_stride / 4)
                self.texcoord1.data = ([[[float] for x in range(comp)] for y in range(self.vertex_count)])
                for x in range(0, self.vertex_count):
                    for y in range(0, comp):
                        self.texcoord1.data[x][y] = readFloat(f)
            else:
                print("Unidentified Block ID:\t%i" % block_id)
            f.set_pointer(block_start + (self.vertex_count * block_stride))
        
        # Faces
        self.face_count = readLong(f)
        self.faces = [[int] for x in range(self.face_count)]
        
        face_stride = 4
        if self.unk01 == 6:
            face_stride = readLong(f)
        if face_stride == 4:
            for x in range(0, self.face_count):
                self.faces[x] = readLong(f)
        elif face_stride == 2:
            for x in range(0, self.face_count):
                self.faces[x] = readShort(f)
        return True


def read_triangle_strip(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    i = 0
    face = [1, 1, 1]
    while i < faceCount:
        faceCW = True
        face[0] = faces[i + facePosition]
        face[1] = faces[i + facePosition + 1]
        i += 2
        while i < faceCount:
            face[2] = faces[i + facePosition]
            if face[2] == 0xFFFF or face[2] == -1: break
            if face[0] != face[2] and face[1] != face[2] and face[2] != face[0]:
                if faceCW:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[1] + faceOffset,
                        face[2] + faceOffset
                    ])
                else:
                    faceArray.append([
                        face[0] + faceOffset,
                        face[2] + faceOffset,
                        face[1] + faceOffset
                    ])
            faceCW = not faceCW
            face = [face[1], face[2], face[0]]
            i += 1
    return None


def read_triangle_list(faces=[], faceArray=[], faceCount=0, facePosition=0, faceOffset=0):
    for i in range(0, int(faceCount / 3)):
        faceArray.append([
            faces[(i * 3) + facePosition] + faceOffset,
            faces[(i * 3) + facePosition + 1] + faceOffset,
            faces[(i * 3) + facePosition + 2] + faceOffset
        ])
    return None


def read(file="", mscale=1.0):
    # Check File is present
    if not doesFileExist(file):
        print("Error:\tFailed To Find Geo File")
        return False

    # Strip Paths From fullpath to find sister file
    fpath = getFilenamePath(file)
    fname = getFilenameFile(file)
    h3d_file = fpath + fname + ".h3d"

    # Check if sister file is found
    if not doesFileExist(h3d_file):
        print("Error:\tFailed To Find H3D File")
        #return False

    # open GEO file
    f = fopen(file, 'rb')

    # Create GEO Object to store data from Geo file
    geo = h3d_geo_file()

    # Attempt to read GEO file into Geo Class
    read_good = False
    try:
        read_good = geo.read(f)
    except:
        print("Error:\t Failed to Read File")
        return False

    # Check if Geo File Was Read
    if not read_good:
        print("Error:\t Failed to Read File")
        return False

    # Print Geo Class Info
    print(repr(geo))

    # Close Geo File
    fclose(f)

    # Read Sister File, import data
    h3d = None
    h3d_mat = []
    h3d_mat_index = 0
    h3d_sp = h3d_sampler()
    h3d_un = h3d_uniform()
    msh = None
    msh_name = ""
    msh_matn = ""
    msh_tx = 0.0
    msh_ty = 0.0
    msh_tz = 0.0
    msh_batchStart = 0
    msh_batchCount = 0
    msh_vertRStart = 0
    msh_vertREnd = 0
    msh_vertRCount = 0
    mat_index = 0
    mat_name = ""
    vertArray = []
    normArray = []
    uvw0Array = []
    uvw1Array = []
    faceArray = []
    matidArray = []
    uvSet = []
    mats = []
    try:
        h3d = minidom.parse(h3d_file)
        for materials in h3d.getElementsByTagName('Materials'):
            for material in materials.getElementsByTagName('Material'):
                h3d_mat.append(h3d_material())

                h3d_mat[h3d_mat_index].name = material.attributes['name'].value

                for sampler in material.getElementsByTagName('Sampler'):
                    h3d_sp = h3d_sampler()
                    try:
                        h3d_sp.name = sampler.attributes['name'].value
                        h3d_sp.map = sampler.attributes['map'].value
                        h3d_mat[h3d_mat_index].sampler.append(h3d_sp)
                    except:
                        pass

                for uniform in material.getElementsByTagName('Uniform'):
                    h3d_un = h3d_uniform()
                    try:
                        h3d_un.name = sampler.attributes['name'].value
                        h3d_un.a = float(sampler.attributes['a'].value)
                        h3d_un.b = float(sampler.attributes['b'].value)
                        h3d_un.c = float(sampler.attributes['c'].value)
                        h3d_un.d = float(sampler.attributes['d'].value)
                        h3d_mat[h3d_mat_index].uniform.append(h3d_un)
                    except:
                        pass
                h3d_mat_index += 1

    except:
        print("Error:\tFailed to Parse XML file")
        #return False

    if h3d != None:
        for m in h3d_mat:
            mat = StandardMaterial(m.name)
            for t in m.sampler:
                if t.name == 'albedoMap':
                    if '/' in t.map:
                        mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map.split('/')[-1:][0]))
                    else:
                        mat.diffuseMap(Bitmaptexture(mat.data, filename=t.map))
            mats.append(mat.data)


        for gmesh in h3d.getElementsByTagName('Mesh'):
            try:
                msh_name = gmesh.attributes['name'].value
            except:
                pass
            try:
                msh_matn = gmesh.attributes['material'].value
            except:
                pass
            try:
                msh_tx = float(gmesh.attributes['tx'].value)
            except:
                pass
            try:
                msh_ty = float(gmesh.attributes['ty'].value)
            except:
                pass
            try:
                msh_tz = float(gmesh.attributes['tz'].value)
            except:
                pass
            try:
                msh_batchStart = int(gmesh.attributes['batchStart'].value)
            except:
                pass
            try:
                msh_batchCount = int(gmesh.attributes['batchCount'].value)
            except:
                pass
            try:
                msh_vertRStart = int(gmesh.attributes['vertRStart'].value)
            except:
                pass
            try:
                msh_vertREnd = int(gmesh.attributes['vertREnd'].value)
            except:
                pass

            mat_index = 0
            if '#' in msh_matn:
                mat_name = msh_matn.split('#')[-1:][0]
                mat_index = 0
                for i in range(0, len(h3d_mat)):
                    if h3d_mat[i].name == mat_name:
                        mat_index = i
                        break
                mat_index = mat_index % len(h3d_mat)
            
            msh_vertRCount = msh_vertREnd - msh_vertRStart + 1
            vertArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            normArray = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvw0Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvw1Array = ([[[float] for x in range(3)] for y in range(msh_vertRCount)])
            uvSet = []
            for i in range(0, msh_vertRCount):
                vertArray[i] = geo.vertices.data[msh_vertRStart + i]

            for i in range(0, msh_vertRCount):
                normArray[i] = geo.normals.data[msh_vertRStart + i]
            
            if len(geo.texcoord0.data) >= msh_vertRStart + msh_vertRCount:
                for i in range(0, msh_vertRCount):
                    uvw0Array[i] = geo.texcoord0.data[msh_vertRStart + i]
                uvSet.append(uvw0Array)
            
            if len(geo.texcoord1.data) >= msh_vertRStart + msh_vertRCount:
                for i in range(0, msh_vertRCount):
                    uvw1Array[i] = geo.texcoord1.data[msh_vertRStart + i]
                uvSet.append(uvw1Array)
                
            faceArray = []
            matidArray = []
            matidArray = [mat_index for i in range(int(msh_batchCount / 3))]
            read_triangle_list(geo.faces, faceArray, msh_batchCount, msh_batchStart, -msh_vertRStart)
       
            msh = mesh(
                vertices=vertArray,
                tverts=uvSet,
                normals=normArray,
                faces=faceArray,
                obj_name=msh_name,
                flipAxis=True,
                mscale=mscale,
                materials=mats,
                materialIDs=matidArray,
                position=(msh_tx, -msh_tz, msh_ty)
                )

    else:
        uvSet = []

        if len(geo.texcoord0.data) > 0:
            uvSet.append(geo.texcoord0.data)

        if len(geo.texcoord1.data) > 0:
            uvSet.append(geo.texcoord1.data)

        faceArray = []
        read_triangle_list(geo.faces, faceArray, geo.face_count, 0, 0)
        
        msh = mesh (
            vertices=geo.vertices.data,
            tverts=uvSet,
            normals=geo.normals.data,
            faces=faceArray,
            flipAxis=True,
            mscale=mscale
            )

    return True


# Callback when file(s) are selected
def offroad_legends_imp_callback(fpath="", files=[], clearScene=True, mscale = 1.0):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read(fpath + file.name, mscale)
    if len(files) > 0:
        messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def offroad_legends_imp(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_offroad_legends_imp"):  # print(bpy.ops.importhelper.offroad_legends_imp.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_offroad_legends_imp'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_offroad_legends_imp(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.offroad_legends_imp"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.geo', options={'HIDDEN'}, subtype='FILE_PATH')

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
            try: self.filepath = bpy.types.Scene.offroad_legends_imp_filepath
            except: bpy.types.Scene.offroad_legends_imp_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.offroad_legends_imp_directory
            except: bpy.types.Scene.offroad_legends_imp_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.offroad_legends_imp_my_float1
            except: bpy.types.Scene.offroad_legends_imp_my_float1 = bpy.props.FloatProperty(default=1.0)

            try: self.my_bool1 = bpy.types.Scene.offroad_legends_imp_my_bool1
            except: bpy.types.Scene.offroad_legends_imp_my_bool1 = bpy.props.BoolProperty(default=False)


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
            bpy.types.Scene.offroad_legends_imp_filepath = self.filepath
            bpy.types.Scene.offroad_legends_imp_directory = self.directory
            bpy.types.Scene.offroad_legends_imp_my_float1 = self.my_float1
            bpy.types.Scene.offroad_legends_imp_my_bool1 = self.my_bool1

            # Run Callback
            offroad_legends_imp_callback(self.directory + "\\", self.files, self.my_bool1, self.my_float1)

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
            col.label(text="March 16, 2021")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.offroad_legends_imp", text="Off Road Legends (*.geo)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_offroad_legends_imp)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_offroad_legends_imp.menu_func_import)

    # Call ImportHelper
    bpy.ops.importhelper.offroad_legends_imp('INVOKE_DEFAULT')


if not useOpenDialog:
    deleteScene(['MESH', 'ARMATURE'])  # Clear Scene
    clearListener()  # clears out console
    read(
        "C:\\Users\\Corey\\Downloads\\Cars The Video Game\\OL_Brokencars\\BrokenCars\\jeep\\chassis.geo"
        )
    messageBox("Done!")
else:
    offroad_legends_imp(True)

Did I forgot to include H3D? O CRAP!!!!!!!
HERE: [https://www.mediafire.com/file/j0oqfvcg ... 9.h3d/file](https://www.mediafire.com/file/j0oqfvcggkeo0vb/chassis%25282%2529.h3d/file)
aaa I'm so sorry for not including an h3d
## Post #40
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-03-21T13:16:26+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from ReVolt ↑Sat Mar 20, 2021 12:59 am at Sat Mar 20, 2021 12:59 am
>
> 
Coming back to you, it seems like the models from "Off the Road" won't load. It just tells me the 1st polygon is "bad". ????
Here: https://www.mediafire.com/file/s7i3tbfr ... 9.geo/file

I have modified my 6 years old Horde3D loader module (that supported the v5 model format only) to support the v6 model format and I have released the 3D Object Converter v7.046 (Windows).

How to get the 3D Object Converter v7.046:
Download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.046.


I must rewrite the Horde3D .geo loader module to support the external .h3d file (subobjects with material information).
## Post #41
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-22T15:06:12+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from Karpati ↑Sun Mar 21, 2021 9:16 pm at Sun Mar 21, 2021 9:16 pm
>
> 
ReVolt wrote: ↑Sat Mar 20, 2021 12:59 am
Coming back to you, it seems like the models from "Off the Road" won't load. It just tells me the 1st polygon is "bad". ????
Here: https://www.mediafire.com/file/s7i3tbfr ... 9.geo/file


I have modified my 6 years old Horde3D loader module (that supported the v5 model format only) to support the v6 model format and I have released the 3D Object Converter v7.046 (Windows).

How to get the 3D Object Converter v7.046:
Download the 3D Object Converter from http://3doc.i3dconverter.com and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.046.


I must rewrite the Horde3D .geo loader module to support the external .h3d file (subobjects with material information).

Okay, will buy in a few month, but right now, I'm saving up for an RC car.
## Post #42
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-04-03T12:58:50+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

I have finished my Horde3D Engine (v5;v6; Offroad Legends; Offroad Legends 2) *.GEO/*.SCENE.XML/*.MATERIAL.XML or *.GEO/*.H3D loader module and I have released the following programs as web updates:

- 3D Object Converter v7.047 (Windows)
- i3DConverter v3.905 (macOS)
- i3DConverter v1.905 (Linux)

How to get the 3D Object Converter v7.047:
Download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.047.

How to get the i3DConverter v3.905 macOS:
Download the i3DConverter from [http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v3.905.

How to get the i3DConverter v1.905 Linux:
Download the i3DConverter from [http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v1.905.
## Post #43
- Username: MarKreationsStudios
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 03, 2020 5:47 am
- Post datetime: 2021-04-08T16:03:54+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

So sorry if it's already been asked, but can you try making a converter for PS3 .str models?
## Post #44
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-04-21T23:34:52+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

> Reply from Karpati ↑Sat Apr 03, 2021 8:58 pm at Sat Apr 03, 2021 8:58 pm
>
> 
I have finished my Horde3D Engine (v5;v6; Offroad Legends; Offroad Legends 2) *.GEO/*.SCENE.XML/*.MATERIAL.XML or *.GEO/*.H3D loader module and I have released the following programs as web updates:

- 3D Object Converter v7.047 (Windows)
- i3DConverter v3.905 (macOS)
- i3DConverter v1.905 (Linux)

How to get the 3D Object Converter v7.047:
Download the 3D Object Converter from http://3doc.i3dconverter.com and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.047.

How to get the i3DConverter v3.905 macOS:
Download the i3DConverter from http://www.i3dconverter.com and install it.
After it just use the Help/Check for updates... function to get the v3.905.

How to get the i3DConverter v1.905 Linux:
Download the i3DConverter from http://www.i3dconverter.com and install it.
After it just use the Help/Check for updates... function to get the v1.905.

UVs are messed up.


GEO: [https://www.mediafire.com/file/6ngoz3ei ... r.geo/file](https://www.mediafire.com/file/6ngoz3eiald1kvd/rally_car.geo/file)
H3D: [https://www.mediafire.com/file/k62t3cib ... r.h3d/file](https://www.mediafire.com/file/k62t3cibwdx6l95/rally_car.h3d/file)
Texture (converted): [https://cdn.discordapp.com/attachments/ ... s_diff.tga](https://cdn.discordapp.com/attachments/755131267179348132/834573118827397211/chassis_diff.tga)
## Post #45
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-04-22T17:37:46+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

I have modified the Horde3D .geo loader module to get the correct UV datas from the v6 .geo files.

After it I have released the following program as web updates:
    - 3D Object Converter v8.001 (Windows)

How to get the 3D Object Converter v8.001:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.001.




Horde_v6_geo.jpg (155.81 KiB) Viewed 39 times
## Post #46
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-25T05:05:16+00:00
- Post Title: Re: Offroad Legends GEO/H3D model file, convertor?

Thanks!
