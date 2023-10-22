## Post #1
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2014-02-10T12:06:29+00:00
- Post Title: [REQUEST] Dekaron/2moons model exporter/importer

i am searching for someone who can help me get a script for Dekaron/2moons from gamehi its a MMORPG game .. 

someone released a importer on blender using python lang and its like 90% finished .. and it works great ..
but now i am searching for exporter so i can export this models and use them on the game 

if someone needs the python importer script to blender i can post it here

i can upload some unpacked models from the game too if that helps somehow

i dont know if i am allowed to post the game url here but u can pm me so i can give u the game url or upload any file that helps

PS # : i can offer money if its kinda hard to make this script and u dont wanna make it free for me ...

i dont want this script to go public i want it private so PM ME if you can help me ...

thanks
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-10T14:58:33+00:00
- Post Title: [REQUEST] Dekaron/2moons model exporter/importer

> Reply from lol2k12
>
> i am searching for someone who can help me get a script for Dekaron/2moons from gamehi its a MMORPG game .. 

someone released a importer on blender using python lang and its like 90% finished .. and it works great ..
but now i am searching for exporter so i can export this models and use them on the game 

if someone needs the python importer script to blender i can post it here

i can upload some unpacked models from the game too if that helps somehow

i dont know if i am allowed to post the game url here but u can pm me so i can give u the game url or upload any file that helps

PS # : i can offer money if its kinda hard to make this script and u dont wanna make it free for me ...

i dont want this script to go public i want it private so PM ME if you can help me ...

thanks

You could atleast just share the currently released import script. I dislike how you are hesitant to do so. Also, the fact you want an exporter to be private is just selfish. I believe we're a community that believes in sharing with one and another so it's unlikely someone is just going to make you a free model exporter script for your own personal use, maybe for everyone else but you can't ask someone to make something which requires time and effort so it doesn't get released, it's not fair and is plain selfish. Why would someone go into all the trouble of that only to have it used by you, it's not very likely. They may as well just make it from themself and be selfish, how would you feel?

If it weren't for people who are not selfish and good hearted. For example, the guy who released the blender import script as you said.... 

The world would be a very selfish place....
Just my thoughts.
Cheers.
## Post #3
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2014-02-11T12:10:50+00:00
- Post Title: [REQUEST] Dekaron/2moons model exporter/importer

> Reply from Gh0stBlade
>
> lol2k12 wrote:i am searching for someone who can help me get a script for Dekaron/2moons from gamehi its a MMORPG game .. 

someone released a importer on blender using python lang and its like 90% finished .. and it works great ..
but now i am searching for exporter so i can export this models and use them on the game 

if someone needs the python importer script to blender i can post it here

i can upload some unpacked models from the game too if that helps somehow

i dont know if i am allowed to post the game url here but u can pm me so i can give u the game url or upload any file that helps

PS # : i can offer money if its kinda hard to make this script and u dont wanna make it free for me ...

i dont want this script to go public i want it private so PM ME if you can help me ...

thanks

You could atleast just share the currently released import script. I dislike how you are hesitant to do so. Also, the fact you want an exporter to be private is just selfish. I believe we're a community that believes in sharing with one and another so it's unlikely someone is just going to make you a free model exporter script for your own personal use, maybe for everyone else but you can't ask someone to make something which requires time and effort so it doesn't get released, it's not fair and is plain selfish. Why would someone go into all the trouble of that only to have it used by you, it's not very likely. They may as well just make it from themself and be selfish, how would you feel?

If it weren't for people who are not selfish and good hearted. For example, the guy who released the blender import script as you said.... 

The world would be a very selfish place....
Just my thoughts.
Cheers.

the guy who released the import script was working on 2moons official sever and after it closed he released it ..
second reason is i said that i will pay money for that .. why do i have to pay money by my self then share it for public ? thats unfair too .. i dont ask for free (but if the helper wants to help me and make it free just for fun or something)

thats wt i am trying to say .. and the dekaron import script is already here somewere on a post on the forums .. the import script is not private anymore ... 

still waiting for someone to help i really need this script .


This script works only with Blender 2.5 Alpha 0 and Python 3.1.x

here's the script :

