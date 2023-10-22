## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-01T00:09:17+00:00
- Post Title: Cabal Online File Format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-01T12:31:10+00:00
- Post Title: Cabal Online File Format

umm yes I try rip this game before, and found some interesting things, the model and texture are attached into same file, anyway here some examples, you need something,  know where can found me 

PD: I attached .MAX and OBJ you want see.


[Cabal Testing Files.rar](https://xentaxbackup.github.io/file/4679_Cabal Testing Files.rar)
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-01T13:10:23+00:00
- Post Title: Cabal Online File Format

I didn't quite understand all you said but the tool that he made can load models, maps and animations. What I have seen all characters load ALL models in one pack so you manually have to delete everything you don't want to see
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-01T14:01:25+00:00
- Post Title: Cabal Online File Format

> Reply from pixellegolas
>
> I didn't quite understand all you said but the tool that he made can load models, maps and animations. What I have seen all characters load ALL models in one pack so you manually have to delete everything you don't want to seewhat tool you mean? about animations are not supported think, I read something but not sure about that

PD: I say before is the model+textures are in same file .EBM
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-01T17:50:41+00:00
- Post Title: Cabal Online File Format

.EBM files can be unpacked this its posible i remember with something blender script, now the .ebm files can be exported back to the game file format of course, i talk abouth .ech format, .ech format its the format of the armors and costumes stored in this files, i talk abouth maybe its posible first make a importer for .ech files then in the future make exporter.
## Post #6
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-09-02T11:31:35+00:00
- Post Title: Cabal Online File Format

For Bleder 2.46, copy and save as: ebm_import.py

```

# Copyright (c) 2007-2011 Randall Stevens
# 
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
# 
# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.
# 
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
# THE SOFTWARE.
#
# -----------------------------------------------------------------------------
#
# Version 0.0.1
#     * Initial release
#
# Version 0.0.2
#     * Fixed setting face mode to double sided
#     * Fixed mirroring the UV coordinates
#     * Fixed reading vertex influences
#     * Added setting material mode to texture face with alpha
#
# Version 0.0.3
#     * Fixed importing textures in Microsoft Windows
#
# Version 0.0.4
#     * Fixed armature edit bone matrix
#     * Added animation importing

"""
Name: 'CABAL (.ebm)...'
Blender: 246
Group: 'Import'
Tooltip: 'Import CABAL game (*.ebm) files'
"""

__author__ = 'Peter S. Stevens'
__email__ = 'pstevens:cryptomail*org'
__url__ = ('blender', 'elysiun', 'Project homepage, http://www.ragezone.com/')
__version__ = '0.0.4'
__bpydoc__ = """ \
This script imports CABAL game (*.ebm) files.
"""


import Blender
import struct
import tempfile
import math
import re


EBM_BONE_NAMES = []


LEFT_TO_RIGHT = Blender.Mathutils.Matrix([-1.0, 0.0, 0.0, 0.0],
                                         [0.0, 0.0, 1.0, 0.0],
                                         [0.0, 1.0, 0.0, 0.0],
                                         [0.0, 0.0, 0.0, 1.0])


class MagicError(ValueError):
    pass


def ebm_read_material(file_object):
    diffuse = struct.unpack('<4f', file_object.read(16))
    ambient = struct.unpack('<4f', file_object.read(16))
    specular = struct.unpack('<4f', file_object.read(16))
    emissive = struct.unpack('<4f', file_object.read(16))
    power = struct.unpack('<f', file_object.read(4))[0]
    
    material = Blender.Material.New()
    
    material.setRGBCol(diffuse[0:3])
    material.setAlpha(diffuse[3])
    material.setMirCol(ambient[0:3])
    material.setAmb(ambient[3])
    material.setSpecCol(specular[0:3])
    material.setSpec(power)
    material.setEmit(emissive[3])
    
    return material


def ebm_read_texture(file_object):
    name_length = struct.unpack('<H', file_object.read(2))[0]
    
    name = file_object.read(name_length)
    
    texture_data_size = struct.unpack('<I', file_object.read(4))[0]
    
    texture_data = file_object.read(texture_data_size)
    
    file_object.read(26) # ?, 00 00 00 00 00 00 00 00 00 FF FF FF FF 00 00 00 00 00 00 00 00 00 04 00 00 00 DXT3
    
    # Clean the file name
    rec = re.compile('[^\w\.]*')
    name = rec.sub('', name)
    # Create a temporary texture file
    texture_file = open(Blender.sys.join(tempfile.gettempdir(), name), 'wb')
    texture_file.write(texture_data)
    texture_file.close()
    
    texture = None
    
    try:
        texture = Blender.Texture.Get(name)
    except:
        texture = Blender.Texture.New(name)
        texture.setType('Image')
        
        image = None
        
        try:
            image = Blender.Image.Get(name)
        except:
            try:
                image = Blender.Image.Load(Blender.sys.join(tempfile.gettempdir(), name))
            except:
                raise
        finally:
            if image is not None:
                texture.setImage(image)
    
    return texture


def ebm_read_mesh(file_object, materials):
    name_length = struct.unpack('<H', file_object.read(2))[0]
    
    name = file_object.read(name_length)
    
    world_matrix = Blender.Mathutils.Matrix(struct.unpack('<4f', file_object.read(16)), \
                                            struct.unpack('<4f', file_object.read(16)), \
                                            struct.unpack('<4f', file_object.read(16)), \
                                            struct.unpack('<4f', file_object.read(16)))
    
    local_matrix = Blender.Mathutils.Matrix(struct.unpack('<4f', file_object.read(16)), \
                                            struct.unpack('<4f', file_object.read(16)), \
                                            struct.unpack('<4f', file_object.read(16)), \
                                            struct.unpack('<4f', file_object.read(16)))
    
    unknown_0 = struct.unpack('<I', file_object.read(4))[0] # 0xFFFFFF
    
    material_index = struct.unpack('<B', file_object.read(1))[0]
    
    vertex_count = struct.unpack('<H', file_object.read(2))[0]
    
    face_count = struct.unpack('<H', file_object.read(2))[0]
    
    if vertex_count == 0 or face_count == 0:
        return None
    
    mesh_object = Blender.Object.New('Mesh', name)
    
    mesh = mesh_object.getData(mesh = True)
    
    if mesh is None:
        mesh = Blender.Mesh.New(name)
        
        mesh_object.link(mesh)
    
    mesh.vertexUV = True
    
    material = materials[material_index]
    
    mesh.materials = [material]
    
    textures = material.getTextures()
    
    image = None
    
    if len(textures) > 0:
        texture = textures[0].tex
        
        image = texture.getImage()
    
    for x in xrange(vertex_count):
        position = Blender.Mathutils.Vector(struct.unpack('<3f', file_object.read(12)))
        normal = Blender.Mathutils.Vector(struct.unpack('<3f', file_object.read(12)))
        uv = Blender.Mathutils.Vector(struct.unpack('<2f', file_object.read(8)))
        
        mesh.verts.extend(position)
        
        vertex = mesh.verts[-1]
        vertex.no = normal
        vertex.uvco = uv
        vertex.uvco[1] = 1.0 - vertex.uvco[1]
    
    for x in xrange(face_count):
        mesh.faces.extend([mesh.verts[y] for y in struct.unpack('<3H', file_object.read(6))])
        
        face = mesh.faces[-1]
        face.uv = [vertex.uvco for vertex in face.verts]
        
        if image is not None:
            face.mode = Blender.Mesh.FaceModes.TEX + Blender.Mesh.FaceModes.TWOSIDE
            face.image = image
    
    mesh.faceUV = True
    
    mesh_object.setMatrix(LEFT_TO_RIGHT) # mesh_object.setMatrix(world_matrix)
    
    return mesh_object


def ebm_read_influence(file_object, mesh, armatures):
    armature_object = armatures[-1]
    
    mesh_object = mesh
    
    armature_object.makeParent([mesh_object])
    
    armature_modifier = mesh_object.modifiers.append(Blender.Modifier.Types.ARMATURE)
    armature_modifier[Blender.Modifier.Settings.OBJECT] = armature_object
    
    armature = armature_object.getData()
    
    mesh = mesh_object.getData(mesh = True)
    
    for x in xrange(0, len(EBM_BONE_NAMES)):
        vertex_influences_count = struct.unpack('<I', file_object.read(4))[0]
        
        group_id = EBM_BONE_NAMES[x]
        
        mesh.addVertGroup(group_id)
        
        if vertex_influences_count != 0:
            vertex_influences = []
            
            for y in xrange(vertex_influences_count):
                vertex_index = struct.unpack('<I', file_object.read(4))[0]
                vertex_influences.append(vertex_index)
            
            for y in xrange(vertex_influences_count):
                vertex_weight = struct.unpack('<f', file_object.read(4))[0]
                mesh.assignVertsToGroup(group_id, \
                                        [vertex_influences[y]], \
                                        vertex_weight, \
                                        Blender.Mesh.AssignModes.ADD)
#        else: # problems on bike_10, comment out
#                mesh.assignVertsToGroup(group_id, \
#                                        [vertex.index for vertex in mesh.verts], \
#                                        1.0, \
#                                        Blender.Mesh.AssignModes.ADD)


def ebm_read_bone(file_object, bones):
    global EBM_BONE_NAMES
    
    name_length = struct.unpack('<H', file_object.read(2))[0]
    
    name = file_object.read(name_length)
    
    parent_bone_index = struct.unpack('<I', file_object.read(4))[0]
    
    armature_space_matrix = Blender.Mathutils.Matrix(struct.unpack('<4f', file_object.read(16)), \
                                                     struct.unpack('<4f', file_object.read(16)), \
                                                     struct.unpack('<4f', file_object.read(16)), \
                                                     struct.unpack('<4f', file_object.read(16)))
    
    parent_armature_space_matrix = Blender.Mathutils.Matrix(struct.unpack('<4f', file_object.read(16)), \
                                                            struct.unpack('<4f', file_object.read(16)), \
                                                            struct.unpack('<4f', file_object.read(16)), \
                                                            struct.unpack('<4f', file_object.read(16)))
    
    armature_space_matrix.invert()
    
    edit_bone = Blender.Armature.Editbone()
    
    edit_bone.name = name
    
    edit_bone.matrix = armature_space_matrix

    if parent_bone_index != 0xFFFFFFFF:
        edit_bone.parent = bones[parent_bone_index]
    
    bones.append(edit_bone)
    
    EBM_BONE_NAMES.append(name)
    
    return edit_bone


def ebm_read_animation(file_object, magic, armatures):
    name_length = struct.unpack('<H', file_object.read(2))[0]
    
    name = file_object.read(name_length)
    
    armature_object = armatures[-1]#EBM_ARMATURES[-1]
    
    armature = armature_object.getData()
    
    action = Blender.Armature.NLA.NewAction(name)
    action.setActive(armature_object)
    
#    ipo = Blender.Ipo.New('Object', name)
    
    armature_pose = armature_object.getPose()
    
    armature_pose_bones = armature_pose.bones
    
    bone_count = struct.unpack('<H', file_object.read(2))[0]
    
    for x in xrange(bone_count):
        bone_name_length = struct.unpack('<H', file_object.read(2))[0]
        
        bone_name = file_object.read(bone_name_length)
        
        translation_count = struct.unpack('<I', file_object.read(4))[0]
        
        key_frames = {}
        
        for y in xrange(translation_count):
            key_frame_second = struct.unpack('<f', file_object.read(4))[0]
            
            x, y, z = struct.unpack('<3f', file_object.read(12))
            
            key_frame_index = int(math.floor(key_frame_second * 100))
            
            if key_frame_index < 1:
                key_frame_index = 1
            
            translation = Blender.Mathutils.Vector(x, y, z)
            
            key_frames[key_frame_index] = Blender.Mathutils.TranslationMatrix(translation)
        
        rotation_count = struct.unpack('<I', file_object.read(4))[0]
        
        for y in xrange(rotation_count):
            key_frame_second = struct.unpack('<f', file_object.read(4))[0]
            
            x, y, z, w = struct.unpack('<4f', file_object.read(16))
            
            key_frame_index = int(math.floor(key_frame_second * 100))
            
            if key_frame_index < 1:
                key_frame_index = 1
            
            xx = x * x
            xy = x * y
            xz = x * z
            xw = x * w
            
            yy = y * y
            yz = y * z
            yw = y * w
            
            zz = z * z
            zw = z * w
            
            rotation_matrix = Blender.Mathutils.Matrix([1.0 - 2.0 * (yy + zz), 2.0 * (xy - zw), 2.0 * (xz + yw), 0.0], \
                                                       [2.0 * (xy + zw), 1.0 - 2.0 * (xx + zz), 2.0 * (yz - xw), 0.0], \
                                                       [2.0 * (xz - yw), 2.0 * (yz + xw), 1.0 - 2.0 * (xx + yy), 0.0], \
                                                       [0.0, 0.0, 0.0, 1.0])
            
            if key_frame_index in key_frames:
                key_frames[key_frame_index] = rotation_matrix * key_frames[key_frame_index]
            else:
                bone = armature.bones[bone_name]
                
                rest_bone_matrix = bone.matrix['ARMATURESPACE'].copy()
                
                if bone.parent is not None:
                    parent_bone = bone.parent
                    
                    parent_rest_bone_matrix = parent_bone.matrix['ARMATURESPACE'].copy()
                    
                    parent_rest_bone_matrix.invert()
                    
                    rest_bone_matrix *= parent_rest_bone_matrix
                
                translation = rest_bone_matrix.translationPart()
                
                translation_matrix = Blender.Mathutils.TranslationMatrix(translation)
                
                key_frames[key_frame_index] = rotation_matrix * translation_matrix
        
        if bone_name in armature.bones.keys():
            for key_frame_index, key_frame_transformation in key_frames.iteritems():
                local_matrix = key_frame_transformation.copy()
                
                bone = armature.bones[bone_name]
                
                rest_bone_matrix = bone.matrix['ARMATURESPACE'].copy()
                
                if bone.parent is not None and magic != 0x3EF03:
                    parent_bone = bone.parent
                    
                    parent_rest_bone_matrix = parent_bone.matrix['ARMATURESPACE'].copy()
                    
                    parent_rest_bone_matrix.invert()
                    
                    local_matrix *= (rest_bone_matrix * parent_rest_bone_matrix).invert()
                else:
                    rest_bone_matrix.invert()
                    
                    local_matrix *= rest_bone_matrix
                
                armature_pose_bones[bone_name].localMatrix = local_matrix
                armature_pose_bones[bone_name].insertKey(armature_object, key_frame_index, [Blender.Object.Pose.ROT, Blender.Object.Pose.LOC])
#        else:
#            mesh_object = Blender.Object.Get(bone_name)
#            
#            mesh_object.setIpo(ipo)
#            
#            for key_frame_index, key_frame_transformation in key_frames.iteritems():
#                Blender.Set("curframe", key_frame_index)
#                
#                mesh_object.setMatrix(key_frame_transformation)
#                
#                mesh_object.insertIpoKey(Blender.Object.LOCROT)
#            
#            Blender.Set("curframe", 1)
    
    armature_pose.update()


def ebm_read_material_chunk(file_object, materials):
    material_count = struct.unpack('<H', file_object.read(2))[0]
    
    for x in xrange(material_count):
        material = ebm_read_material(file_object)
        texture = ebm_read_texture(file_object)
        
        if texture is not None:
            material.setTexture(0, texture, Blender.Texture.TexCo.UV)
            material.setMode(Blender.Material.Modes.TEXFACE + Blender.Material.Modes.TEXFACE_ALPHA)
        
        materials.append(material)


def ebm_read_influence_chunk(file_object, mesh, armatures):
    influence_count = struct.unpack('<H', file_object.read(2))[0]
    
    for x in xrange(influence_count):
        ebm_read_influence(file_object, mesh, armatures)


def ebm_read_mesh_chunk(file_object, materials, meshes, armatures):
    mesh_count = struct.unpack('<H', file_object.read(2))[0]
    
    for x in xrange(mesh_count):
        mesh_object = ebm_read_mesh(file_object, materials)
        
        if mesh_object is not None:
            chunk_id = struct.unpack('<I', file_object.read(4))[0]
            
            if chunk_id == 0x41470205:
                ebm_read_influence_chunk(file_object, mesh_object, armatures)
            else: # WTF? fix...
                file_object.seek(-5, os.SEEK_CUR)
            
            meshes.append(mesh_object)


def ebm_read_armature_chunk(file_object):
    bone_count = struct.unpack('<H', file_object.read(2))[0]
    
    armature_object = Blender.Object.New('Armature')
    
    armature_object.drawMode = Blender.Object.DrawModes.XRAY
    
    armature = armature_object.getData()
    
    if armature is None:
        base_name = Blender.sys.basename(file_object.name)
        
        armature_name = Blender.sys.splitext(base_name)[0]
        
        armature = Blender.Armature.New(armature_name)
        
        armature_object.link(armature)
    
    armature.drawType = Blender.Armature.STICK
    armature.envelopes = False
    armature.vertexGroups = True
    
    armature.makeEditable()
    
    bones = []
    
    for x in xrange(bone_count):
        edit_bone = ebm_read_bone(file_object, bones)
        
        armature.bones[edit_bone.name] = edit_bone
    
    armature_object.setMatrix(LEFT_TO_RIGHT)
    
    armature.update()
    
    return armature_object


def ebm_read_animation_chunk(file_object, magic, armatures):
    animation_count = struct.unpack('<H', file_object.read(2))[0]
    
    for x in xrange(animation_count):
        ebm_read_animation(file_object, magic, armatures)


def ebm_import(file_path):
    file_object = None
    
    materials = []
    meshes = []
    armatures = []
    
    try:
        Blender.Window.WaitCursor(1)
        
        file_object = open(file_path, 'rb')
        
        magic = struct.unpack('<I', file_object.read(4))[0]
        
        if magic != 0x3ED03 and \
           magic != 0x3EE03 and \
           magic != 0x3EF03:
            raise MagicError, "Bad magic number, %08x" % magic
        
        print hex(magic)
        
        unknown_0 = struct.unpack('<H', file_object.read(2))[0] # 0x100 (256)
        
        unknown_1 = struct.unpack('<I', file_object.read(4))[0] # ?
        
        bounding_box_min = Blender.Mathutils.Vector(struct.unpack('<3f', file_object.read(12)))
        
        bounding_box_max = Blender.Mathutils.Vector(struct.unpack('<3f', file_object.read(12)))
        
        unknown_2 = struct.unpack('<I', file_object.read(4))[0] # 0x64 (100)
        
        while True:
            data = file_object.read(4)
            
            if len(data) == 0: # Clean break
                break
            
            chunk_id = struct.unpack('<I', data)[0]
            
            if chunk_id == 0x41470201:
                ebm_read_material_chunk(file_object, materials)
                continue
            
            if chunk_id == 0x41470202:
                ebm_read_mesh_chunk(file_object, materials, meshes, armatures)
                continue
            
            if chunk_id == 0x41470203:
                armature_object = ebm_read_armature_chunk(file_object)
                
                armatures.append(armature_object)
                continue
            
            if chunk_id == 0x41470204:
                ebm_read_animation_chunk(file_object, magic, armatures)
                continue
    except IOError:
        raise
    else:
        scene = Blender.Scene.GetCurrent()
        
        for mesh_object in meshes:
            scene.objects.link(mesh_object)
        
        for armature_object in armatures:
            scene.objects.link(armature_object)
    finally:
        if file_object is not None:
            file_object.close()
        
        Blender.Window.WaitCursor(0)


def main():
    def ebm_file_selector(file_path):
        if file_path and \
           not Blender.sys.exists(file_path):
            Blender.Draw.PupMenu("Warning%%t|The file %s does not exist." % file_path)
        else:
            ebm_import(file_path)
    
    Blender.Window.FileSelector(ebm_file_selector, 'Ok', Blender.sys.makename(ext='.ebm'))


if __name__ == "__main__":
    main()

```


Source:
[http://forum.ragezone.com/f458/ebm-blen ... er-449555/](http://forum.ragezone.com/f458/ebm-blender-importer-449555/)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-02T13:29:28+00:00
- Post Title: Cabal Online File Format

> Reply from Rimbros
>
> .EBM files can be unpacked this its posible i remember with something blender script, now the .ebm files can be exported back to the game file format of course, i talk abouth .ech format, .ech format its the format of the armors and costumes stored in this files, i talk abouth maybe its posible first make a importer for .ech files then in the future make exporter.

If textures are stored as part of the format, it is most likely stored at a specific offset or the offset is referenced by some material or mesh.

I would handle it the same way the blender script does it so people don't have to unpack it.
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-02T15:02:44+00:00
- Post Title: Cabal Online File Format

> * Added animation importing

I remember opening up model files. All the characters where at origin and I had to manually delete costumes untill I found witch one I wanted, very heavy files because all was loaded. But costumes, animations and everything loaded.

The script is from ragezone forum and will probably not be updated any more. The guy has done some other importers for perfect world etc
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-09-02T17:40:30+00:00
- Post Title: Cabal Online File Format

> I would handle it the same way the blender script does it so people don't have to unpack it.

You can extract the .dds files using this very useful utility:
[http://wiki.xentax.com/index.php/Extrac ... e_Stripper](http://wiki.xentax.com/index.php/Extraction_tools#File_Stripper)
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-02T18:02:43+00:00
- Post Title: Cabal Online File Format

> Reply from Karpati
>
> I would handle it the same way the blender script does it so people don't have to unpack it.

You can extract the .dds files using this very useful utility:
http://wiki.xentax.com/index.php/Extrac ... e_Strippereasy using bms script like this.

```
findloc RES_START string "X9´;"
goto RES_START
savepos RES_START
math FILES += 0xFFF

for i = 0 < FILES
getdstring NULL1 0x14
get NSIZE short
getdstring NAME NSIZE
get SIZE long
savepos OFFSET
log NAME OFFSET SIZE
math RES_START += SIZE
goto RES_START
findloc RES_START string "X9´;"
goto RES_START

next i
```
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-02T22:57:18+00:00
- Post Title: Cabal Online File Format

> Reply from pixellegolas
>
> * Added animation importing

I remember opening up model files. All the characters where at origin and I had to manually delete costumes untill I found witch one I wanted, very heavy files because all was loaded. But costumes, animations and everything loaded.

The script is from ragezone forum and will probably not be updated any more. The guy has done some other importers for perfect world etc

The guy its phantom a genius of 3D file formats encrypted like the guys here in xentax, but he leave the forums long time ago.
## Post #12
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-09-03T10:24:29+00:00
- Post Title: Cabal Online File Format

For 3dmax?
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-09-03T12:22:47+00:00
- Post Title: Cabal Online File Format

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-03T13:19:25+00:00
- Post Title: Cabal Online File Format

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-03T16:31:23+00:00
- Post Title: Cabal Online File Format

Alright, more blender script to reference with
## Post #16
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-07T17:39:53+00:00
- Post Title: Re: Cabal Online File Format

The point and the Imposible its since this game its in the Network nowhere can make a importer for .ECH files, this have all the armors stored on this format.
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-07T17:50:23+00:00
- Post Title: Re: Cabal Online File Format

> Reply from Rimbros
>
> The point and the Imposible its since this game its in the Network nowhere can make a importer for .ECH files, this have all the armors stored on this format.well yes but maybe with structure of the file maybe can help with that, I leave here and maybe someone can try.
[Cabal EBM-ECH Structure.rar](https://xentaxbackup.github.io/file/4693_Cabal EBM-ECH Structure.rar)
## Post #18
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-21T08:29:34+00:00
- Post Title: Re: Cabal Online File Format

Finally i understand nobody can keep out the models in .ech files, i am the only no leave this project, and.....   
T pose models ripped out can be possible with gameassassin Tool. Dont Ask by bones or animations.



This dont look like ¨T¨ its more like ¨I¨ Pose.
## Post #19
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-21T13:16:52+00:00
- Post Title: Re: Cabal Online File Format

good job my friend, I am happy to continue with that, the truth is one of the few who remain with the project.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-22T04:00:11+00:00
- Post Title: Re: Cabal Online File Format

Looks a little weird though, like he's stretched too much lol
## Post #21
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-09T23:44:21+00:00
- Post Title: Re: Cabal Online File Format

> Reply from finale00
>
> Looks a little weird though, like he's stretched too much lol

Yep, now i understand one think, .ECH files are containers and have something armors in each file, hope aluigui can made a bms script to keep out the files stored on this format, and u can take a view now with your new amazing skills, i remember you made the first post abouth this game and format years ago.
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T01:30:12+00:00
- Post Title: Re: Cabal Online File Format

Do the existing scripts support ECH? Or are they all EBM?
## Post #23
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-10T02:14:45+00:00
- Post Title: Re: Cabal Online File Format

> Reply from finale00
>
> Do the existing scripts support ECH? Or are they all EBM?the script exist is for EMB.

EBM Script

```
findloc RES_START string "X9?"
goto RES_START
savepos RES_START
math FILES += 0xFFF

for i = 0 < FILES
getdstring NULL1 0x14
get NSIZE short
getdstring NAME NSIZE
get SIZE long
savepos OFFSET
log NAME OFFSET SIZE
math RES_START += SIZE
goto RES_START
findloc RES_START string "X9?"
goto RES_START

next i
```


ECH Script (Waiting)
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T02:53:38+00:00
- Post Title: Re: Cabal Online File Format

Ok so an EBM file contains multiple meshes, presumably related (like all of a character's armor, etc).
ECH can probably just be parsed the same way.

I can look into it, but I've got several papers to write so maybe on sunday lol
## Post #25
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-10T03:31:21+00:00
- Post Title: Re: Cabal Online File Format

> Reply from finale00
>
> Ok so an EBM file contains multiple meshes, presumably related (like all of a character's armor, etc).
ECH can probably just be parsed the same way.

I can look into it, but I've got several papers to write so maybe on sunday lolgood to hear that my friend, but all in good time, one by one, I think that you should first focus on a single, once what he wanted out because it can proceed to the next, I speak from experience of work is not ripping games, but 3D modeling, graphic design, because it does not end and neither half is all, is only a recommendation not get me wrong.
## Post #26
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T05:50:58+00:00
- Post Title: Re: Cabal Online File Format

I don't see much of a point in just getting one mesh.
Unless you mean he is going to add it to a different game.
## Post #27
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-10T07:24:06+00:00
- Post Title: Re: Cabal Online File Format

Time ago yamachi made someting editor of textures and other thinks for cabal, btw he made a tool to made new weapons for cabal and expor from obj to ebm format, but he never made exporter for armors coz same he tell, armors are in .ech file an ech file its a container.
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T08:50:49+00:00
- Post Title: Re: Cabal Online File Format

I re-wrote the ebm importer in noesis cause I already had a plugin script for Sanae3D.
I opened ech and found that it's the same as the ebm format.

Ok, so I just added ".ech" to the plugin and it loaded up the models as expected.
And of course, I see that there are potentially dozens of armors in a single file.

Splitting it up becomes quite difficult for several reasons

1: It's the same as the ebm format. It defines all of the materials (could be 3, could be 20, could be 200), followed by all the textures, followed by bones, mesh, animation, etc.

2: You probably realized that all of the models use a base body, with just different meshes for the clothes (and consequently different material). 

3: That blender script that has "selected meshes" feature. Does it work? Cause ech is no different from ebm.

[http://db.tt/LSkR0GTc](http://db.tt/LSkR0GTc)

Though the format is pretty much given, I still didn't load the animations/skeleton. Someone can always add it though..

Though I did find a couple ebm's that had different chunks and idstring...kind of weird. I'm not going to care much about it though. It's Object\Object\fearofd\fearofd_z2_fx_sand.ebm if anyone's interested.
## Post #29
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-11T17:00:17+00:00
- Post Title: Re: Cabal Online File Format

simply amazing   , thanks finally finale made the script for Noesis, of course like i said ech its multi-object container, 



and btw this have a trouble... the .py script load the whole .ech file and the problem its this, each armor have around 5 parts, if u export the .each file to every format you like you get this 5 parts are atached in 1 single object, then you not lose only the cuts, you lost also the maping.



Really hope finale u can fix this bro. cheers.
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T18:23:02+00:00
- Post Title: Re: Cabal Online File Format

Hmm that's interesting.
Anyways I'll look into loading them as separate models so you can just scroll through them.

Does it matter whether a single model is a full set (body, legs, arms, etc) or not?
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-11T18:37:22+00:00
- Post Title: Re: Cabal Online File Format

> Reply from finale00
>
> Hmm that's interesting.
Anyways I'll look into loading them as separate models so you can just scroll through them.

Does it matter whether a single model is a full set (body, legs, arms, etc) or not?

You remember the one i rip from gameassain the one looks like he's stretched too much, well if u can see this looks fine, and have 5 parts, pants, legs, head, chest and gloves, this model have 3 textures.
This...


The same model exported from Noesis have all the parts body, legs, arms, etc but its only a single model and coz this the model load one texture and looks wrong.

In the gameassing file he ripped separated, single model its a chest or boot or helm, not all the body.

btw i see something models like boots or gloves are riped out fine, separated u can see in the screen with wrong texture message.
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T18:48:10+00:00
- Post Title: Re: Cabal Online File Format

Ya it looked a little odd to me I wasn't sure what the problem was.
Maybe just a small bug. I don't have ech files on me right now so I'll look at it tomorrow or next week.
## Post #33
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-11T19:55:41+00:00
- Post Title: Re: Cabal Online File Format

[http://www.mediafire.com/?cclwzp7v0p3suaa](http://www.mediafire.com/?cclwzp7v0p3suaa)

Link for .ech files.
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T21:13:19+00:00
- Post Title: Re: Cabal Online File Format

Each outfit comes in sets.
So the torso/arms/legs/hat/etc is a single mesh.

Once I see what the issue is with [this problem](http://forum.xentax.com/viewtopic.php?p=66775#p66775) the export problem should be fixed.

The textures look kind of weird though, like they are sort of transparent. Why does it look like that?



They also look quite stiff lol
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-11T21:30:31+00:00
- Post Title: Re: Cabal Online File Format

that issue normally happens when they store a spec map in the alpha channel.
## Post #36
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T21:47:35+00:00
- Post Title: Re: Cabal Online File Format

Hmm, hopefully it isn't too much of an issue if I disable default blend in the script (using material.setDefaultBlend(0))

I'm sure after export it can be edited appropriately.
## Post #37
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-12T07:20:23+00:00
- Post Title: Re: Cabal Online File Format

All this outfits u post bro its a single model, but maybe u can take a view of this outfits.

[http://www.4shared.com/rar/BPmJnNII/Character.html](http://www.4shared.com/rar/BPmJnNII/Character.html)

This its the preview of Noesis, only in the cape u can see the Texture are Wrong asigned.



Hope u can found a solution bro, cheers.
## Post #38
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T08:07:14+00:00
- Post Title: Re: Cabal Online File Format

I was experimenting with loading each mesh as a separate model.
But I haven't found a good way to do it yet.
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T05:18:16+00:00
- Post Title: Re: Cabal Online File Format

Script updated.

I found that rpgReset() seems to do the job.
Everytime I finish constructing a model I should reset the context for the next one.

I'm not entirely sure what the context is, but it looks like it keeps previous bindings there even though I clearBufferBinds()

Now it should load all of the meshes into separate models.

Problem is...not all of the meshes are full sets lol. I'll probably have to figure out a way to selectively determine how many meshes form a particular set.

Anyways at least they're separated for now.
## Post #40
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-19T06:21:35+00:00
- Post Title: Re: Cabal Online File Format

WTF, wath its that butom to changue from one model to other?  , first time i see this in Noesis, amazing job finale, thanks so much.
