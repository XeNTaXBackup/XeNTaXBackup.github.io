## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-06T17:07:58+00:00
- Post Title: Blender import template

I can write scripts in python, but I don't want to take the time to spend reading blender's API because I don't see myself doing much with blender.

I want something very intuitive that anyone with basic programming knowledge would be able to write working import scripts. This way, if file format specs are available, people have a better chance of doing it themselves (because the biggest roadblock is "how do I draw the model?") Chances are, if I am someone that is only interested in modeling, and don't really understand programming but have a very slight idea how it works, I'm not going to be motivated enough to learn blender scripting.

And it's not about being lazy, though in my case it is.
For those that would argue that it's up to the user to learn it themselves "if they really wanted it": have you ever programmed without using a single library that wasn't written by yourself? If you have, that's great, but is that very productive? Efficient? effective? Bug-free?

Requirements:

-the user does not need to know anything about the functions that load the model. We can assume the user is a skilled modeler and can use blender, but just doesn't know how to load a model cause that's "techy programming stuff".

-a set of functions should be available to allow the user to provide the data required to draw the model. The user should not need to think about how to store the data

For instance, if your Vertex object needs coords, normals, and texcoords, then write three separate functions like "add_coords", "add_normals", and "add_texcoords" that will take an arbitrary number of parameters and then load them into some data structure (ie: a list of lists maybe, or what you think would be most optimal). Then the internal function that will actually create the Vertex will grab the data from these lists, and the user only needs to say "these are my coords and my normals" and move on.

-works for versions that are probably in use the most, like 2.49 and 2.57, so people have a choice which they want to use.

Essentially, all the user needs to do is fill in a parser function and call the appropriate functions that will accept their data. The user can follow existing file specs to parse the file, and that is all that is required. Then anyone can write good blender importers.

Anyone up for it?

A general outline would look like

```
...
#global declarations and stuff
...
#"private" things I don't need to know about that tells blender what to do
...
#functions that I will interface with to store the data without knowing the data structures
#efficiency is not important here, as having all of these extra interfaces rather than
#accessing the objects directly will definitely slow things down
def add_vertex(...)
   '''SAMPLE: Appends a Vertex object to the list of vertices'''
...
#parser function wrapper (if necessary)
...
#parser function
#TO-DO - this is what the user will fill in

```


EDIT: thinking about it, you should probably place the parser function at the top so people don't have to scroll past all the stuff they don't need to know about.
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-06T20:07:07+00:00
- Post Title: Blender import template

The explanation i search jojojo, thanks man its very good.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-24T17:08:20+00:00
- Post Title: Blender import template

I'll be writing some sort of template that will integrate the Sanae 3D converter to blender so I can pass any objects to some drawing functions. It'll pretty much be based on Szkaradek123's import scripts though since it appears he uses his own template since all of the drawing functions are the same.

After that, I guess I could just take the drawing functions and move them into its own import template with a custom set of functions since it won't be using my model3D class.

Noesis also supports plugins written in python so if people want models they can use that to write their import scripts and export from there.

EDIT: actually, I should start with the template to actually verify that I can get something to work.

A really easy way to do it would be to just copy all of the classes I've written into a script, write a new class called Drawer or something, then pass the model3D object to this drawer. To import a different format, just copy the class from the appropriate plugin and it'll work.

But there's too much manual work involved, so a better way needs to be used.

Here's a simple blender import class that takes the model3D object and draws it. I just took it off some tutorial and told it to load from a custom object rather than while it's reading from the file. All I need to do is add more methods to load bones and stuff.

Another issue I guess would be, blender 2.57 or 2.49? (or even 2.58).

```
	
	def __init__(self, obj3D):

		self.obj3D = obj3D

	def draw_mesh(self):

		mesh = Blender.NMesh.New(meshName)
		
		meshName = self.obj3D.get_objects()[0]
		numVerts = self.obj3D.vert_count(meshName)
		for i in xrange(numVerts):
				vx, vy, vz = self.obj3D.get_coords(meshName, i)
				mesh.verts.append(Blender.NMesh.Vert(vx, vy, vz))
				
		numFaces = self.obj3D.face_count(meshName)
		for i in xrange(numFaces):
				v1, v2, v3 = self.obj3D.get_face_verts(meshName, i)
				mesh.faces.append(Blender.NMesh.Face([f1, f2, f3]))
		
		ob = Blender.Object.New('Mesh', meshName) 
		ob.link(mesh) # tell the object to use the mesh we just made
		scn = Blender.Scene.GetCurrent()
		for o in scn.objects:
				o.sel = 0
		
		scn.link(ob) # link the object to the current scene
		ob.sel= 1
		ob.Layers = scn.Layers
		#Blender.Window.WaitCursor(0)
		Blender.Window.RedrawAll()

```
