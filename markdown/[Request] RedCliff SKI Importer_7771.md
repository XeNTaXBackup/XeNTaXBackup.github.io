## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-11-29T18:12:01+00:00
- Post Title: [Request] RedCliff SKI Importer

Hello to all, well today I rip models of RedCliff game, the game use same format Perfect World, Jade Dynasty,etc anyway I try using the python importer of PW but fail when importer it, the error in console is:

Bone01
Bone02

here I leave script, maybe someone can give me a hand or make a maxscript better 

```

# Copyright (c) 2008 Peter S. Stevens
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


"""
Name: 'Perfect World (*.ski)...'
Blender: 246
Group: 'Import'
Tooltip: 'Import Perfect World *.ski game files'
"""

__author__ = 'Peter S. Stevens'
__email__ = 'pstevens:cryptomail*org'
__url__ = ('blender', 'elysiun', 'Project homepage, http://www.ragezone.com/')
__version__ = '08.12.0a'
__bpydoc__ = """ \
This script imports Perfect World *.ski game files
"""


import Blender
import struct


def pw_ski_read_texture(file_object):
    file_name_length = struct.unpack('<I', file_object.read(4))[0]
    
    file_name = file_object.read(file_name_length)
    
    texture = None
    
    print file_name
    
    try:
        texture = Blender.Texture.Get(file_name)
    except:
        texture = Blender.Texture.New(file_name)
        
        texture.setType('Image')
        
        image = None
        
        try:
            file_path = Blender.sys.dirname(file_object.name)
            file_path = Blender.sys.join(search_path, file_name)
            
            print file_path
            
            image = Blender.Image.Get(file_path)
        except:
            pass
        finally:
            if image is not None:
                texture.setImage(image)
    
    return texture


def pw_ski_read_material(file_object, texture_objects):
    material_type = file_object.read(11)
    
    file_object.seek(68, 1)
    
    texture_index = struct.unpack('<B', file_object.read(1))[0]
    
    material = Blender.Material.New()
    
    if texture_index < len(texture_objects):
        material.setTexture(0, texture_objects[texture_index], Blender.Texture.TexCo.UV)
        
        material.setMode(Blender.Material.Modes.TEXFACE + Blender.Material.Modes.TEXFACE_ALPHA)
    
    return material


def pw_ski_read_mesh(file_object, vertex_type, material_objects):
    name_length = struct.unpack('<I', file_object.read(4))[0]
    
    name = file_object.read(name_length)
    
    index = struct.unpack('<I', file_object.read(4))[0]
    
    material_index = struct.unpack('<I', file_object.read(4))[0]
    
    if vertex_type == 1:
        file_object.seek(4, 1)
    
    vertex_count = struct.unpack('<I', file_object.read(4))[0]
    
    index_count = struct.unpack('<I', file_object.read(4))[0]
    
    mesh_object = Blender.Object.New('Mesh', name)
    
    mesh = mesh_object.getData(mesh = True)
    
    if mesh is None:
        mesh = Blender.Mesh.New(name)
        
        mesh_object.link(mesh)
    
    mesh.vertexUV = True
    
    for x in xrange(vertex_count):
        position = Blender.Mathutils.Vector(struct.unpack('<3f', file_object.read(12)))
        
        if vertex_type == 0:
            file_object.seek(16, 1)
        
        normal = Blender.Mathutils.Vector(struct.unpack('<3f', file_object.read(12)))
        
        uv_coordinates = Blender.Mathutils.Vector(struct.unpack('<2f', file_object.read(8)))
        
        mesh.verts.extend(position)
        
        vertex = mesh.verts[-1]
        
        vertex.no = normal
        
        vertex.uvco = uv_coordinates
        vertex.uvco[1] = 1.0 - vertex.uvco[1]
    
    for x in xrange(index_count / 3):
        face_vertices = [mesh.verts[y] for y in struct.unpack('<3H', file_object.read(6))]
        
        mesh.faces.extend(face_vertices)
        
        face = mesh.faces[-1]
        
        face.uv = [vertex.uvco for vertex in face_vertices]
    
    if material_index < len(material_objects):
        material = material_objects[material_index]
        
        mesh.materials = [material]
        
        textures = material.getTextures()
        
        if textures[0] is not None:
            texture = textures[0].tex
            
            image = texture.getImage()
            
            for face in mesh.faces:
                face.mode = Blender.Mesh.FaceModes.TEX + Blender.Mesh.FaceModes.TWOSIDE
                face.image = image
    
    return mesh_object


def pw_ski_read(file_path):
    file_object = None
    
    try:
        file_object = open(file_path, 'rb')
        
        moxbiksa = file_object.read(8) # a ski bmox
        
        unknown_0 = struct.unpack('<I', file_object.read(4))[0]
        
        vertex_type_count = struct.unpack('<4I', file_object.read(16))
        
        texture_count = struct.unpack('<I', file_object.read(4))[0]
        
        material_count = struct.unpack('<I', file_object.read(4))[0]
        
        unknown_1 = struct.unpack('<I', file_object.read(4))[0] # always 4
        
        unknown_2 = struct.unpack('<I', file_object.read(4))[0]
        
        unknown_3 = struct.unpack('<I', file_object.read(4))[0] # ?
        
        file_object.seek(60, 1)
        
        texture_objects = []
        
        for x in xrange(texture_count):
            texture_objects.append(pw_ski_read_texture(file_object))
        
        material_objects = []
        
        for x in xrange(material_count):
            material_objects.append(pw_ski_read_material(file_object, texture_objects))
        
        mesh_objects = []
        
        for vertex_type, vertex_count in enumerate(vertex_type_count):
            for x in xrange(vertex_count):
                mesh_objects.append(pw_ski_read_mesh(file_object, vertex_type, material_objects))
        
        scene = Blender.Scene.GetCurrent()
        
        for mesh_object in mesh_objects:
            scene.objects.link(mesh_object)
    except IOError, (errno, strerror):
        Blender.Draw.PupMenu("Error%%t|I/O error(%d): %s." % (errno, strerror))
    except Exception, err:
        Blender.Draw.PupMenu("Error%%t|.%s" % err)
    finally:
        if file_object is not None:
            file_object.close()


def main():
    def pw_file_selector(file_path):
        if file_path and not Blender.sys.exists(file_path):
            Blender.Draw.PupMenu("Error%%t|The file %s does not exist." % file_path)
        else:
            pw_ski_read(file_path)
    
    Blender.Window.FileSelector(pw_file_selector, 'Ok', Blender.sys.makename(ext='.ski'))


if __name__ == "__main__":
    main()


```