> # Copyright (c) 2009-2012 AJ
>
> # 
>
> # Permission is hereby granted, free of charge, to any person obtaining a copy
>
> # of this software and associated documentation files (the "Software"), to deal
>
> # in the Software without restriction, including without limitation the rights
>
> # to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
>
> # copies of the Software, and to permit persons to whom the Software is
>
> # furnished to do so, subject to the following conditions:
>
> # 
>
> # The above copyright notice and this permission notice shall be included in
>
> # all copies or substantial portions of the Software.
>
> # 
>
> # THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
>
> # IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
>
> # FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
>
> # AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
>
> # LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
>
> # OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
>
> # THE SOFTWARE.
>
> #
>
> # Version 0.0.1
>
> #     * Initial release
>
> 
>
> __author__ = 'AJ'
>
> __email__ = ''
>
> __url__ = ('blender', 'elysiun', 'Project homepage, http://www.ragezone.com/')
>
> __version__ = '0.0.1'
>
> __bpydoc__ = ''' \
>
> Import Dekaron mesh files
>
> '''
>
> 
>
> 
>
> import bpy
>
> import dynamic_menu
>
> import io
>
> import os
>
> import struct
>
> 
>
> 
>
> def create_dekaron_mesh(dekaron_mesh_name, dekaron_mesh_vertices_co, dekaron_mesh_vertices_uv, dekaron_mesh_indices):
>
>     dekaron_mesh = bpy.data.add_mesh(dekaron_mesh_name)
>
> 
>
>     dekaron_mesh.add_geometry(int(len(dekaron_mesh_vertices_co) / 3), 0, int(len(dekaron_mesh_indices) / 4))
>
> 
>
>     dekaron_mesh.verts.foreach_set("co", dekaron_mesh_vertices_co)
>
> 
>
>     dekaron_mesh.faces.foreach_set("verts_raw", dekaron_mesh_indices)
>
> 
>
>     if dekaron_mesh.faces is not None and \
>
>        dekaron_mesh_vertices_uv is not None and \
>
>        len(dekaron_mesh_vertices_uv) > 0:
>
>         dekaron_mesh.add_uv_texture()
>
> 
>
>         for i, dekaron_mesh_face in enumerate(dekaron_mesh.faces):
>
>             dekaron_mesh_texture_face = dekaron_mesh.uv_textures[0].data
>
> 
>
>             dekaron_mesh_texture_face_uvs = [dekaron_mesh_vertices_uv[j] for j in dekaron_mesh_face.verts]
>
> 
>
>             dekaron_mesh_texture_face.uv1 = dekaron_mesh_texture_face_uvs[0]
>
>             dekaron_mesh_texture_face.uv2 = dekaron_mesh_texture_face_uvs[1]
>
>             dekaron_mesh_texture_face.uv3 = dekaron_mesh_texture_face_uvs[2]
>
> 
>
>     dekaron_mesh.update()
>
> 
>
>     dekaron_mesh_object = bpy.data.add_object("MESH", dekaron_mesh_name)
>
> 
>
>     dekaron_mesh_object.data = dekaron_mesh
>
> 
>
>     return dekaron_mesh_object
>
> 
>
> 
>
> def parse_dekaron_mesh_file_mesh0(dekaron_mesh_file):
>
>     dekaron_mesh_file_mesh_name_length = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     dekaron_mesh_file_mesh_name = dekaron_mesh_file.read(dekaron_mesh_file_mesh_name_length)
>
> 
>
>     dekaron_mesh_file_mesh_aabb = struct.unpack('<6f', dekaron_mesh_file.read(24))[0]
>
> 
>
>     dekaron_mesh_file_mesh_vertex_count = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     dekaron_mesh_file_mesh_vertices_co = []
>
> 
>
>     for i in range(dekaron_mesh_file_mesh_vertex_count):
>
>         dekaron_mesh_file_mesh_vertices_co.extend(list(struct.unpack('3f', dekaron_mesh_file.read(12))))
>
> 
>
>         dekaron_mesh_file.seek(28, os.SEEK_CUR)
>
> 
>
>     dekaron_mesh_file_mesh_index_count = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     dekaron_mesh_file_mesh_indices = []
>
> 
>
>     for i in range(int(dekaron_mesh_file_mesh_index_count / 3)):
>
>         dekaron_mesh_file_mesh_indices.extend(list(struct.unpack('<3H', dekaron_mesh_file.read(6))))
>
>         dekaron_mesh_file_mesh_indices.append(0)
>
> 
>
>     if len(dekaron_mesh_file_mesh_name) <= 0:
>
>         dekaron_mesh_file_mesh_name = os.path.splitext(os.path.basename(dekaron_mesh_file.name))[0]
>
> 
>
>     dekaron_mesh_file_mesh_bone_count = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     for i in range(dekaron_mesh_file_mesh_bone_count):
>
>         dekaron_mesh_file_mesh_bone_name_length = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>         dekaron_mesh_file_mesh_bone_name = dekaron_mesh_file.read(dekaron_mesh_file_mesh_bone_name_length)
>
> 
>
>     return create_dekaron_mesh(dekaron_mesh_file_mesh_name, \
>
>                                dekaron_mesh_file_mesh_vertices_co, \
>
>                                None, \
>
>                                dekaron_mesh_file_mesh_indices)
>
> 
>
> 
>
> def parse_dekaron_mesh_file_mesh3(dekaron_mesh_file):
>
>     def is_face_degenerate(face_indices):
>
>         if face_indices[0] == face_indices[1]:
>
>             return True
>
>         elif face_indices[0] == face_indices[2]:
>
>             return True
>
>         elif face_indices[1] == face_indices[2]:
>
>             return True
>
> 
>
>         return False
>
> 
>
>     dekaron_mesh_file_mesh_aabb = struct.unpack('<6f', dekaron_mesh_file.read(24))[0]
>
> 
>
>     dekaron_mesh_file_mesh_unknown_count0 = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     dekaron_mesh_file_mesh_indices = []
>
> 
>
>     for i in range(dekaron_mesh_file_mesh_unknown_count0):
>
>         dekaron_mesh_file_mesh_unknown0, \
>
>         dekaron_mesh_file_mesh_unknown1, \
>
>         dekaron_mesh_file_mesh_unknown2, \
>
>         dekaron_mesh_file_mesh_unknown3, \
>
>         dekaron_mesh_file_mesh_index_count = struct.unpack('<IIIII', dekaron_mesh_file.read(20))
>
> 
>
>         if dekaron_mesh_file_mesh_index_count > 0:
>
>             face_indices = list(struct.unpack('<2H', dekaron_mesh_file.read(4)))
>
> 
>
>             for j in range(2, dekaron_mesh_file_mesh_index_count):
>
>                 face_indices.append(struct.unpack('<H', dekaron_mesh_file.read(2))[0])
>
> 
>
>                 face_indices_copy = face_indices[:]
>
> 
>
>                 if not j % 2:
>
>                     face_indices_copy.reverse()
>
> 
>
>                 if is_face_degenerate(face_indices_copy) is False:
>
>                     dekaron_mesh_file_mesh_indices.extend(face_indices_copy)
>
>                     dekaron_mesh_file_mesh_indices.append(0)
>
> 
>
>                 face_indices.pop(0)
>
> 
>
>     dekaron_mesh_file_mesh_vertex_count = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     dekaron_mesh_file_mesh_vertices_co = []
>
>     dekaron_mesh_file_mesh_vertices_no = []
>
>     dekaron_mesh_file_mesh_vertices_uv1 = []
>
> 
>
>     for i in range(dekaron_mesh_file_mesh_vertex_count):
>
>         dekaron_mesh_file_mesh_vertices_co.extend(list(struct.unpack('3f', dekaron_mesh_file.read(12))))
>
>         dekaron_mesh_file_mesh_vertices_no.extend(list(struct.unpack('3f', dekaron_mesh_file.read(12))))
>
>         dekaron_mesh_file_mesh_vertex_uv1 = list(struct.unpack('2f', dekaron_mesh_file.read(8)))
>
> 
>
>         dekaron_mesh_file_mesh_vertex_uv1[1] = (1.0 - dekaron_mesh_file_mesh_vertex_uv1[1]) - 1.0
>
> 
>
>         dekaron_mesh_file_mesh_vertices_uv1.append(dekaron_mesh_file_mesh_vertex_uv1)
>
> 
>
>         dekaron_mesh_file.seek(24, os.SEEK_CUR)
>
> 
>
>     dekaron_mesh_file_mesh_bone_count = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     for i in range(dekaron_mesh_file_mesh_bone_count):
>
>         dekaron_mesh_file_mesh_bone_name_length = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>         dekaron_mesh_file_mesh_bone_name = dekaron_mesh_file.read(dekaron_mesh_file_mesh_bone_name_length)
>
> 
>
>     dekaron_mesh_file.seek(4, os.SEEK_CUR)
>
> 
>
>     return create_dekaron_mesh(os.path.splitext(os.path.basename(dekaron_mesh_file.name))[0], \
>
>                                dekaron_mesh_file_mesh_vertices_co, \
>
>                                dekaron_mesh_file_mesh_vertices_uv1, \
>
>                                dekaron_mesh_file_mesh_indices)
>
> 
>
> 
>
> def parse_dekaron_mesh_file_meshes(dekaron_mesh_file, dekaron_mesh_type):
>
>     dekaron_mesh_file_mesh_count = struct.unpack('<I', dekaron_mesh_file.read(4))[0]
>
> 
>
>     dekaron_mesh_objects = []
>
> 
>
>     for i in range(dekaron_mesh_file_mesh_count):
>
>         if dekaron_mesh_type == 0:
>
>             dekaron_mesh_objects.append(parse_dekaron_mesh_file_mesh0(dekaron_mesh_file))
>
>         elif dekaron_mesh_type == 3:
>
>             dekaron_mesh_objects.append(parse_dekaron_mesh_file_mesh3(dekaron_mesh_file))
>
> 
>
>     return dekaron_mesh_objects
>
> 
>
> 
>
> def parse_dekaron_mesh_file(dekaron_mesh_file):
>
>     dekaron_mesh_file_header_magic, \
>
>     dekaron_mesh_file_header_unknown0, \
>
>     dekaron_mesh_file_header_unknown1, \
>
>     dekaron_mesh_file_header_unknown2, \
>
>     dekaron_mesh_file_header_mesh_data_address0, \
>
>     dekaron_mesh_file_header_mesh_data_size0, \
>
>     dekaron_mesh_file_header_mesh_data_address1, \
>
>     dekaron_mesh_file_header_mesh_data_size1, \
>
>     dekaron_mesh_file_header_mesh_data_address2, \
>
>     dekaron_mesh_file_header_mesh_data_size2, \
>
>     dekaron_mesh_file_header_mesh_data_address3, \
>
>     dekaron_mesh_file_header_mesh_data_size3 = struct.unpack('<IIIIIIIIIIII', dekaron_mesh_file.read(48))
>
> 
>
>     dekaron_mesh_file_header_work_path = dekaron_mesh_file.read(64)
>
> 
>
>     if dekaron_mesh_file_header_magic != 0x20031117:
>
>         return
>
> 
>
>     dekaron_mesh_objects = []
>
> 
>
>     # Parse collision meshes
>
>     if dekaron_mesh_file_header_mesh_data_size0 >= 4:
>
>         dekaron_mesh_file.seek(dekaron_mesh_file_header_mesh_data_address0)
>
> 
>
>         dekaron_mesh_objects.extend(parse_dekaron_mesh_file_meshes(dekaron_mesh_file, 0))
>
> 
>
>     # Parse meshes
>
>     if dekaron_mesh_file_header_mesh_data_size3 >= 4:
>
>         dekaron_mesh_file.seek(dekaron_mesh_file_header_mesh_data_address3)
>
> 
>
>         dekaron_mesh_objects.extend(parse_dekaron_mesh_file_meshes(dekaron_mesh_file, 3))
>
> 
>
>     return dekaron_mesh_objects
>
> 
>
> 
>
> def import_dekaron_mesh_file_from_path(dekaron_mesh_file_path, context):   
>
> #    dekaron_mesh_scene = bpy.data.scenes.new()
>
> #    
>
> #    dekaron_mesh_scene.make_current()
>
> #    
>
>     with io.open(dekaron_mesh_file_path, mode='r+b') as dekaron_mesh_file:
>
>         dekaron_mesh_objects = parse_dekaron_mesh_file(dekaron_mesh_file)
>
> 
>
>         for dekaron_mesh_object in dekaron_mesh_objects:
>
>             context.scene.objects.link(dekaron_mesh_object)
>
> 
>
> 
>
> class ImportDekaronMeshFile(bpy.types.Operator):
>
>     '''Import Dekaron mesh'''
>
> 
>
>     bl_idname = "import_scene.dekaron_mesh"
>
>     bl_label = 'Import Dekaron Mesh'
>
> 
>
>     path = bpy.props.StringProperty(name="File Path", description="Dekaron mesh file path", maxlen= 1024, default= "")
>
> 
>
>     def execute(self, context):
>
>         import_dekaron_mesh_file_from_path(self.properties.path, context)
>
> 
>
>         return ('FINISHED',)
>
> 
>
>     def invoke(self, context, event):
>
>         window_manager = context.manager
>
> 
>
>         window_manager.add_fileselect(self)
>
> 
>
>         return ('RUNNING_MODAL',)
>
> 
>
> 
>
> bpy.ops.add(ImportDekaronMeshFile)
>
> 
>
> menu_function = lambda self, context: self.layout.operator(ImportDekaronMeshFile.bl_idname, text="Dekaron (.mesh)...")
>
> menu_item = dynamic_menu.add(bpy.types.INFO_MT_file_import, menu_function)
## Post #4
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2014-03-12T23:10:57+00:00
- Post Title: [REQUEST] Dekaron/2moons model exporter/importer

no new yet ?!
## Post #5
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2014-03-24T00:05:24+00:00
- Post Title: [REQUEST] Dekaron/2moons model exporter/importer

someone help me still waiting and interested on working on that ...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-24T07:00:36+00:00
- Post Title: [REQUEST] Dekaron/2moons model exporter/importer

what about FattyB from elitepvpers forum and his Dekaron .mesh exporter project from 3 years ago?
Seems he didn't finish it. (So I guess noone ever will write an exporter.)

But if you uploaded some .mesh samples (a character, an armor, a weapon and a small object like a book or a box for example) maybe someone will have a look at them.
