## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-25T13:11:55+00:00
- Post Title: Importing animations to blender

Does anyone have sample import scripts for to get animation into blender, along with samples from whatever game it imports?
I want to see what is imported and how it looks when I run the animation. There are probably a couple lying around but there's too many threads to search through.
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-08-25T13:18:25+00:00
- Post Title: Importing animations to blender

check milkshape importer for Blender249 in .scripts folder
Import psk model with psa animation to Milkshape and than save as milkshape format.
This file import to Blender249.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-26T03:00:17+00:00
- Post Title: Importing animations to blender

Found your war of dragons script that imports mesh and animations, then watched a cute spider walk around.
Ok, I see how animations work now.

Now I'm trying to texture the model but the textures don't get applied to the mesh (it's just all black).
I've been referencing your importers, but not sure where I might have messed up.

It should be just

1: create a material
2: create a texture
3: load an image
4: assign image to texture
5: assign texture to material
6: assign material to mesh

?

```
    
    def __init__(self, obj3D, dirPath):
	
			self.obj3D = obj3D
			self.dirPath = dirPath
	
    def add_texture(self, material, matNum):
	
			texName = self.obj3D.get_material_texture(matNum)
			texture = Blender.Texture.New(texName)
			texture.setType("Image")
	
			texPath = os.path.join(self.dirPath, texName)	
			#check if image already exists
			try:
					img = Blender.Image.get(texName)
					texture.image = img
					material.setTexture(0,texture,texture.TexCo.UV, texture.MapTo.COL)
			except:
					#Does not exist. Try to load it
					try:
				img = Blender.Image.Load(texPath) 
				texture.image = img
				material.setTexture(0,texture,Blender.Texture.TexCo.UV,Blender.Texture.MapTo.COL)
					except:
				print "couldn't load image: %s" %texName
					#print "Created new image", img
	    
    def add_vertex_uv(self, mesh, meshName):
	
			mesh.vertexUV = 1
			for i in xrange(len(mesh.verts)):
					uv = self.obj3D.get_vert_uv(meshName, i)
					mesh.verts[i].uvco = Blender.Mathutils.Vector(uv)
			mesh.update()
				
    def add_face_uv(self, mesh, meshName):
			
			mesh.faceUV = 1
			for face in mesh.faces:
					face.uv = [vert.uvco for vert in face.verts]
					#face.smooth = 1
			mesh.update()
	    
    def add_material(self, mesh, matNum):
	
			matName = self.obj3D.get_material_name(matNum)
			material = Blender.Material.New(matName)
			self.add_texture(material, matNum)

			print material.textures
			mesh.materials.append(material)
			mesh.update()
	
    def add_face_material(self, mesh, meshName):
	
			for i in xrange(len(mesh.faces)):
					matNum = self.obj3D.get_face_mat(meshName, i)
					mesh.faces[i].mat = matNum
	
    def draw_mesh(self):
	
			objects = self.obj3D.get_objects()
			for meshName in objects:
					mesh = bpy.data.meshes.new(meshName)
					print "drawing", meshName
					
					numVerts = self.obj3D.vert_count(meshName)
					vertices = []
					for i in xrange(numVerts):
				coords = self.obj3D.get_coords(meshName, i)
				vertices.append(coords)
					
					numFaces = self.obj3D.face_count(meshName)
					faces = []
					for i in xrange(numFaces):
				vertList = self.obj3D.get_face_verts(meshName, i)
				faces.append(vertList)
					
					mesh.verts.extend(vertices)
					mesh.faces.extend(faces,ignoreDups=True)
					
					matNum = self.obj3D.get_face_mat(meshName, 0)	    
					self.add_material(mesh, matNum)
					self.add_vertex_uv(mesh, meshName)
					self.add_face_uv(mesh, meshName)
					self.add_face_material(mesh, meshName)
				
					scene = bpy.data.scenes.active
					obj = scene.objects.new(mesh,meshName)
					mesh.recalcNormals()
					mesh.update()
					Blender.Window.RedrawAll()

```
